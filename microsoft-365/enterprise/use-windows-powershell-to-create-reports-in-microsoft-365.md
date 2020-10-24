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
description: 'Сводка: использование PowerShell для Microsoft 365 для создания отчетов, которые невозможно создать в центре администрирования Microsoft 365.'
ms.openlocfilehash: 10000f62b1d6a747cf0373623c6038b080666e1a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753982"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="2e756-103">Создание отчетов для Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e756-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="2e756-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="2e756-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2e756-105">В центре администрирования Microsoft 365 доступно множество различных отчетов.</span><span class="sxs-lookup"><span data-stu-id="2e756-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2e756-106">Но в этих отчетах предоставляется очень много сведений, и иногда вам нужно больше.</span><span class="sxs-lookup"><span data-stu-id="2e756-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="2e756-107">Это необходимо, когда вам понадобится PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e756-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="2e756-108">В этих статьях описано, как использовать PowerShell для Microsoft 365 для получения сведений от клиента Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="2e756-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="2e756-109">Приступая к работе с отчетами с помощью PowerShell для Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="2e756-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="2e756-110">Зачем использовать PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e756-110">Why you need to use PowerShell for Microsoft 365</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
    
- <span data-ttu-id="2e756-111">Отчеты для пользовательских учетных записей и лицензий:</span><span class="sxs-lookup"><span data-stu-id="2e756-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="2e756-112">Просмотр лицензий и служб Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e756-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="2e756-113">Просмотр Microsoft 365 с лицензией и нелицензированными пользователями с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e756-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="2e756-114">Просмотр сведений о лицензии и службе учетной записи Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e756-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="2e756-115">Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e756-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="2e756-116">Отчеты для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="2e756-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="2e756-117">Начало работы с командной консолью SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2e756-117">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="2e756-118">Get-SPOSiteGroup — получает все группы в указанном семействе веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="2e756-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="2e756-119">Отчеты для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2e756-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="2e756-120">Отображение почтового ящика с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e756-120">Use Exchange Online PowerShell to display mailbox</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="2e756-121">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="2e756-121">Related articlesl</span></span>

[<span data-ttu-id="2e756-122">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e756-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2e756-123">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e756-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2e756-124">Управление SharePoint с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e756-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2e756-125">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e756-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  