---
title: Действия после миграции для миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Сводка. Действия после миграции после перехода из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в Office 365 службы в новом немецком регионе центра обработки данных.
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930419"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="7363b-103">Действия после миграции для миграции из Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="7363b-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="7363b-104">В следующих разделах предусматриваются действия после миграции для нескольких служб после перехода из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в Office 365 службы в новом немецком регионе центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="7363b-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="7363b-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="7363b-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="7363b-106">Федерарная проверка подлинности Azure AD с помощью AD FS</span><span class="sxs-lookup"><span data-stu-id="7363b-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="7363b-107">**Применяется к:** Все клиенты, использующие федератированную проверку подлинности с помощью AD FS</span><span class="sxs-lookup"><span data-stu-id="7363b-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="7363b-108">Step(s)</span><span class="sxs-lookup"><span data-stu-id="7363b-108">Step(s)</span></span> | <span data-ttu-id="7363b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7363b-109">Description</span></span> | <span data-ttu-id="7363b-110">Влияние</span><span class="sxs-lookup"><span data-stu-id="7363b-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="7363b-111">Удаление доверчивых партийных трастов из Microsoft Cloud Deutschland AD FS.</span><span class="sxs-lookup"><span data-stu-id="7363b-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="7363b-112">После завершения подключения к Azure AD организация полностью использует Office 365 и больше не подключена к Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="7363b-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="7363b-113">На этом этапе клиенту необходимо удалить доверение доверчивых сторон конечным точкам Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="7363b-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="7363b-114">Это можно сделать только в том случае, если ни одно из приложений клиента не указывает на конечные точки Microsoft Cloud Deutschland, когда Azure AD будет использовать в качестве поставщика удостоверений (IdP).</span><span class="sxs-lookup"><span data-stu-id="7363b-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="7363b-115">Федерационные организации проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="7363b-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="7363b-116">Утверждения группы</span><span class="sxs-lookup"><span data-stu-id="7363b-116">Group approvals</span></span>
<span data-ttu-id="7363b-117">**Применяется к:** Конечные пользователи, запросы на утверждение группы Azure AD не были утверждены за последние 30 дней до миграции</span><span class="sxs-lookup"><span data-stu-id="7363b-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="7363b-118">Step(s)</span><span class="sxs-lookup"><span data-stu-id="7363b-118">Step(s)</span></span> | <span data-ttu-id="7363b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="7363b-119">Description</span></span> | <span data-ttu-id="7363b-120">Влияние</span><span class="sxs-lookup"><span data-stu-id="7363b-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="7363b-121">Запросы на вступление в группу Azure AD в течение последних 30 дней до миграции необходимо будет снова запрашивать, если первоначальный запрос не был утвержден.</span><span class="sxs-lookup"><span data-stu-id="7363b-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="7363b-122">Клиенты конечных пользователей должны будут использовать панель Access для отправки запроса на повторное присоединение к группе Azure AD, если эти запросы не были утверждены за последние 30 дней до переноса.</span><span class="sxs-lookup"><span data-stu-id="7363b-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="7363b-123">Как конечный пользователь:</span><span class="sxs-lookup"><span data-stu-id="7363b-123">As an end-user:</span></span> <ol><li><span data-ttu-id="7363b-124">Перейдите к [панели Access.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</span><span class="sxs-lookup"><span data-stu-id="7363b-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="7363b-125">Найдите группу Azure AD, для которой утверждение членства ожидалось в течение 30 дней до миграции.</span><span class="sxs-lookup"><span data-stu-id="7363b-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="7363b-126">Запрос на повторное вступление в группу Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7363b-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="7363b-127">Запросы на вступление в группу, активную менее чем за 30 дней до миграции, не могут быть утверждены, если они не будут снова запрашиваться после миграции.</span><span class="sxs-lookup"><span data-stu-id="7363b-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="7363b-128">Настраиваемые обновления DNS</span><span class="sxs-lookup"><span data-stu-id="7363b-128">Custom DNS updates</span></span>
<span data-ttu-id="7363b-129">**Применяется к:**  Все клиенты, управляющие своими зонами DNS</span><span class="sxs-lookup"><span data-stu-id="7363b-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="7363b-130">Step(s)</span><span class="sxs-lookup"><span data-stu-id="7363b-130">Step(s)</span></span> | <span data-ttu-id="7363b-131">Описание</span><span class="sxs-lookup"><span data-stu-id="7363b-131">Description</span></span> | <span data-ttu-id="7363b-132">Влияние</span><span class="sxs-lookup"><span data-stu-id="7363b-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="7363b-133">Обновление локальной службЫ DNS для конечных точек Office 365 служб.</span><span class="sxs-lookup"><span data-stu-id="7363b-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="7363b-134">Записи DNS с управляемым клиентом, указывающие на Microsoft Cloud Deutschland, должны быть обновлены, чтобы указать на конечные точки Office 365 глобальных служб.</span><span class="sxs-lookup"><span data-stu-id="7363b-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="7363b-135">Обратитесь к [доменам в центре администрирования Microsoft 365](https://admin.microsoft.com/Adminportal/Home#/Domains) и применяйте изменения в конфигурации DNS.</span><span class="sxs-lookup"><span data-stu-id="7363b-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="7363b-136">Невыполнение этого может привести к сбою службы или клиентов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="7363b-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="7363b-137">Сторонние службы</span><span class="sxs-lookup"><span data-stu-id="7363b-137">Third-party services</span></span>
<span data-ttu-id="7363b-138">**Применяется к:** Клиенты, использующие сторонние службы для конечных точек Office 365 служб</span><span class="sxs-lookup"><span data-stu-id="7363b-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="7363b-139">Step(s)</span><span class="sxs-lookup"><span data-stu-id="7363b-139">Step(s)</span></span> | <span data-ttu-id="7363b-140">Описание</span><span class="sxs-lookup"><span data-stu-id="7363b-140">Description</span></span> | <span data-ttu-id="7363b-141">Влияние</span><span class="sxs-lookup"><span data-stu-id="7363b-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="7363b-142">Обновление партнеров и сторонних служб для конечных точек Office 365 служб.</span><span class="sxs-lookup"><span data-stu-id="7363b-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="7363b-143">Сторонние службы и партнеры, которые указывают на Office 365 Германии, должны быть обновлены, чтобы указать на конечные точки Office 365 служб.</span><span class="sxs-lookup"><span data-stu-id="7363b-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="7363b-144">Пример. Перерегистрируйтесь в соответствии с вашими поставщиками и партнерами, если это доступно, версия приложения-галереи.</span><span class="sxs-lookup"><span data-stu-id="7363b-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="7363b-145">Указать все настраиваемые приложения, Graph API `graph.microsoft.de` от до `graph.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="7363b-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="7363b-146">Другие API с измененными конечными точками также должны быть обновлены, если они будут заемными.</span><span class="sxs-lookup"><span data-stu-id="7363b-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="7363b-147">Измените все непредназначимые корпоративные приложения, чтобы перенаправить их на конечные точки по всему миру.</span><span class="sxs-lookup"><span data-stu-id="7363b-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="7363b-148">Обязательное действие.</span><span class="sxs-lookup"><span data-stu-id="7363b-148">Required action.</span></span> <span data-ttu-id="7363b-149">Невыполнение этого может привести к сбою службы или клиентов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="7363b-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||