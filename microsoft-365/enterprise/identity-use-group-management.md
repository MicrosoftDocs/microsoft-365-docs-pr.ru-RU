---
title: Шаг 5. Управление с помощью групп.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Группы позволяют автоматизировать управление некоторыми административными задачами.
ms.openlocfilehash: 01bbce00457362ed0eb089e126f0d17f31237eb4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090809"
---
# <a name="step-5-use-groups-for-management"></a><span data-ttu-id="d0b85-103">Шаг 5. Управление с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="d0b85-103">Step 6: Use groups for easier management</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="d0b85-104">Разрешение пользователям создавать собственные группы и управлять ими</span><span class="sxs-lookup"><span data-stu-id="d0b85-104">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="d0b85-105">*Это необязательная процедура, применимая к наборам Microsoft 365 корпоративный E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="d0b85-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d0b85-106">В этом разделе описывается, как определить группы Azure Active Directory (Azure AD), которыми будут управлять владельцы групп, а не ИТ-администраторы.</span><span class="sxs-lookup"><span data-stu-id="d0b85-106">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="d0b85-107">Эта функция называется *самостоятельным управлением группами* и позволяет владельцам групп, которым не назначена роль администратора, создавать группы безопасности и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="d0b85-107">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="d0b85-108">Пользователи могут отправлять заявки на членство в группе безопасности, которые отправляются владельцу группы, а не ИТ-администратору.</span><span class="sxs-lookup"><span data-stu-id="d0b85-108">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator.</span></span> <span data-ttu-id="d0b85-109">Это позволяет делегировать повседневное управление членством в группах владельцам команд, проектов или компаний, которые понимают пользу группы для бизнеса и могут управлять членством в ней.</span><span class="sxs-lookup"><span data-stu-id="d0b85-109">This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="d0b85-110">Самостоятельное управление группами поддерживается только для групп безопасности Azure AD и групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="d0b85-110">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="d0b85-111">Оно недоступно для групп, поддерживающих почту, списков рассылки и других групп, синхронизированных с локальными доменными службами Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="d0b85-111">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="d0b85-112">Дополнительные сведения см. в статье [Настройка самостоятельного управления группами в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="d0b85-112">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="d0b85-113">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-self-service-groups).</span><span class="sxs-lookup"><span data-stu-id="d0b85-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="d0b85-114">Настройка динамического членства в группах</span><span class="sxs-lookup"><span data-stu-id="d0b85-114">Set up dynamic group membership</span></span>

<span data-ttu-id="d0b85-115">*Это необязательная процедура, применимая к наборам Microsoft 365 корпоративный E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="d0b85-115">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d0b85-116">В этом разделе описывается создание ряда правил, которые автоматически добавляют или удаляют учетные записи в списке участников группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d0b85-116">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="d0b85-117">Это называется *динамическим членством в группах*.</span><span class="sxs-lookup"><span data-stu-id="d0b85-117">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="d0b85-118">Правила основаны на атрибутах учетных записей, например атрибуте "Отдел" или "Страна".</span><span class="sxs-lookup"><span data-stu-id="d0b85-118">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="d0b85-119">Ниже рассказывается, как применяются такие правила.</span><span class="sxs-lookup"><span data-stu-id="d0b85-119">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="d0b85-120">Если новая учетная запись пользователя соответствует всем правилам для группы, она становится членом группы.</span><span class="sxs-lookup"><span data-stu-id="d0b85-120">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="d0b85-121">Если учетная запись пользователя не является членом группы, но ее атрибуты изменились так, что теперь она соответствует всем правилам для группы, она становится членом группы.</span><span class="sxs-lookup"><span data-stu-id="d0b85-121">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="d0b85-122">Если учетная запись пользователя не соответствует всем правилам для группы, она не будет добавлена в группу.</span><span class="sxs-lookup"><span data-stu-id="d0b85-122">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="d0b85-123">Если учетная запись пользователя является членом группы, но ее атрибуты изменились так, что теперь она не соответствует всем правилам для группы, она будет удалена из группы.</span><span class="sxs-lookup"><span data-stu-id="d0b85-123">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="d0b85-p105">Чтобы использовать функцию динамического членства в группах, вам потребуется сначала определить наборы групп с общими наборами атрибутов учетных записей пользователей. Например, все сотрудники отдела продаж должны быть в группе Azure AD "Отдел продаж", так как у этих учетных записей атрибут "Отдел" имеет значение "Отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="d0b85-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="d0b85-126">См. [инструкции по созданию и настройке правил для динамических групп Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="d0b85-126">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="d0b85-127">Ниже перечислены результаты, которые вы получите после выполнения инструкций с данного этапа.</span><span class="sxs-lookup"><span data-stu-id="d0b85-127">The results of this section are:</span></span>

- <span data-ttu-id="d0b85-128">Набор групп Azure AD, которые можно настроить для использовании функции динамического членства.</span><span class="sxs-lookup"><span data-stu-id="d0b85-128">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="d0b85-129">Набор правил в каждой динамической группе.</span><span class="sxs-lookup"><span data-stu-id="d0b85-129">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d0b85-131">Руководства по лаборатории тестирования: автоматизация лицензий и членства в группах</span><span class="sxs-lookup"><span data-stu-id="d0b85-131">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="d0b85-132">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-dyn-groups).</span><span class="sxs-lookup"><span data-stu-id="d0b85-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="d0b85-133">Настройка автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="d0b85-133">Set up automatic licensing</span></span>

<span data-ttu-id="d0b85-134">*Это необязательная процедура, применимая к наборам Microsoft 365 корпоративный E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="d0b85-134">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d0b85-135">В этом разделе описывается настройка групп безопасности в Azure AD на автоматическое назначение лицензий из набора подписок всем участникам группы.</span><span class="sxs-lookup"><span data-stu-id="d0b85-135">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="d0b85-136">Это называется *лицензированием на основе групп*.</span><span class="sxs-lookup"><span data-stu-id="d0b85-136">This is known as *group-based licensing*.</span></span> <span data-ttu-id="d0b85-137">Когда учетная запись добавляется в группу или удаляется из нее, лицензии для подписок группы автоматически назначаются этой учетной записи или отменяются для нее.</span><span class="sxs-lookup"><span data-stu-id="d0b85-137">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="d0b85-138">Чтобы назначить соответствующую лицензию на Microsoft 365 корпоративный, нужно настроить группы безопасности Azure AD для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="d0b85-138">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="d0b85-139">Убедитесь, что у вас есть достаточно лицензий для всех участников группы.</span><span class="sxs-lookup"><span data-stu-id="d0b85-139">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="d0b85-140">Если лицензии закончатся, они не будут назначаться новым пользователям, пока эти лицензии не станут доступны.</span><span class="sxs-lookup"><span data-stu-id="d0b85-140">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="d0b85-141">*Лицензирование на основе групп* не следует настраивать для групп, содержащих учетные записи типа "бизнес-бизнес" (B2B) в Azure.</span><span class="sxs-lookup"><span data-stu-id="d0b85-141">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="d0b85-142">См. дополнительные сведения в статье [Основы группового лицензирования в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="d0b85-142">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="d0b85-143">См. статью [Назначение лицензий пользователям в соответствии с членством в группах в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="d0b85-143">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="d0b85-144">Ниже перечислены результаты, которые вы получите после выполнения инструкций с данного этапа.</span><span class="sxs-lookup"><span data-stu-id="d0b85-144">The results of this section are:</span></span>

- <span data-ttu-id="d0b85-145">Вы определили группы безопасности, подходящие для лицензирования на основе групп.</span><span class="sxs-lookup"><span data-stu-id="d0b85-145">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="d0b85-146">Вы настроили эти группы для лицензирования на основе групп.</span><span class="sxs-lookup"><span data-stu-id="d0b85-146">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d0b85-148">Руководства по лаборатории тестирования: автоматизация лицензий и членства в группах</span><span class="sxs-lookup"><span data-stu-id="d0b85-148">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="d0b85-149">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-group-license).</span><span class="sxs-lookup"><span data-stu-id="d0b85-149">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="d0b85-150">Настройка управления удостоверениями</span><span class="sxs-lookup"><span data-stu-id="d0b85-150">Configure identity governance</span></span>](identity-configure-identity-governance.md) |
