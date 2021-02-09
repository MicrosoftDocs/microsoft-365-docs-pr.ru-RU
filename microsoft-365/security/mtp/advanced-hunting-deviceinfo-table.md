---
title: Таблица DeviceInfo в схеме advanced hunting
description: Сведения об ОС, имени компьютера и других сведениях о компьютере в таблице DeviceInfo схемы расширенных поисков
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
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
ms.openlocfilehash: 6462096a6c1b44ee11299f652a54f261d0355523
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145371"
---
# <a name="deviceinfo"></a><span data-ttu-id="deb86-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="deb86-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="deb86-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="deb86-105">**Applies to:**</span></span>
- <span data-ttu-id="deb86-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="deb86-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="deb86-107">Таблица в схеме advanced hunting содержит сведения о компьютерах в организации, включая версию `DeviceInfo` ОС, активных пользователей и имя компьютера. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="deb86-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="deb86-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="deb86-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="deb86-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="deb86-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="deb86-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="deb86-110">Column name</span></span> | <span data-ttu-id="deb86-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="deb86-111">Data type</span></span> | <span data-ttu-id="deb86-112">Описание</span><span class="sxs-lookup"><span data-stu-id="deb86-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="deb86-113">datetime</span><span class="sxs-lookup"><span data-stu-id="deb86-113">datetime</span></span> | <span data-ttu-id="deb86-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="deb86-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="deb86-115">string</span><span class="sxs-lookup"><span data-stu-id="deb86-115">string</span></span> | <span data-ttu-id="deb86-116">Уникальный идентификатор для обслуживаемого компьютера</span><span class="sxs-lookup"><span data-stu-id="deb86-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="deb86-117">string</span><span class="sxs-lookup"><span data-stu-id="deb86-117">string</span></span> | <span data-ttu-id="deb86-118">Полное доменное имя компьютера</span><span class="sxs-lookup"><span data-stu-id="deb86-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="deb86-119">string</span><span class="sxs-lookup"><span data-stu-id="deb86-119">string</span></span> | <span data-ttu-id="deb86-120">Версия агента конечной точки или датчика, запущенного на компьютере</span><span class="sxs-lookup"><span data-stu-id="deb86-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="deb86-121">string</span><span class="sxs-lookup"><span data-stu-id="deb86-121">string</span></span> | <span data-ttu-id="deb86-122">Общедоступный IP-адрес, используемый подключенным компьютером для подключения к службе Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="deb86-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="deb86-123">Это может быть IP-адрес самого компьютера, устройство NAT или прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="deb86-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="deb86-124">string</span><span class="sxs-lookup"><span data-stu-id="deb86-124">string</span></span> | <span data-ttu-id="deb86-125">Архитектура операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="deb86-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="deb86-126">string</span><span class="sxs-lookup"><span data-stu-id="deb86-126">string</span></span> | <span data-ttu-id="deb86-127">Платформа операционной системы, используемой на компьютере.</span><span class="sxs-lookup"><span data-stu-id="deb86-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="deb86-128">Это указывает на определенные операционные системы, включая варианты одного семейства, такие как Windows 10 и Windows 7</span><span class="sxs-lookup"><span data-stu-id="deb86-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="deb86-129">string</span><span class="sxs-lookup"><span data-stu-id="deb86-129">string</span></span> | <span data-ttu-id="deb86-130">Версия сборки операционной системы, запущенной на компьютере</span><span class="sxs-lookup"><span data-stu-id="deb86-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="deb86-131">boolean</span><span class="sxs-lookup"><span data-stu-id="deb86-131">boolean</span></span> | <span data-ttu-id="deb86-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="deb86-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `DeviceObjectId` | <span data-ttu-id="deb86-133">string</span><span class="sxs-lookup"><span data-stu-id="deb86-133">string</span></span> | <span data-ttu-id="deb86-134">Уникальный идентификатор устройства в Azure AD</span><span class="sxs-lookup"><span data-stu-id="deb86-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="deb86-135">string</span><span class="sxs-lookup"><span data-stu-id="deb86-135">string</span></span> | <span data-ttu-id="deb86-136">Список всех пользователей, которые вошли в систему на компьютере во время события в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="deb86-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="deb86-137">string</span><span class="sxs-lookup"><span data-stu-id="deb86-137">string</span></span> | <span data-ttu-id="deb86-138">Тег компьютера, добавленный через реестр</span><span class="sxs-lookup"><span data-stu-id="deb86-138">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="deb86-139">long</span><span class="sxs-lookup"><span data-stu-id="deb86-139">long</span></span> | <span data-ttu-id="deb86-140">Идентификатор события на основе повторяющегося счетчика.</span><span class="sxs-lookup"><span data-stu-id="deb86-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="deb86-141">Чтобы определить уникальные события, этот столбец необходимо использовать вместе со столбцами DeviceName и Timestamp.</span><span class="sxs-lookup"><span data-stu-id="deb86-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="deb86-142">string</span><span class="sxs-lookup"><span data-stu-id="deb86-142">string</span></span> | <span data-ttu-id="deb86-143">Дополнительные сведения о событии в формате массива JSON</span><span class="sxs-lookup"><span data-stu-id="deb86-143">Additional information about the event in JSON array format</span></span> |
| `OSVersion` | <span data-ttu-id="deb86-144">string</span><span class="sxs-lookup"><span data-stu-id="deb86-144">string</span></span> | <span data-ttu-id="deb86-145">Версия операционной системы, используемой на компьютере</span><span class="sxs-lookup"><span data-stu-id="deb86-145">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="deb86-146">string</span><span class="sxs-lookup"><span data-stu-id="deb86-146">string</span></span> | <span data-ttu-id="deb86-147">Группа компьютера.</span><span class="sxs-lookup"><span data-stu-id="deb86-147">Machine group of the machine.</span></span> <span data-ttu-id="deb86-148">Эта группа используется управлением доступом на основе ролей для определения доступа к компьютеру</span><span class="sxs-lookup"><span data-stu-id="deb86-148">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="deb86-149">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="deb86-149">Related topics</span></span>
- [<span data-ttu-id="deb86-150">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="deb86-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="deb86-151">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="deb86-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="deb86-152">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="deb86-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="deb86-153">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="deb86-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="deb86-154">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="deb86-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="deb86-155">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="deb86-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
