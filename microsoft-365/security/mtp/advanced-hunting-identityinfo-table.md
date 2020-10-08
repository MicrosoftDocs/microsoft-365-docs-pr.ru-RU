---
title: Таблица идентитинфо в схеме расширенного поискового окна
description: Сведения об учетных записях пользователей в таблице Идентитинфо расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Аккаунтинфо, Идентитинфо, учетная запись
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
ms.openlocfilehash: 6922f50906013cfbfa3bd63c69fff3e89ed46cd5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196829"
---
# <a name="identityinfo"></a><span data-ttu-id="568c2-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="568c2-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="568c2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="568c2-105">**Applies to:**</span></span>
- <span data-ttu-id="568c2-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="568c2-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="568c2-107">`IdentityInfo`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения об учетных записях пользователей, полученных из различных служб, в том числе Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="568c2-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="568c2-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="568c2-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="568c2-109">Эта таблица была переименована из `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="568c2-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="568c2-110">Во время переименования все сохраненные на портале запросы автоматически обновляются.</span><span class="sxs-lookup"><span data-stu-id="568c2-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="568c2-111">Проверьте сохраненные в других запросах.</span><span class="sxs-lookup"><span data-stu-id="568c2-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="568c2-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="568c2-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="568c2-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="568c2-113">Column name</span></span> | <span data-ttu-id="568c2-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="568c2-114">Data type</span></span> | <span data-ttu-id="568c2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="568c2-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="568c2-116">string</span><span class="sxs-lookup"><span data-stu-id="568c2-116">string</span></span> | <span data-ttu-id="568c2-117">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="568c2-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="568c2-118">string</span><span class="sxs-lookup"><span data-stu-id="568c2-118">string</span></span> | <span data-ttu-id="568c2-119">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="568c2-120">string</span><span class="sxs-lookup"><span data-stu-id="568c2-120">string</span></span> | <span data-ttu-id="568c2-121">Локальный идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="568c2-122">string</span><span class="sxs-lookup"><span data-stu-id="568c2-122">string</span></span> | <span data-ttu-id="568c2-123">Идентификатор безопасности облака учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="568c2-124">string</span><span class="sxs-lookup"><span data-stu-id="568c2-124">string</span></span> | <span data-ttu-id="568c2-125">Заданное имя или имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="568c2-126">string</span><span class="sxs-lookup"><span data-stu-id="568c2-126">string</span></span> | <span data-ttu-id="568c2-127">Фамилия, имя семейства или фамилия пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="568c2-128">string</span><span class="sxs-lookup"><span data-stu-id="568c2-128">string</span></span> | <span data-ttu-id="568c2-129">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="568c2-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="568c2-130">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="568c2-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="568c2-131">string</span><span class="sxs-lookup"><span data-stu-id="568c2-131">string</span></span> | <span data-ttu-id="568c2-132">Имя отдела, к которому относится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="568c2-133">string</span><span class="sxs-lookup"><span data-stu-id="568c2-133">string</span></span> | <span data-ttu-id="568c2-134">Должность пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="568c2-135">string</span><span class="sxs-lookup"><span data-stu-id="568c2-135">string</span></span> | <span data-ttu-id="568c2-136">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="568c2-137">string</span><span class="sxs-lookup"><span data-stu-id="568c2-137">string</span></span> | <span data-ttu-id="568c2-138">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="568c2-139">string</span><span class="sxs-lookup"><span data-stu-id="568c2-139">string</span></span> | <span data-ttu-id="568c2-140">SMTP-адрес учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="568c2-141">string</span><span class="sxs-lookup"><span data-stu-id="568c2-141">string</span></span> | <span data-ttu-id="568c2-142">SIP-адрес учетной записи протокола передачи голоса по протоколу IP (VOIP)</span><span class="sxs-lookup"><span data-stu-id="568c2-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="568c2-143">string</span><span class="sxs-lookup"><span data-stu-id="568c2-143">string</span></span> | <span data-ttu-id="568c2-144">Город, в котором находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="568c2-145">string</span><span class="sxs-lookup"><span data-stu-id="568c2-145">string</span></span> | <span data-ttu-id="568c2-146">Страна или регион, где находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="568c2-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="568c2-147">boolean</span><span class="sxs-lookup"><span data-stu-id="568c2-147">boolean</span></span> | <span data-ttu-id="568c2-148">Указывает, включена ли учетная запись</span><span class="sxs-lookup"><span data-stu-id="568c2-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="568c2-149">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="568c2-149">Related topics</span></span>
- [<span data-ttu-id="568c2-150">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="568c2-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="568c2-151">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="568c2-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="568c2-152">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="568c2-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="568c2-153">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="568c2-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="568c2-154">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="568c2-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="568c2-155">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="568c2-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
