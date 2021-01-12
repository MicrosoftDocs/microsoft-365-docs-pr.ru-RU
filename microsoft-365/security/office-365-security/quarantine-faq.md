---
title: Quarantined messages FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут просматривать часто задаваемые вопросы и ответы о сообщениях на карантине в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddb5847706aef3d2c3b8ea8cd9a96fd65a9b3d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794416"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="cfdd1-103">Quarantined messages FAQ</span><span class="sxs-lookup"><span data-stu-id="cfdd1-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cfdd1-104">В этом разделе даны вопросы и ответы о сообщениях электронной почты, отправленных на карантин, для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организаций Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="cfdd1-105">Вопросы и ответы о защите от нежелательной почты см. в вопросах о защите от нежелательной [почты.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="cfdd1-106">Вопросы и ответы о защите от вредоносных программ см. в вопросах о защите от [вредоносных программ.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="cfdd1-107">Вопросы и ответы о защите от спуфинга см. в ответах на вопросы о защите от [спуфинга.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="cfdd1-108">Как управлять сообщениями, которые были на карантине для вредоносных программ?</span><span class="sxs-lookup"><span data-stu-id="cfdd1-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="cfdd1-109">Управлять сообщениями, которые были на карантине для вредоносных программ, могут только администраторы.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="cfdd1-110">Дополнительные сведения см. в под управлением сообщений и файлов на карантине от [имени администратора.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="cfdd1-111">Как сделать карантин нежелательной почты?</span><span class="sxs-lookup"><span data-stu-id="cfdd1-111">How do I quarantine spam?</span></span>

<span data-ttu-id="cfdd1-112">По умолчанию сообщения, классифицированные как спам или массовая рассылка с помощью фильтрации нежелательной почты, доставляются в почтовый ящик пользователя и перемещаются в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="cfdd1-113">Однако вместо этого можно создать и настроить политики нежелательной почты для карантина нежелательной почты или массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="cfdd1-114">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="cfdd1-115">Как предоставить пользователям доступ к карантину?</span><span class="sxs-lookup"><span data-stu-id="cfdd1-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="cfdd1-116">Для доступа к собственным сообщениям в карантине у пользователя должна быть действительная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="cfdd1-117">Автономный EOP требует, чтобы пользователи были представлены в EOP как почтовые пользователи (вручную созданные или созданные с помощью синхронизации каталогов).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="cfdd1-118">Дополнительные сведения об управлении пользователями в автономных средах EOP см. в подсети ["Управление почтовыми пользователями в EOP".](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="cfdd1-119">Какие сообщения могут быть доступны конечным пользователям в карантине?</span><span class="sxs-lookup"><span data-stu-id="cfdd1-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="cfdd1-120">Пользователи могут получать доступ к нежелательным, массовым рассылкам и (в апреле 2020 г.) фишинговыми сообщениями, в которых они являются получателями.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="cfdd1-121">Конечные пользователи не могут получить доступ к вредоносным программам, отправленным на карантин, фишингу с высокой достоверности или сообщениям, которые были отправлены в карантин из-за действия "Доставка сообщения на карантин" в правилах потока почты (также известных как правила транспорта). </span><span class="sxs-lookup"><span data-stu-id="cfdd1-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="cfdd1-122">Дополнительные сведения о пользователях, которые имеют доступ к сообщениям на карантине, см. в подсети "Поиск и освобождение сообщений на карантине" в [качестве пользователя.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="cfdd1-123">Как долго сообщения хранятся в карантине?</span><span class="sxs-lookup"><span data-stu-id="cfdd1-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="cfdd1-124">С помощью политик защиты от нежелательной почты вы можете настроить срок, в течение который нежелательные, фишинговые и массовые сообщения электронной почты будут храниться в карантине.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="cfdd1-125">Значение по умолчанию — 30 дней, что также является максимальным значением.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="cfdd1-126">Дополнительные сведения см. в подстроке "Настройка политик [нежелательной почты" в EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cfdd1-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="cfdd1-127">Для сообщений, которые были отправлены в карантин действием правила потока почты **Доставить** сообщение в почтовый карантин, сообщения хранятся в карантине в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="cfdd1-128">Этот срок настроить нельзя.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-128">You can't configure this duration.</span></span>

<span data-ttu-id="cfdd1-129">По истечении этого периода сообщения удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="cfdd1-130">Можно ли освободить одновременно несколько сообщений, помещенных на карантин, или сообщить о них?</span><span class="sxs-lookup"><span data-stu-id="cfdd1-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="cfdd1-131">В Центре безопасности & соответствия требованиям можно выбрать и освободить до 100 сообщений одновременно.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="cfdd1-132">Администраторы могут использовать [](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) в Exchange Online PowerShell [](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) или автономных EOP PowerShell для массового поиска и освобождения сообщений из карантина и массовой рассылки сообщений в карантине и массового сообщения о ложных срабатываниях.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="cfdd1-133">Поддерживаются ли подстановочные знаки при поиске сообщений, помещенных на карантин?</span><span class="sxs-lookup"><span data-stu-id="cfdd1-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="cfdd1-134">Можно ли искать помещенные на карантин сообщения для определенного домена?</span><span class="sxs-lookup"><span data-stu-id="cfdd1-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="cfdd1-135">Wildcards aren't supported in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="cfdd1-136">Например, при поиске отправители необходимо указать полный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="cfdd1-137">Но вы можете использовать поддиапные знаки в Exchange Online PowerShell или в автономных EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="cfdd1-138">Например, чтобы найти нежелательные сообщения на карантине от всех отправителей в домене, contoso.com:</span><span class="sxs-lookup"><span data-stu-id="cfdd1-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="cfdd1-139">Затем запустите следующую команду, чтобы освободить эти сообщения для всех исходных получателей:</span><span class="sxs-lookup"><span data-stu-id="cfdd1-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="cfdd1-140">После освобождения сообщения вы не сможете освободить его снова.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-140">After you release a message, you can't release it again.</span></span>
