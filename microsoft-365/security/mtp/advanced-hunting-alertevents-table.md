---
title: Таблица AlertEvents в схеме расширенной охоты
description: Сведения о событиях создания оповещений в таблице AlertEvents схемы расширенной охоты
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, алертевентс, предупреждение, серьезность, Категория
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9f341705d8247183b7e8a5271231c82faf8b386a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235098"
---
# <a name="alertevents"></a><span data-ttu-id="0fd43-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="0fd43-104">AlertEvents</span></span>

<span data-ttu-id="0fd43-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0fd43-105">**Applies to:**</span></span>
- <span data-ttu-id="0fd43-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="0fd43-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="0fd43-107">В таблице `AlertEvents` схемы [расширенной охоты](advanced-hunting-overview.md) содержится информация об оповещениях ATP в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0fd43-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="0fd43-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="0fd43-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0fd43-109">Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0fd43-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0fd43-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="0fd43-110">Column name</span></span> | <span data-ttu-id="0fd43-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0fd43-111">Data type</span></span> | <span data-ttu-id="0fd43-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd43-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="0fd43-113">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-113">string</span></span> | <span data-ttu-id="0fd43-114">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="0fd43-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="0fd43-115">datetime</span><span class="sxs-lookup"><span data-stu-id="0fd43-115">datetime</span></span> | <span data-ttu-id="0fd43-116">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="0fd43-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0fd43-117">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-117">string</span></span> | <span data-ttu-id="0fd43-118">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="0fd43-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0fd43-119">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-119">string</span></span> | <span data-ttu-id="0fd43-120">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="0fd43-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="0fd43-121">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-121">string</span></span> | <span data-ttu-id="0fd43-122">Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="0fd43-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="0fd43-123">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-123">string</span></span> | <span data-ttu-id="0fd43-124">Тип индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="0fd43-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="0fd43-125">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-125">string</span></span> | <span data-ttu-id="0fd43-126">Название оповещения</span><span class="sxs-lookup"><span data-stu-id="0fd43-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="0fd43-127">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-127">string</span></span> | <span data-ttu-id="0fd43-128">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="0fd43-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="0fd43-129">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-129">string</span></span> | <span data-ttu-id="0fd43-130">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="0fd43-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="0fd43-131">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-131">string</span></span> | <span data-ttu-id="0fd43-132">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="0fd43-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="0fd43-133">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-133">string</span></span> | <span data-ttu-id="0fd43-134">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="0fd43-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="0fd43-135">long</span><span class="sxs-lookup"><span data-stu-id="0fd43-135">long</span></span> | <span data-ttu-id="0fd43-136">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="0fd43-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0fd43-137">Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp</span><span class="sxs-lookup"><span data-stu-id="0fd43-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="0fd43-138">string</span><span class="sxs-lookup"><span data-stu-id="0fd43-138">string</span></span> | <span data-ttu-id="0fd43-139">Таблица, содержащая сведения о событии</span><span class="sxs-lookup"><span data-stu-id="0fd43-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0fd43-140">См. также</span><span class="sxs-lookup"><span data-stu-id="0fd43-140">Related topics</span></span>
- [<span data-ttu-id="0fd43-141">Профилактическая охота на угрозы</span><span class="sxs-lookup"><span data-stu-id="0fd43-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0fd43-142">Сведения о языке запросов</span><span class="sxs-lookup"><span data-stu-id="0fd43-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0fd43-143">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="0fd43-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0fd43-144">Охота на угрозы в электронной почте и устройствах</span><span class="sxs-lookup"><span data-stu-id="0fd43-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0fd43-145">Общие сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="0fd43-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0fd43-146">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="0fd43-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
