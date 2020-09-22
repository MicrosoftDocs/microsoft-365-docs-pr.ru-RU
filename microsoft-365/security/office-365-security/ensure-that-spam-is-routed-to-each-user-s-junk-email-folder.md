---
title: Настройка EOP для нежелательной почты в гибридных средах
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться маршрутизировать спам в папки нежелательной почты пользователя в гибридной среде Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4c01ad0e8efa4d28e1b5d1e72b3daa87bb01b619
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196597"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Настройка автономных EOP для доставки спама в папку нежелательной почты в гибридных средах

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Этот раздел предназначен только для изолированных клиентов EOP в гибридных средах. Эта статья не относится к клиентам Microsoft 365 с почтовыми ящиками Exchange Online.

Если вы используете автономный клиент Exchange Online Protection (EOP) в гибридной среде, вам необходимо настроить локальную организацию Exchange на распознавание и перевод фильтра нежелательной почты вердиктс EOP, поэтому правило нежелательной почты в локальном почтовом ящике может перемещать сообщения в папку "Нежелательная почта".

В частности, необходимо создать правила для поток обработки почты (также называемые правилами транспорта) в локальной организации Exchange с условиями поиска сообщений, которые имеют любой из следующих заголовков и значений EOP защиты от нежелательной почты, а также действия, которые задают уровень вероятности нежелательной почты (SCL) этих сообщений равным 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (сообщение с пометкой "Нежелательная почта" при фильтрации спама)

- `X-Forefront-Antispam-Report: SFV:SKS` (сообщение с пометкой "Нежелательная почта" для правил обработки почты в EOP перед фильтрацией нежелательной почты)

- `X-Forefront-Antispam-Report: SFV:SKB` (сообщение, помеченное фильтром нежелательной почты, в связи с адресом электронной почты отправителя или доменом электронной почты из списка заблокированных отправителей или списка заблокированных доменов в EOP)

Дополнительные сведения об этих значениях заголовков можно узнать в статье [заголовки сообщений по защите от нежелательной почты](anti-spam-message-headers.md).

В этом разделе описывается, как создать эти правила для почтовых ящиков: центр администрирования Exchange и Командная консоль Exchange (Exchange PowerShell) в локальной организации Exchange.

> [!TIP]
> Вместо доставки сообщений в папку нежелательной почты локального пользователя можно настроить политики защиты от нежелательной почты в EOP для помещения нежелательных сообщений в карантин в EOP. Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Прежде чем выполнять эти процедуры, необходимо назначить разрешения в локальной среде Exchange. В частности, необходимо назначить роль " **правила транспорта** ", которая назначается для ролей управления **организацией**, **управления соответствием требованиям**и управления **записями** по умолчанию. Дополнительные сведения см в разделе [Добавление членов в группу ролей](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).

- Если и когда сообщение доставляется в папку нежелательной почты в локальной организации Exchange, управляется сочетанием следующих параметров:

  - Значение параметра _SCLJunkThreshold_ в командлете [Set – OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) в командной консоли Exchange. Значение по умолчанию — 4, что означает, что сообщение нежелательной почты из 5 или выше должно доставлять сообщение в папку нежелательной почты пользователя.

  - Значение параметра _SCLJunkThreshold_ командлета [Set — Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) в командной консоли Exchange. Значение по умолчанию — пустое ($null), что означает, что используется параметр Организации.

  Подробнее о [порогах вероятности нежелательной почты Exchange (вероятности нежелательной почты)](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).

  - Указывает, включено ли правило нежелательной почты в почтовом ящике (значение параметра _enabled_ $true в командлете [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) в командной консоли Exchange). Это правило нежелательной почты, которое фактически перемещает сообщение в папку "Нежелательная почта" после доставки. По умолчанию правило нежелательной почты включено в почтовых ящиках. Дополнительные сведения см. в статье [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).

- Чтобы открыть центр администрирования Exchange на сервере Exchange Server, ознакомьтесь со статьей [центр администрирования Exchange в Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center). Чтобы открыть командную консоль Exchange, ознакомьтесь [со статьей открытие консоли управления Exchange](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).

- Дополнительные сведения о правилах обработки почтового ящика в локальном Exchange представлены в следующих разделах:

  - [Правила для почтового процесса в Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Условия и исключения правила для обработки почтового процесса (предикаты) в Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Действия правил обработки почты в Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Использование центра администрирования Exchange для создания правил для почтовых ящиков, в которых задаются нежелательные сообщения EOP

1. В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.

2. Нажмите **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) и выберите **создать новое правило** в раскрывающемся списке.

3. На открывшейся странице **Новое правило** настройте следующие параметры:

   - **Name**: введите уникальное описательное имя правила. Например:

     - EOP SFV: SPM на SCL 6

     - EOP SFV: СКС на SCL 6

     - EOP SFV: СКБ на SCL 6

   - Нажмите кнопку **Дополнительные параметры**.

   - **Применять это правило, если**: выберите **заголовок сообщения** , \> **содержащий любое из этих слов**.

     В **заголовке ввод текста содержит предложение ввести слова** , которое появляется, выполните следующие действия:

     - Нажмите **Ввод текста**. В появившемся диалоговом окне **Укажите имя заголовка** введите **X — Forefront – защиты от спама – Report** , а затем нажмите кнопку **ОК**.

     - Нажмите кнопку  **ввод слов**. В появившемся диалоговом окне **Укажите слова или фразы** введите одно из значений заголовка нежелательной почты EOP (**SFV: SPM**, **SFV: СКС**или **SFV: СКБ**), нажмите **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) , а затем нажмите кнопку **ОК**.

   - **Выполните следующие**действия: выберите **изменить свойства сообщения** \> **установите уровень вероятности нежелательной почты (SCL)**.

     В появившемся диалоговом окне **Указание вероятности нежелательной почты** выберите **6** (значение по умолчанию — **5**).

   Когда все будет готово, нажмите кнопку **сохранить**

Повторите эти действия для оставшихся EOP спама вредоносности (**SFV: SPM**, **SFV: СКС**или **SFV: СКБ**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Использование Командная консоль Exchange для создания правил для обработки почты, заданных для нежелательной почты EOP нежелательных сообщений

Используйте следующий синтаксис для создания трех правил для обработки почтового процесса:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Например:

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

Чтобы убедиться, что вы успешно настроили автономный EOP для доставки спама в папку нежелательной почты в гибридной среде, выполните одно из указанных ниже действий.

- В центре администрирования Exchange перейдите к разделу правила обработки **почты** \> **Rules**, выберите правило, а затем щелкните **изменить** ![ значок редактирования, ](../../media/ITPro-EAC-EditIcon.png) чтобы проверить параметры.

- В командной консоли Exchange замените на \<RuleName\> имя правила для процесса обработки почты и Рул следующую команду для проверки параметров:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- В внешней почтовой системе **, которая не сканирует исходящие сообщения для спама**, отправьте общий тест для сообщения о незапрошенной массовой рассылке (сообщение gtube) заданному получателю и убедитесь, что он доставлен в папку нежелательной почты. Сообщение GTUBE похоже на текстовый файл Европейского института исследования антивирусных программ (EICAR) для тестирования параметров вредоносных программ.

  Чтобы отправить сообщение сообщение GTUBE, включите следующий текст в текст сообщения электронной почты в одну строку без пробелов и разрывов строк:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
