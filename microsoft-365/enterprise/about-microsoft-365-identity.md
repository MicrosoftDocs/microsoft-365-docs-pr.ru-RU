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
description: Узнайте, как управлять службой удостоверений пользователей Azure AD в Microsoft 365 с помощью облачных или гибридных моделей удостоверений.
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327955"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="7db86-103">Модели удостоверений Microsoft 365 и Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7db86-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="7db86-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="7db86-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7db86-105">Microsoft 365 использует Azure Active Directory (Azure AD), облачную службу идентификации и проверки подлинности пользователей, включенную в подписку На Microsoft 365, для управления удостоверениями и проверкой подлинности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7db86-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="7db86-106">Правильная настройка инфраструктуры удостоверений очень важна для управления доступом пользователей Microsoft 365 и разрешениями для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7db86-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="7db86-107">Перед началом работы посмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7db86-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="7db86-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="7db86-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="7db86-109">Первым вариантом планирования является модель удостоверений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7db86-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="7db86-110">Модели удостоверений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7db86-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="7db86-111">Чтобы спланировать учетные записи пользователей, сначала необходимо понять две модели удостоверений в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7db86-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="7db86-112">Вы можете сохранить удостоверения организации только в облаке или сохранить свои удостоверения доменных служб Active Directory (AD DS) и использовать их для проверки подлинности при доступе пользователей к облачным службам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7db86-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="7db86-113">Вот два типа удостоверений, их наилучшее подгонка и преимущества.</span><span class="sxs-lookup"><span data-stu-id="7db86-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="7db86-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7db86-114">Attribute</span></span> | <span data-ttu-id="7db86-115">Облачное удостоверение</span><span class="sxs-lookup"><span data-stu-id="7db86-115">Cloud-only identity</span></span> | <span data-ttu-id="7db86-116">Гибридное удостоверение</span><span class="sxs-lookup"><span data-stu-id="7db86-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="7db86-117">**Определение**</span><span class="sxs-lookup"><span data-stu-id="7db86-117">**Definition**</span></span> | <span data-ttu-id="7db86-118">Учетная запись пользователя существует только в клиенте Azure AD для подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7db86-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="7db86-119">Учетная запись пользователя существует в AD DS, а копия также находится в клиенте Azure AD для подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7db86-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="7db86-120">Учетная запись пользователя в Azure AD также может включать в себя версию с уже схващенным паролем учетной записи пользователя AD DS.</span><span class="sxs-lookup"><span data-stu-id="7db86-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="7db86-121">**Проверка подлинности учетных данных пользователей в Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="7db86-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="7db86-122">Клиент Azure AD для подписки На Microsoft 365 выполняет проверку подлинности с помощью облачной учетной записи удостоверения.</span><span class="sxs-lookup"><span data-stu-id="7db86-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="7db86-123">Клиент Azure AD для подписки Microsoft 365 обрабатывает процесс проверки подлинности или перенаправляет пользователя к другому поставщику удостоверений.</span><span class="sxs-lookup"><span data-stu-id="7db86-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="7db86-124">**Оптимально для**.</span><span class="sxs-lookup"><span data-stu-id="7db86-124">**Best for**</span></span> | <span data-ttu-id="7db86-125">Организации, которые не имеют или не нуждаются в локальной AD DS.</span><span class="sxs-lookup"><span data-stu-id="7db86-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="7db86-126">Организации, использующие AD DS или другого поставщика удостоверений.</span><span class="sxs-lookup"><span data-stu-id="7db86-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="7db86-127">**Наибольшее преимущество**</span><span class="sxs-lookup"><span data-stu-id="7db86-127">**Greatest benefit**</span></span> | <span data-ttu-id="7db86-128">Простое в использовании.</span><span class="sxs-lookup"><span data-stu-id="7db86-128">Simple to use.</span></span> <span data-ttu-id="7db86-129">Дополнительные средства или серверы каталогов не требуются.</span><span class="sxs-lookup"><span data-stu-id="7db86-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="7db86-130">Пользователи могут использовать те же учетные данные при доступе к локальному или облачному ресурсу.</span><span class="sxs-lookup"><span data-stu-id="7db86-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="7db86-131">Облачное удостоверение</span><span class="sxs-lookup"><span data-stu-id="7db86-131">Cloud-only identity</span></span>

<span data-ttu-id="7db86-132">Для облачного удостоверения используются учетные записи пользователей, которые существуют только в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7db86-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="7db86-133">Облачные удостоверения обычно используются небольшими организациями, у которые не имеют локальных серверов или не используют AD DS для управления локальными удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="7db86-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="7db86-134">Вот основные компоненты облачной идентификации.</span><span class="sxs-lookup"><span data-stu-id="7db86-134">Here are the basic components of cloud-only identity.</span></span>
 
![Основные компоненты облачной идентификации](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="7db86-136">Как локально, так и удаленные (сетевые) пользователи используют свои учетные записи и пароли Azure AD для доступа к облачным службам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7db86-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="7db86-137">Azure AD аутентификация учетных данных пользователя на основе сохраненных учетных записей пользователей и паролей.</span><span class="sxs-lookup"><span data-stu-id="7db86-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="7db86-138">Администрирование</span><span class="sxs-lookup"><span data-stu-id="7db86-138">Administration</span></span>
<span data-ttu-id="7db86-139">Так как учетные записи пользователей хранятся только в Azure AD, вы управляете облачными удостоверениями с помощью таких средств, как Центр администрирования [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/) [и](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7db86-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="7db86-140">Гибридное удостоверение</span><span class="sxs-lookup"><span data-stu-id="7db86-140">Hybrid identity</span></span>

<span data-ttu-id="7db86-141">Гибридное удостоверение использует учетные записи, которые происходят из локальной службы AD DS и имеют копию в клиенте Azure AD подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7db86-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="7db86-142">Однако большинство изменений происходят только в одном случае.</span><span class="sxs-lookup"><span data-stu-id="7db86-142">However, most changes only flow one way.</span></span> <span data-ttu-id="7db86-143">Изменения, внесенные в учетные записи пользователей AD DS, синхронизируются с их копией в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7db86-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="7db86-144">Однако изменения, внесенные в облачные учетные записи в Azure AD, например новые учетные записи пользователей, не синхронизируются с AD DS.</span><span class="sxs-lookup"><span data-stu-id="7db86-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="7db86-145">Azure AD Connect обеспечивает текущую синхронизацию учетных записей.</span><span class="sxs-lookup"><span data-stu-id="7db86-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="7db86-146">Он выполняется на локальном сервере, проверяет изменения в AD DS и перенаправирует эти изменения в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7db86-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="7db86-147">Azure AD Connect позволяет фильтровать, какие учетные записи синхронизируются и следует ли синхронизировать хешизированную версию паролей пользователей, которая называется синхронизацией хеш-паролей (PHS).</span><span class="sxs-lookup"><span data-stu-id="7db86-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="7db86-148">При реализации гибридного удостоверения ваша локальное AD DS является до полномочного источника сведений об учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7db86-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="7db86-149">Это означает, что задачи администрирования выполняются в основном локально, которые затем синхронизируются с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7db86-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="7db86-150">Ниже компоненты гибридной идентификации.</span><span class="sxs-lookup"><span data-stu-id="7db86-150">Here are the components of hybrid identity.</span></span>

![Компоненты гибридной идентификации](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="7db86-152">У клиента Azure AD есть копия учетных записей AD DS.</span><span class="sxs-lookup"><span data-stu-id="7db86-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="7db86-153">В этой конфигурации как локально, так и удаленные пользователи, которые имеют доступ к облачным службам Microsoft 365, могут проверить подлинность в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7db86-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="7db86-154">Для синхронизации учетных записей пользователей с гибридными удостоверениями всегда необходимо использовать Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="7db86-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="7db86-155">Синхронизированные учетные записи пользователей в Azure AD необходимы для назначения лицензий и управления группой, настройки разрешений и других административных задач, в том числе учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="7db86-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="7db86-156">Администрирование</span><span class="sxs-lookup"><span data-stu-id="7db86-156">Administration</span></span>

<span data-ttu-id="7db86-157">Так как исходные и до полномонные учетные записи пользователей хранятся в локальной AD DS, вы управляете удостоверениями с помощью тех же средств, что и для управления AD DS.</span><span class="sxs-lookup"><span data-stu-id="7db86-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="7db86-158">Вы не используете Центр администрирования Microsoft 365 или PowerShell для Microsoft 365 для управления синхронизированными учетными записями пользователей в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7db86-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="7db86-159">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="7db86-159">Next step</span></span>

<span data-ttu-id="7db86-160">Если вам нужна модель облачного удостоверения, см. только [облачное удостоверение.](cloud-only-identities.md)</span><span class="sxs-lookup"><span data-stu-id="7db86-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="7db86-161">Если вам нужна гибридная модель удостоверений, см. ["Гибридное удостоверение".](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="7db86-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="7db86-162">См. также</span><span class="sxs-lookup"><span data-stu-id="7db86-162">See also</span></span>

[<span data-ttu-id="7db86-163">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="7db86-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
