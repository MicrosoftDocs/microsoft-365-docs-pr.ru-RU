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
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910862"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="d5067-103">Настройка автономных EOP для доставки нежелательной почты в папку нежелательной почты в гибридных средах</span><span class="sxs-lookup"><span data-stu-id="d5067-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d5067-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="d5067-104">**Applies to**</span></span>
-  [<span data-ttu-id="d5067-105">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d5067-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

> [!IMPORTANT]
> <span data-ttu-id="d5067-106">Этот раздел касается только автономных клиентов EOP в гибридных средах.</span><span class="sxs-lookup"><span data-stu-id="d5067-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="d5067-107">Этот раздел не применяется к клиентам Microsoft 365 с почтовыми ящиками Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d5067-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="d5067-108">Если вы автономный клиент Exchange Online Protection (EOP) в гибридной среде, необходимо настроить локальное устройство Exchange для распознавания и перевода вердиктов EOP по фильтрации нежелательной почты, поэтому правило нежелательной почты в локальном почтовом ящике может перемещать сообщения в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d5067-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="d5067-109">В частности, необходимо создать правила потока почты (также известные как правила транспорта) в локальной организации Exchange с условиями поиска сообщений с любыми из следующих загонщиков и значений EOP по борьбе со спамом, а также действиями, которые устанавливают уровень доверия к нежелательной почте (SCL) этих сообщений до 6:</span><span class="sxs-lookup"><span data-stu-id="d5067-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="d5067-110">`X-Forefront-Antispam-Report: SFV:SPM` (сообщение, помеченное как спам путем фильтрации нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="d5067-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="d5067-111">`X-Forefront-Antispam-Report: SFV:SKS` (сообщение, помеченное как спам по правилам потока почты в EOP перед фильтрацией нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="d5067-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="d5067-112">`X-Forefront-Antispam-Report: SFV:SKB` (сообщение, помеченное как спам путем фильтрации нежелательной почты из-за того, что адрес электронной почты или домен электронной почты отправитель находится в заблокированном списке отправитель или заблокированном списке доменов в EOP)</span><span class="sxs-lookup"><span data-stu-id="d5067-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="d5067-113">Дополнительные сведения об этих значениях загона см. в загонах сообщений по борьбе [со спамом.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="d5067-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="d5067-114">В этом разделе описывается, как создать эти правила потока почты в центре администрирования Exchange (EAC) и в exchange Management Shell (Exchange PowerShell) в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5067-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="d5067-115">Вместо доставки сообщений в папку нежелательной почты локального пользователя можно настроить политики по борьбе со спамом в EOP для карантиных сообщений нежелательной почты в EOP.</span><span class="sxs-lookup"><span data-stu-id="d5067-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="d5067-116">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d5067-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d5067-117">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d5067-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d5067-118">Чтобы сделать эти процедуры, необходимо получить разрешения в локальной среде Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5067-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="d5067-119">В частности, вам должна быть  назначена роль "Правила транспорта", которая по  умолчанию назначена роли "Управление организацией", "Управление соответствием требованиям" и "Управление записями".  </span><span class="sxs-lookup"><span data-stu-id="d5067-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="d5067-120">Дополнительные сведения см. в [добавлении участников в группу ролей.](/Exchange/permissions/role-group-members#add-members-to-a-role-group)</span><span class="sxs-lookup"><span data-stu-id="d5067-120">For more information, see [Add members to a role group](/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="d5067-121">Если и когда сообщение доставляется в папку нежелательной почты в локальной организации Exchange, управляется сочетанием следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d5067-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="d5067-122">Значение _параметра SCLJunkThreshold_ для команды [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) в оболочке управления Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5067-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="d5067-123">По умолчанию значение 4, что означает, что SCL из 5 или выше должен доставить сообщение в папку нежелательной электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5067-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="d5067-124">Значение _параметра SCLJunkThreshold_ для команды [Set-Mailbox](/powershell/module/exchange/set-mailbox) в оболочке управления Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5067-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="d5067-125">Значение по умолчанию пусто ($null), что означает, что используется параметр организации.</span><span class="sxs-lookup"><span data-stu-id="d5067-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="d5067-126">Подробные сведения см. в [материале Exchange spam confidence level (SCL).](/Exchange/antispam-and-antimalware/antispam-protection/scl)</span><span class="sxs-lookup"><span data-stu-id="d5067-126">For details, see [Exchange spam confidence level (SCL) thresholds](/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="d5067-127">Включено ли правило нежелательной почты в  почтовом ящике (значение параметра Включено $true в комлете [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) в оболочке управления Exchange).</span><span class="sxs-lookup"><span data-stu-id="d5067-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="d5067-128">Это правило нежелательной почты, которое фактически перемещает сообщение в папку нежелательной почты после доставки.</span><span class="sxs-lookup"><span data-stu-id="d5067-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="d5067-129">По умолчанию правило нежелательной почты включено в почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="d5067-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="d5067-130">Дополнительные сведения см. в статье [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="d5067-130">For more information, see [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="d5067-131">Чтобы открыть центр администрирования на Exchange Server, см. в [Exchange Server.](/Exchange/architecture/client-access/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="d5067-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="d5067-132">Чтобы открыть командную консоль Exchange, см. статью [Запуск командной консоли Exchange](/powershell/exchange/open-the-exchange-management-shell).</span><span class="sxs-lookup"><span data-stu-id="d5067-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="d5067-133">Дополнительные сведения о правилах потока почты в локальной exchange см. в следующих темах:</span><span class="sxs-lookup"><span data-stu-id="d5067-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="d5067-134">Правила потока почты в Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d5067-134">Mail flow rules in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="d5067-135">Условия и исключения правил потока почты (предикаты) в Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d5067-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="d5067-136">Действия правила потока почты в Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d5067-136">Mail flow rule actions in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="d5067-137">Используйте EAC для создания правил потока почты, которые устанавливают SCL сообщений нежелательной почты EOP</span><span class="sxs-lookup"><span data-stu-id="d5067-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="d5067-138">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="d5067-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="d5067-139">Нажмите **кнопку** Добавить значок Добавить и выберите Создать новое правило в ![ ](../../media/ITPro-EAC-AddIcon.png) выпадаемом, который отображается. </span><span class="sxs-lookup"><span data-stu-id="d5067-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="d5067-140">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d5067-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d5067-141">**Имя.** Введите уникальное, описательное имя для правила.</span><span class="sxs-lookup"><span data-stu-id="d5067-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="d5067-142">Например:</span><span class="sxs-lookup"><span data-stu-id="d5067-142">For example:</span></span>

     - <span data-ttu-id="d5067-143">EOP SFV:SPM для SCL 6</span><span class="sxs-lookup"><span data-stu-id="d5067-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="d5067-144">EOP SFV:SKS для SCL 6</span><span class="sxs-lookup"><span data-stu-id="d5067-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="d5067-145">EOP SFV:SKB для SCL 6</span><span class="sxs-lookup"><span data-stu-id="d5067-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="d5067-146">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="d5067-146">Click **More Options**.</span></span>

   - <span data-ttu-id="d5067-147">**Применить это правило,** если: **Выберите заглавную** часть \> **сообщения, включаемую любое из этих слов.**</span><span class="sxs-lookup"><span data-stu-id="d5067-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="d5067-148">В **текстовом заголовке Enter содержится предложение Ввод** слов, которое отображается, сделайте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d5067-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="d5067-149">Нажмите **кнопку Ввод текста**.</span><span class="sxs-lookup"><span data-stu-id="d5067-149">Click **Enter text**.</span></span> <span data-ttu-id="d5067-150">В **диалоговом окте** "Укажите имя" введите **X-Forefront-Antispam-Report** и нажмите **кнопку ОК.**</span><span class="sxs-lookup"><span data-stu-id="d5067-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="d5067-151">Нажмите  **кнопку Введите слова**.</span><span class="sxs-lookup"><span data-stu-id="d5067-151">Click  **Enter words**.</span></span> <span data-ttu-id="d5067-152">В  диалоговом окну "Укажите слова или фразы", введите одно из значений загона нежелательной почты EOP **(SFV:SPM,** **SFV:SKS** или **SFV:SKB),** нажмите кнопку Добавить значок Добавить, а затем нажмите  ![ ](../../media/ITPro-EAC-AddIcon.png) **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="d5067-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="d5067-153">**Сделайте следующее:** **Выберите Изменение свойств сообщений** Установите уровень доверия нежелательной почты \> **(SCL).**</span><span class="sxs-lookup"><span data-stu-id="d5067-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="d5067-154">В **диалоговом окте указать SCL,** который отображается, выберите **6** (по умолчанию значение **5).**</span><span class="sxs-lookup"><span data-stu-id="d5067-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="d5067-155">По завершению нажмите кнопку **Сохранить**</span><span class="sxs-lookup"><span data-stu-id="d5067-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="d5067-156">Повторите эти действия для оставшихся значений вердикта о нежелательной почте EOP **(SFV:SPM,** **SFV:SKS** или **SFV:SKB).**</span><span class="sxs-lookup"><span data-stu-id="d5067-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="d5067-157">Используйте оболочку управления Exchange для создания правил потока почты, которые устанавливают SCL сообщений нежелательной почты EOP</span><span class="sxs-lookup"><span data-stu-id="d5067-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="d5067-158">Чтобы создать три правила потока почты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d5067-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="d5067-159">Например:</span><span class="sxs-lookup"><span data-stu-id="d5067-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="d5067-160">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="d5067-160">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d5067-161">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="d5067-161">How do you know this worked?</span></span>

<span data-ttu-id="d5067-162">Чтобы убедиться, что вы успешно настроили автономный EOP для доставки нежелательной почты в папку нежелательной почты в гибридной среде, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d5067-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="d5067-163">В EAC перейдите к правилам потока **почты,** выберите правило, а затем нажмите кнопку Изменить изменить значок, чтобы проверить \>   ![ ](../../media/ITPro-EAC-EditIcon.png) параметры.</span><span class="sxs-lookup"><span data-stu-id="d5067-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="d5067-164">В командной командной оболочке Exchange замените имя правила потока почты и обнажь следующую команду для проверки \<RuleName\> параметров:</span><span class="sxs-lookup"><span data-stu-id="d5067-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="d5067-165">Во внешней системе электронной почты, которая не сканирует исходящие сообщения для нежелательной почты, отправьте сообщение Generic Test for Unsolicited Bulk Email (GTUBE) пострадавшему получателю и подтвердите, что оно доставлено в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d5067-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="d5067-166">Сообщение GTUBE похоже на текстовый файл Европейского института исследования антивирусных программ (EICAR) для тестирования параметров вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="d5067-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="d5067-167">Чтобы отправить сообщение GTUBE, включайте следующий текст в текст сообщения электронной почты в одной строке без пробелов или разрывов строки:</span><span class="sxs-lookup"><span data-stu-id="d5067-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```