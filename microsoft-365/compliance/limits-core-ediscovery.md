---
title: Пределы базового случая обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: В этой статье описываются пределы базового случая обнаружения электронных данных в Microsoft 365.
ms.openlocfilehash: 4d91b81caee31e693ce29c6d8d629d563d973ae7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551486"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="9dfb0-103">Пределы в ядре обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="9dfb0-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="9dfb0-104">В следующей таблице перечислены пределы для основных случаев обнаружения электронных данных и удержания, связанные с основным вариантом обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="9dfb0-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="9dfb0-105">Дополнительные сведения о базовом обнаружении содержатся в статье [Обзор основных средств обнаружения электронных](ediscovery-cases.md)данных.</span><span class="sxs-lookup"><span data-stu-id="9dfb0-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="9dfb0-106">**Описание ограничения**</span><span class="sxs-lookup"><span data-stu-id="9dfb0-106">**Description of limit**</span></span>|<span data-ttu-id="9dfb0-107">**Ограничение**</span><span class="sxs-lookup"><span data-stu-id="9dfb0-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="9dfb0-108">Максимальное количество обращений в Организации</span><span class="sxs-lookup"><span data-stu-id="9dfb0-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="9dfb0-109">Нет ограничений</span><span class="sxs-lookup"><span data-stu-id="9dfb0-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="9dfb0-110">Максимальное количество удержаний для Организации</span><span class="sxs-lookup"><span data-stu-id="9dfb0-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="9dfb0-111">10 000</span><span class="sxs-lookup"><span data-stu-id="9dfb0-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="9dfb0-112">Максимальное количество почтовых ящиков в едином случае удержания</span><span class="sxs-lookup"><span data-stu-id="9dfb0-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="9dfb0-113">1,000</span><span class="sxs-lookup"><span data-stu-id="9dfb0-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="9dfb0-114">Максимальное количество сайтов SharePoint и OneDrive для бизнеса в случае единого удержания</span><span class="sxs-lookup"><span data-stu-id="9dfb0-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="9dfb0-115">100</span><span class="sxs-lookup"><span data-stu-id="9dfb0-115">100</span></span>  <br/> |
  |<span data-ttu-id="9dfb0-116">Максимальное число обращений, отображаемых на основной странице обнаружения электронных данных, и максимальное количество элементов, отображаемых на вкладках удержания, поиска и экспорта в случае.</span><span class="sxs-lookup"><span data-stu-id="9dfb0-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="9dfb0-117"><sup>1,1</sup></span><span class="sxs-lookup"><span data-stu-id="9dfb0-117"><sup>1</sup></span></span> |<span data-ttu-id="9dfb0-118">1,000</span><span class="sxs-lookup"><span data-stu-id="9dfb0-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="9dfb0-119"><sup>1</sup> чтобы просмотреть список более чем 1 000 обращений, удержаний, поисков или экспортов, вы можете использовать соответствующий командлет PowerShell для безопасности & соответствия требованиям для Office 365:</span><span class="sxs-lookup"><span data-stu-id="9dfb0-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="9dfb0-120">Get — ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="9dfb0-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [<span data-ttu-id="9dfb0-121">Get — Caseholdpolicy позволяет</span><span class="sxs-lookup"><span data-stu-id="9dfb0-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [<span data-ttu-id="9dfb0-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="9dfb0-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [<span data-ttu-id="9dfb0-123">Get — ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="9dfb0-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)
