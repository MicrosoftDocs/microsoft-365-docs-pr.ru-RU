---
title: Функция DeviceFromIP() в продвинутой охоте для Microsoft 365 Defender
description: Узнайте, как использовать функцию DeviceFromIP() для получения устройств, которые были назначены определенному IP-адресу
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933185"
---
# <a name="devicefromip"></a><span data-ttu-id="996a5-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="996a5-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="996a5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="996a5-105">**Applies to:**</span></span>
- <span data-ttu-id="996a5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="996a5-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="996a5-107">Используйте `DeviceFromIP()` функцию [](advanced-hunting-overview.md) в расширенных запросах на охоту, чтобы быстро получить список устройств, которые были назначены определенному IP-адресу в определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="996a5-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="996a5-108">Эта функция возвращает таблицу со следующими столбцами:</span><span class="sxs-lookup"><span data-stu-id="996a5-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="996a5-109">Column</span><span class="sxs-lookup"><span data-stu-id="996a5-109">Column</span></span> | <span data-ttu-id="996a5-110">Тип данных</span><span class="sxs-lookup"><span data-stu-id="996a5-110">Data type</span></span> | <span data-ttu-id="996a5-111">Описание</span><span class="sxs-lookup"><span data-stu-id="996a5-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="996a5-112">string</span><span class="sxs-lookup"><span data-stu-id="996a5-112">string</span></span> | <span data-ttu-id="996a5-113">IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="996a5-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="996a5-114">Строка</span><span class="sxs-lookup"><span data-stu-id="996a5-114">string</span></span> | <span data-ttu-id="996a5-115">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="996a5-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="996a5-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="996a5-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="996a5-117">Аргументы</span><span class="sxs-lookup"><span data-stu-id="996a5-117">Arguments</span></span>

<span data-ttu-id="996a5-118">Эта функция вызывается в рамках запроса.</span><span class="sxs-lookup"><span data-stu-id="996a5-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="996a5-119">**x**— первый параметр обычно уже является столбцом в запросе.</span><span class="sxs-lookup"><span data-stu-id="996a5-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="996a5-120">В этом случае это столбец с именем , IP-адрес, для которого необходимо увидеть список устройств, которые были назначены `IP` ему.</span><span class="sxs-lookup"><span data-stu-id="996a5-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="996a5-121">Это должен быть локальный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="996a5-121">It should be a local IP address.</span></span> <span data-ttu-id="996a5-122">Внешние IP-адреса не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="996a5-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="996a5-123">**y**— второй необязательный параметр — это параметр, который предписывает функции получать самые последние назначенные `Timestamp` устройства в определенное время.</span><span class="sxs-lookup"><span data-stu-id="996a5-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="996a5-124">Если не указано, функция возвращает последние доступные записи.</span><span class="sxs-lookup"><span data-stu-id="996a5-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="996a5-125">Пример</span><span class="sxs-lookup"><span data-stu-id="996a5-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="996a5-126">Получите новейшие устройства, которые были назначены определенным IP-адресам</span><span class="sxs-lookup"><span data-stu-id="996a5-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="996a5-127">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="996a5-127">Related topics</span></span>
- [<span data-ttu-id="996a5-128">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="996a5-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="996a5-129">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="996a5-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="996a5-130">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="996a5-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
