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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Узнайте, как использовать параметры безопасности по умолчанию для настройки многофакторной проверки подлинности для пользователей.
monikerRange: o365-worldwide
ms.openlocfilehash: 1000689794b8b5471efa898e731fd75a0e5a8cce
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665636"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="f62a5-103">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f62a5-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f62a5-104">Если вы приобрели подписку или пробную версию после 21 октября 2019 г., а вы неожиданно запрашиваете многофакторную проверку подлинности (MFA), для вашей подписки автоматически включена поддержка [по умолчанию для безопасности](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) .</span><span class="sxs-lookup"><span data-stu-id="f62a5-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="f62a5-105">Для каждой новой подписки Microsoft 365 автоматически будут включены [Параметры безопасности по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) .</span><span class="sxs-lookup"><span data-stu-id="f62a5-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="f62a5-106">Это означает, что каждый пользователь должен будет настроить многофакторную проверку подлинности (MFA) и установить приложение Microsoft Authenticator на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="f62a5-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="f62a5-107">Дополнительные сведения см. [в разделе Настройка MFA для учетной записи Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="f62a5-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="f62a5-108">Потребуются следующие девять ролей администраторов для дополнительной проверки подлинности при каждом входе:</span><span class="sxs-lookup"><span data-stu-id="f62a5-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="f62a5-109">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="f62a5-109">Global administrator</span></span>
- <span data-ttu-id="f62a5-110">Администратор SharePoint</span><span class="sxs-lookup"><span data-stu-id="f62a5-110">SharePoint administrator</span></span>
- <span data-ttu-id="f62a5-111">Администратор Exchange</span><span class="sxs-lookup"><span data-stu-id="f62a5-111">Exchange administrator</span></span>
- <span data-ttu-id="f62a5-112">Администратор условного доступа</span><span class="sxs-lookup"><span data-stu-id="f62a5-112">Conditional Access administrator</span></span>
- <span data-ttu-id="f62a5-113">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="f62a5-113">Security administrator</span></span>
- <span data-ttu-id="f62a5-114">Администратор службы технической поддержки и администратор паролей</span><span class="sxs-lookup"><span data-stu-id="f62a5-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="f62a5-115">Администратор выставления счетов</span><span class="sxs-lookup"><span data-stu-id="f62a5-115">Billing administrator</span></span>
- <span data-ttu-id="f62a5-116">Администратор пользователей</span><span class="sxs-lookup"><span data-stu-id="f62a5-116">User administrator</span></span>
- <span data-ttu-id="f62a5-117">Администратор проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f62a5-117">Authentication administrator</span></span>

<span data-ttu-id="f62a5-118">У всех остальных пользователей дополнительная проверка подлинности будет запрашиваться при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f62a5-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="f62a5-119">Для настройки и изменения MFA необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="f62a5-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="f62a5-120">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="f62a5-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="f62a5-121">Если вы уже настроили MFA с помощью базовых политик, [необходимо отключить их, чтобы включить параметры по умолчанию для безопасности](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="f62a5-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="f62a5-122">Однако если у вас есть Microsoft 365 бизнес или ваша подписка включает [Azure Active Directory Premium P1 или Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), вы также можете настроить политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) .</span><span class="sxs-lookup"><span data-stu-id="f62a5-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="f62a5-123">Чтобы использовать политики условного доступа, необходимо убедиться в том, что параметры безопасности по умолчанию отключены, а [современная проверка подлинности](#enable-modern-authentication-for-your-organization) включена.</span><span class="sxs-lookup"><span data-stu-id="f62a5-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="f62a5-124">Чтобы объяснить пользователям, как настроить приложение для проверки подлинности (Майкрософт), ознакомьтесь со статьей [Использование средства проверки подлинности Майкрософт в Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span><span class="sxs-lookup"><span data-stu-id="f62a5-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="f62a5-125">Управление параметрами безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f62a5-125">Manage security defaults</span></span>

1. <span data-ttu-id="f62a5-126">Войдите в [центр администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="f62a5-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="f62a5-127">Перейдите на [страницу "свойства Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)".</span><span class="sxs-lookup"><span data-stu-id="f62a5-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="f62a5-128">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="f62a5-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="f62a5-129">Нажмите кнопку **Да** , чтобы включить параметры безопасности по умолчанию и **нет** для отключения параметров безопасности по умолчанию, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f62a5-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="f62a5-130">Переход с базовых политик на параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f62a5-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="f62a5-131">Перейдите на [страницу условного доступа — политики](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="f62a5-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="f62a5-132">Выберите каждую базовую политику, **On** включенную в **параметр** , и установите для **нее значение отключено**.</span><span class="sxs-lookup"><span data-stu-id="f62a5-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="f62a5-133">Перейдите на [страницу "свойства Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)".</span><span class="sxs-lookup"><span data-stu-id="f62a5-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="f62a5-134">В нижней части страницы выберите **Управление параметрами безопасности по умолчанию**, а затем в области **включить** параметры безопасности по умолчанию установите переключатель **включить параметры безопасности по умолчанию** в значение **Да**, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f62a5-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="f62a5-135">Включение современной проверки подлинности в Организации</span><span class="sxs-lookup"><span data-stu-id="f62a5-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="f62a5-136">Все клиентские приложения Office 2016 поддерживают многофакторную проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="f62a5-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="f62a5-137">Это означает, что для клиентов Office 2016 пароли приложений необязательны.</span><span class="sxs-lookup"><span data-stu-id="f62a5-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="f62a5-138">Тем не менее, необходимо убедиться, что для подписки Microsoft 365 включена поддержка ADAL или современная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="f62a5-138">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="f62a5-139">Чтобы включить современную проверку подлинности, в [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) выберите **Параметры** \> **Параметры**, затем на вкладке **Службы** выберите в списке **Современная проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="f62a5-139">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="f62a5-140">Установите флажок **включить современная проверка подлинности (рекомендуется)** на панели **современная проверка подлинности** и нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="f62a5-140">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Область "Современная проверка подлинности" с установленным флажком включения.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="f62a5-142">В августе 2017 г. все новые подписки на Microsoft 365, в которые входит Skype для бизнеса Online и Exchange Online, по умолчанию включены современные проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f62a5-142">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="f62a5-143">Чтобы проверить состояние современной проверки подлинности для Skype для бизнеса Online, можно использовать PowerShell в Skype для бизнеса Online с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="f62a5-143">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="f62a5-144">Выполните команду Get-CsOAuthConfiguration, чтобы проверить значение параметра -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="f62a5-144">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="f62a5-145">Если у параметра -ClientADALAuthOverride значение "Разрешено", современная проверка подлинности включена.</span><span class="sxs-lookup"><span data-stu-id="f62a5-145">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="f62a5-146">Чтобы узнать состояние современной проверки подлинности для Exchange Online, см. статью [Включение современной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="f62a5-146">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="f62a5-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f62a5-147">Related articles</span></span>

[<span data-ttu-id="f62a5-148">10 основных способов защиты Microsoft 365 для бизнес-планов</span><span class="sxs-lookup"><span data-stu-id="f62a5-148">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="f62a5-149">Включение современной проверки подлинности для Office 2013 на устройствах с Windows</span><span class="sxs-lookup"><span data-stu-id="f62a5-149">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
