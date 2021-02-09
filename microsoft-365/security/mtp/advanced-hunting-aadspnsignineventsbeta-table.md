---
title: Таблица AADSpnSignInEventsBeta в схеме advanced hunting
description: Сведения о сведениях, связанных с участником-службой Azure Active Directory и таблицой событий управляемого удостоверения для регистрации в службе advanced hunting schema
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, user, account, identity, AAD
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3eba2459fd9a0af1963ca8d1446b22fc0b1bdb93
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145407"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="e79ba-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="e79ba-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="e79ba-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e79ba-105">**Applies to:**</span></span>

- <span data-ttu-id="e79ba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e79ba-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="e79ba-107">Таблица в настоящее время находится в бета-версии и предлагается на краткосрочной основе, чтобы вы могли использовать события регистрации в azure `AADSpnSignInEventsBeta` Active Directory (AAD) и основного пользователя службы и управляемого удостоверения.</span><span class="sxs-lookup"><span data-stu-id="e79ba-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="e79ba-108">Со временем все сведения о схеме для входов будут перемещаться в `IdentityLogonEvents` таблицу.</span><span class="sxs-lookup"><span data-stu-id="e79ba-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="e79ba-109">Клиенты, которые могут получить доступ к Microsoft 365 Defender через интегрированное решение Microsoft Defender для конечных точек в Центре безопасности Azure, но не имеют лицензий на Microsoft Defender для Office, Microsoft Defender для удостоверений или Microsoft Cloud App Security, не смогут просматривать эту схему.</span><span class="sxs-lookup"><span data-stu-id="e79ba-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="e79ba-110">Таблица в схеме advanced hunting содержит сведения о основном и управляемом входе в службу `AADSpnSignInEventsBeta` Azure Active Directory. Вы можете узнать больше о различных типах входов в Отчеты о действиях при входе [в Azure Active Directory —](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="e79ba-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="e79ba-111">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="e79ba-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e79ba-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="e79ba-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="e79ba-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="e79ba-113">Column name</span></span>     | <span data-ttu-id="e79ba-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e79ba-114">Data type</span></span> | <span data-ttu-id="e79ba-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e79ba-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="e79ba-116">datetime</span><span class="sxs-lookup"><span data-stu-id="e79ba-116">datetime</span></span>      | <span data-ttu-id="e79ba-117">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="e79ba-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="e79ba-118">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-118">string</span></span>        | <span data-ttu-id="e79ba-119">Приложение, которое выполнило записанную действие</span><span class="sxs-lookup"><span data-stu-id="e79ba-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="e79ba-120">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-120">string</span></span>        | <span data-ttu-id="e79ba-121">Уникальный идентификатор приложения</span><span class="sxs-lookup"><span data-stu-id="e79ba-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="e79ba-122">boolean</span><span class="sxs-lookup"><span data-stu-id="e79ba-122">boolean</span></span>       | <span data-ttu-id="e79ba-123">Указывает, инициировался ли вход с помощью управляемого удостоверения</span><span class="sxs-lookup"><span data-stu-id="e79ba-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="e79ba-124">int</span><span class="sxs-lookup"><span data-stu-id="e79ba-124">int</span></span>        | <span data-ttu-id="e79ba-125">Содержит код ошибки при ошибке при входе.</span><span class="sxs-lookup"><span data-stu-id="e79ba-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="e79ba-126">Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> сайт .</span><span class="sxs-lookup"><span data-stu-id="e79ba-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="e79ba-127">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-127">string</span></span>        | <span data-ttu-id="e79ba-128">Уникальный идентификатор события для регистрации</span><span class="sxs-lookup"><span data-stu-id="e79ba-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="e79ba-129">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-129">string</span></span>        | <span data-ttu-id="e79ba-130">Имя основного службы, инициа которого был инициирован вход</span><span class="sxs-lookup"><span data-stu-id="e79ba-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="e79ba-131">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-131">string</span></span>        | <span data-ttu-id="e79ba-132">Уникальный идентификатор основного службы, инициировал вход</span><span class="sxs-lookup"><span data-stu-id="e79ba-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="e79ba-133">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-133">string</span></span>        | <span data-ttu-id="e79ba-134">Отображаемого имени ресурса, к который был доступ</span><span class="sxs-lookup"><span data-stu-id="e79ba-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="e79ba-135">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-135">string</span></span>        | <span data-ttu-id="e79ba-136">Уникальный идентификатор доступного ресурса</span><span class="sxs-lookup"><span data-stu-id="e79ba-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="e79ba-137">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-137">string</span></span>        | <span data-ttu-id="e79ba-138">Уникальный идентификатор клиента доступного ресурса</span><span class="sxs-lookup"><span data-stu-id="e79ba-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="e79ba-139">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-139">string</span></span>        | <span data-ttu-id="e79ba-140">IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях</span><span class="sxs-lookup"><span data-stu-id="e79ba-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="e79ba-141">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-141">string</span></span>        | <span data-ttu-id="e79ba-142">Двух буквный код, указывающий страну, в которой расположен IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="e79ba-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="e79ba-143">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-143">string</span></span>        | <span data-ttu-id="e79ba-144">Состояние, в котором произошел вход, если доступно</span><span class="sxs-lookup"><span data-stu-id="e79ba-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="e79ba-145">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-145">string</span></span>        | <span data-ttu-id="e79ba-146">Город, где находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="e79ba-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="e79ba-147">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-147">string</span></span>        | <span data-ttu-id="e79ba-148">Координаты расположения для входов с севера на север и на север</span><span class="sxs-lookup"><span data-stu-id="e79ba-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="e79ba-149">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-149">string</span></span>        | <span data-ttu-id="e79ba-150">Координаты расположения для входов с востока на запад</span><span class="sxs-lookup"><span data-stu-id="e79ba-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="e79ba-151">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-151">string</span></span>        | <span data-ttu-id="e79ba-152">Уникальный идентификатор запроса</span><span class="sxs-lookup"><span data-stu-id="e79ba-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="e79ba-153">string</span><span class="sxs-lookup"><span data-stu-id="e79ba-153">string</span></span> | <span data-ttu-id="e79ba-154">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e79ba-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="e79ba-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e79ba-155">Related articles</span></span>

-   [<span data-ttu-id="e79ba-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="e79ba-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="e79ba-157">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="e79ba-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="e79ba-158">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="e79ba-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="e79ba-159">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="e79ba-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

