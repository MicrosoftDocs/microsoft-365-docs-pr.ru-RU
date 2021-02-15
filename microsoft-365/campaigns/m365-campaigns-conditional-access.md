---
title: Настройка политик условного доступа
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как требовать MFA и настроить политики условного доступа для Microsoft 365 для бизнеса.
ms.openlocfilehash: b13ba9f8c948d9a1209655c44871ca62cb5354dd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044504"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="cea4d-103">Требовать многофакторную проверку подлинности и настроить политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="cea4d-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="cea4d-104">Вы защищаете доступ к данным с помощью многофакторной проверки подлинности и политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="cea4d-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="cea4d-105">Они добавляют значительные дополнительные средства безопасности.</span><span class="sxs-lookup"><span data-stu-id="cea4d-105">These add substantial additional security.</span></span> <span data-ttu-id="cea4d-106">Корпорация Майкрософт предоставляет набор базовых политик условного доступа, рекомендуемых для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="cea4d-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="cea4d-107">Базовые политики — это набор предварительно задающих политик, которые помогают защитить организации от многих распространенных атак.</span><span class="sxs-lookup"><span data-stu-id="cea4d-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="cea4d-108">Эти распространенные атаки могут включать распыление пароля, воспроизведение и фишинг.</span><span class="sxs-lookup"><span data-stu-id="cea4d-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="cea4d-109">Эти политики требуют от администраторов и пользователей вводить вторую форму проверки подлинности (многофакторную проверку подлинности или многофакторную проверку подлинности) при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="cea4d-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="cea4d-110">Например, если пользователь в вашей организации пытается войти в Microsoft 365 из другой страны или с неизвестного устройства, вход может считаться рискованным.</span><span class="sxs-lookup"><span data-stu-id="cea4d-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="cea4d-111">Пользователь должен предоставить дополнительную форму проверки подлинности (например, отпечаток пальца или код), чтобы подтвердить свою личность.</span><span class="sxs-lookup"><span data-stu-id="cea4d-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="cea4d-112">В настоящее время базовые политики включают следующие политики:</span><span class="sxs-lookup"><span data-stu-id="cea4d-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="cea4d-113">Настройка в Центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="cea4d-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="cea4d-114">**Требовать многофакторную** проверку подлинности для администраторов: требуется многофакторная проверка подлинности для наиболее привилегированных ролей администраторов, включая глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="cea4d-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="cea4d-115">**Защита конечных пользователей:** многофакторная проверка подлинности для пользователей требуется только в том случае, если вход является рискованным.</span><span class="sxs-lookup"><span data-stu-id="cea4d-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="cea4d-116">Настройка на портале Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="cea4d-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="cea4d-117">**Блокировка устаревшей проверки** подлинности: старые клиентские приложения и некоторые новые приложения не используют новые, более безопасные протоколы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="cea4d-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="cea4d-118">Эти старые приложения могут обходить политики условного доступа и получать несанкционированный доступ к вашей среде.</span><span class="sxs-lookup"><span data-stu-id="cea4d-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="cea4d-119">Эта политика блокирует доступ от клиентов, которые не поддерживают условный доступ.</span><span class="sxs-lookup"><span data-stu-id="cea4d-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="cea4d-120">**Требовать многофакторную** проверку подлинности для управления службами: требуется многофакторная проверка подлинности для доступа к средствам управления, включая портал Azure (где настраиваются базовые политики).</span><span class="sxs-lookup"><span data-stu-id="cea4d-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="cea4d-121">Рекомендуется включить все эти базовые политики.</span><span class="sxs-lookup"><span data-stu-id="cea4d-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="cea4d-122">После включения этих политик администраторам и пользователям будет предложено зарегистрироваться для многофакторной идентификации Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cea4d-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="cea4d-123">Дополнительные сведения об этих политиках см. в [дополнительных сведениях о базовых политиках?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="cea4d-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="cea4d-124">Требование многофакторной идентификации</span><span class="sxs-lookup"><span data-stu-id="cea4d-124">Require MFA</span></span>

<span data-ttu-id="cea4d-125">Чтобы требовать, чтобы все пользователи влияли во вторую форму ID:</span><span class="sxs-lookup"><span data-stu-id="cea4d-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="cea4d-126">Перейдите в Центр администрирования и <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> выберите **"Настройка".**</span><span class="sxs-lookup"><span data-stu-id="cea4d-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="cea4d-127">На странице "Установка" выберите **"Вид"** в карточке "Сделать **вход более безопасным".**</span><span class="sxs-lookup"><span data-stu-id="cea4d-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![Сделайте вход более безопасной картой.](../media/setupmfa.png)
3. <span data-ttu-id="cea4d-129">На странице "Сделать вход более безопасным" выберите **"Начало работы".**</span><span class="sxs-lookup"><span data-stu-id="cea4d-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="cea4d-130">В области безопасности "Усилить вход" выберите флажки  "Требовать многофакторную проверку подлинности для администраторов" и "Требовать регистрацию для многофакторной проверки подлинности" и заблокировать доступ при обнаружении **риска.**</span><span class="sxs-lookup"><span data-stu-id="cea4d-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="cea4d-131">Не забудьте исключить учетную запись администратора экстренной службы или "взлома" из требования MFA в поле **"Найти** пользователей". [](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)</span><span class="sxs-lookup"><span data-stu-id="cea4d-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![Усилить страницу безопасности sing-in.](../media/requiremfa.png)

5. <span data-ttu-id="cea4d-133">Выберите **"Создать политику"** в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="cea4d-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="cea4d-134">Настройка базовых политик</span><span class="sxs-lookup"><span data-stu-id="cea4d-134">Set up baseline policies</span></span>

1. <span data-ttu-id="cea4d-135">Перейдите на [портал Azure](https://portal.azure.com)и перейдите на условный доступ Azure **Active Directory,** чтобы создать новую \>  **политику.**</span><span class="sxs-lookup"><span data-stu-id="cea4d-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="cea4d-136">См. следующие инструкции для каждой политики:</span><span class="sxs-lookup"><span data-stu-id="cea4d-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="cea4d-137">Требовать MFA для администраторов</span><span class="sxs-lookup"><span data-stu-id="cea4d-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="cea4d-138">Требовать многофаксную MFA для пользователей</span><span class="sxs-lookup"><span data-stu-id="cea4d-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="cea4d-139">Блокирование традиционной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="cea4d-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="cea4d-140">Требовать MFA для управления службами</span><span class="sxs-lookup"><span data-stu-id="cea4d-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="cea4d-141">Политики предварительного просмотра больше не существуют, и пользователям потребуется создать собственные политики.</span><span class="sxs-lookup"><span data-stu-id="cea4d-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="cea4d-142">Вы можете настроить дополнительные политики, например требовать утверждения клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="cea4d-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="cea4d-143">Дополнительные сведения см. в [документации по условному доступу.](https://docs.microsoft.com/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="cea4d-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
