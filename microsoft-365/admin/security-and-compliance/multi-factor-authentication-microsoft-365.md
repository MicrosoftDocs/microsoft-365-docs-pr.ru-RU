---
title: Многофакторная проверка подлинности для Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Сведения о многофакторной проверке подлинности в Microsoft 365.
ms.openlocfilehash: 128296b7dbc37ba5ebffb25a87bce589f8e5a904
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340850"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="fd848-103">Многофакторная проверка подлинности для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd848-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="fd848-104">Пароли — это наиболее распространенный способ проверки подлинности входа на компьютер или сетевую службу, но они также наиболее уязвимы.</span><span class="sxs-lookup"><span data-stu-id="fd848-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="fd848-105">Пользователи могут выбирать простые пароли и использовать одни и те же пароли для нескольких входов на разных компьютерах и службах.</span><span class="sxs-lookup"><span data-stu-id="fd848-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="fd848-106">Чтобы обеспечить дополнительный уровень безопасности для входов, необходимо использовать многофакторную проверку подлинности (MFA), которая использует как пароль, который должен быть надежным, так и дополнительный метод проверки на основе:</span><span class="sxs-lookup"><span data-stu-id="fd848-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="fd848-107">Что-то не так, что вам легко дублировать, например, смарт-телефон.</span><span class="sxs-lookup"><span data-stu-id="fd848-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="fd848-108">Что-то у вас уникально и у вас есть свои уникальные и биометрические действия, такие как отпечатки пальца, лица или другие биометрические атрибуты.</span><span class="sxs-lookup"><span data-stu-id="fd848-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="fd848-109">Дополнительный метод проверки не используется до тех пор, пока не будет проверен пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="fd848-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="fd848-110">При использовании MFA даже в случае взлома надежного пароля пользователя у взломщика нет своего смарт-телефона или отпечатка пальца для завершения входа.</span><span class="sxs-lookup"><span data-stu-id="fd848-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="fd848-111">Поддержка MFA в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd848-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="fd848-112">По умолчанию Microsoft 365 и Office 365 поддерживают MFA для учетных записей пользователей с помощью следующих средств:</span><span class="sxs-lookup"><span data-stu-id="fd848-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="fd848-113">Текстовое сообщение, отправленное на телефон, с помощью которого пользователь должен ввести код подтверждения.</span><span class="sxs-lookup"><span data-stu-id="fd848-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="fd848-114">Телефонный звонок.</span><span class="sxs-lookup"><span data-stu-id="fd848-114">A phone call.</span></span>
- <span data-ttu-id="fd848-115">Приложение интеллектуального телефона для проверки подлинности Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fd848-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="fd848-116">В обоих случаях вход в MFA использует для дополнительной проверки "что-то с нелегко дублированным" методом.</span><span class="sxs-lookup"><span data-stu-id="fd848-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="fd848-117">Включить MFA для Microsoft 365 и Office 365 можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="fd848-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="fd848-118">С использованием значений по умолчанию для безопасности</span><span class="sxs-lookup"><span data-stu-id="fd848-118">With security defaults</span></span>
- <span data-ttu-id="fd848-119">С политиками условного доступа</span><span class="sxs-lookup"><span data-stu-id="fd848-119">With Conditional Access policies</span></span>
- <span data-ttu-id="fd848-120">Для каждой индивидуальной учетной записи пользователя (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="fd848-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="fd848-121">Эти способы основаны на плане Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd848-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="fd848-122">План</span><span class="sxs-lookup"><span data-stu-id="fd848-122">Plan</span></span>  |<span data-ttu-id="fd848-123">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="fd848-123">Recommendation</span></span>  | <span data-ttu-id="fd848-124">Тип клиента</span><span class="sxs-lookup"><span data-stu-id="fd848-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="fd848-125">Все планы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd848-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="fd848-126">Используйте параметры безопасности по умолчанию, которые требуют MFA для всех учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="fd848-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="fd848-127">Кроме того, для каждой учетной записи на уровне пользователя необходимо использовать MFA, но это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="fd848-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="fd848-128">Для малого бизнеса</span><span class="sxs-lookup"><span data-stu-id="fd848-128">Small business</span></span> |
| <span data-ttu-id="fd848-129">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="fd848-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="fd848-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="fd848-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="fd848-131">Лицензии Azure Active Directory (Azure AD) Premium P1</span><span class="sxs-lookup"><span data-stu-id="fd848-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="fd848-132">Используйте политики условного доступа, чтобы требовать использование MFA для учетных записей пользователей в соответствии с членством в группах, приложениями или другими условиями.</span><span class="sxs-lookup"><span data-stu-id="fd848-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="fd848-133">Малый бизнес для предприятий</span><span class="sxs-lookup"><span data-stu-id="fd848-133">Small business to enterprise</span></span> |
| <span data-ttu-id="fd848-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fd848-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="fd848-135">Лицензии Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="fd848-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="fd848-136">Используйте службу защиты удостоверений Azure AD, чтобы запрашивать MFA на основе условий риска входа в систему.</span><span class="sxs-lookup"><span data-stu-id="fd848-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="fd848-137">Предприятие</span><span class="sxs-lookup"><span data-stu-id="fd848-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="fd848-138">Параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fd848-138">Security defaults</span></span>

<span data-ttu-id="fd848-139">Параметры безопасности по умолчанию — новая функция в платных и пробных подписках Microsoft 365 и Office 365, появившаяся после 21 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="fd848-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="fd848-140">Для этих подписок включены параметры безопасности по умолчанию, которые:</span><span class="sxs-lookup"><span data-stu-id="fd848-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="fd848-141">Все пользователи должны использовать MFA в приложении Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="fd848-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="fd848-142">Блокирует устаревшую проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="fd848-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="fd848-143">На регистрацию MFA в приложении Microsoft Authenticator с помощью смартфонов у пользователей есть 14 дней с момента первого входа в систему после включения параметров безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd848-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="fd848-144">По истечении 14 дней пользователь не сможет войти в систему до завершения регистрации MFA.</span><span class="sxs-lookup"><span data-stu-id="fd848-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="fd848-145">Применение параметров безопасности по умолчанию гарантирует, что все организации имеют базовый уровень безопасности при входе пользователей в систему, включенный по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd848-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="fd848-146">Вы можете отключить параметры безопасности по умолчанию в пользу использования MFA с политиками условного доступа.</span><span class="sxs-lookup"><span data-stu-id="fd848-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="fd848-147">Вы включаете или отключаете параметры безопасности по умолчанию в области **свойств** для Azure AD на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="fd848-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="fd848-148">Вы можете использовать параметры по умолчанию для безопасности с любым планом Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd848-148">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="fd848-149">Дополнительные сведения см. в статье [Обзор параметров безопасности, заданных по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="fd848-149">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="fd848-150">Политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="fd848-150">Conditional Access policies</span></span>

<span data-ttu-id="fd848-151">Политики условного доступа — это набор правил, определяющих условия, в соответствии с которым оценивается и разрешается вход в систему.</span><span class="sxs-lookup"><span data-stu-id="fd848-151">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="fd848-152">Например, вы можете создать политику условного доступа, которая устанавливает указанные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="fd848-152">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="fd848-153">Если имя учетной записи пользователя является членом группы для пользователей, которым назначены роли Exchange, пользователь, пароль, безопасность, SharePoint или глобальный администратор, требуется MFA, прежде чем разрешить доступ.</span><span class="sxs-lookup"><span data-stu-id="fd848-153">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="fd848-154">Эта политика позволяет вам требовать MFA на основе членства в группах, а не пытаться настроить отдельные учетные записи пользователей для MFA, когда они назначены или не назначены из этих ролей администратора.</span><span class="sxs-lookup"><span data-stu-id="fd848-154">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="fd848-155">Кроме того, вы можете использовать политики условного доступа для более сложных возможностей, таких как требование MFA для определенных приложений, или то, что вход выполняется на соответствующем устройстве, например на ноутбуке с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fd848-155">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="fd848-156">Политики условного доступа настраиваются в области **безопасности** для Azure AD на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="fd848-156">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="fd848-157">Политики условного доступа можно использовать с:</span><span class="sxs-lookup"><span data-stu-id="fd848-157">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="fd848-158">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="fd848-158">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="fd848-159">Microsoft 365 E3 и в ~</span><span class="sxs-lookup"><span data-stu-id="fd848-159">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="fd848-160">Лицензии Azure AD Premium P1 и Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="fd848-160">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="fd848-161">Для малых предприятий с Microsoft 365 Business Premium можно легко использовать политики условного доступа, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fd848-161">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="fd848-162">Создайте группу, содержащую учетные записи пользователей, для которых требуется MFA.</span><span class="sxs-lookup"><span data-stu-id="fd848-162">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="fd848-163">Включите параметр **требовать использования MFA для глобальных администраторов** .</span><span class="sxs-lookup"><span data-stu-id="fd848-163">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="fd848-164">Создайте политику условного доступа на основе групп с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="fd848-164">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="fd848-165">Назначения > пользователи и группы: имя группы, описанное в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="fd848-165">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="fd848-166">Назначения > облачные приложения или действия: все облачные приложения.</span><span class="sxs-lookup"><span data-stu-id="fd848-166">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="fd848-167">Для управления доступом > предоставления > предоставления доступа > требуется многофакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="fd848-167">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="fd848-168">Включите политику.</span><span class="sxs-lookup"><span data-stu-id="fd848-168">Enable the policy.</span></span>
5. <span data-ttu-id="fd848-169">Добавьте учетную запись пользователя в группу, созданную на шаге 1, и проверьте ее.</span><span class="sxs-lookup"><span data-stu-id="fd848-169">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="fd848-170">Чтобы включить MFA для дополнительных учетных записей пользователей, добавьте их в группу, созданную на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="fd848-170">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="fd848-171">Эта политика условного доступа позволяет пользователям в удобном для вас темпе выполнить развертывание требования MFA для пользователей.</span><span class="sxs-lookup"><span data-stu-id="fd848-171">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="fd848-172">Предприятия должны использовать [Общие политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) для настройки следующих политик:</span><span class="sxs-lookup"><span data-stu-id="fd848-172">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="fd848-173">Обязательное использование MFA для администраторов</span><span class="sxs-lookup"><span data-stu-id="fd848-173">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="fd848-174">Обязательное использование MFA для всех пользователей</span><span class="sxs-lookup"><span data-stu-id="fd848-174">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="fd848-175">Блокирование традиционной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="fd848-175">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="fd848-176">Дополнительные сведения см. в статье [Обзор условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="fd848-176">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="fd848-177">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="fd848-177">Azure AD Identity Protection</span></span>

<span data-ttu-id="fd848-178">С помощью средства защиты идентификации Azure AD можно создать дополнительную политику условного доступа, чтобы [требовать, когда риск входа в систему имеет средний или высокий](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)уровень.</span><span class="sxs-lookup"><span data-stu-id="fd848-178">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="fd848-179">Вы можете использовать политики защиты удостоверений Azure AD и условного доступа на основе риска с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="fd848-179">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="fd848-180">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fd848-180">Microsoft 365 E5</span></span>
- <span data-ttu-id="fd848-181">Лицензии Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="fd848-181">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="fd848-182">Дополнительные сведения см. в статье [Обзор защиты идентификации Azure AD](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="fd848-182">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="fd848-183">MFA для отдельной учетной записи пользователя (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="fd848-183">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="fd848-184">Для входа в учетную запись пользователя необходимо использовать политики безопасности по умолчанию или политики условного доступа. Тем не менее, если какой – либо из этих вариантов, корпорация Майкрософт настоятельно рекомендует MFA для учетных записей пользователей, у которых есть роли администратора, в частности роль глобального администратора, для любой подписки на размер.</span><span class="sxs-lookup"><span data-stu-id="fd848-184">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="fd848-185">Вы включаете MFA для отдельных учетных записей пользователей в области **активного пользователя** центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd848-185">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="fd848-186">После включения этого параметра при следующем входе пользователя будет предложено зарегистрироваться для MFA, а затем выбрать и проверить дополнительный метод проверки.</span><span class="sxs-lookup"><span data-stu-id="fd848-186">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="fd848-187">Совместное использование этих методов</span><span class="sxs-lookup"><span data-stu-id="fd848-187">Using these methods together</span></span>

<span data-ttu-id="fd848-188">В этой таблице показаны результаты использования MFA с параметрами безопасности по умолчанию, политиками условного доступа и индивидуальными параметрами учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="fd848-188">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="fd848-189">Включен</span><span class="sxs-lookup"><span data-stu-id="fd848-189">Enabled</span></span> | <span data-ttu-id="fd848-190">Отключено</span><span class="sxs-lookup"><span data-stu-id="fd848-190">Disabled</span></span> | <span data-ttu-id="fd848-191">Дополнительный метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="fd848-191">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="fd848-192">**Параметры безопасности по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="fd848-192">**Security defaults**</span></span> | <span data-ttu-id="fd848-193">Невозможно использовать политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="fd848-193">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="fd848-194">Возможно использование политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="fd848-194">Can use Conditional Access policies</span></span> | <span data-ttu-id="fd848-195">Приложение Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="fd848-195">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="fd848-196">**Политики условного доступа**</span><span class="sxs-lookup"><span data-stu-id="fd848-196">**Conditional Access policies**</span></span> |<span data-ttu-id="fd848-197">Если включена хотя бы одна из них, то включение параметров безопасности по умолчанию невозможно</span><span class="sxs-lookup"><span data-stu-id="fd848-197">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="fd848-198">Если все отключены, вы можете включить настройки безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fd848-198">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="fd848-199">Указываются пользователем во время регистрации MFA</span><span class="sxs-lookup"><span data-stu-id="fd848-199">User-specified during MFA registration</span></span> |
| <span data-ttu-id="fd848-200">**Параметр учетной записи для отдельных пользователей (не рекомендуется)**</span><span class="sxs-lookup"><span data-stu-id="fd848-200">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="fd848-201">Переопределение политиками безопасности по умолчанию и условным доступом, требующим MFA</span><span class="sxs-lookup"><span data-stu-id="fd848-201">Overridden by security defaults and Conditional Access policies requiring MFA</span></span> | <span data-ttu-id="fd848-202">Переопределение политиками по умолчанию безопасности и условного доступа</span><span class="sxs-lookup"><span data-stu-id="fd848-202">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="fd848-203">Указываются пользователем во время регистрации MFA</span><span class="sxs-lookup"><span data-stu-id="fd848-203">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="fd848-204">Если включены параметры безопасности по умолчанию, все новые пользователи получают запросы на регистрацию MFA и использование приложения проверки подлинности Майкрософт при следующем входе в систему.</span><span class="sxs-lookup"><span data-stu-id="fd848-204">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

<span data-ttu-id="fd848-205">Тем не менее, если у пользователя есть старый телефон, который может получать текстовые сообщения, но не может запустить приложение Microsoft Authenticator, можно включить MFA для этой учетной записи пользователя и зарегистрировать его с помощью дополнительного метода проверки кода, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fd848-205">However, if a user has an older phone that can receive text messages but cannot run the Microsoft Authenticator app, you can enable MFA on that specific user account and have them register using the text code additional verification method with these steps:</span></span>

1. <span data-ttu-id="fd848-206">Отключение параметров безопасности по умолчанию на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="fd848-206">Disable security defaults in the Azure portal.</span></span>
2. <span data-ttu-id="fd848-207">Включите MFA для учетной записи пользователя в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd848-207">Enable MFA for the user account in the Microsoft 365 admin center.</span></span>
3. <span data-ttu-id="fd848-208">Попросите пользователя войти и зарегистрировать для MFA и метода проверки подлинности текстового кода.</span><span class="sxs-lookup"><span data-stu-id="fd848-208">Have the user sign in and register for MFA and the text code authentication method.</span></span>
4. <span data-ttu-id="fd848-209">По завершении включите параметры безопасности по умолчанию на портале Azure</span><span class="sxs-lookup"><span data-stu-id="fd848-209">When complete, enable security defaults in the Azure portal</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="fd848-210">Способы управления параметрами MFA</span><span class="sxs-lookup"><span data-stu-id="fd848-210">Ways to manage MFA settings</span></span>

<span data-ttu-id="fd848-211">Управлять параметрами MFA можно двумя способами.</span><span class="sxs-lookup"><span data-stu-id="fd848-211">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="fd848-212">На портале Azure можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fd848-212">In the Azure portal, you can:</span></span>

- <span data-ttu-id="fd848-213">Включение и отключение параметров безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fd848-213">Enable and disable security defaults</span></span>
- <span data-ttu-id="fd848-214">Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="fd848-214">Configure Conditional Access policies</span></span>

<span data-ttu-id="fd848-215">В центре администрирования Microsoft 365 можно настроить параметры MFA для отдельных пользователей и служб.</span><span class="sxs-lookup"><span data-stu-id="fd848-215">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="fd848-216">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="fd848-216">Your next step</span></span>

[<span data-ttu-id="fd848-217">Настройка MFA для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd848-217">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

