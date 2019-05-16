---
title: Шаг 4. Настройка безопасной проверки подлинности пользователя
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить многофакторную проверку подлинности для учетных записей пользователей.
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072089"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="4d5d6-103">Шаг 4. Настройка безопасной проверки подлинности пользователя</span><span class="sxs-lookup"><span data-stu-id="4d5d6-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="4d5d6-104">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="4d5d6-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="4d5d6-105">*Это необязательная процедура, применимая к версиям Microsoft 365 Enterprise E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="4d5d6-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4d5d6-p101">На этом шаге вы настроите многофакторную проверку подлинности, чтобы добавить второй уровень обеспечения безопасности при входе пользователей в систему и выполнении транзакций. При многофакторной проверке подлинности требуется использовать дополнительный метод проверки после того, как пользователь правильно ввел свой пароль. Если многофакторная проверка подлинности не используется, то пароль — единственный метод проверки. С паролями связана одна проблема: злоумышленники могут легко угадать многие пароли. Кроме того, пользователи могут непреднамеренно сообщить свои пароли ненадежным лицам и организациям.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="4d5d6-110">При многофакторной проверке подлинности можно использовать указанные ниже варианты второго уровня обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="4d5d6-111">Личное надежное устройство, которое трудно подделать, например смартфон.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="4d5d6-112">Биометрический атрибут, например отпечаток пальца.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="4d5d6-p102">Вы включите многофакторную проверку подлинности и настроите дополнительный метод проверки подлинности для каждой учетной записи. Обязательно сообщите пользователям, что включена многофакторная проверка подлинности, чтобы они понимали все требования (например, обязательное использование смартфона для входа в систему) и могли успешно входить в систему.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span>

<span data-ttu-id="4d5d6-115">Дополнительные сведения см. в статье [планирование многофакторной проверки подлинности](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="4d5d6-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="4d5d6-116">В некоторых приложениях, например Microsoft Office 2010 или более ранних версий и Apple Mail, нельзя использовать многофакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-116">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA.</span></span> <span data-ttu-id="4d5d6-117">Чтобы использовать эти приложения, нужно применять «пароли приложений» вместо традиционных паролей.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-117">To use these apps, you’ll need to use “app passwords” in place of your traditional password.</span></span> <span data-ttu-id="4d5d6-118">Пароль приложения дает возможность приложению обойти многофакторную проверку подлинности и продолжить работу.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-118">The app password allows the app to bypass MFA and continue working.</span></span> <span data-ttu-id="4d5d6-119">Дополнительные сведения о паролях приложений см. в статье [Создание пароля приложения для Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="4d5d6-119">To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4d5d6-121">Руководство по лаборатории тестирования: многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="4d5d6-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4d5d6-122">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-mfa).</span><span class="sxs-lookup"><span data-stu-id="4d5d6-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="4d5d6-123">Защита от кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="4d5d6-123">Protect against credential compromise</span></span>

<span data-ttu-id="4d5d6-124">*Это необязательная процедура, применимая только к версии Microsoft 365 Enterprise E5*</span><span class="sxs-lookup"><span data-stu-id="4d5d6-124">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4d5d6-125">В этом разделе описано, как настроить политики, которые защищают от кражи учетных данных, когда злоумышленник определяет имя учетной записи пользователя и пароль, чтобы получить доступ к облачным службам и данным организации.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-125">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="4d5d6-126">Защита удостоверений Azure AD несколькими способами мешает злоумышленнику переместиться между учетными записями и группами и выйти в итоге к наиболее ценным данным.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-126">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="4d5d6-127">С помощью защиты удостоверений Azure AD можно выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-127">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="4d5d6-128">Определять и устранять потенциальные уязвимости в удостоверениях организации.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-128">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="4d5d6-129">В Azure AD используется машинное обучение для выявления отклонений от нормы и подозрительных событий, например входов и действий после входов.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-129">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="4d5d6-130">Используя эти данные, защита удостоверений создает отчеты и оповещения, которые помогут вам оценить проблемы и принять соответствующие меры.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-130">Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="4d5d6-131">Определять подозрительные действия, связанные с удостоверениями организации, и автоматически реагировать на них.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-131">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="4d5d6-132">Можно настроить политики на основе рисков, автоматически реагирующие на выявленные проблемы при возникновении риска указанного уровня.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-132">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="4d5d6-133">Эти политики, а также другие средства контроля условного доступа, предоставляемые Azure Active Directory и решение Enterprise Mobility + Security (EMS), могут либо автоматически блокировать доступ, либо принимать соответствующие меры, включая сброс паролей и требование многофакторной проверки подлинности для последующих входов.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-133">These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="4d5d6-134">Исследовать подозрительные происшествия и разрешать их с помощью административных действий.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-134">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="4d5d6-135">Вы можете исследовать события, связанные с риском, используя сведения об инцидентах безопасности.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-135">You can investigate risk events using information about the security incident.</span></span> <span data-ttu-id="4d5d6-136">Доступны основные рабочие процессы  для отслеживания исследований и принятия мер, например сброс паролей.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-136">Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="4d5d6-137">См. [дополнительные сведения о защите удостоверений Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="4d5d6-137">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="4d5d6-138">См. описание [действий по включению защиты идентификации Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="4d5d6-138">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="4d5d6-139">В результате выполнения данного шага у вас будет включена защита идентификации Azure AD, и вы будете использовать ее для выполнения указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-139">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="4d5d6-140">Устранение потенциальных уязвимостей, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-140">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="4d5d6-141">Обнаружение попыток компрометации учетных данных.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-141">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="4d5d6-142">Изучение и разрешение текущих подозрительных инцидентов, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-142">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4d5d6-144">Руководство по лаборатории тестирования: защита удостоверений Azure AD</span><span class="sxs-lookup"><span data-stu-id="4d5d6-144">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4d5d6-145">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-ident-prot).</span><span class="sxs-lookup"><span data-stu-id="4d5d6-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="4d5d6-146">Отслеживать активность клиента и вход</span><span class="sxs-lookup"><span data-stu-id="4d5d6-146">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="4d5d6-147">*Это необязательная процедура, применимая к версиям Microsoft 365 Enterprise E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="4d5d6-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4d5d6-p108">На этом шаге вы научитесь проверять журналы аудита и действия при входе в систему с помощью функции создания отчетов в Azure AD. Доступны два типа отчетов.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-p108">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="4d5d6-p109">В **отчете о действиях в журналах аудита** указаны сведения о каждой задаче, выполненной в вашем клиенте Azure AD. Этот отчет отвечает на указанные ниже вопросы.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-p109">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="4d5d6-152">Кто добавил определенного пользователя в группу администраторов?</span><span class="sxs-lookup"><span data-stu-id="4d5d6-152">Who added someone to an admin group?</span></span>
- <span data-ttu-id="4d5d6-153">Какие пользователи выполняют вход в определенном приложении?</span><span class="sxs-lookup"><span data-stu-id="4d5d6-153">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="4d5d6-154">Какое количество сбросов паролей выполняется?</span><span class="sxs-lookup"><span data-stu-id="4d5d6-154">How many password resets are happening?</span></span>

<span data-ttu-id="4d5d6-p110">В **отчете о действиях при входе в систему** указаны сведения о том, кто выполнял задачи, указанные в отчете журналов аудита. Этот отчет отвечает на указанные ниже вопросы.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-p110">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="4d5d6-157">Каков шаблон входа в систему для определенного пользователя?</span><span class="sxs-lookup"><span data-stu-id="4d5d6-157">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="4d5d6-158">Сколько входов в систему было выполнено за день, неделю или месяц?</span><span class="sxs-lookup"><span data-stu-id="4d5d6-158">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="4d5d6-159">Какое количество попыток входа в систему было неуспешным и для каких учетных записей?</span><span class="sxs-lookup"><span data-stu-id="4d5d6-159">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="4d5d6-160">Дополнительные сведения об отчетах и о том, как получить доступ к ним, см. в статье [Отчеты Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="4d5d6-160">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="4d5d6-161">В результате выполнения этого шага вы узнаете об этих отчетах и будете понимать, как использовать их для анализа событий и действий в Azure AD с целью планирования и обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="4d5d6-161">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>



## <a name="next-step"></a><span data-ttu-id="4d5d6-162">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="4d5d6-162">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="4d5d6-163">Упрощение доступа для пользователей</span><span class="sxs-lookup"><span data-stu-id="4d5d6-163">Simplify access for users</span></span>](identity-password-reset.md) |

