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
ms.openlocfilehash: 6a47f52a30f90d7a19cc01dc9e14eb9b534ec244
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034954"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="17e94-103">Обнаружение вирусов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="17e94-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="17e94-104">Microsoft 365 поможет защитить среду от вредоносных программ, обнаруживая вирусы в файлах, отправляемых пользователями в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="17e94-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="17e94-105">После отправки файлы могут быть проверены на наличие вирусов.</span><span class="sxs-lookup"><span data-stu-id="17e94-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="17e94-106">Если вирус заражен, для него задается соответствующее свойство, которое не позволяет пользователям скачать его из браузера или синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="17e94-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17e94-107">Эти возможности в SharePoint Online позволяют включать вирусы.</span><span class="sxs-lookup"><span data-stu-id="17e94-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="17e94-108">Они не предназначены для защиты от вредоносных программ в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="17e94-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="17e94-109">Мы рекомендуем всем клиентам оценивать и внедрять защиту от вредоносных программ на различных уровнях и применять рекомендации по обеспечению безопасности корпоративной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="17e94-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="17e94-110">Более подробную информацию о стратегиях и рекомендациях можно узнать в статье [Security Security](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="17e94-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="17e94-111">Что происходит при отправке зараженного файла в SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="17e94-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="17e94-112">Microsoft 365 использует общий механизм обнаружения вирусов.</span><span class="sxs-lookup"><span data-stu-id="17e94-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="17e94-113">Ядро работает асинхронно в SharePoint Online и сканирует некоторые файлы после их отправки.</span><span class="sxs-lookup"><span data-stu-id="17e94-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="17e94-114">Эвристические алгоритмы используются для определения сканируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="17e94-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="17e94-115">Если выясняется, что файл содержит вирус, он помечается, чтобы его нельзя было снова скачать.</span><span class="sxs-lookup"><span data-stu-id="17e94-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="17e94-116">В апреле 2018 был удален лимит в 25 МБ для сканированных файлов.</span><span class="sxs-lookup"><span data-stu-id="17e94-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="17e94-117">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="17e94-117">Here's what happens:</span></span>

1. <span data-ttu-id="17e94-118">Пользователь отправляет файл в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="17e94-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="17e94-119">SharePoint Online определяет, соответствует ли файл условиям проверки.</span><span class="sxs-lookup"><span data-stu-id="17e94-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="17e94-120">Модуль поиска вирусов проверяет файл.</span><span class="sxs-lookup"><span data-stu-id="17e94-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="17e94-121">Если обнаружен вирус, антивирусная программа задает для файла свойство, указывающее на то, что оно заражено.</span><span class="sxs-lookup"><span data-stu-id="17e94-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="17e94-122">Что происходит, когда пользователь пытается скачать зараженный файл через браузер?</span><span class="sxs-lookup"><span data-stu-id="17e94-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="17e94-123">Если файл заражен, пользователи не могут скачать файл из SharePoint Online с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="17e94-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="17e94-124">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="17e94-124">Here's what happens:</span></span>

1. <span data-ttu-id="17e94-125">Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="17e94-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="17e94-126">Пользователю выдается предупреждение о том, что вирус обнаружен.</span><span class="sxs-lookup"><span data-stu-id="17e94-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="17e94-127">Пользователю предоставляется возможность загрузить файл и попытаться очистить его с помощью собственного антивирусного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="17e94-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="17e94-128">Вы можете использовать параметр *дисалловинфектедфиледовнлоад* командлета [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженный файл даже в окне предупреждения о антивирусной борьбе.</span><span class="sxs-lookup"><span data-stu-id="17e94-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="17e94-129">Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?</span><span class="sxs-lookup"><span data-stu-id="17e94-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="17e94-p105">Неважно, какой клиент вы используете  новый клиент синхронизации OneDrive (OneDrive.exe) или старый клиент синхронизации OneDrive для бизнеса(Groove.exe),  если файл содержит вирус, он не будет скачан. Клиент выведет уведомление о том, что файл невозможно синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="17e94-p105">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
