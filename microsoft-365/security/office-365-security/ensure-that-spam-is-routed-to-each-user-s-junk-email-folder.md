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
description: Администраторы могут научиться настраивать локальную среду Exchange для маршрутизации нежелательной почты в папки нежелательной почты локальных пользователей, если они используют автономную защиту Exchange Online (EOP) в гибридных средах.
ms.openlocfilehash: f2964324c6d9104719fc79ff31f14b4b94c627cc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621286"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="bbf0b-103">Настройка автономных EOP для доставки спама в папку нежелательной почты в гибридных средах</span><span class="sxs-lookup"><span data-stu-id="bbf0b-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbf0b-104">Этот раздел предназначен только для изолированных клиентов EOP в гибридных средах.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="bbf0b-105">Эта статья не относится к клиентам Microsoft 365 с почтовыми ящиками Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="bbf0b-106">Если вы используете автономный клиент Exchange Online Protection (EOP) в гибридной среде, вам необходимо настроить локальную организацию Exchange на распознавание и перевод фильтра нежелательной почты вердиктс EOP, поэтому правило нежелательной почты в локальном почтовом ящике может перемещать сообщения в папку "Нежелательная почта".</span><span class="sxs-lookup"><span data-stu-id="bbf0b-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="bbf0b-107">В частности, необходимо создать правила для поток обработки почты (также называемые правилами транспорта) в локальной организации Exchange с условиями поиска сообщений, которые имеют любой из следующих заголовков и значений EOP защиты от нежелательной почты, а также действия, которые задают уровень вероятности нежелательной почты (SCL) этих сообщений равным 6:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="bbf0b-108">`X-Forefront-Antispam-Report: SFV:SPM`(сообщение с пометкой "Нежелательная почта" при фильтрации спама)</span><span class="sxs-lookup"><span data-stu-id="bbf0b-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="bbf0b-109">`X-Forefront-Antispam-Report: SFV:SKS`(сообщение с пометкой "Нежелательная почта" для правил обработки почты в EOP перед фильтрацией нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="bbf0b-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="bbf0b-110">`X-Forefront-Antispam-Report: SFV:SKB`(сообщение, помеченное фильтром нежелательной почты, в связи с адресом электронной почты отправителя или доменом электронной почты из списка заблокированных отправителей или списка заблокированных доменов в EOP)</span><span class="sxs-lookup"><span data-stu-id="bbf0b-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="bbf0b-111">Дополнительные сведения об этих значениях заголовков можно узнать в статье [заголовки сообщений по защите от нежелательной почты](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="bbf0b-112">В этом разделе описывается, как создать эти правила для почтовых ящиков: центр администрирования Exchange и Командная консоль Exchange (Exchange PowerShell) в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="bbf0b-113">Вместо доставки сообщений в папку нежелательной почты локального пользователя можно настроить политики защиты от нежелательной почты в EOP для помещения нежелательных сообщений в карантин в EOP.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="bbf0b-114">Дополнительные сведения см. в разделе [Настройка политик защиты от спама в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bbf0b-115">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="bbf0b-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bbf0b-116">Прежде чем выполнять эти процедуры, необходимо назначить разрешения в локальной среде Exchange.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="bbf0b-117">В частности, необходимо назначить роль " **правила транспорта** ", которая назначается для ролей управления **организацией**, **управления соответствием требованиям**и управления **записями** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="bbf0b-118">Дополнительные сведения см в разделе [Добавление членов в группу ролей](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="bbf0b-119">Если и когда сообщение доставляется в папку нежелательной почты в локальной организации Exchange, управляется сочетанием следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="bbf0b-120">Значение параметра _SCLJunkThreshold_ в командлете [Set – OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) в командной консоли Exchange.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="bbf0b-121">Значение по умолчанию — 4, что означает, что сообщение нежелательной почты из 5 или выше должно доставлять сообщение в папку нежелательной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="bbf0b-122">Значение параметра _SCLJunkThreshold_ командлета [Set — Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) в командной консоли Exchange.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="bbf0b-123">Значение по умолчанию — пустое ($null), что означает, что используется параметр Организации.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="bbf0b-124">Подробнее о [порогах вероятности нежелательной почты Exchange (вероятности нежелательной почты)](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="bbf0b-125">Указывает, включено ли правило нежелательной почты в почтовом ящике (значение параметра _enabled_ $true в командлете [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) в командной консоли Exchange).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="bbf0b-126">Это правило нежелательной почты, которое фактически перемещает сообщение в папку "Нежелательная почта" после доставки.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="bbf0b-127">По умолчанию правило нежелательной почты включено в почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="bbf0b-128">Дополнительные сведения см. в статье [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>
  
- <span data-ttu-id="bbf0b-129">Чтобы открыть центр администрирования Exchange на сервере Exchange Server, ознакомьтесь со статьей [центр администрирования Exchange в Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="bbf0b-130">Чтобы открыть командную консоль Exchange, ознакомьтесь [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)со статьей.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-130">To open the Exchange Management Shell, see [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="bbf0b-131">Дополнительные сведения о правилах обработки почтового ящика в локальном Exchange представлены в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="bbf0b-132">Правила для почтового процесса в Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bbf0b-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="bbf0b-133">Условия и исключения правила для обработки почтового процесса (предикаты) в Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bbf0b-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="bbf0b-134">Действия правил обработки почты в Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bbf0b-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="bbf0b-135">Использование центра администрирования Exchange для создания правил для почтовых ящиков, в которых задаются нежелательные сообщения EOP</span><span class="sxs-lookup"><span data-stu-id="bbf0b-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="bbf0b-136">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="bbf0b-137">Нажмите **Добавить** ![значок](../../media/ITPro-EAC-AddIcon.png) добавить и выберите **создать новое правило** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="bbf0b-138">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="bbf0b-139">**Name**: введите уникальное описательное имя правила.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="bbf0b-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-140">For example:</span></span>

     - <span data-ttu-id="bbf0b-141">EOP SFV: SPM на SCL 6</span><span class="sxs-lookup"><span data-stu-id="bbf0b-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="bbf0b-142">EOP SFV: СКС на SCL 6</span><span class="sxs-lookup"><span data-stu-id="bbf0b-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="bbf0b-143">EOP SFV: СКБ на SCL 6</span><span class="sxs-lookup"><span data-stu-id="bbf0b-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="bbf0b-144">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-144">Click **More Options**.</span></span>

   - <span data-ttu-id="bbf0b-145">**Применять это правило, если**: выберите **заголовок** \> сообщения, **содержащий любое из этих слов**.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="bbf0b-146">В **заголовке ввод текста содержит предложение ввести слова** , которое появляется, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="bbf0b-147">Нажмите **Ввод текста**.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-147">Click **Enter text**.</span></span> <span data-ttu-id="bbf0b-148">В появившемся диалоговом окне **Укажите имя заголовка** введите **X — Forefront – защиты от спама – Report** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="bbf0b-149">Нажмите кнопку **ввод слов**.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-149">Click  **Enter words**.</span></span> <span data-ttu-id="bbf0b-150">В появившемся диалоговом окне **Укажите слова или фразы** введите одно из значений заголовка нежелательной почты EOP (**SFV: SPM**, **SFV: СКС**или **SFV: СКБ**) **Add** ![, нажмите Добавить](../../media/ITPro-EAC-AddIcon.png)значок Добавить, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="bbf0b-151">**Выполните следующие**действия: выберите **изменить свойства** \> сообщения **установите уровень вероятности нежелательной почты (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="bbf0b-152">В появившемся диалоговом окне **Указание вероятности нежелательной почты** выберите **6** (значение по умолчанию — **5**).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="bbf0b-153">Когда все будет готово, нажмите кнопку **сохранить**</span><span class="sxs-lookup"><span data-stu-id="bbf0b-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="bbf0b-154">Повторите эти действия для оставшихся EOP спама вредоносности (**SFV: SPM**, **SFV: СКС**или **SFV: СКБ**).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="bbf0b-155">Использование Командная консоль Exchange для создания правил для обработки почты, заданных для нежелательной почты EOP нежелательных сообщений</span><span class="sxs-lookup"><span data-stu-id="bbf0b-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="bbf0b-156">Используйте следующий синтаксис для создания трех правил для обработки почтового процесса:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="bbf0b-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="bbf0b-158">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="bbf0b-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bbf0b-159">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="bbf0b-159">How do you know this worked?</span></span>

<span data-ttu-id="bbf0b-160">Чтобы убедиться, что вы успешно настроили автономный EOP для доставки спама в папку нежелательной почты в гибридной среде, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="bbf0b-161">В центре администрирования Exchange перейдите к разделу **правила**обработки **почты** \> , выберите правило, а затем щелкните **изменить** ![значок](../../media/ITPro-EAC-EditIcon.png) редактирования, чтобы проверить параметры.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="bbf0b-162">В командной консоли Exchange замените \<RuleName\> на имя правила для процесса обработки почты и Рул следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="bbf0b-163">В внешней почтовой системе **, которая не сканирует исходящие сообщения для спама**, отправьте общий тест для сообщения о незапрошенной массовой рассылке (сообщение gtube) заданному получателю и убедитесь, что он доставлен в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="bbf0b-164">Сообщение GTUBE похоже на текстовый файл Европейского института исследования антивирусных программ (EICAR) для тестирования параметров вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="bbf0b-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="bbf0b-165">Чтобы отправить сообщение сообщение GTUBE, включите следующий текст в текст сообщения электронной почты в одну строку без пробелов и разрывов строк:</span><span class="sxs-lookup"><span data-stu-id="bbf0b-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
