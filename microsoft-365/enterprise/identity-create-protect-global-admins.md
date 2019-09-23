---
title: Шаг 1. Создание и защита учетных записей глобальных администраторов
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
description: Учетные записи глобальных администраторов нуждаются в особой обработке, чтобы защитить их от компрометации учетных данных.
ms.openlocfilehash: a32781686cd972ca96f6bb08f31c15ede016c4cd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090812"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="76c36-103">Шаг 1. Создание и защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="76c36-103">Step 1: Create and protect your global admin accounts</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="76c36-104">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="76c36-104">Protect global administrator accounts</span></span>

<span data-ttu-id="76c36-105">\**Этот шаг обязателен и применяется к планам E3 и E5 Microsoft 365 корпоративный*</span><span class="sxs-lookup"><span data-stu-id="76c36-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="76c36-106">В данном разделе рассматривается предотвращение цифровых атак в вашей организации за счет как можно большего укрепления безопасности учетных записей администраторов.</span><span class="sxs-lookup"><span data-stu-id="76c36-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="76c36-107">Чтобы достичь этого, примите следующие меры:</span><span class="sxs-lookup"><span data-stu-id="76c36-107">To do this, you must:</span></span>

- <span data-ttu-id="76c36-108">Создавайте несколько выделенных учетных записей глобальных администраторов с [надежными паролями](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) и используйте эти учетные записи только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="76c36-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="76c36-109">Для выполнения повседневных задач администрирования назначайте конкретные роли администраторов, например администратора Exchange или администратора паролей, для других выделенных учетных записей для этих ролей или пользователей-сотрудников ИТ-подразделения, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="76c36-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="76c36-110">Кроме того, для выделенных учетных записей глобальных администраторов необходимо выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="76c36-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="76c36-111">Чтобы убедиться, что многофакторная проверка подлинности Azure для отдельных учетных записей пользователей или на основе условного доступа работает правильно и предсказуемо, проверяйте ее параметры на тестовых учетных записях пользователей. </span><span class="sxs-lookup"><span data-stu-id="76c36-111">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="76c36-112">Для работы многофакторной проверки подлинности необходимо использовать дополнительный способ проверки подлинности, например отправлять код проверки на смартфон.</span><span class="sxs-lookup"><span data-stu-id="76c36-112">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="76c36-113">Создайте и активируйте политику условного доступа для ваших учетных записей глобальных администраторов, которые требуют многофакторной проверки подлинности, и используйте наиболее надежную форму дополнительной проверки подлинности в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="76c36-113">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="76c36-114">Дополнительные сведения см. в статье [Многофакторная проверка подлинности Azure](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="76c36-114">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="76c36-115">Сведения по дополнительным средствам защиты см. в статье [Защита учетных записей глобальных администраторов Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="76c36-115">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="76c36-116">Учетные записи для экстренных ситуаций при возникновении сценариев аварийного доступа, таких как кибератаки, должны быть только облачными учетными записями.</span><span class="sxs-lookup"><span data-stu-id="76c36-116">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="76c36-117">У вас могут также иметься учетные записи глобальных администраторов (разрешенные или постоянные) не только в облаке.</span><span class="sxs-lookup"><span data-stu-id="76c36-117">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="76c36-118">Дополнительные сведения см. в статье [Управление учетными записями администраторов для аварийного доступа в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="76c36-118">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="76c36-119">Ниже перечислены результаты, которые вы получите после выполнения инструкций с данного этапа.</span><span class="sxs-lookup"><span data-stu-id="76c36-119">The results of this section are:</span></span>

- <span data-ttu-id="76c36-120">Роль глобального администратора имеют только новые специальные учетные записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="76c36-120">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="76c36-121">Проверьте это с помощью указанной ниже команды Azure Active Directory PowerShell для Graph:</span><span class="sxs-lookup"><span data-stu-id="76c36-121">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="76c36-122">Всем остальным учетным записям пользователей, которые управляют вашей подпиской, назначены роли администраторов, соответствующие должностным обязанностям этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="76c36-122">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="76c36-123">Инструкции по установке модуля Azure Active Directory PowerShell для Graph и входу в него см. в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="76c36-123">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="76c36-125">Сведения о том, как можно испытать эту конфигурацию в среде лаборатории тестирования см. в статье [Защита учетных записей глобальных администраторов: руководство по лаборатории тестирования](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="76c36-125">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="76c36-126">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-global-admin).</span><span class="sxs-lookup"><span data-stu-id="76c36-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="76c36-127">Настройка администраторов по требованию</span><span class="sxs-lookup"><span data-stu-id="76c36-127">Set up on-demand global administrators</span></span>

<span data-ttu-id="76c36-128">*Это необязательная процедура, применимая только к версии Microsoft 365 корпоративный E5*</span><span class="sxs-lookup"><span data-stu-id="76c36-128">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="76c36-129">В этом разделе рассматривается настройка Azure AD Privileged Identity Management (PIM) для сокращения времени уязвимости учетных записей ваших администраторов к атакам злоумышленников.</span><span class="sxs-lookup"><span data-stu-id="76c36-129">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="76c36-130">PIM обеспечивает своевременное присвоение роли администратора, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="76c36-130">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="76c36-131">Ваши учетные записи администраторов становятся разрешенными, а не постоянными администраторами.</span><span class="sxs-lookup"><span data-stu-id="76c36-131">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="76c36-132">Роль администратора будет неактивной до тех пор, пока она не понадобится.</span><span class="sxs-lookup"><span data-stu-id="76c36-132">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="76c36-133">После этого вы сможете выполнить процесс активации, чтобы добавить роль администратора в учетную запись администратора в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="76c36-133">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="76c36-134">По истечении этого времени PIM удаляет роль администратора из учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="76c36-134">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="76c36-135">PIM доступна в службе Azure Active Directory Premium P2, которая входит в состав Microsoft 365 корпоративный E5.</span><span class="sxs-lookup"><span data-stu-id="76c36-135">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span> <span data-ttu-id="76c36-136">Кроме того, вы можете приобрести отдельные лицензии Azure Active Directory Premium P2 для ваших учетных записей администраторов.</span><span class="sxs-lookup"><span data-stu-id="76c36-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="76c36-137">Чтобы включить Azure PIM для вашего клиента Azure AD и учетных записей администраторов, см. [указания по настройке PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="76c36-137">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="76c36-138">Чтобы разработать комплексный стратегический план защиты привилегированного доступа от кибератак, см. статью [Защита привилегированного доступа для гибридных и облачных развертываний в Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="76c36-138">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="76c36-139">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-pim).</span><span class="sxs-lookup"><span data-stu-id="76c36-139">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="76c36-140">Управление привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="76c36-140">Privileged access management</span></span>

<span data-ttu-id="76c36-p109">Управление привилегированным доступом включается посредством настройки политик, определяющих своевременный доступ для действий на основе задач в вашем клиенте Office 365. Вашей организации может понадобиться защита от нарушений с использованием существующих привилегированных учетных записей администратора с постоянным доступом к конфиденциальным данным или доступом к критическим параметрам конфигурации. Например, можно настроить политику управления привилегированным доступом так, чтобы требовалось явное утверждение для доступа к параметрам почтового ящика организации и их изменения в клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="76c36-p109">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="76c36-p110">На этом этапе вы включаете управление привилегированным доступом в вашем клиенте Office 365 и настраиваете политики привилегированного доступа, которые обеспечивают дополнительную защиту для доступа на основе задач к данным Office 365 и параметрам конфигурации для вашей организации. Существует три основных этапа настройки управления привилегированным доступом в организации Office 365:</span><span class="sxs-lookup"><span data-stu-id="76c36-p110">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="76c36-146">создание группы утверждающего;</span><span class="sxs-lookup"><span data-stu-id="76c36-146">Creating an approver's group</span></span>
- <span data-ttu-id="76c36-147">включение привилегированного доступа;</span><span class="sxs-lookup"><span data-stu-id="76c36-147">Enabling privileged access</span></span>
- <span data-ttu-id="76c36-148">создание политик утверждения.</span><span class="sxs-lookup"><span data-stu-id="76c36-148">Creating approval policies</span></span>

<span data-ttu-id="76c36-p111">Настройка управления привилегированным доступом позволит вашей организации работать без постоянного привилегированного доступа и обеспечить уровень защиты от уязвимостей, связанных с таким постоянным административным доступом. Привилегированный доступ требует утверждения выполнения любой задачи, для которой установлена соответствующая политика утверждения. Пользователи, которым необходимо выполнить задачи, регулируемые политикой утверждения, должны запросить и получить утверждение доступа, чтобы иметь разрешения, необходимые для выполнения определенных в политике задач.</span><span class="sxs-lookup"><span data-stu-id="76c36-p111">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="76c36-152">Чтобы включить управление привилегированным доступом в Office 365, см. статью [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="76c36-152">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="76c36-153">Дополнительные сведения см. в статье [Управление привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="76c36-153">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="76c36-155">Сведения о том, как можно испытать эту конфигурацию в среде лаборатории тестирования см. в статье [Управление привилегированным доступом: руководство по лаборатории тестирования](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="76c36-155">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="76c36-156">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-pam), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="76c36-156">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="76c36-157">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="76c36-157">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="76c36-158">Защита паролей</span><span class="sxs-lookup"><span data-stu-id="76c36-158">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

