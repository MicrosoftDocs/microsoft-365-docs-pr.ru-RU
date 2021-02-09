---
title: Таблица IdentityQueryEvents в схеме advanced hunting
description: Узнайте о событиях запросов Active Directory в таблице IdentityQueryEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identities, LDAP queries
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
ms.openlocfilehash: 48a1520e9fc6239fd3105f01a32a03e5e58df174
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145299"
---
# <a name="identityqueryevents"></a><span data-ttu-id="7efd9-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="7efd9-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7efd9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7efd9-105">**Applies to:**</span></span>
- <span data-ttu-id="7efd9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7efd9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7efd9-107">Таблица в схеме advanced hunting содержит сведения о запросах, выполняемых к объектам Active Directory, таким как `IdentityQueryEvents` пользователи, группы, устройства и [](advanced-hunting-overview.md) домены.</span><span class="sxs-lookup"><span data-stu-id="7efd9-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="7efd9-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="7efd9-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="7efd9-109">Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="7efd9-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="7efd9-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7efd9-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7efd9-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="7efd9-111">Column name</span></span> | <span data-ttu-id="7efd9-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7efd9-112">Data type</span></span> | <span data-ttu-id="7efd9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7efd9-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7efd9-114">datetime</span><span class="sxs-lookup"><span data-stu-id="7efd9-114">datetime</span></span> | <span data-ttu-id="7efd9-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="7efd9-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="7efd9-116">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-116">string</span></span> | <span data-ttu-id="7efd9-117">Тип действия, которое вызвало событие.</span><span class="sxs-lookup"><span data-stu-id="7efd9-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="7efd9-118">Подробные сведения см. в справке [по схеме портала](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="7efd9-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="7efd9-119">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-119">string</span></span> | <span data-ttu-id="7efd9-120">Приложение, которое выполнило записанную действие</span><span class="sxs-lookup"><span data-stu-id="7efd9-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="7efd9-121">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-121">string</span></span> | <span data-ttu-id="7efd9-122">Тип запроса, например QueryGroup, QueryUser или EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="7efd9-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="7efd9-123">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-123">string</span></span> | <span data-ttu-id="7efd9-124">Имя пользователя, группы, устройства, домена или любого другого типа объекта, для которого запрашивается</span><span class="sxs-lookup"><span data-stu-id="7efd9-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="7efd9-125">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-125">string</span></span> | <span data-ttu-id="7efd9-126">Строка, используемая для выполнения запроса</span><span class="sxs-lookup"><span data-stu-id="7efd9-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="7efd9-127">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-127">string</span></span> | <span data-ttu-id="7efd9-128">Протокол, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="7efd9-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="7efd9-129">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-129">string</span></span> | <span data-ttu-id="7efd9-130">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="7efd9-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7efd9-131">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-131">string</span></span> | <span data-ttu-id="7efd9-132">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="7efd9-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="7efd9-133">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-133">string</span></span> | <span data-ttu-id="7efd9-134">Имя пользователя-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="7efd9-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="7efd9-135">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-135">string</span></span> | <span data-ttu-id="7efd9-136">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="7efd9-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7efd9-137">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-137">string</span></span> | <span data-ttu-id="7efd9-138">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="7efd9-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7efd9-139">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-139">string</span></span> | <span data-ttu-id="7efd9-140">Имя пользователя учетной записи, отображаемой в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="7efd9-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7efd9-141">Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="7efd9-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="7efd9-142">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-142">string</span></span> | <span data-ttu-id="7efd9-143">Полное доменное имя конечной точки</span><span class="sxs-lookup"><span data-stu-id="7efd9-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="7efd9-144">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-144">string</span></span> | <span data-ttu-id="7efd9-145">IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях</span><span class="sxs-lookup"><span data-stu-id="7efd9-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="7efd9-146">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-146">string</span></span> | <span data-ttu-id="7efd9-147">TCP-порт, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="7efd9-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="7efd9-148">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-148">string</span></span> | <span data-ttu-id="7efd9-149">Имя устройства, на которое запущено серверное приложение, обрабатывающее записанное действие</span><span class="sxs-lookup"><span data-stu-id="7efd9-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="7efd9-150">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-150">string</span></span> | <span data-ttu-id="7efd9-151">IP-адрес устройства, на которое запущено серверное приложение, обрабатывающее записанное действие</span><span class="sxs-lookup"><span data-stu-id="7efd9-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="7efd9-152">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-152">string</span></span> | <span data-ttu-id="7efd9-153">Порт назначения связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="7efd9-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="7efd9-154">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-154">string</span></span> | <span data-ttu-id="7efd9-155">Полное доменное имя устройства, к которое было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="7efd9-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="7efd9-156">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-156">string</span></span> | <span data-ttu-id="7efd9-157">Имя пользователя-пользователя (UPN) учетной записи, к которую было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="7efd9-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="7efd9-158">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-158">string</span></span> | <span data-ttu-id="7efd9-159">Отображаемого имени учетной записи, к которую было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="7efd9-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="7efd9-160">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-160">string</span></span> | <span data-ttu-id="7efd9-161">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="7efd9-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="7efd9-162">long</span><span class="sxs-lookup"><span data-stu-id="7efd9-162">long</span></span> | <span data-ttu-id="7efd9-163">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7efd9-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="7efd9-164">string</span><span class="sxs-lookup"><span data-stu-id="7efd9-164">string</span></span> | <span data-ttu-id="7efd9-165">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="7efd9-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7efd9-166">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="7efd9-166">Related topics</span></span>
- [<span data-ttu-id="7efd9-167">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="7efd9-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7efd9-168">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="7efd9-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7efd9-169">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="7efd9-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7efd9-170">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="7efd9-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7efd9-171">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="7efd9-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7efd9-172">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="7efd9-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
