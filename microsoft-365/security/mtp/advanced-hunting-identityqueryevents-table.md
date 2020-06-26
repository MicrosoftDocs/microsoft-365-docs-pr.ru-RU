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
ms.openlocfilehash: bec7f13d49e2ccf4e3a9121d5e5a2fecd1b10aa2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899117"
---
# <a name="identityqueryevents"></a><span data-ttu-id="3e151-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="3e151-104">IdentityQueryEvents</span></span>

<span data-ttu-id="3e151-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3e151-105">**Applies to:**</span></span>
- <span data-ttu-id="3e151-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3e151-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3e151-107">`IdentityQueryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о запросах, выполненных для объектов Active Directory, таких как пользователи, группы, устройства и домены.</span><span class="sxs-lookup"><span data-stu-id="3e151-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="3e151-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="3e151-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="3e151-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="3e151-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3e151-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="3e151-110">Column name</span></span> | <span data-ttu-id="3e151-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3e151-111">Data type</span></span> | <span data-ttu-id="3e151-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3e151-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3e151-113">datetime</span><span class="sxs-lookup"><span data-stu-id="3e151-113">datetime</span></span> | <span data-ttu-id="3e151-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="3e151-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="3e151-115">string</span><span class="sxs-lookup"><span data-stu-id="3e151-115">string</span></span> | <span data-ttu-id="3e151-116">Тип действия, вызвавшего событие</span><span class="sxs-lookup"><span data-stu-id="3e151-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="3e151-117">string</span><span class="sxs-lookup"><span data-stu-id="3e151-117">string</span></span> | <span data-ttu-id="3e151-118">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="3e151-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="3e151-119">string</span><span class="sxs-lookup"><span data-stu-id="3e151-119">string</span></span> | <span data-ttu-id="3e151-120">Тип запроса: Куериграуп, Куерюсер или Енумератеусерс</span><span class="sxs-lookup"><span data-stu-id="3e151-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="3e151-121">string</span><span class="sxs-lookup"><span data-stu-id="3e151-121">string</span></span> | <span data-ttu-id="3e151-122">Имя пользователя, группы, устройства, домена или любого другого типа сущностей, запрашиваемых</span><span class="sxs-lookup"><span data-stu-id="3e151-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="3e151-123">string</span><span class="sxs-lookup"><span data-stu-id="3e151-123">string</span></span> | <span data-ttu-id="3e151-124">Протокол, используемый при обмене данными</span><span class="sxs-lookup"><span data-stu-id="3e151-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="3e151-125">string</span><span class="sxs-lookup"><span data-stu-id="3e151-125">string</span></span> | <span data-ttu-id="3e151-126">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="3e151-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="3e151-127">string</span><span class="sxs-lookup"><span data-stu-id="3e151-127">string</span></span> | <span data-ttu-id="3e151-128">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="3e151-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="3e151-129">string</span><span class="sxs-lookup"><span data-stu-id="3e151-129">string</span></span> | <span data-ttu-id="3e151-130">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="3e151-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="3e151-131">string</span><span class="sxs-lookup"><span data-stu-id="3e151-131">string</span></span> | <span data-ttu-id="3e151-132">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="3e151-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="3e151-133">string</span><span class="sxs-lookup"><span data-stu-id="3e151-133">string</span></span> | <span data-ttu-id="3e151-134">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e151-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="3e151-135">string</span><span class="sxs-lookup"><span data-stu-id="3e151-135">string</span></span> | <span data-ttu-id="3e151-136">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="3e151-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="3e151-137">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="3e151-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="3e151-138">string</span><span class="sxs-lookup"><span data-stu-id="3e151-138">string</span></span> | <span data-ttu-id="3e151-139">Полное доменное имя (FQDN) конечной точки</span><span class="sxs-lookup"><span data-stu-id="3e151-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="3e151-140">string</span><span class="sxs-lookup"><span data-stu-id="3e151-140">string</span></span> | <span data-ttu-id="3e151-141">IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="3e151-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="3e151-142">string</span><span class="sxs-lookup"><span data-stu-id="3e151-142">string</span></span> | <span data-ttu-id="3e151-143">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="3e151-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3e151-144">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3e151-144">Related topics</span></span>
- [<span data-ttu-id="3e151-145">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="3e151-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3e151-146">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="3e151-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3e151-147">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="3e151-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3e151-148">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="3e151-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3e151-149">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="3e151-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3e151-150">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="3e151-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
