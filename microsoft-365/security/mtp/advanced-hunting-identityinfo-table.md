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
ms.openlocfilehash: b384e76439ae706520725e7193fa64224b724be0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898961"
---
# <a name="identityinfo"></a><span data-ttu-id="b05e1-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="b05e1-104">IdentityInfo</span></span>

<span data-ttu-id="b05e1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b05e1-105">**Applies to:**</span></span>
- <span data-ttu-id="b05e1-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b05e1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b05e1-107">`IdentityInfo`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения об учетных записях пользователей, полученных из различных служб, в том числе Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b05e1-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="b05e1-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b05e1-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="b05e1-109">Эта таблица была переименована из `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="b05e1-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="b05e1-110">Во время переименования все сохраненные на портале запросы автоматически обновляются.</span><span class="sxs-lookup"><span data-stu-id="b05e1-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="b05e1-111">Проверьте сохраненные в других запросах.</span><span class="sxs-lookup"><span data-stu-id="b05e1-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="b05e1-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b05e1-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b05e1-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="b05e1-113">Column name</span></span> | <span data-ttu-id="b05e1-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b05e1-114">Data type</span></span> | <span data-ttu-id="b05e1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b05e1-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="b05e1-116">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-116">string</span></span> | <span data-ttu-id="b05e1-117">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="b05e1-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="b05e1-118">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-118">string</span></span> | <span data-ttu-id="b05e1-119">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="b05e1-120">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-120">string</span></span> | <span data-ttu-id="b05e1-121">Локальный идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="b05e1-122">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-122">string</span></span> | <span data-ttu-id="b05e1-123">Идентификатор безопасности облака учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="b05e1-124">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-124">string</span></span> | <span data-ttu-id="b05e1-125">Заданное имя или имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="b05e1-126">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-126">string</span></span> | <span data-ttu-id="b05e1-127">Фамилия, имя семейства или фамилия пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="b05e1-128">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-128">string</span></span> | <span data-ttu-id="b05e1-129">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="b05e1-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="b05e1-130">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="b05e1-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="b05e1-131">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-131">string</span></span> | <span data-ttu-id="b05e1-132">Имя отдела, к которому относится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="b05e1-133">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-133">string</span></span> | <span data-ttu-id="b05e1-134">Должность пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="b05e1-135">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-135">string</span></span> | <span data-ttu-id="b05e1-136">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="b05e1-137">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-137">string</span></span> | <span data-ttu-id="b05e1-138">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="b05e1-139">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-139">string</span></span> | <span data-ttu-id="b05e1-140">SMTP-адрес учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="b05e1-141">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-141">string</span></span> | <span data-ttu-id="b05e1-142">Протокол передачи голоса по протоколу IP (VOIP) учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-142">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="b05e1-143">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-143">string</span></span> | <span data-ttu-id="b05e1-144">Город, в котором находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="b05e1-145">string</span><span class="sxs-lookup"><span data-stu-id="b05e1-145">string</span></span> | <span data-ttu-id="b05e1-146">Страна или регион, где находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="b05e1-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="b05e1-147">boolean</span><span class="sxs-lookup"><span data-stu-id="b05e1-147">boolean</span></span> | <span data-ttu-id="b05e1-148">Указывает, включена ли учетная запись</span><span class="sxs-lookup"><span data-stu-id="b05e1-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b05e1-149">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b05e1-149">Related topics</span></span>
- [<span data-ttu-id="b05e1-150">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="b05e1-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b05e1-151">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="b05e1-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b05e1-152">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="b05e1-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b05e1-153">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="b05e1-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b05e1-154">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="b05e1-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b05e1-155">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="b05e1-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
