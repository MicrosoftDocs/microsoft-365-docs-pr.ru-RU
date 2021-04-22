---
title: Таблица CloudAppEvents в продвинутой схеме охоты
description: Узнайте о событиях из облачных приложений и служб в таблице CloudAppEvents продвинутой схемы охоты
keywords: передовая охота, охота на угрозы, поиск киберугроз, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка на схему, kusto, таблица, столбец, тип данных, описание, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935873"
---
# <a name="cloudappevents"></a><span data-ttu-id="2ddf0-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="2ddf0-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2ddf0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2ddf0-105">**Applies to:**</span></span>
- <span data-ttu-id="2ddf0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ddf0-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="2ddf0-107">Таблица в продвинутой схеме охоты содержит сведения о действиях в различных облачных приложениях и службах, охваченных `CloudAppEvents` microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2ddf0-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="2ddf0-108">Для полного списка переперейти к [приложениям и службам, охваченным](#apps-and-services-covered).</span><span class="sxs-lookup"><span data-stu-id="2ddf0-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="2ddf0-109">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="2ddf0-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="2ddf0-110">В эту таблицу включены сведения, которые раньше были доступны в `AppFileEvents` таблице.</span><span class="sxs-lookup"><span data-stu-id="2ddf0-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="2ddf0-111">Начиная с 7 марта 2021 г. пользователи, которые охотятся через действия, связанные с файлами, в облачных службах и после этой даты, должны использовать `CloudAppEvents` таблицу вместо этого.</span><span class="sxs-lookup"><span data-stu-id="2ddf0-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="2ddf0-112">Не забудьте найти запросы и пользовательские правила обнаружения, которые по-прежнему используются в таблице, и `AppFileEvents` изменить их для использования `CloudAppEvents` таблицы.</span><span class="sxs-lookup"><span data-stu-id="2ddf0-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="2ddf0-113">Дополнительные инструкции по преобразованию затронутых запросов можно найти в Hunt в облачных приложениях с помощью расширенных методов охоты На защитника [Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)</span><span class="sxs-lookup"><span data-stu-id="2ddf0-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="2ddf0-114">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2ddf0-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2ddf0-115">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="2ddf0-115">Column name</span></span> | <span data-ttu-id="2ddf0-116">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2ddf0-116">Data type</span></span> | <span data-ttu-id="2ddf0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="2ddf0-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2ddf0-118">datetime</span><span class="sxs-lookup"><span data-stu-id="2ddf0-118">datetime</span></span> | <span data-ttu-id="2ddf0-119">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="2ddf0-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="2ddf0-120">string</span><span class="sxs-lookup"><span data-stu-id="2ddf0-120">string</span></span> | <span data-ttu-id="2ddf0-121">Тип действий, которые вызвали событие</span><span class="sxs-lookup"><span data-stu-id="2ddf0-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="2ddf0-122">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-122">string</span></span> | <span data-ttu-id="2ddf0-123">Приложение, которое выполнило записанную акцию</span><span class="sxs-lookup"><span data-stu-id="2ddf0-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="2ddf0-124">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-124">string</span></span> | <span data-ttu-id="2ddf0-125">Уникальный идентификатор для приложения</span><span class="sxs-lookup"><span data-stu-id="2ddf0-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="2ddf0-126">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-126">string</span></span> | <span data-ttu-id="2ddf0-127">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2ddf0-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2ddf0-128">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-128">string</span></span> | <span data-ttu-id="2ddf0-129">Имя пользователя учетной записи, отображаемого в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="2ddf0-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2ddf0-130">Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="2ddf0-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="2ddf0-131">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-131">string</span></span> | <span data-ttu-id="2ddf0-132">Указывает, выполнялось ли действие администратором</span><span class="sxs-lookup"><span data-stu-id="2ddf0-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="2ddf0-133">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-133">string</span></span> | <span data-ttu-id="2ddf0-134">Тип устройства на основе целей и функциональных возможностей, таких как "Сетевое устройство", "Workstation", "Server", "Mobile", "Gaming console" или "Printer"</span><span class="sxs-lookup"><span data-stu-id="2ddf0-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="2ddf0-135">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-135">string</span></span> | <span data-ttu-id="2ddf0-136">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="2ddf0-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2ddf0-137">В этом столбце указаны определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2ddf0-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="2ddf0-138">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-138">string</span></span> | <span data-ttu-id="2ddf0-139">IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="2ddf0-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="2ddf0-140">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-140">string</span></span> | <span data-ttu-id="2ddf0-141">Указывает, принадлежит ли IP-адрес известному анонимному прокси-серверу</span><span class="sxs-lookup"><span data-stu-id="2ddf0-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="2ddf0-142">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-142">string</span></span> | <span data-ttu-id="2ddf0-143">Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="2ddf0-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="2ddf0-144">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-144">string</span></span> | <span data-ttu-id="2ddf0-145">Город, в котором расположен IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="2ddf0-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="2ddf0-146">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-146">string</span></span> | <span data-ttu-id="2ddf0-147">Поставщик интернет-услуг (ISP), связанный с IP-адресом</span><span class="sxs-lookup"><span data-stu-id="2ddf0-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="2ddf0-148">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-148">string</span></span> | <span data-ttu-id="2ddf0-149">Сведения агента пользователя из веб-браузера или другого клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="2ddf0-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="2ddf0-150">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-150">string</span></span> | <span data-ttu-id="2ddf0-151">Тип действий, которые вызвали событие</span><span class="sxs-lookup"><span data-stu-id="2ddf0-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="2ddf0-152">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-152">string</span></span> | <span data-ttu-id="2ddf0-153">Список объектов, таких как файлы или папки, которые были вовлечены в записанную деятельность.</span><span class="sxs-lookup"><span data-stu-id="2ddf0-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="2ddf0-154">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-154">string</span></span> | <span data-ttu-id="2ddf0-155">Имя объекта, к который было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="2ddf0-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="2ddf0-156">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-156">string</span></span> | <span data-ttu-id="2ddf0-157">Тип объекта, например файла или папки, к который было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="2ddf0-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="2ddf0-158">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-158">string</span></span> | <span data-ttu-id="2ddf0-159">Уникальный идентификатор объекта, к котором было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="2ddf0-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="2ddf0-160">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-160">string</span></span> | <span data-ttu-id="2ddf0-161">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="2ddf0-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="2ddf0-162">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-162">string</span></span> | <span data-ttu-id="2ddf0-163">Необработанные сведения о событиях из исходных приложений или служб в формате JSON</span><span class="sxs-lookup"><span data-stu-id="2ddf0-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="2ddf0-164">Строка</span><span class="sxs-lookup"><span data-stu-id="2ddf0-164">string</span></span> | <span data-ttu-id="2ddf0-165">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="2ddf0-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="2ddf0-166">Приложения и службы, охваченные</span><span class="sxs-lookup"><span data-stu-id="2ddf0-166">Apps and services covered</span></span>

- <span data-ttu-id="2ddf0-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="2ddf0-167">Dropbox</span></span>
- <span data-ttu-id="2ddf0-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2ddf0-168">Dynamics 365</span></span>
- <span data-ttu-id="2ddf0-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ddf0-169">Exchange Online</span></span>
- <span data-ttu-id="2ddf0-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ddf0-170">Microsoft Teams</span></span>
- <span data-ttu-id="2ddf0-171">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2ddf0-171">OneDrive for Business</span></span>
- <span data-ttu-id="2ddf0-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="2ddf0-172">Power Automate</span></span>
- <span data-ttu-id="2ddf0-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="2ddf0-173">Power BI</span></span>
- <span data-ttu-id="2ddf0-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2ddf0-174">SharePoint Online</span></span>
- <span data-ttu-id="2ddf0-175">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2ddf0-175">Skype for Business</span></span>
- <span data-ttu-id="2ddf0-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="2ddf0-176">Office 365</span></span>
- <span data-ttu-id="2ddf0-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="2ddf0-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="2ddf0-178">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="2ddf0-178">Related topics</span></span>
- [<span data-ttu-id="2ddf0-179">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="2ddf0-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2ddf0-180">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="2ddf0-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2ddf0-181">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="2ddf0-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2ddf0-182">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="2ddf0-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2ddf0-183">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="2ddf0-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2ddf0-184">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="2ddf0-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
