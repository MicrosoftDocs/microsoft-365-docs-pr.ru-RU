---
title: Таблица идентитикуеревентс в схеме расширенного поискового окна
description: Сведения о событиях запросов Active Directory в таблице Идентитикуеревентс расширенной схемы поиска
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Идентитикуеревентс, Azure AD, Active Directory, Azure ATP, удостоверения, запросы LDAP
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: d6650a36d07427df6148d43894cc8aaa845faf05
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412710"
---
# <a name="identityqueryevents"></a><span data-ttu-id="b44ad-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="b44ad-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b44ad-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b44ad-105">**Applies to:**</span></span>
- <span data-ttu-id="b44ad-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b44ad-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b44ad-107">`IdentityQueryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о запросах, выполненных для объектов Active Directory, таких как пользователи, группы, устройства и домены.</span><span class="sxs-lookup"><span data-stu-id="b44ad-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="b44ad-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b44ad-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="b44ad-109">Для получения подробных сведений о типах событий ( `ActionType` значений), поддерживаемых таблицей, используйте [встроенную справочную](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) информацию о схеме, доступную в центре обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b44ad-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="b44ad-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b44ad-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b44ad-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="b44ad-111">Column name</span></span> | <span data-ttu-id="b44ad-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b44ad-112">Data type</span></span> | <span data-ttu-id="b44ad-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b44ad-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b44ad-114">datetime</span><span class="sxs-lookup"><span data-stu-id="b44ad-114">datetime</span></span> | <span data-ttu-id="b44ad-115">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="b44ad-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="b44ad-116">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-116">string</span></span> | <span data-ttu-id="b44ad-117">Тип действия, вызвавшего событие.</span><span class="sxs-lookup"><span data-stu-id="b44ad-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="b44ad-118">Дополнительные сведения см. [в справочнике по схемам на портале](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="b44ad-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="b44ad-119">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-119">string</span></span> | <span data-ttu-id="b44ad-120">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="b44ad-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="b44ad-121">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-121">string</span></span> | <span data-ttu-id="b44ad-122">Тип запроса, например Куериграуп, Куерюсер или Енумератеусерс</span><span class="sxs-lookup"><span data-stu-id="b44ad-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="b44ad-123">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-123">string</span></span> | <span data-ttu-id="b44ad-124">Имя пользователя, группы, устройства, домена или любого другого типа сущностей, запрашиваемых</span><span class="sxs-lookup"><span data-stu-id="b44ad-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="b44ad-125">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-125">string</span></span> | <span data-ttu-id="b44ad-126">Строка, используемая для выполнения запроса</span><span class="sxs-lookup"><span data-stu-id="b44ad-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="b44ad-127">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-127">string</span></span> | <span data-ttu-id="b44ad-128">Протокол, используемый при обмене данными</span><span class="sxs-lookup"><span data-stu-id="b44ad-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="b44ad-129">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-129">string</span></span> | <span data-ttu-id="b44ad-130">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="b44ad-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="b44ad-131">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-131">string</span></span> | <span data-ttu-id="b44ad-132">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="b44ad-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="b44ad-133">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-133">string</span></span> | <span data-ttu-id="b44ad-134">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="b44ad-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="b44ad-135">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-135">string</span></span> | <span data-ttu-id="b44ad-136">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="b44ad-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="b44ad-137">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-137">string</span></span> | <span data-ttu-id="b44ad-138">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="b44ad-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="b44ad-139">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-139">string</span></span> | <span data-ttu-id="b44ad-140">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="b44ad-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="b44ad-141">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="b44ad-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="b44ad-142">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-142">string</span></span> | <span data-ttu-id="b44ad-143">Полное доменное имя (FQDN) конечной точки</span><span class="sxs-lookup"><span data-stu-id="b44ad-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="b44ad-144">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-144">string</span></span> | <span data-ttu-id="b44ad-145">IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="b44ad-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="b44ad-146">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-146">string</span></span> | <span data-ttu-id="b44ad-147">Имя устройства, на котором работает серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="b44ad-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="b44ad-148">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-148">string</span></span> | <span data-ttu-id="b44ad-149">IP-адрес устройства, на котором запущено серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="b44ad-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="b44ad-150">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-150">string</span></span> | <span data-ttu-id="b44ad-151">Полное доменное имя (FQDN) устройства, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="b44ad-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="b44ad-152">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-152">string</span></span> | <span data-ttu-id="b44ad-153">Имя участника-пользователя (UPN) учетной записи, к которой было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="b44ad-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="b44ad-154">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-154">string</span></span> | <span data-ttu-id="b44ad-155">Отображаемое имя учетной записи, к которой было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="b44ad-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="b44ad-156">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-156">string</span></span> | <span data-ttu-id="b44ad-157">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="b44ad-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="b44ad-158">long</span><span class="sxs-lookup"><span data-stu-id="b44ad-158">long</span></span> | <span data-ttu-id="b44ad-159">Уникальный идентификатор для события</span><span class="sxs-lookup"><span data-stu-id="b44ad-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="b44ad-160">string</span><span class="sxs-lookup"><span data-stu-id="b44ad-160">string</span></span> | <span data-ttu-id="b44ad-161">Дополнительные сведения о сущности или событии</span><span class="sxs-lookup"><span data-stu-id="b44ad-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b44ad-162">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b44ad-162">Related topics</span></span>
- [<span data-ttu-id="b44ad-163">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="b44ad-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b44ad-164">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="b44ad-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b44ad-165">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="b44ad-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b44ad-166">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="b44ad-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b44ad-167">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="b44ad-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b44ad-168">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="b44ad-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
