---
title: Таблица IdentityInfo в продвинутой схеме охоты
description: Сведения о учетной записи пользователя в таблице IdentityInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка на схему, кусто, таблица, столбец, тип данных, описание, AccountInfo, IdentityInfo, учетная запись
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
ms.openlocfilehash: e3e5410c868336308b1ecb34ba4326bf2dc5796f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072774"
---
# <a name="identityinfo"></a><span data-ttu-id="38515-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="38515-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="38515-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="38515-105">**Applies to:**</span></span>
- <span data-ttu-id="38515-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38515-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="38515-107">Таблица в продвинутой схеме охоты содержит сведения о учетных записях пользователей, полученных из различных служб, в том числе `IdentityInfo` Azure Active [](advanced-hunting-overview.md) Directory.</span><span class="sxs-lookup"><span data-stu-id="38515-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="38515-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="38515-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="38515-109">Эта таблица была переименована из `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="38515-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="38515-110">При переименовании все запросы, сохраненные на портале, автоматически обновляются.</span><span class="sxs-lookup"><span data-stu-id="38515-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="38515-111">Проверьте запросы, сохраненные в другом месте.</span><span class="sxs-lookup"><span data-stu-id="38515-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="38515-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="38515-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="38515-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="38515-113">Column name</span></span> | <span data-ttu-id="38515-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="38515-114">Data type</span></span> | <span data-ttu-id="38515-115">Описание</span><span class="sxs-lookup"><span data-stu-id="38515-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="38515-116">string</span><span class="sxs-lookup"><span data-stu-id="38515-116">string</span></span> | <span data-ttu-id="38515-117">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="38515-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="38515-118">строка</span><span class="sxs-lookup"><span data-stu-id="38515-118">string</span></span> | <span data-ttu-id="38515-119">Основное имя пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="38515-120">строка</span><span class="sxs-lookup"><span data-stu-id="38515-120">string</span></span> | <span data-ttu-id="38515-121">Идентификатор локальной безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="38515-122">строка</span><span class="sxs-lookup"><span data-stu-id="38515-122">string</span></span> | <span data-ttu-id="38515-123">Идентификатор облачной безопасности учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="38515-124">строка</span><span class="sxs-lookup"><span data-stu-id="38515-124">string</span></span> | <span data-ttu-id="38515-125">Имя или имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="38515-126">строка</span><span class="sxs-lookup"><span data-stu-id="38515-126">string</span></span> | <span data-ttu-id="38515-127">Фамилия, фамилия или фамилия пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="38515-128">строка</span><span class="sxs-lookup"><span data-stu-id="38515-128">string</span></span> | <span data-ttu-id="38515-129">Имя пользователя учетной записи, отображаемого в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="38515-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="38515-130">Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="38515-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="38515-131">строка</span><span class="sxs-lookup"><span data-stu-id="38515-131">string</span></span> | <span data-ttu-id="38515-132">Имя отдела, к которой принадлежит пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="38515-133">строка</span><span class="sxs-lookup"><span data-stu-id="38515-133">string</span></span> | <span data-ttu-id="38515-134">Название задания пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="38515-135">строка</span><span class="sxs-lookup"><span data-stu-id="38515-135">string</span></span> | <span data-ttu-id="38515-136">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="38515-137">строка</span><span class="sxs-lookup"><span data-stu-id="38515-137">string</span></span> | <span data-ttu-id="38515-138">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="38515-139">строка</span><span class="sxs-lookup"><span data-stu-id="38515-139">string</span></span> | <span data-ttu-id="38515-140">SMTP-адрес учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="38515-141">строка</span><span class="sxs-lookup"><span data-stu-id="38515-141">string</span></span> | <span data-ttu-id="38515-142">Протокол инициации сеанса голосовой связи по IP (VOIP) учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="38515-143">строка</span><span class="sxs-lookup"><span data-stu-id="38515-143">string</span></span> | <span data-ttu-id="38515-144">Город, в котором находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="38515-145">строка</span><span class="sxs-lookup"><span data-stu-id="38515-145">string</span></span> | <span data-ttu-id="38515-146">Страна/регион, где находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="38515-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="38515-147">boolean</span><span class="sxs-lookup"><span data-stu-id="38515-147">boolean</span></span> | <span data-ttu-id="38515-148">Указывает, включена учетная запись или нет.</span><span class="sxs-lookup"><span data-stu-id="38515-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="38515-149">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="38515-149">Related topics</span></span>
- [<span data-ttu-id="38515-150">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="38515-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="38515-151">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="38515-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="38515-152">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="38515-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="38515-153">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="38515-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="38515-154">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="38515-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="38515-155">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="38515-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
