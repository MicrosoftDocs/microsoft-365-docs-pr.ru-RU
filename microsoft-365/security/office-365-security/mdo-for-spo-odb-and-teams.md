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
description: Узнайте о Microsoft Defender для Office 365 файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a0c9721c4d8fc2087e0dbbce19305060344430c
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096748"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="65432-103">Безопасные вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65432-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="65432-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="65432-104">**Applies to**</span></span>
- [<span data-ttu-id="65432-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="65432-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="65432-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65432-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="65432-107">Сейф Вложения для SharePoint, OneDrive и Microsoft Teams [в Microsoft Defender для Office 365](whats-new-in-defender-for-office-365.md) обеспечивают дополнительный уровень защиты файлов, которые уже асинхронно отсканированы обычным механизмом обнаружения вирусов в [Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="65432-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned asynchronously by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="65432-108">Сейф Вложения для SharePoint, OneDrive и Microsoft Teams помогают обнаруживать и блокировать существующие файлы, идентифицированные как вредоносные на сайтах группы и библиотеках документов.</span><span class="sxs-lookup"><span data-stu-id="65432-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="65432-109">Сейф Вложения для SharePoint, OneDrive и Microsoft Teams по умолчанию не включены.</span><span class="sxs-lookup"><span data-stu-id="65432-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="65432-110">Чтобы включить его, включив Сейф вложения для [SharePoint, OneDrive и Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="65432-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="65432-111">Как Сейф вложения для SharePoint, OneDrive и Microsoft Teams работает</span><span class="sxs-lookup"><span data-stu-id="65432-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="65432-112">Когда Сейф вложения для SharePoint, OneDrive и Microsoft Teams и идентифицирует файл как вредоносный, файл блокируется с помощью прямой интеграции с хранилищами файлов.</span><span class="sxs-lookup"><span data-stu-id="65432-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="65432-113">На следующем изображении показан пример вредоносного файла, обнаруженного в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="65432-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Файлы в OneDrive для бизнеса с одним, обнаруженным как вредоносные](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="65432-115">Несмотря на то, что заблокированный файл по-прежнему перечислены в библиотеке документов и в веб-, мобильных или настольных приложениях, люди не могут открывать, копировать, перемещать или делиться файлом.</span><span class="sxs-lookup"><span data-stu-id="65432-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="65432-116">Но они могут удалить заблокированный файл.</span><span class="sxs-lookup"><span data-stu-id="65432-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="65432-117">Вот пример того, как заблокированный файл выглядит на мобильном устройстве:</span><span class="sxs-lookup"><span data-stu-id="65432-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Удаление заблокированного файла из OneDrive для бизнеса из OneDrive приложения](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="65432-119">По умолчанию люди могут скачать заблокированный файл.</span><span class="sxs-lookup"><span data-stu-id="65432-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="65432-120">Вот как выглядит загрузка заблокированного файла на мобильном устройстве:</span><span class="sxs-lookup"><span data-stu-id="65432-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Загрузка заблокированного файла в OneDrive для бизнеса](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="65432-122">SharePoint Сетевые администраторы могут запретить людям скачивать вредоносные файлы.</span><span class="sxs-lookup"><span data-stu-id="65432-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="65432-123">Инструкции см. в SharePoint Online PowerShell, чтобы запретить пользователям [скачивать вредоносные файлы.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)</span><span class="sxs-lookup"><span data-stu-id="65432-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="65432-124">Дополнительные данные о пользовательском опыте, когда файл был обнаружен как вредоносный, см. в материалах What [to do when a malicious file is found in SharePoint Online, OneDrive или Microsoft Teams.](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="65432-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="65432-125">Просмотр сведений о вредоносных файлах, обнаруженных Сейф вложениями для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65432-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="65432-126">Файлы, которые определены как вредоносные Сейф вложения для SharePoint, OneDrive и Microsoft Teams будут показываться в отчетах для [Microsoft Defender](view-reports-for-mdo.md) для Office 365 и в Explorer (и обнаружения в режиме реального [времени).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="65432-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="65432-127">С мая 2018 г., когда файл Сейф вложениями для SharePoint, OneDrive и Microsoft Teams, файл также доступен в карантине.</span><span class="sxs-lookup"><span data-stu-id="65432-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="65432-128">Дополнительные сведения см. в [материалах Управление карантинными](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)файлами в Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="65432-128">For more information, see [Manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="65432-129">Имейте в виду эти точки</span><span class="sxs-lookup"><span data-stu-id="65432-129">Keep these points in mind</span></span>

- <span data-ttu-id="65432-130">Defender for Office 365 не будет сканировать каждый файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="65432-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="65432-131">Данное поведение является особенностью продукта.</span><span class="sxs-lookup"><span data-stu-id="65432-131">This is by design.</span></span> <span data-ttu-id="65432-132">Файлы сканируют асинхронно.</span><span class="sxs-lookup"><span data-stu-id="65432-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="65432-133">В этом процессе для выявления вредоносных файлов используются события совместной и гостевой активности, а также интеллектуальные heuristics и сигналы угрозы.</span><span class="sxs-lookup"><span data-stu-id="65432-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="65432-134">Убедитесь, что SharePoint веб-сайты настроены для использования современного [опыта](/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="65432-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="65432-135">Защита для Office 365 применяется независимо от того, используется ли современный опыт или классическое представление; Однако визуальные индикаторы блокировки файла доступны только в современном опыте.</span><span class="sxs-lookup"><span data-stu-id="65432-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="65432-136">Сейф Вложения для SharePoint, OneDrive и Microsoft Teams являются частью общей стратегии защиты от угроз вашей организации, которая включает защиту от нежелательной почты и вредоносных программ в Exchange Online Protection (EOP), а также ссылки Сейф и Сейф вложения в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="65432-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="65432-137">Дополнительные дополнительные новости [см.](protect-against-threats.md)в Office 365.</span><span class="sxs-lookup"><span data-stu-id="65432-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
