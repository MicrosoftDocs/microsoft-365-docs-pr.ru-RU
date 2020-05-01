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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929271"
---
# <a name="identityqueryevents"></a><span data-ttu-id="152b9-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="152b9-104">IdentityQueryEvents</span></span>

<span data-ttu-id="152b9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="152b9-105">**Applies to:**</span></span>
- <span data-ttu-id="152b9-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="152b9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="152b9-107">`IdentityQueryEvents` Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о запросах, выполненных для объектов Active Directory, таких как пользователи, группы, устройства и домены.</span><span class="sxs-lookup"><span data-stu-id="152b9-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="152b9-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="152b9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="152b9-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="152b9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="152b9-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="152b9-110">Column name</span></span> | <span data-ttu-id="152b9-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="152b9-111">Data type</span></span> | <span data-ttu-id="152b9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="152b9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="152b9-113">datetime</span><span class="sxs-lookup"><span data-stu-id="152b9-113">datetime</span></span> | <span data-ttu-id="152b9-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="152b9-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="152b9-115">string</span><span class="sxs-lookup"><span data-stu-id="152b9-115">string</span></span> | <span data-ttu-id="152b9-116">Тип действия, вызвавшего событие</span><span class="sxs-lookup"><span data-stu-id="152b9-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="152b9-117">string</span><span class="sxs-lookup"><span data-stu-id="152b9-117">string</span></span> | <span data-ttu-id="152b9-118">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="152b9-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="152b9-119">string</span><span class="sxs-lookup"><span data-stu-id="152b9-119">string</span></span> | <span data-ttu-id="152b9-120">Тип запроса: Куериграуп, Куерюсер или Енумератеусерс</span><span class="sxs-lookup"><span data-stu-id="152b9-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="152b9-121">string</span><span class="sxs-lookup"><span data-stu-id="152b9-121">string</span></span> | <span data-ttu-id="152b9-122">Имя пользователя, группы, устройства, домена или любого другого типа сущностей, запрашиваемых</span><span class="sxs-lookup"><span data-stu-id="152b9-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="152b9-123">string</span><span class="sxs-lookup"><span data-stu-id="152b9-123">string</span></span> | <span data-ttu-id="152b9-124">Протокол, используемый при обмене данными</span><span class="sxs-lookup"><span data-stu-id="152b9-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="152b9-125">string</span><span class="sxs-lookup"><span data-stu-id="152b9-125">string</span></span> | <span data-ttu-id="152b9-126">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="152b9-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="152b9-127">string</span><span class="sxs-lookup"><span data-stu-id="152b9-127">string</span></span> | <span data-ttu-id="152b9-128">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="152b9-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="152b9-129">string</span><span class="sxs-lookup"><span data-stu-id="152b9-129">string</span></span> | <span data-ttu-id="152b9-130">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="152b9-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="152b9-131">string</span><span class="sxs-lookup"><span data-stu-id="152b9-131">string</span></span> | <span data-ttu-id="152b9-132">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="152b9-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="152b9-133">string</span><span class="sxs-lookup"><span data-stu-id="152b9-133">string</span></span> | <span data-ttu-id="152b9-134">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="152b9-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="152b9-135">string</span><span class="sxs-lookup"><span data-stu-id="152b9-135">string</span></span> | <span data-ttu-id="152b9-136">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="152b9-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="152b9-137">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="152b9-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="152b9-138">string</span><span class="sxs-lookup"><span data-stu-id="152b9-138">string</span></span> | <span data-ttu-id="152b9-139">Полное доменное имя (FQDN) конечной точки</span><span class="sxs-lookup"><span data-stu-id="152b9-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="152b9-140">string</span><span class="sxs-lookup"><span data-stu-id="152b9-140">string</span></span> | <span data-ttu-id="152b9-141">IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="152b9-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="152b9-142">string</span><span class="sxs-lookup"><span data-stu-id="152b9-142">string</span></span> | <span data-ttu-id="152b9-143">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="152b9-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="152b9-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="152b9-144">Related topics</span></span>
- [<span data-ttu-id="152b9-145">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="152b9-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="152b9-146">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="152b9-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="152b9-147">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="152b9-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="152b9-148">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="152b9-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="152b9-149">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="152b9-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="152b9-150">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="152b9-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
