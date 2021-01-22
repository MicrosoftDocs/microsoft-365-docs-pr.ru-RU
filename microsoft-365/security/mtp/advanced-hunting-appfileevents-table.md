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
ms.openlocfilehash: 59e9affc53398f2a1b06fbab9774e4b53e146425
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932878"
---
# <a name="appfileevents"></a><span data-ttu-id="3c20e-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="3c20e-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3c20e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3c20e-105">**Applies to:**</span></span>
- <span data-ttu-id="3c20e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c20e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3c20e-107">Таблица в схеме advanced hunting содержит сведения о действиях, связанных с файлами, в облачных приложениях и службах, `AppFileEvents` отслеживаемом Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3c20e-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="3c20e-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="3c20e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="3c20e-109">Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="3c20e-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="3c20e-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="3c20e-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3c20e-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="3c20e-111">Column name</span></span> | <span data-ttu-id="3c20e-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3c20e-112">Data type</span></span> | <span data-ttu-id="3c20e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3c20e-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3c20e-114">datetime</span><span class="sxs-lookup"><span data-stu-id="3c20e-114">datetime</span></span> | <span data-ttu-id="3c20e-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="3c20e-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="3c20e-116">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-116">string</span></span> | <span data-ttu-id="3c20e-117">Тип действия, которое вызвало событие.</span><span class="sxs-lookup"><span data-stu-id="3c20e-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="3c20e-118">Подробные сведения см. в справке [по схеме портала](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="3c20e-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="3c20e-119">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-119">string</span></span> | <span data-ttu-id="3c20e-120">Приложение, которое выполнило записанную действие</span><span class="sxs-lookup"><span data-stu-id="3c20e-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="3c20e-121">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-121">string</span></span> | <span data-ttu-id="3c20e-122">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="3c20e-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="3c20e-123">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-123">string</span></span> | <span data-ttu-id="3c20e-124">Папка, содержащая файл, к которой было применено записано действие</span><span class="sxs-lookup"><span data-stu-id="3c20e-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="3c20e-125">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-125">string</span></span> | <span data-ttu-id="3c20e-126">Исходное имя файла, переименованного в результате действия</span><span class="sxs-lookup"><span data-stu-id="3c20e-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="3c20e-127">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-127">string</span></span> | <span data-ttu-id="3c20e-128">Исходная папка, содержащая файл перед примененным записанным действием</span><span class="sxs-lookup"><span data-stu-id="3c20e-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="3c20e-129">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-129">string</span></span> | <span data-ttu-id="3c20e-130">Используемый сетевой протокол</span><span class="sxs-lookup"><span data-stu-id="3c20e-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="3c20e-131">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-131">string</span></span> | <span data-ttu-id="3c20e-132">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="3c20e-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="3c20e-133">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-133">string</span></span> | <span data-ttu-id="3c20e-134">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="3c20e-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="3c20e-135">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-135">string</span></span> | <span data-ttu-id="3c20e-136">Имя пользователя-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="3c20e-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="3c20e-137">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-137">string</span></span> | <span data-ttu-id="3c20e-138">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="3c20e-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="3c20e-139">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-139">string</span></span> | <span data-ttu-id="3c20e-140">Имя пользователя учетной записи, отображаемой в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="3c20e-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="3c20e-141">Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="3c20e-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="3c20e-142">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-142">string</span></span> | <span data-ttu-id="3c20e-143">Полное доменное имя устройства</span><span class="sxs-lookup"><span data-stu-id="3c20e-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="3c20e-144">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-144">string</span></span> | <span data-ttu-id="3c20e-145">Тип устройства</span><span class="sxs-lookup"><span data-stu-id="3c20e-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="3c20e-146">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-146">string</span></span> | <span data-ttu-id="3c20e-147">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="3c20e-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="3c20e-148">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="3c20e-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="3c20e-149">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-149">string</span></span> | <span data-ttu-id="3c20e-150">IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях</span><span class="sxs-lookup"><span data-stu-id="3c20e-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="3c20e-151">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-151">string</span></span> | <span data-ttu-id="3c20e-152">Имя устройства, на которое запущено серверное приложение, обрабатывающее записанное действие</span><span class="sxs-lookup"><span data-stu-id="3c20e-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="3c20e-153">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-153">string</span></span> | <span data-ttu-id="3c20e-154">IP-адрес устройства, на которое запущено серверное приложение, обрабатывающее записанное действие</span><span class="sxs-lookup"><span data-stu-id="3c20e-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="3c20e-155">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-155">string</span></span> | <span data-ttu-id="3c20e-156">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="3c20e-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="3c20e-157">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-157">string</span></span> | <span data-ttu-id="3c20e-158">Поставщик услуг Интернета, связанный с IP-адресом конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c20e-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="3c20e-159">long</span><span class="sxs-lookup"><span data-stu-id="3c20e-159">long</span></span> | <span data-ttu-id="3c20e-160">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="3c20e-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="3c20e-161">string</span><span class="sxs-lookup"><span data-stu-id="3c20e-161">string</span></span> | <span data-ttu-id="3c20e-162">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="3c20e-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3c20e-163">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3c20e-163">Related topics</span></span>
- [<span data-ttu-id="3c20e-164">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="3c20e-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3c20e-165">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="3c20e-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3c20e-166">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="3c20e-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3c20e-167">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="3c20e-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3c20e-168">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="3c20e-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3c20e-169">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="3c20e-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
