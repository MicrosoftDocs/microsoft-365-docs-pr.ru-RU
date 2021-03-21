---
title: Настройка обнаружения электронных данных в Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Узнайте, как использовать параметр Region для настройки электронных открытий для использования в спутниковых расположениях в Microsoft 365 Multi-Geo.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923724"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="e1cfe-103">Настройка обнаружения электронных данных в Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="e1cfe-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="e1cfe-104">[Расширенные возможности по](../compliance/overview-ediscovery-20.md) обнаружению электронных данных позволяют администратору многоэтапного электронного поиска искать все географические области без необходимости использовать фильтр безопасности "Region".</span><span class="sxs-lookup"><span data-stu-id="e1cfe-104">[Advanced eDiscovery capabilities](../compliance/overview-ediscovery-20.md) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="e1cfe-105">Данные экспортируются в экземпляр Azure центрального расположения клиента с несколькими географическими данными.</span><span class="sxs-lookup"><span data-stu-id="e1cfe-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="e1cfe-106">Без расширенных возможностей по обнаружению электронных данных менеджер по обнаружению электронных данных или администратор клиента с несколькими географическими данными смогут проводить проверку данных только в центральном расположении этого клиента.</span><span class="sxs-lookup"><span data-stu-id="e1cfe-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="e1cfe-107">Чтобы поддерживать возможность проведения электронных разыскных данных для спутниковых местоположений, с помощью PowerShell доступен новый параметр фильтра безопасности соответствия требованиям с именем "Регион".</span><span class="sxs-lookup"><span data-stu-id="e1cfe-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="e1cfe-108">Этот параметр можно использовать для клиентов, центральное расположение которых находится в Северной Америке, Европе или Азиатско-Тихоокеанском регионе.</span><span class="sxs-lookup"><span data-stu-id="e1cfe-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="e1cfe-109">Предварительное открытие электронных данных рекомендуется для клиентов, центральное расположение которых не находится в Северной Америке, Европе или Азиатско-Тихоокеанском регионе и которым необходимо выполнять данные об обнаружении электронных данных в спутниковых георасположениях.</span><span class="sxs-lookup"><span data-stu-id="e1cfe-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="e1cfe-110">Глобальный администратор Microsoft 365 должен предоставить менеджеру по обнаружению электронных данных право разрешать другим пользователям выполнять обнаружение электронных данных и назначать параметр Region в соответствующем фильтре соответствия требованиям безопасности, чтобы указывать вспомогательное расположение в качестве региона для обнаружения электронных данных. В противном случае обнаружение электронных данных не будет выполняться для вспомогательного расположения.</span><span class="sxs-lookup"><span data-stu-id="e1cfe-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="e1cfe-p103">Если роль менеджера по обнаружению электронных данных или администратора задана для определенного периферийного расположения, то соответствующий пользователь сможет выполнять операции поиска с обнаружением электронных данных только на сайтах SharePoint и OneDrive, расположенных в этом периферийном расположении. Если менеджер по обнаружению электронных данных попробует выполнить поиск на сайтах SharePoint или OneDrive за пределами указанного периферийного расположения, результаты не будут возвращаться. Кроме того, когда менеджер по обнаружению электронных данных или администратор для периферийного расположения запускает экспорт, данные экспортируются в экземпляр Azure в этом регионе. Это помогает организациям обеспечивать соответствие требованиям, не разрешая экспорт содержимого через контролируемые границы.</span><span class="sxs-lookup"><span data-stu-id="e1cfe-p103">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location. If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned. Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region. This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="e1cfe-115">Если менеджеру по обнаружению электронных данных требуется искать содержимое в нескольких периферийных расположениях SharePoint, необходимо создать для него еще одну учетную запись, указывающую альтернативное периферийное расположение, где находятся сайты OneDrive или SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1cfe-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="e1cfe-116">Установка фильтра соответствия требованиям безопасности для региона:</span><span class="sxs-lookup"><span data-stu-id="e1cfe-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="e1cfe-117">Подключение к PowerShell в Центре безопасности и соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1cfe-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="e1cfe-118">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e1cfe-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="e1cfe-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="e1cfe-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="e1cfe-120">Дополнительные параметры и синтаксис рассматриваются в статье [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter).</span><span class="sxs-lookup"><span data-stu-id="e1cfe-120">See the [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>