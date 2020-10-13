---
title: Миграция между клиентами и клиентами Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Сведения о переносе клиентов Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17aabbd945c6dec699384eb9f203029255ae62f6
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447154"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="d59c4-103">Миграция между клиентами и клиентами Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d59c4-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="d59c4-104">Существует несколько подходов к архитектуре для слияния, приобретения, дивеститурес и других сценариев, которые могут привести к переносу существующего клиента Microsoft 365 в новый клиент.</span><span class="sxs-lookup"><span data-stu-id="d59c4-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="d59c4-105">Большинство клиентов работают с консалтинговой службой Майкрософт или партнером корпорации Майкрософт для переноса клиентов, в том числе с помощью сторонних средств для переноса контента.</span><span class="sxs-lookup"><span data-stu-id="d59c4-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="d59c4-106">Используйте [модель архитектуры миграции "клиент — клиент](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) ", чтобы определить, как планировать миграцию между клиентами и клиентами Microsoft 365 и действиями по переносу.</span><span class="sxs-lookup"><span data-stu-id="d59c4-106">Use the [Tenant-to-tenant migration architecture model](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="d59c4-107">[![Модель миграции "клиент — клиент"](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="d59c4-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="d59c4-108">Вы также можете скачать эту модель в форматах [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) или [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) и распечатать ее на бумаге размера Letter, Legal или таблоид (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="d59c4-108">You can also download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) or [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="d59c4-109">Эта модель предоставляет рекомендации и начальные точки для планирования с разделами по следующим вопросам:</span><span class="sxs-lookup"><span data-stu-id="d59c4-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="d59c4-110">Сопоставление бизнес-сценариев с подходами архитектуры</span><span class="sxs-lookup"><span data-stu-id="d59c4-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="d59c4-111">Особенности дизайна</span><span class="sxs-lookup"><span data-stu-id="d59c4-111">Design considerations</span></span>

<span data-ttu-id="d59c4-112">Эта модель также содержит подробные примеры:</span><span class="sxs-lookup"><span data-stu-id="d59c4-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="d59c4-113">Поток миграции одного события</span><span class="sxs-lookup"><span data-stu-id="d59c4-113">A single event migration flow</span></span>
- <span data-ttu-id="d59c4-114">Поэтапный процесс миграции</span><span class="sxs-lookup"><span data-stu-id="d59c4-114">A phased migration flow</span></span>
- <span data-ttu-id="d59c4-115">Перемещение или разбиение клиента</span><span class="sxs-lookup"><span data-stu-id="d59c4-115">A tenant move or split flow</span></span>
