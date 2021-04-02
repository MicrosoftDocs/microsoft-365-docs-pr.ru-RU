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
ms.openlocfilehash: d7e1ad4d10c3b71a04421d92304dc2bfcb6147da
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498202"
---
# <a name="identityinfo"></a><span data-ttu-id="c5e81-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="c5e81-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c5e81-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c5e81-105">**Applies to:**</span></span>
- <span data-ttu-id="c5e81-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5e81-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c5e81-107">Таблица в продвинутой схеме охоты содержит сведения о учетных записях пользователей, полученных из различных служб, в том числе `IdentityInfo` Azure Active [](advanced-hunting-overview.md) Directory.</span><span class="sxs-lookup"><span data-stu-id="c5e81-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="c5e81-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="c5e81-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="c5e81-109">Эта таблица была переименована из `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="c5e81-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="c5e81-110">При переименовании все запросы, сохраненные на портале, автоматически обновляются.</span><span class="sxs-lookup"><span data-stu-id="c5e81-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="c5e81-111">Проверьте запросы, сохраненные в другом месте.</span><span class="sxs-lookup"><span data-stu-id="c5e81-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="c5e81-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c5e81-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c5e81-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="c5e81-113">Column name</span></span> | <span data-ttu-id="c5e81-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c5e81-114">Data type</span></span> | <span data-ttu-id="c5e81-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c5e81-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="c5e81-116">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-116">string</span></span> | <span data-ttu-id="c5e81-117">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="c5e81-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="c5e81-118">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-118">string</span></span> | <span data-ttu-id="c5e81-119">Основное имя пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="c5e81-120">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-120">string</span></span> | <span data-ttu-id="c5e81-121">Идентификатор локальной безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="c5e81-122">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-122">string</span></span> | <span data-ttu-id="c5e81-123">Идентификатор облачной безопасности учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="c5e81-124">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-124">string</span></span> | <span data-ttu-id="c5e81-125">Имя или имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="c5e81-126">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-126">string</span></span> | <span data-ttu-id="c5e81-127">Фамилия, фамилия или фамилия пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c5e81-128">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-128">string</span></span> | <span data-ttu-id="c5e81-129">Имя пользователя учетной записи, отображаемого в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="c5e81-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c5e81-130">Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="c5e81-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="c5e81-131">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-131">string</span></span> | <span data-ttu-id="c5e81-132">Имя отдела, к которой принадлежит пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="c5e81-133">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-133">string</span></span> | <span data-ttu-id="c5e81-134">Название задания пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="c5e81-135">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-135">string</span></span> | <span data-ttu-id="c5e81-136">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c5e81-137">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-137">string</span></span> | <span data-ttu-id="c5e81-138">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="c5e81-139">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-139">string</span></span> | <span data-ttu-id="c5e81-140">SMTP-адрес учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="c5e81-141">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-141">string</span></span> | <span data-ttu-id="c5e81-142">Протокол инициации сеанса голосовой связи по IP (VOIP) учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="c5e81-143">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-143">string</span></span> | <span data-ttu-id="c5e81-144">Город, в котором находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="c5e81-145">string</span><span class="sxs-lookup"><span data-stu-id="c5e81-145">string</span></span> | <span data-ttu-id="c5e81-146">Страна/регион, где находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="c5e81-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="c5e81-147">boolean</span><span class="sxs-lookup"><span data-stu-id="c5e81-147">boolean</span></span> | <span data-ttu-id="c5e81-148">Указывает, включена учетная запись или нет.</span><span class="sxs-lookup"><span data-stu-id="c5e81-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c5e81-149">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c5e81-149">Related topics</span></span>
- [<span data-ttu-id="c5e81-150">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="c5e81-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c5e81-151">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="c5e81-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c5e81-152">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="c5e81-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c5e81-153">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="c5e81-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c5e81-154">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="c5e81-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c5e81-155">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="c5e81-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
