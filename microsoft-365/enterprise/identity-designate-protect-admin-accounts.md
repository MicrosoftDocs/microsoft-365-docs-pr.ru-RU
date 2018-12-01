---
title: Шаг 2. Защита учетных записей глобальных администраторов
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
description: В этой статье рассказывается об учетных записях администраторов и о том, как настроить их, чтобы обеспечить максимальную защиту.
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871076"
---
# <a name="step-2-protect-global-administrator-accounts"></a><span data-ttu-id="21cb1-103">Шаг 2. Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="21cb1-103">Step 2: Protect global administrator accounts</span></span>

<span data-ttu-id="21cb1-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="21cb1-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="21cb1-p101">На этом шаге вы предпримете меры для предотвращения цифровых атак на вашу организацию, максимально надежно защитив свои учетные записи администраторов. Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="21cb1-p101">In Step 5, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span>

- <span data-ttu-id="21cb1-107">Создавайте выделенные учетные записи глобальных администраторов с очень [надежными паролями](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) и используйте эти учетные записи только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="21cb1-107">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="21cb1-108">Для выполнения повседневных задач администрирования назначайте конкретные роли администраторов, например администратора Exchange или администратора паролей, учетным записям пользователей-сотрудников ИТ-подразделения.</span><span class="sxs-lookup"><span data-stu-id="21cb1-108">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="21cb1-109">Кроме того, для выделенных учетных записей глобальных администраторов необходимо выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="21cb1-109">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="21cb1-p102">Чтобы убедиться, что многофакторная проверка подлинности для отдельных учетных записей пользователей или на основе условного доступа работает правильно и предсказуемо, проверяйте ее параметры на тестовых учетных записях пользователей. Для работы многофакторной проверки подлинности необходимо использовать дополнительный способ проверки подлинности, например отправлять код проверки на смартфон.</span><span class="sxs-lookup"><span data-stu-id="21cb1-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="21cb1-p103">Настраивайте многофакторную проверку подлинности для каждой выделенной учетной записи глобального администратора Office 365 и используйте самый надежный способ дополнительной проверки подлинности, доступный в вашей организации. Дополнительные сведения см. в статье, посвященной [многофакторной проверке подлинности](identity-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="21cb1-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md) for more information.</span></span>
2. <span data-ttu-id="21cb1-p104">Используйте политику условного доступа, чтобы запрашивать многофакторную проверку подлинности для учетных записей глобальных администраторов. Дополнительные сведения см. в статье [Защита учетных записей администраторов](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="21cb1-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="21cb1-p105">Используйте политику Office 365 Cloud App Security, чтобы отслеживать активность учетной записи глобального администратора. Дополнительные сведения см. в статье [Настройка повышенной безопасности для Office 365](infoprotect-configure-increased-security-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="21cb1-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Information protection for Microsoft 365 Enterprise](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="21cb1-118">Дополнительные сведения о настройке см. в статье [Защита учетных записей глобальных администраторов Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="21cb1-118">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="21cb1-p106">Организациям следует использовать только облачные удостоверения для создания привилегированных учетных записей (таких как учетная запись глобального администратора) для экстренных ситуаций, например кибератак. Дополнительные сведения см. в статье [Управление административными учетными записями для экстренных ситуаций в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="21cb1-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="21cb1-121">Ниже перечислены результаты, которые вы получите после выполнения данного шага.</span><span class="sxs-lookup"><span data-stu-id="21cb1-121">The results of this step are:</span></span>

- <span data-ttu-id="21cb1-p107">В вашей подписке роль глобального администратора имеется только у вновь настроенных или выделенных учетных записей администраторов. Чтобы проверить, так ли это, выполните следующую команду Windows Azure AD V2 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21cb1-p107">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="21cb1-124">Всем остальным повседневным учетным записям пользователей, которые управляют вашей подпиской, назначены роли администраторов, соответствующие должностным обязанностям этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="21cb1-124">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="21cb1-125">Инструкции по установке модуля Azure AD V2 PowerShell и входу в систему см. в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="21cb1-125">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="21cb1-127">Руководство по лаборатории тестирования: защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="21cb1-127">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="21cb1-128">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-global-admin), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="21cb1-128">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="21cb1-129">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="21cb1-129">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="21cb1-130">Настройка глобальных администраторов по требованию</span><span class="sxs-lookup"><span data-stu-id="21cb1-130">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |

