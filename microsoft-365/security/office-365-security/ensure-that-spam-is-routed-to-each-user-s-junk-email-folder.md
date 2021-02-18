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
description: Администраторы могут узнать, как отправлять нежелатели в папки нежелательной почты пользователей в гибридной среде Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b8fbc1b065e348f759806d80fd85421eb9d66098
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288877"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Настройка автономных EOP для доставки нежелательной почты в папку нежелательной почты в гибридных средах

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

> [!IMPORTANT]
> Этот раздел касается только пользователей автономных EOP в гибридных средах. Этот раздел не относится к клиентам Microsoft 365 с почтовыми ящиками Exchange Online.

Если вы автономный клиент Exchange Online Protection (EOP) в гибридной среде, необходимо настроить свою локальной организации Exchange для распознавания и перевода решения фильтрации нежелательной почты EOP, поэтому правило нежелательной почты в локальном почтовом ящике может перемещать сообщения в папку нежелательной почты.

В частности, необходимо создать правила потока почты (также известные как правила транспорта) в локальной организации Exchange с условиями, которые находят сообщения с любым из следующих заглавных и значений EOP для нежелательной почты, а также действиями, которые устанавливают уровень безопасности нежелательной почты (SCL) этих сообщений, равное 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (Сообщение, помеченное как нежелательное с помощью фильтрации нежелательной почты)

- `X-Forefront-Antispam-Report: SFV:SKS` (Сообщение, помеченное как нежелательное правилами потока почты в EOP перед фильтрацией нежелательной почты)

- `X-Forefront-Antispam-Report: SFV:SKB` (Сообщение, помеченное как нежелательное с помощью фильтрации нежелательной почты из-за того, что адрес электронной почты или домен электронной почты отправитель находится в списке заблокированных отправников или в списке заблокированных доменов в EOP)

Дополнительные сведения об этих значениях см. в сообщениях для борьбы [с нежелательной почтой.](anti-spam-message-headers.md)

В этом разделе описывается создание этих правил потока обработки почты в Центре администрирования Exchange (EAC) и в exchange Management Shell (Exchange PowerShell) в локальной организации Exchange.

> [!TIP]
> Вместо доставки сообщений в папку нежелательной почты локального пользователя можно настроить политики борьбы со нежелательной почтой в EOP для помещения нежелательных сообщений на карантин в EOP. Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Для этого необходимы соответствующие разрешения в локальной среде Exchange. В частности, вам должна быть  назначена роль правил транспорта, которая по умолчанию  назначена ролям управления **организацией,** управления соответствием требованиям и управления записями. Дополнительные сведения см. в [подстройки "Добавление участников в группу ролей".](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)

- Если и когда сообщение доставляется в папку нежелательной почты в локальной организации Exchange, управляется сочетанием следующих параметров:

  - Значение _параметра SCLJunkThreshold_ в параметре [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) в exchange Management Shell. Значение по умолчанию — 4, что означает, что уровень нежелательной почты, который составляет 5 или более, должен доставить сообщение в папку нежелательной почты пользователя.

  - Значение _параметра SCLJunkThreshold_ в параметре [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) в exchange Management Shell. Значение по умолчанию пусто ($null), что означает, что используется параметр организации.

  Подробные сведения см. в сведениях о пороговых значениях уровня нежелательной почты [(SCL) Exchange.](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)

  - Включено ли правило нежелательной почты для почтового ящика (значение параметра _Enabled_ $true в cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) в exchange Management Shell). Это правило нежелательной почты перемещает сообщение в папку нежелательной почты после доставки. По умолчанию правило нежелательной почты включено для почтовых ящиков. Дополнительные сведения см. в статье [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).

- Чтобы открыть Центр администрирования Exchange в Exchange Server, см. центр администрирования [Exchange в Exchange Server.](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center) Чтобы открыть командную консоль Exchange, см. статью [Запуск командной консоли Exchange](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).

- Дополнительные сведения о правилах потока почты в локальной организации Exchange см. в следующих темах:

  - [Правила потока почты в Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения правил потока почты (предикаты) в Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правил потока почты в Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Использование EAC для создания правил потока почты, которые устанавливают SCL для нежелательных сообщений EOP

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Щелкните **значок** "Добавить" и выберите "Создать новое правило" в отображаемом ![ ](../../media/ITPro-EAC-AddIcon.png) выпадаке. 

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Name**: Enter a unique, descriptive name for the rule. Например,

     - EOP SFV:SPM to SCL 6

     - EOP SFV:SKS to SCL 6

     - EOP SFV:SKB to SCL 6

   - Нажмите кнопку **Дополнительные параметры**.

   - **Применив это правило,** если :Select **A message** \> **header includes any of these words**.

     В **текстовом заголовке "Ввод"** содержится предложение "Введите слова", которое отображается, и сделайте следующее:

     - Нажмите **кнопку ВВОД текста.** В от **имени загона** введите **X-Forefront-Antispam-Report** и нажмите кнопку **"ОК".**

     - Нажмите  **кнопку "Введите слова"**. В  диалоговом окну "Укажите слова или фразы" введите одно из значений в загон нежелательной почты EOP  **(SFV:SPM,** **SFV:SKS или** **SFV:SKB),** нажмите кнопку "Добавить" и нажмите кнопку "ОК". ![ ](../../media/ITPro-EAC-AddIcon.png) 

   - **Сделайте следующее:** select **Modify the message properties** \> **Set the spam confidence level (SCL)**.

     В **отобратом диалоговом** окле "Укажите SCL" выберите **6** (значение по умолчанию **— 5).**

   По завершению нажмите кнопку **"Сохранить"**

Повторите эти действия для оставшихся значений решения о нежелательной почте EOP (**SFV:SPM,** **SFV:SKS** или **SFV:SKB).**

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Использование exchange Management Shell для создания правил потока почты, которые устанавливают SCL нежелательных сообщений EOP

Используйте следующий синтаксис для создания трех правил потока почты:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Например,

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы успешно настроили автономный EOP для доставки нежелательной почты в папку нежелательной почты в гибридной среде, сделайте следующее:

- В EAC перейдите к **правилам** потока обработки почты, выберите правило и нажмите значок редактирования, чтобы \>   ![ проверить ](../../media/ITPro-EAC-EditIcon.png) параметры.

- В командной оболочке Exchange замените имя правила потока почты и перенаправить следующую команду для проверки \<RuleName\> параметров:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- Во внешней почтовой системе, которая не сканирует исходящие сообщения на наличие нежелательной **почты,** отправьте сообщение generic Test for Unsolicited Bulk Email (GTUBE) затронутого получателя и подтвердите, что оно доставлено в папку нежелательной почты. Сообщение GTUBE похоже на текстовый файл Европейского института исследования антивирусных программ (EICAR) для тестирования параметров вредоносных программ.

  Чтобы отправить сообщение GTUBE, включайте следующий текст в текст сообщения электронной почты в одной строке без пробелов или разрывов строки:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
