---
title: Таблица DeviceInfo в продвинутой схеме охоты
description: Сведения об ОС, имени компьютера и других сведениях о машине в таблице DeviceInfo в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, machine, OS, platform, users
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
ms.openlocfilehash: f97947c2c9f02720facae4f0c3c29ff702416261
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023133"
---
# <a name="deviceinfo"></a><span data-ttu-id="638a2-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="638a2-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="638a2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="638a2-105">**Applies to:**</span></span>
- <span data-ttu-id="638a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="638a2-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="638a2-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="638a2-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="638a2-108">Таблица в продвинутой схеме охоты содержит сведения о устройствах в организации, включая версию ОС, активных пользователей `DeviceInfo` и имя компьютера. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="638a2-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="638a2-109">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="638a2-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="638a2-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="638a2-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="638a2-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="638a2-111">Column name</span></span> | <span data-ttu-id="638a2-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="638a2-112">Data type</span></span> | <span data-ttu-id="638a2-113">Описание</span><span class="sxs-lookup"><span data-stu-id="638a2-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="638a2-114">datetime</span><span class="sxs-lookup"><span data-stu-id="638a2-114">datetime</span></span> | <span data-ttu-id="638a2-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="638a2-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="638a2-116">string</span><span class="sxs-lookup"><span data-stu-id="638a2-116">string</span></span> | <span data-ttu-id="638a2-117">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="638a2-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="638a2-118">string</span><span class="sxs-lookup"><span data-stu-id="638a2-118">string</span></span> | <span data-ttu-id="638a2-119">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="638a2-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="638a2-120">string</span><span class="sxs-lookup"><span data-stu-id="638a2-120">string</span></span> | <span data-ttu-id="638a2-121">Версия агента конечной точки или датчика, запущенного на компьютере</span><span class="sxs-lookup"><span data-stu-id="638a2-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="638a2-122">String</span><span class="sxs-lookup"><span data-stu-id="638a2-122">string</span></span> | <span data-ttu-id="638a2-123">Общедоступный IP-адрес, используемый бортовой машиной для подключения к службе Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="638a2-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="638a2-124">Это может быть IP-адрес самой машины, устройство NAT или прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="638a2-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="638a2-125">string</span><span class="sxs-lookup"><span data-stu-id="638a2-125">string</span></span> | <span data-ttu-id="638a2-126">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="638a2-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="638a2-127">string</span><span class="sxs-lookup"><span data-stu-id="638a2-127">string</span></span> | <span data-ttu-id="638a2-128">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="638a2-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="638a2-129">Это указывает на определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="638a2-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="638a2-130">String</span><span class="sxs-lookup"><span data-stu-id="638a2-130">string</span></span> | <span data-ttu-id="638a2-131">Сборка версии операционной системы, запущенной на компьютере</span><span class="sxs-lookup"><span data-stu-id="638a2-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="638a2-132">boolean</span><span class="sxs-lookup"><span data-stu-id="638a2-132">boolean</span></span> | <span data-ttu-id="638a2-133">Индикатор Boolean о том, присоединяется ли машина к Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="638a2-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="638a2-134">String</span><span class="sxs-lookup"><span data-stu-id="638a2-134">string</span></span> | <span data-ttu-id="638a2-135">Уникальный идентификатор устройства в Azure AD</span><span class="sxs-lookup"><span data-stu-id="638a2-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="638a2-136">String</span><span class="sxs-lookup"><span data-stu-id="638a2-136">string</span></span> | <span data-ttu-id="638a2-137">Список всех пользователей, зарегистрированных на компьютере во время события в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="638a2-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="638a2-138">String</span><span class="sxs-lookup"><span data-stu-id="638a2-138">string</span></span> | <span data-ttu-id="638a2-139">Тег машины, добавленный в реестр</span><span class="sxs-lookup"><span data-stu-id="638a2-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="638a2-140">string</span><span class="sxs-lookup"><span data-stu-id="638a2-140">string</span></span> | <span data-ttu-id="638a2-141">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="638a2-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="638a2-142">string</span><span class="sxs-lookup"><span data-stu-id="638a2-142">string</span></span> | <span data-ttu-id="638a2-143">Машинная группа машины.</span><span class="sxs-lookup"><span data-stu-id="638a2-143">Machine group of the machine.</span></span> <span data-ttu-id="638a2-144">Эта группа используется управлением доступом на основе ролей для определения доступа к машине</span><span class="sxs-lookup"><span data-stu-id="638a2-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="638a2-145">long</span><span class="sxs-lookup"><span data-stu-id="638a2-145">long</span></span> | <span data-ttu-id="638a2-146">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="638a2-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="638a2-147">Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="638a2-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="638a2-148">String</span><span class="sxs-lookup"><span data-stu-id="638a2-148">string</span></span> | <span data-ttu-id="638a2-149">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="638a2-149">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="638a2-150">В таблице содержится информация об устройстве на основе пульса, которые являются периодическими отчетами или `DeviceInfo` сигналами с устройства.</span><span class="sxs-lookup"><span data-stu-id="638a2-150">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="638a2-151">Каждые 15 минут устройство отправляет частичное сердцебиение, которое содержит часто меняющиеся атрибуты, такие как `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="638a2-151">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="638a2-152">Один раз в день отправляется полное сердцебиение, содержащее атрибуты устройства.</span><span class="sxs-lookup"><span data-stu-id="638a2-152">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="638a2-153">Чтобы получить последнее состояние устройства, можно использовать следующий пример запроса:</span><span class="sxs-lookup"><span data-stu-id="638a2-153">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="638a2-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="638a2-154">Related topics</span></span>
- [<span data-ttu-id="638a2-155">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="638a2-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="638a2-156">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="638a2-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="638a2-157">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="638a2-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="638a2-158">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="638a2-158">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="638a2-159">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="638a2-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="638a2-160">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="638a2-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
