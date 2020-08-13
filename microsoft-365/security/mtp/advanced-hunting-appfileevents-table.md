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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4221af6b0378e67e12852dbef0bbc0a11ff56511
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649479"
---
# <a name="appfileevents"></a><span data-ttu-id="04a54-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="04a54-104">AppFileEvents</span></span>

<span data-ttu-id="04a54-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="04a54-105">**Applies to:**</span></span>
- <span data-ttu-id="04a54-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="04a54-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="04a54-107">`AppFileEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о действиях, связанных с файлами, в облачных приложениях и службах, отслеживаемых Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="04a54-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="04a54-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="04a54-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="04a54-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="04a54-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="04a54-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="04a54-110">Column name</span></span> | <span data-ttu-id="04a54-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="04a54-111">Data type</span></span> | <span data-ttu-id="04a54-112">Описание</span><span class="sxs-lookup"><span data-stu-id="04a54-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="04a54-113">datetime</span><span class="sxs-lookup"><span data-stu-id="04a54-113">datetime</span></span> | <span data-ttu-id="04a54-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="04a54-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="04a54-115">string</span><span class="sxs-lookup"><span data-stu-id="04a54-115">string</span></span> | <span data-ttu-id="04a54-116">Тип действия, вызвавшего событие</span><span class="sxs-lookup"><span data-stu-id="04a54-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="04a54-117">string</span><span class="sxs-lookup"><span data-stu-id="04a54-117">string</span></span> | <span data-ttu-id="04a54-118">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="04a54-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="04a54-119">string</span><span class="sxs-lookup"><span data-stu-id="04a54-119">string</span></span> | <span data-ttu-id="04a54-120">Имя файла, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="04a54-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="04a54-121">string</span><span class="sxs-lookup"><span data-stu-id="04a54-121">string</span></span> | <span data-ttu-id="04a54-122">Папка, содержащая файл, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="04a54-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="04a54-123">string</span><span class="sxs-lookup"><span data-stu-id="04a54-123">string</span></span> | <span data-ttu-id="04a54-124">Исходное имя файла, переименованного в результате действия</span><span class="sxs-lookup"><span data-stu-id="04a54-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="04a54-125">string</span><span class="sxs-lookup"><span data-stu-id="04a54-125">string</span></span> | <span data-ttu-id="04a54-126">Исходная папка, содержащая файл перед применением записанного действия</span><span class="sxs-lookup"><span data-stu-id="04a54-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="04a54-127">string</span><span class="sxs-lookup"><span data-stu-id="04a54-127">string</span></span> | <span data-ttu-id="04a54-128">Используемый сетевой протокол</span><span class="sxs-lookup"><span data-stu-id="04a54-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="04a54-129">string</span><span class="sxs-lookup"><span data-stu-id="04a54-129">string</span></span> | <span data-ttu-id="04a54-130">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="04a54-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="04a54-131">string</span><span class="sxs-lookup"><span data-stu-id="04a54-131">string</span></span> | <span data-ttu-id="04a54-132">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="04a54-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="04a54-133">string</span><span class="sxs-lookup"><span data-stu-id="04a54-133">string</span></span> | <span data-ttu-id="04a54-134">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="04a54-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="04a54-135">string</span><span class="sxs-lookup"><span data-stu-id="04a54-135">string</span></span> | <span data-ttu-id="04a54-136">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="04a54-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="04a54-137">string</span><span class="sxs-lookup"><span data-stu-id="04a54-137">string</span></span> | <span data-ttu-id="04a54-138">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="04a54-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="04a54-139">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="04a54-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="04a54-140">string</span><span class="sxs-lookup"><span data-stu-id="04a54-140">string</span></span> | <span data-ttu-id="04a54-141">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="04a54-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="04a54-142">string</span><span class="sxs-lookup"><span data-stu-id="04a54-142">string</span></span> | <span data-ttu-id="04a54-143">Тип устройства</span><span class="sxs-lookup"><span data-stu-id="04a54-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="04a54-144">string</span><span class="sxs-lookup"><span data-stu-id="04a54-144">string</span></span> | <span data-ttu-id="04a54-145">Платформа операционной системы, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="04a54-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="04a54-146">Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.</span><span class="sxs-lookup"><span data-stu-id="04a54-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="04a54-147">string</span><span class="sxs-lookup"><span data-stu-id="04a54-147">string</span></span> | <span data-ttu-id="04a54-148">IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="04a54-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="04a54-149">string</span><span class="sxs-lookup"><span data-stu-id="04a54-149">string</span></span> | <span data-ttu-id="04a54-150">Имя устройства, на котором работает серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="04a54-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="04a54-151">string</span><span class="sxs-lookup"><span data-stu-id="04a54-151">string</span></span> | <span data-ttu-id="04a54-152">IP-адрес устройства, на котором запущено серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="04a54-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="04a54-153">string</span><span class="sxs-lookup"><span data-stu-id="04a54-153">string</span></span> | <span data-ttu-id="04a54-154">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="04a54-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="04a54-155">string</span><span class="sxs-lookup"><span data-stu-id="04a54-155">string</span></span> | <span data-ttu-id="04a54-156">Поставщик услуг Интернета (ISP), связанный с IP-адресом конечной точки.</span><span class="sxs-lookup"><span data-stu-id="04a54-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="04a54-157">long</span><span class="sxs-lookup"><span data-stu-id="04a54-157">long</span></span> | <span data-ttu-id="04a54-158">Уникальный идентификатор для события</span><span class="sxs-lookup"><span data-stu-id="04a54-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="04a54-159">string</span><span class="sxs-lookup"><span data-stu-id="04a54-159">string</span></span> | <span data-ttu-id="04a54-160">Дополнительные сведения о сущности или событии</span><span class="sxs-lookup"><span data-stu-id="04a54-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="04a54-161">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="04a54-161">Related topics</span></span>
- [<span data-ttu-id="04a54-162">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="04a54-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="04a54-163">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="04a54-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="04a54-164">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="04a54-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="04a54-165">Слежение за устройствами, сообщениями электронной почты, приложениями и удостоверениями</span><span class="sxs-lookup"><span data-stu-id="04a54-165">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="04a54-166">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="04a54-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="04a54-167">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="04a54-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
