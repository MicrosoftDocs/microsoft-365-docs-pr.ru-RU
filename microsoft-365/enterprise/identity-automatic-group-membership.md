---
title: Шаг 15. Настройка динамического членства в группах
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается об автоматическом членстве в группах на основе атрибутов учетных записей и его настройке.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870955"
---
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="8d7da-103">Шаг 15. Настройка динамического членства в группах</span><span class="sxs-lookup"><span data-stu-id="8d7da-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="8d7da-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="8d7da-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="8d7da-p101">На этом шаге вы создадите ряд правил, автоматически добавляющих учетные записи пользователей в группу Azure AD и удаляющих их из нее. Такая функция называется *динамическим членством в группах*. Для этих правил используются атрибуты учетных записей пользователей, например атрибут "Отдел" или "Страна".</span><span class="sxs-lookup"><span data-stu-id="8d7da-p101">In Step 12, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as *dynamic group membership*. The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="8d7da-108">Ниже рассказывается, как применяются такие правила.</span><span class="sxs-lookup"><span data-stu-id="8d7da-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="8d7da-109">Если новая учетная запись пользователя соответствует всем правилам для группы, она становится членом группы.</span><span class="sxs-lookup"><span data-stu-id="8d7da-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="8d7da-110">Если учетная запись пользователя не является членом группы, но ее атрибуты изменились так, что теперь она соответствует всем правилам для группы, она становится членом группы.</span><span class="sxs-lookup"><span data-stu-id="8d7da-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="8d7da-111">Если учетная запись пользователя не соответствует всем правилам для группы, она не будет добавлена в группу.</span><span class="sxs-lookup"><span data-stu-id="8d7da-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="8d7da-112">Если учетная запись пользователя является членом группы, но ее атрибуты изменились так, что теперь она не соответствует всем правилам для группы, она будет удалена из группы.</span><span class="sxs-lookup"><span data-stu-id="8d7da-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="8d7da-p102">Чтобы использовать функцию динамического членства в группах, вам потребуется сначала определить наборы групп с общими наборами атрибутов учетных записей пользователей. Например, все сотрудники отдела продаж должны быть в группе Azure AD "Отдел продаж", так как у этих учетных записей атрибут "Отдел" имеет значение "Отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="8d7da-p102">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="8d7da-115">См. [инструкции по созданию и настройке правил для динамических групп Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="8d7da-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="8d7da-116">Ниже перечислены результаты, которые вы получите после выполнения данного шага.</span><span class="sxs-lookup"><span data-stu-id="8d7da-116">The results of this step are:</span></span>

- <span data-ttu-id="8d7da-117">Набор групп Azure AD, которые можно настроить для использовании функции динамического членства.</span><span class="sxs-lookup"><span data-stu-id="8d7da-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="8d7da-118">Набор правил в каждой динамической группе.</span><span class="sxs-lookup"><span data-stu-id="8d7da-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="8d7da-120">Руководства по лаборатории тестирования: автоматизация лицензий и членства в группах</span><span class="sxs-lookup"><span data-stu-id="8d7da-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="8d7da-121">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-dyn-groups), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="8d7da-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8d7da-122">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8d7da-122">Next step</span></span>

[<span data-ttu-id="8d7da-123">Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной</span><span class="sxs-lookup"><span data-stu-id="8d7da-123">Identity exit criteria</span></span>](identity-exit-criteria.md)
