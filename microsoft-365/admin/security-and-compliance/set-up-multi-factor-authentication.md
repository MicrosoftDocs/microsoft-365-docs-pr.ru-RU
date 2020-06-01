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
ms.openlocfilehash: c84c66cc051363fbc582abfb5521f922440b6801
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432383"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="b1676-103">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b1676-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="b1676-104">Основываясь на понимании [многофакторной проверки подлинности (MFA) и ее поддержке в Microsoft 365](multi-factor-authentication-microsoft-365.md), можно настроить ее и выполнить ее развертывание в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b1676-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="b1676-105">Прежде чем приступать к работе, определите, применимы ли эти особые условия, и выполните соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="b1676-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="b1676-106">Если у вас есть клиенты Office 2013 на устройствах с Windows, [включите современная проверка подлинности](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="b1676-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="b1676-107">Если у вас есть сторонние службы каталогов со службами федерации Active Directory (AD FS), настройте сервер Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="b1676-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="b1676-108">Более подробную информацию можно найти [в статье Расширенные сценарии с многофакторной проверкой подлинности Azure и сторонние решения VPN](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) .</span><span class="sxs-lookup"><span data-stu-id="b1676-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="b1676-109">Шаг 1: принятие решения о необходимости использовать MFA для пользователей</span><span class="sxs-lookup"><span data-stu-id="b1676-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="b1676-110">Для установки или изменения MFA необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="b1676-110">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="b1676-111">Существует три способа потребовать от пользователей использовать MFA для входа. Подробные сведения можно найти [в статье поддержка MFA в Microsoft 365](multi-factor-authentication-microsoft-365.md) .</span><span class="sxs-lookup"><span data-stu-id="b1676-111">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="b1676-112">Значения по умолчанию для системы безопасности (рекомендуется для малых предприятий)</span><span class="sxs-lookup"><span data-stu-id="b1676-112">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="b1676-113">Если вы приобрели подписку или пробную версию после 21 октября 2019 г., а вы неожиданно запрашиваете MFA, для подписки автоматически включается параметр [безопасности по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) .</span><span class="sxs-lookup"><span data-stu-id="b1676-113">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="b1676-114">Для каждой новой подписки Microsoft 365 автоматически будут включены параметры безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1676-114">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="b1676-115">Это означает, что каждый пользователь должен настроить MFA и установить приложение Microsoft Authenticator на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="b1676-115">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="b1676-116">Все пользователи должны использовать приложение Microsoft Authenticator в качестве дополнительного метода проверки, а устаревшая проверка подлинности заблокирована.</span><span class="sxs-lookup"><span data-stu-id="b1676-116">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="b1676-117">Политики условного доступа (рекомендуется для предприятий)</span><span class="sxs-lookup"><span data-stu-id="b1676-117">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="b1676-118">Во время регистрации MFA пользователи выбирают дополнительный метод проверки.</span><span class="sxs-lookup"><span data-stu-id="b1676-118">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="b1676-119">Учетная запись для каждого пользователя (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="b1676-119">Per-user account (not recommended)</span></span>

  <span data-ttu-id="b1676-120">Во время регистрации MFA пользователи выбирают дополнительный метод проверки.</span><span class="sxs-lookup"><span data-stu-id="b1676-120">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="b1676-121">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="b1676-121">Step 2.</span></span> <span data-ttu-id="b1676-122">Тестирование MFA для пилотных пользователей</span><span class="sxs-lookup"><span data-stu-id="b1676-122">Test MFA on your pilot users</span></span>

<span data-ttu-id="b1676-123">Если вы используете политики условного доступа или пользователь MFA (не рекомендуется), выберите пилотных пользователей в вашей организации или в Организации, чтобы проверить регистрацию и вход в систему MFA. Например:</span><span class="sxs-lookup"><span data-stu-id="b1676-123">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="b1676-124">Для политик условного доступа создайте группу пилотных пользователей и политику, которая требует MFA для участников группы и всех приложений.</span><span class="sxs-lookup"><span data-stu-id="b1676-124">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="b1676-125">Затем добавьте учетные записи пилотного пользователя в группу.</span><span class="sxs-lookup"><span data-stu-id="b1676-125">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="b1676-126">Для каждого пользователя MFA включите MFA для учетных записей пользователей пилотного проекта один раз.</span><span class="sxs-lookup"><span data-stu-id="b1676-126">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="b1676-127">Работайте с пилотными пользователями, чтобы решить вопросы и проблемы, которые могут быть готовы к развертыванию в Организации.</span><span class="sxs-lookup"><span data-stu-id="b1676-127">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="b1676-128">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="b1676-128">Step 3.</span></span> <span data-ttu-id="b1676-129">Сообщите вашей организации о том, что MFA поступает</span><span class="sxs-lookup"><span data-stu-id="b1676-129">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="b1676-130">Используйте уведомления по электронной почте, афиши халлвай, собрания группы или формальное обучение, чтобы убедиться, что ваши сотрудники понимают:</span><span class="sxs-lookup"><span data-stu-id="b1676-130">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="b1676-131">Почему MFA необходимо для входа в систему.</span><span class="sxs-lookup"><span data-stu-id="b1676-131">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="b1676-132">Регистрация для дополнительного метода проверки</span><span class="sxs-lookup"><span data-stu-id="b1676-132">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="b1676-133">Вход после регистрации</span><span class="sxs-lookup"><span data-stu-id="b1676-133">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="b1676-134">Изменение дополнительного метода проверки</span><span class="sxs-lookup"><span data-stu-id="b1676-134">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="b1676-135">Как работать с такими ситуациями, как новый смарт-телефон</span><span class="sxs-lookup"><span data-stu-id="b1676-135">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="b1676-136">Самое важное, убедитесь, что сотрудники понимают, ***когда требование MFA будет направляться*** , чтобы оно не было неожиданным.</span><span class="sxs-lookup"><span data-stu-id="b1676-136">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="b1676-137">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="b1676-137">Step 4.</span></span> <span data-ttu-id="b1676-138">Развертывание требования к MFA для организации или пользователей</span><span class="sxs-lookup"><span data-stu-id="b1676-138">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="b1676-139">В соответствии с выбранным методом требования MFA развертывание проверки подлинности MFA для сотрудников за пределами пилотных тестовых инженеров.</span><span class="sxs-lookup"><span data-stu-id="b1676-139">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="b1676-140">Параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b1676-140">Security defaults</span></span>

<span data-ttu-id="b1676-141">Вы включаете или отключаете параметры безопасности по умолчанию в области **свойств** для Azure Active Directory (Azure AD) на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="b1676-141">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="b1676-142">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="b1676-142">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="b1676-143">Перейдите на [страницу "свойства Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)".</span><span class="sxs-lookup"><span data-stu-id="b1676-143">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="b1676-144">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="b1676-144">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="b1676-145">Нажмите кнопку **Да** , чтобы включить параметры безопасности по умолчанию и **нет** для отключения параметров безопасности по умолчанию, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1676-145">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="b1676-146">Если вы используете [базовые политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), то как вы переходите к использованию параметров безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1676-146">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="b1676-147">Перейдите на [страницу условного доступа — политики](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="b1676-147">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="b1676-148">Выберите каждую базовую политику, **On** включенную в **параметр** , и установите для **нее значение отключено**.</span><span class="sxs-lookup"><span data-stu-id="b1676-148">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="b1676-149">Перейдите на [страницу "свойства Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)".</span><span class="sxs-lookup"><span data-stu-id="b1676-149">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="b1676-150">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="b1676-150">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="b1676-151">Нажмите кнопку **Да** , чтобы включить параметры безопасности по умолчанию и **нет** для отключения параметров безопасности по умолчанию, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1676-151">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="b1676-152">Политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="b1676-152">Conditional Access policies</span></span>

<span data-ttu-id="b1676-153">Создание, Настройка и включение соответствующих политик, включающих группу пользователей, для которых требуется вход в систему MFA.</span><span class="sxs-lookup"><span data-stu-id="b1676-153">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="b1676-154">MFA для пользователя (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="b1676-154">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="b1676-155">Включение учетных записей пользователей для MFA, соответствующих развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b1676-155">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="b1676-156">Поддержка сотрудников</span><span class="sxs-lookup"><span data-stu-id="b1676-156">Supporting your employees</span></span>

<span data-ttu-id="b1676-157">Когда ваши сотрудники регистрируются и начинают вход с помощью MFA, убедитесь, что ИТ ИТ, ИТ отдела или служба технической поддержки могут быстро ответить на вопросы и устранить проблемы.</span><span class="sxs-lookup"><span data-stu-id="b1676-157">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="b1676-158">В этой статье приведены [сведения об устранении неполадок входа в MFA](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="b1676-158">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


