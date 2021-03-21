---
title: Использование правил потока почты для фильтрации массовой электронной почты
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
description: Администраторы могут узнать, как использовать правила потока почты (правила транспорта) для идентификации и фильтрации массовой почты (серой почты) в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8632a0b583ec0457ea1146f0e197321890414ce3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926682"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Использование правил потока почты для фильтрации массовой рассылки в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP использует политики защиты от нежелательной почты (также известные как политики фильтра спама или политики фильтрации контента) для сканирования входящих сообщений для нежелательной почты и массовой почты (также известной как серая почта). Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

Если вы хотите использовать дополнительные параметры для фильтрации массовой почты, можно создать правила потока почты (также известные как правила транспорта) для поиска текстовых шаблонов или фраз, которые часто находятся в массовой почте, и пометить эти сообщения как спам. Дополнительные сведения о массовой почте см. в дополнительных сведениях о разнице между нежелательной электронной почтой и массовой электронной [почтой?](what-s-the-difference-between-junk-email-and-bulk-email.md) и уровнем массовой [жалобы (BCL) в EOP.](bulk-complaint-level-values.md)

В этом разделе объясняется, как создавать эти правила потока почты в центре администрирования Exchange (EAC) и PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Вам необходимо получить разрешения в Exchange Online или Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье. В частности, вам  нужна роль Правил транспорта, которая по умолчанию назначена группам  ролей **"Управление** организацией",  "Управление соответствием требованиям" (глобальные администраторы) и "Управление записями".

  Дополнительную информацию см. в следующих статьях:

  - [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Разрешения в автономном EOP](feature-permissions-in-eop.md)
  - [Использование EAC измените список участников в группах ролей](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Чтобы открыть центр администрирования в Exchange Online, см. в центре [администрирования Exchange в Exchange Online.](/Exchange/exchange-admin-center) Чтобы открыть EAC в автономных EOP, см. в центре администрирования Exchange в режиме [автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Дополнительные сведения о правилах потока почты в Exchange Online и автономных EOP см. в следующих темах:

  - [Правила потока обработки почты (правила транспорта) в Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения правил потока почты (предикаты) в Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правила потока почты в Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Список слов и текстовых шаблонов, используемых для идентификации массовой почты в примерах, не является исчерпывающим; при необходимости можно добавлять и удалять записи. Тем не менее, они являются хорошей отправной точкой.

- Поиск слов и текстовых шаблонов в теме или других полях заголовка сообщения выполняется *после* расшифровки сообщения, к которому применялся метод кодирования для передачи сообщений MIME. Этот метод используется для передачи двоичных сообщений между SMTP-серверами с преобразованием их в текст ASCII. Вы не можете применять условия или исключения для поиска необработанных закодированных значений (обычно в формате Base64) в теме или других полях заголовка сообщения.

- Следующие процедуры отмечают массовое сообщение как спам для всей организации. Однако можно добавить еще одно условие, чтобы применять эти правила только к конкретным получателям, чтобы можно было использовать агрессивный фильтрацию для нескольких пользователей с высокой целевой аудиторией, в то время как остальные пользователи (которые в основном получают массовое письмо, на которое они подписались) не влияют.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Используйте EAC для создания правил потока почты, фильтруя массовую электронную почту

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Нажмите **кнопку Добавить** ![ значок Добавить, ](../../media/ITPro-EAC-AddIcon.png) а затем выберите Создать новое **правило**.

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Имя.** Введите уникальное, описательное имя для правила.

   - Нажмите кнопку **Дополнительные параметры**.

   - **Применить это правило,** если: настройте один из следующих параметров, чтобы искать контент в сообщениях с помощью регулярных выражений (RegEx) или слов или фраз:

     - **Субъект или тело** \> **тема** или тело совпадает с этими  текстовыми шаблонами. В диалоговом окте "Укажите слова или фразы", введите одно из следующих значений, нажмите кнопку **Добавить** значок добавить и повторите, пока не введите все ![ ](../../media/ITPro-EAC-AddIcon.png) значения.

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

      Чтобы изменить запись, выберите ее и нажмите **кнопку Изменить значок Изменить** ![ ](../../media/ITPro-EAC-EditIcon.png) . Чтобы удалить запись, выберите ее и нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

       После этого нажмите кнопку **ОК**.

     - **Субъект или тело** \> **тема** или тело включает любое из  этих слов. В диалоговом окантовке "Укажите слова или фразы", введите одно из следующих значений, нажмите кнопку **Добавить** значок добавить и повторите, пока не введите все ![ ](../../media/ITPro-EAC-AddIcon.png) значения.

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

      Чтобы изменить запись, выберите ее и нажмите **кнопку Изменить значок Изменить** ![ ](../../media/ITPro-EAC-EditIcon.png) . Чтобы удалить запись, выберите ее и нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

       После этого нажмите кнопку **ОК**.

   - **У следующих**: **Выберите Изменение свойств сообщения** установить уровень доверия нежелательной почты \> **(SCL).** В **диалоговом окантовке Указать SCL,** который отображается, настройте один из следующих параметров:

     - Чтобы отметить сообщения как **спам,** выберите **6**. Действие, настроенное для вердиктов фильтрации нежелательной почты в политиках по борьбе со спамом, применяется к сообщениям (по умолчанию значение **Move message to Junk Email folder).** 

     - Для маркировки сообщений в качестве **нежелательной почты высокой уверенности** выберите **9**. Действие, настроенное для вердиктов о фильтрации нежелательной почты с высоким уровнем доверия в политиках по борьбе со спамом, применяется к сообщениям (по умолчанию значение **Move message to Junk Email folder).** 

    Дополнительные сведения о значениях SCL см. в сообщении уровня доверия к нежелательной почте [(SCL) в EOP.](spam-confidence-levels.md)

   По завершению нажмите кнопку **Сохранить**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Используйте PowerShell для создания правил потока почты, которые фильтруют массовую электронную почту

Используйте следующий синтаксис для создания одного или обоих правил потока почты (регулярные выражения и слова):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

В этом примере создается новое правило с именем "Массовая фильтрация электронной почты - RegEx", которое использует тот же список регулярных выражений из более ранних разделов для набора сообщений, как **спам**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

В этом примере создается новое правило с именем "Массовая фильтрация электронной почты - слова", которое использует тот же список слов из более ранних разделов для набора сообщений, как спам высокой **уверенности**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы настроили правила потока почты для фильтрации массовой почты, сделайте все следующие действия:

- В EAC перейдите к **правилу потока почты** выберите правило \>  \> \> нажмите кнопку Изменить значок **Редактирование** ![ и проверьте ](../../media/ITPro-EAC-EditIcon.png) параметры.

- В PowerShell замените имя правила и запустите следующую команду для \<Rule Name\> проверки параметров:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Из внешней учетной записи отправьте тестовые сообщения пострадавшему получателю, содержаму одну из фраз или текстовых шаблонов, и убедитесь в результатах.