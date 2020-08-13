---
title: Обнаружение вирусов в SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Сведения о том, как SharePoint Online обнаруживает вирусы в файлах, отправляемых пользователями, и запрещает пользователям загружать или синхронизировать эти файлы.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0e58fa8dc8b30c5bc6ff5db1508d8b7f9189b73a
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653513"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="8fa7d-103">Обнаружение вирусов в SharePoint Online, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8fa7d-103">Virus detection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="8fa7d-104">Microsoft 365 поможет защитить среду от вредоносных программ, обнаруживая вирусы в файлах, отправляемых пользователями в SharePoint Online, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="8fa7d-105">После отправки файлы могут быть проверены на наличие вирусов.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="8fa7d-106">Если вирус заражен, для него задается соответствующее свойство, которое не позволяет пользователям скачать его из браузера или синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fa7d-107">Эти возможности в SharePoint Online позволяют включать вирусы.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="8fa7d-108">Они не предназначены для защиты от вредоносных программ в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="8fa7d-109">Мы рекомендуем всем клиентам оценивать и внедрять защиту от вредоносных программ на различных уровнях и применять рекомендации по обеспечению безопасности корпоративной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="8fa7d-110">Более подробную информацию о стратегиях и рекомендациях можно узнать в статье [Security Security](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="8fa7d-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="8fa7d-111">Что происходит при отправке зараженного файла в SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="8fa7d-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="8fa7d-112">Microsoft 365 использует общий механизм обнаружения вирусов.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="8fa7d-113">Ядро работает асинхронно в SharePoint Online и сканирует некоторые файлы после их отправки.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="8fa7d-114">Эвристические алгоритмы используются для определения сканируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="8fa7d-115">Если выясняется, что файл содержит вирус, он помечается, чтобы его нельзя было снова скачать.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="8fa7d-116">В апреле 2018 был удален лимит в 25 МБ для сканированных файлов.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="8fa7d-117">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-117">Here's what happens:</span></span>

1. <span data-ttu-id="8fa7d-118">Пользователь отправляет файл в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="8fa7d-119">SharePoint Online определяет, соответствует ли файл условиям проверки.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="8fa7d-120">Модуль поиска вирусов проверяет файл.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="8fa7d-121">Если обнаружен вирус, антивирусная программа задает для файла свойство, указывающее на то, что оно заражено.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="8fa7d-122">Что происходит, когда пользователь пытается скачать зараженный файл через браузер?</span><span class="sxs-lookup"><span data-stu-id="8fa7d-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="8fa7d-123">Если файл заражен, пользователи не могут скачать файл из SharePoint Online с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="8fa7d-124">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-124">Here's what happens:</span></span>

1. <span data-ttu-id="8fa7d-125">Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="8fa7d-126">Пользователю выдается предупреждение о том, что вирус обнаружен.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="8fa7d-127">Пользователю предоставляется возможность загрузить файл и попытаться очистить его с помощью собственного антивирусного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
>
> <span data-ttu-id="8fa7d-128">Вы можете использовать параметр *дисалловинфектедфиледовнлоад* командлета [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженный файл даже в окне предупреждения о антивирусной борьбе.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>
>
> <span data-ttu-id="8fa7d-129">Кроме того, следует учитывать, что при включении параметра *дисалловинфектедфиледовнлоад* доступ к обнаруженным и заблокированным файлам полностью блокируется для пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-129">Also keep in mind, that as soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completly blocked for users and administrators.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="8fa7d-130">Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?</span><span class="sxs-lookup"><span data-stu-id="8fa7d-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="8fa7d-p105">Неважно, какой клиент вы используете  новый клиент синхронизации OneDrive (OneDrive.exe) или старый клиент синхронизации OneDrive для бизнеса(Groove.exe),  если файл содержит вирус, он не будет скачан. Клиент выведет уведомление о том, что файл невозможно синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-p105">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-atp"></a><span data-ttu-id="8fa7d-133">Расширенные возможности Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8fa7d-133">Extended capabilities with Office 365 ATP</span></span>

<span data-ttu-id="8fa7d-134">Пользователи, которым разрешено Office 365 ATP для SharePoint, OneDrive и Microsoft Teams [включают ATP для SharePoint, onedrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) , могут использовать центр безопасности & соответствия требованиям для управления файлами на карантине для обнаружения AV и ATP.</span><span class="sxs-lookup"><span data-stu-id="8fa7d-134">Customers who enabled Office 365 ATP for Sharepoint, OneDrive, and Microsoft Teams [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) are able to use the Security & Compliance Center to manage quarantined files for AV and ATP detections.</span></span> <span data-ttu-id="8fa7d-135">[Только ATP: используйте центр безопасности & соответствия требованиям для управления файлами, помещенными в карантин](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="8fa7d-135">[ATP Only: Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="more-information"></a><span data-ttu-id="8fa7d-136">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="8fa7d-136">More information</span></span>

<span data-ttu-id="8fa7d-137">Для получения дополнительных сведений о настройке антивирусной программы SharePoint Online обратитесь к разделу [Защита от угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) и [Включение ATP для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="8fa7d-137">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


