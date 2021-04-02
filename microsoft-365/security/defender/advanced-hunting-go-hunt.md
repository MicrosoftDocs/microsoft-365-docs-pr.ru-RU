---
title: Получить релевантные сведения об объекте с помощью охоты
description: Узнайте, как использовать средство охоты go для быстрого запроса соответствующих сведений об объекте или событии с помощью продвинутой охоты.
keywords: продвинутая охота, инцидент, поворот, сущность, go hunt, релевантные события, охота на угрозы, охота на киберугрозы, поиск, запрос, телеметрия, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 392db06aa517e3e970f85ccc971c3a6a6bc6e548
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498291"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="a4758-104">Быстрая охота за сведениями о сущности или событиях с помощью go hunt</span><span class="sxs-lookup"><span data-stu-id="a4758-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a4758-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a4758-105">**Applies to:**</span></span>
- <span data-ttu-id="a4758-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4758-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a4758-107">С помощью *действия go hunt* можно быстро исследовать события и различные типы сущности с помощью мощных расширенных возможностей охоты на основе запросов. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a4758-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="a4758-108">Это действие автоматически запускает расширенный запрос на поиск соответствующих сведений о выбранном событии или объекте.</span><span class="sxs-lookup"><span data-stu-id="a4758-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="a4758-109">Действие *охоты на перейти* доступно в различных разделах центра безопасности всякий раз, когда отображаются сведения о событии или объекте.</span><span class="sxs-lookup"><span data-stu-id="a4758-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="a4758-110">Например, можно использовать go *hunt* из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="a4758-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="a4758-111">На странице [инцидента](investigate-incidents.md#incident-overview)можно просмотреть сведения о пользователях, устройствах и многих других сущностях, связанных с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="a4758-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="a4758-112">При выборе объекта вы получаете дополнительные сведения, а также различные действия, которые можно принять для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="a4758-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="a4758-113">В приведенной ниже примере выбирается почтовый ящик, в котором отображаются сведения о почтовом ящике, а также возможность охоты за дополнительными сведениями о почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="a4758-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Изображение, на котором показаны сведения о почтовом ящике с помощью параметра go hunt](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="a4758-115">На странице инцидента можно также получить доступ к списку сущностям в вкладке доказательства. Выбор одного из этих сущностей позволяет быстро искать сведения об этом объекте.</span><span class="sxs-lookup"><span data-stu-id="a4758-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Изображение, показывающая выбранный файл с параметром go hunt на вкладке Evidence](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="a4758-117">При просмотре временной шкалы устройства можно выбрать событие в временной шкале, чтобы просмотреть дополнительные сведения об этом событии.</span><span class="sxs-lookup"><span data-stu-id="a4758-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="a4758-118">После выбора события вы получите возможность охотиться за другими соответствующими событиями в продвинутой охоте.</span><span class="sxs-lookup"><span data-stu-id="a4758-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Изображение, показывающая сведения о событии с помощью параметра "Охота на перейдите"](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="a4758-120">Выбор **перейти на охоту** или **охоту для** связанных событий передает различные запросы в зависимости от того, выбрали ли вы объект или событие.</span><span class="sxs-lookup"><span data-stu-id="a4758-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="a4758-121">Запрос сведений об объектах</span><span class="sxs-lookup"><span data-stu-id="a4758-121">Query for entity information</span></span>
<span data-ttu-id="a4758-122">При использовании *go hunt* для запроса сведений о пользователе, устройстве или любом другом типе сущности запрос проверяет все соответствующие таблицы схемы на наличие событий, связанных с этим объектом.</span><span class="sxs-lookup"><span data-stu-id="a4758-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="a4758-123">Чтобы сохранить управляемые результаты, запрос охватывает примерно тот же период времени, что и самое раннее действие за последние 30 дней, связанное с объектом и связанное с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="a4758-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="a4758-124">Вот пример запроса на поиск для устройства:</span><span class="sxs-lookup"><span data-stu-id="a4758-124">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a><span data-ttu-id="a4758-125">Поддерживаемые типы сущности</span><span class="sxs-lookup"><span data-stu-id="a4758-125">Supported entity types</span></span>
<span data-ttu-id="a4758-126">Вы можете использовать *go hunt* после выбора любого из этих типов сущности:</span><span class="sxs-lookup"><span data-stu-id="a4758-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="a4758-127">Файлы</span><span class="sxs-lookup"><span data-stu-id="a4758-127">Files</span></span>
- <span data-ttu-id="a4758-128">Сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="a4758-128">Emails</span></span>
- <span data-ttu-id="a4758-129">Кластеры электронной почты</span><span class="sxs-lookup"><span data-stu-id="a4758-129">Email clusters</span></span>
- <span data-ttu-id="a4758-130">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="a4758-130">Mailboxes</span></span>
- <span data-ttu-id="a4758-131">Пользователи</span><span class="sxs-lookup"><span data-stu-id="a4758-131">Users</span></span>
- <span data-ttu-id="a4758-132">Устройства</span><span class="sxs-lookup"><span data-stu-id="a4758-132">Devices</span></span>
- <span data-ttu-id="a4758-133">IP-адреса</span><span class="sxs-lookup"><span data-stu-id="a4758-133">IP addresses</span></span>
- <span data-ttu-id="a4758-134">URL-адреса</span><span class="sxs-lookup"><span data-stu-id="a4758-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="a4758-135">Запрос сведений о событиях</span><span class="sxs-lookup"><span data-stu-id="a4758-135">Query for event information</span></span>
<span data-ttu-id="a4758-136">При использовании *go hunt* для запроса сведений о событии временной шкалы запрос проверяет все соответствующие таблицы схемы для других событий во время выбранного события.</span><span class="sxs-lookup"><span data-stu-id="a4758-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="a4758-137">Например, в следующих запросах перечислены события в различных таблицах схем, которые происходили примерно в один и тот же период времени на одном устройстве:</span><span class="sxs-lookup"><span data-stu-id="a4758-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="a4758-138">Настройка запроса</span><span class="sxs-lookup"><span data-stu-id="a4758-138">Adjust the query</span></span>
<span data-ttu-id="a4758-139">С некоторым знанием языка [запроса](advanced-hunting-query-language.md)можно настроить запрос на свои предпочтения.</span><span class="sxs-lookup"><span data-stu-id="a4758-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="a4758-140">Например, можно настроить эту строку, которая определяет размер окна времени:</span><span class="sxs-lookup"><span data-stu-id="a4758-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="a4758-141">Помимо изменения запроса, чтобы получить более релевантные результаты, вы также можете:</span><span class="sxs-lookup"><span data-stu-id="a4758-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="a4758-142">Просмотр результатов в качестве диаграмм</span><span class="sxs-lookup"><span data-stu-id="a4758-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="a4758-143">Создание настраиваемой нормы обнаружения</span><span class="sxs-lookup"><span data-stu-id="a4758-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="a4758-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a4758-144">Related topics</span></span>
- [<span data-ttu-id="a4758-145">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="a4758-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a4758-146">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="a4758-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a4758-147">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="a4758-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="a4758-148">Правила настраиваемого обнаружения</span><span class="sxs-lookup"><span data-stu-id="a4758-148">Custom detection rules</span></span>](custom-detection-rules.md)
