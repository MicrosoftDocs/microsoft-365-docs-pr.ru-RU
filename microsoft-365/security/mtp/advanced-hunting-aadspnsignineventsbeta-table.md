---
title: Таблица AADSpnSignInEventsBeta в продвинутой схеме охоты
description: Сведения о сведениях, связанных с руководителем службы Azure Active Directory и таблицой событий, связанных с управляемым входом удостоверений, в таблице расширенных схем охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: 5050f4f91d61369e927eae15ca7c156a17792c24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924544"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="6c12a-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="6c12a-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="6c12a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6c12a-105">**Applies to:**</span></span>

- <span data-ttu-id="6c12a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c12a-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="6c12a-107">В настоящее время таблица находится в стадии бета-версии и предлагается на краткосрочной основе, чтобы разрешить вам охотиться на руководителя `AADSpnSignInEventsBeta` службы Azure Active Directory (AAD) и управляемых событий регистрации удостоверений.</span><span class="sxs-lookup"><span data-stu-id="6c12a-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="6c12a-108">В конечном итоге мы переместим все сведения о схеме входов в `IdentityLogonEvents` таблицу.</span><span class="sxs-lookup"><span data-stu-id="6c12a-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="6c12a-109">Пользователи, которые могут получить доступ к Microsoft 365 Defender через интегрированное решение Microsoft Defender для конечной точки Центра безопасности Azure, но не имеют лицензий для Microsoft Defender для Office, Microsoft Defender for Identity или Microsoft Cloud App Security, не смогут просмотреть эту схему.</span><span class="sxs-lookup"><span data-stu-id="6c12a-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="6c12a-110">Таблица в продвинутой схеме охоты содержит сведения о директоре службы Azure Active Directory и управляемых входных знаках `AADSpnSignInEventsBeta` удостоверений. Дополнительные новости о различных типах входных входов можно узнать в отчетах о действиях для регистрации [Azure Active Directory — предварительный просмотр.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="6c12a-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="6c12a-111">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="6c12a-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6c12a-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="6c12a-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="6c12a-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="6c12a-113">Column name</span></span>     | <span data-ttu-id="6c12a-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6c12a-114">Data type</span></span> | <span data-ttu-id="6c12a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6c12a-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="6c12a-116">datetime</span><span class="sxs-lookup"><span data-stu-id="6c12a-116">datetime</span></span>      | <span data-ttu-id="6c12a-117">Дата и время создания записи</span><span class="sxs-lookup"><span data-stu-id="6c12a-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="6c12a-118">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-118">string</span></span>        | <span data-ttu-id="6c12a-119">Приложение, которое выполнило записанную акцию</span><span class="sxs-lookup"><span data-stu-id="6c12a-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="6c12a-120">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-120">string</span></span>        | <span data-ttu-id="6c12a-121">Уникальный идентификатор для приложения</span><span class="sxs-lookup"><span data-stu-id="6c12a-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="6c12a-122">boolean</span><span class="sxs-lookup"><span data-stu-id="6c12a-122">boolean</span></span>       | <span data-ttu-id="6c12a-123">Указывает, был ли вход инициирован управляемым удостоверением</span><span class="sxs-lookup"><span data-stu-id="6c12a-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="6c12a-124">int</span><span class="sxs-lookup"><span data-stu-id="6c12a-124">int</span></span>        | <span data-ttu-id="6c12a-125">Содержит код ошибки при ошибке при входе.</span><span class="sxs-lookup"><span data-stu-id="6c12a-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="6c12a-126">Чтобы найти описание определенного кода ошибки, посетите <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="6c12a-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="6c12a-127">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-127">string</span></span>        | <span data-ttu-id="6c12a-128">Уникальный идентификатор события входной записи</span><span class="sxs-lookup"><span data-stu-id="6c12a-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="6c12a-129">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-129">string</span></span>        | <span data-ttu-id="6c12a-130">Имя директора службы, который инициировал вход</span><span class="sxs-lookup"><span data-stu-id="6c12a-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="6c12a-131">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-131">string</span></span>        | <span data-ttu-id="6c12a-132">Уникальный идентификатор директора службы, который инициировал вход</span><span class="sxs-lookup"><span data-stu-id="6c12a-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="6c12a-133">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-133">string</span></span>        | <span data-ttu-id="6c12a-134">Отображение имени доступного ресурса</span><span class="sxs-lookup"><span data-stu-id="6c12a-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="6c12a-135">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-135">string</span></span>        | <span data-ttu-id="6c12a-136">Уникальный идентификатор доступного ресурса</span><span class="sxs-lookup"><span data-stu-id="6c12a-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="6c12a-137">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-137">string</span></span>        | <span data-ttu-id="6c12a-138">Уникальный идентификатор клиента доступного ресурса</span><span class="sxs-lookup"><span data-stu-id="6c12a-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="6c12a-139">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-139">string</span></span>        | <span data-ttu-id="6c12a-140">IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций</span><span class="sxs-lookup"><span data-stu-id="6c12a-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="6c12a-141">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-141">string</span></span>        | <span data-ttu-id="6c12a-142">Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="6c12a-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="6c12a-143">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-143">string</span></span>        | <span data-ttu-id="6c12a-144">Состояние, в котором произошла входная информация при наличии</span><span class="sxs-lookup"><span data-stu-id="6c12a-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="6c12a-145">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-145">string</span></span>        | <span data-ttu-id="6c12a-146">Город, в котором находится пользователь учетной записи</span><span class="sxs-lookup"><span data-stu-id="6c12a-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="6c12a-147">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-147">string</span></span>        | <span data-ttu-id="6c12a-148">Координаты расположения входного знака с севера на юг</span><span class="sxs-lookup"><span data-stu-id="6c12a-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="6c12a-149">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-149">string</span></span>        | <span data-ttu-id="6c12a-150">Координаты расположения входного знака с востока на запад</span><span class="sxs-lookup"><span data-stu-id="6c12a-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="6c12a-151">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-151">string</span></span>        | <span data-ttu-id="6c12a-152">Уникальный идентификатор запроса</span><span class="sxs-lookup"><span data-stu-id="6c12a-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="6c12a-153">string</span><span class="sxs-lookup"><span data-stu-id="6c12a-153">string</span></span> | <span data-ttu-id="6c12a-154">Уникальный идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6c12a-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="6c12a-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6c12a-155">Related articles</span></span>

-   [<span data-ttu-id="6c12a-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="6c12a-156">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="6c12a-157">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="6c12a-157">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="6c12a-158">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="6c12a-158">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="6c12a-159">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="6c12a-159">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)