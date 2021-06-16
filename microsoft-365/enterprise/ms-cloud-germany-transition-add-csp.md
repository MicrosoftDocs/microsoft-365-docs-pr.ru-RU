---
title: Дополнительные сведения для поставщиков облачных решений
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Сводка. Дополнительные сведения для поставщиков облачных решений, которые имеют отношение к миграции из Microsoft Cloud Deutschland.
ms.openlocfilehash: 7a7c377d8e0b72a0179ff28a93018f88d22a5325
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52931057"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="5e210-103">Дополнительные сведения для поставщиков облачных решений</span><span class="sxs-lookup"><span data-stu-id="5e210-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="5e210-104">Поставщики облачных решений (CSPs), поддерживающие клиентов, должны предпринять дополнительные действия во время миграции из Microsoft Cloud Deutschland в новый немецкий центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="5e210-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="5e210-105">Миграция клиента-партнера</span><span class="sxs-lookup"><span data-stu-id="5e210-105">Partner tenant migration</span></span>

<span data-ttu-id="5e210-106">Клиенты партнеров Microsoft Cloud Deutschland не будут перенесены.</span><span class="sxs-lookup"><span data-stu-id="5e210-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="5e210-107">Вместо этого для каждого Office 365 Microsoft Partner в новом немецком регионе центра обработки данных будет создан новый клиент Office 365 служб.</span><span class="sxs-lookup"><span data-stu-id="5e210-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="5e210-108">Клиенты CSP будут перенесены в новый немецкий центр обработки данных и связаны с новым клиентом Office 365 услуг того же партнера.</span><span class="sxs-lookup"><span data-stu-id="5e210-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="5e210-109">После перехода клиента партнер может управлять клиентом с помощью нового клиента Office 365 служб в немецком регионе центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="5e210-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="5e210-110">Отсутствующие подписки в Azure</span><span class="sxs-lookup"><span data-stu-id="5e210-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="5e210-111">После завершения перехода на подписку и лицензирование [(этап 3)](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) поставщики облачных решений больше не будут иметь доступ к подписке Azure.</span><span class="sxs-lookup"><span data-stu-id="5e210-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="5e210-112">Чтобы восстановить доступ, выполните следующие действия, чтобы повысить доступ к управлению всеми подписками [и группами управления Azure.](/azure/role-based-access-control/elevate-access-global-admin)</span><span class="sxs-lookup"><span data-stu-id="5e210-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
