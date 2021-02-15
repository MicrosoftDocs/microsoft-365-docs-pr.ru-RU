---
title: Таблица IdentityDirectoryEvents в схеме advanced hunting
description: Узнайте о событиях контроллера домена и Active Directory в таблице IdentityDirectoryEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityDirectoryEvents, domain controller, Active Directory, Azure ATP, identities
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
ms.openlocfilehash: 95090b0f4abe0b0f0552c81495936f4f2261cf8e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929938"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="569a2-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="569a2-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="569a2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="569a2-105">**Applies to:**</span></span>
- <span data-ttu-id="569a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="569a2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="569a2-107">Таблица в схеме advanced hunting содержит события, связанные с контроллером локального домена под управлением `IdentityDirectoryEvents` Active Directory [](advanced-hunting-overview.md) (AD).</span><span class="sxs-lookup"><span data-stu-id="569a2-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="569a2-108">В этой таблице фиксироваться различные события, связанные с удостоверениями, такие как изменение паролей, истечение срока действия пароля и изменение имени пользователя-пользователя.</span><span class="sxs-lookup"><span data-stu-id="569a2-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="569a2-109">Он также захватывает системные события на контроллере домена, такие как планирование задач и действия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="569a2-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="569a2-110">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="569a2-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="569a2-111">Для получения подробных сведений о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в Центре безопасности. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="569a2-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="569a2-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="569a2-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="569a2-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="569a2-113">Column name</span></span> | <span data-ttu-id="569a2-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="569a2-114">Data type</span></span> | <span data-ttu-id="569a2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="569a2-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="569a2-116">datetime</span><span class="sxs-lookup"><span data-stu-id="569a2-116">datetime</span></span> | <span data-ttu-id="569a2-117">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="569a2-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="569a2-118">string</span><span class="sxs-lookup"><span data-stu-id="569a2-118">string</span></span> | <span data-ttu-id="569a2-119">Тип действия, которое вызвало событие.</span><span class="sxs-lookup"><span data-stu-id="569a2-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="569a2-120">Подробные сведения см. в справке [по схеме портала](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="569a2-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="569a2-121">string</span><span class="sxs-lookup"><span data-stu-id="569a2-121">string</span></span> | <span data-ttu-id="569a2-122">Приложение, которое выполнило записанную действие</span><span class="sxs-lookup"><span data-stu-id="569a2-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="569a2-123">string</span><span class="sxs-lookup"><span data-stu-id="569a2-123">string</span></span> | <span data-ttu-id="569a2-124">Имя пользователя-пользователя (UPN) учетной записи, к которую было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="569a2-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="569a2-125">string</span><span class="sxs-lookup"><span data-stu-id="569a2-125">string</span></span> | <span data-ttu-id="569a2-126">Отображаемого имени учетной записи, к которую было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="569a2-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="569a2-127">string</span><span class="sxs-lookup"><span data-stu-id="569a2-127">string</span></span> | <span data-ttu-id="569a2-128">Полное доменное имя устройства, к которое было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="569a2-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="569a2-129">string</span><span class="sxs-lookup"><span data-stu-id="569a2-129">string</span></span> | <span data-ttu-id="569a2-130">Имя устройства, на которое запущено серверное приложение, обрабатывающее записанное действие</span><span class="sxs-lookup"><span data-stu-id="569a2-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="569a2-131">string</span><span class="sxs-lookup"><span data-stu-id="569a2-131">string</span></span> | <span data-ttu-id="569a2-132">IP-адрес устройства, на которое запущено серверное приложение, обрабатывающее записанное действие</span><span class="sxs-lookup"><span data-stu-id="569a2-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="569a2-133">string</span><span class="sxs-lookup"><span data-stu-id="569a2-133">string</span></span> | <span data-ttu-id="569a2-134">Порт назначения действия</span><span class="sxs-lookup"><span data-stu-id="569a2-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="569a2-135">string</span><span class="sxs-lookup"><span data-stu-id="569a2-135">string</span></span> | <span data-ttu-id="569a2-136">Протокол, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="569a2-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="569a2-137">string</span><span class="sxs-lookup"><span data-stu-id="569a2-137">string</span></span> | <span data-ttu-id="569a2-138">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="569a2-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="569a2-139">string</span><span class="sxs-lookup"><span data-stu-id="569a2-139">string</span></span> | <span data-ttu-id="569a2-140">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="569a2-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="569a2-141">string</span><span class="sxs-lookup"><span data-stu-id="569a2-141">string</span></span> | <span data-ttu-id="569a2-142">Имя пользователя-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="569a2-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="569a2-143">string</span><span class="sxs-lookup"><span data-stu-id="569a2-143">string</span></span> | <span data-ttu-id="569a2-144">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="569a2-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="569a2-145">string</span><span class="sxs-lookup"><span data-stu-id="569a2-145">string</span></span> | <span data-ttu-id="569a2-146">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="569a2-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="569a2-147">string</span><span class="sxs-lookup"><span data-stu-id="569a2-147">string</span></span> | <span data-ttu-id="569a2-148">Имя пользователя учетной записи, отображаемой в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="569a2-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="569a2-149">Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="569a2-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="569a2-150">string</span><span class="sxs-lookup"><span data-stu-id="569a2-150">string</span></span> | <span data-ttu-id="569a2-151">Полное доменное имя устройства</span><span class="sxs-lookup"><span data-stu-id="569a2-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="569a2-152">string</span><span class="sxs-lookup"><span data-stu-id="569a2-152">string</span></span> | <span data-ttu-id="569a2-153">IP-адрес, присвоенный устройству во время связи</span><span class="sxs-lookup"><span data-stu-id="569a2-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="569a2-154">string</span><span class="sxs-lookup"><span data-stu-id="569a2-154">string</span></span> | <span data-ttu-id="569a2-155">TCP-порт, используемый во время связи</span><span class="sxs-lookup"><span data-stu-id="569a2-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="569a2-156">string</span><span class="sxs-lookup"><span data-stu-id="569a2-156">string</span></span> | <span data-ttu-id="569a2-157">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="569a2-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="569a2-158">string</span><span class="sxs-lookup"><span data-stu-id="569a2-158">string</span></span> | <span data-ttu-id="569a2-159">Поставщик услуг Интернета, связанный с IP-адресом</span><span class="sxs-lookup"><span data-stu-id="569a2-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="569a2-160">long</span><span class="sxs-lookup"><span data-stu-id="569a2-160">long</span></span> | <span data-ttu-id="569a2-161">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="569a2-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="569a2-162">string</span><span class="sxs-lookup"><span data-stu-id="569a2-162">string</span></span> | <span data-ttu-id="569a2-163">Дополнительные сведения об объекте или событии</span><span class="sxs-lookup"><span data-stu-id="569a2-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="569a2-164">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="569a2-164">Related topics</span></span>
- [<span data-ttu-id="569a2-165">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="569a2-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="569a2-166">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="569a2-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="569a2-167">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="569a2-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="569a2-168">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="569a2-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="569a2-169">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="569a2-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="569a2-170">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="569a2-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
