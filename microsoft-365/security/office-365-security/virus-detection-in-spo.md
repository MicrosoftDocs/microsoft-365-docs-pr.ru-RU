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
ms.openlocfilehash: 9776dd7791d8543e0fd401a3c21c95d9fbf60f09
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639829"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="9dbad-105">Обнаружение вирусов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9dbad-105">Virus detection in SharePoint Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dbad-106">Для использования этой функции требуется Office 365 Advanced Threat protection (ATP).</span><span class="sxs-lookup"><span data-stu-id="9dbad-106">To use this feature, Office 365 Advanced Threat Protection (ATP) is required.</span></span> <span data-ttu-id="9dbad-107">Дополнительные сведения см. в статье [Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="9dbad-107">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="9dbad-p103">Office 365 помогает защитить рабочую среду от вредоносных программ, обнаруживая вирусы в файлах, которые пользователи отправляют в SharePoint Online. Файлы проверяются на наличие вирусов после отправки. Если вирус заражен, для него задается соответствующее свойство, которое не позволяет пользователям скачать его из браузера или синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="9dbad-p103">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online. Files are scanned for viruses after they are uploaded. If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9dbad-111">Эти возможности в SharePoint Online позволяют включать вирусы.</span><span class="sxs-lookup"><span data-stu-id="9dbad-111">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="9dbad-112">Они не предназначены для защиты от вредоносных программ в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="9dbad-112">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="9dbad-113">Мы рекомендуем всем клиентам оценивать и внедрять защиту от вредоносных программ на различных уровнях и применять рекомендации по обеспечению безопасности корпоративной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="9dbad-113">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="9dbad-114">Более подробную информацию о стратегиях и рекомендациях можно узнать в статье [Security Security](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="9dbad-114">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="9dbad-115">Что происходит при отправке зараженного файла в SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="9dbad-115">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="9dbad-116">Office 365 использует стандартный модуль обнаружения вирусов.</span><span class="sxs-lookup"><span data-stu-id="9dbad-116">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="9dbad-117">Ядро работает асинхронно в SharePoint Online и сканирует файлы после их отправки.</span><span class="sxs-lookup"><span data-stu-id="9dbad-117">The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded.</span></span> <span data-ttu-id="9dbad-118">Если выясняется, что файл содержит вирус, он помечается, чтобы его нельзя было снова скачать.</span><span class="sxs-lookup"><span data-stu-id="9dbad-118">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="9dbad-119">В апреле 2018 был удален лимит в 25 МБ для сканированных файлов.</span><span class="sxs-lookup"><span data-stu-id="9dbad-119">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="9dbad-120">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="9dbad-120">Here's what happens:</span></span>
  
1. <span data-ttu-id="9dbad-121">Пользователь отправляет файл в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9dbad-121">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="9dbad-122">Модуль поиска вирусов проверяет файл.</span><span class="sxs-lookup"><span data-stu-id="9dbad-122">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="9dbad-123">Если обнаруживается вирус, антивирусный модуль устанавливает для файла свойство, которое обозначает, что он заражен.</span><span class="sxs-lookup"><span data-stu-id="9dbad-123">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="9dbad-124">Что происходит, когда пользователь пытается скачать зараженный файл через браузер?</span><span class="sxs-lookup"><span data-stu-id="9dbad-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="9dbad-125">Если файл заражен вирусом, пользователь не может скачать его из SharePoint Online с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="9dbad-125">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="9dbad-126">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="9dbad-126">Here's what happens:</span></span>
  
1. <span data-ttu-id="9dbad-127">Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9dbad-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="9dbad-128">Пользователю выдается предупреждение о том, что вирус обнаружен.</span><span class="sxs-lookup"><span data-stu-id="9dbad-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="9dbad-129">Пользователю предоставляется возможность загрузить файл и попытаться очистить его с помощью собственного антивирусного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="9dbad-129">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="9dbad-130">Командлет Set – SPOTenant можно использовать с параметром **дисалловинфектедфиледовнлоад** , чтобы запретить пользователям скачивать обнаруженный файл даже в окне предупреждения о защите от вирусов.</span><span class="sxs-lookup"><span data-stu-id="9dbad-130">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="9dbad-131">См. раздел [Дисалловинфектедфиледовнлоадhttps://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)] (.</span><span class="sxs-lookup"><span data-stu-id="9dbad-131">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="9dbad-132">Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?</span><span class="sxs-lookup"><span data-stu-id="9dbad-132">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="9dbad-p108">Неважно, какой клиент вы используете  новый клиент синхронизации OneDrive (OneDrive.exe) или старый клиент синхронизации OneDrive для бизнеса(Groove.exe),  если файл содержит вирус, он не будет скачан. Клиент выведет уведомление о том, что файл невозможно синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="9dbad-p108">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
  

