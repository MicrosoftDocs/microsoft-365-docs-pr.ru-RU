---
title: Таблица DeviceAlertEvents в продвинутой схеме охоты
description: Узнайте о событиях генерации оповещений в таблице DeviceAlertEvents продвинутой схемы охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, microsoft defender for endpoint, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, DeviceAlertEvents, alert, severity, category
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: f4f6ecdc57d8602f49fb389c741c5e01dc1b41b5
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939653"
---
# <a name="devicealertevents"></a><span data-ttu-id="6381f-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="6381f-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6381f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6381f-105">**Applies to:**</span></span>
- [<span data-ttu-id="6381f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6381f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="6381f-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="6381f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6381f-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="6381f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="6381f-109">Таблица `DeviceAlertEvents` в [продвинутой схеме](advanced-hunting-overview.md) охоты содержит сведения о оповещениях в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6381f-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="6381f-110">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="6381f-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6381f-111">Сведения о других таблицах в продвинутой схеме охоты см. в справке [о схеме охоты.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="6381f-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="6381f-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="6381f-112">Column name</span></span> | <span data-ttu-id="6381f-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6381f-113">Data type</span></span> | <span data-ttu-id="6381f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6381f-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="6381f-115">string</span><span class="sxs-lookup"><span data-stu-id="6381f-115">string</span></span> | <span data-ttu-id="6381f-116">Уникальный идентификатор оповещения</span><span class="sxs-lookup"><span data-stu-id="6381f-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="6381f-117">datetime</span><span class="sxs-lookup"><span data-stu-id="6381f-117">datetime</span></span> | <span data-ttu-id="6381f-118">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="6381f-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6381f-119">string</span><span class="sxs-lookup"><span data-stu-id="6381f-119">string</span></span> | <span data-ttu-id="6381f-120">Уникальный идентификатор устройства в службе</span><span class="sxs-lookup"><span data-stu-id="6381f-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6381f-121">Строка</span><span class="sxs-lookup"><span data-stu-id="6381f-121">string</span></span> | <span data-ttu-id="6381f-122">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="6381f-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="6381f-123">string</span><span class="sxs-lookup"><span data-stu-id="6381f-123">string</span></span> | <span data-ttu-id="6381f-124">Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="6381f-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="6381f-125">string</span><span class="sxs-lookup"><span data-stu-id="6381f-125">string</span></span> | <span data-ttu-id="6381f-126">Тип индикатора угрозы или нарушения, определенного оповещением</span><span class="sxs-lookup"><span data-stu-id="6381f-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="6381f-127">string</span><span class="sxs-lookup"><span data-stu-id="6381f-127">string</span></span> | <span data-ttu-id="6381f-128">Название оповещения</span><span class="sxs-lookup"><span data-stu-id="6381f-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="6381f-129">string</span><span class="sxs-lookup"><span data-stu-id="6381f-129">string</span></span> | <span data-ttu-id="6381f-130">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="6381f-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="6381f-131">string</span><span class="sxs-lookup"><span data-stu-id="6381f-131">string</span></span> | <span data-ttu-id="6381f-132">SHA-1 файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="6381f-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="6381f-133">string</span><span class="sxs-lookup"><span data-stu-id="6381f-133">string</span></span> | <span data-ttu-id="6381f-134">URL-адрес или полное доменное имя, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="6381f-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="6381f-135">string</span><span class="sxs-lookup"><span data-stu-id="6381f-135">string</span></span> | <span data-ttu-id="6381f-136">IP-адрес, к которому выполнено подключение</span><span class="sxs-lookup"><span data-stu-id="6381f-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="6381f-137">Строка</span><span class="sxs-lookup"><span data-stu-id="6381f-137">string</span></span> | <span data-ttu-id="6381f-138">МЕТОДЫ ATT MITRE&CK, связанные с действиями, которые вызвали оповещение</span><span class="sxs-lookup"><span data-stu-id="6381f-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="6381f-139">long</span><span class="sxs-lookup"><span data-stu-id="6381f-139">long</span></span> | <span data-ttu-id="6381f-140">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="6381f-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6381f-141">Чтобы определить уникальные события, этот столбец должен использоваться совместно с `DeviceName` `Timestamp` столбцами и</span><span class="sxs-lookup"><span data-stu-id="6381f-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="6381f-142">string</span><span class="sxs-lookup"><span data-stu-id="6381f-142">string</span></span> | <span data-ttu-id="6381f-143">Таблица, содержащая сведения о событии</span><span class="sxs-lookup"><span data-stu-id="6381f-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6381f-144">См. также</span><span class="sxs-lookup"><span data-stu-id="6381f-144">Related topics</span></span>
- [<span data-ttu-id="6381f-145">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="6381f-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6381f-146">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="6381f-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6381f-147">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="6381f-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
