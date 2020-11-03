---
title: Получение релевантных сведений об объекте с помощью слежения за Go
description: Узнайте, как использовать средство "Поиск", чтобы быстро запросить релевантные сведения о сущности или событии с помощью расширенного поиска.
keywords: Расширенный поиск, инцидент, сведение, объект, отслеживание, релевантные события, Поиск угроз, Поиск угроз кибератак, поиск, запрос, телеметрии, Microsoft 365, защита от угроз Майкрософт
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9ddad74d179ac16a25640e2bdf4ed4906f920102
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846884"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="fc3a2-104">Быстрый поиск сведений об объекте или событии с помощью службы поиска Go</span><span class="sxs-lookup"><span data-stu-id="fc3a2-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fc3a2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fc3a2-105">**Applies to:**</span></span>
- <span data-ttu-id="fc3a2-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc3a2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fc3a2-107">С помощью действия *"Go Go* " можно быстро исследовать события и различные типы сущностей с помощью мощных [расширенных](advanced-hunting-overview.md) возможностей поиска на основе запросов.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="fc3a2-108">Это действие автоматически запускает Расширенный запрос поиска для поиска релевантных сведений о выбранном событии или сущности.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="fc3a2-109">Действие по восвыполнению *Go* доступно в различных разделах центра безопасности, когда отображаются сведения о событиях или объектах.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="fc3a2-110">Например, можно использовать *слежение* за следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="fc3a2-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="fc3a2-111">На [странице инцидент](investigate-incidents.md#incident-overview)можно просмотреть сведения о пользователях, устройствах и многих других сущностях, связанных с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="fc3a2-112">При выборе объекта вы получаете дополнительные сведения, а также различные действия, которые можно выполнять с ентитити.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="fc3a2-113">В приведенном ниже примере выбирается почтовый ящик, в котором содержатся сведения о почтовом ящике, а также возможность поиска для получения дополнительных сведений о почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Изображение, содержащее сведения о почтовом ящике с параметром "Go"](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="fc3a2-115">На странице инцидент можно также получить доступ к списку сущностей на вкладке свидетельство. Выбор одной из этих сущностей предоставляет возможность быстрого поиска сведений об этой сущности.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Изображение, в котором показан выбранный файл с параметром "Go Go" на вкладке "свидетельство"](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="fc3a2-117">При просмотре временной шкалы для устройства можно выбрать событие на временной шкале, чтобы просмотреть дополнительные сведения об этом событии.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="fc3a2-118">После выбора события вы получаете возможность поиска других важных событий в разделе Advanced поиске.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Изображение, в котором показаны сведения о событиях с параметром "Go"](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="fc3a2-120">Выбор команды **"перейти" или "Поиск"** **для связанных событий** передает различные запросы в зависимости от того, выбрана сущность или событие.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="fc3a2-121">Запрос сведений об объекте</span><span class="sxs-lookup"><span data-stu-id="fc3a2-121">Query for entity information</span></span>
<span data-ttu-id="fc3a2-122">При использовании команды *Go* для получения сведений о пользователях, устройствах и других типах сущностей запрос проверяет все релевантные таблицы схемы для всех событий, содержащих эту сущность.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="fc3a2-123">Чтобы обеспечить управляемость результатов, запрос ограничивается до того же периода времени, что и самое раннее действие за прошедшие 30 дней, включающее сущность и связанное с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="fc3a2-124">Ниже приведен пример запроса на перезапись для устройства.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="fc3a2-125">Поддерживаемые типы объектов</span><span class="sxs-lookup"><span data-stu-id="fc3a2-125">Supported entity types</span></span>
<span data-ttu-id="fc3a2-126">С помощью команды *"слежение"* можно использовать следующие типы сущностей:</span><span class="sxs-lookup"><span data-stu-id="fc3a2-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="fc3a2-127">Файлы</span><span class="sxs-lookup"><span data-stu-id="fc3a2-127">Files</span></span>
- <span data-ttu-id="fc3a2-128">Сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="fc3a2-128">Emails</span></span>
- <span data-ttu-id="fc3a2-129">Кластеры электронной почты</span><span class="sxs-lookup"><span data-stu-id="fc3a2-129">Email clusters</span></span>
- <span data-ttu-id="fc3a2-130">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="fc3a2-130">Mailboxes</span></span>
- <span data-ttu-id="fc3a2-131">Пользователи</span><span class="sxs-lookup"><span data-stu-id="fc3a2-131">Users</span></span>
- <span data-ttu-id="fc3a2-132">Устройства</span><span class="sxs-lookup"><span data-stu-id="fc3a2-132">Devices</span></span>
- <span data-ttu-id="fc3a2-133">IP-адреса</span><span class="sxs-lookup"><span data-stu-id="fc3a2-133">IP addresses</span></span>
- <span data-ttu-id="fc3a2-134">URL-адреса</span><span class="sxs-lookup"><span data-stu-id="fc3a2-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="fc3a2-135">Запрос сведений о событиях</span><span class="sxs-lookup"><span data-stu-id="fc3a2-135">Query for event information</span></span>
<span data-ttu-id="fc3a2-136">При использовании команды *Go* для получения сведений о событии временной шкалы запрос проверяет все релевантные таблицы схемы для других событий во время выбранного события.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="fc3a2-137">Например, следующий запрос перечисляет события в различных таблицах схемы, которые выполнялись за один и тот же период времени, на одном устройстве:</span><span class="sxs-lookup"><span data-stu-id="fc3a2-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="fc3a2-138">Изменение запроса</span><span class="sxs-lookup"><span data-stu-id="fc3a2-138">Adjust the query</span></span>
<span data-ttu-id="fc3a2-139">С некоторыми знаниями [языка запросов](advanced-hunting-query-language.md), вы можете скорректировать запрос на свой выбор.</span><span class="sxs-lookup"><span data-stu-id="fc3a2-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="fc3a2-140">Например, вы можете скорректировать эту строку, которая определяет размер временного интервала:</span><span class="sxs-lookup"><span data-stu-id="fc3a2-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="fc3a2-141">Кроме изменения запроса для получения более релевантных результатов, можно также выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fc3a2-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="fc3a2-142">Просмотр результатов в виде диаграмм</span><span class="sxs-lookup"><span data-stu-id="fc3a2-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="fc3a2-143">Создание настраиваемого правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="fc3a2-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="fc3a2-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fc3a2-144">Related topics</span></span>
- [<span data-ttu-id="fc3a2-145">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="fc3a2-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fc3a2-146">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="fc3a2-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fc3a2-147">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="fc3a2-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="fc3a2-148">Настраиваемые правила обнаружения</span><span class="sxs-lookup"><span data-stu-id="fc3a2-148">Custom detection rules</span></span>](custom-detection-rules.md)
