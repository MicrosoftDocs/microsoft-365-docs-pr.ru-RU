---
title: Таблица CloudAppEvents в продвинутой схеме охоты
description: Узнайте о событиях из облачных приложений и служб в таблице CloudAppEvents продвинутой схемы охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 2aa592e70bce7bb469f851bedc542ee58cac0037
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498667"
---
# <a name="cloudappevents"></a><span data-ttu-id="0c7e3-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="0c7e3-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0c7e3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0c7e3-105">**Applies to:**</span></span>
- <span data-ttu-id="0c7e3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c7e3-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="0c7e3-107">Таблица в схеме расширенных схем охоты содержит сведения о действиях в различных облачных приложениях и службах, охваченных безопасностью облачных приложений Microsoft, в частности `CloudAppEvents` Dropbox, [](advanced-hunting-overview.md) Exchange Online, OneDrive, Microsoft Teams и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="0c7e3-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="0c7e3-109">В эту таблицу включены сведения, которые раньше были доступны в `AppFileEvents` таблице.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="0c7e3-110">Начиная с 7 марта 2021 г. пользователи, которые охотятся через действия, связанные с файлами, в облачных службах и после этой даты, должны использовать `CloudAppEvents` таблицу вместо этого.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="0c7e3-111">Не забудьте найти запросы и пользовательские правила обнаружения, которые по-прежнему используются в таблице, и `AppFileEvents` изменить их для использования `CloudAppEvents` таблицы.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="0c7e3-112">Дополнительные инструкции по преобразованию затронутых запросов можно найти в Hunt в облачных приложениях с помощью расширенных методов охоты На защитника [Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)</span><span class="sxs-lookup"><span data-stu-id="0c7e3-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="0c7e3-113">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0c7e3-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0c7e3-114">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="0c7e3-114">Column name</span></span> | <span data-ttu-id="0c7e3-115">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0c7e3-115">Data type</span></span> | <span data-ttu-id="0c7e3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0c7e3-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0c7e3-117">datetime</span><span class="sxs-lookup"><span data-stu-id="0c7e3-117">datetime</span></span> | <span data-ttu-id="0c7e3-118">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="0c7e3-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0c7e3-119">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-119">string</span></span> | <span data-ttu-id="0c7e3-120">Тип действий, которые вызвали событие</span><span class="sxs-lookup"><span data-stu-id="0c7e3-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="0c7e3-121">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-121">string</span></span> | <span data-ttu-id="0c7e3-122">Приложение, которое выполнило записанную акцию</span><span class="sxs-lookup"><span data-stu-id="0c7e3-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="0c7e3-123">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-123">string</span></span> | <span data-ttu-id="0c7e3-124">Уникальный идентификатор для приложения</span><span class="sxs-lookup"><span data-stu-id="0c7e3-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="0c7e3-125">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-125">string</span></span> | <span data-ttu-id="0c7e3-126">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0c7e3-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0c7e3-127">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-127">string</span></span> | <span data-ttu-id="0c7e3-128">Имя пользователя учетной записи, отображаемого в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0c7e3-129">Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="0c7e3-130">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-130">string</span></span> | <span data-ttu-id="0c7e3-131">Указывает, выполнялось ли действие администратором</span><span class="sxs-lookup"><span data-stu-id="0c7e3-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="0c7e3-132">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-132">string</span></span> | <span data-ttu-id="0c7e3-133">Тип устройства на основе целей и функциональных возможностей, таких как "Сетевое устройство", "Workstation", "Server", "Mobile", "Gaming console" или "Printer"</span><span class="sxs-lookup"><span data-stu-id="0c7e3-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="0c7e3-134">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-134">string</span></span> | <span data-ttu-id="0c7e3-135">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0c7e3-136">В этом столбце указаны определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="0c7e3-137">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-137">string</span></span> | <span data-ttu-id="0c7e3-138">IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="0c7e3-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="0c7e3-139">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-139">string</span></span> | <span data-ttu-id="0c7e3-140">Указывает, принадлежит ли IP-адрес известному анонимному прокси-серверу</span><span class="sxs-lookup"><span data-stu-id="0c7e3-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="0c7e3-141">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-141">string</span></span> | <span data-ttu-id="0c7e3-142">Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="0c7e3-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="0c7e3-143">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-143">string</span></span> | <span data-ttu-id="0c7e3-144">Город, в котором расположен IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="0c7e3-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="0c7e3-145">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-145">string</span></span> | <span data-ttu-id="0c7e3-146">Поставщик интернет-услуг (ISP), связанный с IP-адресом</span><span class="sxs-lookup"><span data-stu-id="0c7e3-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="0c7e3-147">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-147">string</span></span> | <span data-ttu-id="0c7e3-148">Сведения агента пользователя из веб-браузера или другого клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="0c7e3-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="0c7e3-149">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-149">string</span></span> | <span data-ttu-id="0c7e3-150">Тип действий, которые вызвали событие</span><span class="sxs-lookup"><span data-stu-id="0c7e3-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="0c7e3-151">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-151">string</span></span> | <span data-ttu-id="0c7e3-152">Список объектов, таких как файлы или папки, которые были вовлечены в записанную деятельность.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="0c7e3-153">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-153">string</span></span> | <span data-ttu-id="0c7e3-154">Имя объекта, к который было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="0c7e3-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="0c7e3-155">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-155">string</span></span> | <span data-ttu-id="0c7e3-156">Тип объекта, например файла или папки, к который было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="0c7e3-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="0c7e3-157">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-157">string</span></span> | <span data-ttu-id="0c7e3-158">Уникальный идентификатор объекта, к котором было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="0c7e3-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="0c7e3-159">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-159">string</span></span> | <span data-ttu-id="0c7e3-160">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0c7e3-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="0c7e3-161">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-161">string</span></span> | <span data-ttu-id="0c7e3-162">Необработанные сведения о событиях из исходных приложений или служб в формате JSON</span><span class="sxs-lookup"><span data-stu-id="0c7e3-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="0c7e3-163">string</span><span class="sxs-lookup"><span data-stu-id="0c7e3-163">string</span></span> | <span data-ttu-id="0c7e3-164">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="0c7e3-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="0c7e3-165">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0c7e3-165">Related topics</span></span>
- [<span data-ttu-id="0c7e3-166">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="0c7e3-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0c7e3-167">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="0c7e3-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0c7e3-168">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="0c7e3-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0c7e3-169">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="0c7e3-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0c7e3-170">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="0c7e3-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0c7e3-171">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="0c7e3-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
