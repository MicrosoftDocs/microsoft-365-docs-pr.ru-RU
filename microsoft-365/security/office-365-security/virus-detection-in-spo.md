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
description: Узнайте, как SharePoint Online обнаруживает вирусы в файлах, которые загружают пользователи, и не позволяет пользователям загружать или синхронизировать файлы.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ab11d4c1e2a064ad0717e6619f72a38b0cbc831
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932834"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="17bbe-103">Встроенная защита от вирусов в SharePoint Online, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17bbe-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="17bbe-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="17bbe-104">**Applies to**</span></span>
- [<span data-ttu-id="17bbe-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="17bbe-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="17bbe-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="17bbe-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="17bbe-107">Microsoft 365 используется общий механизм обнаружения вирусов для сканирования файлов, которые пользователи загружают в SharePoint Online, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="17bbe-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="17bbe-108">Эта защита включена во все подписки, которые включают SharePoint Online, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="17bbe-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17bbe-109">Встроенные антивирусные возможности помогают сдержать вирусы.</span><span class="sxs-lookup"><span data-stu-id="17bbe-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="17bbe-110">Они не предназначены как одна точка защиты от вредоносных программ для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="17bbe-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="17bbe-111">Мы рекомендуем всем клиентам исследовать и внедрять защиту от вредоносных программ на различных уровнях и применять лучшие практики для обеспечения безопасности корпоративной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="17bbe-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="17bbe-112">Дополнительные сведения о стратегиях и лучших практиках см. в ["Дорожной карте безопасности".](security-roadmap.md)</span><span class="sxs-lookup"><span data-stu-id="17bbe-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="17bbe-113">Что произойдет, если зараженный файл будет загружен в SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="17bbe-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="17bbe-114">Двигатель Microsoft 365 обнаружения вирусов работает асинхронно (независимо от загрузки файлов) SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="17bbe-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="17bbe-115">**Все файлы не сканируются автоматически.**</span><span class="sxs-lookup"><span data-stu-id="17bbe-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="17bbe-116">Heuristics определяет файлы для сканирования.</span><span class="sxs-lookup"><span data-stu-id="17bbe-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="17bbe-117">Если в файле обнаружен вирус, файл помечен.</span><span class="sxs-lookup"><span data-stu-id="17bbe-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="17bbe-118">В апреле 2018 г. мы удалили ограничение в 25 МБ для отсканированных файлов.</span><span class="sxs-lookup"><span data-stu-id="17bbe-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="17bbe-119">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="17bbe-119">Here's what happens:</span></span>

1. <span data-ttu-id="17bbe-120">Пользователь отправляет файл в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="17bbe-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="17bbe-121">SharePoint В Интернете в рамках процессов сканирования вирусов позже определяется, соответствует ли файл критериям проверки.</span><span class="sxs-lookup"><span data-stu-id="17bbe-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="17bbe-122">Если файл соответствует критериям проверки, двигатель обнаружения вирусов сканирует файл.</span><span class="sxs-lookup"><span data-stu-id="17bbe-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="17bbe-123">Если вирус найден в отсканированном файле, вирусный двигатель задает свойство в файле, указывающее, что он заражен.</span><span class="sxs-lookup"><span data-stu-id="17bbe-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="17bbe-124">Что происходит, когда пользователь пытается скачать зараженный файл через браузер?</span><span class="sxs-lookup"><span data-stu-id="17bbe-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="17bbe-125">Если файл заражен, пользователи не могут скачать его из SharePoint Online с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="17bbe-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="17bbe-126">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="17bbe-126">Here's what happens:</span></span>

1. <span data-ttu-id="17bbe-127">Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="17bbe-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="17bbe-128">Пользователю дается предупреждение об обнаружении вируса.</span><span class="sxs-lookup"><span data-stu-id="17bbe-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="17bbe-129">По умолчанию пользователю предоставляется возможность скачивать файл и пытаться очистить его с помощью антивирусного программного обеспечения на своем устройстве.</span><span class="sxs-lookup"><span data-stu-id="17bbe-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="17bbe-130">Администраторы могут использовать параметр *DisallowInfectedFileDownload* в комлете [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженные файлы даже в окне предупреждения о вирусе.</span><span class="sxs-lookup"><span data-stu-id="17bbe-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="17bbe-131">Инструкции см. в SharePoint Online PowerShell, чтобы запретить пользователям [скачивать вредоносные файлы.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)</span><span class="sxs-lookup"><span data-stu-id="17bbe-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="17bbe-132">Как только вы включаете параметр *DisallowInfectedFileDownload,* доступ к обнаруженным/заблокированным файлам полностью блокируется для пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="17bbe-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="17bbe-133">Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?</span><span class="sxs-lookup"><span data-stu-id="17bbe-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="17bbe-134">Когда вредоносный файл будет загружен в OneDrive, он будет синхронизирован с локальной машиной, прежде чем он будет помечен как вредоносный.</span><span class="sxs-lookup"><span data-stu-id="17bbe-134">When a malicious file is uploaded to OneDrive, it will be synced to the local machine before it's marked as malware.</span></span> <span data-ttu-id="17bbe-135">После того как он помечен как вредоносный, пользователь не может открыть синхронизированный файл с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="17bbe-135">After it's marked as malware, the user can't open the synced file anymore from their local machine.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="17bbe-136">Расширенные возможности с Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="17bbe-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="17bbe-137">Microsoft 365 организации, включив Microsoft Defender для [Office 365](defender-for-office-365.md) в подписку или приобретенные в качестве надстройки, могут включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams для расширенной отчетности и защиты.</span><span class="sxs-lookup"><span data-stu-id="17bbe-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](defender-for-office-365.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="17bbe-138">Дополнительные сведения см. [в Сейф вложениях SharePoint, OneDrive и Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="17bbe-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="17bbe-139">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="17bbe-139">Related Articles</span></span>

[<span data-ttu-id="17bbe-140">Защита от вредоносных программ и программ-вымогателей в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="17bbe-140">Malware and ransomware protection in Microsoft 365</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="17bbe-141">Дополнительные сведения о антивирусных приложениях в SharePoint Online, OneDrive и Microsoft Teams см. в руб. Protect [against threats](protect-against-threats.md) and [Turn on Сейф Attachments for SharePoint, OneDrive и Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="17bbe-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>
