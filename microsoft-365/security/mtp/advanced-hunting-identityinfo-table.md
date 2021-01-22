---
title: Таблица IdentityInfo в схеме advanced hunting
description: Сведения об учетной записи пользователя в таблице IdentityInfo схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929914"
---
# <a name="identityinfo"></a><span data-ttu-id="78aec-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="78aec-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="78aec-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="78aec-105">**Applies to:**</span></span>
- <span data-ttu-id="78aec-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78aec-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="78aec-107">Таблица в схеме advanced hunting содержит сведения об учетных записях пользователей, полученных из различных служб, включая `IdentityInfo` Azure Active [](advanced-hunting-overview.md) Directory.</span><span class="sxs-lookup"><span data-stu-id="78aec-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="78aec-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="78aec-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="78aec-109">Эта таблица была переименована `AccountInfo` из .</span><span class="sxs-lookup"><span data-stu-id="78aec-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="78aec-110">Во время переименования все запросы, сохраненные на портале, автоматически обновляются.</span><span class="sxs-lookup"><span data-stu-id="78aec-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="78aec-111">Проверьте запросы, сохраненные в другом месте.</span><span class="sxs-lookup"><span data-stu-id="78aec-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="78aec-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="78aec-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="78aec-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="78aec-113">Column name</span></span> | <span data-ttu-id="78aec-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="78aec-114">Data type</span></span> | <span data-ttu-id="78aec-115">Описание</span><span class="sxs-lookup"><span data-stu-id="78aec-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="78aec-116">string</span><span class="sxs-lookup"><span data-stu-id="78aec-116">string</span></span> | <span data-ttu-id="78aec-117">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="78aec-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="78aec-118">string</span><span class="sxs-lookup"><span data-stu-id="78aec-118">string</span></span> | <span data-ttu-id="78aec-119">Имя пользователя-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="78aec-120">string</span><span class="sxs-lookup"><span data-stu-id="78aec-120">string</span></span> | <span data-ttu-id="78aec-121">Идентификатор безопасности (SID) локальной учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="78aec-122">string</span><span class="sxs-lookup"><span data-stu-id="78aec-122">string</span></span> | <span data-ttu-id="78aec-123">Идентификатор облачной безопасности учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="78aec-124">string</span><span class="sxs-lookup"><span data-stu-id="78aec-124">string</span></span> | <span data-ttu-id="78aec-125">Заданное имя или имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="78aec-126">string</span><span class="sxs-lookup"><span data-stu-id="78aec-126">string</span></span> | <span data-ttu-id="78aec-127">Фамилия, фамилия или фамилия пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="78aec-128">string</span><span class="sxs-lookup"><span data-stu-id="78aec-128">string</span></span> | <span data-ttu-id="78aec-129">Имя пользователя учетной записи, отображаемой в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="78aec-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="78aec-130">Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="78aec-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="78aec-131">string</span><span class="sxs-lookup"><span data-stu-id="78aec-131">string</span></span> | <span data-ttu-id="78aec-132">Название отдела, в который входит пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="78aec-133">string</span><span class="sxs-lookup"><span data-stu-id="78aec-133">string</span></span> | <span data-ttu-id="78aec-134">Должность пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="78aec-135">string</span><span class="sxs-lookup"><span data-stu-id="78aec-135">string</span></span> | <span data-ttu-id="78aec-136">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="78aec-137">string</span><span class="sxs-lookup"><span data-stu-id="78aec-137">string</span></span> | <span data-ttu-id="78aec-138">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="78aec-139">string</span><span class="sxs-lookup"><span data-stu-id="78aec-139">string</span></span> | <span data-ttu-id="78aec-140">SMTP-адрес учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="78aec-141">string</span><span class="sxs-lookup"><span data-stu-id="78aec-141">string</span></span> | <span data-ttu-id="78aec-142">SIP-адрес учетной записи по протоколу SIP</span><span class="sxs-lookup"><span data-stu-id="78aec-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="78aec-143">string</span><span class="sxs-lookup"><span data-stu-id="78aec-143">string</span></span> | <span data-ttu-id="78aec-144">Город, где находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="78aec-145">string</span><span class="sxs-lookup"><span data-stu-id="78aec-145">string</span></span> | <span data-ttu-id="78aec-146">Страна или регион, где находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="78aec-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="78aec-147">boolean</span><span class="sxs-lookup"><span data-stu-id="78aec-147">boolean</span></span> | <span data-ttu-id="78aec-148">Указывает, включена ли учетная запись</span><span class="sxs-lookup"><span data-stu-id="78aec-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="78aec-149">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="78aec-149">Related topics</span></span>
- [<span data-ttu-id="78aec-150">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="78aec-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="78aec-151">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="78aec-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="78aec-152">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="78aec-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="78aec-153">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="78aec-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="78aec-154">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="78aec-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="78aec-155">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="78aec-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
