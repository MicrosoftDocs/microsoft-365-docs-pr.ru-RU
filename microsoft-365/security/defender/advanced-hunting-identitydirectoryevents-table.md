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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ba63bdeb215c24e68d0e507d99e026c5b2695cb0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076365"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="f5eba-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="f5eba-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5eba-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f5eba-105">**Applies to:**</span></span>
- <span data-ttu-id="f5eba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5eba-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f5eba-107">Таблица в продвинутой схеме охоты содержит события, включающие локального контроллера домена под `IdentityDirectoryEvents` управлением Active [](advanced-hunting-overview.md) Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="f5eba-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="f5eba-108">В этой таблице запечатлены различные события, связанные с удостоверением, такие как изменения пароля, истечение срока действия пароля и изменение основного имени пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="f5eba-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="f5eba-109">Он также фиксирует события системы на контроллере домена, например планирование задач и активность PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5eba-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="f5eba-110">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="f5eba-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="f5eba-111">Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="f5eba-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="f5eba-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f5eba-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f5eba-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="f5eba-113">Column name</span></span> | <span data-ttu-id="f5eba-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f5eba-114">Data type</span></span> | <span data-ttu-id="f5eba-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f5eba-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f5eba-116">datetime</span><span class="sxs-lookup"><span data-stu-id="f5eba-116">datetime</span></span> | <span data-ttu-id="f5eba-117">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="f5eba-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f5eba-118">string</span><span class="sxs-lookup"><span data-stu-id="f5eba-118">string</span></span> | <span data-ttu-id="f5eba-119">Тип действий, которые вызвали событие.</span><span class="sxs-lookup"><span data-stu-id="f5eba-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="f5eba-120">Подробные [сведения см. в](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) справке по схеме на портале</span><span class="sxs-lookup"><span data-stu-id="f5eba-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="f5eba-121">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-121">string</span></span> | <span data-ttu-id="f5eba-122">Приложение, которое выполнило записанную акцию</span><span class="sxs-lookup"><span data-stu-id="f5eba-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="f5eba-123">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-123">string</span></span> | <span data-ttu-id="f5eba-124">Основное имя пользователя (UPN) учетной записи, к</span><span class="sxs-lookup"><span data-stu-id="f5eba-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="f5eba-125">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-125">string</span></span> | <span data-ttu-id="f5eba-126">Отображение имени учетной записи, к которую было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="f5eba-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="f5eba-127">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-127">string</span></span> | <span data-ttu-id="f5eba-128">Полное доменное имя (FQDN) устройства, на которое было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="f5eba-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="f5eba-129">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-129">string</span></span> | <span data-ttu-id="f5eba-130">Имя устройства под управлением серверного приложения, обрабатываемого записанным действием</span><span class="sxs-lookup"><span data-stu-id="f5eba-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="f5eba-131">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-131">string</span></span> | <span data-ttu-id="f5eba-132">IP-адрес устройства под управлением серверного приложения, обработав записанное действие</span><span class="sxs-lookup"><span data-stu-id="f5eba-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="f5eba-133">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-133">string</span></span> | <span data-ttu-id="f5eba-134">Порт назначения действия</span><span class="sxs-lookup"><span data-stu-id="f5eba-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="f5eba-135">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-135">string</span></span> | <span data-ttu-id="f5eba-136">Протокол, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="f5eba-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="f5eba-137">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-137">string</span></span> | <span data-ttu-id="f5eba-138">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="f5eba-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f5eba-139">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-139">string</span></span> | <span data-ttu-id="f5eba-140">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="f5eba-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="f5eba-141">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-141">string</span></span> | <span data-ttu-id="f5eba-142">Основное имя пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="f5eba-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="f5eba-143">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-143">string</span></span> | <span data-ttu-id="f5eba-144">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="f5eba-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f5eba-145">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-145">string</span></span> | <span data-ttu-id="f5eba-146">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f5eba-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f5eba-147">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-147">string</span></span> | <span data-ttu-id="f5eba-148">Имя пользователя учетной записи, отображаемого в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="f5eba-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f5eba-149">Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="f5eba-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="f5eba-150">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-150">string</span></span> | <span data-ttu-id="f5eba-151">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="f5eba-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="f5eba-152">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-152">string</span></span> | <span data-ttu-id="f5eba-153">IP-адрес, присвоенный устройству во время связи</span><span class="sxs-lookup"><span data-stu-id="f5eba-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="f5eba-154">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-154">string</span></span> | <span data-ttu-id="f5eba-155">Порт TCP, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="f5eba-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="f5eba-156">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-156">string</span></span> | <span data-ttu-id="f5eba-157">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="f5eba-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="f5eba-158">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-158">string</span></span> | <span data-ttu-id="f5eba-159">Поставщик интернет-услуг, связанный с IP-адресом</span><span class="sxs-lookup"><span data-stu-id="f5eba-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="f5eba-160">long</span><span class="sxs-lookup"><span data-stu-id="f5eba-160">long</span></span> | <span data-ttu-id="f5eba-161">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f5eba-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="f5eba-162">строка</span><span class="sxs-lookup"><span data-stu-id="f5eba-162">string</span></span> | <span data-ttu-id="f5eba-163">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="f5eba-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f5eba-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f5eba-164">Related topics</span></span>
- [<span data-ttu-id="f5eba-165">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="f5eba-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f5eba-166">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="f5eba-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f5eba-167">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="f5eba-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f5eba-168">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="f5eba-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f5eba-169">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="f5eba-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f5eba-170">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="f5eba-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
