---
title: Таблица IdentityQueryEvents в продвинутой схеме охоты
description: Дополнительные данные о событиях запросов Active Directory в таблице IdentityQueryEvents в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, таблица, столбец, тип данных, описание, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identitys, LDAP-запросы
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
ms.openlocfilehash: 40383524ffe26326800369570856499d149e31c3
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500392"
---
# <a name="identityqueryevents"></a><span data-ttu-id="335e8-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="335e8-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="335e8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="335e8-105">**Applies to:**</span></span>
- <span data-ttu-id="335e8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="335e8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="335e8-107">Таблица в продвинутой схеме охоты содержит сведения о запросах, выполняемых в отношении объектов Active Directory, таких как `IdentityQueryEvents` пользователи, группы, устройства и [](advanced-hunting-overview.md) домены.</span><span class="sxs-lookup"><span data-stu-id="335e8-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="335e8-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="335e8-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="335e8-109">Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="335e8-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="335e8-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="335e8-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="335e8-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="335e8-111">Column name</span></span> | <span data-ttu-id="335e8-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="335e8-112">Data type</span></span> | <span data-ttu-id="335e8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="335e8-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="335e8-114">datetime</span><span class="sxs-lookup"><span data-stu-id="335e8-114">datetime</span></span> | <span data-ttu-id="335e8-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="335e8-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="335e8-116">string</span><span class="sxs-lookup"><span data-stu-id="335e8-116">string</span></span> | <span data-ttu-id="335e8-117">Тип действий, которые вызвали событие.</span><span class="sxs-lookup"><span data-stu-id="335e8-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="335e8-118">Подробные [сведения см. в](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) справке по схеме на портале</span><span class="sxs-lookup"><span data-stu-id="335e8-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="335e8-119">string</span><span class="sxs-lookup"><span data-stu-id="335e8-119">string</span></span> | <span data-ttu-id="335e8-120">Приложение, которое выполнило записанную акцию</span><span class="sxs-lookup"><span data-stu-id="335e8-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="335e8-121">string</span><span class="sxs-lookup"><span data-stu-id="335e8-121">string</span></span> | <span data-ttu-id="335e8-122">Тип запроса, например QueryGroup, QueryUser или EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="335e8-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="335e8-123">string</span><span class="sxs-lookup"><span data-stu-id="335e8-123">string</span></span> | <span data-ttu-id="335e8-124">Имя пользователя, группы, устройства, домена или любого другого типа объекта, запрашиваемого</span><span class="sxs-lookup"><span data-stu-id="335e8-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="335e8-125">string</span><span class="sxs-lookup"><span data-stu-id="335e8-125">string</span></span> | <span data-ttu-id="335e8-126">Строка, используемая для выполнения запроса</span><span class="sxs-lookup"><span data-stu-id="335e8-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="335e8-127">string</span><span class="sxs-lookup"><span data-stu-id="335e8-127">string</span></span> | <span data-ttu-id="335e8-128">Протокол, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="335e8-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="335e8-129">string</span><span class="sxs-lookup"><span data-stu-id="335e8-129">string</span></span> | <span data-ttu-id="335e8-130">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="335e8-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="335e8-131">string</span><span class="sxs-lookup"><span data-stu-id="335e8-131">string</span></span> | <span data-ttu-id="335e8-132">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="335e8-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="335e8-133">string</span><span class="sxs-lookup"><span data-stu-id="335e8-133">string</span></span> | <span data-ttu-id="335e8-134">Основное имя пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="335e8-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="335e8-135">string</span><span class="sxs-lookup"><span data-stu-id="335e8-135">string</span></span> | <span data-ttu-id="335e8-136">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="335e8-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="335e8-137">string</span><span class="sxs-lookup"><span data-stu-id="335e8-137">string</span></span> | <span data-ttu-id="335e8-138">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="335e8-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="335e8-139">string</span><span class="sxs-lookup"><span data-stu-id="335e8-139">string</span></span> | <span data-ttu-id="335e8-140">Имя пользователя учетной записи, отображаемого в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="335e8-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="335e8-141">Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="335e8-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="335e8-142">string</span><span class="sxs-lookup"><span data-stu-id="335e8-142">string</span></span> | <span data-ttu-id="335e8-143">Полное доменное имя (FQDN) конечной точки</span><span class="sxs-lookup"><span data-stu-id="335e8-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="335e8-144">string</span><span class="sxs-lookup"><span data-stu-id="335e8-144">string</span></span> | <span data-ttu-id="335e8-145">IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="335e8-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="335e8-146">string</span><span class="sxs-lookup"><span data-stu-id="335e8-146">string</span></span> | <span data-ttu-id="335e8-147">Порт TCP, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="335e8-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="335e8-148">string</span><span class="sxs-lookup"><span data-stu-id="335e8-148">string</span></span> | <span data-ttu-id="335e8-149">Имя устройства под управлением серверного приложения, обрабатываемого записанным действием</span><span class="sxs-lookup"><span data-stu-id="335e8-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="335e8-150">string</span><span class="sxs-lookup"><span data-stu-id="335e8-150">string</span></span> | <span data-ttu-id="335e8-151">IP-адрес устройства под управлением серверного приложения, обработав записанное действие</span><span class="sxs-lookup"><span data-stu-id="335e8-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="335e8-152">string</span><span class="sxs-lookup"><span data-stu-id="335e8-152">string</span></span> | <span data-ttu-id="335e8-153">Порт назначения связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="335e8-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="335e8-154">string</span><span class="sxs-lookup"><span data-stu-id="335e8-154">string</span></span> | <span data-ttu-id="335e8-155">Полное доменное имя (FQDN) устройства, на которое было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="335e8-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="335e8-156">string</span><span class="sxs-lookup"><span data-stu-id="335e8-156">string</span></span> | <span data-ttu-id="335e8-157">Основное имя пользователя (UPN) учетной записи, к</span><span class="sxs-lookup"><span data-stu-id="335e8-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="335e8-158">string</span><span class="sxs-lookup"><span data-stu-id="335e8-158">string</span></span> | <span data-ttu-id="335e8-159">Отображение имени учетной записи, к которую было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="335e8-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="335e8-160">string</span><span class="sxs-lookup"><span data-stu-id="335e8-160">string</span></span> | <span data-ttu-id="335e8-161">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="335e8-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="335e8-162">long</span><span class="sxs-lookup"><span data-stu-id="335e8-162">long</span></span> | <span data-ttu-id="335e8-163">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="335e8-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="335e8-164">string</span><span class="sxs-lookup"><span data-stu-id="335e8-164">string</span></span> | <span data-ttu-id="335e8-165">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="335e8-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="335e8-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="335e8-166">Related topics</span></span>
- [<span data-ttu-id="335e8-167">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="335e8-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="335e8-168">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="335e8-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="335e8-169">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="335e8-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="335e8-170">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="335e8-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="335e8-171">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="335e8-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="335e8-172">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="335e8-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
