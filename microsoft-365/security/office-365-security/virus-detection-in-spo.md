---
title: Обнаружение вирусов в SharePoint Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
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
description: Office 365 помогает защитить рабочую среду от вредоносных программ, обнаруживая вирусы в файлах, которые пользователи отправляют в SharePoint Online. Файлы проверяются на наличие вирусов после отправки. Если вирус заражен, для него задается соответствующее свойство, которое не позволяет пользователям скачать его из браузера или синхронизировать.
ms.openlocfilehash: fdf8fb61ab6923c20401bc8bf2a482ab7515568a
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793693"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="abe53-105">Обнаружение вирусов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="abe53-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="abe53-106">Office 365 помогает защитить рабочую среду от вредоносных программ, обнаруживая вирусы в файлах, которые пользователи отправляют в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="abe53-106">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="abe53-107">После отправки файлы могут быть проверены на наличие вирусов.</span><span class="sxs-lookup"><span data-stu-id="abe53-107">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="abe53-108">Если вирус заражен, для него задается соответствующее свойство, которое не позволяет пользователям скачать его из браузера или синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="abe53-108">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="abe53-109">Эти возможности в SharePoint Online позволяют включать вирусы.</span><span class="sxs-lookup"><span data-stu-id="abe53-109">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="abe53-110">Они не предназначены для защиты от вредоносных программ в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="abe53-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="abe53-111">Мы рекомендуем всем клиентам оценивать и внедрять защиту от вредоносных программ на различных уровнях и применять рекомендации по обеспечению безопасности корпоративной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="abe53-111">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="abe53-112">Более подробную информацию о стратегиях и рекомендациях можно узнать в статье [Security Security](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="abe53-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="abe53-113">Что происходит при отправке зараженного файла в SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="abe53-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="abe53-114">Office 365 использует стандартный модуль обнаружения вирусов.</span><span class="sxs-lookup"><span data-stu-id="abe53-114">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="abe53-115">Ядро работает асинхронно в SharePoint Online и сканирует некоторые файлы после их отправки.</span><span class="sxs-lookup"><span data-stu-id="abe53-115">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="abe53-116">Эвристические алгоритмы используются для определения сканируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="abe53-116">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="abe53-117">Если выясняется, что файл содержит вирус, он помечается, чтобы его нельзя было снова скачать.</span><span class="sxs-lookup"><span data-stu-id="abe53-117">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="abe53-118">В апреле 2018 был удален лимит в 25 МБ для сканированных файлов.</span><span class="sxs-lookup"><span data-stu-id="abe53-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="abe53-119">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="abe53-119">Here's what happens:</span></span>
  
1. <span data-ttu-id="abe53-120">Пользователь отправляет файл в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="abe53-120">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="abe53-121">SharePoint Online определяет, соответствует ли файл условиям проверки.</span><span class="sxs-lookup"><span data-stu-id="abe53-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="abe53-122">Модуль поиска вирусов проверяет файл.</span><span class="sxs-lookup"><span data-stu-id="abe53-122">The virus detection engine scans the file.</span></span>
    
4. <span data-ttu-id="abe53-123">Если обнаруживается вирус, антивирусный модуль устанавливает для файла свойство, которое обозначает, что он заражен.</span><span class="sxs-lookup"><span data-stu-id="abe53-123">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="abe53-124">Что происходит, когда пользователь пытается скачать зараженный файл через браузер?</span><span class="sxs-lookup"><span data-stu-id="abe53-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="abe53-125">Если файл заражен вирусом, пользователь не может скачать его из SharePoint Online с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="abe53-125">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="abe53-126">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="abe53-126">Here's what happens:</span></span>
  
1. <span data-ttu-id="abe53-127">Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="abe53-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="abe53-128">Пользователю выдается предупреждение о том, что вирус обнаружен.</span><span class="sxs-lookup"><span data-stu-id="abe53-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="abe53-129">Пользователю предоставляется возможность загрузить файл и попытаться очистить его с помощью собственного антивирусного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="abe53-129">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="abe53-130">Командлет Set – SPOTenant можно использовать с параметром **дисалловинфектедфиледовнлоад** , чтобы запретить пользователям скачивать обнаруженный файл даже в окне предупреждения о защите от вирусов.</span><span class="sxs-lookup"><span data-stu-id="abe53-130">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="abe53-131">См. раздел [Дисалловинфектедфиледовнлоадhttps://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)] (.</span><span class="sxs-lookup"><span data-stu-id="abe53-131">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="abe53-132">Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?</span><span class="sxs-lookup"><span data-stu-id="abe53-132">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="abe53-p107">Неважно, какой клиент вы используете  новый клиент синхронизации OneDrive (OneDrive.exe) или старый клиент синхронизации OneDrive для бизнеса(Groove.exe),  если файл содержит вирус, он не будет скачан. Клиент выведет уведомление о том, что файл невозможно синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="abe53-p107">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
  

