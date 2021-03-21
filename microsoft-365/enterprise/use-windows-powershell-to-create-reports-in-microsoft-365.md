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
description: Сводка. Используйте PowerShell для Microsoft 365 для создания отчетов, которые нельзя создавать в центре администрирования Microsoft 365.
ms.openlocfilehash: 12cba74d114ea03804741335bd34ece403926033
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924700"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="46f37-103">Создание отчетов для Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="46f37-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="46f37-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="46f37-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="46f37-105">В центре администрирования Microsoft 365 доступно множество различных отчетов.</span><span class="sxs-lookup"><span data-stu-id="46f37-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="46f37-106">Но эти отчеты предоставляют только столько информации, а иногда требуется больше.</span><span class="sxs-lookup"><span data-stu-id="46f37-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="46f37-107">Именно тогда вам потребуется PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46f37-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="46f37-108">В этих статьях описано, как использовать PowerShell для Microsoft 365 для получения информации от клиента Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="46f37-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="46f37-109">Начало работы с отчетами с помощью PowerShell для Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="46f37-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="46f37-110">Зачем использовать PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46f37-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md#reveal)
    
    
- <span data-ttu-id="46f37-111">Отчеты для пользовательских учетных записей и лицензий:</span><span class="sxs-lookup"><span data-stu-id="46f37-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="46f37-112">Просмотр лицензий и служб Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="46f37-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="46f37-113">Просмотр пользователей Microsoft 365 с лицензией и без лицензии с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="46f37-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="46f37-114">Просмотр лицензии учетной записи Microsoft 365 и сведений о службе с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="46f37-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="46f37-115">Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="46f37-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="46f37-116">Отчеты для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="46f37-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="46f37-117">Начало работы с командной консолью SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="46f37-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="46f37-118">Get-SPOSiteGroup — получает все группы в указанной коллекции сайтов</span><span class="sxs-lookup"><span data-stu-id="46f37-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="46f37-119">Отчеты для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="46f37-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="46f37-120">Использование Exchange Online PowerShell для отображения почтового ящика</span><span class="sxs-lookup"><span data-stu-id="46f37-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="46f37-121">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="46f37-121">Related articlesl</span></span>

[<span data-ttu-id="46f37-122">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="46f37-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="46f37-123">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46f37-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="46f37-124">Управление SharePoint с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="46f37-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="46f37-125">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="46f37-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
