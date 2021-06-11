---
title: Создание отчетов для Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: Сводка. Используйте PowerShell для Microsoft 365 для создания отчетов, которые нельзя создавать в центре администрирования Microsoft 365 администратора.
ms.openlocfilehash: 9e3b90dcdd32f80125175ad2e15a852db51e17f8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572745"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="c3634-103">Создание отчетов для Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3634-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="c3634-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="c3634-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c3634-105">В центре администрирования Microsoft 365 различных отчетов.</span><span class="sxs-lookup"><span data-stu-id="c3634-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c3634-106">Но эти отчеты предоставляют только столько информации, а иногда требуется больше.</span><span class="sxs-lookup"><span data-stu-id="c3634-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="c3634-107">Вот когда вам нужна PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3634-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="c3634-108">В этих статьях описывается использование PowerShell для Microsoft 365 получения информации от Microsoft 365 клиента:</span><span class="sxs-lookup"><span data-stu-id="c3634-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="c3634-109">Начало работы с отчетами с помощью PowerShell для Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="c3634-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="c3634-110">Зачем использовать PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3634-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="c3634-111">Отчеты для пользовательских учетных записей и лицензий:</span><span class="sxs-lookup"><span data-stu-id="c3634-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="c3634-112">Просмотр Microsoft 365 лицензий и служб с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3634-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="c3634-113">Просмотр Microsoft 365 лицензированных и нелицензионных пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3634-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="c3634-114">Просмотр Microsoft 365 учетной записи и сведений о службе в PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3634-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="c3634-115">Просмотр Microsoft 365 учетных записей пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3634-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="c3634-116">Отчеты для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="c3634-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="c3634-117">Начало работы с командной консолью SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c3634-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="c3634-118">Get-SPOSiteGroup — получает все группы в указанной коллекции сайтов</span><span class="sxs-lookup"><span data-stu-id="c3634-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="c3634-119">Отчеты для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c3634-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="c3634-120">Использование Exchange Online PowerShell для отображения почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c3634-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articles"></a><span data-ttu-id="c3634-121">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c3634-121">Related articles</span></span>

[<span data-ttu-id="c3634-122">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3634-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c3634-123">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3634-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c3634-124">Управление SharePoint с PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3634-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c3634-125">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3634-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
