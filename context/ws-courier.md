# ws-courier.pdf

## 1. Общая информация об API

- **Базовый URL тестового сервера:** `http://courier-test.esphere.ru/api` или `https://courier-demo-api.esphere.ru`
- **Формат данных:** JSON по умолчанию для методов `v2.0`. XML доступен при заголовке `Accept: application/xml`.
- **Кодировка файлов:** Все бинарные данные (содержимое документов, подписи) передаются в Base64.
- **Авторизация:** Через HTTP-заголовок `Auth-Token`, полученный при аутентификации (`Logon` или `LogonByApiKey`). Время жизни токена — 24 часа.

---

## 2. Аутентификация

### 2.1. Получение токена по логину/паролю
**Метод:** `POST /api/auth/logon`  
**Тело запроса (XML):**
```xml
<Credentials>
    <Username>your_login</Username>
    <Password>your_password</Password>
</Credentials>
```
**Ответ (JSON):**
```json
{
    "token": "15FAA504AD7A39074557A1ED96419D70C436402D08AFD897890CA5E...C9F6"
}
```
**Действие:** Токен из ответа передавать в заголовке `Auth-Token` всех последующих запросов.

### 2.2. Имперсонализация (работа под другим пользователем)
Для выполнения методов от имени другого сотрудника компании добавьте HTTP-заголовок `Thumbprint` с отпечатком сертификата целевого пользователя (у него должна быть роль "Имперсонализация").

---

## 3. Поиск контрагента и определение идентификатора ЭДО (для роуминга)

### 3.1. Поиск организации по ИНН/КПП
**Метод:** `POST /api/dictionary/findClient`  
**Тело запроса (JSON):**
```json
{
    "inn": "1234567890",
    "kpp": "123456789"
}
```
**Ответ:** Структура `Company`, содержащая поле `Code` — идентификатор участника ЭДО (ИдУчЭДО), необходимый для отправки документов в роуминге (например, `2BK-1234567890123-...`).

### 3.2. Получение идентификатора ЭДО напрямую
**Метод:** `GET v2.0/client/ediCode?inn={inn}&kpp={kpp}&documentTypeCode={code}`  
Возвращает структуру `ClientEdiCode` с полем `Code`.

### 3.3. Получение информации о взаимосвязях (активных контрагентах)
**Метод:** `GET /api/dictionary/contractorDocumentTypes`  
Возвращает список контрагентов с доступными типами документов для обмена.

---

## 4. Формирование основного документа: УПД версии 5.03

### 4.1. Создание XML УПД из упрощённой модели
**Метод:** `POST /api/document/createinvoice/{receiverCode}`  
- `receiverCode` — опциональный параметр; если не указан, поиск получателя ведётся по `ИНН+КПП` из данных `Invoice`.
- Тело запроса: структура `Invoice` с версией формата `FormatVersion="5.03"`.

**Ключевые поля `Invoice` для УПД 5.03:**
- `FormatVersion="5.03"`
- `FormatCode="1115131"`
- `Number`, `Date`, `CurrencyCode`
- `Seller` и `Buyer` (структуры `BuyerSeller` с идентификацией и адресом)
- `Rows` — массив `InvoiceRow` (товары/услуги)
- `DocumentSignerInfo` — информация о подписанте (обязательно при `Date >= 01.07.2017`)
- `ProductGroup` — группы товаров (новое для 5.03)
- `AccompanyingDocumentsInfo` — сведения о сопроводительных документах (опционально)

**Пример минимального запроса:**
```json
{
  "FormatVersion": "5.03",
  "FormatCode": "1115131",
  "Number": "1001",
  "Date": "2026-01-15T00:00:00",
  "CurrencyCode": "643",
  "Seller": {
    "IdentificationInfo": {
      "Organization": {
        "Name": "ООО Продавец",
        "Inn": "1234567890",
        "Kpp": "123456789"
      }
    },
    "Address": {
      "Local": { "RegionCode": "77" }
    }
  },
  "Buyer": {
    "IdentificationInfo": {
      "Organization": {
        "Name": "ООО Покупатель",
        "Inn": "0987654321",
        "Kpp": "987654321"
      }
    },
    "Address": {
      "Local": { "RegionCode": "78" }
    }
  },
  "Rows": [
    {
      "Name": "Товар 1",
      "Unit": "796",
      "Amount": 10,
      "Price": 100.0,
      "NetSum": 1000.0,
      "TotalSum": 1200.0,
      "VatType": "20%",
      "VatSum": 200.0
    }
  ],
  "DocumentSignerInfo": [
    {
      "Signer": {
        "Inn": "1234567890",
        "Name": "ООО Продавец",
        "Person": {
          "LastName": "Иванов",
          "FirstName": "Иван"
        },
        "SignerType": "Organization",
        "Title": "Генеральный директор"
      },
      "SignerAuthority": {
        "Authority": "Устав",
        "AuthorityScope": 1,
        "Condition": 1
      }
    }
  ]
}
```
**Ответ:** `FileContent` — готовый XML-файл УПД в Base64.

### 4.2. Ручное формирование и загрузка УПД
Если УПД формируется внешней системой, используется метод `Document.Add` (см. раздел 5).

---

## 5. Отправка документов (одиночных и пакетов)

### 5.1. Добавление одного документа (в статус «Черновик»)
**Метод:** `POST /api/document/add/{receiverCode}`  
**Тело запроса:** `DocumentCard`

**Структура `DocumentCard` (ключевые поля):**
```json
{
  "Number": "Док-001",
  "Date": "2026-01-15T00:00:00",
  "TypeCode": "UPD_SF_DOP",
  "Content": {
    "Filename": "UPD_5.03.xml",
    "MimeType": "application/xml",
    "Content": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz48..."
  },
  "Signature": {
    "Content": "MIIETTCCA/qgAwIBAgIKKEwQmQAAAAAAejAKBgYqhQMCAgMFADCBsDEfMB0GCSqG....OQ=="
  },
  "Properties": [ // Дополнительные свойства (опционально)
    {
      "Key": "system.sendingGIS",
      "Value": "CZ.FIX"
    }
  ]
}
```
- Если передан `Signature`, документ будет подписан и продвинут по маршруту.
- Без подписи сохраняется в «Черновиках».

**Ответ:** Структура `Document` с `Id` созданного документа.

### 5.2. Добавление пачки документов (включая пакет)
**Метод:** `POST /api/document/addBatch/{receiverCode}`  
**Тело запроса:** `DocumentBatch`

**Структура `DocumentBatch`:**
```json
{
  "Documents": [
    {
      "Number": "УПД-001",
      "Date": "2026-01-15T00:00:00",
      "TypeCode": "UPD_SF_DOP",
      "Content": { ... },
      "Signature": { ... }
    },
    {
      "Number": "Спецификация",
      "Date": "2026-01-15T00:00:00",
      "TypeCode": "ACT", // или другой код неформализованного документа
      "Content": {
        "Filename": "specification.pdf",
        "MimeType": "application/pdf",
        "Content": "JVBERi0xLjQKJeLjz9MK..."
      }
    }
  ],
  "LinkToFirst": true,           // все документы ссылаются на первый как на родительский
  "CreatePackage": true,         // объединить документы в пакет
  "PackageName": "Пакет от 15.01.2026",
  "SendSync": true               // признак одновременной отправки получателю
}
```
- `CreatePackage: true` — создаёт пакет, в котором документы будут обрабатываться совместно.
- Документы можно добавить без подписи (статус «Черновик»), затем подписать позже.

**Ответ:** Массив структур `Document` (созданные документы).

### 5.3. Объединение существующих документов в пакет
**Метод:** `POST /v2.0/package`  
**Тело запроса:** `DocumentPackage`
```json
{
  "Name": "Пакет документов",
  "SendSync": true,
  "Documents": [12345, 12346, 12347] // массив ID документов
}
```
**Ответ:** `integer` — ID созданного пакета.

### 5.4. Добавление документов в существующий пакет
**Метод:** `PUT /v2.0/package/{packageId}/documents`  
**Тело запроса:** `ArrayOflong` — массив ID документов.

### 5.5. Получение сведений о составе пакета
**Метод:** `GET /v2.0/package/{packageId}`  
**Ответ:** `PackageCard` с массивом `PackageDocument`.

---

## 6. Подписание документов

### 6.1. Подписание документа (продвижение по маршруту)
**Метод:** `POST /api/document/sign/{documentId}`  
**Тело запроса:** `SignatureWithTicket`
```json
{
  "Content": "MIIETTCCA/qgAwIBAgIKKEwQmQAAAAAAejAKBgYqhQMCAgMFADCBsDEfMB0GCSqG....OQ=="
}
```
- `Content` — отсоединённая подпись в формате PKCS#7, закодированная в Base64.

### 6.2. Принятие документа (для УПД, требующих ответного титула)
**Метод:** `POST /api/document/accept/{documentId}`  
**Тело запроса:** `SignedContent` с подписанной квитанцией.

Для УПД, требующих формирования титула покупателя, используется `Document.AcceptTitle v.2`.

---

## 7. Работа с неформализованными документами и вложениями

### 7.1. Добавление приложения к документу в статусе «Черновик»
**Метод:** `POST /api/document/addAttachment/{documentId}`  
**Тело запроса:** `FileContent`
```json
{
  "Filename": "attachment.pdf",
  "MimeType": "application/pdf",
  "Content": "JVBERi0xLjQK..."
}
```

### 7.2. Отправка неформализованных документов через XML-карты (аналог SFERAConnector)
Хотя API поддерживает прямую отправку через `Document.Add` с типом `Document`, для сложных сценариев с дополнительными атрибутами можно использовать подход, аналогичный SFERAConnector:

**Структура XML-карты (`DocumentCard` с атрибутами):**
```xml
<DocumentCard>
    <Number>Док-001</Number>
    <Date>2026-01-15</Date>
    <TypeCode>ACT</TypeCode>
    <Content>
        <Filename>act.pdf</Filename>
        <MimeType>application/pdf</MimeType>
        <Content>JVBERi0xLjQK...</Content>
    </Content>
    <Attributes>
        <KeyValueObject>
            <Key>2701</Key> <!-- ID справочника -->
            <Value>Значение атрибута</Value>
        </KeyValueObject>
    </Attributes>
</DocumentCard>
```
Для получения списка обязательных атрибутов используется метод `Classifier.Template`.

---

## 8. Обработка входящих документов и квитанций

### 8.1. Получение списка документов на обработку
**Метод:** `POST /api/document/list`  
**Фильтр `ApiDocumentFilter`:**
```json
{
  "Folder": "OnProcess", // "Draft", "Inbox", "Outbox", "Processed", "Trash"
  "Take": 50,
  "Skip": 0
}
```

### 8.2. Получение содержимого документа
**Метод:** `GET v2.0/document/{id}/content` → `FileContent`

### 8.3. Получение подписей документа
**Метод:** `GET /api/document/getsignatures/{id}` → массив `DocumentSign`

### 8.4. Отслеживание событий (рекомендуется использовать подписки)
**Создание подписки:** `PUT v2.0/subscription?isRestricted=false`  
**Получение событий:** `GET v2.0/subscription/{token}/event/totals?count=100` → `DocumentEvents`

---

## 9. Роуминг: настройка и отправка

### 9.1. Проверка наличия взаимосвязи
**Метод:** `GET v2.0/relation/correlated` с параметрами `inn`, `kpp` или `ediCode`.  
Возвращает `RelationInfo` со списком активных взаимосвязей и типами документов.

### 9.2. Создание запроса на взаимосвязь (приглашение)
**Метод:** `PUT v2.0/relation-request`  
**Тело:** `RelationRequest`
```json
{
  "ReceiverInn": "0987654321",
  "ReceiverKpp": "987654321",
  "OperatorCode": "2BK",
  "AbonentCode": "2BK-...",
  "Email": "partner@example.com"
}
```

### 9.3. Отправка документов в роуминг
При отправке через `Document.Add` или `Document.AddBatch` необходимо:
- Указать корректный `receiverCode` (идентификатор участника ЭДО получателя, полученный из `ClientEdiCode`).
- Убедиться, что взаимосвязь по данному типу документа активна (`RelationCorrelated`).

---

## 10. Дополнительные сведения

### 10.1. МЧД (машиночитаемые доверенности)
Согласно требованию, МЧД не требуется. Однако API поддерживает передачу сведений о МЧД в полях `MchdUuid`, `MchdFile`, `MchdPaper` в структурах `Signature`, `SignedContent`, `DocumentSigner`. При необходимости их можно игнорировать.

### 10.2. Ограничения
- Максимальный размер файла документа — явно не указан в API, но рекомендуется придерживаться лимита 70 МБ (как в SFERAConnector).
- Имя файла не должно содержать символов `/ \ : ? *` и быть длиннее 250 символов.

### 10.3. Коды типов документов (наиболее используемые)
| Код          | Описание                                   |
|--------------|--------------------------------------------|
| `UPD_SF`     | УПД. Счёт-фактура                          |
| `UPD_DOP`    | УПД. Документ об отгрузке                  |
| `UPD_SF_DOP` | УПД. Счёт-фактура + документ об отгрузке   |
| `ACT`        | Акт выполненных работ (неструктурированный)|
| `TN`         | Товарная накладная (неструктурированная)   |
| `AGREEMENT`  | Договор                                    |

---

## 11. Рекомендованный алгоритм интеграции для 1С

1. **Аутентификация:** Получить токен через `Logon`.
2. **Определение получателя:**
   - По ИНН/КПП контрагента получить `Company` и его `Code` (ИдУчЭДО).
   - Проверить наличие активной взаимосвязи (`RelationCorrelated`), при необходимости создать запрос (`RelationRequest.AddRequest`).
3. **Формирование пакета:**
   - Создать УПД через `Document.CreateInvoice` (версия 5.03) или сформировать XML вручную.
   - Подготовить неформализованные документы (PDF и др.) в виде `FileContent` (Base64).
   - Вызвать `Document.AddBatch` с `CreatePackage: true` и `PackageName`.
4. **Подписание:**
   - Если требуется подпись отправителя, подписать каждый документ через `Document.Sign`.
   - Для УПД, требующих ответного титула, обрабатывать входящие события и формировать `Document.AcceptTitle`.
5. **Отслеживание статусов:** Использовать подписки (`Subscription`) или периодический опрос `Document.List`.

---

## 12. Полезные ссылки из документации

- **Тестовый сервер:** `http://courier-test.esphere.ru/api`
- **Страница истории изменений:** раздел 1.1 PDF (учёт новых требований ФНС).
- **Описание структур данных:** раздел 1.4 PDF (ключевые структуры: `Invoice`, `DocumentCard`, `DocumentBatch`, `PackageCard`).