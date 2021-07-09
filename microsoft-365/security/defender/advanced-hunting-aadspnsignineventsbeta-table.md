---
title: Таблица AADSpnSignInEventsBeta в продвинутой схеме охоты
description: Сведения о сведениях, связанных Azure Active Directory и управляемой таблице событий для регистрации удостоверений в таблице расширенных схем охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347911"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="d4168-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="d4168-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="d4168-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d4168-105">**Applies to:**</span></span>

- <span data-ttu-id="d4168-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4168-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="d4168-107">В настоящее время таблица находится в бета-версии и предлагается на краткосрочной основе, чтобы разрешить вам охотиться через Azure Active Directory (AAD) главного и управляемых событий регистрации `AADSpnSignInEventsBeta` удостоверений.</span><span class="sxs-lookup"><span data-stu-id="d4168-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="d4168-108">В конечном итоге мы переместим все сведения о схеме входов в `IdentityLogonEvents` таблицу.</span><span class="sxs-lookup"><span data-stu-id="d4168-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="d4168-109">Таблица в продвинутой схеме охоты содержит сведения о Azure Active Directory и управляемых входных знаках `AADSpnSignInEventsBeta` удостоверений. Дополнительные новости о различных типах входов можно узнать в отчетах о Azure Active Directory действий для регистрации [.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="d4168-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="d4168-110">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="d4168-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d4168-111">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="d4168-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="d4168-112">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="d4168-112">Column name</span></span> | <span data-ttu-id="d4168-113">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d4168-113">Data type</span></span> | <span data-ttu-id="d4168-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d4168-114">Description</span></span> |
|-----|-----|-----|
| `Timestamp` | <span data-ttu-id="d4168-115">datetime</span><span class="sxs-lookup"><span data-stu-id="d4168-115">datetime</span></span> | <span data-ttu-id="d4168-116">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="d4168-116">Date and time when the record was generated</span></span> |
| `Application` | <span data-ttu-id="d4168-117">string</span><span class="sxs-lookup"><span data-stu-id="d4168-117">string</span></span> | <span data-ttu-id="d4168-118">Приложение, которое выполнило записанную акцию</span><span class="sxs-lookup"><span data-stu-id="d4168-118">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="d4168-119">string</span><span class="sxs-lookup"><span data-stu-id="d4168-119">string</span></span> | <span data-ttu-id="d4168-120">Уникальный идентификатор для приложения</span><span class="sxs-lookup"><span data-stu-id="d4168-120">Unique identifier for the application</span></span> |
| `IsManagedIdentity`    | <span data-ttu-id="d4168-121">boolean</span><span class="sxs-lookup"><span data-stu-id="d4168-121">boolean</span></span>       | <span data-ttu-id="d4168-122">Указывает, был ли вход инициирован управляемым удостоверением</span><span class="sxs-lookup"><span data-stu-id="d4168-122">Indicates whether the sign-in was initiated by a managed identity</span></span> |
| `ErrorCode`    | <span data-ttu-id="d4168-123">int</span><span class="sxs-lookup"><span data-stu-id="d4168-123">int</span></span> | <span data-ttu-id="d4168-124">Содержит код ошибки при ошибке при входе.</span><span class="sxs-lookup"><span data-stu-id="d4168-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="d4168-125">Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="d4168-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="d4168-126">string</span><span class="sxs-lookup"><span data-stu-id="d4168-126">string</span></span>        | <span data-ttu-id="d4168-127">Уникальный идентификатор события входной записи</span><span class="sxs-lookup"><span data-stu-id="d4168-127">Unique identifier of the sign-in event</span></span> |
| `ServicePrincipalName` | <span data-ttu-id="d4168-128">string</span><span class="sxs-lookup"><span data-stu-id="d4168-128">string</span></span>        | <span data-ttu-id="d4168-129">Имя директора службы, который инициировал вход</span><span class="sxs-lookup"><span data-stu-id="d4168-129">Name of the service principal that initiated the sign-in</span></span>  |
| `ServicePrincipalId`   | <span data-ttu-id="d4168-130">string</span><span class="sxs-lookup"><span data-stu-id="d4168-130">string</span></span>        | <span data-ttu-id="d4168-131">Уникальный идентификатор директора службы, который инициировал вход</span><span class="sxs-lookup"><span data-stu-id="d4168-131">Unique identifier of the service principal that initiated the sign-in</span></span>  |
| `ResourceDisplayName`  | <span data-ttu-id="d4168-132">string</span><span class="sxs-lookup"><span data-stu-id="d4168-132">string</span></span>        | <span data-ttu-id="d4168-133">Отображение имени доступного ресурса</span><span class="sxs-lookup"><span data-stu-id="d4168-133">Display name of the resource accessed</span></span>  |
| `ResourceId`           | <span data-ttu-id="d4168-134">string</span><span class="sxs-lookup"><span data-stu-id="d4168-134">string</span></span>        | <span data-ttu-id="d4168-135">Уникальный идентификатор доступного ресурса</span><span class="sxs-lookup"><span data-stu-id="d4168-135">Unique identifier of the resource accessed</span></span>  |
| `ResourceTenantId`     | <span data-ttu-id="d4168-136">string</span><span class="sxs-lookup"><span data-stu-id="d4168-136">string</span></span>        | <span data-ttu-id="d4168-137">Уникальный идентификатор клиента доступного ресурса</span><span class="sxs-lookup"><span data-stu-id="d4168-137">Unique identifier of the tenant of the resource accessed</span></span> |
| `IPAddress`            | <span data-ttu-id="d4168-138">string</span><span class="sxs-lookup"><span data-stu-id="d4168-138">string</span></span>        | <span data-ttu-id="d4168-139">IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="d4168-139">IP address assigned to the endpoint and used during related network communications</span></span>  |
| `Country`          | <span data-ttu-id="d4168-140">string</span><span class="sxs-lookup"><span data-stu-id="d4168-140">string</span></span>        | <span data-ttu-id="d4168-141">Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="d4168-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `State`                | <span data-ttu-id="d4168-142">string</span><span class="sxs-lookup"><span data-stu-id="d4168-142">string</span></span>        | <span data-ttu-id="d4168-143">Состояние, в котором произошла входная информация при наличии</span><span class="sxs-lookup"><span data-stu-id="d4168-143">State where the sign-in occurred, if available</span></span> |
| `City`                 | <span data-ttu-id="d4168-144">string</span><span class="sxs-lookup"><span data-stu-id="d4168-144">string</span></span>        | <span data-ttu-id="d4168-145">Город, в котором находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="d4168-145">City where the account user is located</span></span>  |
| `Latitude`             | <span data-ttu-id="d4168-146">string</span><span class="sxs-lookup"><span data-stu-id="d4168-146">string</span></span>        | <span data-ttu-id="d4168-147">Координаты расположения входного знака с севера на юг</span><span class="sxs-lookup"><span data-stu-id="d4168-147">The north to south coordinates of the sign-in location</span></span> |
| `Longitude`            | <span data-ttu-id="d4168-148">string</span><span class="sxs-lookup"><span data-stu-id="d4168-148">string</span></span>        | <span data-ttu-id="d4168-149">Координаты расположения входного знака с востока на запад</span><span class="sxs-lookup"><span data-stu-id="d4168-149">The east to west coordinates of the sign-in location</span></span> |
| `RequestId`            | <span data-ttu-id="d4168-150">string</span><span class="sxs-lookup"><span data-stu-id="d4168-150">string</span></span>        | <span data-ttu-id="d4168-151">Уникальный идентификатор запроса</span><span class="sxs-lookup"><span data-stu-id="d4168-151">Unique identifier of the request</span></span> |
|`ReportId` | <span data-ttu-id="d4168-152">string</span><span class="sxs-lookup"><span data-stu-id="d4168-152">string</span></span> | <span data-ttu-id="d4168-153">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d4168-153">Unique identifier for the event</span></span> |

 

## <a name="related-articles"></a><span data-ttu-id="d4168-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d4168-154">Related articles</span></span>

-   [<span data-ttu-id="d4168-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="d4168-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="d4168-156">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="d4168-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="d4168-157">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="d4168-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="d4168-158">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="d4168-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
