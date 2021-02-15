---
title: Условия, исключения и действия политики DLP (предварительная версия)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: узнайте об условиях и исключениях политики DLP
ms.openlocfilehash: 5c2c8e010047c2de05cc8422da1958e2fe5fc54c
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604219"
---
# <a name="dlp-policy-conditions-exceptions-and-actions-preview"></a>Условия, исключения и действия политики DLP (предварительная версия)

Условия и исключения в политиках DLP определяют конфиденциальные элементы, к которые применяется политика. Действия определяют, что происходит как последствие условия исключения.

- Условия определяют, что включать
- Исключения определяют, что исключать.
- Действия определяют, что происходит как последствие с ним условия или исключения
 
Большинство условий и исключений имеют одно свойство, которое поддерживает одно или несколько значений. Например, если политика DLP применяется к электронным письмам Exchange, отправитель является условием, требуя отправитель сообщения.  У некоторых условий есть два свойства. Например, для условия **Заголовок сообщения включает любое из этих слов** необходимо указать в одном свойстве поле заголовка сообщения, а в другом  искомый текст. Некоторые условия или исключения не имеют свойств. Например, условие **"Вложение"** — это условие, защищенное паролем, просто ищет вложения в сообщениях, защищенных паролем.

Для действий обычно требуются дополнительные свойства. Например, если правило политики DLP перенаправляет сообщение, необходимо указать, куда перенаправляется сообщение. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Условия и исключения для политик DLP

В таблицах следующих разделов описываются условия и исключения, доступные в DLP.

- [Отправители](#senders)
- [Получатели](#recipients)
- [Тема или текст сообщения](#message-subject-or-body)
- [Вложения](#attachments)
- [Заголовки сообщений](#message-headers)
- [Свойства сообщения](#message-properties)

### <a name="senders"></a>Senders


|**условие или исключение в DLP**  |**параметры условий и исключений в Microsoft 365 PowerShell** |**тип свойства**  |**description**|
|---------|---------|---------|---------|
|Sender is |condition: *From* <br/> exception: *ExceptIfFrom*      |Addresses |     Сообщения, отправленные указанными почтовыми ящиками, почтовыми пользователями, почтовыми контактами или группами Microsoft 365 в организации.|
|IP-адрес отправителя     |condition: *SenderIPRanges*<br/> exception: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Сообщения, IP-адрес отправителя которых совпадает с указанным IP-адресом или находится в указанном диапазоне IP-адресов.       |
|Адрес отправитель содержит слова   | condition: *FromAddressContainsWords* <br/> exception: *ExceptIfFromAddressContainsWords*        |   Words      |   Сообщения, электронный адрес отправителя которых содержит указанные слова.|
| Адреса отправитель соответствует шаблонам    | condition: *FromAddressMatchesPatterns* <br/> exception: *ExceptFromAddressMatchesPatterns*       |      Patterns   |  Сообщения, электронный адрес отправителя которых содержит текстовые шаблоны, соответствующие указанным регулярным выражениям.  |
|Домен отправитель  |  condition: *SenderDomainIs* <br/> exception: *ExceptIfSenderDomainIs*       |DomainName         |     Сообщения, в которых домен электронного адреса отправителя совпадает с указанным значением. Если вам нужно найти домены  отправитель, содержащие указанный домен (например, любой поддомен домена), используйте условие "Адрес отправитель"*(FromAddressMatchesPatterns)* и укажите домен с помощью синтаксиса " \. домен \. com$".    |
|Область отправитель    | condition: *FromScope* <br/> исключение: *ExceptIfFromScope*    | UserScopeFrom    |    Сообщения, отправляемые внутренними или внешними отправителями.    |

### <a name="recipients"></a>Получатели

|**условие или исключение в DLP**| **параметры условий и исключений в Microsoft 365 PowerShell** |    **тип свойства** | **description**|
|---------|---------|---------|---------|
|Получатель|  condition: *SentTo* <br/> исключение: *ExceptIfSentTo* | Addresses | Сообщения, одним из получателей которых является указанный почтовый ящик, почтовый пользователь или почтовый контакт в организации. Получатели могут быть указаны в поле **To**, **Cc** или **Bcc** сообщения.|
|Домен получателя|   condition: *RecipientDomainIs* <br/> исключение: *ExceptIfRecipientDomainIs* |   DomainName |    Сообщения, в которых домен электронного адреса отправителя совпадает с указанным значением.|
|Адрес получателя содержит слова|  condition: *RecipientAddressContainsWords* <br/> exception: *ExceptIfRecipientAddressContainsWords*|    Words|  Сообщения, электронный адрес получателя которых содержит указанные слова. <br/>**Примечание.** Это условие не учитывает сообщения, отправленные на прокси-адреса получателя. Сопоставляются только сообщения, отправленные на основной электронный адрес получателя.|
|Адрес получателя соответствует шаблонам| condition: *RecipientAddressMatchesPatterns* <br/> exception: *ExceptIfRecipientAddressMatchesPatterns*|   Patterns    |Сообщения, электронный адрес получателя которых содержит текстовые шаблоны, соответствующие указанным регулярным выражениям. <br/> **Примечание.** Это условие не учитывает сообщения, отправленные на прокси-адреса получателя. Сопоставляются только сообщения, отправленные на основной электронный адрес получателя.|
|Отправляется участнику группы| condition: *SentToMemberOf* <br/> исключение: *ExceptIfSentToMemberOf*|  Addresses|  Сообщения, содержащие получателей, которые являются членами указанной группы рассылки, группы безопасности с включенной поддержкой почты или группы Microsoft 365. Группа может быть указана в поле **To**, **Cc** или **Bcc** сообщения.|

### <a name="message-subject-or-body"></a>Тема или текст сообщения

|**условие или исключение в DLP** | **параметры условий и исключений в Microsoft 365 PowerShell** |**тип свойства**| **description**|
|---------|---------|---------|---------|
|Тема содержит слова или фразы| condition: *SubjectContainsWords* <br/> exception: *ExceptIf SubjectContainsWords*| Words   |Сообщения, в которых поле Subject содержит указанные слова.|
|Шаблоны совпадений темы|condition: *SubjectMatchesPatterns* <br/> exception: *ExceptIf SubjectMatchesPatterns*|Patterns   |Сообщения, в которых поле "Тема" содержит текстовые шаблоны, которые соответствуют указанным регулярным выражениям.|
|Содержимое содержит|  condition: *ContentContainsSensitiveInformation* <br/> exception *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Сообщения или документы, содержащие конфиденциальную информацию, определенные политиками защиты от потери данных (DLP).|
| Шаблон совпадений темы или тела    | condition: *SubjectOrBodyMatchesPatterns* <br/> exception: *ExceptIfSubjectOrBodyMatchesPatterns*    | Patterns    | Сообщения, в которых поле темы или текст сообщения содержит текстовые шаблоны, которые соответствуют указанным регулярным выражениям.    |
| Тема или тело содержит слова    | condition: *SubjectOrBodyContainsWords* <br/> exception: *ExceptIfSubjectOrBodyContainsWords*    | Words    | Сообщения с указанными словами в поле темы или тексте сообщения    |


### <a name="attachments"></a>Attachments

|**условие или исключение в DLP**| **параметры условий и исключений в Microsoft 365 PowerShell**| **тип свойства**   |**description**|
|---------|---------|---------|---------|
|Вложение защищено паролем|condition: *DocumentIsPasswordProtected* <br/> exception: *ExceptIfDocumentIsPasswordProtected*|Нет| Сообщения с вложениями, защищенными паролем (такие файлы нельзя проверить). Обнаружение паролей работает только для документов Office, ZIP-файлов и 7Z-файлов.|
|Расширение файла вложения:|condition: *ContentExtensionMatchesWords* <br/> exception: *ExceptIfContentExtensionMatchesWords*|  Words   |Сообщения, в которых расширение файла вложения совпадает с любым из указанных свойств.|
|Не удалось проверить содержимое любого вложения электронной почты|condition: *DocumentIsUnsupported* <br/>exception: *ExceptIf DocumentIsUnsupported*|   н/д|    Сообщения, в которых вложение не распознается в Exchange Online.|
|Содержимое любого вложения электронной почты не завершило сканирование|   condition: *ProcessingLimitExceeded* <br/> исключение: *ExceptIfProcessingLimitExceeded*|    Н/д |Сообщения, для которых обработчику правил не удалось завершить сканирование вложений. С помощью этого условия можно создавать правила, которые совместно определяют и обрабатывают сообщения, содержимое которых не полностью прошло сканирование.|
|Имя документа содержит слова|condition: *DocumentNameMatchesWords* <br/> exception: *ExceptIfDocumentNameMatchesWords* |Words  |Сообщения, в которых имя файла вложения соответствует любому из указанных слов.|
|Имя документа соответствует шаблонам|condition: *DocumentNameMatchesPatterns* <br/> exception: *ExceptIfDocumentNameMatchesPatterns*|    Patterns    |Сообщения, в которых имя файла вложения содержит текстовые шаблоны, соответствующие указанным регулярным выражениям.|
|Свойство документа|condition: *ContentPropertyContainsWords* <br/> exception: *ExceptIfContentPropertyContainsWords* |Words| Сообщения или документы, в которых расширение файла вложения соответствует любому из указанных слов.|
|Размер документа равен или превышает| condition: *DocumentSizeOver* <br/> exception: *ExceptIfDocumentSizeOver*|    Size    |Сообщения, содержащие вложения, размер которых равен заданному или превышает его.|

### <a name="message-headers"></a>Заголовки сообщения

|**условие или исключение в DLP**| **параметры условий и исключений в Microsoft 365 PowerShell**| **тип свойства**|  **description**|
|---------|---------|---------|---------|
|Заголок содержит слова или фразы|condition: *HeaderContainsWords* <br/> exception: *ExceptIfHeaderContainsWords*|  Таблица Hash  |Сообщения, которые содержат указанное поле заголовка. Значение этого поля содержит указанные слова.|
|Заготовая соответствует шаблонам|   condition: *HeaderMatchesPatterns* <br/> exception: *ExceptIfHeaderMatchesPatterns*|    Таблица Hash  |Сообщения, которые содержат указанное поле заголовка. Значение этого поля содержит указанные регулярные выражения.|

### <a name="message-properties"></a>Свойства сообщения

|**условие или исключение в DLP**| **параметры условий и исключений в Microsoft 365 PowerShell**| **тип свойства**   |**description**|
|---------|---------|---------|---------|
|Размер сообщения больше|condition: *MessageSizeOver* <br/> exception: *ExceptIfMessageSizeOver*| Size    |Сообщения, общий размер которых (сообщение и вложения) равен заданному или превышает его. <br/>**Примечание.** Сначала выполняется проверка согласно ограничениям на размер сообщений, и только потом  согласно правилам потока обработки почты. Отправка слишком большого для почтового ящика сообщения будет отклонена прежде, чем сработает правило с соответствующим условием.  |
| С важностью    | condition: *WithImportance* <br/> exception: *ExceptIfWithImportance*    | Importance    | Сообщения, помеченные с указанным уровнем важности.    |
| Набор символов содержимого содержит слова    | condition: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Сообщения с какими-либо из указанных кодировок.    |
| Имеет переопределения отправитель    | condition: *HasSenderOverride* <br/> исключение: *ExceptIfHasSenderOverride*    | Н/д    | Сообщения, для которых отправитель выбрал переопределение политики защиты от потери данных (DLP). Дополнительные сведения о политиках защиты от потери данных см. [в этой теме.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)   |
| Тип сообщения соответствует    | condition: *MessageTypeMatches* <br/> exception: *ExceptIfMessageTypeMatches*    | MessageType    | Сообщения указанного типа.    |

## <a name="actions-for-dlp-policies"></a>Действия для политик DLP

В этой таблице описываются действия, доступные в DLP.


|**действие в DLP**|**параметры действий в Microsoft 365 PowerShell**|**тип свойства**|**description**|
|---------|---------|---------|---------|
|Настройка загона|SetHeader|Первое свойство: *имя загона* </br> Второе свойство: *значение загона*|Параметр SetHeader указывает действие правила DLP, которое добавляет или изменяет поле и значение в заголовок сообщения. Этот параметр использует синтаксис HeaderName:HeaderValue. Можно указать несколько пар имени и значения, разделенных запятой|
|Удаление загона| RemoveHeader| Первое свойство: *MessageHeaderField*</br> Второе свойство: *String*|  Параметр RemoveHeader указывает действие правила DLP, которое удаляет поле заголовок из заголовок сообщения. Этот параметр использует синтаксис HeaderName или HeaderName:HeaderValue. Можно указать несколько имен или пар "имя и значение", разделенных запятой|
|Перенаправление сообщения определенным пользователям|*RedirectMessageTo*|Addresses| Перенаправляет сообщение указанным получателям. Сообщение не доставляется исходным получателям. При этом никакие уведомления не отправляются ни отправителю, ни исходным получателям.|
|Переслать сообщение на утверждение руководителю отправитель| Средний|Первое свойство: *ModerateMessageByManager*</br> Второе свойство: *Boolean*|Параметр Moderate указывает действие правила DLP, которое отправляет сообщение электронной почты модератору. Этот параметр использует синтаксис: @{ModerateMessageByManager = <$true \| $false>;|
|Переадформать сообщение на утверждение определенным утвержденным| Средний|Первое свойство: *ModerateMessageByUser*</br>Второе свойство: *Addresses*|Параметр Moderate указывает действие правила DLP, которое отправляет сообщение электронной почты модератору. Этот параметр использует синтаксис: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Добавление получателя|AddRecipients|Первое свойство: *Field*</br>Второе свойство: *Addresses*| Добавляет одного или несколько получателей в поле "To/Cc/Bcc" сообщения. Этот параметр использует синтаксис: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Добавление руководителя отправитель в качестве получателя|AddRecipients | Первое свойство: *AddedManagerAction*</br>Второе свойство: *Field* | Добавляет руководителя отправитель к сообщению в качестве указанного типа получателя ( To, Cc, Bcc) или перенаправляет сообщение руководителю отправитель без уведомления отправитель или получатель. Это действие работает только в том случае, если в Active Directory определен атрибут диспетчера отправитель. Этот параметр использует синтаксис: @{AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|    
Prepend subject    |PrependSubject    |String    |Добавляет указанный текст в начало поля Subject сообщения. Рекомендуем добавить пробел или двоеточие (:) в конце указанного текста, чтобы отделить его от исходного текста темы.</br>Чтобы предотвратить добавление той же строки в сообщения, которые уже содержат текст в теме (например, ответы), добавьте исключение "Тема содержит слова" (ExceptIfSubjectContainsWords) в правило.    |
Применение заявления об отказе в формате HTML    |ApplyHtmlDisclaimer    |Первое свойство: *Text*</br>Второе свойство: *Location*</br>Третье свойство: *действие отката*    |Применяет указанное заявление об отказе в формате HTML к необходимому расположению сообщения.</br>В этом параметре используется синтаксис: @{ Text = " ; Location = <\| Append Prepend>; FallbackAction = <Wrap \| Ignore \| Reject> }




