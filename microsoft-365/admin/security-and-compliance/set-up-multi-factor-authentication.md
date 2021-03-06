---
title: Настройка многофакторной проверки подлинности для пользователей
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.openlocfilehash: d08ef54c545809bbb2277f8d0a8471245400a3ac
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514972"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="dd335-103">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="dd335-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="dd335-104">С учетом знакомства с [многофакторной проверкой подлинности (MFA) и ее поддержкой в Microsoft 365](multi-factor-authentication-microsoft-365.md) пришло время развернуть и настроить ее для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dd335-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd335-105">Если вы приобрели подписку или получили пробную версию после 21 октября 2019 г. и при выполнении входа вам предлагается пройти многофакторную проверку подлинности (MFA), это значит, что к вашей подписке были автоматически применены [параметры безопасности по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="dd335-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dd335-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="dd335-106">Before you begin</span></span>

- <span data-ttu-id="dd335-107">Управлять многофакторной проверкой подлинности (MFA) может только глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="dd335-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="dd335-108">Дополнительные сведения см. в статье [О ролях администраторов](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="dd335-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="dd335-109">Если у вас включена устаревшая MFA для конкретных пользователей, [отключите устаревшую MFA для конкретных пользователей](#turn-off-legacy-per-user-mfa).</span><span class="sxs-lookup"><span data-stu-id="dd335-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="dd335-110">Если у вас есть клиенты Office 2013 на устройствах с Windows, [включите современную проверку подлинности для клиентов Office 2013](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="dd335-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="dd335-111">Дополнительно: если вы используете сторонние службы каталогов со службами федерации Active Directory (AD FS), настройте сервер Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="dd335-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="dd335-112">Дополнительные сведения см. в статье [Расширенные сценарии с использованием многофакторной проверки подлинности Azure AD и сторонних решений VPN](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="dd335-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="dd335-113">Включение и отключение параметров безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="dd335-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="dd335-114">Параметры безопасности по умолчанию обеспечивают подходящий для большинства организаций уровень безопасности при входе в систему.</span><span class="sxs-lookup"><span data-stu-id="dd335-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="dd335-115">Дополнительные сведения см. в статье [Что такое параметры безопасности по умолчанию?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="dd335-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="dd335-116">Если у вас новая подписка, то параметры безопасности по умолчанию могли быть включены автоматически.</span><span class="sxs-lookup"><span data-stu-id="dd335-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="dd335-117">Включить или отключить параметры безопасности по умолчанию можно на портале Azure в области **Свойства** для Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="dd335-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="dd335-118">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="dd335-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="dd335-119">На левой панели навигации нажмите **Показать все** и в разделе **Центры администрирования** выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="dd335-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="dd335-120">В **Центре администрирования Azure Active Directory** выберите **Azure Active Directory** \> **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="dd335-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="dd335-121">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="dd335-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="dd335-122">Выберите **Да**, чтобы включить параметры безопасности по умолчанию, или **Нет**, чтобы их отключить, а затем нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dd335-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="dd335-123">Если у вас включены [базовые политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), вам будет предложено отключить их до перехода к использованию параметров безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dd335-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="dd335-124">Выберите [Условный доступ — страница "Политики"](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="dd335-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="dd335-125">Выберите все базовые политики в состоянии **Вкл.** и установите для параметра **Включить политику** состояние **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="dd335-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="dd335-126">Выберите [Azure Active Directory — страница "Свойства"](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="dd335-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="dd335-127">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="dd335-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="dd335-128">Выберите **Да**, чтобы включить параметры безопасности по умолчанию, или **Нет**, чтобы их отключить, а затем нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dd335-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="dd335-129">Использование политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="dd335-129">Use Conditional Access policies</span></span>

<span data-ttu-id="dd335-130">Если вашей организации нужно значительное количество различных установок безопасности при входе в систему, то политики условного доступа могут предоставить вам дополнительные возможности управления.</span><span class="sxs-lookup"><span data-stu-id="dd335-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="dd335-131">Условный доступ позволяет создавать и определять политики, которые реагируют на события при входе и запрашивают дополнительные действия, прежде чем пользователю будет предоставлен доступ к приложению или службе.</span><span class="sxs-lookup"><span data-stu-id="dd335-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd335-132">Прежде чем включать политики условного доступа, отключите MFA для конкретных пользователей и параметры безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dd335-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="dd335-133">Условный доступ могут использовать клиенты, которые приобрели Azure AD Premium P1 или лицензии, в которые входит эта служба, например Microsoft 365 бизнес премиум или Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="dd335-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="dd335-134">Для получения дополнительной информации см. статью [Создание политик условного доступа](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span><span class="sxs-lookup"><span data-stu-id="dd335-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="dd335-135">Условный доступ на основе риска доступен в рамках лицензии Azure AD Premium P2 или в рамках лицензий, в которую входит эта служба, например Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dd335-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="dd335-136">Дополнительные сведения см. в статье [Условный доступ на основе рисков](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span><span class="sxs-lookup"><span data-stu-id="dd335-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="dd335-137">Дополнительные сведения об Azure AD P1 и P2 см. в статье [Цены для Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="dd335-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="dd335-138">Включение современной проверки подлинности для организации</span><span class="sxs-lookup"><span data-stu-id="dd335-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="dd335-139">В большинстве подписок современная проверка подлинности включена автоматически, но если вы приобрели подписку до августа 2017 г., скорее всего, вам потребуется включить современную проверку подлинности, чтобы такие функции, как многофакторная проверка подлинности, работали в клиентах Windows, например в Outlook.</span><span class="sxs-lookup"><span data-stu-id="dd335-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription before August 2017, it is likely that you will need to turn on Modern Authentication in order to get features like Multi-Factor Authentication to work in Windows clients like Outlook.</span></span>


1. <span data-ttu-id="dd335-140">В Центре администрирования Microsoft 365 на левой панели навигации выберите **Параметры** \> **Параметры организации**.</span><span class="sxs-lookup"><span data-stu-id="dd335-140">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
2. <span data-ttu-id="dd335-141">На вкладке **Службы** выберите **Современная проверка подлинности**, а затем в области **Современная проверка подлинности** установите флажок **Включить современную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="dd335-141">Under the **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="dd335-142">Выберите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="dd335-142">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="dd335-143">Выключение устаревшей MFA для конкретных пользователей</span><span class="sxs-lookup"><span data-stu-id="dd335-143">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="dd335-144">Если у вас включена MFA для конкретных пользователей, перед включением параметров безопасности по умолчанию ее необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="dd335-144">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="dd335-145">В Центре администрирования Microsoft 365 на левой панели навигации выберите **Пользователи** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="dd335-145">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="dd335-146">На странице **Активные пользователи** нажмите **Многофакторная проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="dd335-146">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="dd335-147">На странице многофакторной проверки подлинности выберите каждого пользователя по отдельности и установите для них многофакторную проверку подлинности в состояние **Отключено**.</span><span class="sxs-lookup"><span data-stu-id="dd335-147">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dd335-148">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="dd335-148">Next steps</span></span>

- [<span data-ttu-id="dd335-149">Как зарегистрировать дополнительный метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="dd335-149">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="dd335-150">Что такое: многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="dd335-150">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="dd335-151">Как войти после регистрации</span><span class="sxs-lookup"><span data-stu-id="dd335-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="dd335-152">Как изменить дополнительный метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="dd335-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-topics"></a><span data-ttu-id="dd335-153">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="dd335-153">Related topics</span></span>

[<span data-ttu-id="dd335-154">Видео: включение многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="dd335-154">Video: Turn on multi-factor authentication</span></span>](https://docs.microsoft.com/microsoft-365/business-video/turn-on-mfa)

[<span data-ttu-id="dd335-155">Видео: включение многофакторной проверки подлинности для телефона</span><span class="sxs-lookup"><span data-stu-id="dd335-155">Video: Turn on multi-factor authentication for your phone</span></span>](https://docs.microsoft.com/microsoft-365/business-video/set-up-mfa)
