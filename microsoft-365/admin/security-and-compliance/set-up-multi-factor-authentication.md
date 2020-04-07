---
title: Настройка многофакторной проверки подлинности для Office 365
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
description: Сведения об использовании параметров безопасности по умолчанию с целью настройки многофакторной проверки подлинности для пользователей Office 365.
monikerRange: o365-worldwide
ms.openlocfilehash: 331552a4de21198fe7fbc9980e89bfcd87449ffa
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153560"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="994da-103">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="994da-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="994da-104">Если вы приобрели подписку или пробную версию после 21 октября 2019 г., а вы неожиданно запрашиваете многофакторную проверку подлинности (MFA), для вашей подписки автоматически включена поддержка [по умолчанию для безопасности](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) .</span><span class="sxs-lookup"><span data-stu-id="994da-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="994da-105">В каждой новой подписке на Office 365 для бизнеса или Microsoft 365 бизнес автоматически включены параметры безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="994da-105">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="994da-106">Это означает, что каждый пользователь должен настроить MFA и установить приложение Microsoft Authenticator на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="994da-106">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="994da-107">Дополнительные сведения см. в статье [Настройка двухфакторной проверки подлинности для Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="994da-107">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="994da-108">Потребуются следующие девять ролей администраторов для дополнительной проверки подлинности при каждом входе:</span><span class="sxs-lookup"><span data-stu-id="994da-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="994da-109">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="994da-109">Global administrator</span></span>
- <span data-ttu-id="994da-110">Администратор SharePoint</span><span class="sxs-lookup"><span data-stu-id="994da-110">SharePoint administrator</span></span>
- <span data-ttu-id="994da-111">Администратор Exchange</span><span class="sxs-lookup"><span data-stu-id="994da-111">Exchange administrator</span></span>
- <span data-ttu-id="994da-112">Администратор условного доступа</span><span class="sxs-lookup"><span data-stu-id="994da-112">Conditional Access administrator</span></span>
- <span data-ttu-id="994da-113">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="994da-113">Security administrator</span></span>
- <span data-ttu-id="994da-114">Администратор службы технической поддержки и администратор паролей</span><span class="sxs-lookup"><span data-stu-id="994da-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="994da-115">Администратор выставления счетов</span><span class="sxs-lookup"><span data-stu-id="994da-115">Billing administrator</span></span>
- <span data-ttu-id="994da-116">Администратор пользователей</span><span class="sxs-lookup"><span data-stu-id="994da-116">User administrator</span></span>
- <span data-ttu-id="994da-117">Администратор проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="994da-117">Authentication administrator</span></span>

<span data-ttu-id="994da-118">У всех остальных пользователей дополнительная проверка подлинности будет запрашиваться при необходимости.</span><span class="sxs-lookup"><span data-stu-id="994da-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="994da-119">Дополнительные сведения см. в статье [Что такое параметры безопасности по умолчанию?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="994da-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="994da-120">Для установки или изменения MFA необходимо быть глобальным администратором Office 365.</span><span class="sxs-lookup"><span data-stu-id="994da-120">You must be an Office 365 global admin to set up or modify MFA.</span></span> <br><br>
> <span data-ttu-id="994da-121">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="994da-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="994da-122">Если вы ранее настроили MFA с использованием базовых политик, [потребуется отключить их и включить параметры безопасности по умолчанию](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="994da-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="994da-123">Однако если у вас есть Microsoft 365 бизнес или ваша подписка включает [Azure Active Directory Premium P1 или Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), вы также можете настроить политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) .</span><span class="sxs-lookup"><span data-stu-id="994da-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="994da-124">Чтобы использовать политики условного доступа, необходимо убедиться, что включена [современная проверка подлинности](#enable-modern-authentication-for-your-organization) .</span><span class="sxs-lookup"><span data-stu-id="994da-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="994da-125">Чтобы объяснить пользователям, как настроить приложение Authenticator, посетите раздел [Использование Microsoft Authenticator для Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="994da-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="994da-126">Управление параметрами безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="994da-126">Manage security defaults</span></span>

1. <span data-ttu-id="994da-127">Войдите в [Центр администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="994da-127">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="994da-128">Перейдите в раздел [свойств Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="994da-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="994da-129">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="994da-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="994da-130">Нажмите кнопку **Да** , чтобы включить параметры безопасности по умолчанию или **нет** , чтобы отключить параметры безопасности по умолчанию, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="994da-130">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="994da-131">Переход с базовых политик на параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="994da-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="994da-132">В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) выберите пункт **Установка**.</span><span class="sxs-lookup"><span data-stu-id="994da-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="994da-133">Рядом с надписью **Вход и безопасность** в разделе **Повышение безопасности входа** нажмите кнопку **Просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="994da-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="994da-134">В разделе **Повышение безопасности входа** нажмите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="994da-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="994da-135">На странице **Условный доступ — Политики** портала Azure выберите все базовые политики со значением **Вкл** и присвойте им значение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="994da-135">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="994da-136">Откройте страницу [свойств Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="994da-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="994da-137">В нижней части страницы щелкните ссылку **Управление параметрами безопасности по умолчанию** и в области **Включение параметров безопасности по умолчанию** установите переключатель **Включение параметров безопасности по умолчанию** в положение **Да**.</span><span class="sxs-lookup"><span data-stu-id="994da-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="994da-138">Включение современной проверки подлинности в Организации</span><span class="sxs-lookup"><span data-stu-id="994da-138">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="994da-139">Все клиентские приложения Office 2016 поддерживают многофакторную проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="994da-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="994da-140">Это означает, что для клиентов Office 2016 пароли приложений необязательны.</span><span class="sxs-lookup"><span data-stu-id="994da-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="994da-141">Однако необходимо убедиться, что ваша подписка на Office 365 поддерживает ADAL или современную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="994da-141">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="994da-142">Чтобы включить современную проверку подлинности, в [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) выберите **Параметры** \> **Параметры**, затем на вкладке **Службы** выберите в списке **Современная проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="994da-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="994da-143">Установите флажок **Включить функцию "Современная проверка подлинности"** в области **Современная проверка подлинности‎**.</span><span class="sxs-lookup"><span data-stu-id="994da-143">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![Область "Современная проверка подлинности" с установленным флажком включения.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="994da-145">С августа 2017 года во всех новых клиентах Office 365, включающих Skype для бизнеса Online и Exchange Online, современная проверка подлинности включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="994da-145">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="994da-146">Чтобы проверить состояние современной проверки подлинности для Skype для бизнеса Online, можно использовать PowerShell в Skype для бизнеса Online с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="994da-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="994da-147">Выполните команду Get-CsOAuthConfiguration, чтобы проверить значение параметра -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="994da-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="994da-148">Если у параметра -ClientADALAuthOverride значение "Разрешено", современная проверка подлинности включена.</span><span class="sxs-lookup"><span data-stu-id="994da-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="994da-149">Чтобы узнать состояние современной проверки подлинности для Exchange Online, см. статью [Включение современной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="994da-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="994da-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="994da-150">Related articles</span></span>

<span data-ttu-id="994da-151">[10 основных способов защиты планов Office 365 и Microsoft 365 для бизнеса](secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="994da-151">[Top 10 ways to secure Office 365 and Microsoft 365 Business plans](secure-your-business-data.md)</span></span>

[<span data-ttu-id="994da-152">Включение современной проверки подлинности для Office 2013 на устройствах с Windows</span><span class="sxs-lookup"><span data-stu-id="994da-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
