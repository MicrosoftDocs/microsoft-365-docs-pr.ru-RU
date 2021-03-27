---
title: Включим по умолчанию безопасность
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как по умолчанию системы безопасности могут защитить организацию от атак, связанных с удостоверениями, путем предоставления заранее задающихся параметров безопасности.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398300"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="9f2fa-103">Включим по умолчанию безопасность</span><span class="sxs-lookup"><span data-stu-id="9f2fa-103">Turn on security defaults</span></span>

<span data-ttu-id="9f2fa-104">По умолчанию по умолчанию безопасность помогает защитить организацию от атак, связанных с удостоверениями, предоставляя заранее задатки безопасности, управляемые Корпорацией Майкрософт от имени вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="9f2fa-105">Эти параметры включают включение многофакторной проверки подлинности (MFA) для всех администраторов и учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="9f2fa-106">Для большинства организаций по умолчанию безопасность предлагает хороший уровень дополнительной безопасности для входов.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="9f2fa-107">Дополнительные сведения о дефолтах безопасности и политиках, которые они применяют, см. в дополнительных сведениях [о том, что такое по умолчанию безопасность?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="9f2fa-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="9f2fa-108">Если ваша подписка была создана 22 октября 2019 г. или после нее, по умолчанию безопасности можно было автоматически включить, чтобы проверить параметры для &mdash; подтверждения.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="9f2fa-109">Чтобы включить по умолчанию безопасность в Azure Active Directory (Azure AD) или проверить, включены ли они:</span><span class="sxs-lookup"><span data-stu-id="9f2fa-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="9f2fa-110">Во входе в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центр администрирования Microsoft 365</a> с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="9f2fa-111">В левой области выберите **Показать все,** а затем в центрах **администрирования** выберите **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="9f2fa-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="9f2fa-112">В левой области центра администрирования **Azure Active Directory выберите** Azure Active **Directory.**</span><span class="sxs-lookup"><span data-stu-id="9f2fa-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="9f2fa-113">В левом меню панели мониторинга в разделе **Управление** выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Снимок экрана центра администрирования Azure Active Directory с указанием расположения элемента меню Properties.":::

5. <span data-ttu-id="9f2fa-115">В нижней части страницы **Свойства** выберите Управление **по умолчанию безопасности.**</span><span class="sxs-lookup"><span data-stu-id="9f2fa-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="9f2fa-116">В правой области вы увидите параметр **Enable Security defaults.**</span><span class="sxs-lookup"><span data-stu-id="9f2fa-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="9f2fa-117">Если **выбран да,** то по умолчанию безопасности уже включены и никаких дальнейших действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="9f2fa-118">Если по умолчанию безопасности в настоящее время не включено, выберите **Да,** чтобы включить их, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="9f2fa-119">Если вы используете политики условного доступа, их необходимо отключить, прежде чем использовать по умолчанию безопасность.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="9f2fa-120">Вы можете использовать как по умолчанию безопасности, так и политики условного доступа, но вы не можете использовать оба одновременно.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="9f2fa-121">Рассмотрите возможность использования условного доступа</span><span class="sxs-lookup"><span data-stu-id="9f2fa-121">Consider using Conditional Access</span></span>

<span data-ttu-id="9f2fa-122">Если в вашей организации есть сложные требования к безопасности или требуется более подробное управление политиками безопасности, следует использовать условный доступ вместо по умолчанию безопасности для достижения аналогичной или более высокой позиции безопасности.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="9f2fa-123">Условный доступ позволяет создавать и определять политики, которые реагируют на события регистрации и запрашивают дополнительные действия перед предоставлением пользователю доступа к приложению или службе.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="9f2fa-124">Политики условного доступа могут быть разнонаверенными и конкретными, что позволяет пользователям быть продуктивными везде и в любое время, а также защищать вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="9f2fa-125">По умолчанию безопасность доступна всем клиентам, в то время как для условного доступа требуется лицензия для одного из следующих планов:</span><span class="sxs-lookup"><span data-stu-id="9f2fa-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="9f2fa-126">Azure Active Directory Premium P1 или P2</span><span class="sxs-lookup"><span data-stu-id="9f2fa-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="9f2fa-127">Microsoft 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="9f2fa-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="9f2fa-128">Microsoft 365 E3 или E5</span><span class="sxs-lookup"><span data-stu-id="9f2fa-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="9f2fa-129">Корпоративная мобильность & безопасности E3 или E5</span><span class="sxs-lookup"><span data-stu-id="9f2fa-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="9f2fa-130">Если вы хотите использовать условный доступ для настройки политик, эквивалентных политикам, включенным по умолчанию безопасности, ознакомьтесь со следующими пошаговыми руководствами:</span><span class="sxs-lookup"><span data-stu-id="9f2fa-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="9f2fa-131">Обязательное использование MFA для администраторов</span><span class="sxs-lookup"><span data-stu-id="9f2fa-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="9f2fa-132">Требуется MFA для управления Azure</span><span class="sxs-lookup"><span data-stu-id="9f2fa-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="9f2fa-133">Блокирование традиционной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="9f2fa-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="9f2fa-134">Обязательное использование MFA для всех пользователей</span><span class="sxs-lookup"><span data-stu-id="9f2fa-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="9f2fa-135">[Требуется регистрация azure AD MFA](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) — требуется защита удостоверений Azure AD, которая является частью Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="9f2fa-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="9f2fa-136">Дополнительные информацию об условном доступе см. в дополнительных подробной информации [о условном доступе?](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="9f2fa-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="9f2fa-137">Дополнительные сведения о создании политик условного доступа см. в дополнительных сведениях [о создании политики условного доступа.](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)</span><span class="sxs-lookup"><span data-stu-id="9f2fa-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="9f2fa-138">Если у вас есть план или лицензия, которая предоставляет условный доступ, но еще не создана политика условного доступа, вы можете использовать по умолчанию безопасность.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="9f2fa-139">Однако необходимо отключить по умолчанию безопасность, прежде чем использовать политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="9f2fa-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
