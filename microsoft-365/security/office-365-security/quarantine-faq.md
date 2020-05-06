---
title: Вопросы и ответы, посвященные карантину
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Часто задаваемые вопросы о карантине для почтовых ящиков Office 365 в Exchange Online или отдельном EOP без почтовых ящиков Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c5d7f426701ebc9a546a86a4fccbd7015fc0e49
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033858"
---
# <a name="quarantine-faq"></a><span data-ttu-id="bf466-103">Вопросы и ответы, посвященные карантину</span><span class="sxs-lookup"><span data-stu-id="bf466-103">Quarantine FAQ</span></span>

<span data-ttu-id="bf466-104">В этом разделе приведены часто задаваемые вопросы и ответы о карантине для пользователей Microsoft 365 с почтовыми ящиками в Exchange Online или отдельных клиентах Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bf466-104">This topic provides frequently asked questions and answers about quarantine for Microsoft 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="bf466-105">Вопрос: как управлять сообщениями, помещенными в карантин для вредоносных программ?</span><span class="sxs-lookup"><span data-stu-id="bf466-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="bf466-106">Только администраторы могут управлять сообщениями, помещенными в карантин для вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="bf466-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="bf466-107">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="bf466-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="bf466-108">В. как помещать спам?</span><span class="sxs-lookup"><span data-stu-id="bf466-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="bf466-109">О.</span><span class="sxs-lookup"><span data-stu-id="bf466-109">A.</span></span> <span data-ttu-id="bf466-110">По умолчанию при фильтрации нежелательной почты сообщения, которые классифицируются как спам, отправляются в почтовый ящик пользователя и перемещаются в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="bf466-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="bf466-111">Но вы можете создавать и настраивать политики защиты от нежелательной почты для помещения нежелательной почты в карантин или массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bf466-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="bf466-112">Дополнительные сведения см. в разделе [Настройка политик защиты от спама в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bf466-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="bf466-113">Вопрос: как предоставить пользователям доступ к карантину?</span><span class="sxs-lookup"><span data-stu-id="bf466-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="bf466-114">О.</span><span class="sxs-lookup"><span data-stu-id="bf466-114">A.</span></span> <span data-ttu-id="bf466-115">Пользователь должен иметь действительную учетную запись для доступа к своим сообщениям в карантине.</span><span class="sxs-lookup"><span data-stu-id="bf466-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="bf466-116">Для автономных EOP необходимо, чтобы пользователи были представлены как почтовые пользователи в EOP (создан или создан вручную через синхронизацию службы каталогов).</span><span class="sxs-lookup"><span data-stu-id="bf466-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="bf466-117">Дополнительные сведения об управлении пользователями в автономных средах EOP можно найти [в статье Управление почтовыми пользователями в EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="bf466-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="bf466-118">Вопрос: какие сообщения могут иметь конечные пользователи в карантине?</span><span class="sxs-lookup"><span data-stu-id="bf466-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="bf466-119">О.</span><span class="sxs-lookup"><span data-stu-id="bf466-119">A.</span></span> <span data-ttu-id="bf466-120">Пользователи могут получать доступ к спаму, рассылке по электронной почте и (на Апрель, 2020) фишинговых сообщениях, в которых они являются получателями.</span><span class="sxs-lookup"><span data-stu-id="bf466-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="bf466-121">Конечные пользователи не могут получить доступ к вредоносным вредоносным программам, высокоточным фишингом или сообщениям, помещенным в карантин из-за **доставки сообщения в размещенное действие карантина** в правилах обработки почтового ящика (также называемых правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="bf466-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="bf466-122">Дополнительные сведения о пользователях, обращающихся к сообщениям в карантине, приведены [в статье Поиск и освобождение сообщений, помещенных в карантин, в качестве пользователя в Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bf466-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="bf466-123">Вопрос: сколько времени сообщения хранятся в карантине?</span><span class="sxs-lookup"><span data-stu-id="bf466-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="bf466-124">О.</span><span class="sxs-lookup"><span data-stu-id="bf466-124">A.</span></span> <span data-ttu-id="bf466-125">Вы настраиваете время хранения нежелательной почты, фишинга и массовых сообщений электронной почты в карантине с помощью политик защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="bf466-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="bf466-126">Значение по умолчанию — 30 дней, которое также является максимальным.</span><span class="sxs-lookup"><span data-stu-id="bf466-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="bf466-127">Дополнительные сведения см в статье [Настройка политик защиты от нежелательной почты в Office 365](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bf466-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="bf466-128">Для сообщений, помещенных в карантин с помощью правила обработки почтового ящика **Доставка сообщения в размещенный карантин**, сообщения хранятся в карантине в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="bf466-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="bf466-129">Вы не можете настроить эту длительность.</span><span class="sxs-lookup"><span data-stu-id="bf466-129">You can't configure this duration.</span></span>

<span data-ttu-id="bf466-130">По истечении периода времени сообщения удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="bf466-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="bf466-131">В: можно ли отпустить или отправить отчет за несколько сообщений, помещенных в карантин?</span><span class="sxs-lookup"><span data-stu-id="bf466-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="bf466-132">О.</span><span class="sxs-lookup"><span data-stu-id="bf466-132">A.</span></span> <span data-ttu-id="bf466-133">В центре безопасности & соответствия требованиям можно выделять и выпустить до 100 сообщений за раз.</span><span class="sxs-lookup"><span data-stu-id="bf466-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="bf466-134">Администраторы могут использовать командлеты [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) и [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) в Exchange Online PowerShell или PowerShell для автономной защиты Exchange Online, чтобы находить и освобождать сообщения, помещенные в карантин, в пакетном режиме, а также сообщать о ложных срабатываниях в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="bf466-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="bf466-135">В: подстановочные знаки, поддерживаемые при поиске сообщений, помещенных в карантин?</span><span class="sxs-lookup"><span data-stu-id="bf466-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="bf466-136">Можно ли искать помещенные на карантин сообщения для определенного домена?</span><span class="sxs-lookup"><span data-stu-id="bf466-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="bf466-137">О.</span><span class="sxs-lookup"><span data-stu-id="bf466-137">A.</span></span> <span data-ttu-id="bf466-138">Подстановочные знаки не поддерживаются в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bf466-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="bf466-139">Например, при поиске отправителя необходимо указать полный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bf466-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="bf466-140">Однако можно использовать подстановочные знаки в Exchange Online PowerShell или PowerShell Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="bf466-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="bf466-141">Например, выполните следующую команду, чтобы найти сообщения, помещенные в карантин нежелательной почты со всех отправителей в домене contoso.com:</span><span class="sxs-lookup"><span data-stu-id="bf466-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="bf466-142">Затем выполните следующую команду, чтобы освободить сообщения всем исходным получателям:</span><span class="sxs-lookup"><span data-stu-id="bf466-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="bf466-143">После освобождения сообщения его невозможно будет снова освободить.</span><span class="sxs-lookup"><span data-stu-id="bf466-143">After you release a message, you can't release it again.</span></span>
