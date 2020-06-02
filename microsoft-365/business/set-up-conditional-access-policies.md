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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как настроить политики условного доступа для кампаний Microsoft 365, чтобы добавить существенную дополнительную защиту.
ms.openlocfilehash: 58ee760877ee2fd7e53ef9463242657ab66a2b6e
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470654"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="121f2-103">Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="121f2-103">Set up conditional access policies</span></span>

<span data-ttu-id="121f2-104">Эта статья относится к Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="121f2-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="121f2-105">Политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) добавляют существенную дополнительную защиту.</span><span class="sxs-lookup"><span data-stu-id="121f2-105">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="121f2-106">Корпорация Майкрософт предоставляет набор базовых политик условного доступа, рекомендуемых для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="121f2-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="121f2-107">Базовые политики это набор предопределенных политик, которые помогают защитить организации от многих распространенных атак.</span><span class="sxs-lookup"><span data-stu-id="121f2-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="121f2-108">Эти распространенные атаки могут включать распылителя, преобразования и фишинга паролей.</span><span class="sxs-lookup"><span data-stu-id="121f2-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="121f2-109">Эти политики требуют, чтобы администраторы и пользователи вводили вторую форму проверки подлинности (называемую многофакторной проверкой подлинности или MFA) при выполнении определенных условий.</span><span class="sxs-lookup"><span data-stu-id="121f2-109">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="121f2-110">Например, если пользователь входит в другую страну, то вход может считаться рискованным и пользователь должен предоставить дополнительную форму проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="121f2-110">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="121f2-111">В настоящее время базовые политики включают следующее:</span><span class="sxs-lookup"><span data-stu-id="121f2-111">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="121f2-112">**Требовать MFA для администраторов** &ndash; Требует многофакторной проверки подлинности для наиболее привилегированных ролей администратора, в том числе глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="121f2-112">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="121f2-113">**Защита от** &ndash; конечных пользователей Требует многофакторной проверки подлинности для пользователей, только если вход в систему рискованный.</span><span class="sxs-lookup"><span data-stu-id="121f2-113">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="121f2-114">**Блокировать устаревшую проверку подлинности** &ndash; Старые клиентские приложения и некоторые новые приложения не используют новые, более безопасные протоколы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="121f2-114">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="121f2-115">Эти старые приложения могут обходить политики условного доступа и получать несанкционированный доступ к вашей среде.</span><span class="sxs-lookup"><span data-stu-id="121f2-115">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="121f2-116">Эта политика блокирует доступ клиентов, не поддерживающих условный доступ.</span><span class="sxs-lookup"><span data-stu-id="121f2-116">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="121f2-117">**Запрос MFA для управления службами** &ndash; Требует многофакторной проверки подлинности для доступа к средствам управления, включая портал Azure (при настройке базовых политик).</span><span class="sxs-lookup"><span data-stu-id="121f2-117">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="121f2-118">Корпорация Майкрософт рекомендует включить все эти базовые политики.</span><span class="sxs-lookup"><span data-stu-id="121f2-118">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="121f2-119">После включения этих политик Администраторы и пользователи будут получать запросы на регистрацию для проверки подлинности Azure Мултии.</span><span class="sxs-lookup"><span data-stu-id="121f2-119">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="121f2-120">Для получения дополнительных сведений об этих политиках, ознакомьтесь со статьями [базовых политик](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="121f2-120">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="121f2-121">Настройка базовых политик</span><span class="sxs-lookup"><span data-stu-id="121f2-121">Set up baseline policies</span></span>

1. <span data-ttu-id="121f2-122">Перейдите на [портал Azure](https://portal.azure.com), а затем перейдите к **Azure Active Directory** \> **условному доступу**к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="121f2-122">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="121f2-123">Базовые политики перечислены на странице.</span><span class="sxs-lookup"><span data-stu-id="121f2-123">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="121f2-124">![Страница, на которой перечисляются базовые политики для условного доступа.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="121f2-124">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="121f2-125">Для каждой политики ознакомьтесь с приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="121f2-125">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="121f2-126">Требовать MFA для администраторов</span><span class="sxs-lookup"><span data-stu-id="121f2-126">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="121f2-127">Требовать MFA для пользователей</span><span class="sxs-lookup"><span data-stu-id="121f2-127">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="121f2-128">Блокирование традиционной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="121f2-128">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="121f2-129">Запрос MFA для управления службами</span><span class="sxs-lookup"><span data-stu-id="121f2-129">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="121f2-130">Можно настроить множество дополнительных политик, например требование утвержденных клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="121f2-130">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="121f2-131">Дополнительные сведения см. в [документации по условному доступу](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="121f2-131">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
