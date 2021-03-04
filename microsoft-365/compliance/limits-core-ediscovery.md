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
description: В этой статье описываются ограничения в случае с основными электронными данными в Microsoft 365.
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423450"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="79e27-103">Ограничения в core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="79e27-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="79e27-104">В следующей таблице перечислены ограничения для основных случаев, связанных с электронным открытием, и содержится, связанный с случаем, связанным с основными данными об обнаружении электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="79e27-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="79e27-105">Дополнительные сведения о core eDiscovery см. в [обзоре основных сведений об обнаружении электронных данных.](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="79e27-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="79e27-106">Описание ограничения</span><span class="sxs-lookup"><span data-stu-id="79e27-106">Description of limit</span></span> | <span data-ttu-id="79e27-107">Ограничение</span><span class="sxs-lookup"><span data-stu-id="79e27-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="79e27-108">Максимальное количество случаев для организации.</span><span class="sxs-lookup"><span data-stu-id="79e27-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="79e27-109">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="79e27-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="79e27-110">Максимальное количество случаев для организации.</span><span class="sxs-lookup"><span data-stu-id="79e27-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="79e27-111">10 000</span><span class="sxs-lookup"><span data-stu-id="79e27-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="79e27-112">Максимальное количество почтовых ящиков в одном удержании.</span><span class="sxs-lookup"><span data-stu-id="79e27-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="79e27-113">Это ограничение включает общее количество почтовых ящиков пользователей и почтовых ящиков, связанных с группами Microsoft 365, Microsoft Teams и Yammer Groups.</span><span class="sxs-lookup"><span data-stu-id="79e27-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="79e27-114">1,000</span><span class="sxs-lookup"><span data-stu-id="79e27-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="79e27-115">Максимальное количество сайтов в одном удержании.</span><span class="sxs-lookup"><span data-stu-id="79e27-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="79e27-116">Это ограничение включает общее количество сайтов OneDrive для бизнеса, сайтов SharePoint и сайтов, связанных с Группами Microsoft 365, Microsoft Teams и Yammer Groups.</span><span class="sxs-lookup"><span data-stu-id="79e27-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="79e27-117">100</span><span class="sxs-lookup"><span data-stu-id="79e27-117">100</span></span>  <br/> |
  |<span data-ttu-id="79e27-118">Максимальное число случаев, отображаемых на основной домашней странице электронного поиска, и максимальное количество элементов, отображаемых на вкладке "Удерживает", "Поиск" и "Экспорт" в рамках дела.</span><span class="sxs-lookup"><span data-stu-id="79e27-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="79e27-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="79e27-119"><sup>1</sup></span></span> |<span data-ttu-id="79e27-120">1,000</span><span class="sxs-lookup"><span data-stu-id="79e27-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="79e27-121"><sup>1</sup> Чтобы просмотреть список из более чем 1000 дел, удерживаний, поисков или экспортов, можно использовать соответствующие cmdlets Office 365 Security & Compliance PowerShell:</span><span class="sxs-lookup"><span data-stu-id="79e27-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="79e27-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="79e27-122">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="79e27-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="79e27-123">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="79e27-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="79e27-124">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="79e27-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="79e27-125">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="79e27-126">Дополнительные сведения об ограничениях, связанных с поиском контента и экспортом, связанными с делом об обнаружении основных данных, см. в материалах [Limits for Content Search and Core eDiscovery.](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="79e27-126">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>