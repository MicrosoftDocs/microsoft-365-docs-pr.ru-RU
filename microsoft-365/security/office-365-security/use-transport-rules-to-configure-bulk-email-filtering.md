---
title: Использование правил обработки почтового процесса для фильтрации массовых сообщений электронной почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать правила для обработки почтовых ящиков (правила транспорта) для идентификации и фильтрации массовой почты (серой почты) в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 62db73ea917139d81a29569d5b452637fd053c92
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775199"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Используйте правила потока почты для фильтрации массовой почты в EOP

В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, EOP использует политики защиты от нежелательной почты (также называемые политиками фильтрации нежелательной почты или фильтрами содержимого) для сканирования входящих сообщений для нежелательной почты и массовой почты (также известной как серый Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

Если вы хотите дополнительно отфильтровать массовую почту, вы можете создать правила для поток обработки почты (также называемые правилами транспорта), чтобы искать текстовые шаблоны или фразы, которые часто встречаются в массовой почте, и помечать эти сообщения как спам. Для получения дополнительных сведений об массовой рассылке почты ознакомьтесь со статьей [различие между нежелательной почтой и массовой](what-s-the-difference-between-junk-email-and-bulk-email.md) почтой и [уровнем жалоб (BCL) в EOP](bulk-complaint-level-values.md).

В этом разделе объясняется, как создавать эти правила для этих почтовых ящиков в центре администрирования Exchange и PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Прежде чем выполнять следующие процедуры, необходимо назначить разрешения.

  - В Exchange Online вы найдете запись "почтовый ящик" в разделе "Управление [разрешениями" функции в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).
  
  - В автономном EOP вам потребуются роли правил транспорта, которые назначаются ролям Организатионманажемент, Комплианцеманажемент и RecordsManagement по умолчанию. Дополнительные сведения см. [в разделе разрешения в автономных EOP](feature-permissions-in-eop.md) и используйте центр администрирования Exchange для [изменения списка участников в группах ролей](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Чтобы открыть центр администрирования Exchange в Exchange Online, обратитесь к [центру администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Чтобы открыть центр администрирования Exchange в автономном EOP, обратитесь к разделу [центр администрирования Exchange в отдельном EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о правилах обработки почтового ящика в Exchange Online и отдельном EOP содержатся в следующих разделах:

  - [Правила потока обработки почты (правила транспорта) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения правила для обработки почтового процесса (предикаты) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правил обработки почты в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Список слов и текстовых шаблонов, используемых для идентификации массовой почты в примерах, не является исчерпывающим; При необходимости вы можете добавлять и удалять записи. Однако они являются хорошей отправной точкой.

- Поиск слов и текстовых шаблонов в теме или других полях заголовка сообщения выполняется *после* расшифровки сообщения, к которому применялся метод кодирования для передачи сообщений MIME. Этот метод используется для передачи двоичных сообщений между SMTP-серверами с преобразованием их в текст ASCII. Вы не можете применять условия или исключения для поиска необработанных закодированных значений (обычно в формате Base64) в теме или других полях заголовка сообщения.

- В приведенных ниже процедурах отмечаются массовые сообщения в качестве нежелательной почты для всей Организации. Однако вы можете добавить еще одно условие, чтобы применить эти правила только к определенным получателям, поэтому вы можете использовать агрессивную фильтрацию для нескольких пользователей с большим количеством целевых пользователей, а остальные пользователи (которые обычно получают массовые сообщения, на которые они подписаны) не затрагиваются.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Использование центра администрирования Exchange для создания правил обработки сообщений, которые отфильтровывают групповые сообщения

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Щелкните **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) , а затем выберите **создать новое правило**.

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Name**: введите уникальное описательное имя правила.

   - Нажмите кнопку **Дополнительные параметры**.

   - **Применять это правило, если**: Настройте один из следующих параметров для поиска содержимого в сообщениях с помощью регулярных выражений (Regex) или слов или фраз:

     - **Тема или основной текст** \> **Тема или текст сообщения соответствует следующим текстовым шаблонам**: в появившемся диалоговом окне **Укажите слова или фразы** введите одно из следующих значений, нажмите **добавить** ![ значок "Добавить" ](../../media/ITPro-EAC-AddIcon.png) и повторяйте до тех пор, пока не ввели все значения.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Чтобы изменить запись, выберите ее и нажмите кнопку **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) . Чтобы удалить запись, выберите ее и нажмите кнопку **Удалить** ![ значок "Удалить" ](../../media/ITPro-EAC-DeleteIcon.png) .

       После этого нажмите кнопку **ОК**.

     - **Тема или основной текст** \> **Тема или текст содержит любое из этих слов**: в появившемся диалоговом окне **Укажите слова или фразы** введите одно из следующих значений, нажмите **добавить** ![ значок "Добавить" ](../../media/ITPro-EAC-AddIcon.png) и повторяйте до тех пор, пока не ввели все значения.

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      Чтобы изменить запись, выберите ее и нажмите кнопку **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) . Чтобы удалить запись, выберите ее и нажмите кнопку **Удалить** ![ значок "Удалить" ](../../media/ITPro-EAC-DeleteIcon.png) .

       После этого нажмите кнопку **ОК**.

   - **Выполните следующие**действия: выберите **изменить свойства сообщения** \> **установите уровень вероятности нежелательной почты (SCL)**. В появившемся диалоговом окне **Указание вероятности** настройте один из следующих параметров:

     - Чтобы пометить сообщения как **Нежелательная почта**, выберите **6**. Действие, настроенное для фильтрации **нежелательной почты** вердиктс в политиках защиты от нежелательной почты, применяется к сообщениям (значение по умолчанию — **Перемещение сообщения в папку нежелательной почты**).

     - Чтобы пометить сообщения как **Нежелательная почта высокой надежности** , выберите **9**. Действие, настроенное для фильтрации нежелательной **почты высокой надежности** , вердиктс в политиках защиты от нежелательной почты применяется к сообщениям (значение по умолчанию — **Перемещение сообщения в папку нежелательной почты**).

    Дополнительные сведения о значениях ВЕРОЯТНОсти нежелательной почты [(SCL) можно найти в EOP](spam-confidence-levels.md).

   Когда все будет готово, нажмите кнопку **сохранить**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Создание правил для почтового процесса с помощью PowerShell для фильтрации массовых сообщений электронной почты с помощью PowerShell

Используйте следующий синтаксис для создания одного или обоих правил для почтового процесса (регулярных выражений и слов):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

В этом примере создается новое правило с именем "BULK Filtering Filtering — RegEx", которое использует тот же список регулярных выражений, начиная с предыдущего раздела, для настройки сообщений как **спама**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

В этом примере создается новое правило с именем "массовая фильтрация электронной почты — слова", которая использует тот же список слов из предыдущего раздела, чтобы установить сообщения в качестве **нежелательной почты высокой достоверности**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы настроили правила обработки почты для фильтрации массовых сообщений электронной почты, выполните одно из следующих действий:

- В центре администрирования Exchange перейдите к разделу правила для обработки **почтового ящика** , \> **Rules** \> выберите правило \> щелкните **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) и проверьте параметры.

- В PowerShell замените \<Rule Name\> именем правила и выполните следующую команду, чтобы проверить параметры:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- С внешней учетной записи отправьте тестовые сообщения затронутому получателю, который содержит одну из фраз или текстовых шаблонов, и проверьте результаты.
