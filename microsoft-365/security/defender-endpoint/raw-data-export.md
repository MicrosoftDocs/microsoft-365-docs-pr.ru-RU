---
title: Stream Microsoft Defender for Endpoint event
description: Узнайте, как настроить Microsoft Defender для конечной точки для потоковой передачи событий advanced Hunting в концентраторы событий или учетную запись хранилища Azure
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
ms.custom: api
ms.openlocfilehash: 3e6d4df1c2c0f4934de1e8a54e8c1676aae230e3
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771631"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="c7bbc-104">Необработанные API потоковой передачи данных</span><span class="sxs-lookup"><span data-stu-id="c7bbc-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c7bbc-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c7bbc-105">**Applies to:**</span></span>
- [<span data-ttu-id="c7bbc-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c7bbc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="c7bbc-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c7bbc-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c7bbc-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c7bbc-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="c7bbc-109">Поток событий advanced Hunting в концентраторы событий и/или учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="c7bbc-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="c7bbc-110">Defender for Endpoint поддерживает потоковую трансляцию всех [](/azure/event-hubs/) событий, доступных с помощью [advanced Hunting,](advanced-hunting-overview.md) в концентраторы событий и/или учетную запись [хранилища Azure.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="c7bbc-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="c7bbc-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c7bbc-111">In this section</span></span>

<span data-ttu-id="c7bbc-112">Статья</span><span class="sxs-lookup"><span data-stu-id="c7bbc-112">Topic</span></span> | <span data-ttu-id="c7bbc-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c7bbc-113">Description</span></span>
:---|:---
[<span data-ttu-id="c7bbc-114">Поток событий Microsoft Defender для конечных точек в концентраторы событий Azure</span><span class="sxs-lookup"><span data-stu-id="c7bbc-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="c7bbc-115">Узнайте о том, как включите потоковый API в клиенте и настройте Defender для конечной точки для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в концентраторы событий.</span><span class="sxs-lookup"><span data-stu-id="c7bbc-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="c7bbc-116">Stream Defender для событий конечной точки в учетной записи хранения Azure</span><span class="sxs-lookup"><span data-stu-id="c7bbc-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="c7bbc-117">Узнайте о включите потоковый API в клиенте и настройте Defender для конечной точки для потоковой передачи [advanced Hunting](advanced-hunting-overview.md) в учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="c7bbc-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c7bbc-118">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c7bbc-118">Related topics</span></span>
- [<span data-ttu-id="c7bbc-119">Обзор расширенных охоты</span><span class="sxs-lookup"><span data-stu-id="c7bbc-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c7bbc-120">Документация по центрам событий Azure</span><span class="sxs-lookup"><span data-stu-id="c7bbc-120">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="c7bbc-121">служба хранилища Azure Документация по учетной записи</span><span class="sxs-lookup"><span data-stu-id="c7bbc-121">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)