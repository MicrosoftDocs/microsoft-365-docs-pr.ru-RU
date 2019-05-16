---
title: Шаг 2. Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Убедитесь, что используемая вами конфигурация соответствует условиям Microsoft 365 корпоративный для служб и инфраструктуры, основанных на удостоверениях.
ms.openlocfilehash: aabd9f5db223b4b1aba0173dcfb739fe27553555
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072129"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="d394d-103">Шаг 2. Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной</span><span class="sxs-lookup"><span data-stu-id="d394d-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="d394d-104">Убедитесь, что инфраструктура удостоверений соответствует указанным ниже обязательным условиям и что рассмотрены необязательные условия.</span><span class="sxs-lookup"><span data-stu-id="d394d-104">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="d394d-105">Дополнительные рекомендации по инфраструктуре удостоверений см. в разделе [Предварительные требования](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="d394d-105">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-all-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="d394d-106">Обязательное требование: созданы все необходимые пользователи, группы и членства в группах</span><span class="sxs-lookup"><span data-stu-id="d394d-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="d394d-107">Вы создали учетные записи пользователей и группы для указанных ниже целей.</span><span class="sxs-lookup"><span data-stu-id="d394d-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="d394d-108">У сотрудников вашей организации, а также у поставщиков, подрядчиков и партнеров, которые работают на вашу организацию или с ней, имеются соответствующие учетные записи пользователей в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d394d-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (Azure AD).</span></span>
- <span data-ttu-id="d394d-109">Группы Azure AD и их участники содержат учетные записи пользователей и другие группы для различных целей, например для подготовки параметров безопасности для облачных служб (Майкрософт), автоматического лицензирования и других целей.</span><span class="sxs-lookup"><span data-stu-id="d394d-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="d394d-110">Чтобы выполнить это требование, см. [шаг 1](identity-plan-users-groups.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="d394d-111">Обязательное требование: ваши учетные записи глобальных администраторов защищены</span><span class="sxs-lookup"><span data-stu-id="d394d-111">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="d394d-112">Вы [защитили свои учетные записи глобальных администраторов Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts), чтобы не допустить компрометации учетных данных, которая может привести к нарушению защиты подписки на Office 365.</span><span class="sxs-lookup"><span data-stu-id="d394d-112">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to avoid compromising credentials that can lead to breaches of an Office 365 subscription.</span></span>

<span data-ttu-id="d394d-113">Если вы не выполните это требование, ваши учетные записи глобальных администраторов могут быть уязвимыми для атак и компрометации. В этом случае злоумышленники получат полный доступ к вашим системе и данным: они смогут использовать или уничтожить ваши данные либо потребовать за них выкуп.</span><span class="sxs-lookup"><span data-stu-id="d394d-113">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="d394d-114">Чтобы выполнить это требование, см. [шаг 2](identity-designate-protect-admin-accounts.md#identity-global-admin) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-114">If needed, [Step 2](identity-designate-protect-admin-accounts.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="d394d-115">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-115">How to test</span></span>

<span data-ttu-id="d394d-116">Чтобы убедиться, что ваши учетные записи глобальных администраторов защищены, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d394d-116">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="d394d-p101">Выполните указанную ниже команду Azure AD V2 в командной строке PowerShell. Должен отобразиться только список выделенных учетных записей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="d394d-p101">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="d394d-p102">Войдите в систему в Office 365 с помощью каждой из учетных записей, указанных в шаге 1. При каждом входе система должна требовать выполнить многофакторную проверку подлинности с использованием максимально надежного способа дополнительной проверки подлинности, доступного в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d394d-p102">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="d394d-121">Инструкции по установке модуля Azure Active Directory PowerShell для Graph и входу в Office 365 см. в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d394d-121">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="d394d-122">Необязательное требование: вы настроили управление привилегированными пользователями для поддержки назначений роли глобального администратора по требованию</span><span class="sxs-lookup"><span data-stu-id="d394d-122">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="d394d-123">С помощью сведений в статье [Что такое Azure AD Privileged Identity Management?](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) вы включили функцию управления привилегированными пользователями в своем клиенте Azure AD и настроили учетные данные глобальных администраторов в качестве администраторов, наделенных соответствующими полномочиями.</span><span class="sxs-lookup"><span data-stu-id="d394d-123">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="d394d-124">Кроме того, следуя рекомендациям в статье [Защита привилегированного доступа для гибридных и облачных развертываний в Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices), вы разработали стратегический план защиты привилегированного доступа от кибератак.</span><span class="sxs-lookup"><span data-stu-id="d394d-124">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="d394d-125">Если вы не выполните это требование, ваши учетные записи глобальных администраторов будут подвергаться постоянным атакам и в случае их компрометации злоумышленники смогут копировать или уничтожать ваши конфиденциальные данные либо требовать выкуп за них.</span><span class="sxs-lookup"><span data-stu-id="d394d-125">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="d394d-126">Чтобы выполнить это требование, см. [шаг 2](identity-designate-protect-admin-accounts.md#identity-pim) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-126">If needed, [Step 2](identity-designate-protect-admin-accounts.md#identity-pim) can help you with this option.</span></span>


<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="d394d-127">Обязательное требование: пользователи и группы синхронизированы с Azure AD</span><span class="sxs-lookup"><span data-stu-id="d394d-127">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="d394d-128">Если у вас есть локальный поставщик удостоверений, например доменные службы Active Directory (AD DS), вы уже использовали Azure AD Connect для синхронизации учетных записей пользователей и групп из вашего локального поставщика удостоверений в клиент Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d394d-128">If you have an existing on-premises identity provider, such as Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="d394d-129">Благодаря службе синхронизации каталогов ваши пользователи могут входить в систему в Office 365 и в других облачных службах Майкрософт, используя те же учетные данные, которые они используют для входа в систему на своих компьютерах и для доступа к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="d394d-129">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="d394d-130">Чтобы выполнить это требование, см. [шаг 3](identity-azure-ad-connect.md#identity-sync) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-130">If needed, [Step 3](identity-azure-ad-connect.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="d394d-131">Если вы не выполните это требование, у вас будут два указанных ниже набора учетных записей пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="d394d-131">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="d394d-132">Учетные записи пользователей и группы в локальном поставщике удостоверений.</span><span class="sxs-lookup"><span data-stu-id="d394d-132">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="d394d-133">Учетные записи пользователей и группы в клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d394d-133">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="d394d-p103">В этом случае ИТ-администраторам и пользователям придется вручную обслуживать оба набора. Это неизбежно приведет к появлению несинхронизированных учетных записей, паролей и групп.</span><span class="sxs-lookup"><span data-stu-id="d394d-p103">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="d394d-136">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-136">How to test</span></span>
<span data-ttu-id="d394d-137">Чтобы проверить, правильно ли работает проверка подлинности с использованием локальных учетных данных, войдите в систему на портале Office с помощью своих локальных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d394d-137">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="d394d-138">Чтобы убедиться, что синхронизация каталогов работает правильно, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d394d-138">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="d394d-139">Создайте тестовую группу в AD DS.</span><span class="sxs-lookup"><span data-stu-id="d394d-139">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="d394d-140">Подождите, пока будет выполнена синхронизация.</span><span class="sxs-lookup"><span data-stu-id="d394d-140">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="d394d-141">Проверьте, появилось ли название новой тестовой группы в клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d394d-141">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="d394d-142">Необязательное требование: отслеживается синхронизация каталогов</span><span class="sxs-lookup"><span data-stu-id="d394d-142">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="d394d-143">С помощью сведений в статье [Мониторинг синхронизации Azure AD Connect с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (для синхронизации паролей) или в статье [Мониторинг AD FS с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (для федеративной проверки подлинности) вы развернули Azure AD Connect Health, выполнив при этом указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d394d-143">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="d394d-144">Установка агента Azure AD Connect Health на каждый из ваших локальных серверов удостоверений.</span><span class="sxs-lookup"><span data-stu-id="d394d-144">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="d394d-145">Отслеживание текущей синхронизации на портале Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="d394d-145">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="d394d-146">Если вы не выполните это требование, то сможете более точно оценивать состояние своей облачной инфраструктуры идентификации.</span><span class="sxs-lookup"><span data-stu-id="d394d-146">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="d394d-147">Чтобы выполнить это требование, см. [шаг 3](identity-azure-ad-connect.md#identity-sync-health) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-147">If needed, [Step 3](identity-azure-ad-connect.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="d394d-148">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-148">How to test</span></span>
<span data-ttu-id="d394d-149">На портале Azure AD Connect Health можно получить сведения о текущем и правильном состоянии ваших локальных серверов удостоверений и текущей синхронизации.</span><span class="sxs-lookup"><span data-stu-id="d394d-149">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="d394d-150">Необязательное требование: многофакторная проверка подлинности включена для ваших пользователей</span><span class="sxs-lookup"><span data-stu-id="d394d-150">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="d394d-151">Чтобы включить многофакторную проверку подлинности для своих пользователей, вы [выполнили планирование многофакторной проверки подлинности для развертываний Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/multi-factor-authentication-plan) и [настроили многофакторную проверку подлинности для пользователей Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="d394d-151">You used [Plan for multi-factor authentication for Office 365 Deployments](https://docs.microsoft.com/office365/admin/security-and-compliance/multi-factor-authentication-plan) and [Set up multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) to enable multifactor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="d394d-p104">Если вы не выполните это требование, ваши учетные записи пользователей будут уязвимы для компрометации злоумышленниками. При компрометации пароля учетной записи пользователя все ресурсы и возможности этой учетной записи, например роли администраторов, будут доступны злоумышленникам, и они смогут копировать или уничтожать данные, а также блокировать их, требуя у вас выкуп.</span><span class="sxs-lookup"><span data-stu-id="d394d-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="d394d-155">Чтобы выполнить это требование, см. [шаг 4](identity-multi-factor-authentication.md#identity-mfa) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-155">If needed, [Step 4](identity-multi-factor-authentication.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="d394d-156">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-156">How to test</span></span>

1.  <span data-ttu-id="d394d-157">Создайте тестовую учетную запись пользователя на портале администрирования Office 365 и назначьте ей лицензию.</span><span class="sxs-lookup"><span data-stu-id="d394d-157">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="d394d-158">Настройте многофакторную проверку подлинности для тестовой учетной записи с дополнительным методом проверки, который вы используете для реальных учетных записей пользователей, например отправку сообщения на телефон.</span><span class="sxs-lookup"><span data-stu-id="d394d-158">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="d394d-159">Войдите в систему в Office 365 или на портале Azure, используя тестовую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="d394d-159">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="d394d-160">Убедитесь, что при многофакторной проверке подлинности система предлагает указать дополнительные проверочные сведения и в результате успешно выполняет проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d394d-160">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="d394d-161">Удалите тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-161">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a><span data-ttu-id="d394d-162">Необязательное требование: включена функция защиты идентификации Azure AD для защиты от компрометации учетных данных</span><span class="sxs-lookup"><span data-stu-id="d394d-162">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="d394d-163">Вы включили функцию защиты идентификации Azure AD для указанных ниже целей.</span><span class="sxs-lookup"><span data-stu-id="d394d-163">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="d394d-164">Устранение потенциальных уязвимостей, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="d394d-164">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="d394d-165">Обнаружение попыток компрометации учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d394d-165">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="d394d-166">Изучение и разрешение текущих подозрительных инцидентов, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="d394d-166">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="d394d-p105">Если вы не выполните это требование, у вас не будет возможности обнаруживать или автоматически пресекать попытки компрометации учетных данных или расследовать инциденты безопасности, связанные с идентификацией. Это сделает вашу организацию уязвимой к попыткам компрометации учетных данных и подвергает конфиденциальные данные организации риску.</span><span class="sxs-lookup"><span data-stu-id="d394d-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="d394d-169">Чтобы выполнить это требование, см. [шаг 4](identity-multi-factor-authentication.md#identity-ident-prot) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-169">If needed, [Step 4](identity-multi-factor-authentication.md#identity-ident-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="d394d-170">Необязательное требование: пользователи могут сбрасывать свои пароли</span><span class="sxs-lookup"><span data-stu-id="d394d-170">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="d394d-171">С помощью сведений в статье [Быстрое развертывание самостоятельного сброса пароля в Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) вы настроили функцию сброса паролей для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="d394d-171">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="d394d-172">Если вы не выполните это условие, то чтобы сбросить пароль, пользователям придется обращаться к администраторам учетных записей пользователей, и это приведет к дополнительным издержкам на ИТ-администрирование.</span><span class="sxs-lookup"><span data-stu-id="d394d-172">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="d394d-173">Чтобы выполнить это требование, см. [шаг 5](identity-password-reset.md#identity-pw-reset) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-173">If needed, [Step 5](identity-password-reset.md#identity-pw-reset) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="d394d-174">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-174">How to test</span></span>

1. <span data-ttu-id="d394d-175">Создайте тестовую учетную запись с первоначальным паролем.</span><span class="sxs-lookup"><span data-stu-id="d394d-175">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="d394d-176">Следуя инструкциям в статье [Предоставление пользователям прав на самостоятельный сброс пароля в Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords), выполните сброс пароля для тестовой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-176">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="d394d-177">Выйдите из системы и войдите в тестовую учетную запись пользователя с помощью функции сброса пароля.</span><span class="sxs-lookup"><span data-stu-id="d394d-177">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="d394d-178">Удалите тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-178">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="d394d-179">Необязательное требование: включена функция обратной записи пароля для ваших пользователей</span><span class="sxs-lookup"><span data-stu-id="d394d-179">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="d394d-180">Выполнив инструкции в статье [Быстрое развертывание самостоятельного сброса пароля в Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started), вы включили функцию обратной записи пароля для клиента Azure AD в своей подписке Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="d394d-180">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="d394d-181">Если пропустить этот параметр, то пользователи, не подключенные к локальной сети, должны будут сбросить или разблокировать свои пароли AD DS через ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="d394d-181">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="d394d-182">Чтобы выполнить это требование, см. [шаг 5](identity-password-reset.md#identity-pw-writeback) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-182">If needed, [Step 5](identity-password-reset.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="d394d-183">Функция обратной записи пароля необходима, чтобы в полной мере использовать возможности защиты идентификации Azure AD, например чтобы требовать от пользователей изменять свои локальные пароли, если Azure AD обнаружила высокий риск компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d394d-183">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="d394d-184">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-184">How to test</span></span>

<span data-ttu-id="d394d-185">Протестируйте функцию обратной записи пароля, изменив свой пароль в Office 365.</span><span class="sxs-lookup"><span data-stu-id="d394d-185">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="d394d-186">У вас должно получиться использовать свою учетную запись и новый пароль для доступа к локальным ресурсам AD DS.</span><span class="sxs-lookup"><span data-stu-id="d394d-186">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="d394d-187">Создайте тестовую учетную запись в локальных службах AD DS, разрешите синхронизацию каталогов, а затем предоставьте этой учетной записи лицензию на Office 365 в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d394d-187">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it an Office 365 license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="d394d-188">Используя учетные данные тестовой учетной записи, войдите в систему на удаленном компьютере, присоединенном к вашему локальному домену AD DS, а также на портал Office.</span><span class="sxs-lookup"><span data-stu-id="d394d-188">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="d394d-189">Щелкните **Параметры > Параметры Office 365 > Пароль > Изменить пароль**.</span><span class="sxs-lookup"><span data-stu-id="d394d-189">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="d394d-190">Введите текущий пароль, введите новый пароль, а затем подтвердите новый пароль.</span><span class="sxs-lookup"><span data-stu-id="d394d-190">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="d394d-191">Выйдите из системы на портале Office и на удаленном компьютере, а затем войдите в систему на компьютере, используя тестовую учетную запись и новый пароль для нее.</span><span class="sxs-lookup"><span data-stu-id="d394d-191">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="d394d-192">Это подтвердит, что вы можете изменить пароль учетной записи в локальных службах AD DS с помощью клиента Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d394d-192">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="d394d-193">Необязательное требование: пользователи могут входить в систему с помощью простого единого входа Azure AD</span><span class="sxs-lookup"><span data-stu-id="d394d-193">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="d394d-194">С помощью сведений в статье [Azure AD Connect: простой единый вход](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) вы включили функцию единого входа для своей организации. Это упростило вход в облачные приложения, например в Office 365, для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d394d-194">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="d394d-195">Если вы не выполните это требование, то система, возможно, будет предлагать вашим пользователям вводить учетные данные при доступе к традиционным приложениям, использующим Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d394d-195">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="d394d-196">Чтобы выполнить это требование, см. [шаг 5](identity-password-reset.md#identity-sso) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-196">If needed, [Step 5](identity-password-reset.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="d394d-197">Необязательное требование: экран входа в Office 365 персонализирован для вашей организации</span><span class="sxs-lookup"><span data-stu-id="d394d-197">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="d394d-198">Вы добавили фирменную символику своей организации на страницу входа Office 365 с помощью функции [добавления фирменной символики своей компании на страницы входа и панели доступа](http://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="d394d-198">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="d394d-199">Если вы не выполните это требование, для ваших пользователей будет отображаться стандартный экран входа в Office 365, и они, возможно, не будут точно знать, что выполняют вход на сайт вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d394d-199">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="d394d-200">Чтобы выполнить это требование, см. [шаг 5](identity-password-reset.md#identity-custom-sign-in) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-200">If needed, [Step 5](identity-password-reset.md#identity-custom-sign-in) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="d394d-201">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-201">How to test</span></span>

<span data-ttu-id="d394d-p108">Войдите в систему на портале Office 365, используя имя вашей учетной записи и пройдя многофакторную проверку подлинности. На странице входа в систему должны отображаться элементы фирменной символики вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d394d-p108">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="d394d-204">Необязательное требование: включено самостоятельное управление группами для определенных групп безопасности Azure AD и групп Office 365</span><span class="sxs-lookup"><span data-stu-id="d394d-204">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="d394d-205">Вы определили группы, подходящие для самостоятельного управления, рассказали их владельцам о рабочем процессе управления группами и об их ответственности, а также [настроили функцию самостоятельного управления в Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) для таких групп.</span><span class="sxs-lookup"><span data-stu-id="d394d-205">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="d394d-206">Если вы не выполните это требование, все задачи по управлению группами Azure AD придется выполнять ИТ-администраторам.</span><span class="sxs-lookup"><span data-stu-id="d394d-206">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="d394d-207">Чтобы выполнить это требование, см. [шаг 6](identity-self-service-group-management.md#identity-self-service-groups) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-207">If needed, [Step 6](identity-self-service-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="d394d-208">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-208">How to test</span></span>
1.  <span data-ttu-id="d394d-209">На портале Azure создайте тестовую учетную запись пользователя в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d394d-209">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="d394d-210">Войдите в систему с помощью тестовой учетной записи пользователя и создайте тестовую группу безопасности Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d394d-210">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="d394d-211">Выйдите из системы, а затем снова войдите в нее с помощью своей учетной записи ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="d394d-211">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="d394d-212">Настройте тестовую группу безопасности для самостоятельного управления для тестовой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-212">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="d394d-213">Выйдите из системы, а затем снова войдите в нее с помощью тестовой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-213">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="d394d-214">На портале Azure добавьте участников в тестовую группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="d394d-214">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="d394d-215">Удалите тестовую группу безопасности и тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-215">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="d394d-216">Необязательное требование: параметры динамического членства в группе настроены так, чтобы система автоматически добавляла учетные записи пользователей в группы на основе атрибутов этих учетных записей</span><span class="sxs-lookup"><span data-stu-id="d394d-216">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="d394d-217">Вы определили набор динамических групп в Azure AD и с помощью инструкций в статье [Создание правил на основе атрибутов для динамического членства в группах в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) создали группы и правила, определяющие набор атрибутов и значений учетных записей пользователей для членства в группах.</span><span class="sxs-lookup"><span data-stu-id="d394d-217">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="d394d-p109">Если вы не выполните это требование, то придется вручную управлять членством в группах при добавлении новых учетных записей или при изменении их атрибутов. Например, если какого-либо пользователя переводят из отдела продаж в бухгалтерию, вам потребуется выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d394d-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="d394d-220">Измените значение атрибута "Отдел" для этой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-220">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="d394d-221">Вручную удалите эту учетную запись из группы "Отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="d394d-221">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="d394d-222">Вручную добавьте ее в группу "Бухгалтерия".</span><span class="sxs-lookup"><span data-stu-id="d394d-222">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="d394d-223">Если бы группы "Отдел продаж" и "Бухгалтерия" были динамическими, вам пришлось бы только изменить значение атрибута "Отдел" учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-223">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="d394d-224">Чтобы выполнить это требование, см. [шаг 6](identity-self-service-group-management.md#identity-dyn-groups) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-224">If needed, [Step 6](identity-self-service-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="d394d-225">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-225">How to test</span></span>

1. <span data-ttu-id="d394d-226">На портале Azure создайте тестовую динамическую группу в Azure AD и настройте правило для случая, когда свойство "Отдел" имеет значение test1.</span><span class="sxs-lookup"><span data-stu-id="d394d-226">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="d394d-227">Создайте тестовую учетную запись пользователя в Azure AD и задайте для свойства "Отдел" значение test1.</span><span class="sxs-lookup"><span data-stu-id="d394d-227">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="d394d-228">Проверьте свойства учетной записи пользователя и убедитесь, что она стала членом тестовой динамической группы.</span><span class="sxs-lookup"><span data-stu-id="d394d-228">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="d394d-229">Измените значение свойства "Отдел" тестовой учетной записи на test2.</span><span class="sxs-lookup"><span data-stu-id="d394d-229">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="d394d-230">Проверьте свойства учетной записи пользователя и убедитесь, что она больше не является членом тестовой динамической группы.</span><span class="sxs-lookup"><span data-stu-id="d394d-230">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="d394d-231">Удалите тестовую динамическую группу и тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-231">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="d394d-232">Необязательное требование: лицензирование на основе групп для автоматического назначения и удаления лицензий для учетных записей пользователей с учетом членства в группах</span><span class="sxs-lookup"><span data-stu-id="d394d-232">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="d394d-233">Вы [включили лицензирование на основе групп](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) для соответствующих групп безопасности Azure AD, чтобы можно было автоматически назначать и удалять лицензии для Office 365 и EMS.</span><span class="sxs-lookup"><span data-stu-id="d394d-233">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="d394d-234">Если вы не выполните это требование, вам потребуется вручную выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d394d-234">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="d394d-235">Назначить лицензии новым пользователям, которым вы планируете предоставить доступ к Office 365 и EMS.</span><span class="sxs-lookup"><span data-stu-id="d394d-235">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="d394d-236">Удалить лицензии у пользователей, которые покинули организацию либо у которых не должно быть доступа к Office 365 и EMS.</span><span class="sxs-lookup"><span data-stu-id="d394d-236">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="d394d-237">Чтобы выполнить это требование, см. [шаг 6](identity-self-service-group-management.md#identity-group-license) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="d394d-237">If needed, [Step 6](identity-self-service-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="d394d-238">Проверка</span><span class="sxs-lookup"><span data-stu-id="d394d-238">How to test</span></span>

1. <span data-ttu-id="d394d-239">Создайте тестовую группу безопасности в Azure AD с помощью портала Azure и настройте лицензирование на основе групп, чтобы можно было назначать лицензии на Office 365 и EMS.</span><span class="sxs-lookup"><span data-stu-id="d394d-239">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="d394d-240">Создайте тестовую учетную запись пользователя в Azure AD и добавьте ее в тестовую группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="d394d-240">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="d394d-241">Проверьте свойства учетной записи пользователя в Центре администрирования Microsoft 365 и убедитесь, что ей назначены лицензии на Office 365 и EMS.</span><span class="sxs-lookup"><span data-stu-id="d394d-241">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="d394d-242">Удалите тестовую учетную запись пользователя из тестовой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="d394d-242">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="d394d-243">Проверьте свойства учетной записи пользователя и убедитесь, что этой учетной записи не назначены лицензии на Office 365 и EMS.</span><span class="sxs-lookup"><span data-stu-id="d394d-243">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="d394d-244">Удалите тестовую группу безопасности и тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="d394d-244">Delete the test security group and the test user account.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="d394d-245">Результаты и дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="d394d-245">Results and next steps</span></span>

<span data-ttu-id="d394d-246">В вашей инфраструктуре удостоверений в облаке Microsoft 365 используются строгая проверка подлинности, защищенные учетные записи администраторов, а также упрощенный доступ для пользователей и управление ими.</span><span class="sxs-lookup"><span data-stu-id="d394d-246">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="d394d-247">Если вы выполняете этапы полного развертывания Microsoft 365 корпоративный, следующий этап —[Windows 10 Корпоративная](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="d394d-247">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

