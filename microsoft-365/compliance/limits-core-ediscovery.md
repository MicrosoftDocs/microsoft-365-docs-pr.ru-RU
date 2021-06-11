---
title: Ограничения в случае с основными электронными данными
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: В этой статье описываются ограничения в случае с основными данными об обнаружении электронных Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311428"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="fe422-103">Ограничения в core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fe422-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="fe422-104">В следующей таблице перечислены ограничения для основных случаев, связанных с электронным открытием, и содержится, связанный с случаем, связанным с основными данными об обнаружении электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="fe422-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="fe422-105">Дополнительные сведения о core eDiscovery см. в [обзоре основных сведений об обнаружении электронных данных.](./get-started-core-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="fe422-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="fe422-106">Описание ограничения</span><span class="sxs-lookup"><span data-stu-id="fe422-106">Description of limit</span></span> | <span data-ttu-id="fe422-107">Ограничение</span><span class="sxs-lookup"><span data-stu-id="fe422-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="fe422-108">Максимальное количество случаев для организации.</span><span class="sxs-lookup"><span data-stu-id="fe422-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="fe422-109">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="fe422-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="fe422-110">Максимальное количество случаев для организации.</span><span class="sxs-lookup"><span data-stu-id="fe422-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="fe422-111">10 000</span><span class="sxs-lookup"><span data-stu-id="fe422-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="fe422-112">Максимальное количество почтовых ящиков в одном удержании.</span><span class="sxs-lookup"><span data-stu-id="fe422-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="fe422-113">Это ограничение включает общее общее число почтовых ящиков пользователей и почтовых ящиков, связанных с Microsoft 365, Microsoft Teams и Yammer групп.</span><span class="sxs-lookup"><span data-stu-id="fe422-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="fe422-114">1 000</span><span class="sxs-lookup"><span data-stu-id="fe422-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="fe422-115">Максимальное количество сайтов в одном удержании.</span><span class="sxs-lookup"><span data-stu-id="fe422-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="fe422-116">Это ограничение включает общее количество OneDrive для бизнеса, SharePoint сайтов и сайтов, связанных с Microsoft 365, Microsoft Teams и Yammer groups.</span><span class="sxs-lookup"><span data-stu-id="fe422-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="fe422-117">100</span><span class="sxs-lookup"><span data-stu-id="fe422-117">100</span></span>  <br/> |
  |<span data-ttu-id="fe422-118">Максимальное число случаев, отображаемых на основной домашней странице электронного поиска, и максимальное количество элементов, отображаемых на вкладке "Удерживает", "Поиск" и "Экспорт" в рамках дела.</span><span class="sxs-lookup"><span data-stu-id="fe422-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="fe422-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fe422-119"><sup>1</sup></span></span> |<span data-ttu-id="fe422-120">1 000</span><span class="sxs-lookup"><span data-stu-id="fe422-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="fe422-121"><sup>1</sup> Чтобы просмотреть список из более чем 1000 случаев, удерживаний, поисков или экспорта, можно использовать соответствующие Office 365 безопасности & PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fe422-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="fe422-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="fe422-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="fe422-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="fe422-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="fe422-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="fe422-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="fe422-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="fe422-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="fe422-126">Дополнительные сведения об ограничениях, связанных с поиском и экспортом, связанным с делом об обнаружении основных электронных данных, см. в материалах [Limits for Content search and Core eDiscovery.](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="fe422-126">For more information about limits related to searches and exports associated with a Core eDiscovery case, see [Limits for Content search and Core eDiscovery](limits-for-content-search.md).</span></span>