---
title: Настройка политик условного доступа для кампаний Microsoft 365
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как настроить политики условного доступа для кампаний Microsoft 365.
ms.openlocfilehash: 1ef90bd77da43ded624d85cef9c7a33beec74345
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42064624"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="42b64-103">Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="42b64-103">Set up conditional access policies</span></span>

<span data-ttu-id="42b64-104">Политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) добавляют существенную дополнительную защиту.</span><span class="sxs-lookup"><span data-stu-id="42b64-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="42b64-105">Корпорация Майкрософт предоставляет набор базовых политик условного доступа, рекомендуемых для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="42b64-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="42b64-106">Базовые политики это набор предопределенных политик, которые помогают защитить организации от многих распространенных атак.</span><span class="sxs-lookup"><span data-stu-id="42b64-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="42b64-107">Эти распространенные атаки могут включать распылителя, преобразования и фишинга паролей.</span><span class="sxs-lookup"><span data-stu-id="42b64-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="42b64-108">Эти политики требуют, чтобы администраторы и пользователи вводили вторую форму проверки подлинности (называемую многофакторной проверкой подлинности или MFA) при выполнении определенных условий.</span><span class="sxs-lookup"><span data-stu-id="42b64-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="42b64-109">Например, если пользователь входит в другую страну, то вход может считаться рискованным и пользователь должен предоставить дополнительную форму проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="42b64-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="42b64-110">В настоящее время базовые политики включают следующее:</span><span class="sxs-lookup"><span data-stu-id="42b64-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="42b64-111">Для **администраторов** &ndash; необходимо включить многофакторную проверку подлинности для наиболее привилегированных ролей администратора, в том числе глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="42b64-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="42b64-112">Для **защиты от** &ndash; пользователей требуется многофакторная проверка подлинности для пользователей, только если вход в систему рискованный.</span><span class="sxs-lookup"><span data-stu-id="42b64-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="42b64-113">**Блокировать устаревшую проверку подлинности** &ndash; устаревшие клиентские приложения и некоторые новые приложения не используют новые, более безопасные протоколы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="42b64-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="42b64-114">Эти старые приложения могут обходить политики условного доступа и получать несанкционированный доступ к вашей среде.</span><span class="sxs-lookup"><span data-stu-id="42b64-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="42b64-115">Эта политика блокирует доступ клиентов, не поддерживающих условный доступ.</span><span class="sxs-lookup"><span data-stu-id="42b64-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="42b64-116">**Для управления** &ndash; службами необходимо требовать многофакторную проверку подлинности для доступа к средствам управления, включая портал Azure (при настройке базовых политик).</span><span class="sxs-lookup"><span data-stu-id="42b64-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="42b64-117">Корпорация Майкрософт рекомендует включить все эти базовые политики.</span><span class="sxs-lookup"><span data-stu-id="42b64-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="42b64-118">После включения этих политик Администраторы и пользователи будут получать запросы на регистрацию для проверки подлинности Azure Мултии.</span><span class="sxs-lookup"><span data-stu-id="42b64-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="42b64-119">Для получения дополнительных сведений об этих политиках, ознакомьтесь со статьями [базовых политик](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="42b64-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="42b64-120">Настройка базовых политик</span><span class="sxs-lookup"><span data-stu-id="42b64-120">Set up baseline policies</span></span>

1. <span data-ttu-id="42b64-121">Перейдите на [портал Azure](https://portal.azure.com), а затем перейдите к **условному доступу**к **Azure Active Directory** \> .</span><span class="sxs-lookup"><span data-stu-id="42b64-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="42b64-122">Базовые политики перечислены на странице.</span><span class="sxs-lookup"><span data-stu-id="42b64-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="42b64-123">![Страница, на которой перечисляются базовые политики для условного доступа.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="42b64-123">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="42b64-124">Для каждой политики ознакомьтесь с приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="42b64-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="42b64-125">Требовать MFA для администраторов</span><span class="sxs-lookup"><span data-stu-id="42b64-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="42b64-126">Требовать MFA для пользователей</span><span class="sxs-lookup"><span data-stu-id="42b64-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="42b64-127">Блокировать устаревшую проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="42b64-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="42b64-128">Запрос MFA для управления службами</span><span class="sxs-lookup"><span data-stu-id="42b64-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="42b64-129">Можно настроить множество дополнительных политик, например требование утвержденных клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="42b64-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="42b64-130">Дополнительные сведения см. в [документации по условному доступу](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="42b64-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
