---
title: Настройка многофакторной проверки подлинности для пользователей
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
ms.openlocfilehash: db858cbd4242a096261942fd12b911ecff43f71f
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558214"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="baaed-103">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="baaed-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="baaed-104">С учетом знакомства с [многофакторной проверкой подлинности (MFA) и ее поддержкой в Microsoft 365](multi-factor-authentication-microsoft-365.md) пришло время развернуть и настроить ее для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="baaed-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="baaed-105">Если вы приобрели подписку или получили пробную версию после 21 октября 2019 г. и при выполнении входа вам предлагается пройти многофакторную проверку подлинности (MFA), это значит, что к вашей подписке были автоматически применены [параметры безопасности по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="baaed-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="baaed-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="baaed-106">Before you begin</span></span>

- <span data-ttu-id="baaed-107">Управлять многофакторной проверкой подлинности (MFA) может только глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="baaed-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="baaed-108">Дополнительные сведения см. в статье [О ролях администраторов](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="baaed-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="baaed-109">Если у вас включена устаревшая MFA для конкретных пользователей, [отключите устаревшую MFA для конкретных пользователей](#turn-off-legacy-per-user-mfa).</span><span class="sxs-lookup"><span data-stu-id="baaed-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="baaed-110">Если у вас есть клиенты Office 2013 на устройствах с Windows, [включите современную проверку подлинности для клиентов Office 2013](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="baaed-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="baaed-111">Дополнительно: если вы используете сторонние службы каталогов со службами федерации Active Directory (AD FS), настройте сервер Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="baaed-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="baaed-112">Дополнительные сведения см. в статье [Расширенные сценарии с использованием многофакторной проверки подлинности Azure AD и сторонних решений VPN](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="baaed-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="baaed-113">Включение и отключение параметров безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="baaed-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="baaed-114">Параметры безопасности по умолчанию обеспечивают подходящий для большинства организаций уровень безопасности при входе в систему.</span><span class="sxs-lookup"><span data-stu-id="baaed-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="baaed-115">Дополнительные сведения см. в статье [Что такое параметры безопасности по умолчанию?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="baaed-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="baaed-116">Если у вас новая подписка, то параметры безопасности по умолчанию могли быть включены автоматически.</span><span class="sxs-lookup"><span data-stu-id="baaed-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="baaed-117">Включить или отключить параметры безопасности по умолчанию можно на портале Azure в области **Свойства** для Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="baaed-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="baaed-118">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="baaed-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="baaed-119">На левой панели навигации нажмите **Показать все** и в разделе **Центры администрирования** выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="baaed-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="baaed-120">В **Центре администрирования Azure Active Directory** выберите **Azure Active Directory** \> **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="baaed-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="baaed-121">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="baaed-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="baaed-122">Выберите **Да**, чтобы включить параметры безопасности по умолчанию, или **Нет**, чтобы их отключить, а затем нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="baaed-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="baaed-123">Если у вас включены [базовые политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), вам будет предложено отключить их до перехода к использованию параметров безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="baaed-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="baaed-124">Выберите [Условный доступ — страница "Политики"](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="baaed-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="baaed-125">Выберите все базовые политики в состоянии **Вкл.** и установите для параметра **Включить политику** состояние **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="baaed-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="baaed-126">Выберите [Azure Active Directory — страница "Свойства"](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="baaed-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="baaed-127">В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="baaed-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="baaed-128">Выберите **Да**, чтобы включить параметры безопасности по умолчанию, или **Нет**, чтобы их отключить, а затем нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="baaed-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="baaed-129">Использование политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="baaed-129">Use Conditional Access policies</span></span>

<span data-ttu-id="baaed-130">Если вашей организации нужно значительное количество различных установок безопасности при входе в систему, то политики условного доступа могут предоставить вам дополнительные возможности управления.</span><span class="sxs-lookup"><span data-stu-id="baaed-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="baaed-131">Условный доступ позволяет создавать и определять политики, которые реагируют на события при входе и запрашивают дополнительные действия, прежде чем пользователю будет предоставлен доступ к приложению или службе.</span><span class="sxs-lookup"><span data-stu-id="baaed-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="baaed-132">Прежде чем включать политики условного доступа, отключите MFA для конкретных пользователей и параметры безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="baaed-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="baaed-133">Условный доступ могут использовать клиенты, которые приобрели Azure AD Premium P1 или лицензии, в которые входит эта служба, например Microsoft 365 бизнес премиум или Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="baaed-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="baaed-134">Для получения дополнительной информации см. статью [Создание политик условного доступа](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span><span class="sxs-lookup"><span data-stu-id="baaed-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="baaed-135">Условный доступ на основе риска доступен в рамках лицензии Azure AD Premium P2 или в рамках лицензий, в которую входит эта служба, например Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="baaed-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="baaed-136">Дополнительные сведения см. в статье [Условный доступ на основе рисков](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span><span class="sxs-lookup"><span data-stu-id="baaed-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="baaed-137">Дополнительные сведения об Azure AD P1 и P2 см. в статье [Цены для Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="baaed-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="baaed-138">Включение современной проверки подлинности для организации</span><span class="sxs-lookup"><span data-stu-id="baaed-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="baaed-139">В большинстве подписок современная проверка подлинности автоматически включена, но если вы приобрели подписку давно, то это может быть не так.</span><span class="sxs-lookup"><span data-stu-id="baaed-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription a long time ago, it might not be.</span></span> <span data-ttu-id="baaed-140">Ее необходимо включить для того, чтобы MFA работала в приложениях Office надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="baaed-140">This has to be turned on before MFA works appropriately with Office apps.</span></span>

1. <span data-ttu-id="baaed-141">В Центре администрирования Microsoft 365 на левой панели навигации выберите **Параметры** \> **Параметры организации**.</span><span class="sxs-lookup"><span data-stu-id="baaed-141">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
1. <span data-ttu-id="baaed-142">На вкладке **Службы** выберите **Современная проверка подлинности**, а затем в области **Современная проверка подлинности** установите флажок **Включить современную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="baaed-142">Under **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="baaed-143">Выберите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="baaed-143">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="baaed-144">Выключение устаревшей MFA для конкретных пользователей</span><span class="sxs-lookup"><span data-stu-id="baaed-144">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="baaed-145">Если у вас включена MFA для конкретных пользователей, перед включением параметров безопасности по умолчанию ее необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="baaed-145">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="baaed-146">В Центре администрирования Microsoft 365 на левой панели навигации выберите **Пользователи** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="baaed-146">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="baaed-147">На странице **Активные пользователи** нажмите **Многофакторная проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="baaed-147">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="baaed-148">На странице многофакторной проверки подлинности выберите каждого пользователя по отдельности и установите для них многофакторную проверку подлинности в состояние **Отключено**.</span><span class="sxs-lookup"><span data-stu-id="baaed-148">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="baaed-149">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="baaed-149">Next steps</span></span>

- [<span data-ttu-id="baaed-150">Как зарегистрировать дополнительный метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="baaed-150">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="baaed-151">Что такое: многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="baaed-151">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="baaed-152">Как войти после регистрации</span><span class="sxs-lookup"><span data-stu-id="baaed-152">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="baaed-153">Как изменить дополнительный метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="baaed-153">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
