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
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844240"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="02c49-103">Встроенная защита от вирусов в SharePoint Online, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="02c49-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="02c49-104">Microsoft 365 использует общий модуль обнаружения вирусов для сканирования файлов, которые пользователи отправляют в SharePoint Online, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="02c49-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="02c49-105">Эта защита включена со всеми подписками, включающими SharePoint Online, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="02c49-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02c49-106">Встроенные средства защиты от вирусов позволяют включать вирусы.</span><span class="sxs-lookup"><span data-stu-id="02c49-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="02c49-107">Они не предназначены для защиты от вредоносных программ в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="02c49-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="02c49-108">Мы рекомендуем всем пользователям исследовать и внедрять защиту от вредоносных программ на различных уровнях и применять рекомендации по обеспечению безопасности инфраструктуры предприятия.</span><span class="sxs-lookup"><span data-stu-id="02c49-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="02c49-109">Более подробную информацию о стратегиях и рекомендациях можно узнать в статье [Security Security](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="02c49-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="02c49-110">Что происходит при отправке зараженного файла в SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="02c49-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="02c49-111">Антивирусный механизм обнаружения вирусов (Майкрософт 365) запускается асинхронно в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="02c49-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="02c49-112">**При отправке не выполняется автоматический поиск всех файлов**.</span><span class="sxs-lookup"><span data-stu-id="02c49-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="02c49-113">Эвристические правила определяют сканируемые файлы.</span><span class="sxs-lookup"><span data-stu-id="02c49-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="02c49-114">Если файл содержит вирус, он помечается с пометкой, поэтому его невозможно скачать повторно.</span><span class="sxs-lookup"><span data-stu-id="02c49-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="02c49-115">В апреле 2018 был удален лимит в 25 МБ для сканированных файлов.</span><span class="sxs-lookup"><span data-stu-id="02c49-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="02c49-116">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="02c49-116">Here's what happens:</span></span>

1. <span data-ttu-id="02c49-117">Пользователь отправляет файл в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="02c49-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="02c49-118">SharePoint Online определяет, соответствует ли файл условиям проверки.</span><span class="sxs-lookup"><span data-stu-id="02c49-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="02c49-119">Модуль поиска вирусов проверяет файл.</span><span class="sxs-lookup"><span data-stu-id="02c49-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="02c49-120">Если обнаружен вирус, антивирусная программа задает для файла свойство, указывающее на то, что оно заражено.</span><span class="sxs-lookup"><span data-stu-id="02c49-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="02c49-121">Что происходит, когда пользователь пытается скачать зараженный файл через браузер?</span><span class="sxs-lookup"><span data-stu-id="02c49-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="02c49-122">Если файл заражен, пользователи не могут скачать файл из SharePoint Online с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="02c49-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="02c49-123">Ниже вкратце описано, что происходит.</span><span class="sxs-lookup"><span data-stu-id="02c49-123">Here's what happens:</span></span>

1. <span data-ttu-id="02c49-124">Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="02c49-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="02c49-125">Пользователю выдается предупреждение о том, что вирус обнаружен.</span><span class="sxs-lookup"><span data-stu-id="02c49-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="02c49-126">По умолчанию пользователю предоставляется возможность загрузить файл и попытаться очистить его с помощью антивирусного программного обеспечения на отдельном устройстве.</span><span class="sxs-lookup"><span data-stu-id="02c49-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="02c49-127">Администраторы могут использовать параметр *дисалловинфектедфиледовнлоад* в командлете [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженные файлы даже в окне предупреждения о антивирусной борьбе.</span><span class="sxs-lookup"><span data-stu-id="02c49-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="02c49-128">Инструкции можно найти [в статье Использование PowerShell для SharePoint Online, чтобы запретить пользователям скачивать вредоносные файлы](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="02c49-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="02c49-129">После включения параметра *дисалловинфектедфиледовнлоад* доступ к обнаруженным и заблокированным файлам полностью блокируется для пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="02c49-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="02c49-130">Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?</span><span class="sxs-lookup"><span data-stu-id="02c49-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="02c49-131">Клиенты синхронизации OneDrive не будут скачивать файлы, содержащие вирусы.</span><span class="sxs-lookup"><span data-stu-id="02c49-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="02c49-132">Клиент выведет уведомление о том, что файл невозможно синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="02c49-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="02c49-133">Расширенные возможности с помощью защитника Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="02c49-133">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="02c49-134">Microsoft 365 организации с [защитником Майкрософт для Office 365](office-365-atp.md) , включенным в свою подписку или приобретенными в качестве надстройки, могут включить ATP для SharePoint, OneDrive и Microsoft Teams для расширенных отчетов и защиты.</span><span class="sxs-lookup"><span data-stu-id="02c49-134">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="02c49-135">Для получения дополнительных сведений ознакомьтесь [со статьей ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="02c49-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="02c49-136">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="02c49-136">More information</span></span>

<span data-ttu-id="02c49-137">Для получения дополнительных сведений о антивирусной борьбе в SharePoint Online, OneDrive и Microsoft Teams, ознакомьтесь со статьей [Защита от угроз](protect-against-threats.md) и [Включение ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="02c49-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
