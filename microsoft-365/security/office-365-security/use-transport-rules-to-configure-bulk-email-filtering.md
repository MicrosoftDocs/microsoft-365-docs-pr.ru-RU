---
title: Использование правил для потока обработки почты для фильтрации массовых рассылок
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
description: Администраторы могут узнать, как использовать правила потока обработки почты (правила транспорта) для определения и фильтрации массовых рассылок (серые рассылки) в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfe841d3e80efc50d6ffbc702faefa1c9a971b13
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826757"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Используйте правила потока почты для фильтрации массовой почты в EOP

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online для проверки входящих сообщений на спам и массовую рассылку (также называемой "серые" — eop). Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

Если вам нужны дополнительные параметры для фильтрации массовых рассылок, можно создать правила потока обработки почты (также называемые правилами транспорта) для поиска текстовых шаблонов или фраз, которые часто используются в массовых радикатных рамках, и пометить эти сообщения как нежелательные. Дополнительные сведения о массовой рассылке почты см. в статье "В чем разница между нежелательной [почтой и массовыми](what-s-the-difference-between-junk-email-and-bulk-email.md) рассылками" [и "Массовые рассылки" (BCL) в EOP.](bulk-complaint-level-values.md)

В этой статье объясняется, как создать эти правила для потока обработки почты в Центр администрирования Exchange и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online, а также автономная оболочка EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Для выполнения следующих процедур необходимы права:

  - В Exchange Online см. запись "Поток обработки почты" в [разрешениях функций в Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)
  
  - В автономной службе EOP требуется роль правил транспорта, по умолчанию присваиваемая ролям OrganizationManagement, ComplianceManagement и RecordsManagement. Дополнительные сведения см. в разделе ["Разрешения в автономной службе EOP"](feature-permissions-in-eop.md) и использовании Центра администрирования [Exchange для изменения списка членов в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Сведения о том, как открыть Центр администрирования Exchange в Exchange Online, [см. в статье Центра администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Сведения о том, как открыть Центр администрирования Exchange в автономной службе EOP, см. в [статье Центр администрирования Exchange в автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о правилах для потока обработки почты в Exchange Online и автономной службе EOP см. в следующих разделах:

  - [Правила потока обработки почты (правила транспорта) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения (предикаты) правил потока обработки почты в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правил обработки почтового потока в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- В этих примерах представлен не исключающий текст слов и текстовые шаблоны; При необходимости можно добавлять и удалять записи. Однако они хорошо служат отправной точкой.

- Поиск слов и текстовых шаблонов в теме или других полях заголовка сообщения выполняется *после* расшифровки сообщения, к которому применялся метод кодирования для передачи сообщений MIME. Этот метод используется для передачи двоичных сообщений между SMTP-серверами с преобразованием их в текст ASCII. Вы не можете применять условия или исключения для поиска необработанных закодированных значений (обычно в формате Base64) в теме или других полях заголовка сообщения.

- Следующие процедуры отмечены как спам для всей организации. Однако вы можете добавить еще одно условие, чтобы применить эти правила только к определенным получателям, поэтому ее можно применять для нескольких жестко целевых пользователей, тогда как остальные пользователи (которые, в основном, получают массовые сообщения, на которые они подписаны) не затронуты.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Создание правил потока обработки почты, фильтрующих массовые сообщения электронной почты, с помощью Центра администрирования Exchange

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Нажмите **кнопку** ![ "Добавить ](../../media/ITPro-EAC-AddIcon.png) значок "Добавить" и **выберите пункт "Создать правило".**

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Имя:** введите уникальное, понятное имя правила.

   - Нажмите кнопку **Дополнительные параметры**.

   - **Применяет это правило, если:** настройте один из следующих параметров для поиска содержимого сообщений с использованием регулярных выражений (RegEx), слов или фраз:

     - **Тема или текст** \> **Тема или текст соответствует этим текстовым шаблонам:** в появившемся диалоговом окне "Укажите слова или фразы" введите одно из следующих значений, нажмите кнопку **Добавить** **Specify words or phrases** ![ ](../../media/ITPro-EAC-AddIcon.png) значок и повторяйте, пока не введите все значения.

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

      Чтобы изменить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования. Чтобы удалить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-DeleteIcon.png) "Удалить".

       После этого нажмите кнопку **ОК**.

     - **Тема или текст** \> **Тема или текст включает любое из следующих**слов: в **Specify words or phrases** появившемся диалоговом окне "Укажите слова или фразы" введите одно из следующих значений, нажмите кнопку **Add** ![ Icon ](../../media/ITPro-EAC-AddIcon.png) (Добавить значок) и повторяйте, пока не введите все значения.

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

      Чтобы изменить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования. Чтобы удалить запись, выберите ее и нажмите **значок** ![ ](../../media/ITPro-EAC-DeleteIcon.png) "Удалить".

       После этого нажмите кнопку **ОК**.

   - **Выполните следующее:** **"Изменить свойства сообщения"** задали вероятность \> **нежелательной почты (SCL).** В **отобразившемся диалоговом окне** "Указание вероятности нежелательной почты" настройте один из следующих параметров:

     - Чтобы пометить сообщения **как нежелательные,** **нажмите 6.** К сообщениям применяется действие, **Spam** настроенное на использование фильтров нежелательной почты в политиках защиты от нежелательной почты (значение по умолчанию "Переместить **сообщение в папку нежелательной почты").**

     - Чтобы пометить сообщения **как нежелательную почту с высокой** вероятностью, **нажмите 9.** К сообщениям применяется действие, **High confidence spam** настроенное на решения фильтров нежелательной почты высокого уровня в политиках защиты от нежелательной почты (значение по умолчанию "Переместить **сообщение в папку нежелательной почты").**

    Дополнительные сведения о значениях SCL см. в статье Об уровне [вероятности нежелательной почты (SCL) в EOP.](spam-confidence-levels.md)

   По завершении нажмите кнопку **"Сохранить".**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Создание правил потока обработки почты, которые фильтруют массовые рассылки, с помощью PowerShell

Используйте следующий синтаксис для создания одного или обоих правил потока обработки почты (обычных выражений и слов):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

В этом примере создается новое правило с именем "Bulk email filtering - RegEx", в котором для установки сообщений как нежелательных используется тот же список регулярных выражений, как у **приведенных ранее**в разделе.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

В этом примере создается новое правило с именем "Фильтрация массовой рассылки — Words", использующее тот же список слов, как и у предыдущего раздела, для установки сообщений с высокой **вероятностью.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что настроены правила потока обработки почты для фильтрации массовых рассылок, выполните одно из указанных ниже действий.

- В Центре администрирования Exchange перейдите в раздел **"Правила** \> **потока обработки** \> почты" и \> выберите правило на значок **Edit** ![ "Изменить ](../../media/ITPro-EAC-EditIcon.png) изменить" и проверьте параметры.

- В PowerShell \<Rule Name\> замените именем правила и выполните следующую команду, чтобы проверить параметры:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Отправьте из внешней учетной записи тестовые сообщения получателю, который содержит одну из фраз или текстовых шаблонов, и проверьте результаты.
