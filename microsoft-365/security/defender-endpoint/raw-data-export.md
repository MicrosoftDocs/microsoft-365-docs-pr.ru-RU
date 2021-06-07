---
title: События Microsoft 365 Defender
description: Узнайте, как настроить Microsoft 365 Defender для потоковой передачи событий advanced Hunting в центры событий или учетную запись хранения Azure
keywords: экспорт необработанных данных, потоковый API, API, концентраторы событий, хранилище Azure, учетная запись хранилища, расширенный доступ к данным, обмен необработанные данные
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778201"
---
# <a name="streaming-api"></a><span data-ttu-id="18d01-104">Потоковый API</span><span class="sxs-lookup"><span data-stu-id="18d01-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="18d01-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="18d01-105">**Applies to:**</span></span>
- [<span data-ttu-id="18d01-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18d01-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="18d01-107">Поток событий advanced Hunting в концентраторы событий и/или учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="18d01-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="18d01-108">Microsoft 365 Defender поддерживает потоковую передачу всех событий, доступных с помощью [Advanced Hunting,](../defender/advanced-hunting-overview.md) в учетную запись хранилища [Event Hubs](/azure/event-hubs/) и/или [Azure.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="18d01-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="18d01-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="18d01-109">In this section</span></span>

<span data-ttu-id="18d01-110">Статья</span><span class="sxs-lookup"><span data-stu-id="18d01-110">Topic</span></span> | <span data-ttu-id="18d01-111">Описание</span><span class="sxs-lookup"><span data-stu-id="18d01-111">Description</span></span>
:---|:---
[<span data-ttu-id="18d01-112">Поток событий в концентраторы событий Azure</span><span class="sxs-lookup"><span data-stu-id="18d01-112">Stream events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="18d01-113">Узнайте о том, как включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="18d01-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="18d01-114">Поток событий в учетную запись хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="18d01-114">Stream events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="18d01-115">Узнайте о включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](../defender/advanced-hunting-overview.md) в учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="18d01-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="18d01-116">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="18d01-116">Related topics</span></span>
- [<span data-ttu-id="18d01-117">Обзор расширенных охоты</span><span class="sxs-lookup"><span data-stu-id="18d01-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="18d01-118">Документация по центрам событий Azure</span><span class="sxs-lookup"><span data-stu-id="18d01-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="18d01-119">служба хранилища Azure Документация по учетной записи</span><span class="sxs-lookup"><span data-stu-id="18d01-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
