---
title: Шаг 3. Защита пользовательских входов и управление ими
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
description: Вы можете создавать пользовательские входы на устройствах с Windows и в Microsoft 365 более безопасным образом.
ms.openlocfilehash: edf51b344ed8f9c8e13587cc2ccf0ba1ed081da6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090811"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="4c720-103">Шаг 3. Защита пользовательских входов и управление ими</span><span class="sxs-lookup"><span data-stu-id="4c720-103">Step 3: Secure and manage your user sign-ins</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="4c720-104">Использование Windows Hello для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4c720-104">Windows Hello for Business</span></span>

<span data-ttu-id="4c720-105">*Это необязательная процедура, применимая к версиям Microsoft 365 корпоративный E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="4c720-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4c720-106">При входе в устройство с Windows Hello для бизнеса в Windows 10 Корпоративная заменяет пароли надежной двухфакторной проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="4c720-106">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="4c720-107">Два фактора — это новый тип учетных данных пользователей, который связан с устройством и биометрией или ПИН-кодом.</span><span class="sxs-lookup"><span data-stu-id="4c720-107">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="4c720-108">Дополнительные сведения см. в статье [Обзор Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span><span class="sxs-lookup"><span data-stu-id="4c720-108">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="4c720-109">Включение Многофакторной идентификации Azure</span><span class="sxs-lookup"><span data-stu-id="4c720-109">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="4c720-110">*Это необязательная процедура, применимая к версиям Microsoft 365 корпоративный E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="4c720-110">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4c720-111">На этом этапе вами осуществляется многофакторная проверка подлинности Azure (MFA), чтобы добавить второй уровень безопасности для входа пользователей в систему и транзакций.</span><span class="sxs-lookup"><span data-stu-id="4c720-111">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="4c720-112">Для использования MFA требуется дополнительный способ проверки после того, как пользователи правильно ввели свои пароли.</span><span class="sxs-lookup"><span data-stu-id="4c720-112">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="4c720-113">При отсутствии MFA, пароль — единственный способ проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4c720-113">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="4c720-114">Проблема с паролями заключается в том, что многие из них легко угадываются злоумышленниками или непреднамеренно предоставляются ненадежным сторонам.</span><span class="sxs-lookup"><span data-stu-id="4c720-114">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="4c720-115">При многофакторной проверке подлинности можно использовать указанные ниже варианты второго уровня обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="4c720-115">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="4c720-116">Личное надежное устройство, которое трудно подделать, например смартфон.</span><span class="sxs-lookup"><span data-stu-id="4c720-116">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="4c720-117">Биометрический атрибут, например отпечаток пальца.</span><span class="sxs-lookup"><span data-stu-id="4c720-117">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="4c720-118">Вы включите многофакторную проверку подлинности и настроите дополнительный метод проверки подлинности с помощью [политик условного доступа](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), что позволяет использовать группы Azure Active Directory (Azure AD) с целью развертывания многофакторной проверки подлинности для определенных наборов пользователей, например пилотных пользователей, географических регионов или отделов.</span><span class="sxs-lookup"><span data-stu-id="4c720-118">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="4c720-119">Обязательно сообщите своим пользователям, что включена многофакторная проверка подлинности, чтобы они понимали все требования (например, обязательное использование смартфона для входа в систему) и могли успешно входить в систему.</span><span class="sxs-lookup"><span data-stu-id="4c720-119">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="4c720-120">Дополнительные сведения см. в статье [Планирование облачной службы многофакторной проверки подлинности Azure](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="4c720-120">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4c720-122">Руководство по лаборатории тестирования: многофакторная проверка подлинности Azure</span><span class="sxs-lookup"><span data-stu-id="4c720-122">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4c720-123">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-mfa).</span><span class="sxs-lookup"><span data-stu-id="4c720-123">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="4c720-124">Защита от кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="4c720-124">Protect against credential compromise</span></span>

<span data-ttu-id="4c720-125">*Это необязательная процедура, применимая только к версии Microsoft 365 Enterprise E5*</span><span class="sxs-lookup"><span data-stu-id="4c720-125">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4c720-126">В этом разделе описано, как настроить политики, которые защищают от кражи учетных данных, когда злоумышленник определяет имя учетной записи пользователя и пароль, чтобы получить доступ к облачным службам и данным организации.</span><span class="sxs-lookup"><span data-stu-id="4c720-126">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="4c720-127">Защита идентификации Azure AD обеспечивает недоступность учетных данных пользователей для злоумышленников несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="4c720-127">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="4c720-128">С помощью защиты удостоверений Azure AD можно выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4c720-128">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="4c720-129">Определять и устранять потенциальные уязвимости в удостоверениях организации.</span><span class="sxs-lookup"><span data-stu-id="4c720-129">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="4c720-130">В Azure AD используется машинное обучение для выявления отклонений от нормы и подозрительных событий, например входов и действий после входов.</span><span class="sxs-lookup"><span data-stu-id="4c720-130">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="4c720-131">Используя эти данные, защита идентификации Azure AD создает отчеты и оповещения, которые помогут вам оценить проблемы и принять соответствующие меры.</span><span class="sxs-lookup"><span data-stu-id="4c720-131">Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="4c720-132">Определять подозрительные действия, связанные с удостоверениями организации, и автоматически реагировать на них.</span><span class="sxs-lookup"><span data-stu-id="4c720-132">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="4c720-133">Можно настроить политики на основе рисков, автоматически реагирующие на выявленные проблемы при возникновении риска указанного уровня.</span><span class="sxs-lookup"><span data-stu-id="4c720-133">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="4c720-134">Эти политики, а также другие средства контроля условного доступа, предоставляемые службами Azure AD и Microsoft Intune, могут либо автоматически блокировать доступ, либо принимать соответствующие меры, включая сброс паролей и требование многофакторной проверки подлинности Azure для последующих входов.</span><span class="sxs-lookup"><span data-stu-id="4c720-134">These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="4c720-135">Исследовать подозрительные происшествия и разрешать их с помощью административных действий.</span><span class="sxs-lookup"><span data-stu-id="4c720-135">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="4c720-136">Вы можете исследовать события, связанные с риском, используя сведения об инцидентах безопасности.</span><span class="sxs-lookup"><span data-stu-id="4c720-136">You can investigate risk events using information about the security incident.</span></span> <span data-ttu-id="4c720-137">Доступны основные рабочие процессы  для отслеживания исследований и принятия мер, например сброс паролей.</span><span class="sxs-lookup"><span data-stu-id="4c720-137">Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="4c720-138">См. [дополнительные сведения о защите удостоверений Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="4c720-138">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="4c720-139">См. описание [действий по включению защиты идентификации Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="4c720-139">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="4c720-140">В результате выполнения данного шага у вас будет включена защита идентификации Azure AD, и вы будете использовать ее для выполнения указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4c720-140">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="4c720-141">Устранение потенциальных уязвимостей, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="4c720-141">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="4c720-142">Обнаружение попыток компрометации учетных данных.</span><span class="sxs-lookup"><span data-stu-id="4c720-142">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="4c720-143">Изучение и разрешение текущих подозрительных инцидентов, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="4c720-143">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4c720-145">Руководство по лаборатории тестирования: защита удостоверений Azure AD</span><span class="sxs-lookup"><span data-stu-id="4c720-145">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4c720-146">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-ident-prot).</span><span class="sxs-lookup"><span data-stu-id="4c720-146">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="4c720-147">Добавление учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="4c720-147">Add your user accounts</span></span>](identity-add-user-accounts.md) |
