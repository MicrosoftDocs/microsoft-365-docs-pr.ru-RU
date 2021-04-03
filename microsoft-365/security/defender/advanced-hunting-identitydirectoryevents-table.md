---
title: Таблица IdentityDirectoryEvents в продвинутой схеме охоты
description: Узнайте о контроллере домена и событиях Active Directory в таблице IdentityDirectoryEvents продвинутой схемы охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, microsoft threat protection, microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка на схему, kusto, таблица, столбец, тип данных, описание, IdentityDirectoryEvents, контроллер домена, Active Directory, Azure ATP, удостоверения
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
ms.openlocfilehash: 73018bb65c011d10234ec9c02fc61bfb93fa125a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501129"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="99d51-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="99d51-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="99d51-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="99d51-105">**Applies to:**</span></span>
- <span data-ttu-id="99d51-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99d51-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="99d51-107">Таблица в продвинутой схеме охоты содержит события, включающие локального контроллера домена под `IdentityDirectoryEvents` управлением Active [](advanced-hunting-overview.md) Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="99d51-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="99d51-108">В этой таблице запечатлены различные события, связанные с удостоверением, такие как изменения пароля, истечение срока действия пароля и изменение основного имени пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="99d51-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="99d51-109">Он также фиксирует события системы на контроллере домена, например планирование задач и активность PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99d51-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="99d51-110">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="99d51-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="99d51-111">Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="99d51-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="99d51-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="99d51-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="99d51-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="99d51-113">Column name</span></span> | <span data-ttu-id="99d51-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="99d51-114">Data type</span></span> | <span data-ttu-id="99d51-115">Описание</span><span class="sxs-lookup"><span data-stu-id="99d51-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="99d51-116">datetime</span><span class="sxs-lookup"><span data-stu-id="99d51-116">datetime</span></span> | <span data-ttu-id="99d51-117">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="99d51-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="99d51-118">string</span><span class="sxs-lookup"><span data-stu-id="99d51-118">string</span></span> | <span data-ttu-id="99d51-119">Тип действий, которые вызвали событие.</span><span class="sxs-lookup"><span data-stu-id="99d51-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="99d51-120">Подробные [сведения см. в](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) справке по схеме на портале</span><span class="sxs-lookup"><span data-stu-id="99d51-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="99d51-121">string</span><span class="sxs-lookup"><span data-stu-id="99d51-121">string</span></span> | <span data-ttu-id="99d51-122">Приложение, которое выполнило записанную акцию</span><span class="sxs-lookup"><span data-stu-id="99d51-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="99d51-123">string</span><span class="sxs-lookup"><span data-stu-id="99d51-123">string</span></span> | <span data-ttu-id="99d51-124">Основное имя пользователя (UPN) учетной записи, к</span><span class="sxs-lookup"><span data-stu-id="99d51-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="99d51-125">string</span><span class="sxs-lookup"><span data-stu-id="99d51-125">string</span></span> | <span data-ttu-id="99d51-126">Отображение имени учетной записи, к которую было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="99d51-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="99d51-127">string</span><span class="sxs-lookup"><span data-stu-id="99d51-127">string</span></span> | <span data-ttu-id="99d51-128">Полное доменное имя (FQDN) устройства, на которое было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="99d51-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="99d51-129">string</span><span class="sxs-lookup"><span data-stu-id="99d51-129">string</span></span> | <span data-ttu-id="99d51-130">Имя устройства под управлением серверного приложения, обрабатываемого записанным действием</span><span class="sxs-lookup"><span data-stu-id="99d51-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="99d51-131">string</span><span class="sxs-lookup"><span data-stu-id="99d51-131">string</span></span> | <span data-ttu-id="99d51-132">IP-адрес устройства под управлением серверного приложения, обработав записанное действие</span><span class="sxs-lookup"><span data-stu-id="99d51-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="99d51-133">string</span><span class="sxs-lookup"><span data-stu-id="99d51-133">string</span></span> | <span data-ttu-id="99d51-134">Порт назначения действия</span><span class="sxs-lookup"><span data-stu-id="99d51-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="99d51-135">string</span><span class="sxs-lookup"><span data-stu-id="99d51-135">string</span></span> | <span data-ttu-id="99d51-136">Протокол, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="99d51-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="99d51-137">string</span><span class="sxs-lookup"><span data-stu-id="99d51-137">string</span></span> | <span data-ttu-id="99d51-138">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="99d51-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="99d51-139">string</span><span class="sxs-lookup"><span data-stu-id="99d51-139">string</span></span> | <span data-ttu-id="99d51-140">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="99d51-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="99d51-141">string</span><span class="sxs-lookup"><span data-stu-id="99d51-141">string</span></span> | <span data-ttu-id="99d51-142">Основное имя пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="99d51-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="99d51-143">string</span><span class="sxs-lookup"><span data-stu-id="99d51-143">string</span></span> | <span data-ttu-id="99d51-144">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="99d51-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="99d51-145">string</span><span class="sxs-lookup"><span data-stu-id="99d51-145">string</span></span> | <span data-ttu-id="99d51-146">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="99d51-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="99d51-147">string</span><span class="sxs-lookup"><span data-stu-id="99d51-147">string</span></span> | <span data-ttu-id="99d51-148">Имя пользователя учетной записи, отображаемого в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="99d51-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="99d51-149">Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="99d51-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="99d51-150">string</span><span class="sxs-lookup"><span data-stu-id="99d51-150">string</span></span> | <span data-ttu-id="99d51-151">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="99d51-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="99d51-152">string</span><span class="sxs-lookup"><span data-stu-id="99d51-152">string</span></span> | <span data-ttu-id="99d51-153">IP-адрес, присвоенный устройству во время связи</span><span class="sxs-lookup"><span data-stu-id="99d51-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="99d51-154">string</span><span class="sxs-lookup"><span data-stu-id="99d51-154">string</span></span> | <span data-ttu-id="99d51-155">Порт TCP, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="99d51-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="99d51-156">string</span><span class="sxs-lookup"><span data-stu-id="99d51-156">string</span></span> | <span data-ttu-id="99d51-157">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="99d51-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="99d51-158">string</span><span class="sxs-lookup"><span data-stu-id="99d51-158">string</span></span> | <span data-ttu-id="99d51-159">Поставщик интернет-услуг, связанный с IP-адресом</span><span class="sxs-lookup"><span data-stu-id="99d51-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="99d51-160">long</span><span class="sxs-lookup"><span data-stu-id="99d51-160">long</span></span> | <span data-ttu-id="99d51-161">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="99d51-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="99d51-162">string</span><span class="sxs-lookup"><span data-stu-id="99d51-162">string</span></span> | <span data-ttu-id="99d51-163">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="99d51-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="99d51-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="99d51-164">Related topics</span></span>
- [<span data-ttu-id="99d51-165">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="99d51-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="99d51-166">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="99d51-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="99d51-167">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="99d51-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="99d51-168">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="99d51-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="99d51-169">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="99d51-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="99d51-170">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="99d51-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
