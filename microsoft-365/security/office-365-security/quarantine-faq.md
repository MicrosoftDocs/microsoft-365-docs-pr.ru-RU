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
ms.openlocfilehash: 019f1c103ef1aaf7641072cd1259d22e83f0de4c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166931"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="97ae8-103">Quarantined messages FAQ</span><span class="sxs-lookup"><span data-stu-id="97ae8-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97ae8-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="97ae8-104">**Applies to**</span></span>
- [<span data-ttu-id="97ae8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="97ae8-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="97ae8-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="97ae8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="97ae8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97ae8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="97ae8-108">В этом разделе даны вопросы и ответы о сообщениях электронной почты, отправленных на карантин, для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организаций Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="97ae8-108">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="97ae8-109">Вопросы и ответы о защите от нежелательной почты см. в ответах на вопросы о защите от нежелательной [почты.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="97ae8-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="97ae8-110">Вопросы и ответы о защите от вредоносных программ см. в ответах на вопросы о защите от [вредоносных программ.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="97ae8-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="97ae8-111">Вопросы и ответы о защите от спуфинга см. в ответах на вопросы о защите от [спуфинга.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="97ae8-111">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="97ae8-112">Как управлять сообщениями, которые были на карантине для вредоносных программ?</span><span class="sxs-lookup"><span data-stu-id="97ae8-112">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="97ae8-113">Управлять сообщениями, которые были на карантине для вредоносных программ, могут только администраторы.</span><span class="sxs-lookup"><span data-stu-id="97ae8-113">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="97ae8-114">Дополнительные сведения см. в под управлением сообщений и файлов на карантине от [имени администратора.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="97ae8-114">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="97ae8-115">Как сделать карантин нежелательной почты?</span><span class="sxs-lookup"><span data-stu-id="97ae8-115">How do I quarantine spam?</span></span>

<span data-ttu-id="97ae8-116">По умолчанию сообщения, классифицированные как спам или массовая рассылка с помощью фильтрации нежелательной почты, доставляются в почтовый ящик пользователя и перемещаются в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="97ae8-116">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="97ae8-117">Однако вместо этого можно создать и настроить политики нежелательной почты для карантина нежелательной почты или массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="97ae8-117">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="97ae8-118">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="97ae8-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="97ae8-119">Как предоставить пользователям доступ к карантину?</span><span class="sxs-lookup"><span data-stu-id="97ae8-119">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="97ae8-120">Для доступа к собственным сообщениям в карантине у пользователя должна быть действительная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="97ae8-120">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="97ae8-121">Автономный EOP требует, чтобы пользователи были представлены в EOP как почтовые пользователи (вручную созданные или созданные с помощью синхронизации каталогов).</span><span class="sxs-lookup"><span data-stu-id="97ae8-121">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="97ae8-122">Дополнительные сведения об управлении пользователями в автономных средах EOP см. в подсети ["Управление почтовыми пользователями в EOP".](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="97ae8-122">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="97ae8-123">Какие сообщения могут быть доступны конечным пользователям в карантине?</span><span class="sxs-lookup"><span data-stu-id="97ae8-123">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="97ae8-124">Пользователи могут получать доступ к нежелательным, массовым рассылкам и (в апреле 2020 г.) фишинговыми сообщениями, в которых они являются получателями.</span><span class="sxs-lookup"><span data-stu-id="97ae8-124">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="97ae8-125">Конечные пользователи не могут получить доступ к вредоносным программам, которые были отправлены  на карантин, фишингу с высокой достоверности или сообщениям, которые были отправлены в карантин из-за действия "Доставить сообщение в карантин" в правилах потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="97ae8-125">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="97ae8-126">Дополнительные сведения о пользователях, которые имеют доступ к сообщениям на карантине, см. в подсети "Поиск и освобождение сообщений на карантине" в [качестве пользователя.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="97ae8-126">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="97ae8-127">Как долго сообщения хранятся в карантине?</span><span class="sxs-lookup"><span data-stu-id="97ae8-127">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="97ae8-128">С помощью политик защиты от нежелательной почты вы можете настроить срок, в течение который нежелательные, фишинговые и массовые сообщения электронной почты будут храниться в карантине.</span><span class="sxs-lookup"><span data-stu-id="97ae8-128">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="97ae8-129">Значение по умолчанию — 30 дней, что также является максимальным значением.</span><span class="sxs-lookup"><span data-stu-id="97ae8-129">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="97ae8-130">Дополнительные сведения см. в подстройке "Настройка политик [нежелательной почты" в EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="97ae8-130">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="97ae8-131">Для сообщений, которые были отправлены в карантин действием правила потока почты **Доставить** сообщение в почтовый карантин, сообщения хранятся в карантине в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="97ae8-131">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="97ae8-132">Этот срок настроить нельзя.</span><span class="sxs-lookup"><span data-stu-id="97ae8-132">You can't configure this duration.</span></span>

<span data-ttu-id="97ae8-133">По истечении этого периода сообщения удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="97ae8-133">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="97ae8-134">Можно ли освободить одновременно несколько сообщений, помещенных на карантин, или сообщить о них?</span><span class="sxs-lookup"><span data-stu-id="97ae8-134">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="97ae8-135">В Центре безопасности & соответствия требованиям можно выбрать и освободить до 100 сообщений одновременно.</span><span class="sxs-lookup"><span data-stu-id="97ae8-135">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="97ae8-136">Администраторы могут использовать [](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) в Exchange Online PowerShell [](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) или автономных EOP PowerShell для массового поиска и освобождения сообщений из карантина и массовой рассылки сообщений в карантине и массового сообщения о ложных срабатываниях.</span><span class="sxs-lookup"><span data-stu-id="97ae8-136">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="97ae8-137">Поддерживаются ли подстановочные знаки при поиске сообщений, помещенных на карантин?</span><span class="sxs-lookup"><span data-stu-id="97ae8-137">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="97ae8-138">Можно ли искать помещенные на карантин сообщения для определенного домена?</span><span class="sxs-lookup"><span data-stu-id="97ae8-138">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="97ae8-139">В Центре безопасности и соответствия & не поддерживаются поддеревные знаки.</span><span class="sxs-lookup"><span data-stu-id="97ae8-139">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="97ae8-140">Например, при поиске отправители необходимо указать полный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="97ae8-140">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="97ae8-141">Но вы можете использовать поддиапные знаки в Exchange Online PowerShell или в автономных EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97ae8-141">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="97ae8-142">Например, скопируйте следующий код PowerShell в Блокнот и сохраните файл как PS1 в расположении, которое легко найти (например, C:\Data\QuarantineRelease.ps1).</span><span class="sxs-lookup"><span data-stu-id="97ae8-142">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="97ae8-143">Затем после подключения к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) или [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)запустите следующую команду, чтобы запустить сценарий:</span><span class="sxs-lookup"><span data-stu-id="97ae8-143">Then, after you connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="97ae8-144">Сценарий делает следующие действия:</span><span class="sxs-lookup"><span data-stu-id="97ae8-144">The script does the following actions:</span></span>

- <span data-ttu-id="97ae8-145">Найдите неоформленные сообщения, которые были на карантине как спам от всех отправителей в домене fabrikam.</span><span class="sxs-lookup"><span data-stu-id="97ae8-145">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="97ae8-146">Максимальное число результатов — 50 000 (50 страниц с 1000 результатов).</span><span class="sxs-lookup"><span data-stu-id="97ae8-146">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="97ae8-147">Сохраните результаты в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="97ae8-147">Save the results to a CSV file.</span></span>
- <span data-ttu-id="97ae8-148">Отпустите совпадающие сообщения на карантине для всех исходных получателей.</span><span class="sxs-lookup"><span data-stu-id="97ae8-148">Release the matching quarantined messages to all original recipients.</span></span>

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

<span data-ttu-id="97ae8-149">После освобождения сообщения вы не сможете освободить его снова.</span><span class="sxs-lookup"><span data-stu-id="97ae8-149">After you release a message, you can't release it again.</span></span>
