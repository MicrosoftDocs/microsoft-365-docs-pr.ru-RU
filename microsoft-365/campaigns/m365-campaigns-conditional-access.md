---
title: Настройка политик условного доступа
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Сведения о том, как запрашивать MFA и настраивать политики условного доступа для Microsoft 365 Business.
ms.openlocfilehash: 570edce03a68dad56c895e2484a5162496d7a3eb
ms.sourcegitcommit: 75b97d1ff617bc4b1b0ef9135dfe6a8842ea1b52
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2019
ms.locfileid: "35772546"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="66dae-103">Требуется многофакторная проверка подлинности и Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="66dae-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="66dae-104">Вы защищаете доступ к данным с помощью многофакторной проверки подлинности и политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="66dae-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="66dae-105">Они применяют существенную дополнительную защиту.</span><span class="sxs-lookup"><span data-stu-id="66dae-105">These add substantial additional security.</span></span> <span data-ttu-id="66dae-106">Корпорация Майкрософт предоставляет набор базовых политик условного доступа, рекомендуемых для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="66dae-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="66dae-107">Базовые политики это набор предопределенных политик, которые помогают защитить организации от многих распространенных атак.</span><span class="sxs-lookup"><span data-stu-id="66dae-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="66dae-108">Эти распространенные атаки могут включать распылителя, преобразования и фишинга паролей.</span><span class="sxs-lookup"><span data-stu-id="66dae-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="66dae-109">Эти политики требуют, чтобы администраторы и пользователи вводили вторую форму проверки подлинности (называемую многофакторной проверкой подлинности или MFA) при выполнении определенных условий.</span><span class="sxs-lookup"><span data-stu-id="66dae-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="66dae-110">Например, если пользователь в вашей организации пытается войти в Microsoft 365 из другой страны или из неизвестного устройства, то вход может считаться рискованным.</span><span class="sxs-lookup"><span data-stu-id="66dae-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="66dae-111">Пользователь должен предоставить дополнительную форму проверки подлинности (например, с помощью отпечатка пальца или кода), чтобы доказать их подлинность.</span><span class="sxs-lookup"><span data-stu-id="66dae-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="66dae-112">В настоящее время базовые политики включают следующее:</span><span class="sxs-lookup"><span data-stu-id="66dae-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="66dae-113">Настройка в центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="66dae-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="66dae-114">Для **использования MFA для администраторов** требуется многофакторная проверка подлинности для наиболее привилегированных ролей администратора, в том числе глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="66dae-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="66dae-115">**Защита конечных пользователей** — требуется многофакторная проверка подлинности для пользователей, только если вход в систему рискованный.</span><span class="sxs-lookup"><span data-stu-id="66dae-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="66dae-116">Настройка на портале Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="66dae-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="66dae-117">**Блокировать устаревшую проверку** подлинности — старые клиентские приложения и некоторые новые приложения не используют новые, более безопасные протоколы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="66dae-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="66dae-118">Эти старые приложения могут обходить политики условного доступа и получать несанкционированный доступ к вашей среде.</span><span class="sxs-lookup"><span data-stu-id="66dae-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="66dae-119">Эта политика блокирует доступ клиентов, не поддерживающих условный доступ.</span><span class="sxs-lookup"><span data-stu-id="66dae-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="66dae-120">**Для управления службами необходимо требовать** многофакторную проверку подлинности для доступа к средствам управления, включая портал Azure (при настройке базовых политик).</span><span class="sxs-lookup"><span data-stu-id="66dae-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="66dae-121">Корпорация Майкрософт рекомендует включить все эти базовые политики.</span><span class="sxs-lookup"><span data-stu-id="66dae-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="66dae-122">После включения этих политик Администраторы и пользователи будут получать запросы на регистрацию для многофакторной проверки подлинности Azure.</span><span class="sxs-lookup"><span data-stu-id="66dae-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="66dae-123">Для получения дополнительных сведений об этих политиках, ознакомьтесь со статьями [базовых политик](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="66dae-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="66dae-124">Требовать многофакторную идентификацию</span><span class="sxs-lookup"><span data-stu-id="66dae-124">Require MFA</span></span>

<span data-ttu-id="66dae-125">Чтобы потребовать вход всех пользователей с помощью второй формы идентификатора:</span><span class="sxs-lookup"><span data-stu-id="66dae-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="66dae-126">Перейдите в центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> и выберите пункт **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="66dae-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="66dae-127">На странице Настройка выберите пункт **Просмотр** в карточке **сделать вход более защищенной** .</span><span class="sxs-lookup"><span data-stu-id="66dae-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![Сделайте вход в систему с более безопасной картой.](media/setupmfa.png)
3. <span data-ttu-id="66dae-129">На странице Создание безопасного входа нажмите кнопку **начать работу**.</span><span class="sxs-lookup"><span data-stu-id="66dae-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="66dae-130">В области безопасность при входе установите флажки Включить многофакторную **проверку подлинности для администраторов** и **требовать, чтобы пользователи регистрировали многофакторную проверку подлинности и блокировали доступ в случае обнаружения риска**.</span><span class="sxs-lookup"><span data-stu-id="66dae-130">On the Strengthen sign-in security pane, check the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="66dae-131">Обязательно исключите из требования [](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) к MFA учетную запись администратора для экстренного реагирования или "размыкатель" из требования MFA в поле " **найти пользователей** ".</span><span class="sxs-lookup"><span data-stu-id="66dae-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![Веб-страница усиления безопасности.](media/requiremfa.png)

5. <span data-ttu-id="66dae-133">В нижней части страницы выберите **создать политику** .</span><span class="sxs-lookup"><span data-stu-id="66dae-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="66dae-134">Настройка базовых политик</span><span class="sxs-lookup"><span data-stu-id="66dae-134">Set up baseline policies</span></span>

1. <span data-ttu-id="66dae-135">Перейдите на [портал Azure](https://portal.azure.com), а затем перейдите к условному доступу к **Azure Active Directory** \> \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="66dae-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="66dae-136">Базовые политики перечислены на странице, и вы можете увидеть, что запрос MFA для администраторов и защита конечных пользователей уже включены после выполнения действий, описанных в статье [требования к MFA](#require-mfa).</span><span class="sxs-lookup"><span data-stu-id="66dae-136">The baseline policies are listed on the page, and you can see that Require MFA for admins and End user protection are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![Страница, на которой перечисляются базовые политики для условного доступа.](media/casettings.png)
2. <span data-ttu-id="66dae-138">Для каждой политики ознакомьтесь с приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="66dae-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="66dae-139">Требовать MFA для администраторов</span><span class="sxs-lookup"><span data-stu-id="66dae-139">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)

       
    -   [<span data-ttu-id="66dae-140">Требовать MFA для пользователей</span><span class="sxs-lookup"><span data-stu-id="66dae-140">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="66dae-141">Блокировать устаревшую проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="66dae-141">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="66dae-142">Запрос MFA для управления службами</span><span class="sxs-lookup"><span data-stu-id="66dae-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="66dae-143">Можно настроить дополнительные политики, например требования утвержденных клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="66dae-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="66dae-144">Для получения дополнительных сведений ознакомьтесь с [документацией по условному доступу](https://docs.microsoft.com/azure/active-directory/conditional-access/) .</span><span class="sxs-lookup"><span data-stu-id="66dae-144">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>
