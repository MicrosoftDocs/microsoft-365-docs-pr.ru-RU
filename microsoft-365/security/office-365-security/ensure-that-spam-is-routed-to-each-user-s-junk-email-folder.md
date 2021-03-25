---
title: Настройка EOP для нежелательной почты в гибридных средах
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как отправлять спам в папки нежелательной почты пользователей в гибридной среде Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205516"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Настройка автономных EOP для доставки нежелательной почты в папку нежелательной почты в гибридных средах

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

> [!IMPORTANT]
> Этот раздел касается только автономных клиентов EOP в гибридных средах. Этот раздел не применяется к клиентам Microsoft 365 с почтовыми ящиками Exchange Online.

Если вы автономный клиент Exchange Online Protection (EOP) в гибридной среде, необходимо настроить локальное устройство Exchange для распознавания и перевода вердиктов EOP по фильтрации нежелательной почты, поэтому правило нежелательной почты в локальном почтовом ящике может перемещать сообщения в папку нежелательной почты.

В частности, необходимо создать правила потока почты (также известные как правила транспорта) в локальной организации Exchange с условиями поиска сообщений с любыми из следующих загонщиков и значений EOP по борьбе со спамом, а также действиями, которые устанавливают уровень доверия к нежелательной почте (SCL) этих сообщений до 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (сообщение, помеченное как спам путем фильтрации нежелательной почты)

- `X-Forefront-Antispam-Report: SFV:SKS` (сообщение, помеченное как спам по правилам потока почты в EOP перед фильтрацией нежелательной почты)

- `X-Forefront-Antispam-Report: SFV:SKB` (сообщение, помеченное как спам путем фильтрации нежелательной почты из-за того, что адрес электронной почты или домен электронной почты отправитель находится в заблокированном списке отправитель или заблокированном списке доменов в EOP)

Дополнительные сведения об этих значениях загона см. в загонах сообщений по борьбе [со спамом.](anti-spam-message-headers.md)

В этом разделе описывается, как создать эти правила потока почты в центре администрирования Exchange (EAC) и в exchange Management Shell (Exchange PowerShell) в локальной организации Exchange.

> [!TIP]
> Вместо доставки сообщений в папку нежелательной почты локального пользователя можно настроить политики по борьбе со спамом в EOP для карантиных сообщений нежелательной почты в EOP. Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы сделать эти процедуры, необходимо получить разрешения в локальной среде Exchange. В частности, вам должна быть  назначена роль "Правила транспорта", которая по  умолчанию назначена роли "Управление организацией", "Управление соответствием требованиям" и "Управление записями".   Дополнительные сведения см. в [добавлении участников в группу ролей.](/Exchange/permissions/role-group-members#add-members-to-a-role-group)

- Если и когда сообщение доставляется в папку нежелательной почты в локальной организации Exchange, управляется сочетанием следующих параметров:

  - Значение _параметра SCLJunkThreshold_ для команды [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) в оболочке управления Exchange. По умолчанию значение 4, что означает, что SCL из 5 или выше должен доставить сообщение в папку нежелательной электронной почты пользователя.

  - Значение _параметра SCLJunkThreshold_ для команды [Set-Mailbox](/powershell/module/exchange/set-mailbox) в оболочке управления Exchange. Значение по умолчанию пусто ($null), что означает, что используется параметр организации.

  Подробные сведения см. в [материале Exchange spam confidence level (SCL).](/Exchange/antispam-and-antimalware/antispam-protection/scl)

  - Включено ли правило нежелательной почты в  почтовом ящике (значение параметра Включено $true в комлете [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) в оболочке управления Exchange). Это правило нежелательной почты, которое фактически перемещает сообщение в папку нежелательной почты после доставки. По умолчанию правило нежелательной почты включено в почтовых ящиках. Дополнительные сведения см. в статье [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).

- Чтобы открыть центр администрирования на Exchange Server, см. в [Exchange Server.](/Exchange/architecture/client-access/exchange-admin-center) Чтобы открыть командную консоль Exchange, см. статью [Запуск командной консоли Exchange](/powershell/exchange/open-the-exchange-management-shell).

- Дополнительные сведения о правилах потока почты в локальной exchange см. в следующих темах:

  - [Правила потока почты в Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения правил потока почты (предикаты) в Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правила потока почты в Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Используйте EAC для создания правил потока почты, которые устанавливают SCL сообщений нежелательной почты EOP

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Нажмите **кнопку** Добавить значок Добавить и выберите Создать новое правило в ![ ](../../media/ITPro-EAC-AddIcon.png) выпадаемом, который отображается. 

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Имя.** Введите уникальное, описательное имя для правила. Пример.

     - EOP SFV:SPM для SCL 6

     - EOP SFV:SKS для SCL 6

     - EOP SFV:SKB для SCL 6

   - Нажмите кнопку **Дополнительные параметры**.

   - **Применить это правило,** если: **Выберите заглавную** часть \> **сообщения, включаемую любое из этих слов.**

     В **текстовом заголовке Enter содержится предложение Ввод** слов, которое отображается, сделайте следующие действия:

     - Нажмите **кнопку Ввод текста**. В **диалоговом окте** "Укажите имя" введите **X-Forefront-Antispam-Report** и нажмите **кнопку ОК.**

     - Нажмите  **кнопку Введите слова**. В  диалоговом окну "Укажите слова или фразы", введите одно из значений загона нежелательной почты EOP **(SFV:SPM,** **SFV:SKS** или **SFV:SKB),** нажмите кнопку Добавить значок Добавить, а затем нажмите  ![ ](../../media/ITPro-EAC-AddIcon.png) **кнопку ОК**.

   - **Сделайте следующее:** **Выберите Изменение свойств сообщений** Установите уровень доверия нежелательной почты \> **(SCL).**

     В **диалоговом окте указать SCL,** который отображается, выберите **6** (по умолчанию значение **5).**

   По завершению нажмите кнопку **Сохранить**

Повторите эти действия для оставшихся значений вердикта о нежелательной почте EOP **(SFV:SPM,** **SFV:SKS** или **SFV:SKB).**

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Используйте оболочку управления Exchange для создания правил потока почты, которые устанавливают SCL сообщений нежелательной почты EOP

Чтобы создать три правила потока почты, используйте следующий синтаксис:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Пример.

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы успешно настроили автономный EOP для доставки нежелательной почты в папку нежелательной почты в гибридной среде, сделайте все следующие действия:

- В EAC перейдите к правилам потока **почты,** выберите правило, а затем нажмите кнопку Изменить изменить значок, чтобы проверить \>   ![ ](../../media/ITPro-EAC-EditIcon.png) параметры.

- В командной командной оболочке Exchange замените имя правила потока почты и обнажь следующую команду для проверки \<RuleName\> параметров:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- Во внешней системе электронной почты, которая не сканирует исходящие сообщения для нежелательной почты, отправьте сообщение Generic Test for Unsolicited Bulk Email (GTUBE) пострадавшему получателю и подтвердите, что оно доставлено в папку нежелательной почты. Сообщение GTUBE похоже на текстовый файл Европейского института исследования антивирусных программ (EICAR) для тестирования параметров вредоносных программ.

  Чтобы отправить сообщение GTUBE, включайте следующий текст в текст сообщения электронной почты в одной строке без пробелов или разрывов строки:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```