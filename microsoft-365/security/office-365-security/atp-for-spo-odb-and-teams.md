---
title: Безопасные вложения для SharePoint, OneDrive и Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Узнайте о Microsoft Defender для Office 365 для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce73e1fd5c8ecb63bee1db2e9e64aade305b37e9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287057"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e94e2-103">Безопасные вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e94e2-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e94e2-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="e94e2-104">**Applies to**</span></span>
- [<span data-ttu-id="e94e2-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="e94e2-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e94e2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e94e2-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e94e2-107">Безопасные вложения для SharePoint, OneDrive и Microsoft Teams в [Microsoft Defender для Office 365](office-365-atp.md) обеспечивают дополнительный уровень защиты файлов, которые уже были сканированы во время отправки распространенным механизмом обнаружения вирусов в Microsoft [365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="e94e2-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="e94e2-108">Безопасные вложения для SharePoint, OneDrive и Microsoft Teams помогают обнаруживать и блокировать существующие файлы, которые определены как вредоносные на сайтах групп и в библиотеках документов.</span><span class="sxs-lookup"><span data-stu-id="e94e2-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="e94e2-109">Безопасные вложения для SharePoint, OneDrive и Microsoft Teams по умолчанию не включены.</span><span class="sxs-lookup"><span data-stu-id="e94e2-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="e94e2-110">Чтобы включить его, см. раздел "Включить безопасные [вложения для SharePoint, OneDrive и Microsoft Teams".](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e94e2-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="e94e2-111">Как работают безопасные вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e94e2-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="e94e2-112">Если в SharePoint, OneDrive и Microsoft Teams включены безопасные вложения и файл идентифицируется как вредоносный, файл блокируется с помощью прямой интеграции с хранилищами файлов.</span><span class="sxs-lookup"><span data-stu-id="e94e2-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="e94e2-113">На следующем рисунке показан пример вредоносного файла, обнаруженного в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="e94e2-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Файлы в OneDrive для бизнеса, один из них был обнаружен как вредоносный](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="e94e2-115">Хотя заблокированный файл по-прежнему находится в библиотеке документов и в веб-приложениях, мобильных или классических приложениях, пользователи не могут открывать, копировать, перемещать или делиться файлом.</span><span class="sxs-lookup"><span data-stu-id="e94e2-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="e94e2-116">Но они могут удалить заблокированный файл.</span><span class="sxs-lookup"><span data-stu-id="e94e2-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="e94e2-117">Вот пример того, как заблокированный файл выглядит на мобильном устройстве:</span><span class="sxs-lookup"><span data-stu-id="e94e2-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Удаление заблокированного файла из OneDrive для бизнеса из мобильного приложения OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="e94e2-119">По умолчанию люди могут скачать заблокированный файл.</span><span class="sxs-lookup"><span data-stu-id="e94e2-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="e94e2-120">Вот как выглядит скачивание заблокированного файла на мобильном устройстве:</span><span class="sxs-lookup"><span data-stu-id="e94e2-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Скачивание заблокированного файла в OneDrive для бизнеса](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="e94e2-122">Администраторы SharePoint Online могут запретить скачивание вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="e94e2-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="e94e2-123">Инструкции см. в [sharePoint Online PowerShell, чтобы](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)запретить пользователям скачивать вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="e94e2-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="e94e2-124">Чтобы узнать больше о пользовательском интерфейсе при обнаружении файла как вредоносного, см. раздел "Что делать при обнаружении вредоносного файла в [SharePoint Online, OneDrive или Microsoft Teams".](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="e94e2-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e94e2-125">Просмотр сведений о вредоносных файлах, обнаруженных с помощью безопасных вложений для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e94e2-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="e94e2-126">Файлы, которые определены Как вредоносные в Microsoft Defender для Office 365, будут открыться в отчетах для Microsoft Defender для [Office 365](view-reports-for-atp.md) и [в проводнике (и](threat-explorer.md)обнаружения в режиме реального времени).</span><span class="sxs-lookup"><span data-stu-id="e94e2-126">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="e94e2-127">С мая 2018 г., когда Microsoft Defender для Office 365 определил файл как вредоносный, он также доступен в карантине.</span><span class="sxs-lookup"><span data-stu-id="e94e2-127">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="e94e2-128">Дополнительные сведения см. в центре безопасности & соответствия требованиям для управления файлами [на карантине.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)</span><span class="sxs-lookup"><span data-stu-id="e94e2-128">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="e94e2-129">Помните об этих моментах</span><span class="sxs-lookup"><span data-stu-id="e94e2-129">Keep these points in mind</span></span>

- <span data-ttu-id="e94e2-130">Защитник Office 365 не будет сканировать каждый файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e94e2-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="e94e2-131">Данное поведение является особенностью продукта.</span><span class="sxs-lookup"><span data-stu-id="e94e2-131">This is by design.</span></span> <span data-ttu-id="e94e2-132">Файлы проверяются асинхронно.</span><span class="sxs-lookup"><span data-stu-id="e94e2-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="e94e2-133">Этот процесс использует события общего доступа и гостевой активности, а также интеллектуальные сигналы и сигналы угроз для идентификации вредоносных файлов.</span><span class="sxs-lookup"><span data-stu-id="e94e2-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="e94e2-134">Убедитесь, что сайты SharePoint настроены на использование современного [опыта.](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)</span><span class="sxs-lookup"><span data-stu-id="e94e2-134">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="e94e2-135">Защита в Защитнике Office 365 применяется как в современном, так и в классическом представлении; Однако визуальные индикаторы блокировки файла доступны только в современном средстве.</span><span class="sxs-lookup"><span data-stu-id="e94e2-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="e94e2-136">Безопасные вложения для SharePoint, OneDrive и Microsoft Teams входят в общую стратегию вашей организации по защите от угроз, которая включает защиту от нежелательной почты и вредоносных программ в Exchange Online Protection (EOP), а также безопасные ссылки и безопасные вложения в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="e94e2-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e94e2-137">Дополнительные информации [см. в этой теме, в этой теме вы узнаете, как защититься от угроз в Office 365.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="e94e2-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
