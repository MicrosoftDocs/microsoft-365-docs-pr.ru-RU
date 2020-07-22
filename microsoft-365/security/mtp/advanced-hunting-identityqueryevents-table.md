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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204879"
---
# <a name="identityqueryevents"></a><span data-ttu-id="4c7af-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="4c7af-104">IdentityQueryEvents</span></span>

<span data-ttu-id="4c7af-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4c7af-105">**Applies to:**</span></span>
- <span data-ttu-id="4c7af-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="4c7af-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4c7af-107">`IdentityQueryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о запросах, выполненных для объектов Active Directory, таких как пользователи, группы, устройства и домены.</span><span class="sxs-lookup"><span data-stu-id="4c7af-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="4c7af-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="4c7af-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4c7af-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="4c7af-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4c7af-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="4c7af-110">Column name</span></span> | <span data-ttu-id="4c7af-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="4c7af-111">Data type</span></span> | <span data-ttu-id="4c7af-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4c7af-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4c7af-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4c7af-113">datetime</span></span> | <span data-ttu-id="4c7af-114">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="4c7af-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="4c7af-115">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-115">string</span></span> | <span data-ttu-id="4c7af-116">Тип действия, вызвавшего событие</span><span class="sxs-lookup"><span data-stu-id="4c7af-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="4c7af-117">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-117">string</span></span> | <span data-ttu-id="4c7af-118">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="4c7af-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="4c7af-119">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-119">string</span></span> | <span data-ttu-id="4c7af-120">Тип запроса, например Куериграуп, Куерюсер или Енумератеусерс</span><span class="sxs-lookup"><span data-stu-id="4c7af-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="4c7af-121">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-121">string</span></span> | <span data-ttu-id="4c7af-122">Имя пользователя, группы, устройства, домена или любого другого типа сущностей, запрашиваемых</span><span class="sxs-lookup"><span data-stu-id="4c7af-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="4c7af-123">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-123">string</span></span> | <span data-ttu-id="4c7af-124">Строка, используемая для выполнения запроса</span><span class="sxs-lookup"><span data-stu-id="4c7af-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="4c7af-125">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-125">string</span></span> | <span data-ttu-id="4c7af-126">Протокол, используемый при обмене данными</span><span class="sxs-lookup"><span data-stu-id="4c7af-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="4c7af-127">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-127">string</span></span> | <span data-ttu-id="4c7af-128">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="4c7af-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="4c7af-129">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-129">string</span></span> | <span data-ttu-id="4c7af-130">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="4c7af-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="4c7af-131">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-131">string</span></span> | <span data-ttu-id="4c7af-132">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="4c7af-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="4c7af-133">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-133">string</span></span> | <span data-ttu-id="4c7af-134">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="4c7af-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="4c7af-135">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-135">string</span></span> | <span data-ttu-id="4c7af-136">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="4c7af-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="4c7af-137">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-137">string</span></span> | <span data-ttu-id="4c7af-138">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="4c7af-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="4c7af-139">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="4c7af-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="4c7af-140">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-140">string</span></span> | <span data-ttu-id="4c7af-141">Полное доменное имя (FQDN) конечной точки</span><span class="sxs-lookup"><span data-stu-id="4c7af-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="4c7af-142">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-142">string</span></span> | <span data-ttu-id="4c7af-143">IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="4c7af-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="4c7af-144">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-144">string</span></span> | <span data-ttu-id="4c7af-145">Имя устройства, на котором работает серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="4c7af-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="4c7af-146">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-146">string</span></span> | <span data-ttu-id="4c7af-147">IP-адрес устройства, на котором запущено серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="4c7af-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="4c7af-148">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-148">string</span></span> | <span data-ttu-id="4c7af-149">Полное доменное имя (FQDN) устройства, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="4c7af-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="4c7af-150">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-150">string</span></span> | <span data-ttu-id="4c7af-151">Имя участника-пользователя (UPN) учетной записи, к которой было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="4c7af-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="4c7af-152">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-152">string</span></span> | <span data-ttu-id="4c7af-153">Отображаемое имя учетной записи, к которой было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="4c7af-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="4c7af-154">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-154">string</span></span> | <span data-ttu-id="4c7af-155">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="4c7af-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="4c7af-156">long</span><span class="sxs-lookup"><span data-stu-id="4c7af-156">long</span></span> | <span data-ttu-id="4c7af-157">Уникальный идентификатор для события</span><span class="sxs-lookup"><span data-stu-id="4c7af-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="4c7af-158">string</span><span class="sxs-lookup"><span data-stu-id="4c7af-158">string</span></span> | <span data-ttu-id="4c7af-159">Дополнительные сведения о сущности или событии</span><span class="sxs-lookup"><span data-stu-id="4c7af-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4c7af-160">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="4c7af-160">Related topics</span></span>
- [<span data-ttu-id="4c7af-161">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="4c7af-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4c7af-162">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="4c7af-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4c7af-163">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="4c7af-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4c7af-164">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="4c7af-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4c7af-165">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="4c7af-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4c7af-166">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="4c7af-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
