---
title: Получить релевантные сведения об объекте с помощью охоты
description: Узнайте, как использовать средство охоты go для быстрого запроса соответствующих сведений об объекте или событии с помощью продвинутой охоты.
keywords: advanced hunting, incident, pivot, entity, go hunt, relevant events, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft 365 Defender
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
ms.openlocfilehash: a78f37d8c1fed1063095e25f19136f0362f17db7
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952660"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="708b3-104">Быстрая охота за сведениями о сущности или событиях с помощью go hunt</span><span class="sxs-lookup"><span data-stu-id="708b3-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="708b3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="708b3-105">**Applies to:**</span></span>
- <span data-ttu-id="708b3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="708b3-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="708b3-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="708b3-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="708b3-108">С помощью *действия go hunt* можно быстро исследовать события и различные типы сущности с помощью мощных расширенных возможностей охоты на основе запросов. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="708b3-108">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="708b3-109">Это действие автоматически запускает расширенный запрос на поиск соответствующих сведений о выбранном событии или объекте.</span><span class="sxs-lookup"><span data-stu-id="708b3-109">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="708b3-110">Действие *охоты на перейти* доступно в различных разделах центра безопасности всякий раз, когда отображаются сведения о событии или объекте.</span><span class="sxs-lookup"><span data-stu-id="708b3-110">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="708b3-111">Например, можно использовать go *hunt* из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="708b3-111">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="708b3-112">На странице [инцидента](investigate-incidents.md#summary)можно просмотреть сведения о пользователях, устройствах и многих других сущностях, связанных с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="708b3-112">In the [incident page](investigate-incidents.md#summary), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="708b3-113">При выборе объекта вы получаете дополнительные сведения, а также различные действия, которые можно принять для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="708b3-113">As you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="708b3-114">В приведенной ниже примере выбирается почтовый ящик, в котором отображаются сведения о почтовом ящике, а также возможность охоты за дополнительными сведениями о почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="708b3-114">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Изображение, на котором показаны сведения о почтовом ящике с помощью параметра go hunt](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="708b3-116">На странице инцидента можно также получить доступ к списку сущностям в вкладке доказательства. Выбор одного из этих сущностей позволяет быстро искать сведения об этом объекте.</span><span class="sxs-lookup"><span data-stu-id="708b3-116">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Изображение, показывающая выбранный файл с параметром go hunt на вкладке Evidence](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="708b3-118">При просмотре временной шкалы устройства можно выбрать событие в временной шкале, чтобы просмотреть дополнительные сведения об этом событии.</span><span class="sxs-lookup"><span data-stu-id="708b3-118">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="708b3-119">После выбора события вы получите возможность охотиться за другими соответствующими событиями в продвинутой охоте.</span><span class="sxs-lookup"><span data-stu-id="708b3-119">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Изображение, показывающая сведения о событии с помощью параметра "Охота на перейдите"](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="708b3-121">Выбор **перейти на охоту** или **охоту для** связанных событий передает различные запросы в зависимости от того, выбрали ли вы объект или событие.</span><span class="sxs-lookup"><span data-stu-id="708b3-121">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="708b3-122">Запрос сведений об объектах</span><span class="sxs-lookup"><span data-stu-id="708b3-122">Query for entity information</span></span>
<span data-ttu-id="708b3-123">При использовании *go hunt* для запроса сведений о пользователе, устройстве или любом другом типе сущности запрос проверяет все соответствующие таблицы схемы на наличие событий, связанных с этим объектом.</span><span class="sxs-lookup"><span data-stu-id="708b3-123">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="708b3-124">Чтобы сохранить управляемые результаты, запрос охватывает примерно тот же период времени, что и самое раннее действие за последние 30 дней, связанное с объектом и связанное с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="708b3-124">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="708b3-125">Вот пример запроса на поиск для устройства:</span><span class="sxs-lookup"><span data-stu-id="708b3-125">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="708b3-126">Поддерживаемые типы сущности</span><span class="sxs-lookup"><span data-stu-id="708b3-126">Supported entity types</span></span>
<span data-ttu-id="708b3-127">Вы можете использовать *go hunt* после выбора любого из этих типов сущности:</span><span class="sxs-lookup"><span data-stu-id="708b3-127">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="708b3-128">Файлы</span><span class="sxs-lookup"><span data-stu-id="708b3-128">Files</span></span>
- <span data-ttu-id="708b3-129">Сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="708b3-129">Emails</span></span>
- <span data-ttu-id="708b3-130">Кластеры электронной почты</span><span class="sxs-lookup"><span data-stu-id="708b3-130">Email clusters</span></span>
- <span data-ttu-id="708b3-131">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="708b3-131">Mailboxes</span></span>
- <span data-ttu-id="708b3-132">Пользователи</span><span class="sxs-lookup"><span data-stu-id="708b3-132">Users</span></span>
- <span data-ttu-id="708b3-133">Устройства</span><span class="sxs-lookup"><span data-stu-id="708b3-133">Devices</span></span>
- <span data-ttu-id="708b3-134">IP-адреса</span><span class="sxs-lookup"><span data-stu-id="708b3-134">IP addresses</span></span>
- <span data-ttu-id="708b3-135">URL-адреса</span><span class="sxs-lookup"><span data-stu-id="708b3-135">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="708b3-136">Запрос сведений о событиях</span><span class="sxs-lookup"><span data-stu-id="708b3-136">Query for event information</span></span>
<span data-ttu-id="708b3-137">При использовании *go hunt* для запроса сведений о событии временной шкалы запрос проверяет все соответствующие таблицы схемы для других событий во время выбранного события.</span><span class="sxs-lookup"><span data-stu-id="708b3-137">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="708b3-138">Например, в следующих запросах перечислены события в различных таблицах схем, которые происходили примерно в один и тот же период времени на одном устройстве:</span><span class="sxs-lookup"><span data-stu-id="708b3-138">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="708b3-139">Настройка запроса</span><span class="sxs-lookup"><span data-stu-id="708b3-139">Adjust the query</span></span>
<span data-ttu-id="708b3-140">С некоторым знанием языка [запроса](advanced-hunting-query-language.md)можно настроить запрос на свои предпочтения.</span><span class="sxs-lookup"><span data-stu-id="708b3-140">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="708b3-141">Например, можно настроить эту строку, которая определяет размер окна времени:</span><span class="sxs-lookup"><span data-stu-id="708b3-141">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="708b3-142">Помимо изменения запроса, чтобы получить более релевантные результаты, вы также можете:</span><span class="sxs-lookup"><span data-stu-id="708b3-142">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="708b3-143">Просмотр результатов в качестве диаграмм</span><span class="sxs-lookup"><span data-stu-id="708b3-143">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="708b3-144">Создание настраиваемой нормы обнаружения</span><span class="sxs-lookup"><span data-stu-id="708b3-144">Create a custom detection rule</span></span>](custom-detection-rules.md)

>[!NOTE]
><span data-ttu-id="708b3-145">Некоторые таблицы в этой статье могут быть недоступны в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="708b3-145">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="708b3-146">[Включи Microsoft 365 Defender для](m365d-enable.md) охоты на угрозы с помощью дополнительных источников данных.</span><span class="sxs-lookup"><span data-stu-id="708b3-146">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="708b3-147">Вы можете переместить расширенные процессы охоты из Microsoft Defender для конечной точки в Microsoft 365 Defender, следуя шагам в миграции расширенных запросов охоты из [Microsoft Defender для конечной](advanced-hunting-migrate-from-mde.md)точки .</span><span class="sxs-lookup"><span data-stu-id="708b3-147">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="708b3-148">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="708b3-148">Related topics</span></span>
- [<span data-ttu-id="708b3-149">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="708b3-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="708b3-150">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="708b3-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="708b3-151">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="708b3-151">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="708b3-152">Правила настраиваемого обнаружения</span><span class="sxs-lookup"><span data-stu-id="708b3-152">Custom detection rules</span></span>](custom-detection-rules.md)
