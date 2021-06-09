---
title: Microsoft 365 и Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Узнайте, как управлять службой удостоверений пользователей Azure AD в Microsoft 365 с помощью облачных или гибридных моделей удостоверений.
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905708"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="8bdb8-103">Microsoft 365 и Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8bdb8-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="8bdb8-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="8bdb8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8bdb8-105">Microsoft 365 использует Azure Active Directory (Azure AD), облачную службу идентификации и проверки подлинности пользователей, включенную в Microsoft 365 подписки, для управления удостоверениями и проверкой подлинности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="8bdb8-106">Правильная настройка инфраструктуры удостоверений имеет жизненно важное значение для управления доступом Microsoft 365 пользователей и разрешениями для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="8bdb8-107">Перед началом работы посмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="8bdb8-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="8bdb8-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="8bdb8-109">Ваш первый выбор планирования — Microsoft 365 удостоверений.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="8bdb8-110">Microsoft 365 удостоверений</span><span class="sxs-lookup"><span data-stu-id="8bdb8-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="8bdb8-111">Чтобы планировать учетные записи пользователей, сначала необходимо понять две модели удостоверений в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="8bdb8-112">Вы можете поддерживать удостоверения организации только в облаке или поддерживать свои идентификаторы доменных служб Active Directory (AD DS) и использовать их для проверки подлинности при доступе пользователей к облачным службам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="8bdb8-113">Вот два типа удостоверений, а также их наиболее подходящие и полезные свойства.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="8bdb8-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8bdb8-114">Attribute</span></span> | <span data-ttu-id="8bdb8-115">Облачное удостоверение</span><span class="sxs-lookup"><span data-stu-id="8bdb8-115">Cloud-only identity</span></span> | <span data-ttu-id="8bdb8-116">Гибридное удостоверение</span><span class="sxs-lookup"><span data-stu-id="8bdb8-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="8bdb8-117">**Определение**</span><span class="sxs-lookup"><span data-stu-id="8bdb8-117">**Definition**</span></span> | <span data-ttu-id="8bdb8-118">Учетная запись пользователя существует только в клиенте Azure AD для Microsoft 365 подписки.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="8bdb8-119">Учетная запись пользователя существует в AD DS, а копия также находится в клиенте Azure AD для Microsoft 365 подписки.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="8bdb8-120">Учетная запись пользователя в Azure AD также может включать версию с hashed паролем учетной записи пользователя AD DS.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="8bdb8-121">**Проверка Microsoft 365 проверки подлинности учетных данных пользователей**</span><span class="sxs-lookup"><span data-stu-id="8bdb8-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="8bdb8-122">Клиент Azure AD для Microsoft 365 выполняет проверку подлинности с помощью учетной записи облачного удостоверения.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="8bdb8-123">Клиент Azure AD для Microsoft 365 обрабатывает процесс проверки подлинности или перенаправляет пользователя другому поставщику удостоверений.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="8bdb8-124">**Оптимально для**.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-124">**Best for**</span></span> | <span data-ttu-id="8bdb8-125">Организации, которые не имеют или нуждаются в локальной AD DS.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="8bdb8-126">Организации, использующие AD DS или другого поставщика удостоверений.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="8bdb8-127">**Наибольшее преимущество**</span><span class="sxs-lookup"><span data-stu-id="8bdb8-127">**Greatest benefit**</span></span> | <span data-ttu-id="8bdb8-128">Простой в использовании.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-128">Simple to use.</span></span> <span data-ttu-id="8bdb8-129">Дополнительные средства каталога или серверы не требуются.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="8bdb8-130">Пользователи могут использовать те же учетные данные при доступе к локальному или облачному ресурсам.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="8bdb8-131">Облачное удостоверение</span><span class="sxs-lookup"><span data-stu-id="8bdb8-131">Cloud-only identity</span></span>

<span data-ttu-id="8bdb8-132">Облачное удостоверение основано на учетных записях пользователей, которые существуют только в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="8bdb8-133">Идентификатор облачного использования обычно используется небольшими организациями, которые не имеют локальных серверов или не используют AD DS для управления локальными удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="8bdb8-134">Вот основные компоненты идентификатора только для облака.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-134">Here are the basic components of cloud-only identity.</span></span>
 
![Основные компоненты идентификатора только для облака](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="8bdb8-136">Как локально, так и удаленные (онлайн) пользователи используют свои учетные записи пользователей Azure AD и пароли для доступа Microsoft 365 облачных служб.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="8bdb8-137">Azure AD проверяет подлинность учетных данных на основе хранимых на этой платформе учетных записей и паролей.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="8bdb8-138">Администрирование</span><span class="sxs-lookup"><span data-stu-id="8bdb8-138">Administration</span></span>
<span data-ttu-id="8bdb8-139">Так как учетные записи пользователей хранятся только в Azure AD, вы управляете облачными удостоверениями с помощью таких средств, как центр администрирования Microsoft 365 и [Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md) [](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="8bdb8-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](../admin/add-users/index.yml) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="8bdb8-140">Гибридное удостоверение</span><span class="sxs-lookup"><span data-stu-id="8bdb8-140">Hybrid identity</span></span>

<span data-ttu-id="8bdb8-141">Гибридное удостоверение использует учетные записи, которые возникают в локальной AD DS и имеют копию в клиенте Azure AD Microsoft 365 подписки.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="8bdb8-142">Однако большинство изменений течет только в одну сторону.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-142">However, most changes only flow one way.</span></span> <span data-ttu-id="8bdb8-143">Изменения, внесенные в учетные записи пользователей AD DS, синхронизируются с их копией в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="8bdb8-144">Но изменения, внесенные в облачные учетные записи в Azure AD, такие как новые учетные записи пользователей, не синхронизируются с AD DS.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="8bdb8-145">Azure AD Подключение обеспечивает текущую синхронизацию учетных записей.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="8bdb8-146">Он выполняется на локальном сервере, проверяет изменения в AD DS и передает эти изменения в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="8bdb8-147">Azure AD Подключение позволяет фильтровать синхронизированные учетные записи и синхронизировать хеш-версию паролей пользователей, известная как синхронизация хеш-кодов паролей (PHS).</span><span class="sxs-lookup"><span data-stu-id="8bdb8-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="8bdb8-148">При использовании гибридного удостоверения авторитетным источником сведений об учетной записи является локальная система AD DS.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="8bdb8-149">Это означает, что вы выполняете задачи администрирования в основном локально, которые затем синхронизируются с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="8bdb8-150">Ниже компоненты гибридного удостоверения.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-150">Here are the components of hybrid identity.</span></span>

![Компоненты гибридной идентификации](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="8bdb8-152">Клиент Azure AD имеет копию учетных записей AD DS.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="8bdb8-153">В этой конфигурации как локально, так и удаленные пользователи, Microsoft 365 облачные службы, сдают проверку подлинности в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="8bdb8-154">Для синхронизации учетных записей пользователей для гибридной идентификации всегда Подключение Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="8bdb8-155">Синхронизированные учетные записи пользователей в Azure AD необходимы для выполнения назначения лицензий и управления группой, настройки разрешений и других административных задач, которые связаны с учетными записями пользователей.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="8bdb8-156">Администрирование</span><span class="sxs-lookup"><span data-stu-id="8bdb8-156">Administration</span></span>

<span data-ttu-id="8bdb8-157">Поскольку исходные и авторитетные учетные записи пользователей хранятся в локальной AD DS, вы управляете удостоверениями с помощью тех же средств, что и управление AD DS.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="8bdb8-158">Центр администрирования Microsoft 365 PowerShell для управления синхронизированными учетными записями пользователей в Azure AD Microsoft 365 не используется.</span><span class="sxs-lookup"><span data-stu-id="8bdb8-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="8bdb8-159">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="8bdb8-159">Next step</span></span>

<span data-ttu-id="8bdb8-160">Если вам нужна облачная модель удостоверений, см. в [примере Идентификатор только для облака.](cloud-only-identities.md)</span><span class="sxs-lookup"><span data-stu-id="8bdb8-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="8bdb8-161">Если вам нужна гибридная модель удостоверений, см. в [примере Hybrid identity.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="8bdb8-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="8bdb8-162">См. также</span><span class="sxs-lookup"><span data-stu-id="8bdb8-162">See also</span></span>

[<span data-ttu-id="8bdb8-163">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8bdb8-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)