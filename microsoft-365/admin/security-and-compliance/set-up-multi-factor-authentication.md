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
ms.openlocfilehash: 4a829aa597596564b9c2f468e72f3a766b198372
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627684"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="0ab59-103">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="0ab59-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0ab59-104">Если вы приобрели подписку или пробную версию после 21 октября 2019 г., а вы неожиданно запрашиваете MFA, для подписки автоматически включается параметр [безопасности по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) .</span><span class="sxs-lookup"><span data-stu-id="0ab59-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="0ab59-105">Для каждой новой подписки Microsoft 365 автоматически будут включены параметры безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0ab59-105">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="0ab59-106">Это означает, что каждому пользователю потребуется настроить многофакторную проверку подлинности (MFA) и установить приложение для проверки подлинности на своем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="0ab59-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="0ab59-107">Дополнительные сведения см. в [статье Настройка проверки на 2 этапа для Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="0ab59-107">For more information, see [Set up 2-step verification for Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="0ab59-108">Потребуются следующие девять ролей администраторов для дополнительной проверки подлинности при каждом входе:</span><span class="sxs-lookup"><span data-stu-id="0ab59-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="0ab59-109">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="0ab59-109">Global administrator</span></span>
- <span data-ttu-id="0ab59-110">Администратор SharePoint</span><span class="sxs-lookup"><span data-stu-id="0ab59-110">SharePoint administrator</span></span>
- <span data-ttu-id="0ab59-111">Администратор Exchange</span><span class="sxs-lookup"><span data-stu-id="0ab59-111">Exchange administrator</span></span>
- <span data-ttu-id="0ab59-112">Администратор условного доступа</span><span class="sxs-lookup"><span data-stu-id="0ab59-112">Conditional Access administrator</span></span>
- <span data-ttu-id="0ab59-113">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="0ab59-113">Security administrator</span></span>
- <span data-ttu-id="0ab59-114">Администратор службы технической поддержки и администратор паролей</span><span class="sxs-lookup"><span data-stu-id="0ab59-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="0ab59-115">Администратор выставления счетов</span><span class="sxs-lookup"><span data-stu-id="0ab59-115">Billing administrator</span></span>
- <span data-ttu-id="0ab59-116">Администратор пользователей</span><span class="sxs-lookup"><span data-stu-id="0ab59-116">User administrator</span></span>
- <span data-ttu-id="0ab59-117">Администратор проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="0ab59-117">Authentication administrator</span></span>

<span data-ttu-id="0ab59-118">У всех остальных пользователей дополнительная проверка подлинности будет запрашиваться при необходимости.</span><span class="sxs-lookup"><span data-stu-id="0ab59-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="0ab59-119">Дополнительные сведения см. в статье [Что такое параметры безопасности по умолчанию?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="0ab59-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="0ab59-120">Для установки или изменения многофакторной проверки подлинности необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="0ab59-120">You must be a global admin to set up or modify multi-factor authentication.</span></span> <br><br>
> <span data-ttu-id="0ab59-121">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="0ab59-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="0ab59-122">Если вы ранее настроили MFA с использованием базовых политик, [потребуется отключить их и включить параметры безопасности по умолчанию](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="0ab59-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="0ab59-123">Но если вы используете Microsoft 365 бизнес или ваша подписка включает [Azure Active Directory Premium 1 или Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), вы также можете настроить политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="0ab59-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="0ab59-124">Чтобы использовать политики условного доступа, необходимо убедиться, что включена [современная проверка подлинности](#enable-modern-authentication-for-your-organization) .</span><span class="sxs-lookup"><span data-stu-id="0ab59-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="0ab59-125">Чтобы объяснить пользователям, как настроить приложение Authenticator, посетите раздел [Использование Microsoft Authenticator для Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="0ab59-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="0ab59-126">Управление параметрами безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0ab59-126">Manage security defaults</span></span>

1. <span data-ttu-id="0ab59-127">Войдите в [Центр администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="0ab59-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="0ab59-128">Перейдите в раздел [Свойства Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="0ab59-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="0ab59-129">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="0ab59-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="0ab59-130">Нажмите кнопку **Да**, чтобы включить параметры безопасности по умолчанию, или **Нет**, чтобы их отключить.</span><span class="sxs-lookup"><span data-stu-id="0ab59-130">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="0ab59-131">Переход с базовых политик на параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0ab59-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="0ab59-132">В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) выберите пункт **Установка**.</span><span class="sxs-lookup"><span data-stu-id="0ab59-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="0ab59-133">Рядом с надписью **Вход и безопасность** в разделе **Повышение безопасности входа** нажмите кнопку **Просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="0ab59-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="0ab59-134">В разделе **Повышение безопасности входа** нажмите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="0ab59-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="0ab59-135">**На странице**" **Условный доступ к политикам** " выберите каждую базовую политику и присвойте ей значение " **отключено**".</span><span class="sxs-lookup"><span data-stu-id="0ab59-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="0ab59-136">Откройте страницу [свойств Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="0ab59-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="0ab59-137">В нижней части страницы выберите **Управление параметрами безопасности по умолчанию**, а затем в области **включить** параметры безопасности по умолчанию установите переключатель **включить параметры безопасности по умолчанию** в значение **Да**, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0ab59-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="0ab59-138">Включение современной проверки подлинности в Организации</span><span class="sxs-lookup"><span data-stu-id="0ab59-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="0ab59-139">Все клиентские приложения Office 2016 поддерживают многофакторную проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="0ab59-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="0ab59-140">Это означает, что для клиентов Office 2016 пароли приложений необязательны.</span><span class="sxs-lookup"><span data-stu-id="0ab59-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="0ab59-141">Тем не менее, необходимо убедиться, что для подписки Microsoft 365 включена поддержка ADAL или современная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0ab59-141">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="0ab59-142">Чтобы включить современную проверку подлинности, в [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) выберите **Параметры** \> **Параметры**, затем на вкладке **Службы** выберите в списке **Современная проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="0ab59-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="0ab59-143">Установите флажок **включить современная проверка подлинности (рекомендуется)** на панели **современная проверка подлинности** и нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="0ab59-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Область "Современная проверка подлинности" с установленным флажком включения.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="0ab59-145">В августе 2017 г. все новые подписки на Microsoft 365, в которые входит Skype для бизнеса Online и Exchange Online, по умолчанию включены современные проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0ab59-145">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="0ab59-146">Чтобы проверить состояние современной проверки подлинности для Skype для бизнеса Online, можно использовать PowerShell в Skype для бизнеса Online с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="0ab59-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="0ab59-147">Выполните команду Get-CsOAuthConfiguration, чтобы проверить значение параметра -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="0ab59-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="0ab59-148">Если у параметра -ClientADALAuthOverride значение "Разрешено", современная проверка подлинности включена.</span><span class="sxs-lookup"><span data-stu-id="0ab59-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="0ab59-149">Чтобы узнать состояние современной проверки подлинности для Exchange Online, см. статью [Включение современной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="0ab59-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="0ab59-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0ab59-150">Related articles</span></span>

[<span data-ttu-id="0ab59-151">10 основных способов защиты Microsoft 365 для бизнес-планов</span><span class="sxs-lookup"><span data-stu-id="0ab59-151">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="0ab59-152">Включение современной проверки подлинности для Office 2013 на устройствах с Windows</span><span class="sxs-lookup"><span data-stu-id="0ab59-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
