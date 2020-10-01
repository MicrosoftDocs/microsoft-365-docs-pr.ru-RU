---
title: Модели удостоверений Microsoft 365 и Azure Active Directory
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
description: Узнайте, как управлять службой удостоверений пользователей Azure AD в Microsoft 365, используя только облачные или гибридные модели удостоверений.
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327955"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="5551d-103">Модели удостоверений Microsoft 365 и Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5551d-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="5551d-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="5551d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5551d-105">Microsoft 365 использует Azure Active Directory (Azure AD), службу удостоверений и удостоверений пользователей на основе облачной службы проверки подлинности, включенную в подписку Microsoft 365, для управления удостоверениями и проверкой подлинности в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5551d-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="5551d-106">Правильная настройка инфраструктуры удостоверений крайне важна для управления доступом пользователей и разрешений Microsoft 365 для Организации.</span><span class="sxs-lookup"><span data-stu-id="5551d-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="5551d-107">Перед началом работы посмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5551d-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="5551d-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="5551d-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="5551d-109">Первым вариантом планирования является модель удостоверений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5551d-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="5551d-110">Модели удостоверений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5551d-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="5551d-111">Чтобы спланировать учетные записи пользователей, сначала необходимо ознакомиться с двумя моделями идентификации в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5551d-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="5551d-112">Вы можете поддерживать удостоверения вашей организации только в облаке, а также поддерживать локальные удостоверения доменных служб Active Directory (AD DS) и использовать их для проверки подлинности при доступе пользователей к Microsoft 365 Cloud Services.</span><span class="sxs-lookup"><span data-stu-id="5551d-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="5551d-113">Ниже приведены два типа удостоверений, а также их наилучшее соответствие и преимущества.</span><span class="sxs-lookup"><span data-stu-id="5551d-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="5551d-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5551d-114">Attribute</span></span> | <span data-ttu-id="5551d-115">Облачное удостоверение</span><span class="sxs-lookup"><span data-stu-id="5551d-115">Cloud-only identity</span></span> | <span data-ttu-id="5551d-116">Гибридное удостоверение</span><span class="sxs-lookup"><span data-stu-id="5551d-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="5551d-117">**Определение**</span><span class="sxs-lookup"><span data-stu-id="5551d-117">**Definition**</span></span> | <span data-ttu-id="5551d-118">Учетная запись пользователя существует только в клиенте Azure AD для вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5551d-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="5551d-119">Учетная запись пользователя существует в доменных службах Active Directory, а также копия в клиенте Azure AD для вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5551d-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="5551d-120">Учетная запись пользователя в Azure AD также может включать хешированную версию уже хэшированного пароля учетной записи пользователя AD DS.</span><span class="sxs-lookup"><span data-stu-id="5551d-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="5551d-121">**Проверка подлинности учетных данных пользователей в Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="5551d-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="5551d-122">Клиент Azure AD для вашей подписки на Microsoft 365 выполняет проверку подлинности с учетной записью удостоверения в облаке.</span><span class="sxs-lookup"><span data-stu-id="5551d-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="5551d-123">Клиент Azure AD для вашей подписки на Microsoft 365 обрабатывает процесс проверки подлинности или перенаправляет пользователя другому поставщику удостоверений.</span><span class="sxs-lookup"><span data-stu-id="5551d-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="5551d-124">**Оптимально для**.</span><span class="sxs-lookup"><span data-stu-id="5551d-124">**Best for**</span></span> | <span data-ttu-id="5551d-125">Организации, которые не имеют локальных доменных служб Active Directory или не нуждаются в них.</span><span class="sxs-lookup"><span data-stu-id="5551d-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="5551d-126">Организации, использующие AD DS или другого поставщика удостоверений.</span><span class="sxs-lookup"><span data-stu-id="5551d-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="5551d-127">**Наибольшая выгода**</span><span class="sxs-lookup"><span data-stu-id="5551d-127">**Greatest benefit**</span></span> | <span data-ttu-id="5551d-128">Простота использования.</span><span class="sxs-lookup"><span data-stu-id="5551d-128">Simple to use.</span></span> <span data-ttu-id="5551d-129">Не требуются дополнительные средства каталогов или серверы.</span><span class="sxs-lookup"><span data-stu-id="5551d-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="5551d-130">Пользователи могут использовать одни и те же учетные данные при доступе к локальным или облачным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="5551d-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="5551d-131">Облачное удостоверение</span><span class="sxs-lookup"><span data-stu-id="5551d-131">Cloud-only identity</span></span>

<span data-ttu-id="5551d-132">Для удостоверения с единственным облаком используются учетные записи пользователей, существующие только в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5551d-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="5551d-133">В небольших организациях, которые не имеют локальных серверов или не используют доменные службы Active Directory для управления локальными удостоверениями, обычно используется облачное удостоверение.</span><span class="sxs-lookup"><span data-stu-id="5551d-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="5551d-134">Ниже приведены основные компоненты удостоверения "только облако".</span><span class="sxs-lookup"><span data-stu-id="5551d-134">Here are the basic components of cloud-only identity.</span></span>
 
![Основные компоненты удостоверения "только облако"](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="5551d-136">Как локальные, так и удаленные пользователи используют учетные записи пользователей и пароли Azure AD для доступа к облачным службам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5551d-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="5551d-137">Azure AD выполняет проверку подлинности учетных данных пользователя на основе сохраненных учетных записей пользователей и паролей.</span><span class="sxs-lookup"><span data-stu-id="5551d-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="5551d-138">Администрирование</span><span class="sxs-lookup"><span data-stu-id="5551d-138">Administration</span></span>
<span data-ttu-id="5551d-139">Так как учетные записи пользователей хранятся только в Azure AD, управление облачными удостоверениями осуществляется с помощью таких средств, как [центр администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/) и [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5551d-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="5551d-140">Гибридное удостоверение</span><span class="sxs-lookup"><span data-stu-id="5551d-140">Hybrid identity</span></span>

<span data-ttu-id="5551d-141">Гибридное удостоверение использует учетные записи, созданные в локальных доменных службах Active Directory и имеющие копию в клиенте Azure AD подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5551d-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="5551d-142">Однако большинство изменений переходят только один из них.</span><span class="sxs-lookup"><span data-stu-id="5551d-142">However, most changes only flow one way.</span></span> <span data-ttu-id="5551d-143">Изменения, вносимые в учетные записи пользователей доменных служб Active Directory, синхронизируются с их копией в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5551d-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="5551d-144">Но изменения, внесенные в облачные учетные записи в Azure AD, такие как новые учетные записи пользователей, не синхронизируются с AD DS.</span><span class="sxs-lookup"><span data-stu-id="5551d-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="5551d-145">Azure AD Connect обеспечивает текущую синхронизацию учетных записей.</span><span class="sxs-lookup"><span data-stu-id="5551d-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="5551d-146">Он выполняется на локальном сервере, проверяет изменения в доменных СЛУЖБах Active Directory и пересылает эти изменения в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5551d-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="5551d-147">Azure AD Connect предоставляет возможность фильтрации синхронизируемых учетных записей и синхронизации хешированной версии паролей пользователей, называемой синхронизацией хеша паролей (ФС).</span><span class="sxs-lookup"><span data-stu-id="5551d-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="5551d-148">При внедрении гибридного удостоверения для сведений об учетной записи в локальной службе AD DS используется достоверный источник.</span><span class="sxs-lookup"><span data-stu-id="5551d-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="5551d-149">Это означает, что вы выполняете задачи по администрированию преимущественно в локальной среде, которые затем синхронизируются с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5551d-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="5551d-150">Ниже приведены компоненты гибридного удостоверения.</span><span class="sxs-lookup"><span data-stu-id="5551d-150">Here are the components of hybrid identity.</span></span>

![Компоненты гибридного удостоверения](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="5551d-152">У клиента Azure AD есть копия учетных записей доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5551d-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="5551d-153">В этой конфигурации как локальные, так и удаленные пользователи, обращающиеся к Microsoft 365 Cloud Services, проходят проверку подлинности в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5551d-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="5551d-154">Всегда необходимо использовать Azure AD Connect для синхронизации учетных записей пользователей с гибридным удостоверением.</span><span class="sxs-lookup"><span data-stu-id="5551d-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="5551d-155">Учетные записи синхронизированных пользователей в Azure AD необходимы для выполнения задач по управлению назначением лицензий и групп, а также для настройки разрешений и других административных задач, включающих учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="5551d-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="5551d-156">Администрирование</span><span class="sxs-lookup"><span data-stu-id="5551d-156">Administration</span></span>

<span data-ttu-id="5551d-157">Так как исходные и достоверные учетные записи пользователей хранятся в локальной службе AD DS, вы управляете своими удостоверениями с помощью тех же средств, что и управление AD DS.</span><span class="sxs-lookup"><span data-stu-id="5551d-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="5551d-158">Вы не используете центр администрирования Microsoft 365 или PowerShell для Microsoft 365 для управления синхронизированными учетными записями пользователей в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5551d-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="5551d-159">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="5551d-159">Next step</span></span>

<span data-ttu-id="5551d-160">Если требуется только Облачная модель удостоверений, ознакомьтесь со статьей " [удостоверение только в облаке](cloud-only-identities.md)".</span><span class="sxs-lookup"><span data-stu-id="5551d-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="5551d-161">Если вам нужна Гибридная модель идентификации, ознакомьтесь со статьей [Гибридная идентификация](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="5551d-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="5551d-162">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5551d-162">See also</span></span>

[<span data-ttu-id="5551d-163">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="5551d-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
