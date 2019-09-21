---
title: Автоматическая очистка для защиты от спама и вредоносных программ
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Автоматическая очистка (ZAP) с нулевым временем (ZAP) — это функция защиты электронной почты, которая обнаруживает сообщения с нежелательной почтой или вредоносной программой, которая уже доставляется в ящики "Входящие" пользователя, а затем отрисовывает вредоносный контент. Принцип работы ZAP зависит от типа обнаруженного вредоносного содержимого.
ms.openlocfilehash: f43826614def99f8807d8777f128d5bc66f7b46a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090951"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="6bcd2-104">Автоматическая очистка для защиты от спама и вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="6bcd2-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="6bcd2-105">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="6bcd2-105">Overview</span></span>

<span data-ttu-id="6bcd2-106">Автоматическая очистка (ZAP) с нулевым временем (ZAP) — это функция защиты электронной почты, которая определяет сообщения с помощью фишинга, спама или вредоносных программ, которые уже были доставлены в папки "Входящие" пользователя, а затем отрисовывает вредоносный контент.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="6bcd2-107">Принцип работы ZAP зависит от типа обнаруженного вредоносного содержимого; почта может быть заппед из-за содержимого почты, URL-адресов или вложений.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="6bcd2-108">ZAP доступен по умолчанию для Exchange Online Protection, которая входит в состав любой подписки на Office 365, содержащей почтовые ящики Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="6bcd2-109">ZAP включен по умолчанию, но должны быть выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="6bcd2-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="6bcd2-110">Для **действия спама** задано **Перемещение сообщения в папку "Нежелательная почта**".</span><span class="sxs-lookup"><span data-stu-id="6bcd2-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="6bcd2-111">Вы также можете создать новую политику фильтрации нежелательной почты, которая применяется только к набору пользователей, если вы не хотите, чтобы все почтовые ящики были на экране ZAP.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="6bcd2-112">Пользователи сохраняли параметры нежелательной почты по умолчанию и не отключили защиту от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="6bcd2-113">(См. [изменение уровня защиты в фильтре нежелательной почты](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) для получения сведений о параметрах пользователя в Outlook).</span><span class="sxs-lookup"><span data-stu-id="6bcd2-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>
  
## <a name="how-zap-works"></a><span data-ttu-id="6bcd2-114">Как работает ZAP</span><span class="sxs-lookup"><span data-stu-id="6bcd2-114">How ZAP works</span></span>

<span data-ttu-id="6bcd2-115">Office 365 обновляет антивирусную подсистему и сигнатуры вредоносных программ в режиме реального времени ежедневно.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="6bcd2-116">Тем не менее, пользователи могут по-прежнему получать вредоносные сообщения, доставляемые в свои папки "Входящие" по ряду причин, в том числе если контент веапонизед после доставки пользователям.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="6bcd2-117">ZAP решает эту функцию, постоянно отслеживая обновления подписей спама и вредоносных программ Office 365.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="6bcd2-118">ZAP может находить и удалять ранее доставленные сообщения, которые уже находятся в папках "Входящие" пользователей.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="6bcd2-119">Команда ZAP легко работает для пользователя почтового ящика; они не уведомляются при перемещении сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="6bcd2-120">Сообщение не должно быть старше 2 дней.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="6bcd2-121">Разрешения для списков, [правил для поток обработки почты](https://go.microsoft.com/fwlink/p/?LinkId=722755) (также называемых правилами транспорта), а также правил конечного пользователя или дополнительных фильтров имеют приоритет перед ZAP.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="6bcd2-122">Вредоносная программа ZAP</span><span class="sxs-lookup"><span data-stu-id="6bcd2-122">Malware ZAP</span></span>

<span data-ttu-id="6bcd2-123">Для недавно обнаруженных вредоносных программ ZAP удаляет вложения из сообщений электронной почты, оставляя текст сообщения в почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-123">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="6bcd2-124">Вложения удаляются независимо от состояния прочтения почты.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-124">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="6bcd2-125">Вредоносный ZAP включен по умолчанию в политике вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-125">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="6bcd2-126">Вредоносную программу ZAP можно отключить с помощью параметра *запенаблед* командлета [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) в Exchange Online PowerShell или PowerShell Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-126">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="6bcd2-127">Фишинг ZAP</span><span class="sxs-lookup"><span data-stu-id="6bcd2-127">Phish ZAP</span></span>

<span data-ttu-id="6bcd2-128">Для почты, которая определена как фишинг после доставки, ZAP выполняет действия в соответствии с политикой нежелательной почты, на которую покрываем пользователь.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-128">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="6bcd2-129">Если действие фишинга в политике настроено на выполнение действий с почтой (перенаправление, удаление, карантин, перемещение в Нежелательная почта), ZAP переместит сообщение в папку "Нежелательная почта" в папке "Входящие" пользователя, независимо от состояния прочтения почты.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-129">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="6bcd2-130">Если действие антифишинга для политики не настроено на выполнение действий (добавить X-заголовок, изменить тему, без действия), то ZAP не будет предпринимать никаких действий с почтой.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-130">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="6bcd2-131">Узнайте больше о [настройке политик фильтрации нежелательной почты](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) здесь.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-131">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="6bcd2-132">Фишинг ZAP включен по умолчанию в политике нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-132">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="6bcd2-133">Вы можете отключить фишинг ZAP с помощью параметра *запенаблед* командлета [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) в Exchange Online PowerShell или PowerShell Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-133">You can disable Phish ZAP by using the *ZapEnabled* parameter on the [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="6bcd2-134">Нежелательная почта</span><span class="sxs-lookup"><span data-stu-id="6bcd2-134">Spam ZAP</span></span>

<span data-ttu-id="6bcd2-135">Для почты, которая определена как нежелательная почта после доставки, ZAP выполняет действия в соответствии с политикой нежелательной почты, на которую попадают пользователи.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-135">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="6bcd2-136">Если действие "Нежелательная почта" настроено на выполнение действий с почтой (перенаправление, удаление, карантин, перемещение в Нежелательная почта), ZAP переместит сообщение в папку "Нежелательная почта" папки "Входящие" пользователя, если сообщение не прочитано.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-136">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="6bcd2-137">Если действие "Нежелательная почта" не настроено на выполнение действий (добавить X-заголовок, изменить тему, без действия), ZAP не будет предпринимать никаких действий с почтой.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-137">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="6bcd2-138">Узнайте больше о [настройке политик фильтрации нежелательной почты](configure-your-spam-filter-policies.md) здесь.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-138">Learn more about how to [Configure your spam filter policies](configure-your-spam-filter-policies.md) here.</span></span>

<span data-ttu-id="6bcd2-139">В политике нежелательной почты по умолчанию включена Нежелательная почта.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-139">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="6bcd2-140">Отключить нежелательную почту можно с помощью параметра *запенаблед* командлета [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) в Exchange Online PowerShell или PowerShell Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-140">You can disable Spam ZAP by using the *ZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="6bcd2-141">Параметр *запенаблед* командлета **Set-HostedContentFilterPolicy** отключает или включает как фишинг ZAP, так и ZAP нежелательной почты для политики.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-141">The *ZapEnabled* parameter on the **Set-HostedContentFilterPolicy** cmdlet disables or enables both Phish ZAP and Spam ZAP for the policy.</span></span> <span data-ttu-id="6bcd2-142">Вы не можете независимо включать и отключать мошеннические и нежелательную почту ZAP в одной политике.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-142">You can't independently enable or disable Phish ZAP and Spam ZAP within the same policy.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="6bcd2-143">Как убедиться, что сообщение было перемещено из ZAP</span><span class="sxs-lookup"><span data-stu-id="6bcd2-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="6bcd2-144">Чтобы определить, переместилось ли сообщение ZAP, можно использовать [отчет о состоянии защиты от угроз](../../compliance/view-email-security-reports.md#threat-protection-status-report) или [Обозреватель угроз (а также обнаружение в режиме реального времени)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="6bcd2-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](../../compliance/view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="6bcd2-145">Отключение ZAP</span><span class="sxs-lookup"><span data-stu-id="6bcd2-145">Disable ZAP</span></span>

<span data-ttu-id="6bcd2-146">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="6bcd2-146">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="6bcd2-147">Чтобы подключиться к Exchange Online Protection PowerShell, ознакомьтесь [со статьей подключение к PowerShell для Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290).</span><span class="sxs-lookup"><span data-stu-id="6bcd2-147">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="6bcd2-148">Отключение вредоносных программ ZAP \* \*</span><span class="sxs-lookup"><span data-stu-id="6bcd2-148">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="6bcd2-149">В этом примере показано, как отключить ZAP в политике фильтрации вредоносных программ под названием "Test".</span><span class="sxs-lookup"><span data-stu-id="6bcd2-149">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="6bcd2-150">Подробные сведения о синтаксисе и параметрах см. в статье [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="6bcd2-150">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="6bcd2-151">Отключение ZAP-фишинга и нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="6bcd2-151">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="6bcd2-152">В этом примере отключается фишинг ZAP и Нежелательная почта ZAP в политике фильтрации содержимого под названием "Test".</span><span class="sxs-lookup"><span data-stu-id="6bcd2-152">This example disables Phish ZAP and Spam ZAP in the content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="6bcd2-153">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span><span class="sxs-lookup"><span data-stu-id="6bcd2-153">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="6bcd2-154">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="6bcd2-154">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="6bcd2-155">Что произойдет при перемещении законного сообщения в папку "Нежелательная почта"?</span><span class="sxs-lookup"><span data-stu-id="6bcd2-155">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="6bcd2-156">Для [ложных срабатываний](../../compliance/prevent-email-from-being-marked-as-spam.md)необходимо следовать обычным процессам отчетов.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-156">You should follow the normal reporting process for [false-positives](../../compliance/prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="6bcd2-157">Единственная причина, по которой сообщение было бы перемещено из папки "Входящие" в папку нежелательной почты, будет вызвано тем, что эта служба определила, что сообщение является спамом или вредоносным.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-157">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="6bcd2-158">Что делать, если вместо папки нежелательной почты используется карантин Office 365?</span><span class="sxs-lookup"><span data-stu-id="6bcd2-158">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="6bcd2-159">ZAP не перемещает сообщения в карантин из папки "Входящие" в данный момент.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-159">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="6bcd2-160">Что делать, если вы создали правило для обработки почтового процесса (Block/Allow Rule)?</span><span class="sxs-lookup"><span data-stu-id="6bcd2-160">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="6bcd2-161">Правила, созданные администраторами (правила для почтового процесса) или блокировать и разрешать правила, имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-161">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="6bcd2-162">Такие сообщения исключаются из критериев функции, поэтому потоки обработки почты будут следовать действию правила (Block/Allow Rule).</span><span class="sxs-lookup"><span data-stu-id="6bcd2-162">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="6bcd2-163">Что делать, если сообщение перемещено в другую папку (например, правило для папки "Входящие")?</span><span class="sxs-lookup"><span data-stu-id="6bcd2-163">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="6bcd2-164">ZAP все еще работает в этом случае, если сообщение не было удалено или не является нежелательным.</span><span class="sxs-lookup"><span data-stu-id="6bcd2-164">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6bcd2-165">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6bcd2-165">Related Topics</span></span>

[<span data-ttu-id="6bcd2-166">Защита от спама электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="6bcd2-166">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="6bcd2-167">Блокировка спама с помощью фильтра нежелательной почты Office 365 для предотвращения ошибочных результатов</span><span class="sxs-lookup"><span data-stu-id="6bcd2-167">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
