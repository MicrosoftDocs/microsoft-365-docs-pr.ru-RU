---
title: Предоставление доступа к поставщику управляемых служб безопасности (MSSP)
description: Узнайте об изменениях из Центра безопасности Защитника Майкрософт в центр безопасности Microsoft 365
keywords: Начало работы с центром безопасности Microsoft 365, Microsoft Defender для Office 365, Microsoft Defender для endpoint, MDO, MDE, единой области стекла, конвергентного портала, портала безопасности, портала безопасности защитника
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 4b34d3ea20716fb2424d9317b8a51c088a5714a6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935357"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="87303-104">Предоставление доступа к поставщику управляемых служб безопасности (MSSP)</span><span class="sxs-lookup"><span data-stu-id="87303-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="87303-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="87303-105">**Applies to:**</span></span>

- [<span data-ttu-id="87303-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87303-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="87303-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="87303-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="87303-108">Чтобы реализовать решение с делегированием доступа с несколькими клиентами, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="87303-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="87303-109">В [центре](/windows/security/threat-protection/microsoft-defender-atp/rbac) безопасности Microsoft 365 включить управление доступом на основе ролей в Defender for Endpoint и подключиться к группам Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="87303-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="87303-110">Настройка [пакетов доступа к управлению для](/azure/active-directory/governance/identity-governance-overview) запроса доступа и подготовка.</span><span class="sxs-lookup"><span data-stu-id="87303-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="87303-111">Управление запросами и аудитами доступа [в Microsoft Myaccess.](/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="87303-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="87303-112">Включить элементы управления доступом на основе ролей в Microsoft Defender для конечной точки в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87303-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="87303-113">**Создание групп доступа для ресурсов MSSP в AAD клиента: Группы**</span><span class="sxs-lookup"><span data-stu-id="87303-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="87303-114">Эти группы будут связаны с ролями, которые вы создаете в Центре безопасности Defender for Endpoint в Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87303-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="87303-115">Для этого в клиенте AD-клиенте создайте три группы.</span><span class="sxs-lookup"><span data-stu-id="87303-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="87303-116">В нашем примере мы создадим следующие группы:</span><span class="sxs-lookup"><span data-stu-id="87303-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="87303-117">Аналитик уровня 1</span><span class="sxs-lookup"><span data-stu-id="87303-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="87303-118">Аналитик уровня 2</span><span class="sxs-lookup"><span data-stu-id="87303-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="87303-119">Утверждения аналитика MSSP</span><span class="sxs-lookup"><span data-stu-id="87303-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="87303-120">Создание ролей Defender для конечных точек для соответствующих уровней доступа в защитнике клиентов для конечной точки в роли и группы центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87303-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="87303-121">Чтобы включить RBAC в центре безопасности Microsoft 365 клиента, вы сможете получить доступ к > **endpoints** ролей & групп > ролей с учетной записью пользователя с правами глобального администратора или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="87303-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Изображение доступа MSSP](../../media/mssp-access.png)

    <span data-ttu-id="87303-123">Затем создайте роли RBAC для удовлетворения потребностей уровня MSSP SOC.</span><span class="sxs-lookup"><span data-stu-id="87303-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="87303-124">Связывать эти роли с созданными группами пользователей с помощью "Назначены группы пользователей".</span><span class="sxs-lookup"><span data-stu-id="87303-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="87303-125">Две возможные роли:</span><span class="sxs-lookup"><span data-stu-id="87303-125">Two possible roles:</span></span>

    - <span data-ttu-id="87303-126">**Аналитики уровня 1**</span><span class="sxs-lookup"><span data-stu-id="87303-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="87303-127">Выполните все действия, за исключением живого ответа и управления настройками безопасности.</span><span class="sxs-lookup"><span data-stu-id="87303-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="87303-128">**Аналитики уровня 2**</span><span class="sxs-lookup"><span data-stu-id="87303-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="87303-129">Возможности уровня 1 с добавлением [живого ответа](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="87303-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="87303-130">Дополнительные сведения см. в дополнительных сведениях Об использовании управления [доступом на основе ролей.](/windows/security/threat-protection/microsoft-defender-atp/rbac)</span><span class="sxs-lookup"><span data-stu-id="87303-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="87303-131">Настройка пакетов доступа к управлению</span><span class="sxs-lookup"><span data-stu-id="87303-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="87303-132">**Добавление MSSP в качестве связанной организации в AAD клиента: управление удостоверением**</span><span class="sxs-lookup"><span data-stu-id="87303-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="87303-133">Добавление MSSP в качестве связанной организации позволит MSSP запрашивать и получать доступ.</span><span class="sxs-lookup"><span data-stu-id="87303-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="87303-134">Для этого в клиенте AD-клиенте можно получить доступ к организации Identity Governance: Connected.</span><span class="sxs-lookup"><span data-stu-id="87303-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="87303-135">Добавьте новую организацию и ищите клиента msSP Analyst с помощью tenant ID или Domain.</span><span class="sxs-lookup"><span data-stu-id="87303-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="87303-136">Мы предлагаем создать отдельный клиент AD для аналитиков MSSP.</span><span class="sxs-lookup"><span data-stu-id="87303-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="87303-137">**Создание каталога ресурсов в AAD клиента: управление удостоверением**</span><span class="sxs-lookup"><span data-stu-id="87303-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="87303-138">Каталоги ресурсов — это логическое собрание пакетов доступа, созданных в клиенте AD-клиента.</span><span class="sxs-lookup"><span data-stu-id="87303-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="87303-139">Для этого в клиенте AD-клиенте необходимо получить доступ к управлению удостоверениями: каталоги и добавить **новый каталог.**</span><span class="sxs-lookup"><span data-stu-id="87303-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="87303-140">В нашем примере мы назовем это **msSP Accesses**.</span><span class="sxs-lookup"><span data-stu-id="87303-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Изображение нового каталога](../../media/goverance-catalog.png)

    <span data-ttu-id="87303-142">Дополнительные сведения см. [в книге Создание каталога ресурсов.](/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="87303-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="87303-143">**Создание пакетов доступа для ресурсов MSSP Customer AAD: Управление удостоверениями**</span><span class="sxs-lookup"><span data-stu-id="87303-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="87303-144">Пакеты доступа — это коллекция прав и доступов, которые запросчику будет предоставлено после утверждения.</span><span class="sxs-lookup"><span data-stu-id="87303-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="87303-145">Для этого в клиенте AD-клиенте необходимо получить доступ к управлению удостоверениями: пакеты доступа и **добавить новый пакет доступа.**</span><span class="sxs-lookup"><span data-stu-id="87303-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="87303-146">Создание пакета доступа для утверждения MSSP и каждого уровня аналитики.</span><span class="sxs-lookup"><span data-stu-id="87303-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="87303-147">Например, следующая конфигурация аналитики уровня 1 создает пакет доступа, который:</span><span class="sxs-lookup"><span data-stu-id="87303-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="87303-148">Требуется члену группы AD **msSP Analyst Approvers** для авторизации новых запросов</span><span class="sxs-lookup"><span data-stu-id="87303-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="87303-149">Имеет ежегодные обзоры доступа, в которых аналитики SOC могут запрашивать расширение доступа</span><span class="sxs-lookup"><span data-stu-id="87303-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="87303-150">Запросы могут запрашиваться только пользователями в клиенте MSSP SOC</span><span class="sxs-lookup"><span data-stu-id="87303-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="87303-151">Срок действия авто доступа истекает через 365 дней</span><span class="sxs-lookup"><span data-stu-id="87303-151">Access auto expires after 365 days</span></span>

    ![Изображение нового пакета доступа](../../media/new-access-package.png)

    <span data-ttu-id="87303-153">Дополнительные сведения см. в [дополнительных сведениях о создании нового пакета доступа.](/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="87303-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="87303-154">**Предоставление ссылки запроса на доступ к ресурсам MSSP из AAD клиента: управление удостоверением**</span><span class="sxs-lookup"><span data-stu-id="87303-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="87303-155">Ссылка портала My Access используется аналитиками MSSP SOC для запроса доступа через созданные пакеты доступа.</span><span class="sxs-lookup"><span data-stu-id="87303-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="87303-156">Ссылка долговечна, что означает, что эта же ссылка может использоваться со временем для новых аналитиков.</span><span class="sxs-lookup"><span data-stu-id="87303-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="87303-157">Запрос аналитика отправляется в очередь для утверждения с помощью **утверждений аналитиков MSSP.**</span><span class="sxs-lookup"><span data-stu-id="87303-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![Изображение свойств доступа](../../media/access-properties.png)

    <span data-ttu-id="87303-159">Ссылка расположена на странице обзор каждого пакета доступа.</span><span class="sxs-lookup"><span data-stu-id="87303-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="87303-160">Управление доступом</span><span class="sxs-lookup"><span data-stu-id="87303-160">Manage access</span></span> 

1. <span data-ttu-id="87303-161">Просмотр и авторизации запросов доступа в myaccess клиента и/или MSSP.</span><span class="sxs-lookup"><span data-stu-id="87303-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="87303-162">Запросы доступа управляются в клиенте My Access членами группы утверждения аналитиков MSSP.</span><span class="sxs-lookup"><span data-stu-id="87303-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="87303-163">Для этого необходимо получить доступ к myaccess клиента с помощью:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="87303-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="87303-164">Пример.</span><span class="sxs-lookup"><span data-stu-id="87303-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="87303-165">Утверждение или отказ в запросах в разделе **Утверждения** пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="87303-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="87303-166">На этом этапе был предусмотрен доступ аналитика, и каждый аналитик должен иметь доступ к Центру безопасности Microsoft 365 клиента:</span><span class="sxs-lookup"><span data-stu-id="87303-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="87303-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` с разрешениями и ролями, которые им были назначены.</span><span class="sxs-lookup"><span data-stu-id="87303-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87303-168">Делегированная возможность доступа к Microsoft Defender для конечной точки в центре безопасности Microsoft 365 в настоящее время позволяет получить доступ к одному клиенту в окне браузера.</span><span class="sxs-lookup"><span data-stu-id="87303-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>