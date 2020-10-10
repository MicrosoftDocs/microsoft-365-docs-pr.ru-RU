---
title: ATP для SharePoint, OneDrive и Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365-initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Сведения о Advanced Threat Protection в Office 365 для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.openlocfilehash: e36efba37ae21ee1e2044d8b631cb14b17fcca55
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411762"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="efd10-103">ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efd10-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="efd10-104">ATP для SharePoint, OneDrive и Microsoft Teams в [Office 365 Advanced Threat protection (ATP)](office-365-atp.md) обеспечивает дополнительный уровень защиты для файлов, которые уже были проверены во время отправки с помощью [общего модуля обнаружения вирусов в Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="efd10-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="efd10-105">ATP для SharePoint, OneDrive и Microsoft Teams помогает обнаруживать и блокировать существующие файлы, которые определены как вредоносные на сайтах групп и библиотеках документов.</span><span class="sxs-lookup"><span data-stu-id="efd10-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="efd10-106">Служба ATP для SharePoint, OneDrive и Microsoft Teams по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="efd10-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="efd10-107">Чтобы включить его, ознакомьтесь со статьей [Включение ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="efd10-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="efd10-108">Принципы работы ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efd10-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="efd10-109">Когда ATP для SharePoint, OneDrive и Microsoft Teams включается и определяет файл как вредоносный, файл блокируется с помощью непосредственной интеграции с хранилищами файлов.</span><span class="sxs-lookup"><span data-stu-id="efd10-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="efd10-110">На следующем рисунке показан пример вредоносного файла, обнаруженного в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="efd10-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Файлы в OneDrive для бизнеса с одной обнаруженной вредоносной службой](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="efd10-112">Несмотря на то, что заблокированный файл все еще отображается в библиотеке документов, в веб-приложениях, мобильных или настольных компьютерах, пользователи не могут открывать, копировать, перемещать файлы и предоставлять к ним общий доступ.</span><span class="sxs-lookup"><span data-stu-id="efd10-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="efd10-113">Но они могут удалить заблокированный файл.</span><span class="sxs-lookup"><span data-stu-id="efd10-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="efd10-114">Ниже приведен пример того, как выглядит заблокированный файл на мобильном устройстве:</span><span class="sxs-lookup"><span data-stu-id="efd10-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Удаление заблокированного файла из OneDrive для бизнеса из мобильного приложения OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="efd10-116">По умолчанию пользователи могут скачать заблокированный файл.</span><span class="sxs-lookup"><span data-stu-id="efd10-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="efd10-117">Ниже показано, как выполняется загрузка заблокированного файла на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="efd10-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Скачивание заблокированного файла в OneDrive для бизнеса](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="efd10-119">Администраторы SharePoint Online могут запретить пользователям загружать вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="efd10-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="efd10-120">Инструкции можно найти [в статье Использование PowerShell для SharePoint Online, чтобы запретить пользователям скачивать вредоносные файлы](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="efd10-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="efd10-121">Чтобы узнать больше о пользовательском интерфейсе, когда файл был определен как вредоносный, посмотрите, [что делать, когда вредоносный файл обнаружен в SharePoint Online, OneDrive или Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="efd10-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="efd10-122">Просмотр сведений о вредоносных файлах, обнаруженных ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efd10-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="efd10-123">Файлы, идентифицируемые средством ATP, будут отображаться в [отчетах для Office 365 Advanced Threat protection](view-reports-for-atp.md) и в [Проводнике (и обнаружения в режиме реального времени)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="efd10-123">Files that are identified as malicious by ATP will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="efd10-124">По достижении мая 2018, когда файл определяется как вредоносный для ATP, он также доступен в карантине.</span><span class="sxs-lookup"><span data-stu-id="efd10-124">As of May 2018, when a file is identified as malicious by ATP, the file is also available in quarantine.</span></span> <span data-ttu-id="efd10-125">Дополнительные сведения можно найти [в статье Использование центра безопасности & соответствия требованиям для управления файлами, помещенными в карантин](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="efd10-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="efd10-126">Помните об этих моментах</span><span class="sxs-lookup"><span data-stu-id="efd10-126">Keep these points in mind</span></span>

- <span data-ttu-id="efd10-127">ATP не будет сканировать каждый отдельный файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="efd10-127">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="efd10-128">Данное поведение является особенностью продукта.</span><span class="sxs-lookup"><span data-stu-id="efd10-128">This is by design.</span></span> <span data-ttu-id="efd10-129">Файлы сканируются асинхронно.</span><span class="sxs-lookup"><span data-stu-id="efd10-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="efd10-130">Процесс использует события общего доступа и гостевых действий, а также интеллектуальные эвристики и сигналы угроз для определения вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="efd10-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="efd10-131">Убедитесь, что сайты SharePoint настроены на использование [современного интерфейса](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="efd10-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="efd10-132">Защита ATP определяет, используется ли современный интерфейс или классическое представление; Однако визуальные индикаторы, заблокированные файлом, доступны только в современном интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="efd10-132">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="efd10-133">ATP для SharePoint, OneDrive и Microsoft Teams является частью общей стратегии защиты от угроз, включающей защиту от нежелательной почты и вредоносных программ в Exchange Online Protection (EOP), а также безопасные ссылки и безопасные вложения в Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="efd10-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Office 365 ATP.</span></span> <span data-ttu-id="efd10-134">Чтобы узнать больше, ознакомьтесь [со статьей защита от угроз в Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="efd10-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
