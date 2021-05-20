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
description: 'Описание: Используйте PowerShell Microsoft 365 для создания отчетов, которые нельзя создавать в Microsoft 365 администратора.'
ms.openlocfilehash: 9e3b90dcdd32f80125175ad2e15a852db51e17f8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572745"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="8a48f-103">Создание отчетов для Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a48f-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="8a48f-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="8a48f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8a48f-105">В центре управления Microsoft 365 доступно множество различных отчетов.</span><span class="sxs-lookup"><span data-stu-id="8a48f-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8a48f-106">Но эти отчеты предоставляют только так много информации, а иногда и нужно больше.</span><span class="sxs-lookup"><span data-stu-id="8a48f-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="8a48f-107">Вот когда вам нужно PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a48f-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="8a48f-108">В этих статьях описывается, как использовать PowerShell Microsoft 365, чтобы получить информацию от Microsoft 365 арендатора:</span><span class="sxs-lookup"><span data-stu-id="8a48f-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="8a48f-109">Начать с отчетности с помощью PowerShell для Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8a48f-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="8a48f-110">Зачем использовать PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a48f-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="8a48f-111">Отчеты для пользовательских учетных записей и лицензий:</span><span class="sxs-lookup"><span data-stu-id="8a48f-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="8a48f-112">Просмотр Microsoft 365 и услуг с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a48f-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="8a48f-113">Просмотр Microsoft 365 и нелицензированных пользователей с Помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a48f-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="8a48f-114">Просмотр Microsoft 365 учетной записи и реквизитов обслуживания с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a48f-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="8a48f-115">Просмотр Microsoft 365 учетных записей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a48f-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="8a48f-116">Отчеты для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="8a48f-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="8a48f-117">Начало работы с командной консолью SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8a48f-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="8a48f-118">Get-SPOSiteGroup - Получает все группы на указанном сайте коллекции</span><span class="sxs-lookup"><span data-stu-id="8a48f-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="8a48f-119">Отчеты для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8a48f-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="8a48f-120">Используйте Exchange Online PowerShell для отображения почтового ящика</span><span class="sxs-lookup"><span data-stu-id="8a48f-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articles"></a><span data-ttu-id="8a48f-121">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="8a48f-121">Related articles</span></span>

[<span data-ttu-id="8a48f-122">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a48f-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8a48f-123">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a48f-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8a48f-124">Управление SharePoint с PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a48f-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8a48f-125">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a48f-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
