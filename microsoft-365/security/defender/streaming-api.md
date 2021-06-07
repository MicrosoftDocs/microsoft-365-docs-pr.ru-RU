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
ms.openlocfilehash: 21a83c4876a90a231eb2a78d10a290be2dca2fa0
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782487"
---
# <a name="streaming-api"></a><span data-ttu-id="ce28f-104">Потоковый API</span><span class="sxs-lookup"><span data-stu-id="ce28f-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ce28f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ce28f-105">**Applies to:**</span></span>
- [<span data-ttu-id="ce28f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce28f-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="ce28f-107">Поток событий advanced Hunting в концентраторы событий и/или учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="ce28f-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="ce28f-108">Microsoft 365 Defender поддерживает потоковую трансляцию событий с помощью [advanced Hunting](../defender/advanced-hunting-overview.md) в [концентраторы](/azure/event-hubs/) событий и/или учетную запись [хранения Azure.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="ce28f-108">Microsoft 365 Defender supports streaming events through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="ce28f-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ce28f-109">In this section</span></span>

<span data-ttu-id="ce28f-110">Статья</span><span class="sxs-lookup"><span data-stu-id="ce28f-110">Topic</span></span> | <span data-ttu-id="ce28f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ce28f-111">Description</span></span>
:---|:---
[<span data-ttu-id="ce28f-112">Поток событий в концентраторы событий Azure</span><span class="sxs-lookup"><span data-stu-id="ce28f-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="ce28f-113">Узнайте о том, как включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="ce28f-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="ce28f-114">Поток событий в учетную запись хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="ce28f-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="ce28f-115">Узнайте о включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="ce28f-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ce28f-116">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ce28f-116">Related topics</span></span>
- [<span data-ttu-id="ce28f-117">Обзор расширенных охоты</span><span class="sxs-lookup"><span data-stu-id="ce28f-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="ce28f-118">Документация по центрам событий Azure</span><span class="sxs-lookup"><span data-stu-id="ce28f-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="ce28f-119">служба хранилища Azure Документация по учетной записи</span><span class="sxs-lookup"><span data-stu-id="ce28f-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
