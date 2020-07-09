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
description: Сведения о настройке многофакторной проверки подлинности для организации.
monikerRange: o365-worldwide
ms.openlocfilehash: b0fd16fc74319c88a6f91bf56ac96346915c35ac
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049764"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="11b17-103">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="11b17-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="11b17-104">С учетом знакомства с [многофакторной проверкой подлинности (MFA) и ее поддержкой в Microsoft 365](multi-factor-authentication-microsoft-365.md) пришло время развернуть и настроить ее для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="11b17-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="11b17-105">Перед началом работы определите, применимы ли к вам следующие особые условия, и выполните соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="11b17-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="11b17-106">Если у вас есть клиенты Office 2013 на устройствах с Windows, [включите современную проверку подлинности](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="11b17-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="11b17-107">Если вы используете сторонние службы каталогов в службах федерации Active Directory (AD FS), настройте сервер Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="11b17-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="11b17-108">Дополнительные сведения см. в статье [Расширенные сценарии с использованием многофакторной проверки подлинности Azure и сторонних решений VPN](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="11b17-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="11b17-109">У всех остальных пользователей дополнительная проверка подлинности будет запрашиваться при необходимости.</span><span class="sxs-lookup"><span data-stu-id="11b17-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="11b17-110">Дополнительные сведения см. в статье [Метод и параметры двухфакторной проверки подлинности](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span><span class="sxs-lookup"><span data-stu-id="11b17-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="11b17-111">Шаг 1. Определение того, как требовать от пользователей применения MFA</span><span class="sxs-lookup"><span data-stu-id="11b17-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="11b17-112">Чтобы настроить или изменить MFA, вы должны быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="11b17-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="11b17-113">Существует три способа требовать от пользователей применения MFA для входа. Дополнительные сведения см. в статье [Поддержка MFA в Microsoft 365](multi-factor-authentication-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="11b17-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="11b17-114">Параметры безопасности по умолчанию (рекомендуется для малого бизнеса)</span><span class="sxs-lookup"><span data-stu-id="11b17-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="11b17-115">Если вы приобрели подписку или пробную версию после 21 октября 2019 г. и неожиданно получили запрос на использование MFA, значит для вашей подписки автоматически включены [параметры безопасности, используемые по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="11b17-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="11b17-116">В каждой новой подписке на Microsoft 365 автоматически включены параметры безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11b17-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="11b17-117">Это означает, что каждому пользователю потребуется настроить MFA и установить приложение Microsoft Authenticator на своем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="11b17-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="11b17-118">Все пользователи должны использовать приложение Microsoft Authenticator в качестве дополнительного метода проверки подлинности, а устаревшая проверка подлинности блокируется.</span><span class="sxs-lookup"><span data-stu-id="11b17-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="11b17-119">Политики условного доступа (рекомендуется для корпораций)</span><span class="sxs-lookup"><span data-stu-id="11b17-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="11b17-120">Пользователи выбирают дополнительный метод проверки подлинности во время регистрации MFA.</span><span class="sxs-lookup"><span data-stu-id="11b17-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="11b17-121">Для отдельных учетных записей пользователей (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="11b17-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="11b17-122">Пользователи выбирают дополнительный метод проверки подлинности во время регистрации MFA.</span><span class="sxs-lookup"><span data-stu-id="11b17-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="11b17-123">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="11b17-123">Step 2.</span></span> <span data-ttu-id="11b17-124">Проверка MFA на пилотных пользователях</span><span class="sxs-lookup"><span data-stu-id="11b17-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="11b17-125">Если вы используете политики условного доступа или MFA для отдельных пользователей (не рекомендуется), выберите пилотных пользователей в компании или организации, чтобы проверить регистрацию в MFA и вход. Например:</span><span class="sxs-lookup"><span data-stu-id="11b17-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="11b17-126">Для политик условного доступа создайте группу пилотных пользователей и политику, требующую применения MFA для участников группы и всех приложений.</span><span class="sxs-lookup"><span data-stu-id="11b17-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="11b17-127">Затем добавьте в группу учетные записи пилотных пользователей.</span><span class="sxs-lookup"><span data-stu-id="11b17-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="11b17-128">Для MFA, применяемой для отдельных пользователей, включайте MFA для каждой учетной записи пилотных пользователей по отдельности.</span><span class="sxs-lookup"><span data-stu-id="11b17-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="11b17-129">Взаимодействуйте со своими пилотными пользователями для ответов на вопросы и устранения проблем, чтобы подготовить беспроблемное развертывание в организации.</span><span class="sxs-lookup"><span data-stu-id="11b17-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="11b17-130">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="11b17-130">Step 3.</span></span> <span data-ttu-id="11b17-131">Информирование организации о предстоящем внедрении MFA</span><span class="sxs-lookup"><span data-stu-id="11b17-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="11b17-132">Используйте уведомления по электронной почте, настенные плакаты, собрания команд и формальное обучение, чтобы обеспечить понимание сотрудниками следующего:</span><span class="sxs-lookup"><span data-stu-id="11b17-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="11b17-133">Почему для входов требуется MFA</span><span class="sxs-lookup"><span data-stu-id="11b17-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="11b17-134">Как зарегистрировать дополнительный метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="11b17-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="11b17-135">Как войти после регистрации</span><span class="sxs-lookup"><span data-stu-id="11b17-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="11b17-136">Как изменить дополнительный метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="11b17-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="11b17-137">Что делать в таких ситуациях, как приобретение нового смартфона</span><span class="sxs-lookup"><span data-stu-id="11b17-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="11b17-138">Важнее всего убедиться, что сотрудники понимают, ***когда требование MFA будет применено***, чтобы оно не стало неожиданным.</span><span class="sxs-lookup"><span data-stu-id="11b17-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="11b17-139">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="11b17-139">Step 4.</span></span> <span data-ttu-id="11b17-140">Развертывание требования MFA для организации или пользователей</span><span class="sxs-lookup"><span data-stu-id="11b17-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="11b17-141">На основе выбранного метода требования MFA разверните многофакторную проверку подлинности (MFA) для сотрудников за пределами пилотных тестировщиков.</span><span class="sxs-lookup"><span data-stu-id="11b17-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="11b17-142">Параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="11b17-142">Security defaults</span></span>

<span data-ttu-id="11b17-143">Включить или отключить параметры безопасности по умолчанию можно на портале Azure в области **Свойства** для Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="11b17-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="11b17-144">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="11b17-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="11b17-145">Выберите [Azure Active Directory — страница "Свойства"](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="11b17-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="11b17-146">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="11b17-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="11b17-147">Выберите **Да**, чтобы включить параметры безопасности по умолчанию, или **Нет**, чтобы их отключить, а затем нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="11b17-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="11b17-148">Если вы используете [базовые политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), вы можете перейти к использованию параметров безопасности по умолчанию следующим образом.</span><span class="sxs-lookup"><span data-stu-id="11b17-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="11b17-149">Выберите [Условный доступ — страница "Политики"](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="11b17-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="11b17-150">Выберите все базовые политики в состоянии **Вкл.** и установите для параметра **Включить политику** состояние **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="11b17-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="11b17-151">Выберите [Azure Active Directory — страница "Свойства"](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="11b17-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="11b17-152">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="11b17-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="11b17-153">Выберите **Да**, чтобы включить параметры безопасности по умолчанию, или **Нет**, чтобы их отключить, а затем нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="11b17-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="11b17-154">Политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="11b17-154">Conditional Access policies</span></span>

<span data-ttu-id="11b17-155">Создавайте, настраивайте и включайте соответствующие политики, содержащие группу пользователей, которым требуется применять MFA для входа.</span><span class="sxs-lookup"><span data-stu-id="11b17-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="11b17-156">MFA для отдельных пользователей (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="11b17-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="11b17-157">Включите учетные записи пользователей для MFA в соответствии с развертыванием.</span><span class="sxs-lookup"><span data-stu-id="11b17-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="11b17-158">Поддержка сотрудников</span><span class="sxs-lookup"><span data-stu-id="11b17-158">Supporting your employees</span></span>

<span data-ttu-id="11b17-159">Когда сотрудники выполняют регистрацию и начинают входить с помощью MFA, убедитесь, что ваши ИТ-специалисты, ИТ-отдел или служба поддержки могут отвечать на вопросы и быстро устранять проблемы.</span><span class="sxs-lookup"><span data-stu-id="11b17-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="11b17-160">См. в этой статье [сведения об устранении неполадок с входами с MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="11b17-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


