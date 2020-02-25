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
ms.openlocfilehash: bc906299e42929dd4dd09b94502a6d463a5971b4
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257192"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="86664-103">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="86664-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="86664-104">В каждой новой подписке на Office 365 для бизнеса или Microsoft 365 бизнес автоматически включены параметры безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="86664-104">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="86664-105">Это означает, что каждому пользователю потребуется настроить многофакторную проверку подлинности (MFA) и установить приложение для проверки подлинности на своем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="86664-105">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="86664-106">Дополнительные сведения см. в статье [Настройка двухфакторной проверки подлинности для Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="86664-106">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="86664-107">Потребуются следующие девять ролей администраторов для дополнительной проверки подлинности при каждом входе:</span><span class="sxs-lookup"><span data-stu-id="86664-107">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="86664-108">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="86664-108">Global administrator</span></span>
- <span data-ttu-id="86664-109">Администратор SharePoint</span><span class="sxs-lookup"><span data-stu-id="86664-109">SharePoint administrator</span></span>
- <span data-ttu-id="86664-110">Администратор Exchange</span><span class="sxs-lookup"><span data-stu-id="86664-110">Exchange administrator</span></span>
- <span data-ttu-id="86664-111">Администратор условного доступа</span><span class="sxs-lookup"><span data-stu-id="86664-111">Conditional Access administrator</span></span>
- <span data-ttu-id="86664-112">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="86664-112">Security administrator</span></span>
- <span data-ttu-id="86664-113">Администратор службы технической поддержки и администратор паролей</span><span class="sxs-lookup"><span data-stu-id="86664-113">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="86664-114">Администратор выставления счетов</span><span class="sxs-lookup"><span data-stu-id="86664-114">Billing administrator</span></span>
- <span data-ttu-id="86664-115">Администратор пользователей</span><span class="sxs-lookup"><span data-stu-id="86664-115">User administrator</span></span>
- <span data-ttu-id="86664-116">Администратор проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="86664-116">Authentication administrator</span></span>

<span data-ttu-id="86664-117">У всех остальных пользователей дополнительная проверка подлинности будет запрашиваться при необходимости.</span><span class="sxs-lookup"><span data-stu-id="86664-117">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="86664-118">Дополнительные сведения см. в статье [Что такое параметры безопасности по умолчанию?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="86664-118">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="86664-p103">Настройку и изменение многофакторной проверки подлинности могут осуществлять только глобальные администраторы Office 365. </span><span class="sxs-lookup"><span data-stu-id="86664-p103">You must be an Office 365 global admin to set up or modify multi-factor authentication. </span></span><br><br>
> <span data-ttu-id="86664-120">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="86664-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="86664-121">Если вы ранее настроили MFA с использованием базовых политик, [потребуется отключить их и включить параметры безопасности по умолчанию](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="86664-121">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="86664-122">Но если вы используете Microsoft 365 бизнес или ваша подписка включает [Azure Active Directory Premium 1 или Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), вы также можете настроить политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="86664-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="86664-123">Чтобы использовать политики условного доступа, убедитесь, что [включена современная проверка подлинности](#enable-multi-factor-authentication-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="86664-123">To use conditional access policies, you need to make sure [modern authentication is enabled](#enable-multi-factor-authentication-for-your-organization).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="86664-124">Управление параметрами безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="86664-124">Manage security defaults</span></span>

1. <span data-ttu-id="86664-125">Войдите в [Центр администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="86664-125">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="86664-126">Перейдите в раздел [свойств Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="86664-126">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="86664-127">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="86664-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="86664-128">Нажмите кнопку **Да**, чтобы включить параметры безопасности по умолчанию, или **Нет**, чтобы их отключить.</span><span class="sxs-lookup"><span data-stu-id="86664-128">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="86664-129">Переход с базовых политик на параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="86664-129">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="86664-130">В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) выберите пункт **Установка**.</span><span class="sxs-lookup"><span data-stu-id="86664-130">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="86664-131">Рядом с надписью **Вход и безопасность** в разделе **Повышение безопасности входа** нажмите кнопку **Просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="86664-131">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="86664-132">В разделе **Повышение безопасности входа** нажмите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="86664-132">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="86664-133">На странице **Условный доступ — Политики** портала Azure выберите все базовые политики со значением **Вкл** и присвойте им значение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="86664-133">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="86664-134">Откройте страницу [свойств Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="86664-134">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="86664-135">В нижней части страницы щелкните ссылку **Управление параметрами безопасности по умолчанию** и в области **Включение параметров безопасности по умолчанию** установите переключатель **Включение параметров безопасности по умолчанию** в положение **Да**.</span><span class="sxs-lookup"><span data-stu-id="86664-135">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="86664-136">Включение современной проверки подлинности в Организации</span><span class="sxs-lookup"><span data-stu-id="86664-136">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="86664-137">Все клиентские приложения Office 2016 поддерживают многофакторную проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="86664-137">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="86664-138">Это означает, что для клиентов Office 2016 пароли приложений необязательны.</span><span class="sxs-lookup"><span data-stu-id="86664-138">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="86664-139">Однако необходимо убедиться, что ваша подписка на Office 365 поддерживает ADAL или современную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="86664-139">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="86664-140">Чтобы включить современную проверку подлинности, в [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) выберите **Параметры** \> **Параметры**, затем на вкладке **Службы** выберите в списке **Современная проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="86664-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="86664-141">Установите флажок **Включить функцию "Современная проверка подлинности"** в области **Современная проверка подлинности‎**.</span><span class="sxs-lookup"><span data-stu-id="86664-141">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![Область "Современная проверка подлинности" с установленным флажком включения.](../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a><span data-ttu-id="86664-143">Включение многофакторной проверки подлинности для организации</span><span class="sxs-lookup"><span data-stu-id="86664-143">Enable multi-factor authentication for your organization</span></span>
    
1. <span data-ttu-id="86664-144">В [центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822)выберите **Пользователи** и **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="86664-144">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Users** and **Active Users**.</span></span>

2. <span data-ttu-id="86664-145">В разделе **Активные пользователи** выберите **многофакторную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="86664-145">In the **Active Users** section, Click on  **multi-factor authentication**.</span></span>

3. <span data-ttu-id="86664-146">На странице **многофакторная проверка подлинности** выберите пункт **пользователь** , если вы включите его для одного пользователя или можете выполните **массовое обновление**.</span><span class="sxs-lookup"><span data-stu-id="86664-146">On the **Multi-factor authentication** page, select **user** if you are enabling this for one user Or you can peform a **Bulk Update**.</span></span>

4. <span data-ttu-id="86664-147">В разделе **быстрые действия**выберите **включить** .</span><span class="sxs-lookup"><span data-stu-id="86664-147">CLick on **Enable** under **Quick Steps**.</span></span>

5. <span data-ttu-id="86664-148">Во всплывающем окне Кликкк **включить многофакторную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="86664-148">In the Pop-up window, CLickc on **Enable Multi-Factor Authentication**.</span></span>

<span data-ttu-id="86664-149">После настройки многофакторной проверки подлинности для организации вашим пользователям потребуется настроить двухфакторную проверку на своих устройствах.</span><span class="sxs-lookup"><span data-stu-id="86664-149">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="86664-150">Дополнительные сведения см. в статье [Настройка двухфакторной проверки подлинности для Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="86664-150">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>
    
> [!TIP]
> <span data-ttu-id="86664-151">Чтобы объяснить пользователям, как настроить приложение Authenticator, посетите раздел [Использование Microsoft Authenticator для Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="86664-151">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="86664-152">С августа 2017 года во всех новых клиентах Office 365, включающих Skype для бизнеса Online и Exchange Online, современная проверка подлинности включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="86664-152">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="86664-153">Чтобы проверить состояние современной проверки подлинности для Skype для бизнеса Online, можно использовать PowerShell в Skype для бизнеса Online с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="86664-153">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="86664-154">Выполните команду Get-CsOAuthConfiguration, чтобы проверить значение параметра -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="86664-154">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="86664-155">Если у параметра -ClientADALAuthOverride значение "Разрешено", современная проверка подлинности включена.</span><span class="sxs-lookup"><span data-stu-id="86664-155">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="86664-156">Чтобы узнать состояние современной проверки подлинности для Exchange Online, см. статью [Включение современной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="86664-156">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="86664-157">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="86664-157">Related articles</span></span>

<span data-ttu-id="86664-158">[10 основных способов защиты планов Office 365 и Microsoft 365 для бизнеса](secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="86664-158">[Top 10 ways to secure Office 365 and Microsoft 365 Business plans](secure-your-business-data.md)</span></span>

[<span data-ttu-id="86664-159">Включение современной проверки подлинности для Office 2013 на устройствах с Windows</span><span class="sxs-lookup"><span data-stu-id="86664-159">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
