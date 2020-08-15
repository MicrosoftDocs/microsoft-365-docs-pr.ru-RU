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
ms.openlocfilehash: 99aa86b1b58b15c63803e1b71d071cbde5c38492
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693282"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="b1525-103">Создание отчетов для Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="b1525-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="b1525-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b1525-105">В Центре администрирования Microsoft 365 доступно множество различных отчетов.</span><span class="sxs-lookup"><span data-stu-id="b1525-105">There are many different reports available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b1525-106">Тем не менее иногда представленной в них информации бывает недостаточно.</span><span class="sxs-lookup"><span data-stu-id="b1525-106">However, these reports only provide so much information and sometimes you need more.</span></span> <span data-ttu-id="b1525-107">Если вам нужна оболочка PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1525-107">That's when you need PowerShell for Microsoft 365</span></span>
  
<span data-ttu-id="b1525-108">В этих статьях описано, как использовать PowerShell для Microsoft 365 для получения сведений от клиента Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="b1525-108">These articles that describe how to use PowerShell for Microsoft 365 to obtain information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="b1525-109">Начало работы с отчетами с помощью PowerShell для Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="b1525-109">Getting started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="b1525-110">В PowerShell для Microsoft 365 могут отображаться дополнительные сведения, которые не отображаются в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="b1525-110">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Admin center</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
  - [<span data-ttu-id="b1525-111">PowerShell для Microsoft 365 отлично подходит для фильтрации данных</span><span class="sxs-lookup"><span data-stu-id="b1525-111">PowerShell for Microsoft 365 is great at filtering data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#filter)
    
  - [<span data-ttu-id="b1525-112">Оболочка PowerShell для Microsoft 365 упрощает печать и сохранение данных</span><span class="sxs-lookup"><span data-stu-id="b1525-112">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#printsave)
    
- <span data-ttu-id="b1525-113">Отчеты для пользовательских учетных записей и лицензий:</span><span class="sxs-lookup"><span data-stu-id="b1525-113">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="b1525-114">Просмотр лицензий и служб Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-114">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="b1525-115">Просмотр Microsoft 365 с лицензией и нелицензированными пользователями с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-115">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="b1525-116">Просмотр сведений о лицензии и службе учетной записи Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-116">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="b1525-117">Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-117">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="b1525-118">Отчеты для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="b1525-118">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="b1525-119">Начало работы с командной консолью SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b1525-119">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="b1525-120">Управление группами сайтов SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-120">Manage SharePoint Online site groups with PowerShell</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="b1525-121">Отчеты для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="b1525-121">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="b1525-122">Отображение сведений о почтовом ящике Exchange Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-122">Display Exchange Online mailbox information with PowerShell</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
  - [<span data-ttu-id="b1525-123">Отображение отчетов Exchange Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-123">Display Exchange Online reports with PowerShell</span></span>](https://technet.microsoft.com/library/4873a063-9fc4-4ed9-826a-6e935fef61d4.aspx)
    
## <a name="related-topics"></a><span data-ttu-id="b1525-124">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b1525-124">Related topics</span></span>

[<span data-ttu-id="b1525-125">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b1525-126">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1525-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b1525-127">Управление SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-127">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b1525-128">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1525-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
