---
title: Таблица аппфиливентс в схеме расширенного поискового окна
description: Сведения о событиях, связанных с файлами, связанными с облачными приложениями и службами, в таблице Аппфиливентс расширенной схемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Аппфиливентс, безопасность облачных приложений, МКАС
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
ms.openlocfilehash: 5cab6e3fe7a3b4b74989dde360c03d58e0bad46f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430155"
---
# <a name="appfileevents"></a><span data-ttu-id="b966c-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="b966c-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b966c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b966c-105">**Applies to:**</span></span>
- <span data-ttu-id="b966c-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b966c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b966c-107">`AppFileEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о действиях, связанных с файлами, в облачных приложениях и службах, отслеживаемых Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="b966c-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="b966c-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b966c-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="b966c-109">Для получения подробных сведений о типах событий ( `ActionType` значений), поддерживаемых таблицей, используйте [встроенную справочную](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) информацию о схеме, доступную в центре обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b966c-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="b966c-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b966c-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b966c-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="b966c-111">Column name</span></span> | <span data-ttu-id="b966c-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b966c-112">Data type</span></span> | <span data-ttu-id="b966c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b966c-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b966c-114">datetime</span><span class="sxs-lookup"><span data-stu-id="b966c-114">datetime</span></span> | <span data-ttu-id="b966c-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="b966c-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="b966c-116">string</span><span class="sxs-lookup"><span data-stu-id="b966c-116">string</span></span> | <span data-ttu-id="b966c-117">Тип действия, вызвавшего событие.</span><span class="sxs-lookup"><span data-stu-id="b966c-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="b966c-118">Дополнительные сведения см. [в справочнике по схемам на портале](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="b966c-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="b966c-119">string</span><span class="sxs-lookup"><span data-stu-id="b966c-119">string</span></span> | <span data-ttu-id="b966c-120">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="b966c-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="b966c-121">string</span><span class="sxs-lookup"><span data-stu-id="b966c-121">string</span></span> | <span data-ttu-id="b966c-122">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="b966c-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="b966c-123">string</span><span class="sxs-lookup"><span data-stu-id="b966c-123">string</span></span> | <span data-ttu-id="b966c-124">Папка, содержащая файл, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="b966c-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="b966c-125">string</span><span class="sxs-lookup"><span data-stu-id="b966c-125">string</span></span> | <span data-ttu-id="b966c-126">Исходное имя файла, переименованного в результате действия</span><span class="sxs-lookup"><span data-stu-id="b966c-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="b966c-127">string</span><span class="sxs-lookup"><span data-stu-id="b966c-127">string</span></span> | <span data-ttu-id="b966c-128">Исходная папка, содержащая файл перед применением записанного действия</span><span class="sxs-lookup"><span data-stu-id="b966c-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="b966c-129">string</span><span class="sxs-lookup"><span data-stu-id="b966c-129">string</span></span> | <span data-ttu-id="b966c-130">Используемый сетевой протокол</span><span class="sxs-lookup"><span data-stu-id="b966c-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="b966c-131">string</span><span class="sxs-lookup"><span data-stu-id="b966c-131">string</span></span> | <span data-ttu-id="b966c-132">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="b966c-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="b966c-133">string</span><span class="sxs-lookup"><span data-stu-id="b966c-133">string</span></span> | <span data-ttu-id="b966c-134">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="b966c-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="b966c-135">string</span><span class="sxs-lookup"><span data-stu-id="b966c-135">string</span></span> | <span data-ttu-id="b966c-136">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="b966c-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="b966c-137">string</span><span class="sxs-lookup"><span data-stu-id="b966c-137">string</span></span> | <span data-ttu-id="b966c-138">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="b966c-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="b966c-139">string</span><span class="sxs-lookup"><span data-stu-id="b966c-139">string</span></span> | <span data-ttu-id="b966c-140">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="b966c-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="b966c-141">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="b966c-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="b966c-142">string</span><span class="sxs-lookup"><span data-stu-id="b966c-142">string</span></span> | <span data-ttu-id="b966c-143">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="b966c-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="b966c-144">string</span><span class="sxs-lookup"><span data-stu-id="b966c-144">string</span></span> | <span data-ttu-id="b966c-145">Тип устройства</span><span class="sxs-lookup"><span data-stu-id="b966c-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="b966c-146">string</span><span class="sxs-lookup"><span data-stu-id="b966c-146">string</span></span> | <span data-ttu-id="b966c-147">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b966c-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="b966c-148">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b966c-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="b966c-149">string</span><span class="sxs-lookup"><span data-stu-id="b966c-149">string</span></span> | <span data-ttu-id="b966c-150">IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="b966c-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="b966c-151">string</span><span class="sxs-lookup"><span data-stu-id="b966c-151">string</span></span> | <span data-ttu-id="b966c-152">Имя устройства, на котором работает серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="b966c-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="b966c-153">string</span><span class="sxs-lookup"><span data-stu-id="b966c-153">string</span></span> | <span data-ttu-id="b966c-154">IP-адрес устройства, на котором запущено серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="b966c-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="b966c-155">string</span><span class="sxs-lookup"><span data-stu-id="b966c-155">string</span></span> | <span data-ttu-id="b966c-156">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="b966c-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="b966c-157">string</span><span class="sxs-lookup"><span data-stu-id="b966c-157">string</span></span> | <span data-ttu-id="b966c-158">Поставщик услуг Интернета (ISP), связанный с IP-адресом конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b966c-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="b966c-159">long</span><span class="sxs-lookup"><span data-stu-id="b966c-159">long</span></span> | <span data-ttu-id="b966c-160">Уникальный идентификатор для события</span><span class="sxs-lookup"><span data-stu-id="b966c-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="b966c-161">string</span><span class="sxs-lookup"><span data-stu-id="b966c-161">string</span></span> | <span data-ttu-id="b966c-162">Дополнительные сведения о сущности или событии</span><span class="sxs-lookup"><span data-stu-id="b966c-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b966c-163">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b966c-163">Related topics</span></span>
- [<span data-ttu-id="b966c-164">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="b966c-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b966c-165">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="b966c-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b966c-166">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="b966c-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b966c-167">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="b966c-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b966c-168">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="b966c-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b966c-169">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="b966c-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
