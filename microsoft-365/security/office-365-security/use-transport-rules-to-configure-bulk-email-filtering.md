---
title: Использование правил обработки почтового процесса для фильтрации массовых сообщений электронной почты в Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать правила обработки почтового ящика в Exchange Online Protection для фильтрации массовых сообщений электронной почты.
ms.openlocfilehash: 2ac81d798af957f23f95b92f633b93bdda677991
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895051"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a>Использование правил обработки почтового процесса для фильтрации массовых сообщений электронной почты в Office 365

Если вы являетесь клиентом Office 365 с почтовыми ящиками в Exchange Online или отдельном клиенте Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, EOP использует политики защиты от нежелательной почты (также называемые политиками фильтрации нежелательной почты или фильтрами содержимого) для сканирования входящие сообщения для нежелательной почты и массовой почты (также называемой серой почтой). Дополнительные сведения см. в разделе [Настройка политик защиты от спама в Office 365](configure-your-spam-filter-policies.md).

Если вы хотите дополнительно отфильтровать массовую почту, вы можете создать правила для поток обработки почты (также называемые правилами транспорта), чтобы искать текстовые шаблоны или фразы, которые часто встречаются в массовой почте, и помечать эти сообщения как спам. Для получения дополнительных сведений об массовой рассылке почты посмотрите, [что такое различие между нежелательной почтой и групповой почтой](what-s-the-difference-between-junk-email-and-bulk-email.md) и [уровнем жалоб (BCL) в Office 365](bulk-complaint-level-values.md).

В этом разделе объясняется, как создавать эти правила для этих почтовых ящиков в центре администрирования Exchange и PowerShell (Exchange Online PowerShell для Office 365 и клиентов). Exchange Online Protection PowerShell для автономных клиентов EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Прежде чем выполнять эти процедуры, вам необходимо назначить разрешения в Exchange Online. В частности, необходимо назначить роль " **правила транспорта** ", которая назначается для ролей управления **организацией**, **управления соответствием требованиям**и управления **записями** по умолчанию. Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Чтобы открыть центр администрирования Exchange в Exchange Online, обратитесь к [центру администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Чтобы подключиться к автономной службе Exchange Online Protection PowerShell, ознакомьтесь со статьей [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о правилах обработки почтового ящика в Exchange Online и отдельном EOP содержатся в следующих разделах:

  - [Правила потока обработки почты (правила транспорта) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения правила для обработки почтового процесса (предикаты) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правил обработки почты в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Список слов и текстовых шаблонов, используемых для идентификации массовой почты в примерах, не является исчерпывающим; При необходимости вы можете добавлять и удалять записи. Однако они являются хорошей отправной точкой.

- Поиск слов и текстовых шаблонов в теме или других полях заголовка сообщения выполняется *после* расшифровки сообщения, к которому применялся метод кодирования для передачи сообщений MIME. Этот метод используется для передачи двоичных сообщений между SMTP-серверами с преобразованием их в текст ASCII. Вы не можете применять условия или исключения для поиска необработанных закодированных значений (обычно в формате Base64) в теме или других полях заголовка сообщения.

- В приведенных ниже процедурах отмечаются массовые сообщения в качестве нежелательной почты для всей Организации. Однако вы можете добавить еще одно условие, чтобы применить эти правила только к определенным получателям, поэтому вы можете использовать агрессивную фильтрацию для нескольких пользователей с большим количеством целевых пользователей, а остальные пользователи (которые обычно получают массовые сообщения, на которые они подписаны) не затрагиваются.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Использование центра администрирования Exchange для создания правил обработки сообщений, которые отфильтровывают групповые сообщения

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Щелкните **Добавить** ![значок](../../media/ITPro-EAC-AddIcon.png) добавить, а затем выберите **создать новое правило**.

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Name**: введите уникальное описательное имя правила.

   - Нажмите кнопку **Дополнительные параметры**.

   - **Применять это правило, если**: Настройте один из следующих параметров для поиска содержимого в сообщениях с помощью регулярных выражений (Regex) или слов или фраз:

     - Тема **или** \> текст темы или текст сообщения **соответствует следующим текстовым шаблонам**: в появившемся диалоговом окне **Укажите слова или фразы** введите одно из следующих значений, нажмите **Добавить** ![значок](../../media/ITPro-EAC-AddIcon.png)"Добавить" и повторяйте столько раз, сколько необходимо.

       - `If you are unable to view the content of this email\, please`

       - `\>(safe )?unsubscribe( here)?\</a\>`

       - `If you do not wish to receive further communications like this\, please`

       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

       - `To stop receiving these+emails\:http\://`

       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

       - `no longer (wish )?(to )?(be sent|receive) w+ email`

       - `If you are unable to view the content of this email\, please click here`

       - `To ensure you receive (your daily deals|our e-?mails)\, add`

       - `If you no longer wish to receive these emails`

       - `to change your (subscription preferences|preferences or unsubscribe)`

       - `click (here to|the) unsubscribe`

      Чтобы изменить запись, выберите ее и нажмите кнопку **изменить** ![значок](../../media/ITPro-EAC-EditIcon.png)редактирования. Чтобы удалить запись, выберите ее и нажмите кнопку **Удалить** ![значок](../../media/ITPro-EAC-DeleteIcon.png)"Удалить".

       После этого нажмите кнопку **ОК**.

     - **Тема или основной текст** \> **содержит любое из этих слов**: в появившемся диалоговом окне **Укажите слова или фразы** введите одно из следующих значений, нажмите **Добавить** ![значок](../../media/ITPro-EAC-AddIcon.png)"Добавить" и повторяйте столько раз, сколько необходимо.

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

      Чтобы изменить запись, выберите ее и нажмите кнопку **изменить** ![значок](../../media/ITPro-EAC-EditIcon.png)редактирования. Чтобы удалить запись, выберите ее и нажмите кнопку **Удалить** ![значок](../../media/ITPro-EAC-DeleteIcon.png)"Удалить".

       После этого нажмите кнопку **ОК**.

   - **Выполните следующие**действия: выберите **изменить свойства** \> сообщения **установите уровень вероятности нежелательной почты (SCL)**. В появившемся диалоговом окне **Указание вероятности** настройте один из следующих параметров:

     - Чтобы пометить сообщения как **Нежелательная почта**, выберите **6**. Действие, настроенное для фильтрации **нежелательной почты** вердиктс в политиках защиты от нежелательной почты, применяется к сообщениям (значение по умолчанию — **Перемещение сообщения в папку нежелательной почты**).

     - Чтобы пометить сообщения как **Нежелательная почта высокой надежности** , выберите **9**. Действие, настроенное для фильтрации нежелательной **почты высокой надежности** , вердиктс в политиках защиты от нежелательной почты применяется к сообщениям (значение по умолчанию — **Перемещение сообщения в папку нежелательной почты**).

    Для получения дополнительных сведений о значениях ВЕРОЯТНОсти нежелательной почты [(SCL) в Office 365](spam-confidence-levels.md).

   Когда все будет готово, нажмите кнопку **сохранить**

## <a name="use-powershell-to-create-a-mail-flow-rules-that-filter-bulk-email"></a>Создание правил для почтового процесса, которые отфильтровывают групповые сообщения, с помощью PowerShell

Используйте следующий синтаксис для создания одного или обоих правил для почтового процесса (регулярных выражений и слов):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

В этом примере создается новое правило с именем "BULK Filtering Filtering — RegEx", которое использует тот же список регулярных выражений, начиная с предыдущего раздела, для настройки сообщений как **спама**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

В этом примере создается новое правило с именем "массовая фильтрация электронной почты — слова", которая использует тот же список слов из предыдущего раздела, чтобы установить сообщения в качестве **нежелательной почты высокой достоверности**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы настроили правила обработки почты для фильтрации массовых сообщений электронной почты, выполните одно из следующих действий:

- В центре администрирования Exchange перейдите к разделу **правила** \> для обработки **почтового ящика** \> ,](../../media/ITPro-EAC-EditIcon.png)выберите правило \> щелкните **изменить** ![значок редактирования и проверьте параметры.

- В PowerShell замените \<имя\> правила именем правила и выполните следующую команду, чтобы проверить параметры:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- С внешней учетной записи отправьте тестовые сообщения затронутому получателю, который содержит одну из фраз или текстовых шаблонов, и проверьте результаты.
