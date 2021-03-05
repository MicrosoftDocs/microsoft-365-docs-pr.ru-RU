---
title: Миграции от клиента к клиенту Microsoft 365
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
description: Узнайте, как перенести клиентов Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 09b2bc77333afaf1991064369846241328db85ff
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461647"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="1a9aa-103">Миграции от клиента к клиенту Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a9aa-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="1a9aa-104">Существует несколько подходов к архитектуре для слияний, приобретений, отгрузок и других сценариев, которые могут привести к переносу существующего клиента Microsoft 365 в нового клиента.</span><span class="sxs-lookup"><span data-stu-id="1a9aa-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="1a9aa-105">Большинство клиентов работают с службами Microsoft Consulting Services или партнером Майкрософт для миграции клиентов, в том числе с помощью сторонних средств для переноса контента.</span><span class="sxs-lookup"><span data-stu-id="1a9aa-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="1a9aa-106">Используйте модель [архитектуры](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) миграции от клиента к арендатору, чтобы понять, как планировать миграции клиента от клиента к клиенту Microsoft 365 и этапы миграции.</span><span class="sxs-lookup"><span data-stu-id="1a9aa-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="1a9aa-107">[![Модель миграции от клиента к арендатору](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="1a9aa-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="1a9aa-108">Вы скачиваете эту модель в [формате PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) и напечатаете ее на бумаге размера буквы, юридической или таблоиды (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="1a9aa-108">You download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="1a9aa-109">Эта модель предоставляет рекомендации и отправную точку для планирования с разделами на:</span><span class="sxs-lookup"><span data-stu-id="1a9aa-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="1a9aa-110">Сопоставление бизнес-сценариев с подходами к архитектуре</span><span class="sxs-lookup"><span data-stu-id="1a9aa-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="1a9aa-111">Особенности дизайна</span><span class="sxs-lookup"><span data-stu-id="1a9aa-111">Design considerations</span></span>

<span data-ttu-id="1a9aa-112">Эта модель также содержит подробные примеры:</span><span class="sxs-lookup"><span data-stu-id="1a9aa-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="1a9aa-113">Миграция одного события</span><span class="sxs-lookup"><span data-stu-id="1a9aa-113">A single event migration flow</span></span>
- <span data-ttu-id="1a9aa-114">Поэтапный миграционный поток</span><span class="sxs-lookup"><span data-stu-id="1a9aa-114">A phased migration flow</span></span>
- <span data-ttu-id="1a9aa-115">Перемещение или разделение потока клиента</span><span class="sxs-lookup"><span data-stu-id="1a9aa-115">A tenant move or split flow</span></span>
