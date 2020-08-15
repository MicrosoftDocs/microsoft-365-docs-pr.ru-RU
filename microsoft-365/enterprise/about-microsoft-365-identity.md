---
title: Модели удостоверений Microsoft 365 и Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 06/09/2020
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
ms.openlocfilehash: d91e14f678e487365805b024e4025e9a39db0c2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693538"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="13b4b-103">Модели удостоверений Microsoft 365 и Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="13b4b-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="13b4b-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="13b4b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="13b4b-105">Microsoft 365 использует Azure Active Directory (Azure AD), службу удостоверений и удостоверений пользователей на основе облачной службы проверки подлинности, включенную в подписку Microsoft 365, для управления удостоверениями и проверкой подлинности в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13b4b-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="13b4b-106">Правильная настройка инфраструктуры удостоверений крайне важна для управления доступом пользователей и разрешений Microsoft 365 для Организации.</span><span class="sxs-lookup"><span data-stu-id="13b4b-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="13b4b-107">Перед началом работы посмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13b4b-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="13b4b-108">Первым вариантом планирования является модель удостоверений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13b4b-108">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="13b4b-109">Модели удостоверений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="13b4b-109">Microsoft 365 identity models</span></span>

<span data-ttu-id="13b4b-110">Чтобы спланировать учетные записи пользователей, сначала необходимо ознакомиться с двумя моделями идентификации в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13b4b-110">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="13b4b-111">Вы можете поддерживать удостоверения вашей организации только в облаке, а также поддерживать локальные удостоверения доменных служб Active Directory (AD DS) и использовать их для проверки подлинности при доступе пользователей к Microsoft 365 Cloud Services.</span><span class="sxs-lookup"><span data-stu-id="13b4b-111">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="13b4b-112">Ниже приведены два типа удостоверений, а также их наилучшее соответствие и преимущества.</span><span class="sxs-lookup"><span data-stu-id="13b4b-112">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="13b4b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="13b4b-113">Attribute</span></span> | <span data-ttu-id="13b4b-114">Облачное удостоверение</span><span class="sxs-lookup"><span data-stu-id="13b4b-114">Cloud-only identity</span></span> | <span data-ttu-id="13b4b-115">Гибридная идентификация</span><span class="sxs-lookup"><span data-stu-id="13b4b-115">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="13b4b-116">**Определение**</span><span class="sxs-lookup"><span data-stu-id="13b4b-116">**Definition**</span></span> | <span data-ttu-id="13b4b-117">Учетная запись пользователя существует только в клиенте Azure AD для вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13b4b-117">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="13b4b-118">Учетная запись пользователя существует в доменных службах Active Directory, а также копия в клиенте Azure AD для вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13b4b-118">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="13b4b-119">Учетная запись пользователя в Azure AD также может включать хешированную версию уже хэшированного пароля учетной записи пользователя AD DS.</span><span class="sxs-lookup"><span data-stu-id="13b4b-119">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="13b4b-120">**Проверка подлинности учетных данных пользователей в Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="13b4b-120">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="13b4b-121">Клиент Azure AD для вашей подписки на Microsoft 365 выполняет проверку подлинности с учетной записью удостоверения в облаке.</span><span class="sxs-lookup"><span data-stu-id="13b4b-121">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="13b4b-122">Клиент Azure AD для вашей подписки на Microsoft 365 обрабатывает процесс проверки подлинности или перенаправляет пользователя другому поставщику удостоверений.</span><span class="sxs-lookup"><span data-stu-id="13b4b-122">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="13b4b-123">**Оптимально для**.</span><span class="sxs-lookup"><span data-stu-id="13b4b-123">**Best for**</span></span> | <span data-ttu-id="13b4b-124">Организации, которые не имеют локальных доменных служб Active Directory или не нуждаются в них.</span><span class="sxs-lookup"><span data-stu-id="13b4b-124">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="13b4b-125">Организации, использующие AD DS или другого поставщика удостоверений.</span><span class="sxs-lookup"><span data-stu-id="13b4b-125">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="13b4b-126">**Наибольшая выгода**</span><span class="sxs-lookup"><span data-stu-id="13b4b-126">**Greatest benefit**</span></span> | <span data-ttu-id="13b4b-127">Простота использования.</span><span class="sxs-lookup"><span data-stu-id="13b4b-127">Simple to use.</span></span> <span data-ttu-id="13b4b-128">Не требуются дополнительные средства каталогов или серверы.</span><span class="sxs-lookup"><span data-stu-id="13b4b-128">No extra directory tools or servers required.</span></span> | <span data-ttu-id="13b4b-129">Пользователи могут использовать одни и те же учетные данные при доступе к локальным или облачным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="13b4b-129">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="13b4b-130">Облачное удостоверение</span><span class="sxs-lookup"><span data-stu-id="13b4b-130">Cloud-only identity</span></span>

<span data-ttu-id="13b4b-131">Для удостоверения с единственным облаком используются учетные записи пользователей, существующие только в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="13b4b-131">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="13b4b-132">Облачное удостоверение обычно используется малыми организациями, не имеющими локальных серверов, или не использующими AD DS для управления локальными удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="13b4b-132">Cloud identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="13b4b-133">Ниже приведены основные компоненты удостоверения "только облако".</span><span class="sxs-lookup"><span data-stu-id="13b4b-133">Here are the basic components of cloud-only identity.</span></span>
 
![Основные компоненты удостоверения "только облако"](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="13b4b-135">Как локальные, так и удаленные пользователи используют учетные записи пользователей и пароли Azure AD для доступа к облачным службам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13b4b-135">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="13b4b-136">Azure AD выполняет проверку подлинности учетных данных пользователя на основе сохраненных учетных записей пользователей и паролей.</span><span class="sxs-lookup"><span data-stu-id="13b4b-136">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="13b4b-137">Администрирование</span><span class="sxs-lookup"><span data-stu-id="13b4b-137">Administration</span></span>
<span data-ttu-id="13b4b-138">Так как учетные записи пользователей хранятся только в Azure AD, управление облачными удостоверениями осуществляется с помощью таких средств, как [центр администрирования Microsoft 365](https://admin.microsoft.com) и [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="13b4b-138">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://admin.microsoft.com) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="13b4b-139">Гибридная идентификация</span><span class="sxs-lookup"><span data-stu-id="13b4b-139">Hybrid identity</span></span>

<span data-ttu-id="13b4b-140">Гибридное удостоверение использует учетные записи, созданные в локальных доменных службах Active Directory и имеющие копию в клиенте Azure AD подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13b4b-140">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="13b4b-141">Однако большинство изменений переходят только один из них.</span><span class="sxs-lookup"><span data-stu-id="13b4b-141">However, most changes only flow one way.</span></span> <span data-ttu-id="13b4b-142">Изменения, вносимые в учетные записи пользователей доменных служб Active Directory, синхронизируются с их копией в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="13b4b-142">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="13b4b-143">Но изменения, внесенные в облачные учетные записи в Azure AD, такие как новые учетные записи пользователей, не синхронизируются с AD DS.</span><span class="sxs-lookup"><span data-stu-id="13b4b-143">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="13b4b-144">Azure AD Connect обеспечивает текущую синхронизацию учетных записей.</span><span class="sxs-lookup"><span data-stu-id="13b4b-144">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="13b4b-145">Он выполняется на локальном сервере, проверяет изменения в доменных СЛУЖБах Active Directory и пересылает эти изменения в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="13b4b-145">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="13b4b-146">Azure AD Connect предоставляет возможность фильтрации синхронизируемых учетных записей и синхронизации хешированной версии паролей пользователей, называемой синхронизацией хеша паролей (ФС).</span><span class="sxs-lookup"><span data-stu-id="13b4b-146">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="13b4b-147">При внедрении гибридного удостоверения для сведений об учетной записи в локальной службе AD DS используется достоверный источник.</span><span class="sxs-lookup"><span data-stu-id="13b4b-147">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="13b4b-148">Это означает, что вы выполняете задачи по администрированию преимущественно в локальной среде, которые затем синхронизируются с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="13b4b-148">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="13b4b-149">Ниже приведены компоненты гибридного удостоверения.</span><span class="sxs-lookup"><span data-stu-id="13b4b-149">Here are the components of hybrid identity.</span></span>

![Компоненты гибридного удостоверения](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="13b4b-151">У клиента Azure AD есть копия учетных записей доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="13b4b-151">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="13b4b-152">В этой конфигурации как локальные, так и удаленные пользователи, обращающиеся к Microsoft 365 Cloud Services, проходят проверку подлинности в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="13b4b-152">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="13b4b-153">Всегда необходимо использовать Azure AD Connect для синхронизации учетных записей пользователей с гибридным удостоверением.</span><span class="sxs-lookup"><span data-stu-id="13b4b-153">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="13b4b-154">Учетные записи синхронизированных пользователей в Azure AD необходимы для выполнения задач по управлению назначением лицензий и групп, а также для настройки разрешений и других административных задач, включающих учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="13b4b-154">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="13b4b-155">Администрирование</span><span class="sxs-lookup"><span data-stu-id="13b4b-155">Administration</span></span>

<span data-ttu-id="13b4b-156">Так как первоначальные и полномочные учетные записи пользователей хранятся в локальной службе AD DS, вы управляете удостоверениями с теми же инструментами, что и AD DS, например с помощью средства "пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="13b4b-156">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as AD DS, such as the Active Directory Users and Computers tool.</span></span> 

<span data-ttu-id="13b4b-157">Вы не используете центр администрирования Microsoft 365 или PowerShell для Microsoft 365 для управления синхронизированными учетными записями пользователей в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="13b4b-157">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="13b4b-158">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="13b4b-158">Next step</span></span>

<span data-ttu-id="13b4b-159">Если требуется только Облачная модель удостоверений, ознакомьтесь со статьей " [удостоверение только в облаке](cloud-only-identities.md)".</span><span class="sxs-lookup"><span data-stu-id="13b4b-159">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="13b4b-160">Если вам нужна Гибридная модель идентификации, ознакомьтесь со статьей [Гибридная идентификация](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="13b4b-160">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="13b4b-161">См. также</span><span class="sxs-lookup"><span data-stu-id="13b4b-161">See also</span></span>

[<span data-ttu-id="13b4b-162">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="13b4b-162">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
