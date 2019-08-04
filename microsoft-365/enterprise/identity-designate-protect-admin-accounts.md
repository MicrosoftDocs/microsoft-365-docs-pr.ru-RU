---
title: Шаг 2. Защита привилегированных удостоверений
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается об учетных записях администраторов и о том, как настроить их, чтобы обеспечить максимальную защиту.
ms.openlocfilehash: 8a1d232ffc0242766d79b2e4884582f3b5524d22
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074059"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="3849b-103">Шаг 2. Защита привилегированных удостоверений</span><span class="sxs-lookup"><span data-stu-id="3849b-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="3849b-104">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="3849b-104">Protect global administrator accounts</span></span>

<span data-ttu-id="3849b-105">\**Этот шаг обязателен и применяется к планам E3 и E5 Microsoft 365 корпоративный*</span><span class="sxs-lookup"><span data-stu-id="3849b-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3849b-106">В данном разделе рассматривается предотвращение цифровых атак в вашей организации за счет как можно большего укрепления безопасности учетных записей администраторов.</span><span class="sxs-lookup"><span data-stu-id="3849b-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="3849b-107">Чтобы достичь этого, примите следующие меры:</span><span class="sxs-lookup"><span data-stu-id="3849b-107">To do this, you must:</span></span>

- <span data-ttu-id="3849b-108">Создавайте выделенные учетные записи глобальных администраторов с очень [надежными паролями](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) и используйте эти учетные записи только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="3849b-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="3849b-109">Для выполнения повседневных задач администрирования назначайте конкретные роли администраторов, например администратора Exchange или администратора паролей, учетным записям пользователей-сотрудников ИТ-подразделения.</span><span class="sxs-lookup"><span data-stu-id="3849b-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="3849b-110">Кроме того, для выделенных учетных записей глобальных администраторов необходимо выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3849b-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="3849b-p102">Чтобы убедиться, что многофакторная проверка подлинности для отдельных учетных записей пользователей или на основе условного доступа работает правильно и предсказуемо, проверяйте ее параметры на тестовых учетных записях пользователей. Для работы многофакторной проверки подлинности необходимо использовать дополнительный способ проверки подлинности, например отправлять код проверки на смартфон.</span><span class="sxs-lookup"><span data-stu-id="3849b-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="3849b-p103">Настраивайте многофакторную проверку подлинности для каждой выделенной учетной записи глобального администратора Office 365 и используйте самый надежный способ дополнительной проверки подлинности, доступный в вашей организации. Дополнительные сведения см. в статье, посвященной [многофакторной проверке подлинности](identity-multi-factor-authentication.md#identity-mfa).</span><span class="sxs-lookup"><span data-stu-id="3849b-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) for more information.</span></span>
2. <span data-ttu-id="3849b-p104">Используйте политику условного доступа, чтобы запрашивать многофакторную проверку подлинности для учетных записей глобальных администраторов. Дополнительные сведения см. в статье [Защита учетных записей администраторов](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="3849b-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="3849b-117">Дополнительные сведения о настройке см. в статье [Защита учетных записей глобальных администраторов Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="3849b-117">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="3849b-p105">Организациям следует использовать только облачные удостоверения для создания привилегированных учетных записей (таких как учетная запись глобального администратора) для экстренных ситуаций, например кибератак. Дополнительные сведения см. в статье [Управление административными учетными записями для экстренных ситуаций в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="3849b-p105">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="3849b-120">Результаты данного раздела:</span><span class="sxs-lookup"><span data-stu-id="3849b-120">The results of this section are:</span></span>

- <span data-ttu-id="3849b-121">Роль глобального администратора имеют только новые специальные учетные записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="3849b-121">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="3849b-122">Проверьте это с помощью указанной ниже команды Azure Active Directory PowerShell для Graph:</span><span class="sxs-lookup"><span data-stu-id="3849b-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="3849b-123">Всем остальным повседневным учетным записям пользователей, которые управляют вашей подпиской, назначены роли администраторов, соответствующие должностным обязанностям этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="3849b-123">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="3849b-124">Инструкции по установке модуля Azure Active Directory PowerShell для Graph и входу в него см. в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="3849b-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3849b-126">Руководство по лаборатории тестирования: защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="3849b-126">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="3849b-127">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-global-admin), при выполнении которых можно считать данный раздел завершенным.</span><span class="sxs-lookup"><span data-stu-id="3849b-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="3849b-128">Настройка глобальных администраторов по требованию</span><span class="sxs-lookup"><span data-stu-id="3849b-128">Set up on-demand global administrators</span></span>

<span data-ttu-id="3849b-129">*Этот шаг обязателен и применяется только к плану Microsoft 365 корпоративный E5*</span><span class="sxs-lookup"><span data-stu-id="3849b-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3849b-130">В этом разделе рассматривается настройка Azure AD Privileged Identity Management (PIM) для сокращения времени уязвимости учетных записей ваших глобальных администраторов к атакам злоумышленников.</span><span class="sxs-lookup"><span data-stu-id="3849b-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="3849b-131">PIM обеспечивает своевременное присвоение роли глобального администратора, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="3849b-131">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="3849b-p108">Вместо присвоения вашим учетным записям глобального администратора статуса администратора на бессрочной основе, им присваивается статус администратора, наделенного соответствующими полномочиями. Роль глобального администратора будет неактивной, пока она кому-либо не потребуется. Затем необходимо выполнить процесс активации, чтобы добавить роль глобального администратора в учетную запись глобального администратора на определенный период времени. По истечении такого периода PIM удаляет роль глобального администратора из учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="3849b-p108">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="3849b-p109">Функция Privileged Identity Management доступна с лицензией на Azure Active Directory Premium P2, которая входит в план Microsoft 365 корпоративный E5. Кроме того, вы можете приобрести отдельные лицензии на Azure Active Directory Premium P2 для ваших учетных записей глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="3849b-p109">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="3849b-138">Чтобы включить Azure PIM для вашего клиента Azure AD и учетных записей глобального администратора, см. [указания по настройке PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="3849b-138">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="3849b-139">Чтобы разработать комплексный стратегический план защиты привилегированного доступа от кибератак, см. статью [Защита привилегированного доступа для гибридных и облачных развертываний в Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="3849b-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="3849b-140">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-pim), при выполнении которых можно считать данный раздел завершенным.</span><span class="sxs-lookup"><span data-stu-id="3849b-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="3849b-141">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="3849b-141">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="3849b-142">Настройка гибридного удостоверения</span><span class="sxs-lookup"><span data-stu-id="3849b-142">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

