---
title: Шаг 14. Разрешение пользователям создавать собственные группы и управлять ими
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
description: В этом разделе рассказывается, как настроить самостоятельное управление группами Azure AD.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870768"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="11044-103">Шаг 14. Разрешение пользователям создавать собственные группы и управлять ими</span><span class="sxs-lookup"><span data-stu-id="11044-103">Step 14: Allow users to create and manage their own groups</span></span>

<span data-ttu-id="11044-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="11044-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="11044-p101">На этом шаге вы определите группы Azure Active Directory (AD), которыми могут управлять владельцы этих групп (вместо ИТ-администраторов). Эта функция, называемая *самостоятельное управление группами*, позволяет владельцам групп, которым не назначена административная роль, создавать группы безопасности и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="11044-p101">In Step 14, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="11044-p102">Пользователи могут запрашивать членство в группе безопасности, и такие запросы будут поступать владельцу группы, а не ИТ-администратору. Это позволяет делегировать повседневный контроль членства в группе владельцам группы, проекта или организации, которые понимают бизнес-цель группы и могут управлять членством в ней.</span><span class="sxs-lookup"><span data-stu-id="11044-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="11044-p103">Функция самостоятельного управления группами доступна только для защиты Azure AD и групп Office 365. Она недоступна для групп, поддерживающих почту, списков рассылки и всех групп, которые были синхронизированы из вашего локального Windows Server Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="11044-p103">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="11044-111">Дополнительные сведения см. в статье с [инструкциями по настройке групп Azure AD для самостоятельного управления группами](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="11044-111">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="11044-112">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-self-service-groups), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="11044-112">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="11044-113">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="11044-113">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="11044-114">Настройка динамического членства в группах</span><span class="sxs-lookup"><span data-stu-id="11044-114">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |
