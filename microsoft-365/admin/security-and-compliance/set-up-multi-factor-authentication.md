---
title: Настройка многофакторной проверки подлинности для пользователей
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Узнайте, как настроить многофакторную проверку подлинности для Организации.
monikerRange: o365-worldwide
ms.openlocfilehash: 2b4ac2b5950d2641254742e03f054f3e4c886833
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399126"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="e7470-103">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="e7470-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="e7470-104">Основываясь на понимании [многофакторной проверки подлинности (MFA) и ее поддержке в Microsoft 365](multi-factor-authentication-microsoft-365.md), можно настроить ее и выполнить ее развертывание в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e7470-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="e7470-105">Прежде чем приступать к работе, определите, применимы ли эти особые условия, и выполните соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="e7470-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="e7470-106">Если у вас есть клиенты Office 2013 на устройствах с Windows, [включите современная проверка подлинности](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="e7470-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="e7470-107">Если у вас есть сторонние службы каталогов со службами федерации Active Directory (AD FS), настройте сервер Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="e7470-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="e7470-108">Более подробную информацию можно найти [в статье Расширенные сценарии с многофакторной проверкой подлинности Azure и сторонние решения VPN](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) .</span><span class="sxs-lookup"><span data-stu-id="e7470-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="e7470-109">Шаг 1: принятие решения о необходимости использовать MFA для пользователей</span><span class="sxs-lookup"><span data-stu-id="e7470-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

<span data-ttu-id="e7470-110">Существует три способа потребовать от пользователей использовать MFA для входа. Подробные сведения можно найти [в статье поддержка MFA в Microsoft 365](multi-factor-authentication-microsoft-365.md) .</span><span class="sxs-lookup"><span data-stu-id="e7470-110">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="e7470-111">Значения по умолчанию для системы безопасности (рекомендуется для малых предприятий)</span><span class="sxs-lookup"><span data-stu-id="e7470-111">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="e7470-112">Если вы приобрели подписку или пробную версию после 21 октября 2019 г., а вы неожиданно запрашиваете MFA, для подписки автоматически включается параметр [безопасности по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) .</span><span class="sxs-lookup"><span data-stu-id="e7470-112">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="e7470-113">Для каждой новой подписки Microsoft 365 автоматически будут включены параметры безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7470-113">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="e7470-114">Это означает, что каждый пользователь должен настроить MFA и установить приложение Microsoft Authenticator на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="e7470-114">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="e7470-115">Все пользователи должны использовать приложение Microsoft Authenticator в качестве дополнительного метода проверки, а устаревшая проверка подлинности заблокирована.</span><span class="sxs-lookup"><span data-stu-id="e7470-115">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="e7470-116">Политики условного доступа (рекомендуется для предприятий)</span><span class="sxs-lookup"><span data-stu-id="e7470-116">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="e7470-117">Во время регистрации MFA пользователи выбирают дополнительный метод проверки.</span><span class="sxs-lookup"><span data-stu-id="e7470-117">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="e7470-118">Учетная запись для каждого пользователя (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="e7470-118">Per-user account (not recommended)</span></span>

  <span data-ttu-id="e7470-119">Во время регистрации MFA пользователи выбирают дополнительный метод проверки.</span><span class="sxs-lookup"><span data-stu-id="e7470-119">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="e7470-120">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="e7470-120">Step 2.</span></span> <span data-ttu-id="e7470-121">Тестирование MFA для пилотных пользователей</span><span class="sxs-lookup"><span data-stu-id="e7470-121">Test MFA on your pilot users</span></span>

<span data-ttu-id="e7470-122">Если вы используете политики условного доступа или пользователь MFA (не рекомендуется), выберите пилотных пользователей в вашей организации или в Организации, чтобы проверить регистрацию и вход в систему MFA. Например:</span><span class="sxs-lookup"><span data-stu-id="e7470-122">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="e7470-123">Для политик условного доступа создайте группу пилотных пользователей и политику, которая требует MFA для участников группы и всех приложений.</span><span class="sxs-lookup"><span data-stu-id="e7470-123">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="e7470-124">Затем добавьте учетные записи пилотного пользователя в группу.</span><span class="sxs-lookup"><span data-stu-id="e7470-124">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="e7470-125">Для каждого пользователя MFA включите MFA для учетных записей пользователей пилотного проекта один раз.</span><span class="sxs-lookup"><span data-stu-id="e7470-125">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="e7470-126">Работайте с пилотными пользователями, чтобы решить вопросы и проблемы, которые могут быть готовы к развертыванию в Организации.</span><span class="sxs-lookup"><span data-stu-id="e7470-126">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="e7470-127">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="e7470-127">Step 3.</span></span> <span data-ttu-id="e7470-128">Сообщите вашей организации о том, что MFA поступает</span><span class="sxs-lookup"><span data-stu-id="e7470-128">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="e7470-129">Используйте уведомления по электронной почте, афиши халлвай, собрания группы или формальное обучение, чтобы убедиться, что ваши сотрудники понимают:</span><span class="sxs-lookup"><span data-stu-id="e7470-129">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="e7470-130">Почему MFA необходимо для входа в систему.</span><span class="sxs-lookup"><span data-stu-id="e7470-130">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="e7470-131">Регистрация для дополнительного метода проверки</span><span class="sxs-lookup"><span data-stu-id="e7470-131">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="e7470-132">Вход после регистрации</span><span class="sxs-lookup"><span data-stu-id="e7470-132">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="e7470-133">Изменение дополнительного метода проверки</span><span class="sxs-lookup"><span data-stu-id="e7470-133">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="e7470-134">Как работать с такими ситуациями, как новый смарт-телефон</span><span class="sxs-lookup"><span data-stu-id="e7470-134">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="e7470-135">Самое важное, убедитесь, что сотрудники понимают, ***когда требование MFA будет направляться*** , чтобы оно не было неожиданным.</span><span class="sxs-lookup"><span data-stu-id="e7470-135">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="e7470-136">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="e7470-136">Step 4.</span></span> <span data-ttu-id="e7470-137">Развертывание требования к MFA для организации или пользователей</span><span class="sxs-lookup"><span data-stu-id="e7470-137">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="e7470-138">В соответствии с выбранным методом требования MFA развертывание проверки подлинности MFA для сотрудников за пределами пилотных тестовых инженеров.</span><span class="sxs-lookup"><span data-stu-id="e7470-138">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="e7470-139">Параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e7470-139">Security defaults</span></span>

<span data-ttu-id="e7470-140">Вы включаете или отключаете параметры безопасности по умолчанию в области **свойств** для Azure Active Directory (Azure AD) на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="e7470-140">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="e7470-141">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e7470-141">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="e7470-142">Перейдите на [страницу "свойства Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)".</span><span class="sxs-lookup"><span data-stu-id="e7470-142">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="e7470-143">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e7470-143">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="e7470-144">Нажмите кнопку **Да** , чтобы включить параметры безопасности по умолчанию и **нет** для отключения параметров безопасности по умолчанию, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e7470-144">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="e7470-145">Если вы используете [базовые политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), то как вы переходите к использованию параметров безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7470-145">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="e7470-146">Перейдите на [страницу условного доступа — политики](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="e7470-146">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="e7470-147">Выберите каждую базовую политику, **On** включенную в **параметр** , и установите для **нее значение отключено**.</span><span class="sxs-lookup"><span data-stu-id="e7470-147">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="e7470-148">Перейдите на [страницу "свойства Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)".</span><span class="sxs-lookup"><span data-stu-id="e7470-148">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="e7470-149">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e7470-149">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="e7470-150">Нажмите кнопку **Да** , чтобы включить параметры безопасности по умолчанию и **нет** для отключения параметров безопасности по умолчанию, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e7470-150">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="e7470-151">Политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="e7470-151">Conditional Access policies</span></span>

<span data-ttu-id="e7470-152">Создание, Настройка и включение соответствующих политик, включающих группу пользователей, для которых требуется вход в систему MFA.</span><span class="sxs-lookup"><span data-stu-id="e7470-152">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="e7470-153">MFA для пользователя (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="e7470-153">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="e7470-154">Включение учетных записей пользователей для MFA, соответствующих развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e7470-154">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="e7470-155">Поддержка сотрудников</span><span class="sxs-lookup"><span data-stu-id="e7470-155">Supporting your employees</span></span>

<span data-ttu-id="e7470-156">Когда ваши сотрудники регистрируются и начинают вход с помощью MFA, убедитесь, что ИТ ИТ, ИТ отдела или служба технической поддержки могут быстро ответить на вопросы и устранить проблемы.</span><span class="sxs-lookup"><span data-stu-id="e7470-156">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="e7470-157">В этой статье приведены [сведения об устранении неполадок входа в MFA](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="e7470-157">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


