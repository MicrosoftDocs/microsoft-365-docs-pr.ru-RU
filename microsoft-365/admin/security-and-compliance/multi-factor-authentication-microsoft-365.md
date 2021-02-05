---
title: Многофакторная проверка подлинности в Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Сведения о многофакторной проверке подлинности в Microsoft 365
ms.openlocfilehash: 5e72e3990db533b49041dc4167283b9487f23426
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105189"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="6d184-103">Многофакторная проверка подлинности в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d184-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="6d184-104">Применение паролей — самый распространенный способ проверки подлинности при входе в компьютер или веб-службу, но это еще и самый уязвимый способ.</span><span class="sxs-lookup"><span data-stu-id="6d184-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="6d184-105">Люди могут выбирать простые пароли и использовать один и тот же пароль для входа в разные компьютеры и службы.</span><span class="sxs-lookup"><span data-stu-id="6d184-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="6d184-106">Чтобы обеспечить дополнительный уровень защиты при входе в систему, нужно использовать многофакторную проверку подлинности (MFA), в которой применяется как пароль (который должен быть надежным), так и дополнительные методы проверки, основанные на:</span><span class="sxs-lookup"><span data-stu-id="6d184-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="6d184-107">использовании того, что принадлежит вам и что не поддается простому дублированию, например смартфона;</span><span class="sxs-lookup"><span data-stu-id="6d184-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="6d184-108">использовании того, что уникально для вас и принадлежит вам биологически. Это может быть отпечаток пальца, ваше лицо или другая биометрическая характеристика.</span><span class="sxs-lookup"><span data-stu-id="6d184-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="6d184-109">Дополнительный метод проверки не используется до тех пор, пока пароль пользователя не будет проверен.</span><span class="sxs-lookup"><span data-stu-id="6d184-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="6d184-110">При использовании MFA, даже если надежный пользовательский пароль скомпрометирован, у злоумышленника нет вашего смартфона или отпечатка пальца, которые нужны для завершения входа в систему.</span><span class="sxs-lookup"><span data-stu-id="6d184-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="6d184-111">Поддержка MFA в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d184-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="6d184-112">По умолчанию как в Microsoft 365, так и в Office 365 служба MFA для учетных записей пользователей поддерживается с помощью:</span><span class="sxs-lookup"><span data-stu-id="6d184-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="6d184-113">отправленных на телефон текстовых сообщений с проверочным кодом, который должны ввести пользователи;</span><span class="sxs-lookup"><span data-stu-id="6d184-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="6d184-114">телефонного звонка;</span><span class="sxs-lookup"><span data-stu-id="6d184-114">A phone call.</span></span>
- <span data-ttu-id="6d184-115">приложения для смартфонов Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="6d184-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="6d184-116">В обоих случаях при входе в MFA используется метод "что-то, что вам не так просто дублировать" для дополнительной проверки.</span><span class="sxs-lookup"><span data-stu-id="6d184-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="6d184-117">Включить MFA для Microsoft 365 и Office 365 можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="6d184-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="6d184-118">С помощью параметров безопасности, заданных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6d184-118">With security defaults</span></span>
- <span data-ttu-id="6d184-119">С помощью политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="6d184-119">With Conditional Access policies</span></span>
- <span data-ttu-id="6d184-120">Для учетной записи каждого отдельного пользователя (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="6d184-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="6d184-121">Эти способы зависят от вашего плана Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d184-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="6d184-122">Планирование</span><span class="sxs-lookup"><span data-stu-id="6d184-122">Plan</span></span>|<span data-ttu-id="6d184-123">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="6d184-123">Recommendation</span></span>|<span data-ttu-id="6d184-124">Тип клиента</span><span class="sxs-lookup"><span data-stu-id="6d184-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="6d184-125">Все планы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d184-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="6d184-126">Используйте параметры безопасности по умолчанию, что требует применения MFA для всех учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="6d184-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="6d184-127">Вы также можете настроить многофайловую многофакузию для отдельных пользователей, но это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="6d184-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="6d184-128">Версия для малого бизнеса</span><span class="sxs-lookup"><span data-stu-id="6d184-128">Small business</span></span>|
|<span data-ttu-id="6d184-129">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="6d184-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="6d184-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="6d184-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="6d184-131">Лицензии Azure Active Directory (Azure AD) Premium P1</span><span class="sxs-lookup"><span data-stu-id="6d184-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="6d184-132">Используйте политики условного доступа, чтобы сделать обязательным применение MFA для учетных записей пользователей с учетом их принадлежности к группам, используемых ими приложений или других условий.</span><span class="sxs-lookup"><span data-stu-id="6d184-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="6d184-133">С версии для малого бизнеса до корпоративной версии</span><span class="sxs-lookup"><span data-stu-id="6d184-133">Small business to enterprise</span></span>|
|<span data-ttu-id="6d184-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6d184-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="6d184-135">Лицензии Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="6d184-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="6d184-136">Используйте защиту идентификации Azure AD, чтобы требовать применения MFA на основе критериев риска при входе в систему.</span><span class="sxs-lookup"><span data-stu-id="6d184-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="6d184-137">Корпоративная версия</span><span class="sxs-lookup"><span data-stu-id="6d184-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="6d184-138">Параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6d184-138">Security defaults</span></span>

<span data-ttu-id="6d184-139">Параметры безопасности по умолчанию — новая функция в платных и пробных подписках Microsoft 365 и Office 365, появившаяся после 21 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="6d184-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="6d184-140">В этих подписках включены параметры безопасности по умолчанию, что предполагает:</span><span class="sxs-lookup"><span data-stu-id="6d184-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="6d184-141">необходимость использования MFA с приложением Microsoft Authenticator для всех пользователей;</span><span class="sxs-lookup"><span data-stu-id="6d184-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="6d184-142">блокировку традиционной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="6d184-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="6d184-143">На регистрацию MFA в приложении Microsoft Authenticator с помощью смартфонов у пользователей есть 14 дней с момента первого входа в систему после включения параметров безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6d184-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="6d184-144">По истечении 14 дней пользователь не сможет войти в систему до завершения регистрации MFA.</span><span class="sxs-lookup"><span data-stu-id="6d184-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="6d184-145">Применение параметров безопасности по умолчанию гарантирует, что все организации имеют базовый уровень безопасности при входе пользователей в систему, включенный по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6d184-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="6d184-146">Параметры безопасности по умолчанию можно отключить и вместо них использовать политики условного доступа MFA.</span><span class="sxs-lookup"><span data-stu-id="6d184-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="6d184-147">Включить или отключить параметры безопасности по умолчанию можно на портале Azure в области **Свойства** для Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6d184-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Изображение страницы свойств каталога.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="6d184-149">Параметры безопасности по умолчанию можно использовать в любом плане Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d184-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="6d184-150">Дополнительные сведения см. в статье [Обзор параметров безопасности, заданных по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="6d184-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="6d184-151">Политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="6d184-151">Conditional Access policies</span></span>

<span data-ttu-id="6d184-152">Политики условного доступа — это набор правил, определяющих условия, в соответствии с которым оценивается и разрешается вход в систему.</span><span class="sxs-lookup"><span data-stu-id="6d184-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="6d184-153">Например, вы можете создать политику условного доступа, которая устанавливает указанные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="6d184-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="6d184-154">Если имя учетной записи пользователя является членом группы для пользователей, которым назначены роли Exchange, пользователь, пароль, безопасность, SharePoint или глобальный администратор, требуется MFA, прежде чем разрешить доступ.</span><span class="sxs-lookup"><span data-stu-id="6d184-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="6d184-155">Эта политика позволяет вам требовать MFA на основе членства в группах, а не пытаться настроить отдельные учетные записи пользователей для MFA, когда они назначены или не назначены из этих ролей администратора.</span><span class="sxs-lookup"><span data-stu-id="6d184-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="6d184-156">Кроме того, вы можете использовать политики условного доступа для более сложных функций, таких как применение MFA для работы в конкретных приложениях или для выполнения входа с совместимого устройства, например ноутбука с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6d184-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="6d184-157">Настроить политики условного доступа можно на портале Azure в области **Безопасность** для Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6d184-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Изображение параметра меню для условного доступа](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="6d184-159">Использование политик условного доступа возможно с:</span><span class="sxs-lookup"><span data-stu-id="6d184-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="6d184-160">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="6d184-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="6d184-161">Microsoft 365 E3 и E5</span><span class="sxs-lookup"><span data-stu-id="6d184-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="6d184-162">лицензиями Azure AD Premium P1 и Azure AD Premium P2.</span><span class="sxs-lookup"><span data-stu-id="6d184-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="6d184-163">Для малого бизнеса с Microsoft 365 бизнес премиум можно легко использовать политики условного доступа, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6d184-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="6d184-164">Создайте группу, в которую войдут учетные записи пользователей, для которых требуется применение MFA.</span><span class="sxs-lookup"><span data-stu-id="6d184-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="6d184-165">Включите политику **Требуется MFA для глобальных администраторов**.</span><span class="sxs-lookup"><span data-stu-id="6d184-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="6d184-166">Создайте политику условного доступа на уровне группы со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="6d184-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="6d184-167">Назначения > Пользователи и группы: имя группы, указанное выше в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="6d184-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="6d184-168">Назначения > Облачные приложения или действия: все облачные приложения.</span><span class="sxs-lookup"><span data-stu-id="6d184-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="6d184-169">Элементы управления доступом > Предоставить > Предоставить доступ > Требовать многофакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="6d184-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="6d184-170">Включите политику.</span><span class="sxs-lookup"><span data-stu-id="6d184-170">Enable the policy.</span></span>
5. <span data-ttu-id="6d184-171">Добавьте учетную запись пользователя в группу, созданную на шаге 1 выше, и проверьте ее.</span><span class="sxs-lookup"><span data-stu-id="6d184-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="6d184-172">Чтобы сделать обязательным применение MFA для дополнительных учетных записей пользователей, добавьте их в группу, созданную на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="6d184-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="6d184-173">Эта политика условного доступа позволяет развертывать для пользователей требование применения MFA в удобном для вас темпе.</span><span class="sxs-lookup"><span data-stu-id="6d184-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="6d184-174">На предприятиях следует использовать [Общие политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) для настройки указанных ниже политик.</span><span class="sxs-lookup"><span data-stu-id="6d184-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="6d184-175">Обязательное использование MFA для администраторов</span><span class="sxs-lookup"><span data-stu-id="6d184-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="6d184-176">Обязательное использование MFA для всех пользователей</span><span class="sxs-lookup"><span data-stu-id="6d184-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="6d184-177">Блокирование традиционной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="6d184-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="6d184-178">Дополнительные сведения см. в статье [Обзор условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="6d184-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="6d184-179">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d184-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="6d184-180">Защита идентификации Azure AD позволяет создать дополнительную политику условного доступа [Необходимость MFA в случае среднего или высокого риска при входе](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="6d184-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="6d184-181">Защиту идентификации Azure AD и политики условного доступа на основе риска можно использовать с:</span><span class="sxs-lookup"><span data-stu-id="6d184-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="6d184-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6d184-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="6d184-183">Лицензиями Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="6d184-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="6d184-184">Дополнительные сведения см. в статье [Общие сведения о защите идентификации Azure AD](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="6d184-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="6d184-185">Устаревшая многофайловая версия (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="6d184-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="6d184-186">Чтобы установить требование применения MFA при входе в пользовательскую учетную запись, необходимо использовать или параметры безопасности по умолчанию, или политики условного доступа. Однако если ни один из этих вариантов не подходит, корпорация Майкрософт настоятельно рекомендует в подписке любой величины устанавливать MFA для учетных записей пользователей, которым назначены роли администратора, особенно роль глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6d184-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="6d184-187">MFA для отдельных учетных записей пользователей можно включить в области **Активные пользователи** центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d184-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Изображение параметра многофакторной проверки подлинности на странице "Активные пользователи"](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="6d184-189">После включения MFA при следующем входе пользователя ему будет предложено выполнить регистрацию для MFA, а также выбрать и протестировать дополнительный метод проверки.</span><span class="sxs-lookup"><span data-stu-id="6d184-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="6d184-190">Совместное использование этих методов</span><span class="sxs-lookup"><span data-stu-id="6d184-190">Using these methods together</span></span>

<span data-ttu-id="6d184-191">В этой таблице показаны результаты использования MFA с параметрами безопасности по умолчанию, политиками условного доступа и индивидуальными параметрами учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="6d184-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

||<span data-ttu-id="6d184-192">Включен</span><span class="sxs-lookup"><span data-stu-id="6d184-192">Enabled</span></span>|<span data-ttu-id="6d184-193">Отключено</span><span class="sxs-lookup"><span data-stu-id="6d184-193">Disabled</span></span>|<span data-ttu-id="6d184-194">Дополнительный метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="6d184-194">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="6d184-195">**Параметры безопасности по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="6d184-195">**Security defaults**</span></span>|<span data-ttu-id="6d184-196">Не может использовать политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="6d184-196">Can't use Conditional Access policies</span></span>|<span data-ttu-id="6d184-197">Возможно использование политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="6d184-197">Can use Conditional Access policies</span></span>|<span data-ttu-id="6d184-198">Приложение Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="6d184-198">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="6d184-199">**Политики условного доступа**</span><span class="sxs-lookup"><span data-stu-id="6d184-199">**Conditional Access policies**</span></span>|<span data-ttu-id="6d184-200">Если они включены, вы не можете включить значения по умолчанию для системы безопасности</span><span class="sxs-lookup"><span data-stu-id="6d184-200">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="6d184-201">Если все отключены, вы можете включить настройки безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6d184-201">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="6d184-202">Указываются пользователем во время регистрации MFA</span><span class="sxs-lookup"><span data-stu-id="6d184-202">User-specified during MFA registration</span></span>|
|<span data-ttu-id="6d184-203">**Устаревшая многофайловая версия (не рекомендуется)**</span><span class="sxs-lookup"><span data-stu-id="6d184-203">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="6d184-204">Переопределяет параметры безопасности по умолчанию и политики условного доступа, требующие MFA для каждого входа в систему.</span><span class="sxs-lookup"><span data-stu-id="6d184-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="6d184-205">Переопределено параметрами безопасности по умолчанию и политиками условного доступа</span><span class="sxs-lookup"><span data-stu-id="6d184-205">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="6d184-206">Указываются пользователем во время регистрации MFA</span><span class="sxs-lookup"><span data-stu-id="6d184-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="6d184-207">Если включены параметры безопасности по умолчанию, всем новым пользователям будет предложено пройти регистрацию для MFA и при следующем входе в систему использовать приложение Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="6d184-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="6d184-208">Способы управления параметрами MFA</span><span class="sxs-lookup"><span data-stu-id="6d184-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="6d184-209">Существует два способа управления параметрами MFA.</span><span class="sxs-lookup"><span data-stu-id="6d184-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="6d184-210">На портале Azure вы можете выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6d184-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="6d184-211">Включать и выключать параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6d184-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="6d184-212">Настраивать политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="6d184-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="6d184-213">В центре администрирования Microsoft 365 можно настраивать параметры MFA для каждого пользователя и службы.</span><span class="sxs-lookup"><span data-stu-id="6d184-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="6d184-214">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="6d184-214">Your next step</span></span>

[<span data-ttu-id="6d184-215">Настройка MFA для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d184-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

## <a name="related-topics"></a><span data-ttu-id="6d184-216">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6d184-216">Related topics</span></span>

[<span data-ttu-id="6d184-217">Видео: включив многофакторную проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="6d184-217">Video: Turn on multi-factor authentication</span></span>](https://docs.microsoft.com/microsoft-365/business-video/turn-on-mfa)

[<span data-ttu-id="6d184-218">Видео: включите многофакторную проверку подлинности для телефона</span><span class="sxs-lookup"><span data-stu-id="6d184-218">Video: Turn on multi-factor authentication for your phone</span></span>](https://docs.microsoft.com/microsoft-365/business-video/set-up-mfa)
