---
title: Таблица DeviceAlertEvents в продвинутой схеме охоты
description: Узнайте о событиях генерации оповещений в таблице DeviceAlertEvents продвинутой схемы охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, DeviceAlertEvents, alert, severity, category
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: c22e4b754f9d28156c3d26c567581572e59d718d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072429"
---
# <a name="devicealertevents"></a><span data-ttu-id="9060a-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="9060a-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9060a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9060a-105">**Applies to:**</span></span>
- [<span data-ttu-id="9060a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9060a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="9060a-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9060a-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9060a-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9060a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="9060a-109">Таблица `DeviceAlertEvents` в [продвинутой схеме охоты](advanced-hunting-overview.md) содержит сведения о оповещениях в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9060a-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="9060a-110">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="9060a-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9060a-111">Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="9060a-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="9060a-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="9060a-112">Column name</span></span> | <span data-ttu-id="9060a-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9060a-113">Data type</span></span> | <span data-ttu-id="9060a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9060a-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="9060a-115">string</span><span class="sxs-lookup"><span data-stu-id="9060a-115">string</span></span> | <span data-ttu-id="9060a-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="9060a-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="9060a-117">datetime</span><span class="sxs-lookup"><span data-stu-id="9060a-117">datetime</span></span> | <span data-ttu-id="9060a-118">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="9060a-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="9060a-119">string</span><span class="sxs-lookup"><span data-stu-id="9060a-119">string</span></span> | <span data-ttu-id="9060a-120">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="9060a-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9060a-121">строка</span><span class="sxs-lookup"><span data-stu-id="9060a-121">string</span></span> | <span data-ttu-id="9060a-122">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="9060a-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="9060a-123">string</span><span class="sxs-lookup"><span data-stu-id="9060a-123">string</span></span> | <span data-ttu-id="9060a-124">Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="9060a-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="9060a-125">string</span><span class="sxs-lookup"><span data-stu-id="9060a-125">string</span></span> | <span data-ttu-id="9060a-126">Тип индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="9060a-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="9060a-127">string</span><span class="sxs-lookup"><span data-stu-id="9060a-127">string</span></span> | <span data-ttu-id="9060a-128">Название оповещения</span><span class="sxs-lookup"><span data-stu-id="9060a-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="9060a-129">string</span><span class="sxs-lookup"><span data-stu-id="9060a-129">string</span></span> | <span data-ttu-id="9060a-130">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="9060a-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="9060a-131">string</span><span class="sxs-lookup"><span data-stu-id="9060a-131">string</span></span> | <span data-ttu-id="9060a-132">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="9060a-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="9060a-133">string</span><span class="sxs-lookup"><span data-stu-id="9060a-133">string</span></span> | <span data-ttu-id="9060a-134">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="9060a-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="9060a-135">string</span><span class="sxs-lookup"><span data-stu-id="9060a-135">string</span></span> | <span data-ttu-id="9060a-136">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="9060a-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="9060a-137">строка</span><span class="sxs-lookup"><span data-stu-id="9060a-137">string</span></span> | <span data-ttu-id="9060a-138">МЕТОДЫ ATT MITRE&CK, связанные с действиями, которые вызвали оповещение</span><span class="sxs-lookup"><span data-stu-id="9060a-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="9060a-139">long</span><span class="sxs-lookup"><span data-stu-id="9060a-139">long</span></span> | <span data-ttu-id="9060a-140">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="9060a-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="9060a-141">Чтобы определить уникальные события, этот столбец должен использоваться совместно с `DeviceName` `Timestamp` столбцами и</span><span class="sxs-lookup"><span data-stu-id="9060a-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="9060a-142">string</span><span class="sxs-lookup"><span data-stu-id="9060a-142">string</span></span> | <span data-ttu-id="9060a-143">Таблица, содержащая сведения о событии</span><span class="sxs-lookup"><span data-stu-id="9060a-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9060a-144">См. также</span><span class="sxs-lookup"><span data-stu-id="9060a-144">Related topics</span></span>
- [<span data-ttu-id="9060a-145">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="9060a-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9060a-146">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="9060a-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9060a-147">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="9060a-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
