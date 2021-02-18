---
title: Встроенная защита от вирусов в SharePoint Online, OneDrive и Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Узнайте, как SharePoint Online обнаруживает вирусы в файлах, которые пользователи загружают, и не позволяет пользователям скачивать или синхронизировать файлы.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286505"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="85e97-103">Встроенная защита от вирусов в SharePoint Online, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85e97-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="85e97-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="85e97-104">**Applies to**</span></span>
- [<span data-ttu-id="85e97-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="85e97-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="85e97-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="85e97-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="85e97-107">Microsoft 365 использует распространенный механизм обнаружения вирусов для сканирования файлов, которые пользователи загружают в SharePoint Online, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85e97-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="85e97-108">Эта защита включена во все подписки, в том числе SharePoint Online, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85e97-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85e97-109">Встроенные антивирусные возможности помогают сдержать вирусы.</span><span class="sxs-lookup"><span data-stu-id="85e97-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="85e97-110">Они не предназначены в качестве единой точки защиты от вредоносных программ в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="85e97-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="85e97-111">Мы рекомендуем всем клиентам изучить и внедрить защиту от вредоносных программ на различных уровнях и применить лучшие методики защиты корпоративной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="85e97-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="85e97-112">Дополнительные сведения о стратегиях и советах см. в [стратегии безопасности.](security-roadmap.md)</span><span class="sxs-lookup"><span data-stu-id="85e97-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="85e97-113">Что происходит при отправке зараженного файла в SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="85e97-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="85e97-114">Механизм обнаружения вирусов Microsoft 365 работает в SharePoint Online асинхронно.</span><span class="sxs-lookup"><span data-stu-id="85e97-114">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="85e97-115">**Все файлы не проверяются автоматически при отправке.**</span><span class="sxs-lookup"><span data-stu-id="85e97-115">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="85e97-116">Сканируйте файлы, которые необходимо сканировать, с его целью сканироваться с 1 по 100 000.</span><span class="sxs-lookup"><span data-stu-id="85e97-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="85e97-117">Если файл содержит вирус, он помечается, поэтому его нельзя загрузить снова.</span><span class="sxs-lookup"><span data-stu-id="85e97-117">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="85e97-118">В апреле 2018 г. мы удалили ограничение в 25 МБ для отсканированных файлов.</span><span class="sxs-lookup"><span data-stu-id="85e97-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="85e97-119">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="85e97-119">Here's what happens:</span></span>

1. <span data-ttu-id="85e97-120">Пользователь отправляет файл в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="85e97-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="85e97-121">SharePoint Online определяет, соответствует ли файл критериям проверки.</span><span class="sxs-lookup"><span data-stu-id="85e97-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="85e97-122">Модуль поиска вирусов проверяет файл.</span><span class="sxs-lookup"><span data-stu-id="85e97-122">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="85e97-123">Если вирус найден, антивирусная система задает свойство файла, указывающее на то, что он заражен.</span><span class="sxs-lookup"><span data-stu-id="85e97-123">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="85e97-124">Что происходит, когда пользователь пытается скачать зараженный файл через браузер?</span><span class="sxs-lookup"><span data-stu-id="85e97-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="85e97-125">Если файл заражен, пользователи не смогут скачать его из SharePoint Online с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="85e97-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="85e97-126">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="85e97-126">Here's what happens:</span></span>

1. <span data-ttu-id="85e97-127">Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="85e97-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="85e97-128">Пользователю выдается предупреждение об обнаружении вируса.</span><span class="sxs-lookup"><span data-stu-id="85e97-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="85e97-129">По умолчанию пользователю предоставляется возможность скачать файл и попытаться очистить его с помощью антивирусного программного обеспечения на своем устройстве.</span><span class="sxs-lookup"><span data-stu-id="85e97-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="85e97-130">Администраторы могут использовать параметр *DisallowInfectedFileDownload* в cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженные файлы даже в окне предупреждения антивируса.</span><span class="sxs-lookup"><span data-stu-id="85e97-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="85e97-131">Инструкции см. в [sharePoint Online PowerShell, чтобы](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)запретить пользователям скачивать вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="85e97-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="85e97-132">Как только вы включаете параметр *DisallowInfectedFileDownload,* доступ к обнаруженным или заблокированным файлам полностью блокируется для пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="85e97-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="85e97-133">Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?</span><span class="sxs-lookup"><span data-stu-id="85e97-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="85e97-134">Клиенты синхронизации OneDrive не будут скачивать файлы, содержащие вирусы.</span><span class="sxs-lookup"><span data-stu-id="85e97-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="85e97-135">Клиент выведет уведомление о том, что файл невозможно синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="85e97-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="85e97-136">Расширенные возможности с помощью Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="85e97-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="85e97-137">Организации Microsoft 365 с Microsoft [Defender для Office 365,](office-365-atp.md) включенными в подписку или приобретенными в качестве надстройки, могут включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams для улучшенной отчетности и защиты.</span><span class="sxs-lookup"><span data-stu-id="85e97-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="85e97-138">Дополнительные сведения см. в записях ["Безопасные вложения" для SharePoint, OneDrive и Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="85e97-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="85e97-139">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="85e97-139">Related Articles</span></span>

[<span data-ttu-id="85e97-140">Защита от вредоносных программ и программ-вымогателей в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85e97-140">Malware and ransomware protection in Microsoft 365</span></span>](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="85e97-141">Дополнительные сведения о антивирусной защите в SharePoint Online, [](protect-against-threats.md) OneDrive и Microsoft Teams см. в подзащите от угроз и включите безопасные вложения для [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85e97-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
