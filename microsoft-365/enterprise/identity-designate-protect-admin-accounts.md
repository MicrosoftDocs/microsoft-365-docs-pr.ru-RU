---
title: Шаг 2. Защита привилегированных удостоверений
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается об учетных записях администраторов и о том, как настроить их, чтобы обеспечить максимальную защиту.
ms.openlocfilehash: b9c645d597dfeb2bdc42e2b0b7615252dc1f5ecb
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981910"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="e20f9-103">Шаг 2. Защита привилегированных удостоверений</span><span class="sxs-lookup"><span data-stu-id="e20f9-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="e20f9-104">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="e20f9-104">Protect global administrator accounts</span></span>

<span data-ttu-id="e20f9-105">\**Этот шаг обязателен и применяется к планам E3 и E5 Microsoft 365 корпоративный*</span><span class="sxs-lookup"><span data-stu-id="e20f9-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="e20f9-106">В данном разделе рассматривается предотвращение цифровых атак в вашей организации за счет как можно большего укрепления безопасности учетных записей администраторов.</span><span class="sxs-lookup"><span data-stu-id="e20f9-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="e20f9-107">Чтобы достичь этого, примите следующие меры:</span><span class="sxs-lookup"><span data-stu-id="e20f9-107">To do this, you must:</span></span>

- <span data-ttu-id="e20f9-108">Создавайте выделенные учетные записи глобальных администраторов с очень [надежными паролями](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) и используйте эти учетные записи только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="e20f9-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="e20f9-109">Для выполнения повседневных задач администрирования назначайте конкретные роли администраторов, например администратора Exchange или администратора паролей, учетным записям пользователей-сотрудников ИТ-подразделения.</span><span class="sxs-lookup"><span data-stu-id="e20f9-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="e20f9-110">Кроме того, для выделенных учетных записей глобальных администраторов необходимо выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e20f9-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="e20f9-p102">Чтобы убедиться, что многофакторная проверка подлинности для отдельных учетных записей пользователей или на основе условного доступа работает правильно и предсказуемо, проверяйте ее параметры на тестовых учетных записях пользователей. Для работы многофакторной проверки подлинности необходимо использовать дополнительный способ проверки подлинности, например отправлять код проверки на смартфон.</span><span class="sxs-lookup"><span data-stu-id="e20f9-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="e20f9-113">Включите политику условного доступа **Базовая политика: требовать многофакторную проверку подлинности для администраторов** для ваших учетных записей глобальных администраторов и используйте наиболее надежную форму дополнительной проверки подлинности в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e20f9-113">Enable the **Baseline policy: Require MFA for admins** conditional access policy for your global administrator accounts and use the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="e20f9-114">Дополнительные сведения см. в статье [Многофакторная проверка подлинности](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="e20f9-114">See [Multi-factor authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="e20f9-115">Сведения по дополнительным средствам защиты см. в статье [Защита учетных записей глобальных администраторов Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="e20f9-115">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="e20f9-p104">Организациям следует использовать только облачные удостоверения для создания привилегированных учетных записей (таких как учетная запись глобального администратора) для экстренных ситуаций, например кибератак. Дополнительные сведения см. в статье [Управление административными учетными записями для экстренных ситуаций в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="e20f9-p104">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="e20f9-118">Ниже перечислены результаты, которые вы получите после выполнения инструкций с данного этапа.</span><span class="sxs-lookup"><span data-stu-id="e20f9-118">The results of this section are:</span></span>

- <span data-ttu-id="e20f9-119">Роль глобального администратора имеют только новые специальные учетные записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e20f9-119">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="e20f9-120">Проверьте это с помощью указанной ниже команды Azure Active Directory PowerShell для Graph:</span><span class="sxs-lookup"><span data-stu-id="e20f9-120">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="e20f9-121">Всем остальным учетным записям пользователей, которые управляют вашей подпиской, назначены роли администраторов, соответствующие должностным обязанностям этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="e20f9-121">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="e20f9-122">Инструкции по установке модуля Azure Active Directory PowerShell для Graph и входу в него см. в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="e20f9-122">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="e20f9-124">Сведения о том, как можно испытать эту конфигурацию в среде лаборатории тестирования см. в статье [Защита учетных записей глобальных администраторов: руководство по лаборатории тестирования](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e20f9-124">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="e20f9-125">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-global-admin).</span><span class="sxs-lookup"><span data-stu-id="e20f9-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="e20f9-126">Настройка глобальных администраторов по требованию</span><span class="sxs-lookup"><span data-stu-id="e20f9-126">Set up on-demand global administrators</span></span>

<span data-ttu-id="e20f9-127">*Этот шаг обязателен и применяется только к плану Microsoft 365 корпоративный E5*</span><span class="sxs-lookup"><span data-stu-id="e20f9-127">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="e20f9-128">В этом разделе рассматривается настройка Azure AD Privileged Identity Management (PIM) для сокращения времени уязвимости учетных записей ваших глобальных администраторов к атакам злоумышленников.</span><span class="sxs-lookup"><span data-stu-id="e20f9-128">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="e20f9-129">PIM обеспечивает своевременное присвоение роли глобального администратора, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="e20f9-129">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="e20f9-p107">Вместо присвоения вашим учетным записям глобального администратора статуса администратора на бессрочной основе, им присваивается статус администратора, наделенного соответствующими полномочиями. Роль глобального администратора будет неактивной, пока она кому-либо не потребуется. Затем необходимо выполнить процесс активации, чтобы добавить роль глобального администратора в учетную запись глобального администратора на определенный период времени. По истечении такого периода PIM удаляет роль глобального администратора из учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e20f9-p107">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="e20f9-p108">Функция Privileged Identity Management доступна с лицензией на Azure Active Directory Premium P2, которая входит в план Microsoft 365 корпоративный E5. Кроме того, вы можете приобрести отдельные лицензии на Azure Active Directory Premium P2 для ваших учетных записей глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e20f9-p108">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="e20f9-136">Чтобы включить Azure PIM для вашего клиента Azure AD и учетных записей глобального администратора, см. [указания по настройке PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="e20f9-136">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="e20f9-137">Чтобы разработать комплексный стратегический план защиты привилегированного доступа от кибератак, см. статью [Защита привилегированного доступа для гибридных и облачных развертываний в Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="e20f9-137">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="e20f9-138">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-pim), при выполнении которых можно считать данный раздел завершенным.</span><span class="sxs-lookup"><span data-stu-id="e20f9-138">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="e20f9-139">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="e20f9-139">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="e20f9-140">Настройка гибридного удостоверения</span><span class="sxs-lookup"><span data-stu-id="e20f9-140">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

