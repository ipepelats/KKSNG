
## Принципы Объединения Документов в Пакет при Отправке по ЭДО через Роуминг: Детальный Анализ

В современном деловом мире электронный документооборот (ЭДО) стал стандартом для обмена юридически значимыми документами [[1]](https://nopaper.ru/faq/ehdo-zakony)[[2]](https://endocs.ru/zakonodatelstvo-ob-edo-kakie-novye-zakony-izmenyat-vashu-rabotu-s-dokumentami/) . Часто возникает необходимость отправить не один документ, а целый комплект, связанный с одной сделкой, например, формализованный универсальный передаточный документ (УПД) и сопутствующие ему договор, спецификацию или отчет в свободном формате [[3]](https://xn--80ahbomx.xn--p1ai/%D0%BD%D0%BE%D0%B2%D0%BE%D1%81%D1%82%D0%B8/%D0%B2-%D1%87%D0%B5%D0%BC-%D1%80%D0%B0%D0%B7%D0%BD%D0%B8%D1%86%D0%B0-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D0%BC%D0%B8-%D0%B2-%D1%8D%D0%B4%D0%BE/)[[4]](https://www.diadoc.ru/articles/22582-formalizovannye_i_neformalizovannye_dokumenty) . В данном исследовании мы подробно рассмотрим принципы, по которым эти документы объединяются в единый пакет для отправки контрагенту, в том числе через роуминг, а также рассмотрим полный жизненный цикл такого пакета, включая обработку ошибок, исправление и процедуру аннулирования.

### 1. Нормативно-правовая база ЭДО

В России не существует единого закона, который бы полностью описывал электронный документооборот [[1]](https://nopaper.ru/faq/ehdo-zakony)[[2]](https://endocs.ru/zakonodatelstvo-ob-edo-kakie-novye-zakony-izmenyat-vashu-rabotu-s-dokumentami/)[[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote) . Регулирование этой сферы представляет собой комплексную систему, состоящую из нескольких ключевых федеральных законов и подзаконных актов, издаваемых преимущественно Федеральной налоговой службой (ФНС) [[6]](https://astral.ru/aj/elem/zakony-ob-elektronnom-dokumentooborote-rf/) .

#### Федеральные законы:

*   **ФЗ-63 «Об электронной подписи»**: Это основополагающий закон, который определяет виды электронных подписей и придает юридическую значимость электронным документам [[1]](https://nopaper.ru/faq/ehdo-zakony)[[7]](https://elma365.com/ru/articles/zakon-ob-edo/)[[6]](https://astral.ru/aj/elem/zakony-ob-elektronnom-dokumentooborote-rf/) . Для обмена счетами-фактурами и предоставления документов в госорганы требуется усиленная квалифицированная электронная подпись (УКЭП) [[8]](https://nopaper.ru/faq/ehdo-formalizovannye-i-neformalizovannye-dokumenty)[[9]](https://elma365.com/ru/articles/yuridicheski-znachimyi-elektronnyi-dokumentooborot/) .
*   **ФЗ-402 «О бухгалтерском учете»**: Закрепляет возможность создавать и хранить первичные учетные документы в электронном виде при условии их подписания электронной подписью .
*   **Налоговый кодекс РФ**: Статья 169 НК РФ устанавливает требования к электронным счетам-фактурам, а статья 93 — к порядку предоставления электронных документов в налоговые органы [[2]](https://endocs.ru/zakonodatelstvo-ob-edo-kakie-novye-zakony-izmenyat-vashu-rabotu-s-dokumentami/)[[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote) .
*   **Гражданский кодекс РФ**: Статьи 160 и 434 ГК РФ допускают заключение договоров и совершение сделок путем обмена электронными документами, что является правовой основой для B2B-взаимодействия [[1]](https://nopaper.ru/faq/ehdo-zakony)[[2]](https://endocs.ru/zakonodatelstvo-ob-edo-kakie-novye-zakony-izmenyat-vashu-rabotu-s-dokumentami/)[[6]](https://astral.ru/aj/elem/zakony-ob-elektronnom-dokumentooborote-rf/) .
*   **ФЗ-149 «Об информации, информационных технологиях и о защите информации»**: Регулирует общие вопросы, связанные с документооборотом в электронной форме [[1]](https://nopaper.ru/faq/ehdo-zakony)[[7]](https://elma365.com/ru/articles/zakon-ob-edo/) .

#### Приказы ФНС и форматы документов:

ФНС утверждает форматы для так называемых **формализованных документов**. Это файлы в формате XML, имеющие строго определенную структуру, что позволяет автоматизировать их обработку [[10]](https://www.esphere.ru/blog/chem-otlichayutsya-formalizovannye-elektronnye-dokumenty-ot-neformalizovannykh/)[[3]](https://xn--80ahbomx.xn--p1ai/%D0%BD%D0%BE%D0%B2%D0%BE%D1%81%D1%82%D0%B8/%D0%B2-%D1%87%D0%B5%D0%BC-%D1%80%D0%B0%D0%B7%D0%BD%D0%B8%D1%86%D0%B0-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D0%BC%D0%B8-%D0%B2-%D1%8D%D0%B4%D0%BE/) .

*   **Формализованные документы:** К ним относятся счета-фактуры, универсальные передаточные документы (УПД) и их корректировочные формы (УКД) [[3]](https://xn--80ahbomx.xn--p1ai/%D0%BD%D0%BE%D0%B2%D0%BE%D1%81%D1%82%D0%B8/%D0%B2-%D1%87%D0%B5%D0%BC-%D1%80%D0%B0%D0%B7%D0%BD%D0%B8%D1%86%D0%B0-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D0%BC%D0%B8-%D0%B2-%D1%8D%D0%B4%D0%BE/)[[4]](https://www.diadoc.ru/articles/22582-formalizovannye_i_neformalizovannye_dokumenty) . Актуальный формат УПД и счета-фактуры утвержден **Приказом ФНС от 19.12.2023 № ЕД-7-26/970@**. Обмен такими документами с ФНС возможен только через аккредитованных операторов ЭДО [[10]](https://www.esphere.ru/blog/chem-otlichayutsya-formalizovannye-elektronnye-dokumenty-ot-neformalizovannykh/) .
*   **Неформализованные документы:** Это любые документы в произвольном формате (PDF, DOCX, JPG), для которых ФНС не установила строгих требований к структуре [[8]](https://nopaper.ru/faq/ehdo-formalizovannye-i-neformalizovannye-dokumenty)[[3]](https://xn--80ahbomx.xn--p1ai/%D0%BD%D0%BE%D0%B2%D0%BE%D1%81%D1%82%D0%B8/%D0%B2-%D1%87%D0%B5%D0%BC-%D1%80%D0%B0%D0%B7%D0%BD%D0%B8%D1%86%D0%B0-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D0%BC%D0%B8-%D0%B2-%D1%8D%D0%B4%D0%BE/) . К ним относятся договоры, спецификации, отчеты, письма и т.д. [[8]](https://nopaper.ru/faq/ehdo-formalizovannye-i-neformalizovannye-dokumenty)[[11]](https://edo.ru/integration/api-edopotok) . Подписанные УКЭП, они обладают полной юридической силой, эквивалентной бумажному документу с собственноручной подписью [[12]](https://www.diadoc.ru/docs/faq/faq-127) .

### 2. Концепция и Технические Принципы Формирования Пакета

Ключевой принцип, который необходимо понять: **пакет документов в ЭДО — это не единый файл, а логическая совокупность нескольких независимых электронных документов** . Каждый документ в пакете, будь то формализованный XML-файл или неформализованный PDF-договор, является самостоятельным юридически значимым документом, подписанным электронной подписью [[13]](https://xn--n1adei3c.xn--p1ai/services/) . Объединение в пакет служит для того, чтобы установить и зафиксировать смысловую связь между ними, относя их к одной хозяйственной операции [[14]](https://developer.kontur.ru/doc/diadoc-api/glossary/packet.html) .

Формирование пакета происходит на стороне системы оператора ЭДО, как правило, через вызовы API [[11]](https://edo.ru/integration/api-edopotok) . Хотя для пользователя это выглядит как простое "прикрепление файлов", в фоновом режиме запускается стандартизированный технический процесс.

#### 2.1. Сравнительный анализ API ведущих операторов

Каждый оператор ЭДО предлагает свой набор API-методов и моделей данных для отправки пакетов документов .

*   **Контур.Диадок**:
    *   **Подход**: Используется модель "сообщений" и "пакетов" [[1]](https://nopaper.ru/faq/ehdo-zakony) . Отправка выполняется единым асинхронным вызовом метода `POST /V3/PostMessage` [[15]](https://xn--n1adei3c.xn--p1ai/roaming/) .
    *   **Связывание**: В теле запроса `MessageToPost` передается массив вложений `DocumentAttachments` [[16]](https://www.diadoc.ru/articles/44466-yuridicheski_znachimyy_elektronnyy_dokumentooborot) . Связь устанавливается внутри одного запроса: основному документу (УПД) присваивается временный `CustomDocumentId`, а сопутствующий документ (договор) ссылается на него через поле `InitialDocumentIds` [[17]](https://www.diadoc.ru/articles/53174-otpravka_paketa_dokumentov_po_edo)[[18]](https://help.docsvision.com/dv5/edi/5.5.5/_exports/edi-5.5.5.pdf) . Все документы в одном вызове автоматически объединяются в пакет с общим `PacketId` [[2]](https://endocs.ru/zakonodatelstvo-ob-edo-kakie-novye-zakony-izmenyat-vashu-rabotu-s-dokumentami/)[[19]](https://edo.mig24.ru/help/api) .

*   **СБИС (Saby)**:
    *   **Подход**: Оперирует объектами "Документ", которые могут содержать множество вложений и иметь "редакции" [[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote) . Пакет создается и отправляется через команду `СБИС.ЗаписатьДокумент` по протоколу JSON-RPC [[20]](https://www.esphere.ru/products/edo/faq/kak-podpisat-dokument-v-edo/)[[11]](https://edo.ru/integration/api-edopotok) .
    *   **Связывание**: Все файлы (УПД, договор) передаются как массив "Вложение" внутри одного объекта "Документ" [[21]](https://developer.kontur.ru/Docs/Diadoc_UM/methods/JeDO_Podgotovit%27IOtpravit%27Paket.html) . Для связи с ранее созданным документом-основанием используется объект `ДокументОснование`, в котором указывается его идентификатор [[8]](https://nopaper.ru/faq/ehdo-formalizovannye-i-neformalizovannye-dokumenty)[[22]](https://markirovka.ru/knowledge/tovarnye-gruppy/tabachniye-izdeliya/podacha-upd-v-novom-formate-cherez-edo-layt-motp-atp-nsp-nszh-i-pivnaya-produktsiya)[[23]](https://www.delta-i.ru/print/articles/poleznaya-informacziya/rouming-v-edo-kak-nastroit-obmen-mezhdu-kontur-diadok-sbis-tenzor-i-1s/) .

*   **Такском**:
    *   **Подход**: Используется концепция "транспортного контейнера" (ZIP-архива), который отправляется через Web API (метод `SendMessage`) или обрабатывается утилитой "Такском-Ассистент" [[10]](https://www.esphere.ru/blog/chem-otlichayutsya-formalizovannye-elektronnye-dokumenty-ot-neformalizovannykh/)[[3]](https://xn--80ahbomx.xn--p1ai/%D0%BD%D0%BE%D0%B2%D0%BE%D1%81%D1%82%D0%B8/%D0%B2-%D1%87%D0%B5%D0%BC-%D1%80%D0%B0%D0%B7%D0%BD%D0%B8%D1%86%D0%B0-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D0%BC%D0%B8-%D0%B2-%D1%8D%D0%B4%D0%BE/)[[24]](https://taxcom.ru/baza-znaniy/novosti-partnyerov/novosti/rouming-v-edo-chto-nuzhno-znat-o-tekhnologii/)[[13]](https://xn--n1adei3c.xn--p1ai/services/) .
    *   **Связывание**: Связь между документами устанавливается в служебном файле `card.xml` (или `meta.xml`), который сопровождает каждый документ в контейнере [[12]](https://www.diadoc.ru/docs/faq/faq-127)[[25]](https://xn--n1adei3c.xn--p1ai/news/roaming-upd-117/)[[15]](https://xn--n1adei3c.xn--p1ai/roaming/) . В XML-описании сопутствующего документа добавляется параметр `AdditionalParameter` с именем `LinkedDocument`, значение которого равно `docflowId` (идентификатору документооборота) основного документа [[26]](https://www.diadoc.ru/Files/userfiles/file/news/EDO_TechnologyV2.doc) .

### 3. Особенности Передачи Пакетов в Роуминге (Технология РОСЭУ)

**Роуминг в ЭДО** — это технология, которая обеспечивает обмен документами между контрагентами, использующими разных операторов ЭДО [[7]](https://elma365.com/ru/articles/zakon-ob-edo/)[[8]](https://nopaper.ru/faq/ehdo-formalizovannye-i-neformalizovannye-dokumenty) . Ассоциация "РОСЭУ" (Разработчики и операторы систем электронных услуг) разработала технологию, стандартизирующую это взаимодействие [[1]](https://nopaper.ru/faq/ehdo-zakony)[[2]](https://endocs.ru/zakonodatelstvo-ob-edo-kakie-novye-zakony-izmenyat-vashu-rabotu-s-dokumentami/)[[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote)[[12]](https://www.diadoc.ru/docs/faq/faq-127)[[27]](https://saby.ru/help/integration/api/doc_guide) . Поддержка пакетной передачи документов была утверждена в версии технологии v1.17, что стало основой для реализации сложных сценариев обмена [[4]](https://www.diadoc.ru/articles/22582-formalizovannye_i_neformalizovannye_dokumenty)[[27]](https://saby.ru/help/integration/api/doc_guide) .

#### 3.1. Технологическая схема роуминга

1.  **Маршрутизация**: Документ от отправителя поступает к его оператору (Оператор 1) [[28]](https://saby.ru/help/integration/api/sequence/ep) .
2.  **Упаковка**: Оператор 1 упаковывает все файлы пакета и метаданные в специальный **транспортный контейнер (ТП)** [[28]](https://saby.ru/help/integration/api/sequence/ep)[[29]](https://saby.ru/help/integration/api/documents)[[22]](https://markirovka.ru/knowledge/tovarnye-gruppy/tabachniye-izdeliya/podacha-upd-v-novom-formate-cherez-edo-layt-motp-atp-nsp-nszh-i-pivnaya-produktsiya) .
3.  **Передача**: Контейнер передается по защищенному протоколу **HTTPS** оператору получателя (Оператор 2) .
4.  **Распаковка и доставка**: Оператор 2 распаковывает контейнер, проверяет его целостность, содержимое и доставляет документы получателю в его систему ЭДО [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf) .
5.  **Обмен квитанциями**: Для обеспечения гарантированной доставки операторы обмениваются **технологическими квитанциями (ТК)**, которые фиксируют факт передачи и результат обработки [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf)[[11]](https://edo.ru/integration/api-edopotok) .

#### 3.2. Структура транспортного контейнера и файла-описания

Транспортный пакет (ТП) представляет собой **ZIP-архив**, подписанный электронной подписью оператора-отправителя [[28]](https://saby.ru/help/integration/api/sequence/ep)[[29]](https://saby.ru/help/integration/api/documents)[[22]](https://markirovka.ru/knowledge/tovarnye-gruppy/tabachniye-izdeliya/podacha-upd-v-novom-formate-cherez-edo-layt-motp-atp-nsp-nszh-i-pivnaya-produktsiya)[[31]](https://xn--n1adei3c.xn--p1ai/upload/iblock/a93/%D0%A2%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F%20%D0%A0%D0%9E%D0%A1%D0%AD%D0%A3%20%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%201.15%20%D0%BE%D1%82%2011.01.2021.pdf) . Архив не использует шифрование [[32]](https://71.rosstat.gov.ru/storage/mediabank/%D0%A3%D0%BD%D0%B8%D1%84%D0%B8%D1%86%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B9%20%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%20%D1%82%D1%80%D0%B0%D0%BD%D1%81%D0%BF%D0%BE%D1%80%D1%82%D0%BD%D0%BE%D0%B3%D0%BE%20%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D1%8F.pdf)[[26]](https://www.diadoc.ru/Files/userfiles/file/news/EDO_TechnologyV2.doc) . Внутри него содержатся одно или несколько **логических сообщений (ЛС)** [[14]](https://developer.kontur.ru/doc/diadoc-api/glossary/packet.html)[[28]](https://saby.ru/help/integration/api/sequence/ep)[[29]](https://saby.ru/help/integration/api/documents)[[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf)[[22]](https://markirovka.ru/knowledge/tovarnye-gruppy/tabachniye-izdeliya/podacha-upd-v-novom-formate-cherez-edo-layt-motp-atp-nsp-nszh-i-pivnaya-produktsiya) .

*   **Структура каталогов**: Для каждого логического сообщения внутри ZIP-архива создается отдельная директория, имя которой является уникальным идентификатором (GUID) этого сообщения [[14]](https://developer.kontur.ru/doc/diadoc-api/glossary/packet.html) . Впрочем, регламент не предписывает строгую иерархию, и все файлы могут располагаться в корне архива [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf) .
*   **Содержимое и правила именования**:
    *   **`description.xml`**: Обязательный служебный XML-файл, который является описью вложения и задает структуру пакета, описывая все его компоненты и связи между ними [[14]](https://developer.kontur.ru/doc/diadoc-api/glossary/packet.html)[[33]](https://info.doc.astral.ru/docs/main/api/controllers/PackagesAPI)[[22]](https://markirovka.ru/knowledge/tovarnye-gruppy/tabachniye-izdeliya/podacha-upd-v-novom-formate-cherez-edo-layt-motp-atp-nsp-nszh-i-pivnaya-produktsiya)[[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf) .
    *   **Файлы документов**: Имена файлов указываются в `description.xml` [[33]](https://info.doc.astral.ru/docs/main/api/controllers/PackagesAPI) . Для формализованных документов это XML-файл (например, `ON_NSCHFDOPPR_... .xml`), для неформализованных — файл в произвольном формате (например, `contract.pdf`) .
    *   **Файлы подписей**: Файл отсоединенной электронной подписи в формате `.sgn` или `.p7s` [[28]](https://saby.ru/help/integration/api/sequence/ep) . Имя файла подписи должно совпадать с именем подписываемого документа с добавлением соответствующего расширения (например, `contract.pdf.sgn`) [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf) .

#### 3.3. Структура `description.xml`

Именно `description.xml` является "манифестом" пакета, устанавливая иерархию документов [[14]](https://developer.kontur.ru/doc/diadoc-api/glossary/packet.html)[[33]](https://info.doc.astral.ru/docs/main/api/controllers/PackagesAPI)[[22]](https://markirovka.ru/knowledge/tovarnye-gruppy/tabachniye-izdeliya/podacha-upd-v-novom-formate-cherez-edo-layt-motp-atp-nsp-nszh-i-pivnaya-produktsiya) .

*   **Ключевые теги и атрибуты**:
    *   **`<Сообщение>`**: Корневой узел с общей информацией: `Отправитель`, `Получатель`, `ДатаОтправки` .
    *   **`<Документ>`**: Описывает каждый файл в пакете. Атрибуты включают `ИдДокумента` (уникальный GUID), `ИмяФайла`, `ТипДокумента` ("УПД", "Неформализованный" и т.д.) и `Функция` ("СЧФДОП", "Договор") .
    *   **`ИдРодительскогоДокумента`**: **Ключевой атрибут для построения иерархии**. Он содержит `ИдДокумента` родительского документа, "привязывая" к нему сопутствующие файлы [[33]](https://info.doc.astral.ru/docs/main/api/controllers/PackagesAPI) . В некоторых версиях технологии может называться `РодительскийДокумент` [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf) .
    *   **`<Подпись>`**: Указывает на файл подписи для данного документа [[33]](https://info.doc.astral.ru/docs/main/api/controllers/PackagesAPI) .

*   **Пример `description.xml` для пакета (УПД + Договор)**:
    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <Сообщение xmlns="http://www.roseu.org/images/stories/roaming/description.xml"
               Отправитель="2BMA-7707....-201202291124410000000"
               Получатель="2BMA-7707....-201202291200440000000"
               ДатаОтправки="2024-10-26T15:30:00Z">
        <Документ ИдДокумента="A4E5C...01"
                  ИмяФайла="ON_NSCHFDOPPR_2BM..._2BM..._20241026_A4E5C..._1.xml"
                  ТипДокумента="УПД"
                  Функция="СЧФДОП"
                  ОжидаетсяПодписьПолучателя="true">
            <Подпись ИмяФайла="ON_NSCHFDOPPR_2BM..._2BM..._20241026_A4E5C..._1.xml.sgn" />
        </Документ>
        <Документ ИдДокумента="A4E5C...02"
                  ИмяФайла="Договор_123.pdf"
                  ТипДокумента="Неформализованный"
                  Функция="Договор"
                  ИдРодительскогоДокумента="A4E5C...01">
            <Подпись ИмяФайла="Договор_123.pdf.sgn" />
        </Документ>
    </Сообщение>
    ```

#### 3.4. Обработка сбоев при передаче по технологии РОСЭУ

Технология РОСЭУ предусматривает многоуровневую систему подтверждений для обеспечения надежности доставки [[34]](https://saby.ru/help/integration/api/sequence/send_doc)[[11]](https://edo.ru/integration/api-edopotok) . Для фиксации ошибок используются **транспортные (ТрК)** и **технологические (ТК)** квитанции [[34]](https://saby.ru/help/integration/api/sequence/send_doc)[[27]](https://saby.ru/help/integration/api/doc_guide)[[11]](https://edo.ru/integration/api-edopotok) .

*   **Нарушение целостности контейнера или недействительная подпись оператора**: Эти ошибки выявляются на транспортном уровне . Оператор-получатель, обнаружив, что ZIP-архив поврежден или подпись оператора-отправителя недействительна, не сможет его обработать и вернет отправителю **отрицательную транспортную квитанцию (ТрК)** или ошибку на уровне HTTP-протокола [[21]](https://developer.kontur.ru/Docs/Diadoc_UM/methods/JeDO_Podgotovit%27IOtpravit%27Paket.html) .
*   **Некорректная структура `description.xml`**: Эта ошибка выявляется на технологическом уровне [[23]](https://www.delta-i.ru/print/articles/poleznaya-informacziya/rouming-v-edo-kak-nastroit-obmen-mezhdu-kontur-diadok-sbis-tenzor-i-1s/) . Если файл `description.xml` имеет неверную структуру (например, отсутствует обязательный узел `<Сообщение>`), оператор-получатель формирует **отрицательную технологическую квитанцию (ТК)** с кодом ошибки (например, «ОшибкаОбработки») [[27]](https://saby.ru/help/integration/api/doc_guide)[[23]](https://www.delta-i.ru/print/articles/poleznaya-informacziya/rouming-v-edo-kak-nastroit-obmen-mezhdu-kontur-diadok-sbis-tenzor-i-1s/)[[13]](https://xn--n1adei3c.xn--p1ai/services/) .
*   **Принцип атомарности**: Технология РОСЭУ обеспечивает атомарность обработки логического сообщения [[34]](https://saby.ru/help/integration/api/sequence/send_doc) . Это означает, что если при проверке возникает ошибка хотя бы с одним документом внутри пакета, то **весь пакет считается необработанным**, и ни один из документов не будет доставлен получателю [[34]](https://saby.ru/help/integration/api/sequence/send_doc)[[27]](https://saby.ru/help/integration/api/doc_guide)[[21]](https://developer.kontur.ru/Docs/Diadoc_UM/methods/JeDO_Podgotovit%27IOtpravit%27Paket.html) .

### 4. Жизненный цикл пакета: Ответные действия, Исправление и Аннулирование

#### 4.1. Сценарий Частичного Подписания и Отклонения

Технология РОСЭУ позволяет обрабатывать каждый документ в пакете независимо, что делает возможным сценарий частичного подписания . Если получатель согласен с УПД, но обнаружил ошибки в договоре, он формирует два разных ответных документа :

*   **Для УПД (принятие):** Формируется **"Титул 2"** (информация покупателя) — стандартный XML-файл, подтверждающий приемку товара/услуги, который подписывается УКЭП получателя [[13]](https://xn--n1adei3c.xn--p1ai/services/) .
*   **Для договора (отклонение):** Формируется **"Уведомление об уточнении" (УОУ)**. Это специальный XML-документ, который сигнализирует о несогласии с конкретным файлом и содержит текстовое описание причин для уточнения [[11]](https://edo.ru/integration/api-edopotok)[[34]](https://saby.ru/help/integration/api/sequence/send_doc)[[28]](https://saby.ru/help/integration/api/sequence/ep)[[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf)[[13]](https://xn--n1adei3c.xn--p1ai/services/)[[15]](https://xn--n1adei3c.xn--p1ai/roaming/) . В УОУ обязательно указывается ссылка на идентификатор отклоняемого файла [[13]](https://xn--n1adei3c.xn--p1ai/services/)[[31]](https://xn--n1adei3c.xn--p1ai/upload/iblock/a93/%D0%A2%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F%20%D0%A0%D0%9E%D0%A1%D0%AD%D0%A3%20%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%201.15%20%D0%BE%D1%82%2011.01.2021.pdf)[[35]](https://www.diadoc.ru/Files/userfiles/file/spb/%D0%A0%D0%BE%D1%83%D0%BC%D0%B8%D0%BD%D0%B3_%D0%A0%D0%9E%D0%A1%D0%A3%D0%AD_%D0%B4%D0%BB%D1%8F_%D1%81%D0%B5%D0%BC%D0%B8%D0%BD%D0%B0%D1%80%D0%B0.pdf) .

*   **Пример Уведомления об уточнении (УОУ) для отклонения договора**:
    ```xml
    <?xml version="1.0" encoding="windows-1251"?>
    <Файл ИдФайла="DP_UVUTOCH_..." ВерсПрог="1.0" ВерсФорм="1.03">
      <СвУчДокОбор ИдОтпр="..." ИдПол="...">
        <СвУведУточ НаимДок="Уведомление об уточнении" Дата="27.10.2024" Ном="5">
          <ОснУведУточ>
            <НаимОсн>Договор_123.pdf</НаимОсн>
            <НомОсн>б/н</НомОсн>
            <ДатаОсн>26.10.2024</ДатаОсн>
            <ИдФайлОсн>A4E5C...02</ИдФайлОсн> <!-- Ссылка на ИдДокумента отклоняемого файла -->
            <СодОпер>Обнаружены некорректные реквизиты в пункте 4.5</СодОпер>
          </ОснУведУточ>
        </СвУведУточ>
      </СвУчДокОбор>
      <Подписант ОблПолн="1" Статус="1" ... />
    </Файл>
    ```

#### 4.2. Технический процесс исправления документа после получения УОУ

Получение УОУ запускает процесс исправления, который стандартизирован в роуминге [[36]](https://astral.ru/help/pochta-edo/zakonodatelnaya-baza/tekhnologiya-roseu/) .

1.  **Формирование исправления**: Отправитель создает новую, исправленную версию неформализованного документа (например, `Договор_123_испр.pdf`) [[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote) .
2.  **Отправка исправленной версии**: Формируется новый транспортный ZIP-архив с новым `description.xml` для отправки исправленного документа .
3.  **Связывание с исходным пакетом**: В `description.xml` нового пакета, в элементе `<Документ>`, описывающем исправленный договор, используются два ключевых атрибута для поддержания целостности документооборота:
    *   `ИдРодительскогоДокумента`: Сохраняет связь с исходным УПД.
    *   `ПредыдущийИдДокумента`: Ссылается на `ИдДокумента` отклоненного ранее договора, явно указывая на замену [[37]](https://astral.ru/help/astral-edo/zakonodatelnaya-baza/tekhnologiya-roseu/) .
4.  **Подтверждение**: После подписания контрагентом исправленной версии статус исходного документа меняется на "Заменен" или "Завершен с исправлением", а у нового устанавливается статус "Подписан" [[38]](https://xn--n1adei3c.xn--p1ai/upload/iblock/f98/%D0%A2%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F%20%D0%A0%D0%9E%D0%A1%D0%AD%D0%A3%20%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%201.15.1%20%D0%BE%D1%82%2015.03.2021.pdf)[[31]](https://xn--n1adei3c.xn--p1ai/upload/iblock/a93/%D0%A2%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F%20%D0%A0%D0%9E%D0%A1%D0%AD%D0%A3%20%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%201.15%20%D0%BE%D1%82%2011.01.2021.pdf) .

*   **Пример `description.xml` для отправки исправления**:
    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <Сообщение xmlns="http://www.roseu.org/images/stories/roaming/description.xml" ...>
        <Документ ИдДокумента="B5F6D...03"
                  ИмяФайла="Договор_123_испр.pdf"
                  ТипДокумента="Неформализованный"
                  ИдРодительскогоДокумента="A4E5C...01"
                  ПредыдущийИдДокумента="A4E5C...02">
            <Подпись ИмяФайла="Договор_123_испр.pdf.sgn" />
        </Документ>
    </Сообщение>
    ```

#### 4.3. Процесс аннулирования документов

Аннулирование — это процедура лишения юридической силы уже подписанного обеими сторонами документа по их взаимному согласию [[1]](https://nopaper.ru/faq/ehdo-zakony)[[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote)[[39]](https://xn--n1adei3c.xn--p1ai/) .

*   **Юридический аспект**: Понятие "аннулирование" в законодательстве РФ об ЭДО отсутствует [[1]](https://nopaper.ru/faq/ehdo-zakony)[[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote) . Процедура реализуется операторами на основе общих положений ГК РФ [[6]](https://astral.ru/aj/elem/zakony-ob-elektronnom-dokumentooborote-rf/) . Ключевое условие — **согласие обеих сторон**; в одностороннем порядке аннулировать подписанный документ нельзя [[1]](https://nopaper.ru/faq/ehdo-zakony)[[2]](https://endocs.ru/zakonodatelstvo-ob-edo-kakie-novye-zakony-izmenyat-vashu-rabotu-s-dokumentami/)[[9]](https://elma365.com/ru/articles/yuridicheski-znachimyi-elektronnyi-dokumentooborot/) .
*   **Технический процесс**:
    1.  Инициатор формирует и подписывает УКЭП **"Предложение об аннулировании" (ПОА)** — формализованный XML-документ формата `DP_PRANNUL` [[8]](https://nopaper.ru/faq/ehdo-formalizovannye-i-neformalizovannye-dokumenty)[[4]](https://www.diadoc.ru/articles/22582-formalizovannye_i_neformalizovannye_dokumenty)[[40]](https://developer.kontur.ru/doc/diadoc-api/docflows/utd.html)[[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf) .
    2.  Контрагент, получив ПОА, может либо подписать его своей УКЭП (согласие), либо отклонить [[8]](https://nopaper.ru/faq/ehdo-formalizovannye-i-neformalizovannye-dokumenty)[[4]](https://www.diadoc.ru/articles/22582-formalizovannye_i_neformalizovannye_dokumenty) .
    3.  В случае согласия документ получает статус "Аннулирован" и утрачивает юридическую силу [[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote)[[9]](https://elma365.com/ru/articles/yuridicheski-znachimyi-elektronnyi-dokumentooborot/)[[10]](https://www.esphere.ru/blog/chem-otlichayutsya-formalizovannye-elektronnye-dokumenty-ot-neformalizovannykh/)[[39]](https://xn--n1adei3c.xn--p1ai/) .
*   **Аннулирование в роуминге**: Не все операторы поддерживают эту технологию [[1]](https://nopaper.ru/faq/ehdo-zakony)[[4]](https://www.diadoc.ru/articles/22582-formalizovannye_i_neformalizovannye_dokumenty)[[19]](https://edo.mig24.ru/help/api) . Если стандартная процедура невозможна, стороны могут обменяться подписанным неформализованным соглашением об аннулировании [[4]](https://www.diadoc.ru/articles/22582-formalizovannye_i_neformalizovannye_dokumenty)[[7]](https://elma365.com/ru/articles/zakon-ob-edo/)[[11]](https://edo.ru/integration/api-edopotok) .

*   **Пример Предложения об аннулировании (ПОА) в формате `DP_PRANNUL`**:
    ```xml
    <?xml version="1.0" encoding="windows-1251"?>
    <Файл ИдФайл="DP_PRANNUL_..." ВерсПрог="1.0" ВерсФорм="1.02">
      <СвУчДокОбор ИдОтпр="..." ИдПол="...">
        <ПредАн>
          <НаимДокАн>Договор_123.pdf</НаимДокАн>
          <НомДокАн>б/н</НомДокАн>
          <ДатаДокАн>26.10.2024</ДатаДокАн>
          <ОснАн>Аннулирование в связи с технической ошибкой.</ОснАн>
        </ПредАн>
      </СвУчДокОбор>
      <Подписант ОблПолн="1" ... />
    </Файл>
    ```

### 5. Получение статусов: Архитектурные подходы к интеграции

Для информирования внешних учетных систем (1С, SAP и др.) об изменении статусов документов операторы ЭДО применяют два основных подхода [[33]](https://info.doc.astral.ru/docs/main/api/controllers/PackagesAPI)[[29]](https://saby.ru/help/integration/api/documents)[[2]](https://endocs.ru/zakonodatelstvo-ob-edo-kakie-novye-zakony-izmenyat-vashu-rabotu-s-dokumentami/)[[25]](https://xn--n1adei3c.xn--p1ai/news/roaming-upd-117/) .

#### 5.1. Периодический опрос API (Polling)

*   **Принцип работы**: Внешняя система с заданной периодичностью обращается к API оператора с запросом о новых событиях или статусах документов [[33]](https://info.doc.astral.ru/docs/main/api/controllers/PackagesAPI)[[25]](https://xn--n1adei3c.xn--p1ai/news/roaming-upd-117/) .
*   **Техническая реализация**: Используются HTTP-запросы к специальным методам API, таким как `GetNewEvents` или `GetDocuments` [[28]](https://saby.ru/help/integration/api/sequence/ep)[[15]](https://xn--n1adei3c.xn--p1ai/roaming/)[[26]](https://www.diadoc.ru/Files/userfiles/file/news/EDO_TechnologyV2.doc) . Чтобы не запрашивать всю историю, используется идентификатор последнего полученного события (`lastEventId`) [[26]](https://www.diadoc.ru/Files/userfiles/file/news/EDO_TechnologyV2.doc) .
*   **Плюсы и минусы**: Этот подход прост в реализации, но создает постоянную нагрузку на серверы и приводит к задержкам в получении информации [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf)[[25]](https://xn--n1adei3c.xn--p1ai/news/roaming-upd-117/)[[26]](https://www.diadoc.ru/Files/userfiles/file/news/EDO_TechnologyV2.doc) .

#### 5.2. Webhooks (Push-уведомления)

*   **Принцип работы**: Это более современный подход, работающий по push-модели [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf)[[41]](https://ru.wikipedia.org/wiki/HTTPS) . Система оператора сама мгновенно отправляет HTTP POST-запрос на заранее указанный URL-адрес клиента при наступлении события [[13]](https://xn--n1adei3c.xn--p1ai/services/)[[26]](https://www.diadoc.ru/Files/userfiles/file/news/EDO_TechnologyV2.doc)[[31]](https://xn--n1adei3c.xn--p1ai/upload/iblock/a93/%D0%A2%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F%20%D0%A0%D0%9E%D0%A1%D0%AD%D0%A3%20%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%201.15%20%D0%BE%D1%82%2011.01.2021.pdf) .
*   **Техническая реализация**: Клиент настраивает у оператора URL своего веб-сервиса [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf) . Тело запроса (payload) обычно содержит JSON-объект с информацией о событии: `eventType`, `documentId`, `timestamp` [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf)[[1]](https://nopaper.ru/faq/ehdo-zakony)[[32]](https://71.rosstat.gov.ru/storage/mediabank/%D0%A3%D0%BD%D0%B8%D1%84%D0%B8%D1%86%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B9%20%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%20%D1%82%D1%80%D0%B0%D0%BD%D1%81%D0%BF%D0%BE%D1%80%D1%82%D0%BD%D0%BE%D0%B3%D0%BE%20%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D1%8F.pdf) .
*   **Плюсы и минусы**: Обеспечивает уведомление в реальном времени и снижает нагрузку [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf)[[26]](https://www.diadoc.ru/Files/userfiles/file/news/EDO_TechnologyV2.doc) . Однако требует более сложной начальной настройки, включая развертывание публично доступного и надежного веб-сервиса [[1]](https://nopaper.ru/faq/ehdo-zakony)[[26]](https://www.diadoc.ru/Files/userfiles/file/news/EDO_TechnologyV2.doc)[[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf) .

### Итоговое резюме

Объединение формализованных и неформализованных документов в единый пакет при отправке по ЭДО, в том числе в роуминге, базируется на следующих ключевых принципах:

*   **Нормативная основа:** Процесс регулируется комплексом федеральных законов (ФЗ-63, ФЗ-402, НК РФ) и приказами ФНС, которые определяют форматы документов и придают им юридическую силу [[1]](https://nopaper.ru/faq/ehdo-zakony)[[2]](https://endocs.ru/zakonodatelstvo-ob-edo-kakie-novye-zakony-izmenyat-vashu-rabotu-s-dokumentami/)[[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote)[[7]](https://elma365.com/ru/articles/zakon-ob-edo/)[[6]](https://astral.ru/aj/elem/zakony-ob-elektronnom-dokumentooborote-rf/) .
*   **Логическая связка через метаданные:** Пакет — это набор независимых, отдельно подписанных документов [[13]](https://xn--n1adei3c.xn--p1ai/services/) . Их иерархическая связь устанавливается в служебном файле **`description.xml`** с помощью атрибута **`ИдРодительскогоДокумента`**, который ссылается на идентификатор родительского документа [[33]](https://info.doc.astral.ru/docs/main/api/controllers/PackagesAPI) .
*   **Различия в API операторов**: Несмотря на общую цель, операторы (Контур.Диадок, СБИС, Такском) используют разные модели данных и методы API для формирования пакетов: "сообщения" с `InitialDocumentIds` у Диадока, объект "Документ" с вложениями у СБИС и "контейнеры" с `card.xml` у Такском [[1]](https://nopaper.ru/faq/ehdo-zakony)[[5]](https://kontur.ru/diadoc/spravka/20806-zakon_ob_elektronnom_dokumentooborote)[[10]](https://www.esphere.ru/blog/chem-otlichayutsya-formalizovannye-elektronnye-dokumenty-ot-neformalizovannykh/) .
*   **Стандартизированный роуминг (РОСЭУ):** Передача пакетов между операторами происходит с помощью транспортного контейнера (подписанного ZIP-архива), содержащего файлы документов, подписей и `description.xml` [[28]](https://saby.ru/help/integration/api/sequence/ep)[[29]](https://saby.ru/help/integration/api/documents)[[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf) . Технология обеспечивает **атомарность** обработки пакета и включает механизмы обработки сбоев через технологические квитанции [[34]](https://saby.ru/help/integration/api/sequence/send_doc)[[27]](https://saby.ru/help/integration/api/doc_guide)[[11]](https://edo.ru/integration/api-edopotok)[[21]](https://developer.kontur.ru/Docs/Diadoc_UM/methods/JeDO_Podgotovit%27IOtpravit%27Paket.html) .
*   **Гибкий жизненный цикл:** Технология позволяет реализовывать сложные сценарии, такие как **частичное подписание** (с использованием "Титула 2" и **УОУ**), **исправление** отклоненного документа (с помощью атрибута **`ПредыдущийИдДокумента`** в `description.xml`) и **аннулирование** по взаимному согласию (через **ПОА**) [[28]](https://saby.ru/help/integration/api/sequence/ep)[[13]](https://xn--n1adei3c.xn--p1ai/services/)[[4]](https://www.diadoc.ru/articles/22582-formalizovannye_i_neformalizovannye_dokumenty)[[37]](https://astral.ru/help/astral-edo/zakonodatelnaya-baza/tekhnologiya-roseu/) .
*   **Интеграция и получение статусов:** Внешние системы могут отслеживать статусы документов, используя либо периодический **опрос API (polling)**, либо более современный механизм **Webhooks** [[30]](https://xn--n1adei3c.xn--p1ai/upload/iblock/417/technology_1.14_03.04.2019.pdf)[[25]](https://xn--n1adei3c.xn--p1ai/news/roaming-upd-117/)[[41]](https://ru.wikipedia.org/wiki/HTTPS) .

Такой многоуровневый подход обеспечивает как удобство для пользователей, работающих с комплектом документов по одной сделке, так и строгую юридическую корректность и возможность автоматизированной обработки на всех этапах жизненного цикла документа.