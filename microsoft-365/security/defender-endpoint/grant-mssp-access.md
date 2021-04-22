---
title: Предоставление доступа к поставщику управляемых служб безопасности (MSSP)
description: Предпринять необходимые действия для настройки интеграции MSSP с Microsoft Defender для конечной точки
keywords: поставщик управляемых служб безопасности, mssp, настройка, интеграция
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 320355f838db5dbb1540350e95e4cc0645acd805
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932755"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="ceb4c-104">Предоставление доступа к поставщику управляемых служб безопасности (MSSP) (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="ceb4c-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ceb4c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-105">**Applies to:**</span></span>
- [<span data-ttu-id="ceb4c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ceb4c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ceb4c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceb4c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="ceb4c-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ceb4c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ceb4c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="ceb4c-110">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ceb4c-111">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ceb4c-112">Чтобы реализовать решение с делегированием доступа с несколькими клиентами, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ceb4c-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="ceb4c-113">Включить [управление доступом на основе ролей](rbac.md) в Defender для конечной точки и подключиться к группам Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="ceb4c-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="ceb4c-114">Настройка [пакетов доступа к управлению для](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) запроса доступа и подготовка.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-114">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="ceb4c-115">Управление запросами и аудитами доступа [в Microsoft Myaccess.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="ceb4c-115">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="ceb4c-116">Включить элементы управления доступом на основе ролей в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ceb4c-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="ceb4c-117">**Создание групп доступа для ресурсов MSSP в AAD клиента: Группы**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="ceb4c-118">Эти группы будут связаны с ролями, которые вы создаете в Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="ceb4c-119">Для этого в клиенте AD-клиенте создайте три группы.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="ceb4c-120">В нашем примере мы создадим следующие группы:</span><span class="sxs-lookup"><span data-stu-id="ceb4c-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="ceb4c-121">Аналитик уровня 1</span><span class="sxs-lookup"><span data-stu-id="ceb4c-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="ceb4c-122">Аналитик уровня 2</span><span class="sxs-lookup"><span data-stu-id="ceb4c-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="ceb4c-123">Утверждения аналитика MSSP</span><span class="sxs-lookup"><span data-stu-id="ceb4c-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="ceb4c-124">Создание ролей Defender для конечной точки для соответствующих уровней доступа в защитнике клиента для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="ceb4c-125">Чтобы включить RBAC в центре безопасности microsoft Defender клиента, вы сможете получить доступ к > разрешениям **>** ролей и "Включить роли" из учетной записи пользователя с правами глобального администратора или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Изображение доступа MSSP](images/mssp-access.png)

    <span data-ttu-id="ceb4c-127">Затем создайте роли RBAC для удовлетворения потребностей уровня MSSP SOC.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="ceb4c-128">Связывать эти роли с созданными группами пользователей с помощью "Назначены группы пользователей".</span><span class="sxs-lookup"><span data-stu-id="ceb4c-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="ceb4c-129">Две возможные роли:</span><span class="sxs-lookup"><span data-stu-id="ceb4c-129">Two possible roles:</span></span>

    - <span data-ttu-id="ceb4c-130">**Аналитики уровня 1**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="ceb4c-131">Выполните все действия, за исключением живого ответа и управления настройками безопасности.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="ceb4c-132">**Аналитики уровня 2**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="ceb4c-133">Возможности уровня 1 с добавлением [живого ответа](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="ceb4c-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="ceb4c-134">Дополнительные сведения см. в дополнительных сведениях Об использовании управления [доступом на основе ролей.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="ceb4c-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="ceb4c-135">Настройка пакетов доступа к управлению</span><span class="sxs-lookup"><span data-stu-id="ceb4c-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="ceb4c-136">**Добавление MSSP в качестве связанной организации в AAD клиента: управление удостоверением**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="ceb4c-137">Добавление MSSP в качестве связанной организации позволит MSSP запрашивать и получать доступ.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="ceb4c-138">Для этого в клиенте AD-клиенте можно получить доступ к организации Identity Governance: Connected.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="ceb4c-139">Добавьте новую организацию и ищите клиента msSP Analyst с помощью tenant ID или Domain.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="ceb4c-140">Мы предлагаем создать отдельный клиент AD для аналитиков MSSP.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="ceb4c-141">**Создание каталога ресурсов в AAD клиента: управление удостоверением**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="ceb4c-142">Каталоги ресурсов — это логическое собрание пакетов доступа, созданных в клиенте AD-клиента.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="ceb4c-143">Для этого в клиенте AD-клиенте необходимо получить доступ к управлению удостоверениями: каталоги и добавить **новый каталог.**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="ceb4c-144">В нашем примере мы назовем это **msSP Accesses**.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Изображение нового каталога](images/goverance-catalog.png)

    <span data-ttu-id="ceb4c-146">Дополнительные сведения см. [в книге Создание каталога ресурсов.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="ceb4c-146">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="ceb4c-147">**Создание пакетов доступа для ресурсов MSSP Customer AAD: Управление удостоверениями**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="ceb4c-148">Пакеты доступа — это коллекция прав и доступов, которые запросчику будет предоставлено после утверждения.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="ceb4c-149">Для этого в клиенте AD-клиенте необходимо получить доступ к управлению удостоверениями: пакеты доступа и **добавить новый пакет доступа.**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="ceb4c-150">Создание пакета доступа для утверждения MSSP и каждого уровня аналитики.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="ceb4c-151">Например, следующая конфигурация аналитики уровня 1 создает пакет доступа, который:</span><span class="sxs-lookup"><span data-stu-id="ceb4c-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="ceb4c-152">Требуется члену группы AD **msSP Analyst Approvers** для авторизации новых запросов</span><span class="sxs-lookup"><span data-stu-id="ceb4c-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="ceb4c-153">Имеет ежегодные обзоры доступа, в которых аналитики SOC могут запрашивать расширение доступа</span><span class="sxs-lookup"><span data-stu-id="ceb4c-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="ceb4c-154">Запросы могут запрашиваться только пользователями в клиенте MSSP SOC</span><span class="sxs-lookup"><span data-stu-id="ceb4c-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="ceb4c-155">Срок действия авто доступа истекает через 365 дней</span><span class="sxs-lookup"><span data-stu-id="ceb4c-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ceb4c-156">![Изображение нового пакета доступа](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="ceb4c-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="ceb4c-157">Дополнительные сведения см. в [дополнительных сведениях о создании нового пакета доступа.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="ceb4c-157">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="ceb4c-158">**Предоставление ссылки запроса на доступ к ресурсам MSSP из AAD клиента: управление удостоверением**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="ceb4c-159">Ссылка портала My Access используется аналитиками MSSP SOC для запроса доступа через созданные пакеты доступа.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="ceb4c-160">Ссылка долговечна, что означает, что эта же ссылка может использоваться со временем для новых аналитиков.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="ceb4c-161">Запрос аналитика отправляется в очередь для утверждения с помощью **утверждений аналитиков MSSP.**</span><span class="sxs-lookup"><span data-stu-id="ceb4c-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ceb4c-162">![Изображение свойств доступа](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="ceb4c-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="ceb4c-163">Ссылка расположена на странице обзор каждого пакета доступа.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="ceb4c-164">Управление доступом</span><span class="sxs-lookup"><span data-stu-id="ceb4c-164">Manage access</span></span> 

1. <span data-ttu-id="ceb4c-165">Просмотр и авторизации запросов доступа в myaccess клиента и/или MSSP.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="ceb4c-166">Запросы доступа управляются в клиенте My Access членами группы утверждения аналитиков MSSP.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="ceb4c-167">Для этого необходимо получить доступ к myaccess клиента с помощью:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="ceb4c-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="ceb4c-168">Пример.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="ceb4c-169">Утверждение или отказ в запросах в разделе **Утверждения** пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ceb4c-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="ceb4c-170">На этом этапе был предусмотрен доступ аналитика, и каждый аналитик должен иметь доступ к Центру безопасности Microsoft Defender клиента: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="ceb4c-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="ceb4c-171">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="ceb4c-171">Related topics</span></span>
- [<span data-ttu-id="ceb4c-172">Получение доступа к порталу клиентов MSSP</span><span class="sxs-lookup"><span data-stu-id="ceb4c-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="ceb4c-173">Настройка уведомлений оповещений</span><span class="sxs-lookup"><span data-stu-id="ceb4c-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="ceb4c-174">Получение оповещений от владельца клиента</span><span class="sxs-lookup"><span data-stu-id="ceb4c-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

