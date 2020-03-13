---
title: Шаг 2. Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной
f1.keywords:
- NOCSH
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
description: Убедитесь, что используемая вами конфигурация соответствует условиям Microsoft 365 корпоративный для служб и инфраструктуры, основанных на удостоверениях.
ms.openlocfilehash: 3fd4d0a1df50d55cb7a21668b609341d0c01aa35
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544068"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="5c6cf-103">Шаг 2. Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной</span><span class="sxs-lookup"><span data-stu-id="5c6cf-103">Phase 2: Identity infrastructure exit criteria</span></span>

![Этап 2. Удостоверения](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5c6cf-105">Убедитесь, что инфраструктура удостоверений соответствует указанным ниже обязательным условиям и что рассмотрены необязательные условия.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-105">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="5c6cf-106">Дополнительные рекомендации по инфраструктуре удостоверений см. в разделе [Предварительные требования](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-106">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="5c6cf-107">Обязательное требование: ваши учетные записи глобальных администраторов защищены</span><span class="sxs-lookup"><span data-stu-id="5c6cf-107">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="5c6cf-108">Вы [защитили свои учетные записи глобальных администраторов Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts), чтобы предотвратить компрометацию учетных данных злоумышленниками, которая может привести к нарушению безопасности подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-108">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="5c6cf-109">Если вы не выполните это требование, ваши учетные записи глобальных администраторов могут быть уязвимыми для атак и компрометации. В этом случае злоумышленники получат полный доступ к вашим системе и данным: они смогут использовать или уничтожить ваши данные либо потребовать за них выкуп.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-109">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="5c6cf-110">Чтобы выполнить это требование, см. [шаг 1](identity-create-protect-global-admins.md#identity-global-admin) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-110">If needed, [Step 1](identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5c6cf-111">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-111">How to test</span></span>

<span data-ttu-id="5c6cf-112">Чтобы убедиться, что ваши учетные записи глобальных администраторов защищены, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-112">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="5c6cf-113">Выполните указанную ниже команду Azure Active Directory PowerShell для Graph в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-113">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="5c6cf-114">Должен отобразиться только список выделенных учетных записей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-114">You should see only the list of dedicated global administrator accounts.</span></span>
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="5c6cf-115">Войдите в Office 365 с помощью каждой из учетных записей, указанных в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-115">Sign in to Office 365 using each of the accounts from step 1.</span></span> <span data-ttu-id="5c6cf-116">При каждом входе система должна требовать многофакторную проверку подлинности Azure с использованием максимально надежного способа дополнительной проверки подлинности, доступного в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-116">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="5c6cf-117">Инструкции по установке модуля Azure Active Directory PowerShell для Graph и входу в Office 365 см. в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-117">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="5c6cf-118">Необязательное требование: вы настроили управление привилегированными пользователями для поддержки назначений роли глобального администратора по требованию</span><span class="sxs-lookup"><span data-stu-id="5c6cf-118">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="5c6cf-119">С помощью сведений в статье [Что такое Azure AD Privileged Identity Management?](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) вы включили функцию управления привилегированными пользователями в своем клиенте Azure AD и настроили учетные данные глобальных администраторов в качестве администраторов, наделенных соответствующими полномочиями.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-119">You've used the instructions in [Configure Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="5c6cf-120">Кроме того, следуя рекомендациям в статье [Защита привилегированного доступа для гибридных и облачных развертываний в Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices), вы разработали стратегический план защиты привилегированного доступа от кибератак.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-120">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="5c6cf-121">Если вы не выполните это требование, ваши учетные записи глобальных администраторов будут подвергаться постоянным атакам и в случае их компрометации злоумышленники смогут копировать или уничтожать ваши конфиденциальные данные либо требовать выкуп за них.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-121">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="5c6cf-122">В этом вам поможет описание [шага 1](identity-create-protect-global-admins.md#identity-pim).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-122">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="5c6cf-123">Необязательное требование: у вас настроено управление привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="5c6cf-123">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="5c6cf-124">С помощью сведений в статье [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) вы включили привилегированный доступ и создали одну или несколько политик привилегированного доступа в организации.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-124">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="5c6cf-125">Вы настроили эти политики и включили своевременный доступ для получения доступа к конфиденциальным данным или важным параметрам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-125">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="5c6cf-126">Чтобы выполнить это требование, см. [шаг 1](identity-create-protect-global-admins.md#identity-pam) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-126">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="5c6cf-127">Необязательное требование: защита паролей Azure AD запрещает использовать слабые пароли</span><span class="sxs-lookup"><span data-stu-id="5c6cf-127">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="5c6cf-128">Вы можете включить запрет слабых паролей в [облачной среде](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) и [локальных доменных службах Active Directory (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) с применением глобально запрещенных паролей и, при желании, настраиваемых терминов.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-128">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="5c6cf-129">Чтобы выполнить это требование, см. [шаг 2](identity-secure-your-passwords.md#identity-password-prot) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-129">If needed, [Step 2](identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="5c6cf-130">Необязательное требование: пользователи могут сбрасывать свои пароли</span><span class="sxs-lookup"><span data-stu-id="5c6cf-130">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="5c6cf-131">С помощью сведений в статье [Быстрое развертывание самостоятельного сброса пароля в Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) вы настроили функцию сброса паролей для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-131">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="5c6cf-132">Если вы не выполните это условие, то чтобы сбросить пароль, пользователям придется обращаться к администраторам учетных записей пользователей, и это приведет к дополнительным издержкам на ИТ-администрирование.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-132">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="5c6cf-133">Чтобы выполнить это требование, см. [шаг 2](identity-secure-your-passwords.md#identity-pw-reset) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-133">If needed, [Step 2](identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="5c6cf-134">Необязательное требование: пользователи могут входить в систему с помощью простого единого входа Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c6cf-134">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="5c6cf-135">С помощью сведений в статье [Azure AD Connect: простой единый вход](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) вы включили функцию единого входа для своей организации. Это упростило вход в облачные приложения, например в Office 365, для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-135">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="5c6cf-136">Если вы не выполните это требование, система, возможно, будет предлагать вашим пользователям вводить учетные данные при доступе к дополнительным приложениям, использующим клиент Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-136">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use you Azure AD tenant.</span></span>

<span data-ttu-id="5c6cf-137">Чтобы выполнить это требование, см. [шаг 2](identity-secure-your-passwords.md#identity-sso) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-137">If needed, [Step 2](identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="5c6cf-138">Необязательное требование: экран входа в Office 365 персонализирован для вашей организации</span><span class="sxs-lookup"><span data-stu-id="5c6cf-138">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="5c6cf-139">Вы добавили фирменную символику своей организации на страницу входа Office 365 с помощью функции [добавления фирменной символики своей компании на страницы входа и панели доступа](https://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-139">You have used [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="5c6cf-140">Если вы не выполните это требование, для ваших пользователей будет отображаться стандартный экран входа в Office 365, и они, возможно, не будут точно знать, что выполняют вход на сайт вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-140">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="5c6cf-141">Чтобы выполнить это требование, см. [шаг 2](identity-secure-your-passwords.md#identity-custom-sign-in) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-141">If needed, [Step 2](identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="5c6cf-142">Необязательное требование: многофакторная проверка подлинности Azure включена для ваших пользователей</span><span class="sxs-lookup"><span data-stu-id="5c6cf-142">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="5c6cf-143">Чтобы включить многофакторную проверку подлинности Azure для своих пользователей, вы [выполнили планирование многофакторной проверки подлинности Azure](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) и использовали [политики условного доступа](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-143">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="5c6cf-p104">Если вы не выполните это требование, ваши учетные записи пользователей будут уязвимы для компрометации злоумышленниками. При компрометации пароля учетной записи пользователя все ресурсы и возможности этой учетной записи, например роли администраторов, будут доступны злоумышленникам, и они смогут копировать или уничтожать данные, а также блокировать их, требуя у вас выкуп.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="5c6cf-147">Чтобы выполнить это требование, см. [шаг 3](identity-secure-user-sign-ins.md#identity-mfa) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-147">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5c6cf-148">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-148">How to test</span></span>

1.  <span data-ttu-id="5c6cf-149">Создайте тестовую учетную запись пользователя и назначьте ей лицензию.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-149">Create a test user account and assign them a license.</span></span> 
2.  <span data-ttu-id="5c6cf-150">Настройте многофакторную проверку подлинности Azure для тестовой учетной записи с дополнительным методом проверки, который вы используете для реальных учетных записей пользователей, например отправку текстового сообщения на телефон.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-150">Configure Azure Multi-Factor Authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a text message to your phone.</span></span> 
3.  <span data-ttu-id="5c6cf-151">Войдите в систему на портале Office 365, используя тестовую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-151">Sign in to the Office 36 portal with the test user account.</span></span>
4.  <span data-ttu-id="5c6cf-152">Убедитесь, что при многофакторной проверке подлинности система предлагает указать дополнительные проверочные сведения и в результате успешно выполняет проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-152">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="5c6cf-153">Удалите тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-153">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-e5-only"></a><span data-ttu-id="5c6cf-154">Необязательное требование: включена функция защиты идентификации Azure AD для защиты от компрометации учетных данных (только для Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="5c6cf-154">Optional: Azure AD Identity Protection is enabled to protect against credential compromise (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="5c6cf-155">Вы включили функцию защиты идентификации Azure AD для указанных ниже целей.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-155">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="5c6cf-156">Устранение потенциальных уязвимостей, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-156">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="5c6cf-157">Обнаружение попыток компрометации учетных данных.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-157">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="5c6cf-158">Изучение и разрешение текущих подозрительных инцидентов, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-158">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="5c6cf-p105">Если вы не выполните это требование, у вас не будет возможности обнаруживать или автоматически пресекать попытки компрометации учетных данных или расследовать инциденты безопасности, связанные с идентификацией. Это сделает вашу организацию уязвимой к попыткам компрометации учетных данных и подвергает конфиденциальные данные организации риску.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="5c6cf-161">Чтобы выполнить это требование, см. [шаг 3](identity-secure-user-sign-ins.md#identity-ident-prot) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-161">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="5c6cf-162">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-162">How to test</span></span>

1. <span data-ttu-id="5c6cf-163">Создайте тестовую учетную запись с первоначальным паролем.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-163">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="5c6cf-164">Следуя инструкциям в статье [Предоставление пользователям прав на самостоятельный сброс пароля в Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords), выполните сброс пароля для тестовой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-164">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="5c6cf-165">Выйдите из системы и войдите в тестовую учетную запись пользователя с помощью функции сброса пароля.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-165">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="5c6cf-166">Удалите тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-166">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="5c6cf-167">Обязательное требование для гибридной идентификации: пользователи и группы синхронизированы с Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c6cf-167">Required for hybrid identity: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="5c6cf-168">Если у вас есть локальные доменные службы Active Directory (AD DS), вы уже использовали Azure AD Connect для синхронизации учетных записей пользователей и групп из ваших локальных служб AD DS в клиент Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-168">If you have an existing on-premises Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises AD DS to your Azure AD tenant.</span></span>

<span data-ttu-id="5c6cf-169">Благодаря службе синхронизации каталогов ваши пользователи могут входить в систему в Office 365 и в других облачных службах Майкрософт, используя те же учетные данные, которые они используют для входа в систему на своих компьютерах и для доступа к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-169">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="5c6cf-170">Чтобы выполнить это требование, см. [шаг 4](identity-add-user-accounts.md#identity-sync) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-170">If needed, [Step 4](identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="5c6cf-171">Если вы не выполните это требование, у вас будут два указанных ниже набора учетных записей пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-171">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="5c6cf-172">Учетные записи пользователей и группы в локальных службах AD DS</span><span class="sxs-lookup"><span data-stu-id="5c6cf-172">User accounts and groups that exist in your on-premises AD DS</span></span>
- <span data-ttu-id="5c6cf-173">Учетные записи пользователей и группы в клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-173">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="5c6cf-p106">В этом случае ИТ-администраторам и пользователям придется вручную обслуживать оба набора. Это неизбежно приведет к появлению несинхронизированных учетных записей, паролей и групп.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-p106">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5c6cf-176">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-176">How to test</span></span>
<span data-ttu-id="5c6cf-177">Чтобы проверить, правильно ли работает проверка подлинности с использованием локальных учетных данных, войдите в систему на портале Office с помощью своих локальных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-177">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="5c6cf-178">Чтобы убедиться, что синхронизация каталогов работает правильно, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-178">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="5c6cf-179">Создайте тестовую группу в AD DS.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-179">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="5c6cf-180">Подождите, пока будет выполнена синхронизация.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-180">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="5c6cf-181">Проверьте, появилось ли название новой тестовой группы в клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-181">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="5c6cf-182">Необязательное требование: отслеживается синхронизация каталогов</span><span class="sxs-lookup"><span data-stu-id="5c6cf-182">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="5c6cf-183">С помощью сведений в статье [Мониторинг синхронизации Azure AD Connect с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (для синхронизации паролей) или в статье [Мониторинг AD FS с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (для федеративной проверки подлинности) вы развернули Azure AD Connect Health, выполнив при этом указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-183">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="5c6cf-184">Установка агента Azure AD Connect Health на каждый из ваших локальных серверов удостоверений.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-184">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="5c6cf-185">Отслеживание текущей синхронизации на портале Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-185">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="5c6cf-186">Если вы не выполните это требование, то сможете более точно оценивать состояние своей облачной инфраструктуры идентификации.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-186">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="5c6cf-187">Чтобы выполнить это требование, см. [шаг 4](identity-add-user-accounts.md#identity-sync-health) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-187">If needed, [Step 4](identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5c6cf-188">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-188">How to test</span></span>
<span data-ttu-id="5c6cf-189">На портале Azure AD Connect Health можно получить сведения о текущем и правильном состоянии ваших локальных контроллеров доменов и текущей синхронизации.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-189">The Azure AD Connect Health portal shows the current and correct state of your on-premises domain controllers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="5c6cf-190">Необязательное требование: включена функция обратной записи пароля для ваших пользователей</span><span class="sxs-lookup"><span data-stu-id="5c6cf-190">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="5c6cf-191">Выполнив инструкции в статье [Быстрое развертывание самостоятельного сброса пароля в Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started), вы включили функцию обратной записи пароля для клиента Azure AD в своей подписке Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-191">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="5c6cf-192">Если пропустить этот параметр, то пользователи, не подключенные к локальной сети, должны будут сбросить или разблокировать свои пароли AD DS через ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-192">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="5c6cf-193">Чтобы выполнить это требование, см. [шаг 4](identity-add-user-accounts.md#identity-pw-writeback) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-193">If needed, [Step 4](identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="5c6cf-194">Функция обратной записи пароля необходима, чтобы в полной мере использовать возможности защиты идентификации Azure AD, например чтобы требовать от пользователей изменять свои локальные пароли, если Azure AD обнаружила высокий риск компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-194">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="5c6cf-195">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-195">How to test</span></span>

<span data-ttu-id="5c6cf-196">Протестируйте функцию обратной записи пароля, изменив свой пароль в Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-196">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="5c6cf-197">У вас должно получиться использовать свою учетную запись и новый пароль для доступа к локальным ресурсам AD DS.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-197">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="5c6cf-198">Создайте тестовую учетную запись в локальных службах AD DS, разрешите синхронизацию каталогов, а затем предоставьте этой учетной записи лицензию на Microsoft 365 корпоративный в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-198">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it a Microsoft 365 Enterprise license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="5c6cf-199">Используя учетные данные тестовой учетной записи, войдите в систему на удаленном компьютере, присоединенном к вашему локальному домену AD DS, а также на портал Office.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-199">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="5c6cf-200">Щелкните **Параметры > Параметры Office 365 > Пароль > Изменить пароль**.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-200">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="5c6cf-201">Введите текущий пароль, введите новый пароль, а затем подтвердите новый пароль.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-201">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="5c6cf-202">Выйдите из системы на портале Office и на удаленном компьютере, а затем войдите в систему на компьютере, используя тестовую учетную запись и новый пароль для нее.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-202">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="5c6cf-203">Это подтвердит, что вы можете изменить пароль учетной записи в локальных службах AD DS с помощью клиента Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-203">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5c6cf-204">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-204">How to test</span></span>

<span data-ttu-id="5c6cf-205">Войдите в систему на портале Office 365, используя имя вашей учетной записи и пройдя многофакторную проверку подлинности Azure.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-205">Sign in to the Office 365 portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="5c6cf-206">На странице входа в систему должны отображаться элементы фирменной символики вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-206">You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="5c6cf-207">Необязательное требование: включено самостоятельное управление группами для определенных групп безопасности Azure AD и групп Office 365</span><span class="sxs-lookup"><span data-stu-id="5c6cf-207">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="5c6cf-208">Вы определили группы, подходящие для самостоятельного управления, рассказали их владельцам о рабочем процессе управления группами и об их ответственности, а также [настроили функцию самостоятельного управления в Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) для таких групп.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-208">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="5c6cf-209">Если вы не выполните это требование, все задачи по управлению группами Azure AD придется выполнять ИТ-администраторам.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-209">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="5c6cf-210">Чтобы выполнить это требование, см. [шаг 5](identity-use-group-management.md#identity-self-service-groups) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-210">If needed, [Step 5](identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5c6cf-211">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-211">How to test</span></span>
1.  <span data-ttu-id="5c6cf-212">На портале Azure создайте тестовую учетную запись пользователя в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-212">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="5c6cf-213">Войдите в систему с помощью тестовой учетной записи пользователя и создайте тестовую группу безопасности Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-213">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="5c6cf-214">Выйдите из системы, а затем снова войдите в нее с помощью своей учетной записи ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-214">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="5c6cf-215">Настройте тестовую группу безопасности для самостоятельного управления для тестовой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-215">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="5c6cf-216">Выйдите из системы, а затем снова войдите в нее с помощью тестовой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-216">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="5c6cf-217">На портале Azure добавьте участников в тестовую группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-217">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="5c6cf-218">Удалите тестовую группу безопасности и тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-218">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="5c6cf-219">Необязательное требование: параметры динамического членства в группе настроены так, чтобы система автоматически добавляла учетные записи пользователей в группы на основе атрибутов этих учетных записей</span><span class="sxs-lookup"><span data-stu-id="5c6cf-219">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="5c6cf-220">Вы определили набор динамических групп в Azure AD и с помощью инструкций в статье [Создание правил на основе атрибутов для динамического членства в группах в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) создали группы и правила, определяющие набор атрибутов и значений учетных записей пользователей для членства в группах.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-220">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="5c6cf-p110">Если вы не выполните это требование, то придется вручную управлять членством в группах при добавлении новых учетных записей или при изменении их атрибутов. Например, если какого-либо пользователя переводят из отдела продаж в бухгалтерию, вам потребуется выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-p110">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="5c6cf-223">Измените значение атрибута "Отдел" для этой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-223">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="5c6cf-224">Вручную удалите эту учетную запись из группы "Отдел продаж".</span><span class="sxs-lookup"><span data-stu-id="5c6cf-224">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="5c6cf-225">Вручную добавьте ее в группу "Бухгалтерия".</span><span class="sxs-lookup"><span data-stu-id="5c6cf-225">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="5c6cf-226">Если бы группы "Отдел продаж" и "Бухгалтерия" были динамическими, вам пришлось бы только изменить значение атрибута "Отдел" учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-226">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="5c6cf-227">Чтобы выполнить это требование, см. [шаг 5](identity-use-group-management.md#identity-dyn-groups) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-227">If needed, [Step 5](identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5c6cf-228">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-228">How to test</span></span>

1. <span data-ttu-id="5c6cf-229">На портале Azure создайте тестовую динамическую группу в Azure AD и настройте правило для случая, когда свойство "Отдел" имеет значение test1.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-229">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="5c6cf-230">Создайте тестовую учетную запись пользователя в Azure AD и задайте для свойства "Отдел" значение test1.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-230">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="5c6cf-231">Проверьте свойства учетной записи пользователя и убедитесь, что она стала членом тестовой динамической группы.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-231">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="5c6cf-232">Измените значение свойства "Отдел" тестовой учетной записи на test2.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-232">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="5c6cf-233">Проверьте свойства учетной записи пользователя и убедитесь, что она больше не является членом тестовой динамической группы.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-233">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="5c6cf-234">Удалите тестовую динамическую группу и тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-234">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="5c6cf-235">Необязательное требование: лицензирование на основе групп для автоматического назначения и удаления лицензий для учетных записей пользователей с учетом членства в группах</span><span class="sxs-lookup"><span data-stu-id="5c6cf-235">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="5c6cf-236">Вы [включили лицензирование на основе групп](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) для соответствующих групп безопасности Azure AD, чтобы можно было автоматически назначать и отменять лицензии на Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-236">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that your Microsoft 365 Enterprise licenses are automatically assigned or unassigned.</span></span>

<span data-ttu-id="5c6cf-237">Если вы не выполните это требование, вам потребуется вручную выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-237">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="5c6cf-238">Назначить лицензии новым пользователям, которым вы планируете предоставить доступ.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-238">Assign licenses to new users whom you intend to have access.</span></span>
- <span data-ttu-id="5c6cf-239">Отменить лицензии у пользователей, которые покинули организацию либо у которых не должно быть доступа.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-239">Unassign licenses from users who are no longer with your organization or do not have access.</span></span>

<span data-ttu-id="5c6cf-240">Чтобы выполнить это требование, см. [шаг 5](identity-use-group-management.md#identity-group-license) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-240">If needed, [Step 5](identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="5c6cf-241">Проверка</span><span class="sxs-lookup"><span data-stu-id="5c6cf-241">How to test</span></span>

1. <span data-ttu-id="5c6cf-242">Создайте тестовую группу безопасности в Azure AD с помощью портала Azure и настройте лицензирование на основе групп, чтобы можно было назначать лицензии на Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-242">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Microsoft 365 Enterprise license.</span></span>
2. <span data-ttu-id="5c6cf-243">Создайте тестовую учетную запись пользователя в Azure AD и добавьте ее в тестовую группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-243">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="5c6cf-244">Проверьте свойства учетной записи пользователя в Центре администрирования Microsoft 365 и убедитесь, что ей назначены лицензии на Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-244">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Microsoft 365 Enterprise license.</span></span>
4. <span data-ttu-id="5c6cf-245">Удалите тестовую учетную запись пользователя из тестовой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-245">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="5c6cf-246">Проверьте свойства учетной записи пользователя и убедитесь, что этой учетной записи не назначены лицензии на Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-246">Examine the properties of the user account to ensure that it no longer has the Microsoft 365 Enterprise license assigned.</span></span>
6. <span data-ttu-id="5c6cf-247">Удалите тестовую группу безопасности и тестовую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-247">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="5c6cf-248">Необязательное требование: настроенные проверки доступа используются для контроля доступа</span><span class="sxs-lookup"><span data-stu-id="5c6cf-248">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="5c6cf-249">Вы использовали эти статьи, чтобы настроить различные типов проверок доступа для контроля участия в группах, доступа к корпоративным приложениям и назначения ролей:</span><span class="sxs-lookup"><span data-stu-id="5c6cf-249">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="5c6cf-250">Группы и приложения</span><span class="sxs-lookup"><span data-stu-id="5c6cf-250">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="5c6cf-251">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c6cf-251">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="5c6cf-252">Роли ресурсов Azure</span><span class="sxs-lookup"><span data-stu-id="5c6cf-252">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="5c6cf-253">Чтобы выполнить это требование, см. [шаг 6](identity-configure-identity-governance.md#identity-access-reviews) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-253">If needed, [Step 6](identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>


## <a name="results-and-next-steps"></a><span data-ttu-id="5c6cf-254">Результаты и дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5c6cf-254">Results and next steps</span></span>

<span data-ttu-id="5c6cf-255">В вашей инфраструктуре удостоверений в облаке Microsoft 365 используются строгая проверка подлинности, защищенные учетные записи администраторов, а также упрощенный доступ для пользователей и управление ими.</span><span class="sxs-lookup"><span data-stu-id="5c6cf-255">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![Этап 3. Windows 10 Корпоративная](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="5c6cf-257">Если вы выполняете этапы полного развертывания Microsoft 365 корпоративный, следующий этап —[Windows 10 Корпоративная](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="5c6cf-257">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

