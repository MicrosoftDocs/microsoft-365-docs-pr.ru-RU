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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут просматривать часто задаваемые вопросы и ответы о сообщениях на карантине в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: abd2304e83d2814cab55d13312535bd94308d8be
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032605"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="6a305-103">Quarantined messages FAQ</span><span class="sxs-lookup"><span data-stu-id="6a305-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6a305-104">В этом разделе даны вопросы и ответы о сообщениях электронной почты, отправленных на карантин, для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организаций Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6a305-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="6a305-105">Вопросы и ответы о защите от нежелательной почты см. в ответах на вопросы о защите от нежелательной [почты.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="6a305-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="6a305-106">Вопросы и ответы о защите от вредоносных программ см. в ответах на вопросы о защите от [вредоносных программ.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="6a305-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="6a305-107">Вопросы и ответы о защите от спуфинга см. в ответах на вопросы о защите от [спуфинга.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="6a305-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="6a305-108">Как управлять сообщениями, которые были на карантине для вредоносных программ?</span><span class="sxs-lookup"><span data-stu-id="6a305-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="6a305-109">Управлять сообщениями, которые были на карантине для вредоносных программ, могут только администраторы.</span><span class="sxs-lookup"><span data-stu-id="6a305-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="6a305-110">Дополнительные сведения см. в под управлением сообщений и файлов на карантине от [имени администратора.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="6a305-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="6a305-111">Как сделать карантин нежелательной почты?</span><span class="sxs-lookup"><span data-stu-id="6a305-111">How do I quarantine spam?</span></span>

<span data-ttu-id="6a305-112">По умолчанию сообщения, классифицированные как спам или массовая рассылка с помощью фильтрации нежелательной почты, доставляются в почтовый ящик пользователя и перемещаются в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="6a305-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="6a305-113">Однако вместо этого можно создать и настроить политики нежелательной почты для карантина нежелательной почты или массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6a305-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="6a305-114">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6a305-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="6a305-115">Как предоставить пользователям доступ к карантину?</span><span class="sxs-lookup"><span data-stu-id="6a305-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="6a305-116">Для доступа к собственным сообщениям в карантине у пользователя должна быть действительная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="6a305-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="6a305-117">Автономный EOP требует, чтобы пользователи были представлены в EOP как почтовые пользователи (вручную созданные или созданные с помощью синхронизации каталогов).</span><span class="sxs-lookup"><span data-stu-id="6a305-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="6a305-118">Дополнительные сведения об управлении пользователями в автономных средах EOP см. в подсети ["Управление почтовыми пользователями в EOP".](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="6a305-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="6a305-119">Какие сообщения могут быть доступны конечным пользователям в карантине?</span><span class="sxs-lookup"><span data-stu-id="6a305-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="6a305-120">Пользователи могут получать доступ к нежелательным, массовым рассылкам и (в апреле 2020 г.) фишинговыми сообщениями, в которых они являются получателями.</span><span class="sxs-lookup"><span data-stu-id="6a305-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="6a305-121">Конечные пользователи не могут получить доступ к вредоносным программам, которые были отправлены  на карантин, фишингу с высокой достоверности или сообщениям, которые были отправлены в карантин из-за действия "Доставить сообщение в карантин" в правилах потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="6a305-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="6a305-122">Дополнительные сведения о пользователях, которые имеют доступ к сообщениям на карантине, см. в подсети "Поиск и освобождение сообщений на карантине" в [качестве пользователя.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="6a305-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="6a305-123">Как долго сообщения хранятся в карантине?</span><span class="sxs-lookup"><span data-stu-id="6a305-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="6a305-124">С помощью политик защиты от нежелательной почты вы можете настроить срок, в течение который нежелательные, фишинговые и массовые сообщения электронной почты будут храниться в карантине.</span><span class="sxs-lookup"><span data-stu-id="6a305-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="6a305-125">Значение по умолчанию — 30 дней, что также является максимальным значением.</span><span class="sxs-lookup"><span data-stu-id="6a305-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="6a305-126">Дополнительные сведения см. в подстроке "Настройка политик [нежелательной почты" в EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6a305-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="6a305-127">Для сообщений, которые были отправлены в карантин действием правила потока почты **Доставить** сообщение в почтовый карантин, сообщения хранятся в карантине в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="6a305-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="6a305-128">Этот срок настроить нельзя.</span><span class="sxs-lookup"><span data-stu-id="6a305-128">You can't configure this duration.</span></span>

<span data-ttu-id="6a305-129">По истечении этого периода сообщения удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="6a305-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="6a305-130">Можно ли освободить одновременно несколько сообщений, помещенных на карантин, или сообщить о них?</span><span class="sxs-lookup"><span data-stu-id="6a305-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="6a305-131">В Центре & соответствия требованиям можно выбрать и освободить до 100 сообщений одновременно.</span><span class="sxs-lookup"><span data-stu-id="6a305-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="6a305-132">Администраторы могут использовать [](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) в Exchange Online PowerShell [](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) или автономных EOP PowerShell для массового поиска и освобождения сообщений из карантина и массовой рассылки сообщений в карантине и массового сообщения о ложных срабатываниях.</span><span class="sxs-lookup"><span data-stu-id="6a305-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="6a305-133">Поддерживаются ли подстановочные знаки при поиске сообщений, помещенных на карантин?</span><span class="sxs-lookup"><span data-stu-id="6a305-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="6a305-134">Можно ли искать помещенные на карантин сообщения для определенного домена?</span><span class="sxs-lookup"><span data-stu-id="6a305-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="6a305-135">В Центре безопасности и соответствия & не поддерживаются поддеревные знаки.</span><span class="sxs-lookup"><span data-stu-id="6a305-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="6a305-136">Например, при поиске отправители необходимо указать полный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6a305-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="6a305-137">Но вы можете использовать поддиапные знаки в Exchange Online PowerShell или в автономных EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a305-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="6a305-138">Например, скопируйте следующий код PowerShell в Блокнот и сохраните файл как PS1 в расположении, которое легко найти (например, C:\Data\QuarantineRelease.ps1).</span><span class="sxs-lookup"><span data-stu-id="6a305-138">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="6a305-139">Затем после подключения к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) или [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)запустите следующую команду, чтобы запустить сценарий:</span><span class="sxs-lookup"><span data-stu-id="6a305-139">Then, after you connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="6a305-140">Сценарий делает следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6a305-140">The script does the following actions:</span></span>

- <span data-ttu-id="6a305-141">Найдите неоформленные сообщения, которые были на карантине как спам от всех отправителей в домене fabrikam.</span><span class="sxs-lookup"><span data-stu-id="6a305-141">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="6a305-142">Максимальное число результатов — 50 000 (50 страниц с 1000 результатов).</span><span class="sxs-lookup"><span data-stu-id="6a305-142">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="6a305-143">Сохраните результаты в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="6a305-143">Save the results to a CSV file.</span></span>
- <span data-ttu-id="6a305-144">Отпустите совпадающие сообщения на карантине для всех исходных получателей.</span><span class="sxs-lookup"><span data-stu-id="6a305-144">Release the matching quarantined messages to all original recipients.</span></span>

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

<span data-ttu-id="6a305-145">После освобождения сообщения вы не сможете освободить его снова.</span><span class="sxs-lookup"><span data-stu-id="6a305-145">After you release a message, you can't release it again.</span></span>
