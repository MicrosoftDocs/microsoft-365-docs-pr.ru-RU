---
title: Таблица аккаунтинфо в схеме расширенного поискового окна
description: Сведения об учетных записях пользователей в таблице Аккаунтинфо расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Алертинфо, оповещения, сущности, пользователь, учетная запись
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929532"
---
# <a name="accountinfo"></a><span data-ttu-id="41cc8-104">AccountInfo</span><span class="sxs-lookup"><span data-stu-id="41cc8-104">AccountInfo</span></span>

<span data-ttu-id="41cc8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="41cc8-105">**Applies to:**</span></span>
- <span data-ttu-id="41cc8-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="41cc8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="41cc8-107">`AccountInfo` Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения об учетных записях пользователей, полученных из различных служб, в том числе Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41cc8-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="41cc8-108">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="41cc8-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="41cc8-109">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="41cc8-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="41cc8-110">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="41cc8-110">Column name</span></span> | <span data-ttu-id="41cc8-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="41cc8-111">Data type</span></span> | <span data-ttu-id="41cc8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="41cc8-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="41cc8-113">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-113">string</span></span> | <span data-ttu-id="41cc8-114">Уникальный идентификатор учетной записи в Azure AD</span><span class="sxs-lookup"><span data-stu-id="41cc8-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="41cc8-115">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-115">string</span></span> | <span data-ttu-id="41cc8-116">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="41cc8-117">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-117">string</span></span> | <span data-ttu-id="41cc8-118">Локальный идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="41cc8-119">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-119">string</span></span> | <span data-ttu-id="41cc8-120">Идентификатор безопасности облака учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="41cc8-121">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-121">string</span></span> | <span data-ttu-id="41cc8-122">Заданное имя или имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="41cc8-123">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-123">string</span></span> | <span data-ttu-id="41cc8-124">Фамилия, имя семейства или фамилия пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="41cc8-125">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-125">string</span></span> | <span data-ttu-id="41cc8-126">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="41cc8-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="41cc8-127">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="41cc8-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="41cc8-128">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-128">string</span></span> | <span data-ttu-id="41cc8-129">Имя отдела, к которому относится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="41cc8-130">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-130">string</span></span> | <span data-ttu-id="41cc8-131">Должность пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="41cc8-132">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-132">string</span></span> | <span data-ttu-id="41cc8-133">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="41cc8-134">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-134">string</span></span> | <span data-ttu-id="41cc8-135">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="41cc8-136">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-136">string</span></span> | <span data-ttu-id="41cc8-137">SMTP-адрес учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="41cc8-138">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-138">string</span></span> | <span data-ttu-id="41cc8-139">Протокол передачи голоса по протоколу IP (VOIP) учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="41cc8-140">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-140">string</span></span> | <span data-ttu-id="41cc8-141">Город, в котором находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="41cc8-142">string</span><span class="sxs-lookup"><span data-stu-id="41cc8-142">string</span></span> | <span data-ttu-id="41cc8-143">Страна или регион, где находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="41cc8-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="41cc8-144">boolean</span><span class="sxs-lookup"><span data-stu-id="41cc8-144">boolean</span></span> | <span data-ttu-id="41cc8-145">Указывает, включена ли учетная запись</span><span class="sxs-lookup"><span data-stu-id="41cc8-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="41cc8-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="41cc8-146">Related topics</span></span>
- [<span data-ttu-id="41cc8-147">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="41cc8-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="41cc8-148">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="41cc8-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="41cc8-149">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="41cc8-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="41cc8-150">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="41cc8-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="41cc8-151">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="41cc8-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="41cc8-152">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="41cc8-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
