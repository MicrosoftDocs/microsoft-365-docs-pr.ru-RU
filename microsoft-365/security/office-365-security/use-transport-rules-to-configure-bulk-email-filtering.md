---
title: Использование правил потока почты для фильтрации массовых рассылок
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться использовать правила потока почты (правила транспорта) для идентификации и фильтрации массовой почты (серой почты) в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8030d21d414cb38769a6831391262fa3798a8838
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287297"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Использование правил потока почты для фильтрации массовой рассылки в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В организациях Microsoft 365 с почтовыми ящиками в Организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP использует политики защиты от нежелательной почты (также известные как политики фильтрации нежелательной почты или политики фильтрации содержимого) для проверки входящих сообщений на спам и массовой рассылки (также известной как серая почта). Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

Если вам нужны дополнительные параметры фильтрации массовой почты, можно создать правила потока почты (также известные как правила транспорта) для поиска текстовых шаблонов или фраз, которые часто используются в массовой рассылке, и пометить эти сообщения как нежелательные. Дополнительные сведения о массовой рассылке см. в сведениях о различиях между нежелательной почтой и массовой рассылкой [электронной почты?](what-s-the-difference-between-junk-email-and-bulk-email.md) И уровень жалоб на массовую рассылку [(BCL) в EOP.](bulk-complaint-level-values.md)

В этом разделе объясняется, как создавать эти правила потока обработки почты в Центре администрирования Exchange (EAC) и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Для этого необходимы соответствующие разрешения в Exchange Online или Exchange Online Protection. В частности, необходима  роль правил транспорта, назначенная по умолчанию группам ролей "Управление  организацией", "Управление соответствием требованиям" **(глобальным** администраторам) и "Управление записями".

  Дополнительную информацию см. в следующих статьях:

  - [Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Разрешения в автономном EOP](feature-permissions-in-eop.md)
  - [Изменение списка участников в группах ролей с помощью EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Чтобы открыть Центр администрирования Exchange в Exchange Online, см. центр [администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Чтобы открыть Центр администрирования Exchange в режиме автономных EOP, см. центр администрирования [Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о правилах потока почты в Exchange Online и автономных EOP см. в следующих темах:

  - [Правила потока обработки почты (правила транспорта) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения правил потока почты (предикаты) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правил потока почты в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Список слов и текстовых шаблонов, используемых для определения массовой рассылки в примерах, не является исчерпывающим; при необходимости можно добавлять и удалять записи. Тем не менее, они являются хорошей отправной точкой.

- Поиск слов и текстовых шаблонов в теме или других полях заголовка сообщения выполняется *после* расшифровки сообщения, к которому применялся метод кодирования для передачи сообщений MIME. Этот метод используется для передачи двоичных сообщений между SMTP-серверами с преобразованием их в текст ASCII. Вы не можете применять условия или исключения для поиска необработанных закодированных значений (обычно в формате Base64) в теме или других полях заголовка сообщения.

- Следующие процедуры пометят массовое сообщение как нежелательное для всей организации. Однако вы можете добавить еще одно условие, чтобы применить эти правила только к определенным получателям, чтобы можно было использовать агрессивное фильтрацию для нескольких пользователей с высокой ориентацией, тогда как остальные пользователи (которые в основном получают массовые сообщения электронной почты, для которых они подписаны) не влияют.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Использование EAC для создания правил потока почты, фильтруя массовые рассылки

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Щелкните **значок** ![ "Добавить", ](../../media/ITPro-EAC-AddIcon.png) а затем выберите **"Создать новое правило".**

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Name**: Enter a unique, descriptive name for the rule.

   - Нажмите кнопку **Дополнительные параметры**.

   - **Применяет это правило, если:** настройте один из следующих параметров, чтобы искать содержимое в сообщениях с помощью регулярных выражений (RegEx) или слов или фраз:

     - **Тема или тело** \> **тема** или текст соответствует этим текстовым  шаблонам: в диалоговом окке "Укажите  слова или фразы" введите одно из следующих значений, нажмите кнопку "Добавить значок добавления" и повторяйте их, пока не введите все ![ ](../../media/ITPro-EAC-AddIcon.png) значения.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Чтобы изменить запись, выберите  ее и нажмите значок ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования. Чтобы удалить запись, выберите ее и нажмите **значок "Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) удалить".

       После этого нажмите кнопку **ОК**.

     - **Тема или тело** \> **тема** или тело содержит любое из  этих слов: в диалоговом окке "Укажите  слова или фразы" введите одно из следующих значений, нажмите кнопку "Добавить значок добавления" и повторите это, пока не введите все ![ ](../../media/ITPro-EAC-AddIcon.png) значения.

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

      Чтобы изменить запись, выберите  ее и нажмите значок ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования. Чтобы удалить запись, выберите ее и нажмите **значок "Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) удалить".

       После этого нажмите кнопку **ОК**.

   - **Сделайте следующее:** выберите **"Изменить свойства сообщения",** чтобы установить уровень достоверности \> **нежелательной почты (SCL).** В **отозваемом** диалоговом окле "Указание SCL" настройте один из следующих параметров:

     - Чтобы пометить сообщения как **нежелательные,** выберите **6.** Действие, настроенное для принятия решения о фильтрации нежелательной почты в политиках борьбы с нежелательной почтой, применяется к сообщениям (значение по умолчанию — Переместить сообщение в папку нежелательной **почты).** 

     - Чтобы пометить сообщения как нежелательные с высокой **достоверности,** выберите **9.** Действие, настроенное для принятия решения о фильтрации нежелательной почты с высокой достоверности в политиках борьбы с нежелательной почтой, применяется к сообщениям (значение по умолчанию — Переместить сообщение в папку нежелательной **почты).** 

    Дополнительные сведения о значениях SCL см. в сведениях о доверии нежелательной почты [(SCL) в EOP.](spam-confidence-levels.md)

   По завершению нажмите кнопку **"Сохранить"**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Использование PowerShell для создания правил потока почты, фильтруя массовые рассылки

Используйте следующий синтаксис для создания одного или обоих правил потока почты (регулярных выражений и слов):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

В этом примере создается новое правило с именем "Массовая фильтрация электронной почты — RegEx", использующее тот же список регулярных выражений, что и ранее в этой теме, для того, чтобы сделать сообщения **нежелательными.**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

В этом примере создается новое правило с именем "Массовая фильтрация электронной почты — слова", которое использует тот же список слов из предыдущей темы, чтобы сделать сообщения нежелательными с высокой **достоверности.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы настроили правила потока почты для фильтрации массовых рассылок, сделайте следующее:

- В EAC перейдите к **правилу потока** обработки почты, выберите правило, щелкните значок редактирования и проверьте \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) параметры.

- В PowerShell замените имя правила и запустите следующую команду, чтобы \<Rule Name\> проверить параметры:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Из внешней учетной записи отправьте тестовые сообщения затронутого получателя, который содержит одну из фраз или текстовых шаблонов, и проверьте результаты.
