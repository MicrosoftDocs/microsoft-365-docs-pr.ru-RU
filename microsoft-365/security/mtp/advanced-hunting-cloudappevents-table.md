---
title: Таблица CloudAppEvents в схеме advanced hunting
description: Узнайте о событиях из облачных приложений и служб в таблице CloudAppEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928457"
---
# <a name="cloudappevents"></a><span data-ttu-id="51059-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="51059-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="51059-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="51059-105">**Applies to:**</span></span>
- <span data-ttu-id="51059-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51059-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="51059-107">В настоящее время доступна в предварительной версии, таблица в схеме advanced hunting содержит сведения о действиях в различных облачных приложениях и службах, в частности `CloudAppEvents` Microsoft Teams и Exchange Online. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="51059-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="51059-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="51059-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="51059-109">Эта таблица будет расширена и будет включать дополнительные действия, отслеживаемые Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="51059-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="51059-110">В итоге эта таблица будет включать действия с файлами, хранимые в таблице [AppFileEvents.](advanced-hunting-appfileevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="51059-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="51059-111">Корпорация Майкрософт предоставит дополнительные рекомендации по мере перемещения дополнительных данных в эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="51059-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="51059-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="51059-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="51059-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="51059-113">Column name</span></span> | <span data-ttu-id="51059-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="51059-114">Data type</span></span> | <span data-ttu-id="51059-115">Описание</span><span class="sxs-lookup"><span data-stu-id="51059-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="51059-116">datetime</span><span class="sxs-lookup"><span data-stu-id="51059-116">datetime</span></span> | <span data-ttu-id="51059-117">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="51059-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="51059-118">string</span><span class="sxs-lookup"><span data-stu-id="51059-118">string</span></span> | <span data-ttu-id="51059-119">Тип действия, которое вызвало событие</span><span class="sxs-lookup"><span data-stu-id="51059-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="51059-120">string</span><span class="sxs-lookup"><span data-stu-id="51059-120">string</span></span> | <span data-ttu-id="51059-121">Приложение, которое выполнило записанную действие</span><span class="sxs-lookup"><span data-stu-id="51059-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="51059-122">string</span><span class="sxs-lookup"><span data-stu-id="51059-122">string</span></span> | <span data-ttu-id="51059-123">Уникальный идентификатор приложения</span><span class="sxs-lookup"><span data-stu-id="51059-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="51059-124">string</span><span class="sxs-lookup"><span data-stu-id="51059-124">string</span></span> | <span data-ttu-id="51059-125">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="51059-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="51059-126">string</span><span class="sxs-lookup"><span data-stu-id="51059-126">string</span></span> | <span data-ttu-id="51059-127">Имя пользователя учетной записи, отображаемой в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="51059-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="51059-128">Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="51059-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="51059-129">string</span><span class="sxs-lookup"><span data-stu-id="51059-129">string</span></span> | <span data-ttu-id="51059-130">Указывает, было ли действие выполнено администратором</span><span class="sxs-lookup"><span data-stu-id="51059-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="51059-131">string</span><span class="sxs-lookup"><span data-stu-id="51059-131">string</span></span> | <span data-ttu-id="51059-132">Тип устройства, основанного на назначении и функциональных возможностях, таких как "Сетевое устройство", "Рабочие станции", "Сервер", "Мобильные устройства", "Игровая консоль" или "Принтер"</span><span class="sxs-lookup"><span data-stu-id="51059-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="51059-133">string</span><span class="sxs-lookup"><span data-stu-id="51059-133">string</span></span> | <span data-ttu-id="51059-134">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="51059-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="51059-135">В этом столбце указаны определенные операционные системы, включая варианты одного семейства, такие как Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="51059-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="51059-136">string</span><span class="sxs-lookup"><span data-stu-id="51059-136">string</span></span> | <span data-ttu-id="51059-137">IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях</span><span class="sxs-lookup"><span data-stu-id="51059-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="51059-138">string</span><span class="sxs-lookup"><span data-stu-id="51059-138">string</span></span> | <span data-ttu-id="51059-139">Указывает, принадлежит ли IP-адрес известному анонимному прокси-серверу</span><span class="sxs-lookup"><span data-stu-id="51059-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="51059-140">string</span><span class="sxs-lookup"><span data-stu-id="51059-140">string</span></span> | <span data-ttu-id="51059-141">Двух буквный код, указывающий страну, в которой расположен IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="51059-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="51059-142">string</span><span class="sxs-lookup"><span data-stu-id="51059-142">string</span></span> | <span data-ttu-id="51059-143">Город, в котором расположен IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="51059-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="51059-144">string</span><span class="sxs-lookup"><span data-stu-id="51059-144">string</span></span> | <span data-ttu-id="51059-145">Поставщик услуг Интернета, связанный с IP-адресом</span><span class="sxs-lookup"><span data-stu-id="51059-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="51059-146">string</span><span class="sxs-lookup"><span data-stu-id="51059-146">string</span></span> | <span data-ttu-id="51059-147">Сведения об агенте пользователя из веб-браузера или другого клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="51059-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="51059-148">string</span><span class="sxs-lookup"><span data-stu-id="51059-148">string</span></span> | <span data-ttu-id="51059-149">Тип действия, которое вызвало событие</span><span class="sxs-lookup"><span data-stu-id="51059-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="51059-150">string</span><span class="sxs-lookup"><span data-stu-id="51059-150">string</span></span> | <span data-ttu-id="51059-151">Список объектов, таких как файлы или папки, которые были задействованы в записанной активности</span><span class="sxs-lookup"><span data-stu-id="51059-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="51059-152">string</span><span class="sxs-lookup"><span data-stu-id="51059-152">string</span></span> | <span data-ttu-id="51059-153">Имя объекта, к который было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="51059-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="51059-154">string</span><span class="sxs-lookup"><span data-stu-id="51059-154">string</span></span> | <span data-ttu-id="51059-155">Тип объекта, например файла или папки, к который было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="51059-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="51059-156">string</span><span class="sxs-lookup"><span data-stu-id="51059-156">string</span></span> | <span data-ttu-id="51059-157">Уникальный идентификатор объекта, к котором было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="51059-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="51059-158">string</span><span class="sxs-lookup"><span data-stu-id="51059-158">string</span></span> | <span data-ttu-id="51059-159">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="51059-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="51059-160">string</span><span class="sxs-lookup"><span data-stu-id="51059-160">string</span></span> | <span data-ttu-id="51059-161">Необработанные сведения о событиях из источника приложения или службы в формате JSON</span><span class="sxs-lookup"><span data-stu-id="51059-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="51059-162">string</span><span class="sxs-lookup"><span data-stu-id="51059-162">string</span></span> | <span data-ttu-id="51059-163">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="51059-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="51059-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="51059-164">Related topics</span></span>
- [<span data-ttu-id="51059-165">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="51059-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="51059-166">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="51059-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="51059-167">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="51059-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="51059-168">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="51059-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="51059-169">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="51059-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="51059-170">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="51059-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
