---
title: Распространенные удостоверения и устройства для доступа к политики - Microsoft 365 Enterprise | Документация Microsoft
description: Описание рекомендаций Майкрософт по применению политик и конфигураций доступа для удостоверений и устройств.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ab8454c27cd57b6bd5cc8df6e1526ee2950ac998
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871074"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="a0dd2-103">Основные политики доступа для удостоверений и устройств</span><span class="sxs-lookup"><span data-stu-id="a0dd2-103">Common identity and device access policies</span></span>
<span data-ttu-id="a0dd2-104">В этой статье описываются общие, рекомендуется политик безопасности доступа к облачные службы, опубликовано включая локальных приложений с Azure AD прокси приложения.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="a0dd2-p101">В этом руководстве содержатся инструкции по развертыванию рекомендуемые политики в среде вновь подготовить к работе. Настройка этих политик в отдельном лабораторной среде позволяет понять и оценка рекомендуемые политики перед поэтапное развертывание вашей подготовки и рабочей среды. Только что подготовленные среда может быть только в облаке или комбинированным.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p101">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments. Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="a0dd2-108">Политика set</span><span class="sxs-lookup"><span data-stu-id="a0dd2-108">Policy set</span></span> 

<span data-ttu-id="a0dd2-p102">На следующем рисунке показано несколько набора политик. Показано какой уровень защиты каждой политики применяется к и ли политики применяются к ПК или телефоны и планшетные ПК или обе категории устройств. Также указывается, где этих политик.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![Общие политики для настройки удостоверения и устройства доступа](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="a0dd2-113">Далее в этой статье описывается, как настроить эти политики.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="a0dd2-p103">Прежде чем отправлять заявки на получение устройств в Intune Software assurance, устройство во временном пользовании целям пользователя рекомендуется использовать многофакторной проверки подлинности. Также необходимо зарегистрировать устройств в Intune до применения политики соответствия устройства.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="a0dd2-p104">Чтобы предоставить время для выполнения этих задач, рекомендуется реализации политик базового в том порядке, перечисленные в следующей таблице. Тем не менее политики многофакторной проверкой Подлинности для защиты конфиденциальных и сильно регулируемого могут быть реализованы в любое время.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="a0dd2-118">Уровень защиты</span><span class="sxs-lookup"><span data-stu-id="a0dd2-118">Protection level</span></span>|<span data-ttu-id="a0dd2-119">Политики.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-119">Policies</span></span>|<span data-ttu-id="a0dd2-120">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="a0dd2-121">**Базовый уровень**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-121">**Baseline**</span></span>|[<span data-ttu-id="a0dd2-122">После входа в риска *Средний* или *высокий* требуют многофакторной проверкой Подлинности</span><span class="sxs-lookup"><span data-stu-id="a0dd2-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="a0dd2-123">Блокировать клиенты, не поддерживающие современных проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a0dd2-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="a0dd2-124">Клиентов, не использующих современных проверки подлинности может обходить правила условного доступа, поэтому важно для блокировки этих</span><span class="sxs-lookup"><span data-stu-id="a0dd2-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="a0dd2-125">Пользователи высокого риска смену пароля</span><span class="sxs-lookup"><span data-stu-id="a0dd2-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="a0dd2-126">Заставляет пользователя должен сменить пароль при входе в высокого риска действия в случае обнаружения для своей учетной записи</span><span class="sxs-lookup"><span data-stu-id="a0dd2-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="a0dd2-127">Определение политик защиты от приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="a0dd2-128">Одна политика на платформу (операций ввода-вывода, Android, Windows).</span><span class="sxs-lookup"><span data-stu-id="a0dd2-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="a0dd2-129">Требовать одобренных приложений</span><span class="sxs-lookup"><span data-stu-id="a0dd2-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="a0dd2-130">Обеспечивает защиту мобильных приложений для телефонов и планшетные ПК</span><span class="sxs-lookup"><span data-stu-id="a0dd2-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="a0dd2-131">Определение политики соответствия устройств</span><span class="sxs-lookup"><span data-stu-id="a0dd2-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="a0dd2-132">Одна политика для каждой платформы</span><span class="sxs-lookup"><span data-stu-id="a0dd2-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="a0dd2-133">Требовать спецификации ПК</span><span class="sxs-lookup"><span data-stu-id="a0dd2-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="a0dd2-134">Обеспечивает управление Intune ПК</span><span class="sxs-lookup"><span data-stu-id="a0dd2-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="a0dd2-135">**Конфиденциальный**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-135">**Sensitive**</span></span>|[<span data-ttu-id="a0dd2-136">После входа в риска *низкий*, *Средний* или *высокий* требуют многофакторной проверкой Подлинности</span><span class="sxs-lookup"><span data-stu-id="a0dd2-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="a0dd2-137">Требовать спецификации ПК *и* мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="a0dd2-138">Обеспечивает управление Intune для и телефона/планшетные ПК</span><span class="sxs-lookup"><span data-stu-id="a0dd2-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="a0dd2-139">**Строго регулируемый уровень**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-139">**Highly regulated**</span></span>|[<span data-ttu-id="a0dd2-140">*Всегда* требовать многофакторной проверкой Подлинности</span><span class="sxs-lookup"><span data-stu-id="a0dd2-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="a0dd2-141">Назначение политик для пользователей</span><span class="sxs-lookup"><span data-stu-id="a0dd2-141">Assigning policies to users</span></span>
<span data-ttu-id="a0dd2-p105">Прежде чем настраивать политики, определяют группы Azure AD, используемой для каждого уровня защиты. Как правило базового защиты применяется ко всем пользователям в организации. Пользователь, который включен для базовой и защите конфиденциальных будут иметь все политики базового применены, а также конфиденциальных политик. Защита накопительным и наиболее строгими политикой.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="a0dd2-p106">Рекомендуется создать группу Azure AD для исключения условного доступа. Добавление этой группы на все правила условного доступа в разделе «Исключить». Это позволяет метод для обеспечения доступа к пользователю во время устранения неполадок access. Рекомендуется в качестве временное решение. Отслеживайте этой группы для изменения и убедитесь, что группа исключения используется только правильно.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="a0dd2-151">Ниже приведен пример назначение пользователя и исключений.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![Назначение пользователя пример и исключения для правил многофакторной проверкой Подлинности](../images/identity-access-policies-assignment.png)

<span data-ttu-id="a0dd2-p107">На рисунке «верхней секретный X группе проекта» назначается политику условного доступа, который требует многофакторной проверкой Подлинности *всегда*. Быть разумное при применении более высокий уровень защиты пользователей. Участники этой группы проекта должны предоставляют следующие способы проверки подлинности при каждом входе в систему, даже в том случае, если они могут не видеть сильно регулируемого содержимого.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="a0dd2-p108">Все группы Azure AD, создаваемого в рамках этих рекомендаций по использованию должен быть создан как группы Office 365. Это особенно важно для развертывания защиты информации Azure (AIP), когда защита документов в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Снимок экрана для создания группы Office 365](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="a0dd2-159">Требовать многофакторной проверкой Подлинности на основании входа риска</span><span class="sxs-lookup"><span data-stu-id="a0dd2-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="a0dd2-p109">Перед требованием многофакторной проверкой Подлинности, используйте политику регистрации многофакторной проверкой Подлинности удостоверения защиты для регистрации пользователей для многофакторной проверкой Подлинности. После регистрации пользователей, вы можете принудительно многофакторной проверкой Подлинности для входа. [Предварительные работы](identity-access-prerequisites.md) включает в себя регистрация всем пользователям с многофакторной проверкой Подлинности.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="a0dd2-163">Чтобы создать политику условного доступа, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="a0dd2-p110">Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a0dd2-166">В меню слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a0dd2-167">В разделе **Безопасность** выберите **Условный доступ**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a0dd2-168">Выберите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-168">Choose **New policy**.</span></span>

![Базовая политика условного доступа](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="a0dd2-170">Следующих таблицах описаны параметры политики условного доступа для реализации для этой политики.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="a0dd2-171">**Назначения**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-171">**Assignments**</span></span>

|<span data-ttu-id="a0dd2-172">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-172">Type</span></span>|<span data-ttu-id="a0dd2-173">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-173">Properties</span></span>|<span data-ttu-id="a0dd2-174">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-174">Values</span></span>|<span data-ttu-id="a0dd2-175">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-176">Пользователи или группы</span><span class="sxs-lookup"><span data-stu-id="a0dd2-176">Users and groups</span></span>|<span data-ttu-id="a0dd2-177">Включить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-177">Include</span></span>|<span data-ttu-id="a0dd2-178">Выберите пользователей и группы — выберите определенную группу безопасности, содержащую целевых пользователей</span><span class="sxs-lookup"><span data-stu-id="a0dd2-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="a0dd2-179">Следует начать с группы безопасности, в которую входят пользователи пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="a0dd2-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="a0dd2-180">Исключить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-180">Exclude</span></span>|<span data-ttu-id="a0dd2-181">Исключение группы безопасности, учетных записей служб (удостоверений приложений)</span><span class="sxs-lookup"><span data-stu-id="a0dd2-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="a0dd2-182">Членство в изменено на основе временные по необходимости</span><span class="sxs-lookup"><span data-stu-id="a0dd2-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="a0dd2-183">Облачные приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-183">Cloud apps</span></span>|<span data-ttu-id="a0dd2-184">Включить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-184">Include</span></span>|<span data-ttu-id="a0dd2-p111">Выберите приложения, правила для применения к. Например выберите Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="a0dd2-187">Условия</span><span class="sxs-lookup"><span data-stu-id="a0dd2-187">Conditions</span></span>|<span data-ttu-id="a0dd2-188">Настроено</span><span class="sxs-lookup"><span data-stu-id="a0dd2-188">Configured</span></span>|<span data-ttu-id="a0dd2-189">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-189">Yes</span></span>|<span data-ttu-id="a0dd2-190">Выполните настройку в соответствии с вашей средой и потребностями</span><span class="sxs-lookup"><span data-stu-id="a0dd2-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="a0dd2-191">Риск при входе</span><span class="sxs-lookup"><span data-stu-id="a0dd2-191">Sign-in risk</span></span>|<span data-ttu-id="a0dd2-192">Уровень риска</span><span class="sxs-lookup"><span data-stu-id="a0dd2-192">Risk level</span></span>||<span data-ttu-id="a0dd2-193">Просмотрите руководства в следующей таблице</span><span class="sxs-lookup"><span data-stu-id="a0dd2-193">See the guidance in the following table</span></span>|

<span data-ttu-id="a0dd2-194">**Риск при входе**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-194">**Sign-in risk**</span></span>

<span data-ttu-id="a0dd2-195">Примените параметры на основании уровень защиты, который вы используете.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="a0dd2-196">Свойство</span><span class="sxs-lookup"><span data-stu-id="a0dd2-196">Property</span></span>|<span data-ttu-id="a0dd2-197">Уровень защиты</span><span class="sxs-lookup"><span data-stu-id="a0dd2-197">Level of protection</span></span>|<span data-ttu-id="a0dd2-198">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-198">Values</span></span>|<span data-ttu-id="a0dd2-199">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-200">Уровень риска</span><span class="sxs-lookup"><span data-stu-id="a0dd2-200">Risk level</span></span>|<span data-ttu-id="a0dd2-201">Базовый уровень</span><span class="sxs-lookup"><span data-stu-id="a0dd2-201">Baseline</span></span>|<span data-ttu-id="a0dd2-202">Высокий, средний</span><span class="sxs-lookup"><span data-stu-id="a0dd2-202">High, medium</span></span>|<span data-ttu-id="a0dd2-203">Выберите оба варианта</span><span class="sxs-lookup"><span data-stu-id="a0dd2-203">Check both</span></span>|
| |<span data-ttu-id="a0dd2-204">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="a0dd2-204">Sensitive</span></span>|<span data-ttu-id="a0dd2-205">High, medium, низкой</span><span class="sxs-lookup"><span data-stu-id="a0dd2-205">High, medium, low</span></span>|<span data-ttu-id="a0dd2-206">Выберите все три варианта</span><span class="sxs-lookup"><span data-stu-id="a0dd2-206">Check all three</span></span>|
| |<span data-ttu-id="a0dd2-207">Строго регулируемый уровень</span><span class="sxs-lookup"><span data-stu-id="a0dd2-207">Highly regulated</span></span>| |<span data-ttu-id="a0dd2-208">Не устанавливайте флажок всегда внедрение многофакторной проверкой Подлинности все параметры</span><span class="sxs-lookup"><span data-stu-id="a0dd2-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="a0dd2-209">**Средства управления доступом**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-209">**Access controls**</span></span>

|<span data-ttu-id="a0dd2-210">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-210">Type</span></span>|<span data-ttu-id="a0dd2-211">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-211">Properties</span></span>|<span data-ttu-id="a0dd2-212">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-212">Values</span></span>|<span data-ttu-id="a0dd2-213">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-214">Предоставить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-214">Grant</span></span>|<span data-ttu-id="a0dd2-215">Предоставление доступа</span><span class="sxs-lookup"><span data-stu-id="a0dd2-215">Grant access</span></span>|<span data-ttu-id="a0dd2-216">True</span><span class="sxs-lookup"><span data-stu-id="a0dd2-216">True</span></span>|<span data-ttu-id="a0dd2-217">Выбрано</span><span class="sxs-lookup"><span data-stu-id="a0dd2-217">Selected</span></span>|
||<span data-ttu-id="a0dd2-218">Требовать многофакторную идентификацию</span><span class="sxs-lookup"><span data-stu-id="a0dd2-218">Require MFA</span></span>|<span data-ttu-id="a0dd2-219">True</span><span class="sxs-lookup"><span data-stu-id="a0dd2-219">True</span></span>|<span data-ttu-id="a0dd2-220">Check</span><span class="sxs-lookup"><span data-stu-id="a0dd2-220">Check</span></span>|
||<span data-ttu-id="a0dd2-221">Требовать устройства будут отмечены как соответствующая требованиям</span><span class="sxs-lookup"><span data-stu-id="a0dd2-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="a0dd2-222">False</span><span class="sxs-lookup"><span data-stu-id="a0dd2-222">False</span></span>||
||<span data-ttu-id="a0dd2-223">Требовать гибридного Azure присоединился к AD устройства</span><span class="sxs-lookup"><span data-stu-id="a0dd2-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="a0dd2-224">False</span><span class="sxs-lookup"><span data-stu-id="a0dd2-224">False</span></span>||
||<span data-ttu-id="a0dd2-225">Требовать утвержденных клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-225">Require approved client app</span></span>|<span data-ttu-id="a0dd2-226">False</span><span class="sxs-lookup"><span data-stu-id="a0dd2-226">False</span></span>||
||<span data-ttu-id="a0dd2-227">Требовать все выбранные средства управления</span><span class="sxs-lookup"><span data-stu-id="a0dd2-227">Require all the selected controls</span></span>|<span data-ttu-id="a0dd2-228">True</span><span class="sxs-lookup"><span data-stu-id="a0dd2-228">True</span></span>|<span data-ttu-id="a0dd2-229">Выбрано</span><span class="sxs-lookup"><span data-stu-id="a0dd2-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="a0dd2-p112">Убедитесь, что этот параметр включен, выбрав **на**. Также рекомендуется использовать средство [что делать, если](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) для проверки политики.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p112">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="a0dd2-232">Блокировать клиенты, не поддерживающие современных проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a0dd2-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="a0dd2-p113">Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a0dd2-235">В меню слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a0dd2-236">В разделе **Безопасность** выберите **Условный доступ**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a0dd2-237">Выберите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-237">Choose **New policy**.</span></span>

<span data-ttu-id="a0dd2-238">Следующих таблицах описаны параметры политики условного доступа для реализации для этой политики.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="a0dd2-239">**Назначения**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-239">**Assignments**</span></span>

|<span data-ttu-id="a0dd2-240">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-240">Type</span></span>|<span data-ttu-id="a0dd2-241">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-241">Properties</span></span>|<span data-ttu-id="a0dd2-242">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-242">Values</span></span>|<span data-ttu-id="a0dd2-243">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-244">Пользователи или группы</span><span class="sxs-lookup"><span data-stu-id="a0dd2-244">Users and groups</span></span>|<span data-ttu-id="a0dd2-245">Включить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-245">Include</span></span>|<span data-ttu-id="a0dd2-246">Выберите пользователей и группы — выберите определенную группу безопасности, содержащую целевых пользователей</span><span class="sxs-lookup"><span data-stu-id="a0dd2-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="a0dd2-247">Следует начать с группы безопасности, в которую входят пользователи пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="a0dd2-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="a0dd2-248">Исключить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-248">Exclude</span></span>|<span data-ttu-id="a0dd2-249">Исключение группы безопасности, учетных записей служб (удостоверений приложений)</span><span class="sxs-lookup"><span data-stu-id="a0dd2-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="a0dd2-250">Изменение членства по мере необходимости на временной основе</span><span class="sxs-lookup"><span data-stu-id="a0dd2-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="a0dd2-251">Облачные приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-251">Cloud apps</span></span>|<span data-ttu-id="a0dd2-252">Включить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-252">Include</span></span>|<span data-ttu-id="a0dd2-p114">Выберите приложения, правила для применения к. Например выберите Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="a0dd2-255">Условия</span><span class="sxs-lookup"><span data-stu-id="a0dd2-255">Conditions</span></span>|<span data-ttu-id="a0dd2-256">Настроено</span><span class="sxs-lookup"><span data-stu-id="a0dd2-256">Configured</span></span>|<span data-ttu-id="a0dd2-257">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-257">Yes</span></span>|<span data-ttu-id="a0dd2-258">Настройка клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-258">Configure Client apps</span></span>|
|<span data-ttu-id="a0dd2-259">Клиентские приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-259">Client apps</span></span>|<span data-ttu-id="a0dd2-260">Настроено</span><span class="sxs-lookup"><span data-stu-id="a0dd2-260">Configured</span></span>|<span data-ttu-id="a0dd2-261">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-261">Yes</span></span>|<span data-ttu-id="a0dd2-262">Мобильных приложений и настольных клиентов, других клиентских программах (оба флажка)</span><span class="sxs-lookup"><span data-stu-id="a0dd2-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="a0dd2-263">**Средства управления доступом**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-263">**Access controls**</span></span>

|<span data-ttu-id="a0dd2-264">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-264">Type</span></span>|<span data-ttu-id="a0dd2-265">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-265">Properties</span></span>|<span data-ttu-id="a0dd2-266">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-266">Values</span></span>|<span data-ttu-id="a0dd2-267">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-268">Предоставить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-268">Grant</span></span>|<span data-ttu-id="a0dd2-269">Заблокировать доступ</span><span class="sxs-lookup"><span data-stu-id="a0dd2-269">Block access</span></span>|<span data-ttu-id="a0dd2-270">True</span><span class="sxs-lookup"><span data-stu-id="a0dd2-270">True</span></span>|<span data-ttu-id="a0dd2-271">Выбрано</span><span class="sxs-lookup"><span data-stu-id="a0dd2-271">Selected</span></span>|
||<span data-ttu-id="a0dd2-272">Требовать многофакторную идентификацию</span><span class="sxs-lookup"><span data-stu-id="a0dd2-272">Require MFA</span></span>|<span data-ttu-id="a0dd2-273">False</span><span class="sxs-lookup"><span data-stu-id="a0dd2-273">False</span></span>||
||<span data-ttu-id="a0dd2-274">Требовать устройства будут отмечены как соответствующая требованиям</span><span class="sxs-lookup"><span data-stu-id="a0dd2-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="a0dd2-275">False</span><span class="sxs-lookup"><span data-stu-id="a0dd2-275">False</span></span>||
||<span data-ttu-id="a0dd2-276">Требовать гибридного Azure присоединился к AD устройства</span><span class="sxs-lookup"><span data-stu-id="a0dd2-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="a0dd2-277">False</span><span class="sxs-lookup"><span data-stu-id="a0dd2-277">False</span></span>||
||<span data-ttu-id="a0dd2-278">Требовать утвержденных клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-278">Require approved client app</span></span>|<span data-ttu-id="a0dd2-279">False</span><span class="sxs-lookup"><span data-stu-id="a0dd2-279">False</span></span>||
||<span data-ttu-id="a0dd2-280">Требовать все выбранные средства управления</span><span class="sxs-lookup"><span data-stu-id="a0dd2-280">Require all the selected controls</span></span>|<span data-ttu-id="a0dd2-281">True</span><span class="sxs-lookup"><span data-stu-id="a0dd2-281">True</span></span>|<span data-ttu-id="a0dd2-282">Выбрано</span><span class="sxs-lookup"><span data-stu-id="a0dd2-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="a0dd2-p115">Убедитесь, что этот параметр включен, выбрав **на**. Также рекомендуется использовать средство [что делать, если](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) для проверки политики.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p115">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="a0dd2-285">Пользователи высокого риска смену пароля</span><span class="sxs-lookup"><span data-stu-id="a0dd2-285">High risk users must change password</span></span>
<span data-ttu-id="a0dd2-286">Убедитесь, что все высокого риска пользователей атаке учетные записи, принудительно выполнить смены пароля при вход в систему, необходимо установить следующие политики.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="a0dd2-287">Выполните вход в систему [портал Microsoft Azure (http://portal.azure.com) ](http://portal.azure.com/) с свои учетные данные администратора, а затем перейдите к **Azure AD защиту > политики пользователя риска**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="a0dd2-288">**Назначения**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-288">**Assignments**</span></span>

|<span data-ttu-id="a0dd2-289">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-289">Type</span></span>|<span data-ttu-id="a0dd2-290">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-290">Properties</span></span>|<span data-ttu-id="a0dd2-291">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-291">Values</span></span>|<span data-ttu-id="a0dd2-292">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-293">Users</span><span class="sxs-lookup"><span data-stu-id="a0dd2-293">Users</span></span>|<span data-ttu-id="a0dd2-294">Включить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-294">Include</span></span>|<span data-ttu-id="a0dd2-295">Все пользователи</span><span class="sxs-lookup"><span data-stu-id="a0dd2-295">All users</span></span>|<span data-ttu-id="a0dd2-296">Выбрано</span><span class="sxs-lookup"><span data-stu-id="a0dd2-296">Selected</span></span>|
||<span data-ttu-id="a0dd2-297">Исключить</span><span class="sxs-lookup"><span data-stu-id="a0dd2-297">Exclude</span></span>|<span data-ttu-id="a0dd2-298">Нет</span><span class="sxs-lookup"><span data-stu-id="a0dd2-298">None</span></span>||
|<span data-ttu-id="a0dd2-299">Условия</span><span class="sxs-lookup"><span data-stu-id="a0dd2-299">Conditions</span></span>|<span data-ttu-id="a0dd2-300">Риск пользователя</span><span class="sxs-lookup"><span data-stu-id="a0dd2-300">User risk</span></span>|<span data-ttu-id="a0dd2-301">Высокий</span><span class="sxs-lookup"><span data-stu-id="a0dd2-301">High</span></span>|<span data-ttu-id="a0dd2-302">Выбрано</span><span class="sxs-lookup"><span data-stu-id="a0dd2-302">Selected</span></span>|

<span data-ttu-id="a0dd2-303">**Элементы управления**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-303">**Controls**</span></span>

| <span data-ttu-id="a0dd2-304">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-304">Type</span></span> | <span data-ttu-id="a0dd2-305">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-305">Properties</span></span> | <span data-ttu-id="a0dd2-306">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-306">Values</span></span>                  | <span data-ttu-id="a0dd2-307">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="a0dd2-308">Доступ</span><span class="sxs-lookup"><span data-stu-id="a0dd2-308">Access</span></span>     | <span data-ttu-id="a0dd2-309">Разрешить доступ</span><span class="sxs-lookup"><span data-stu-id="a0dd2-309">Allow access</span></span>            | <span data-ttu-id="a0dd2-310">True</span><span class="sxs-lookup"><span data-stu-id="a0dd2-310">True</span></span>  |
|      | <span data-ttu-id="a0dd2-311">Доступ</span><span class="sxs-lookup"><span data-stu-id="a0dd2-311">Access</span></span>     | <span data-ttu-id="a0dd2-312">Требовать смену пароля</span><span class="sxs-lookup"><span data-stu-id="a0dd2-312">Require password change</span></span> | <span data-ttu-id="a0dd2-313">True</span><span class="sxs-lookup"><span data-stu-id="a0dd2-313">True</span></span>  |

<span data-ttu-id="a0dd2-314">**Проверки:** неприменимо</span><span class="sxs-lookup"><span data-stu-id="a0dd2-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="a0dd2-p116">Убедитесь, что этот параметр включен, выбрав **на**. Также рекомендуется использовать средство [что делать, если](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) для тестирования политики</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p116">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="a0dd2-317">Определение политик защиты от приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-317">Define app protection policies</span></span>
<span data-ttu-id="a0dd2-p117">Политики в отношении защиты приложений определить, какие приложения разрешено и действия, которые необходимо выполнить с данными вашей организации. Создание приложения Intune политик защиты от Azure портала.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p117">App protection policies define which apps are allowed and the actions they can take with your organization's data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="a0dd2-320">Создайте политику для каждой платформы.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="a0dd2-321">операций ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="a0dd2-321">iOS</span></span>
- <span data-ttu-id="a0dd2-322">Android,</span><span class="sxs-lookup"><span data-stu-id="a0dd2-322">Android</span></span>
- <span data-ttu-id="a0dd2-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a0dd2-323">Windows 10</span></span>

<span data-ttu-id="a0dd2-p118">Чтобы создать новую политику защиты приложения, выполните вход в портал Microsoft Azure с помощью учетных данных администратора и перейдите на **мобильных приложениях > политики в отношении защиты приложений**. Последовательно выберите пункты **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Choose **Add a policy**.</span></span>

<span data-ttu-id="a0dd2-p119">Существует несколько различается защиты приложения параметры политики между iOS и Android (en). Ниже политики — это специально для Android. Используйте это в качестве руководства для других политик.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="a0dd2-329">Рекомендуемые список приложений включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="a0dd2-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="a0dd2-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a0dd2-330">PowerPoint</span></span>
- <span data-ttu-id="a0dd2-331">Excel</span><span class="sxs-lookup"><span data-stu-id="a0dd2-331">Excel</span></span>
- <span data-ttu-id="a0dd2-332">Word</span><span class="sxs-lookup"><span data-stu-id="a0dd2-332">Word</span></span>
- <span data-ttu-id="a0dd2-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a0dd2-333">Microsoft Teams</span></span>
- <span data-ttu-id="a0dd2-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="a0dd2-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="a0dd2-335">Средство просмотра Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="a0dd2-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="a0dd2-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a0dd2-336">OneDrive</span></span>
- <span data-ttu-id="a0dd2-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="a0dd2-337">OneNote</span></span>
- <span data-ttu-id="a0dd2-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="a0dd2-338">Outlook</span></span>

<span data-ttu-id="a0dd2-339">В следующих таблицах описываются рекомендуемые параметры:</span><span class="sxs-lookup"><span data-stu-id="a0dd2-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="a0dd2-340">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-340">Type</span></span>|<span data-ttu-id="a0dd2-341">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-341">Properties</span></span>|<span data-ttu-id="a0dd2-342">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-342">Values</span></span>|<span data-ttu-id="a0dd2-343">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-344">Перемещение данных</span><span class="sxs-lookup"><span data-stu-id="a0dd2-344">Data relocation</span></span>|<span data-ttu-id="a0dd2-345">Запретить резервное копирование на Android</span><span class="sxs-lookup"><span data-stu-id="a0dd2-345">Prevent Android backup</span></span>|<span data-ttu-id="a0dd2-346">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-346">Yes</span></span>|<span data-ttu-id="a0dd2-347">В iOS это касается iTunes и iCloud</span><span class="sxs-lookup"><span data-stu-id="a0dd2-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="a0dd2-348">Разрешить приложению передавать данные в другие приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="a0dd2-349">Приложения, управляемые политикой</span><span class="sxs-lookup"><span data-stu-id="a0dd2-349">Policy managed apps</span></span>||
||<span data-ttu-id="a0dd2-350">Разрешить приложению получать данные от других приложений</span><span class="sxs-lookup"><span data-stu-id="a0dd2-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="a0dd2-351">Приложения, управляемые политикой</span><span class="sxs-lookup"><span data-stu-id="a0dd2-351">Policy managed apps</span></span>||
||<span data-ttu-id="a0dd2-352">Запрет команды "Сохранить как"</span><span class="sxs-lookup"><span data-stu-id="a0dd2-352">Prevent "Save As"</span></span>|<span data-ttu-id="a0dd2-353">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-353">Yes</span></span>||
||<span data-ttu-id="a0dd2-354">Выбор служб хранения данных, в которые могут быть сохранены данные организации</span><span class="sxs-lookup"><span data-stu-id="a0dd2-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="a0dd2-355">OneDrive для бизнеса в SharePoint</span><span class="sxs-lookup"><span data-stu-id="a0dd2-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="a0dd2-356">Ограничить вырезание, копирование и вставку данных между приложениями</span><span class="sxs-lookup"><span data-stu-id="a0dd2-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="a0dd2-357">Политики управляемых приложений с помощью вставки в</span><span class="sxs-lookup"><span data-stu-id="a0dd2-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="a0dd2-358">Ограничить веб-контент, отображаемый в Managed Browser</span><span class="sxs-lookup"><span data-stu-id="a0dd2-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="a0dd2-359">Нет</span><span class="sxs-lookup"><span data-stu-id="a0dd2-359">No</span></span>||
||<span data-ttu-id="a0dd2-360">Шифрование данных приложения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-360">Encrypt app data</span></span>|<span data-ttu-id="a0dd2-361">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-361">Yes</span></span>|<span data-ttu-id="a0dd2-362">В iOS выберите параметр "Когда устройство заблокировано"</span><span class="sxs-lookup"><span data-stu-id="a0dd2-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="a0dd2-363">Отключать шифрование приложения при включении устройства</span><span class="sxs-lookup"><span data-stu-id="a0dd2-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="a0dd2-364">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-364">Yes</span></span>|<span data-ttu-id="a0dd2-365">Отключите этот параметр, чтобы избежать двойного шифрования</span><span class="sxs-lookup"><span data-stu-id="a0dd2-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="a0dd2-366">Отключить синхронизацию контактов</span><span class="sxs-lookup"><span data-stu-id="a0dd2-366">Disable contacts sync</span></span>|<span data-ttu-id="a0dd2-367">Нет</span><span class="sxs-lookup"><span data-stu-id="a0dd2-367">No</span></span>||
||<span data-ttu-id="a0dd2-368">Отключение печати</span><span class="sxs-lookup"><span data-stu-id="a0dd2-368">Disable printing</span></span>|<span data-ttu-id="a0dd2-369">Нет</span><span class="sxs-lookup"><span data-stu-id="a0dd2-369">No</span></span>||
|<span data-ttu-id="a0dd2-370">Доступ</span><span class="sxs-lookup"><span data-stu-id="a0dd2-370">Access</span></span>|<span data-ttu-id="a0dd2-371">Требовать ПИН-код для доступа</span><span class="sxs-lookup"><span data-stu-id="a0dd2-371">Require PIN for access</span></span>|<span data-ttu-id="a0dd2-372">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-372">Yes</span></span>||
||<span data-ttu-id="a0dd2-373">Выберите тип</span><span class="sxs-lookup"><span data-stu-id="a0dd2-373">Select Type</span></span>|<span data-ttu-id="a0dd2-374">Числовой</span><span class="sxs-lookup"><span data-stu-id="a0dd2-374">Numeric</span></span>||
||<span data-ttu-id="a0dd2-375">Разрешить простой ПИН-код</span><span class="sxs-lookup"><span data-stu-id="a0dd2-375">Allow simple PIN</span></span>|<span data-ttu-id="a0dd2-376">Нет</span><span class="sxs-lookup"><span data-stu-id="a0dd2-376">No</span></span>||
||<span data-ttu-id="a0dd2-377">Длина ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="a0dd2-377">PIN length</span></span>|<span data-ttu-id="a0dd2-378">6</span><span class="sxs-lookup"><span data-stu-id="a0dd2-378">6</span></span>||
||<span data-ttu-id="a0dd2-379">Разрешить вход с использованием отпечатков пальцев вместо ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="a0dd2-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="a0dd2-380">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-380">Yes</span></span>||
||<span data-ttu-id="a0dd2-381">Отключить приложение ПИН-код при управляемых устройств ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="a0dd2-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="a0dd2-382">Да</span><span class="sxs-lookup"><span data-stu-id="a0dd2-382">Yes</span></span>||
||<span data-ttu-id="a0dd2-383">Требуются учетные данные организации для access</span><span class="sxs-lookup"><span data-stu-id="a0dd2-383">Require corporate credentials for access</span></span>|<span data-ttu-id="a0dd2-384">Нет</span><span class="sxs-lookup"><span data-stu-id="a0dd2-384">No</span></span>||
||<span data-ttu-id="a0dd2-385">Перепроверять требования к доступу через (мин)</span><span class="sxs-lookup"><span data-stu-id="a0dd2-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="a0dd2-386">30</span><span class="sxs-lookup"><span data-stu-id="a0dd2-386">30</span></span>||
||<span data-ttu-id="a0dd2-387">Блокировать снимки экрана и Android Assistant</span><span class="sxs-lookup"><span data-stu-id="a0dd2-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="a0dd2-388">Нет</span><span class="sxs-lookup"><span data-stu-id="a0dd2-388">No</span></span>|<span data-ttu-id="a0dd2-389">В iOS этот параметр недоступен</span><span class="sxs-lookup"><span data-stu-id="a0dd2-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="a0dd2-390">Требования к безопасности входа</span><span class="sxs-lookup"><span data-stu-id="a0dd2-390">Sign-in security requirements</span></span>|<span data-ttu-id="a0dd2-391">ПИН-код максимальное число попыток</span><span class="sxs-lookup"><span data-stu-id="a0dd2-391">Max PIN attempts</span></span>|<span data-ttu-id="a0dd2-392">5</span><span class="sxs-lookup"><span data-stu-id="a0dd2-392">5</span></span>|<span data-ttu-id="a0dd2-393">Сброс ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="a0dd2-393">Reset Pin</span></span>|
||<span data-ttu-id="a0dd2-394">Период отсрочки в автономном режиме</span><span class="sxs-lookup"><span data-stu-id="a0dd2-394">Offline grace period</span></span>|<span data-ttu-id="a0dd2-395">720</span><span class="sxs-lookup"><span data-stu-id="a0dd2-395">720</span></span>|<span data-ttu-id="a0dd2-396">Заблокировать доступ</span><span class="sxs-lookup"><span data-stu-id="a0dd2-396">Block access</span></span>|
||<span data-ttu-id="a0dd2-397">Интервал в автономном режиме до очистки данных приложения (дн.)</span><span class="sxs-lookup"><span data-stu-id="a0dd2-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="a0dd2-398">90</span><span class="sxs-lookup"><span data-stu-id="a0dd2-398">90</span></span>|<span data-ttu-id="a0dd2-399">Очистка данных</span><span class="sxs-lookup"><span data-stu-id="a0dd2-399">Wipe data</span></span>|
||<span data-ttu-id="a0dd2-400">Корневой каталог/Jailbroken устройств</span><span class="sxs-lookup"><span data-stu-id="a0dd2-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="a0dd2-401">Очистка данных</span><span class="sxs-lookup"><span data-stu-id="a0dd2-401">Wipe data</span></span>|

<span data-ttu-id="a0dd2-p120">Закончив настройку, не забудьте выберите пункт «Создать». Повторите действия, описанные выше и замените выбранной платформы (раскрывающийся список) операций ввода-вывода. При этом создается два политики в отношении приложений, поэтому после создания политики, затем назначать группы к политике и его развертывание.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p120">When complete, remember to select "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="a0dd2-405">Чтобы изменить политики и назначения этих политик для пользователей, узнайте, [как для создания и назначения политики в отношении защиты приложений](https://docs.microsoft.com/intune/app-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="a0dd2-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="a0dd2-406">Требовать одобренных приложений</span><span class="sxs-lookup"><span data-stu-id="a0dd2-406">Require approved apps</span></span>
<span data-ttu-id="a0dd2-407">Чтобы сделать обязательным наличие одобренных приложений:</span><span class="sxs-lookup"><span data-stu-id="a0dd2-407">To require approved apps:</span></span>

1. <span data-ttu-id="a0dd2-p121">Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a0dd2-410">В меню слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a0dd2-411">В разделе **Безопасность** выберите **Условный доступ**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a0dd2-412">Выберите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="a0dd2-413">Введите имя политики, а затем выберите **Пользователей и группы**, к которым нужно ее применить.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="a0dd2-414">Выберите **Облачные приложения**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="a0dd2-p122">Выберите команду **выбрать приложения**, выберите нужный приложений в списке **облачных приложений** . Например выберите Office 365 Exchange Online. Нажмите кнопку **выбрать** и **сделано**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="a0dd2-418">Выберите **Предоставление** в разделе **Элементы управления доступом**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="a0dd2-p123">Нажмите кнопку **предоставить доступ**, выберите **Требовать утверждения клиентского приложения**. Для нескольких элементов управления выберите **Требовать выбранные элементы управления**, а затем выберите команду **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p123">Choose **Grant access**, select **Require approved client app**. For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="a0dd2-421">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-421">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="a0dd2-422">Определение политики соответствия устройств</span><span class="sxs-lookup"><span data-stu-id="a0dd2-422">Define device-compliance policies</span></span>

<span data-ttu-id="a0dd2-p124">Политики соответствия устройства определить требования, устройств, должна придерживаться пометить следующим требованиям. Создание политики соответствия из портала Azure Intune устройства.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p124">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="a0dd2-425">Создайте политику для каждой платформы.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="a0dd2-426">Android</span><span class="sxs-lookup"><span data-stu-id="a0dd2-426">Android</span></span>
- <span data-ttu-id="a0dd2-427">Android enterprise</span><span class="sxs-lookup"><span data-stu-id="a0dd2-427">Android enterprise</span></span>
- <span data-ttu-id="a0dd2-428">операций ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="a0dd2-428">iOS</span></span>
- <span data-ttu-id="a0dd2-429">macOS</span><span class="sxs-lookup"><span data-stu-id="a0dd2-429">macOS</span></span>
- <span data-ttu-id="a0dd2-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="a0dd2-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="a0dd2-431">Windows 8.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="a0dd2-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="a0dd2-432">Windows 10 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="a0dd2-432">Windows 10 and later</span></span>

<span data-ttu-id="a0dd2-p125">Для создания политики соответствия устройства, войдите портал Microsoft Azure с помощью учетных данных администратора и перейдите на **Intune > соответствия устройства**. Выберите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Select **Create policy**.</span></span>

<span data-ttu-id="a0dd2-435">Для Windows 10 рекомендуются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="a0dd2-436">**Устройство работоспособности: правила оценки службы аттестации работоспособности Windows**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="a0dd2-437">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-437">Properties</span></span>|<span data-ttu-id="a0dd2-438">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-438">Values</span></span>|<span data-ttu-id="a0dd2-439">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-440">Необходимо использовать BitLocker</span><span class="sxs-lookup"><span data-stu-id="a0dd2-440">Require BitLocker</span></span>|<span data-ttu-id="a0dd2-441">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-441">Require</span></span>||
|<span data-ttu-id="a0dd2-442">Требовать безопасного загрузки включить на устройстве</span><span class="sxs-lookup"><span data-stu-id="a0dd2-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="a0dd2-443">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-443">Require</span></span>||
|<span data-ttu-id="a0dd2-444">Требовать целостность кода</span><span class="sxs-lookup"><span data-stu-id="a0dd2-444">Require code integrity</span></span>|<span data-ttu-id="a0dd2-445">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-445">Require</span></span>||


<span data-ttu-id="a0dd2-446">**Свойства устройства**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-446">**Device properties**</span></span>

|<span data-ttu-id="a0dd2-447">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-447">Type</span></span>|<span data-ttu-id="a0dd2-448">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-448">Properties</span></span>|<span data-ttu-id="a0dd2-449">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-449">Values</span></span>|<span data-ttu-id="a0dd2-450">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-451">Версия операционной системы</span><span class="sxs-lookup"><span data-stu-id="a0dd2-451">Operating system version</span></span>|<span data-ttu-id="a0dd2-452">all</span><span class="sxs-lookup"><span data-stu-id="a0dd2-452">All</span></span>|<span data-ttu-id="a0dd2-453">Не настроено</span><span class="sxs-lookup"><span data-stu-id="a0dd2-453">Not configured</span></span>||

<span data-ttu-id="a0dd2-p126">Для всех развернуты выше политики следует учитывать они должны предназначены для группы пользователей. Это можно сделать, создав политику (при сохранении) или более поздней версии, выбрав **Управление развертывания** в разделе **Политика** (же уровне, что Add).</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="a0dd2-456">**Безопасность системы**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-456">**System security**</span></span>

|<span data-ttu-id="a0dd2-457">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-457">Type</span></span>|<span data-ttu-id="a0dd2-458">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-458">Properties</span></span>|<span data-ttu-id="a0dd2-459">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-459">Values</span></span>|<span data-ttu-id="a0dd2-460">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-461">Password</span><span class="sxs-lookup"><span data-stu-id="a0dd2-461">Password</span></span>|<span data-ttu-id="a0dd2-462">Требование ввести пароль для разблокировки мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="a0dd2-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="a0dd2-463">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-463">Require</span></span>||
||<span data-ttu-id="a0dd2-464">Простых паролей</span><span class="sxs-lookup"><span data-stu-id="a0dd2-464">Simple passwords</span></span>|<span data-ttu-id="a0dd2-465">Блок</span><span class="sxs-lookup"><span data-stu-id="a0dd2-465">Block</span></span>||
||<span data-ttu-id="a0dd2-466">Введите пароль</span><span class="sxs-lookup"><span data-stu-id="a0dd2-466">Password type</span></span>|<span data-ttu-id="a0dd2-467">Устройство по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a0dd2-467">Device default</span></span>||
||<span data-ttu-id="a0dd2-468">Минимальная длина пароля</span><span class="sxs-lookup"><span data-stu-id="a0dd2-468">Minimum password length</span></span>|<span data-ttu-id="a0dd2-469">6</span><span class="sxs-lookup"><span data-stu-id="a0dd2-469">6</span></span>||
||<span data-ttu-id="a0dd2-470">Максимальное число минут бездействия, прежде чем пароль</span><span class="sxs-lookup"><span data-stu-id="a0dd2-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="a0dd2-471">15 </span><span class="sxs-lookup"><span data-stu-id="a0dd2-471">15</span></span>|<span data-ttu-id="a0dd2-p127">Этот параметр поддерживается для Android версии 4.0 и более или НОКСА 4.0 и выше. Для операций ввода-вывода устройств поддерживается для iOS 8.0 и выше</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="a0dd2-474">Срок действия пароля (дней)</span><span class="sxs-lookup"><span data-stu-id="a0dd2-474">Password expiration (days)</span></span>|<span data-ttu-id="a0dd2-475">41</span><span class="sxs-lookup"><span data-stu-id="a0dd2-475">41</span></span>||
||<span data-ttu-id="a0dd2-476">Число предыдущих паролей для предотвращения повторного использования</span><span class="sxs-lookup"><span data-stu-id="a0dd2-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="a0dd2-477">5</span><span class="sxs-lookup"><span data-stu-id="a0dd2-477">5</span></span>||
||<span data-ttu-id="a0dd2-478">Требовать пароль при возврате устройства из состояния простоя (Mobile и Holographic)</span><span class="sxs-lookup"><span data-stu-id="a0dd2-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="a0dd2-479">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-479">Require</span></span>|<span data-ttu-id="a0dd2-480">Доступные для Windows 10 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="a0dd2-480">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="a0dd2-481">Шифрование</span><span class="sxs-lookup"><span data-stu-id="a0dd2-481">Encryption</span></span>|<span data-ttu-id="a0dd2-482">Шифрование хранения данных на устройстве</span><span class="sxs-lookup"><span data-stu-id="a0dd2-482">Encryption of data storage on device</span></span>|<span data-ttu-id="a0dd2-483">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-483">Require</span></span>||
|<span data-ttu-id="a0dd2-484">Безопасность устройств</span><span class="sxs-lookup"><span data-stu-id="a0dd2-484">Device Security</span></span>|<span data-ttu-id="a0dd2-485">Брандмауэр</span><span class="sxs-lookup"><span data-stu-id="a0dd2-485">Firewall</span></span>|<span data-ttu-id="a0dd2-486">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-486">Require</span></span>||
||<span data-ttu-id="a0dd2-487">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="a0dd2-487">Antivirus</span></span>|<span data-ttu-id="a0dd2-488">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-488">Require</span></span>||
||<span data-ttu-id="a0dd2-489">Антишпионское</span><span class="sxs-lookup"><span data-stu-id="a0dd2-489">Antispyware</span></span>|<span data-ttu-id="a0dd2-490">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-490">Require</span></span>|<span data-ttu-id="a0dd2-491">Этот параметр требуется решение по обеспечению защита от шпионского по зарегистрирован в центре обеспечения безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="a0dd2-491">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="a0dd2-492">Защитник</span><span class="sxs-lookup"><span data-stu-id="a0dd2-492">Defender</span></span>|<span data-ttu-id="a0dd2-493">Защитник Windows защиты от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="a0dd2-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="a0dd2-494">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-494">Require</span></span>||
||<span data-ttu-id="a0dd2-495">Минимальная версия Защитника Windows защиты от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="a0dd2-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="a0dd2-p128">Поддерживается только для настольных компьютеров Windows 10. Корпорация Майкрософт рекомендует версий не более 5 за из наиболее поздней версии</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="a0dd2-498">В актуальном состоянии подписи Защитник Windows защиты от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="a0dd2-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="a0dd2-499">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-499">Require</span></span>||
||<span data-ttu-id="a0dd2-500">"Защита в режиме реального времени"</span><span class="sxs-lookup"><span data-stu-id="a0dd2-500">Real-time protection</span></span>|<span data-ttu-id="a0dd2-501">Обязательность</span><span class="sxs-lookup"><span data-stu-id="a0dd2-501">Require</span></span>|<span data-ttu-id="a0dd2-502">Поддерживается только для настольных компьютеров Windows 10</span><span class="sxs-lookup"><span data-stu-id="a0dd2-502">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="a0dd2-503">**ATP в Защитнике Windows**</span><span class="sxs-lookup"><span data-stu-id="a0dd2-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="a0dd2-504">Type</span><span class="sxs-lookup"><span data-stu-id="a0dd2-504">Type</span></span>|<span data-ttu-id="a0dd2-505">Элемент Property</span><span class="sxs-lookup"><span data-stu-id="a0dd2-505">Properties</span></span>|<span data-ttu-id="a0dd2-506">Значения</span><span class="sxs-lookup"><span data-stu-id="a0dd2-506">Values</span></span>|<span data-ttu-id="a0dd2-507">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0dd2-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a0dd2-508">Правила защиты от угроз дополнительные Защитника Windows</span><span class="sxs-lookup"><span data-stu-id="a0dd2-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="a0dd2-509">Требовать устройства в или в разделе оценки риска компьютера</span><span class="sxs-lookup"><span data-stu-id="a0dd2-509">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="a0dd2-510">Средние</span><span class="sxs-lookup"><span data-stu-id="a0dd2-510">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="a0dd2-511">Требовать спецификации (но не соответствует спецификации телефоны и планшетные ПК)</span><span class="sxs-lookup"><span data-stu-id="a0dd2-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="a0dd2-p129">Перед добавлением политики требуется совместимый ПК, убедитесь, что регистрация устройств для управления в Intune. Прежде чем отправлять заявки на получение устройств в Intune Software assurance, устройство во временном пользовании целям пользователя рекомендуется использовать многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="a0dd2-514">Чтобы сделать обязательным наличие спецификации ПК:</span><span class="sxs-lookup"><span data-stu-id="a0dd2-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="a0dd2-p130">Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a0dd2-517">В меню слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a0dd2-518">В разделе **Безопасность** выберите **Условный доступ**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a0dd2-519">Выберите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="a0dd2-520">Введите имя политики, а затем выберите **Пользователей и группы**, к которым нужно ее применить.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="a0dd2-521">Выберите **Облачные приложения**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="a0dd2-p131">Выберите команду **выбрать приложения**, выберите нужный приложений в списке **облачных приложений** . Например выберите Office 365 Exchange Online. Нажмите кнопку **выбрать** и **сделано**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="a0dd2-p132">Чтобы сделать обязательным наличие спецификации, но не соответствует спецификации телефоны и планшетные ПК, выберите **условия** и **платформах устройств**. Выберите команду **выбрать платформах устройств** и выберите **Windows** и **macOS**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="a0dd2-527">Выберите **Предоставление** в разделе **Элементы управления доступом**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="a0dd2-p133">Нажмите кнопку **предоставить доступ**, выберите **Требовать устройство для помечен как совместимый с**. Для нескольких элементов управления выберите **Требовать все выбранные элементы управления**, а затем выберите команду **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p133">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="a0dd2-530">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-530">Choose **Create**.</span></span>

<span data-ttu-id="a0dd2-p134">Целью является требуют спецификации ПК *и* мобильных устройств, не устанавливайте платформ. Это обеспечивает соответствие требованиям для всех устройств.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="a0dd2-533">Требовать спецификации ПК *и* мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="a0dd2-534">Чтобы сделать обязательным наличие соответствия для всех устройств:</span><span class="sxs-lookup"><span data-stu-id="a0dd2-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="a0dd2-p135">Перейдите в [Azure портала](https://portal.azure.com)и выполнить вход. После того как вы успешно выполнили вход, вы изучите Azure панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a0dd2-537">В меню слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a0dd2-538">В разделе **Безопасность** выберите **Условный доступ**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a0dd2-539">Выберите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="a0dd2-540">Введите имя политики, а затем выберите **Пользователей и группы**, к которым нужно ее применить.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="a0dd2-541">Выберите **Облачные приложения**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="a0dd2-p136">Выберите команду **выбрать приложения**, выберите нужный приложений в списке **облачных приложений** . Например выберите Office 365 Exchange Online. Нажмите кнопку **выбрать** и **сделано**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="a0dd2-545">Выберите **Предоставление** в разделе **Элементы управления доступом**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="a0dd2-p137">Нажмите кнопку **предоставить доступ**, выберите **Требовать устройство для помечен как совместимый с**. Для нескольких элементов управления выберите **Требовать все выбранные элементы управления**, а затем выберите команду **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="a0dd2-548">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-548">Choose **Create**.</span></span>

<span data-ttu-id="a0dd2-p138">При создании этой политики, не устанавливайте флажок платформ. Это приводит к использованию совместимые устройства.</span><span class="sxs-lookup"><span data-stu-id="a0dd2-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>




<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a><span data-ttu-id="a0dd2-551">Дальнейшие шаги</span><span class="sxs-lookup"><span data-stu-id="a0dd2-551">Next steps</span></span>

[<span data-ttu-id="a0dd2-552">Узнайте о рекомендуемых политиках для защиты электронной почты</span><span class="sxs-lookup"><span data-stu-id="a0dd2-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
