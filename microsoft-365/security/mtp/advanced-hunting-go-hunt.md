---
title: Получить релевантную информацию об объекте с помощью go hunt
description: Узнайте, как использовать средство "go hunt on" для быстрого запроса релевантной информации об объекте или событии с помощью дополнительной охоты.
keywords: расширенный поиск, инцидент, pivot, сущность, go hunt, релевантные события, охота на угрозы, поиск, поиск, запрос, телеметрия, Microsoft 365, Защита от угроз (Майкрософт)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929515"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="8fa97-104">Быстрая поиск сведений об объектах или событиях с помощью перейти на поиск</span><span class="sxs-lookup"><span data-stu-id="8fa97-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8fa97-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8fa97-105">**Applies to:**</span></span>
- <span data-ttu-id="8fa97-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fa97-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8fa97-107">С помощью *действия «Go hunt»* вы можете быстро исследовать события и различные типы суружества, используя мощные расширенные возможности [выследавания](advanced-hunting-overview.md) на основе запросов.</span><span class="sxs-lookup"><span data-stu-id="8fa97-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="8fa97-108">Это действие автоматически выполняет запрос на расширенный поиск для поиска релевантной информации о выбранном событии или объекте.</span><span class="sxs-lookup"><span data-stu-id="8fa97-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="8fa97-109">Действие *"Go hunt"* доступно в различных разделах центра безопасности при отобратели событий или сведений об объектах.</span><span class="sxs-lookup"><span data-stu-id="8fa97-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="8fa97-110">Например, вы можете использовать *go hunt* из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="8fa97-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="8fa97-111">На странице [инцидента можно](investigate-incidents.md#incident-overview)просмотреть сведения о пользователях, устройствах и многих других организациях, связанных с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="8fa97-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="8fa97-112">При выборе сущности вы получаете дополнительные сведения, а также различные действия, которые можно принять с этой сущностью.</span><span class="sxs-lookup"><span data-stu-id="8fa97-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="8fa97-113">В примере ниже выбирается почтовый ящик, в котором отображаются сведения о почтовом ящике, а также возможность искать дополнительные сведения о почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="8fa97-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Изображение, на котором показаны сведения о почтовом ящике с параметром "Go hunt"](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="8fa97-115">На странице инцидента также можно получить доступ к списку сущностям на вкладке свидетельства. Выбор одной из этих сущностей позволяет быстро искать сведения об этом объекте.</span><span class="sxs-lookup"><span data-stu-id="8fa97-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Изображение выбранного файла с параметром "Go hunt" на вкладке "Свидетельство"](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="8fa97-117">При просмотре временной шкалы для устройства можно выбрать событие на временной шкале, чтобы просмотреть дополнительные сведения об этом событии.</span><span class="sxs-lookup"><span data-stu-id="8fa97-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="8fa97-118">После выбора события вы получаете возможность искать другие важные события в расширенных охотах.</span><span class="sxs-lookup"><span data-stu-id="8fa97-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Изображение, на котором показаны сведения о событии с параметром "Go hunt"](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="8fa97-120">При выборе **"Go hunt"** или **"Hunt"** для связанных событий проходят различные запросы в зависимости от того, выбрана ли сущность или событие.</span><span class="sxs-lookup"><span data-stu-id="8fa97-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="8fa97-121">Запрос сведений об объектах</span><span class="sxs-lookup"><span data-stu-id="8fa97-121">Query for entity information</span></span>
<span data-ttu-id="8fa97-122">При использовании *go hunt* для запроса сведений о пользователе, устройстве или любом другом типе сущности запрос проверяет все соответствующие таблицы схемы на наличие событий, связанных с этим объектом.</span><span class="sxs-lookup"><span data-stu-id="8fa97-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="8fa97-123">Для поддержания управляемости результатов областью запроса является примерно тот же период времени, что и самый ранний период активности за последние 30 дней, связанный с сущностью и связанный с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="8fa97-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="8fa97-124">Вот пример запроса на поиск по запросу go для устройства:</span><span class="sxs-lookup"><span data-stu-id="8fa97-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="8fa97-125">Поддерживаемые типы су-</span><span class="sxs-lookup"><span data-stu-id="8fa97-125">Supported entity types</span></span>
<span data-ttu-id="8fa97-126">Вы можете использовать *go hunt* после выбора любого из этих типов сущности:</span><span class="sxs-lookup"><span data-stu-id="8fa97-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="8fa97-127">Файлы</span><span class="sxs-lookup"><span data-stu-id="8fa97-127">Files</span></span>
- <span data-ttu-id="8fa97-128">Сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="8fa97-128">Emails</span></span>
- <span data-ttu-id="8fa97-129">Кластеры электронной почты</span><span class="sxs-lookup"><span data-stu-id="8fa97-129">Email clusters</span></span>
- <span data-ttu-id="8fa97-130">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="8fa97-130">Mailboxes</span></span>
- <span data-ttu-id="8fa97-131">Пользователи</span><span class="sxs-lookup"><span data-stu-id="8fa97-131">Users</span></span>
- <span data-ttu-id="8fa97-132">Устройства</span><span class="sxs-lookup"><span data-stu-id="8fa97-132">Devices</span></span>
- <span data-ttu-id="8fa97-133">IP-адреса</span><span class="sxs-lookup"><span data-stu-id="8fa97-133">IP addresses</span></span>
- <span data-ttu-id="8fa97-134">URL-адреса</span><span class="sxs-lookup"><span data-stu-id="8fa97-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="8fa97-135">Запрос сведений о событии</span><span class="sxs-lookup"><span data-stu-id="8fa97-135">Query for event information</span></span>
<span data-ttu-id="8fa97-136">При использовании *go hunt* для запроса сведений о событии временной шкалы запрос проверяет все соответствующие таблицы схемы на наличие других событий, происходящих во время выбранного события.</span><span class="sxs-lookup"><span data-stu-id="8fa97-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="8fa97-137">Например, в следующих запросах перечислены события в различных таблицах схем, которые произошли за один период времени на одном устройстве:</span><span class="sxs-lookup"><span data-stu-id="8fa97-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="8fa97-138">Настройка запроса</span><span class="sxs-lookup"><span data-stu-id="8fa97-138">Adjust the query</span></span>
<span data-ttu-id="8fa97-139">С некоторым знанием языка [запроса](advanced-hunting-query-language.md)вы можете настроить запрос в своих предпочтениях.</span><span class="sxs-lookup"><span data-stu-id="8fa97-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="8fa97-140">Например, можно настроить эту строку, которая определяет размер окне времени:</span><span class="sxs-lookup"><span data-stu-id="8fa97-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="8fa97-141">Помимо изменения запроса, чтобы получить более релевантные результаты, можно также:</span><span class="sxs-lookup"><span data-stu-id="8fa97-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="8fa97-142">Просмотр результатов в качестве диаграмм</span><span class="sxs-lookup"><span data-stu-id="8fa97-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="8fa97-143">Создание настраиваемой правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="8fa97-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="8fa97-144">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="8fa97-144">Related topics</span></span>
- [<span data-ttu-id="8fa97-145">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="8fa97-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8fa97-146">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="8fa97-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8fa97-147">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="8fa97-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="8fa97-148">Настраиваемые правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="8fa97-148">Custom detection rules</span></span>](custom-detection-rules.md)
