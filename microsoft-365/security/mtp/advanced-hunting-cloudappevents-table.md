---
title: Таблица клаудаппевентс в схеме расширенного поискового окна
description: Сведения о событиях из облачных приложений и служб в таблице Клаудаппевентс расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Клаудаппевентс, безопасность облачных приложений, МКАС
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087774"
---
# <a name="cloudappevents"></a><span data-ttu-id="ca743-104">клаудаппевентс</span><span class="sxs-lookup"><span data-stu-id="ca743-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ca743-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ca743-105">**Applies to:**</span></span>
- <span data-ttu-id="ca743-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca743-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ca743-107">В настоящее время в предварительной версии `CloudAppEvents` Таблица, содержащаяся в [расширенной](advanced-hunting-overview.md) схеме Поиск, содержит сведения о действиях в различных облачных приложениях и службах, в частности, Microsoft Teams и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ca743-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="ca743-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="ca743-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ca743-109">Эта таблица будет расширена для включения дополнительных действий, отслеживаемых Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="ca743-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="ca743-110">В конечном итоге, эта таблица будет включать в себя действия с файлами, хранящиеся в таблице [аппфиливентс](advanced-hunting-appfileevents-table.md) .</span><span class="sxs-lookup"><span data-stu-id="ca743-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="ca743-111">Корпорация Майкрософт предоставит дополнительные рекомендации по мере перемещения данных в эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="ca743-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="ca743-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ca743-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ca743-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="ca743-113">Column name</span></span> | <span data-ttu-id="ca743-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ca743-114">Data type</span></span> | <span data-ttu-id="ca743-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ca743-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ca743-116">datetime</span><span class="sxs-lookup"><span data-stu-id="ca743-116">datetime</span></span> | <span data-ttu-id="ca743-117">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="ca743-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="ca743-118">string</span><span class="sxs-lookup"><span data-stu-id="ca743-118">string</span></span> | <span data-ttu-id="ca743-119">Тип действия, вызвавшего событие</span><span class="sxs-lookup"><span data-stu-id="ca743-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="ca743-120">string</span><span class="sxs-lookup"><span data-stu-id="ca743-120">string</span></span> | <span data-ttu-id="ca743-121">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="ca743-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="ca743-122">string</span><span class="sxs-lookup"><span data-stu-id="ca743-122">string</span></span> | <span data-ttu-id="ca743-123">Уникальный идентификатор приложения</span><span class="sxs-lookup"><span data-stu-id="ca743-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="ca743-124">string</span><span class="sxs-lookup"><span data-stu-id="ca743-124">string</span></span> | <span data-ttu-id="ca743-125">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ca743-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="ca743-126">string</span><span class="sxs-lookup"><span data-stu-id="ca743-126">string</span></span> | <span data-ttu-id="ca743-127">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="ca743-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="ca743-128">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="ca743-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="ca743-129">string</span><span class="sxs-lookup"><span data-stu-id="ca743-129">string</span></span> | <span data-ttu-id="ca743-130">Указывает, выполнялась ли действие администратором</span><span class="sxs-lookup"><span data-stu-id="ca743-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="ca743-131">string</span><span class="sxs-lookup"><span data-stu-id="ca743-131">string</span></span> | <span data-ttu-id="ca743-132">Тип устройства, основанный на назначении и функциях, таких как "Сетевое устройство", "Рабочая станция", "сервер", "мобильное устройство", "игровая консоль" или "принтер"</span><span class="sxs-lookup"><span data-stu-id="ca743-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="ca743-133">string</span><span class="sxs-lookup"><span data-stu-id="ca743-133">string</span></span> | <span data-ttu-id="ca743-134">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ca743-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="ca743-135">В этом столбце указываются определенные операционные системы, в том числе варианты в пределах одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="ca743-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="ca743-136">string</span><span class="sxs-lookup"><span data-stu-id="ca743-136">string</span></span> | <span data-ttu-id="ca743-137">IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="ca743-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="ca743-138">string</span><span class="sxs-lookup"><span data-stu-id="ca743-138">string</span></span> | <span data-ttu-id="ca743-139">Указывает, принадлежит ли IP-адрес известному анонимному прокси-серверу</span><span class="sxs-lookup"><span data-stu-id="ca743-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="ca743-140">string</span><span class="sxs-lookup"><span data-stu-id="ca743-140">string</span></span> | <span data-ttu-id="ca743-141">Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="ca743-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="ca743-142">string</span><span class="sxs-lookup"><span data-stu-id="ca743-142">string</span></span> | <span data-ttu-id="ca743-143">Город, в котором расположен IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="ca743-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="ca743-144">string</span><span class="sxs-lookup"><span data-stu-id="ca743-144">string</span></span> | <span data-ttu-id="ca743-145">Поставщик услуг Интернета (ISP), связанный с IP-адресом</span><span class="sxs-lookup"><span data-stu-id="ca743-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="ca743-146">string</span><span class="sxs-lookup"><span data-stu-id="ca743-146">string</span></span> | <span data-ttu-id="ca743-147">Сведения о агенте пользователя из веб-браузера или другого клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="ca743-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="ca743-148">string</span><span class="sxs-lookup"><span data-stu-id="ca743-148">string</span></span> | <span data-ttu-id="ca743-149">Тип действия, вызвавшего событие</span><span class="sxs-lookup"><span data-stu-id="ca743-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="ca743-150">string</span><span class="sxs-lookup"><span data-stu-id="ca743-150">string</span></span> | <span data-ttu-id="ca743-151">Список объектов, например файлов или папок, которые участвовали в записанных действиях</span><span class="sxs-lookup"><span data-stu-id="ca743-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="ca743-152">string</span><span class="sxs-lookup"><span data-stu-id="ca743-152">string</span></span> | <span data-ttu-id="ca743-153">Имя объекта, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ca743-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="ca743-154">string</span><span class="sxs-lookup"><span data-stu-id="ca743-154">string</span></span> | <span data-ttu-id="ca743-155">Тип объекта, например файл или папка, к которым было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ca743-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="ca743-156">string</span><span class="sxs-lookup"><span data-stu-id="ca743-156">string</span></span> | <span data-ttu-id="ca743-157">Уникальный идентификатор объекта, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="ca743-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="ca743-158">string</span><span class="sxs-lookup"><span data-stu-id="ca743-158">string</span></span> | <span data-ttu-id="ca743-159">Уникальный идентификатор для события</span><span class="sxs-lookup"><span data-stu-id="ca743-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="ca743-160">string</span><span class="sxs-lookup"><span data-stu-id="ca743-160">string</span></span> | <span data-ttu-id="ca743-161">Сведения о событиях RAW из исходного приложения или службы в формате JSON</span><span class="sxs-lookup"><span data-stu-id="ca743-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="ca743-162">string</span><span class="sxs-lookup"><span data-stu-id="ca743-162">string</span></span> | <span data-ttu-id="ca743-163">Дополнительные сведения о сущности или событии</span><span class="sxs-lookup"><span data-stu-id="ca743-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ca743-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ca743-164">Related topics</span></span>
- [<span data-ttu-id="ca743-165">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="ca743-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ca743-166">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="ca743-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ca743-167">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="ca743-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ca743-168">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="ca743-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ca743-169">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ca743-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ca743-170">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="ca743-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
