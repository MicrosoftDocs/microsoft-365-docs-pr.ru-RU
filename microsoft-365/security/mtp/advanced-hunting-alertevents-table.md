---
title: Таблица AlertEvents в схеме расширенной охоты
description: Сведения о событиях создания оповещений в таблице AlertEvents схемы расширенной охоты
keywords: расширенная охота, охота на угрозы, охота на киберугрозы, поиск, запрос, телеметрия, справочник схемы, kusto, таблица, столбец, тип данных, описание, события оповещений, оповещение, серьезность, категория
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911539"
---
# <a name="alertevents"></a><span data-ttu-id="06640-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="06640-104">AlertEvents</span></span>

<span data-ttu-id="06640-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="06640-105">**Applies to:**</span></span>
- <span data-ttu-id="06640-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="06640-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="06640-107">В таблице `AlertEvents` схемы [расширенной охоты](advanced-hunting-overview.md) содержится информация об оповещениях ATP в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="06640-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="06640-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="06640-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="06640-109">Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="06640-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="06640-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="06640-110">Column name</span></span> | <span data-ttu-id="06640-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="06640-111">Data type</span></span> | <span data-ttu-id="06640-112">Описание</span><span class="sxs-lookup"><span data-stu-id="06640-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="06640-113">string</span><span class="sxs-lookup"><span data-stu-id="06640-113">string</span></span> | <span data-ttu-id="06640-114">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="06640-114">Unique identifier for the bucket.</span></span> |
| `EventTime` | <span data-ttu-id="06640-115">datetime</span><span class="sxs-lookup"><span data-stu-id="06640-115">dateTime</span></span> | <span data-ttu-id="06640-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="06640-116">Date and time the report was recorded.</span></span> |
| `MachineId` | <span data-ttu-id="06640-117">string</span><span class="sxs-lookup"><span data-stu-id="06640-117">string</span></span> | <span data-ttu-id="06640-118">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="06640-118">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="06640-119">string</span><span class="sxs-lookup"><span data-stu-id="06640-119">string</span></span> | <span data-ttu-id="06640-120">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="06640-120">Fully qualified domain name (FQDN) of the pool</span></span> |
| `Severity` | <span data-ttu-id="06640-121">string</span><span class="sxs-lookup"><span data-stu-id="06640-121">string</span></span> | <span data-ttu-id="06640-122">Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="06640-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="06640-123">string</span><span class="sxs-lookup"><span data-stu-id="06640-123">string</span></span> | <span data-ttu-id="06640-124">Тип индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="06640-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="06640-125">string</span><span class="sxs-lookup"><span data-stu-id="06640-125">string</span></span> | <span data-ttu-id="06640-126">Название оповещения</span><span class="sxs-lookup"><span data-stu-id="06640-126">Title of the alert.</span></span> |
| `FileName` | <span data-ttu-id="06640-127">string</span><span class="sxs-lookup"><span data-stu-id="06640-127">string</span></span> | <span data-ttu-id="06640-128">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="06640-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="06640-129">string</span><span class="sxs-lookup"><span data-stu-id="06640-129">string</span></span> | <span data-ttu-id="06640-130">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="06640-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="06640-131">string</span><span class="sxs-lookup"><span data-stu-id="06640-131">string</span></span> | <span data-ttu-id="06640-132">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="06640-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="06640-133">string</span><span class="sxs-lookup"><span data-stu-id="06640-133">string</span></span> | <span data-ttu-id="06640-134">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="06640-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="06640-135">long</span><span class="sxs-lookup"><span data-stu-id="06640-135">long</span></span> | <span data-ttu-id="06640-136">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="06640-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="06640-137">Чтобы определить уникальные события, этот столбец требуется использовать в сочетании со столбцами ComputerName и EventTime</span><span class="sxs-lookup"><span data-stu-id="06640-137">To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns</span></span> |
| `Table` | <span data-ttu-id="06640-138">string</span><span class="sxs-lookup"><span data-stu-id="06640-138">string</span></span> | <span data-ttu-id="06640-139">Таблица, содержащая сведения о событии</span><span class="sxs-lookup"><span data-stu-id="06640-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="06640-140">См. также</span><span class="sxs-lookup"><span data-stu-id="06640-140">Related topics</span></span>
- [<span data-ttu-id="06640-141">Профилактическая охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="06640-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="06640-142">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="06640-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="06640-143">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="06640-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="06640-144">Охота на угрозы в электронной почте и устройствах</span><span class="sxs-lookup"><span data-stu-id="06640-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="06640-145">Общие сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="06640-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="06640-146">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="06640-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
