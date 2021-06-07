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
ms.openlocfilehash: fad3dd64c9acf079bd8da778d417240c44031569
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772534"
---
# <a name="streaming-api"></a><span data-ttu-id="3d9d6-104">Потоковый API</span><span class="sxs-lookup"><span data-stu-id="3d9d6-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3d9d6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3d9d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="3d9d6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d9d6-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="3d9d6-107">Поток событий advanced Hunting в концентраторы событий и/или учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="3d9d6-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="3d9d6-108">Microsoft 365 Defender поддерживает потоковую передачу всех событий, доступных с помощью [Advanced Hunting,](../defender/advanced-hunting-overview.md) в учетную запись хранилища [Event Hubs](/azure/event-hubs/) и/или [Azure.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="3d9d6-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="3d9d6-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3d9d6-109">In this section</span></span>

<span data-ttu-id="3d9d6-110">Статья</span><span class="sxs-lookup"><span data-stu-id="3d9d6-110">Topic</span></span> | <span data-ttu-id="3d9d6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="3d9d6-111">Description</span></span>
:---|:---
[<span data-ttu-id="3d9d6-112">Поток событий в концентраторы событий Azure</span><span class="sxs-lookup"><span data-stu-id="3d9d6-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="3d9d6-113">Узнайте о том, как включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="3d9d6-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="3d9d6-114">Поток событий в учетную запись хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="3d9d6-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="3d9d6-115">Узнайте о включите потоковый API в клиенте и настройте Microsoft 365 Defender для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="3d9d6-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3d9d6-116">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3d9d6-116">Related topics</span></span>
- [<span data-ttu-id="3d9d6-117">Обзор расширенных охоты</span><span class="sxs-lookup"><span data-stu-id="3d9d6-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="3d9d6-118">Документация по центрам событий Azure</span><span class="sxs-lookup"><span data-stu-id="3d9d6-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="3d9d6-119">служба хранилища Azure Документация по учетной записи</span><span class="sxs-lookup"><span data-stu-id="3d9d6-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
