---
title: Управление группами Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Узнайте, как управлять Microsoft 365 группами.
ms.openlocfilehash: 529bdb874661329497b103a1207b90625ad33a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911011"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="be0f0-103">Управление группами Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="be0f0-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="be0f0-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="be0f0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="be0f0-105">Вы можете управлять Microsoft 365 различными способами, в зависимости от конфигурации.</span><span class="sxs-lookup"><span data-stu-id="be0f0-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="be0f0-106">Вы можете управлять учетными записями пользователей в центре [администрирования Microsoft 365](../admin/add-users/index.yml)PowerShell, в службах домена Active Directory (AD DS) или в центре администрирования [Azure Active Directory Azure AD.](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="be0f0-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="be0f0-107">Планирование, где и как вы будете управлять группами</span><span class="sxs-lookup"><span data-stu-id="be0f0-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="be0f0-108">Где и как можно управлять учетной записью пользователя, зависит от модели удостоверений, используемой для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="be0f0-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="be0f0-109">Две общие модели являются облачными и гибридными.</span><span class="sxs-lookup"><span data-stu-id="be0f0-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="be0f0-110">Только облако</span><span class="sxs-lookup"><span data-stu-id="be0f0-110">Cloud-only</span></span>

<span data-ttu-id="be0f0-111">Вы создаете и управляете группами с помощью:</span><span class="sxs-lookup"><span data-stu-id="be0f0-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="be0f0-112">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="be0f0-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- [<span data-ttu-id="be0f0-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="be0f0-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="be0f0-114">Центр администрирования Azure AD</span><span class="sxs-lookup"><span data-stu-id="be0f0-114">Azure AD admin center</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="be0f0-115">Гибридная среда</span><span class="sxs-lookup"><span data-stu-id="be0f0-115">Hybrid</span></span>

<span data-ttu-id="be0f0-116">Группы DS AD синхронизируются с Microsoft 365 из AD DS, поэтому для управления этими группами необходимо использовать локальное оборудование AD DS.</span><span class="sxs-lookup"><span data-stu-id="be0f0-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="be0f0-117">Можно также создавать и управлять группами Azure AD, которые отделены от групп AD DS, но могут содержать пользователей и группы из AD DS.</span><span class="sxs-lookup"><span data-stu-id="be0f0-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="be0f0-118">В этом случае можно использовать:</span><span class="sxs-lookup"><span data-stu-id="be0f0-118">In this case, you can use:</span></span>

- [<span data-ttu-id="be0f0-119">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="be0f0-119">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- [<span data-ttu-id="be0f0-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="be0f0-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="be0f0-121">Центр администрирования Azure AD</span><span class="sxs-lookup"><span data-stu-id="be0f0-121">Azure AD admin center</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="be0f0-122">Разрешение пользователям создавать собственные группы и управлять ими</span><span class="sxs-lookup"><span data-stu-id="be0f0-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="be0f0-123">Azure AD позволяет группам, которыми могут управлять владельцы групп, а не ИТ-администраторы.</span><span class="sxs-lookup"><span data-stu-id="be0f0-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="be0f0-124">Эта функция называется *самостоятельным управлением группами* и позволяет владельцам групп, которым не назначена роль администратора, создавать группы безопасности и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="be0f0-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="be0f0-125">Пользователи могут отправлять заявки на членство в группе безопасности, которые отправляются владельцу группы, а не ИТ-администратору.</span><span class="sxs-lookup"><span data-stu-id="be0f0-125">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator.</span></span> <span data-ttu-id="be0f0-126">Это позволяет делегировать повседневное управление членством в группах владельцам команд, проектов или компаний, которые понимают пользу группы для бизнеса и могут управлять членством в ней.</span><span class="sxs-lookup"><span data-stu-id="be0f0-126">This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="be0f0-127">Самостоятельное управление группами поддерживается только для групп безопасности Azure AD и групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="be0f0-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="be0f0-128">Она недоступна для групп с поддержкой почты, списков рассылки или какой-либо группы, синхронизированной с AD DS.</span><span class="sxs-lookup"><span data-stu-id="be0f0-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="be0f0-129">Дополнительные сведения см. в статье [Настройка самостоятельного управления группами в Azure Active Directory](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="be0f0-129">For more information, see the [instructions to configure an Azure AD group for self-service management](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="be0f0-130">Настройка динамического членства в группах</span><span class="sxs-lookup"><span data-stu-id="be0f0-130">Set up dynamic group membership</span></span>

<span data-ttu-id="be0f0-131">Azure AD поддерживает настройку ряда правил, которые автоматически добавляют или удаляют учетные записи пользователей в качестве членов группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be0f0-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="be0f0-132">Это называется *динамическим членством в группах*.</span><span class="sxs-lookup"><span data-stu-id="be0f0-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="be0f0-133">Правила основаны на атрибутах учетных записей, например атрибуте "Отдел" или "Страна".</span><span class="sxs-lookup"><span data-stu-id="be0f0-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="be0f0-134">Ниже описано, как применяются такие правила.</span><span class="sxs-lookup"><span data-stu-id="be0f0-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="be0f0-135">Если новая учетная запись пользователя соответствует всем правилам для группы, она становится членом группы.</span><span class="sxs-lookup"><span data-stu-id="be0f0-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="be0f0-136">Если учетная запись пользователя не является членом группы, но ее атрибуты изменились так, что теперь она соответствует всем правилам для группы, она становится членом группы.</span><span class="sxs-lookup"><span data-stu-id="be0f0-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="be0f0-137">Если учетная запись пользователя не соответствует всем правилам для группы, она не будет добавлена в группу.</span><span class="sxs-lookup"><span data-stu-id="be0f0-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="be0f0-138">Если учетная запись пользователя является членом группы, но ее атрибуты изменились так, что теперь она не соответствует всем правилам для группы, она будет удалена из группы.</span><span class="sxs-lookup"><span data-stu-id="be0f0-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="be0f0-p108">Чтобы использовать функцию динамического членства в группах, вам потребуется сначала определить наборы групп с общими наборами атрибутов учетных записей пользователей. Например, все сотрудники отдела продаж должны быть в группе Azure AD "Отдел продаж", так как у этих учетных записей атрибут "Отдел" имеет значение "Отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="be0f0-p108">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="be0f0-141">См. [инструкции по созданию и настройке правил для динамических групп Azure AD](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="be0f0-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="be0f0-142">Настройка автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="be0f0-142">Set up automatic licensing</span></span>

<span data-ttu-id="be0f0-143">Можно настроить группы безопасности в Azure AD, чтобы автоматически назначать лицензии из набора подписок всем участникам группы.</span><span class="sxs-lookup"><span data-stu-id="be0f0-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="be0f0-144">Это называется *лицензированием на основе групп*.</span><span class="sxs-lookup"><span data-stu-id="be0f0-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="be0f0-145">Когда учетная запись добавляется в группу или удаляется из нее, лицензии для подписок группы автоматически назначаются этой учетной записи или отменяются для нее.</span><span class="sxs-lookup"><span data-stu-id="be0f0-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="be0f0-146">Чтобы назначить соответствующую лицензию на Microsoft 365 корпоративный, нужно настроить группы безопасности Azure AD для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="be0f0-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="be0f0-147">Убедитесь, что у вас есть достаточно лицензий для всех участников группы.</span><span class="sxs-lookup"><span data-stu-id="be0f0-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="be0f0-148">Если лицензии закончатся, они не будут назначаться новым пользователям, пока эти лицензии не станут доступны.</span><span class="sxs-lookup"><span data-stu-id="be0f0-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="be0f0-149">Лицензирование на основе групп не следует настраивать для групп, содержащих учетные записи типа "бизнес-бизнес" (B2B) в Azure.</span><span class="sxs-lookup"><span data-stu-id="be0f0-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="be0f0-150">Дополнительные сведения см. в базовых сведениях о лицензировании на основе группы [в Azure AD.](/azure/active-directory/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="be0f0-150">For more information, see [Group-based licensing basics in Azure AD](/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="be0f0-151">См. [инструкции по настройке группового лицензирования для группы безопасности Azure.](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="be0f0-151">See the [instructions to configure group-based licensing for an Azure security group](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>