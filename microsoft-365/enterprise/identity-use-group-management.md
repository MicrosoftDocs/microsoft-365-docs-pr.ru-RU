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
ms.openlocfilehash: 49cdb0c3d394cb423d0565d7093f1b32b6661158
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801714"
---
# <a name="step-5-use-groups-for-management"></a><span data-ttu-id="b3592-103">Шаг 5. Управление с помощью групп</span><span class="sxs-lookup"><span data-stu-id="b3592-103">Step 5: Use groups for management</span></span>

![Этап 2. Удостоверения](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="b3592-105">Разрешение пользователям создавать собственные группы и управлять ими</span><span class="sxs-lookup"><span data-stu-id="b3592-105">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="b3592-106">*Это необязательная процедура, применимая к версиям Microsoft 365 E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="b3592-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b3592-107">В этом разделе описывается, как определить группы Azure Active Directory (Azure AD), которыми будут управлять владельцы групп, а не ИТ-администраторы.</span><span class="sxs-lookup"><span data-stu-id="b3592-107">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="b3592-108">Эта функция называется *самостоятельным управлением группами* и позволяет владельцам групп, которым не назначена роль администратора, создавать группы безопасности и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="b3592-108">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="b3592-109">Пользователи могут отправлять заявки на членство в группе безопасности, которые отправляются владельцу группы, а не ИТ-администратору.</span><span class="sxs-lookup"><span data-stu-id="b3592-109">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator.</span></span> <span data-ttu-id="b3592-110">Это позволяет делегировать повседневное управление членством в группах владельцам команд, проектов или компаний, которые понимают пользу группы для бизнеса и могут управлять членством в ней.</span><span class="sxs-lookup"><span data-stu-id="b3592-110">This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="b3592-111">Самостоятельное управление группами поддерживается только для групп безопасности Azure AD и групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3592-111">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="b3592-112">Оно недоступно для групп, поддерживающих почту, списков рассылки и других групп, синхронизированных с локальными доменными службами Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b3592-112">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="b3592-113">Дополнительные сведения см. в статье [Настройка самостоятельного управления группами в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="b3592-113">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="b3592-114">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-self-service-groups).</span><span class="sxs-lookup"><span data-stu-id="b3592-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="b3592-115">Настройка динамического членства в группах</span><span class="sxs-lookup"><span data-stu-id="b3592-115">Set up dynamic group membership</span></span>

<span data-ttu-id="b3592-116">*Это необязательная процедура, применимая к версиям Microsoft 365 E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="b3592-116">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b3592-117">В этом разделе описывается создание ряда правил, которые автоматически добавляют или удаляют учетные записи в списке участников группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b3592-117">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="b3592-118">Это называется *динамическим членством в группах*.</span><span class="sxs-lookup"><span data-stu-id="b3592-118">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="b3592-119">Правила основаны на атрибутах учетных записей, например атрибуте "Отдел" или "Страна".</span><span class="sxs-lookup"><span data-stu-id="b3592-119">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="b3592-120">Ниже рассказывается, как применяются такие правила.</span><span class="sxs-lookup"><span data-stu-id="b3592-120">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="b3592-121">Если новая учетная запись пользователя соответствует всем правилам для группы, она становится членом группы.</span><span class="sxs-lookup"><span data-stu-id="b3592-121">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="b3592-122">Если учетная запись пользователя не является членом группы, но ее атрибуты изменились так, что теперь она соответствует всем правилам для группы, она становится членом группы.</span><span class="sxs-lookup"><span data-stu-id="b3592-122">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="b3592-123">Если учетная запись пользователя не соответствует всем правилам для группы, она не будет добавлена в группу.</span><span class="sxs-lookup"><span data-stu-id="b3592-123">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="b3592-124">Если учетная запись пользователя является членом группы, но ее атрибуты изменились так, что теперь она не соответствует всем правилам для группы, она будет удалена из группы.</span><span class="sxs-lookup"><span data-stu-id="b3592-124">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="b3592-p105">Чтобы использовать функцию динамического членства в группах, вам потребуется сначала определить наборы групп с общими наборами атрибутов учетных записей пользователей. Например, все сотрудники отдела продаж должны быть в группе Azure AD "Отдел продаж", так как у этих учетных записей атрибут "Отдел" имеет значение "Отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="b3592-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="b3592-127">См. [инструкции по созданию и настройке правил для динамических групп Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b3592-127">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="b3592-128">Ниже перечислены результаты, которые вы получите после выполнения инструкций с данного этапа.</span><span class="sxs-lookup"><span data-stu-id="b3592-128">The results of this section are:</span></span>

- <span data-ttu-id="b3592-129">Набор групп Azure AD, которые можно настроить для использовании функции динамического членства.</span><span class="sxs-lookup"><span data-stu-id="b3592-129">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="b3592-130">Набор правил в каждой динамической группе.</span><span class="sxs-lookup"><span data-stu-id="b3592-130">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b3592-132">Руководства по лаборатории тестирования: автоматизация лицензий и членства в группах</span><span class="sxs-lookup"><span data-stu-id="b3592-132">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="b3592-133">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-dyn-groups).</span><span class="sxs-lookup"><span data-stu-id="b3592-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="b3592-134">Настройка автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="b3592-134">Set up automatic licensing</span></span>

<span data-ttu-id="b3592-135">*Это необязательная процедура, применимая к версиям Microsoft 365 E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="b3592-135">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b3592-136">В этом разделе описывается настройка групп безопасности в Azure AD на автоматическое назначение лицензий из набора подписок всем участникам группы.</span><span class="sxs-lookup"><span data-stu-id="b3592-136">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="b3592-137">Это называется *лицензированием на основе групп*.</span><span class="sxs-lookup"><span data-stu-id="b3592-137">This is known as *group-based licensing*.</span></span> <span data-ttu-id="b3592-138">Когда учетная запись добавляется в группу или удаляется из нее, лицензии для подписок группы автоматически назначаются этой учетной записи или отменяются для нее.</span><span class="sxs-lookup"><span data-stu-id="b3592-138">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="b3592-139">Чтобы назначить соответствующую лицензию на Microsoft 365 корпоративный, нужно настроить группы безопасности Azure AD для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="b3592-139">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="b3592-140">Убедитесь, что у вас есть достаточно лицензий для всех участников группы.</span><span class="sxs-lookup"><span data-stu-id="b3592-140">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="b3592-141">Если лицензии закончатся, они не будут назначаться новым пользователям, пока эти лицензии не станут доступны.</span><span class="sxs-lookup"><span data-stu-id="b3592-141">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="b3592-142">*Лицензирование на основе групп* не следует настраивать для групп, содержащих учетные записи типа "бизнес-бизнес" (B2B) в Azure.</span><span class="sxs-lookup"><span data-stu-id="b3592-142">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="b3592-143">См. дополнительные сведения в статье [Основы группового лицензирования в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b3592-143">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="b3592-144">См. статью [Назначение лицензий пользователям в соответствии с членством в группах в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b3592-144">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="b3592-145">Ниже перечислены результаты, которые вы получите после выполнения инструкций с данного этапа.</span><span class="sxs-lookup"><span data-stu-id="b3592-145">The results of this section are:</span></span>

- <span data-ttu-id="b3592-146">Вы определили группы безопасности, подходящие для лицензирования на основе групп.</span><span class="sxs-lookup"><span data-stu-id="b3592-146">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="b3592-147">Вы настроили эти группы для лицензирования на основе групп.</span><span class="sxs-lookup"><span data-stu-id="b3592-147">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b3592-149">Руководства по лаборатории тестирования: автоматизация лицензий и членства в группах</span><span class="sxs-lookup"><span data-stu-id="b3592-149">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="b3592-150">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-group-license).</span><span class="sxs-lookup"><span data-stu-id="b3592-150">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![Шаг 6](./media/stepnumbers/Step6.png)| [<span data-ttu-id="b3592-152">Настройка управления удостоверениями</span><span class="sxs-lookup"><span data-stu-id="b3592-152">Configure identity governance</span></span>](identity-configure-identity-governance.md) |
