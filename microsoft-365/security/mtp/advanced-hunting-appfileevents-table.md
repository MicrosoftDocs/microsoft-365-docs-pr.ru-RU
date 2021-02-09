---
title: Таблица AppFileEvents в схеме advanced hunting
description: Узнайте о событиях, связанных с файлами, связанных с облачными приложениями и службами, в таблице AppFileEvents схемы advanced hunting
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, телеметрия, справочник по схеме, kusto, таблица, столбец, тип данных, описание, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 8406d1f9e3d56555b1699d191933c6f9735c9574
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145491"
---
# <a name="appfileevents"></a><span data-ttu-id="f64c6-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="f64c6-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f64c6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f64c6-105">**Applies to:**</span></span>
- <span data-ttu-id="f64c6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f64c6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f64c6-107">Таблица в схеме advanced hunting содержит сведения о действиях, связанных с файлами, в облачных приложениях и службах, `AppFileEvents` отслеживаемом Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f64c6-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="f64c6-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="f64c6-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="f64c6-109">Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="f64c6-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="f64c6-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f64c6-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f64c6-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="f64c6-111">Column name</span></span> | <span data-ttu-id="f64c6-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f64c6-112">Data type</span></span> | <span data-ttu-id="f64c6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f64c6-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f64c6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="f64c6-114">datetime</span></span> | <span data-ttu-id="f64c6-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="f64c6-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f64c6-116">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-116">string</span></span> | <span data-ttu-id="f64c6-117">Тип действия, которое вызвало событие.</span><span class="sxs-lookup"><span data-stu-id="f64c6-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="f64c6-118">Подробные сведения см. в справке [по схеме портала](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="f64c6-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="f64c6-119">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-119">string</span></span> | <span data-ttu-id="f64c6-120">Приложение, которое выполнило записанную действие</span><span class="sxs-lookup"><span data-stu-id="f64c6-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="f64c6-121">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-121">string</span></span> | <span data-ttu-id="f64c6-122">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="f64c6-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="f64c6-123">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-123">string</span></span> | <span data-ttu-id="f64c6-124">Папка, содержащая файл, к которой было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="f64c6-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="f64c6-125">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-125">string</span></span> | <span data-ttu-id="f64c6-126">Исходное имя файла, переименованного в результате действия</span><span class="sxs-lookup"><span data-stu-id="f64c6-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="f64c6-127">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-127">string</span></span> | <span data-ttu-id="f64c6-128">Исходная папка, содержащая файл перед примененным записанным действием</span><span class="sxs-lookup"><span data-stu-id="f64c6-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="f64c6-129">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-129">string</span></span> | <span data-ttu-id="f64c6-130">Используемый сетевой протокол</span><span class="sxs-lookup"><span data-stu-id="f64c6-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="f64c6-131">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-131">string</span></span> | <span data-ttu-id="f64c6-132">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="f64c6-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f64c6-133">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-133">string</span></span> | <span data-ttu-id="f64c6-134">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="f64c6-134">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="f64c6-135">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-135">string</span></span> | <span data-ttu-id="f64c6-136">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="f64c6-136">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="f64c6-137">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-137">string</span></span> | <span data-ttu-id="f64c6-138">Имя пользователя-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="f64c6-138">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f64c6-139">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-139">string</span></span> | <span data-ttu-id="f64c6-140">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="f64c6-140">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f64c6-141">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-141">string</span></span> | <span data-ttu-id="f64c6-142">Имя пользователя учетной записи, отображаемой в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="f64c6-142">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f64c6-143">Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="f64c6-143">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="f64c6-144">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-144">string</span></span> | <span data-ttu-id="f64c6-145">Полное доменное имя устройства</span><span class="sxs-lookup"><span data-stu-id="f64c6-145">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="f64c6-146">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-146">string</span></span> | <span data-ttu-id="f64c6-147">Тип устройства</span><span class="sxs-lookup"><span data-stu-id="f64c6-147">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="f64c6-148">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-148">string</span></span> | <span data-ttu-id="f64c6-149">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="f64c6-149">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f64c6-150">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f64c6-150">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="f64c6-151">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-151">string</span></span> | <span data-ttu-id="f64c6-152">IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях</span><span class="sxs-lookup"><span data-stu-id="f64c6-152">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="f64c6-153">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-153">string</span></span> | <span data-ttu-id="f64c6-154">TCP-порт, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="f64c6-154">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="f64c6-155">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-155">string</span></span> | <span data-ttu-id="f64c6-156">Имя устройства, на которое запущено серверное приложение, обрабатывающее записанное действие</span><span class="sxs-lookup"><span data-stu-id="f64c6-156">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="f64c6-157">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-157">string</span></span> | <span data-ttu-id="f64c6-158">IP-адрес устройства, на которое запущено серверное приложение, обрабатывающее записанное действие</span><span class="sxs-lookup"><span data-stu-id="f64c6-158">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="f64c6-159">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-159">string</span></span> | <span data-ttu-id="f64c6-160">Порт назначения связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="f64c6-160">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="f64c6-161">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-161">string</span></span> | <span data-ttu-id="f64c6-162">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="f64c6-162">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="f64c6-163">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-163">string</span></span> | <span data-ttu-id="f64c6-164">Поставщик услуг Интернета, связанный с IP-адресом конечной точки</span><span class="sxs-lookup"><span data-stu-id="f64c6-164">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="f64c6-165">long</span><span class="sxs-lookup"><span data-stu-id="f64c6-165">long</span></span> | <span data-ttu-id="f64c6-166">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f64c6-166">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="f64c6-167">string</span><span class="sxs-lookup"><span data-stu-id="f64c6-167">string</span></span> | <span data-ttu-id="f64c6-168">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="f64c6-168">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f64c6-169">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="f64c6-169">Related topics</span></span>
- [<span data-ttu-id="f64c6-170">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="f64c6-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f64c6-171">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="f64c6-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f64c6-172">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="f64c6-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f64c6-173">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="f64c6-173">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f64c6-174">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="f64c6-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f64c6-175">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="f64c6-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
