---
title: Ограничения в основных случаях eDiscovery
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
description: В этой статье описываются ограничения в основных случаях eDiscovery в Microsoft 365.
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799666"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="72b9e-103">Ограничения в core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="72b9e-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="72b9e-104">В следующей таблице перечислены ограничения для основных дел eDiscovery и случаев, связанных с основным делом eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="72b9e-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="72b9e-105">Дополнительные сведения о core eDiscovery см. в [обзоре core eDiscovery.](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="72b9e-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="72b9e-106">Описание ограничения</span><span class="sxs-lookup"><span data-stu-id="72b9e-106">Description of limit</span></span> | <span data-ttu-id="72b9e-107">Ограничение</span><span class="sxs-lookup"><span data-stu-id="72b9e-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="72b9e-108">Максимальное количество дел в организации</span><span class="sxs-lookup"><span data-stu-id="72b9e-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="72b9e-109">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="72b9e-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="72b9e-110">Максимальное количество случаев, когда дело удерживается в организации</span><span class="sxs-lookup"><span data-stu-id="72b9e-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="72b9e-111">10 000</span><span class="sxs-lookup"><span data-stu-id="72b9e-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="72b9e-112">Максимальное количество почтовых ящиков в одном удержании дела</span><span class="sxs-lookup"><span data-stu-id="72b9e-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="72b9e-113">1,000</span><span class="sxs-lookup"><span data-stu-id="72b9e-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="72b9e-114">Максимальное число сайтов SharePoint и OneDrive для бизнеса в одном удержании дел</span><span class="sxs-lookup"><span data-stu-id="72b9e-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="72b9e-115">100</span><span class="sxs-lookup"><span data-stu-id="72b9e-115">100</span></span>  <br/> |
  |<span data-ttu-id="72b9e-116">Максимальное количество дел, отображаемого на основной домашней странице eDiscovery, и максимальное количество элементов, отображаемого на вкладке "Содержит", "Поиск" и "Экспорт" в рамках дела.</span><span class="sxs-lookup"><span data-stu-id="72b9e-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="72b9e-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="72b9e-117"><sup>1</sup></span></span> |<span data-ttu-id="72b9e-118">1,000</span><span class="sxs-lookup"><span data-stu-id="72b9e-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="72b9e-119"><sup>1</sup> Чтобы просмотреть список из более чем 1000 дел, совмещаний, поисков или экспорта, можно использовать соответствующие & PowerShell для обеспечения безопасности и соответствия требованиям Office 365:</span><span class="sxs-lookup"><span data-stu-id="72b9e-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="72b9e-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="72b9e-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="72b9e-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="72b9e-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="72b9e-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="72b9e-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="72b9e-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="72b9e-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="72b9e-124">Дополнительные сведения об ограничениях, связанных с поиском контента и экспортом, связанным с основным делом eDiscovery, см. в поддомене "Ограничения для поиска контента и основного [eDiscovery".](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="72b9e-124">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>