---
title: Таблица IdentityInfo в продвинутой схеме охоты
description: Сведения о учетной записи пользователя в таблице IdentityInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, поиск киберугроз, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка схемы, кусто, таблица, столбец, тип данных, описание, AccountInfo, IdentityInfo, учетная запись
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
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935825"
---
# <a name="identityinfo"></a><span data-ttu-id="75d53-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="75d53-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75d53-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="75d53-105">**Applies to:**</span></span>
- <span data-ttu-id="75d53-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75d53-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="75d53-107">Таблица в продвинутой схеме охоты содержит сведения о учетных записях пользователей, полученных из различных служб, в том числе `IdentityInfo` Azure Active [](advanced-hunting-overview.md) Directory.</span><span class="sxs-lookup"><span data-stu-id="75d53-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="75d53-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="75d53-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="75d53-109">Эта таблица была переименована из `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="75d53-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="75d53-110">При переименовании все запросы, сохраненные на портале, автоматически обновляются.</span><span class="sxs-lookup"><span data-stu-id="75d53-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="75d53-111">Проверьте запросы, сохраненные в другом месте.</span><span class="sxs-lookup"><span data-stu-id="75d53-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="75d53-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="75d53-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="75d53-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="75d53-113">Column name</span></span> | <span data-ttu-id="75d53-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="75d53-114">Data type</span></span> | <span data-ttu-id="75d53-115">Описание</span><span class="sxs-lookup"><span data-stu-id="75d53-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="75d53-116">string</span><span class="sxs-lookup"><span data-stu-id="75d53-116">string</span></span> | <span data-ttu-id="75d53-117">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="75d53-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="75d53-118">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-118">string</span></span> | <span data-ttu-id="75d53-119">Основное имя пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="75d53-120">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-120">string</span></span> | <span data-ttu-id="75d53-121">Идентификатор локальной безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="75d53-122">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-122">string</span></span> | <span data-ttu-id="75d53-123">Идентификатор облачной безопасности учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="75d53-124">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-124">string</span></span> | <span data-ttu-id="75d53-125">Имя или имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="75d53-126">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-126">string</span></span> | <span data-ttu-id="75d53-127">Фамилия, фамилия или фамилия пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="75d53-128">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-128">string</span></span> | <span data-ttu-id="75d53-129">Имя пользователя учетной записи, отображаемого в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="75d53-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="75d53-130">Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии.</span><span class="sxs-lookup"><span data-stu-id="75d53-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="75d53-131">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-131">string</span></span> | <span data-ttu-id="75d53-132">Имя отдела, к которой принадлежит пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="75d53-133">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-133">string</span></span> | <span data-ttu-id="75d53-134">Название задания пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="75d53-135">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-135">string</span></span> | <span data-ttu-id="75d53-136">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="75d53-137">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-137">string</span></span> | <span data-ttu-id="75d53-138">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="75d53-139">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-139">string</span></span> | <span data-ttu-id="75d53-140">SMTP-адрес учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="75d53-141">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-141">string</span></span> | <span data-ttu-id="75d53-142">Протокол инициации сеанса голосовой связи по IP (VOIP) учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="75d53-143">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-143">string</span></span> | <span data-ttu-id="75d53-144">Город, в котором находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="75d53-145">Строка</span><span class="sxs-lookup"><span data-stu-id="75d53-145">string</span></span> | <span data-ttu-id="75d53-146">Страна/регион, где находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="75d53-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="75d53-147">boolean</span><span class="sxs-lookup"><span data-stu-id="75d53-147">boolean</span></span> | <span data-ttu-id="75d53-148">Указывает, включена учетная запись или нет.</span><span class="sxs-lookup"><span data-stu-id="75d53-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="75d53-149">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="75d53-149">Related topics</span></span>
- [<span data-ttu-id="75d53-150">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="75d53-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="75d53-151">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="75d53-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="75d53-152">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="75d53-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="75d53-153">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="75d53-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="75d53-154">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="75d53-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="75d53-155">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="75d53-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
