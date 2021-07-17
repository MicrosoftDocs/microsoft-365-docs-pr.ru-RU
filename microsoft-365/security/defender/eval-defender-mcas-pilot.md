---
title: Пилотные Microsoft Cloud App Security с Microsoft 365 Defender, создание пилотных групп, настройка условного управления доступом, опробовка возможностей, установка в Microsoft 365 Defender
description: Настройка пробной Microsoft 365 Defender или пилотной среды для тестирования и тестирования решения безопасности, предназначенного для защиты устройств, удостоверений, данных и приложений.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458544"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a><span data-ttu-id="cc77b-103">Пилотный Microsoft Cloud App Security с Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc77b-103">Pilot Microsoft Cloud App Security with Microsoft 365 Defender</span></span>


<span data-ttu-id="cc77b-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cc77b-104">**Applies to:**</span></span>
- <span data-ttu-id="cc77b-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc77b-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="cc77b-106">Эта статья [— шаг 3 из 3](eval-defender-mcas-overview.md) в процессе настройки среды оценки для Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="cc77b-106">This article is [Step 3 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="cc77b-107">Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cc77b-107">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="cc77b-108">Чтобы настроить пилотный пилот для Microsoft Cloud App Security, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="cc77b-108">Use the following steps to setup and configure the pilot for Microsoft Cloud App Security.</span></span>


![Этапы пилотирования Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- <span data-ttu-id="cc77b-110">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="cc77b-110">Step 1.</span></span> [<span data-ttu-id="cc77b-111">Создание пилотной группы — область развертывания пилотного развертывания для определенных групп пользователей</span><span class="sxs-lookup"><span data-stu-id="cc77b-111">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [<span data-ttu-id="cc77b-112">Шаг 2. Настройка защиты — управление приложениями условного доступа</span><span class="sxs-lookup"><span data-stu-id="cc77b-112">Step 2. Configure protection — Conditional Access App Control</span></span>](#step-2-configure-protection--conditional-access-app-control)
- [<span data-ttu-id="cc77b-113">Шаг 3. Опробуйте возможности — пройдитесь по учебникам по защите среды</span><span class="sxs-lookup"><span data-stu-id="cc77b-113">Step 3. Try out capabilities — Walk through tutorials for protecting your environment</span></span>](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a><span data-ttu-id="cc77b-114">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="cc77b-114">Step 1.</span></span> <span data-ttu-id="cc77b-115">Создание пилотной группы — область развертывания пилотного развертывания для определенных групп пользователей</span><span class="sxs-lookup"><span data-stu-id="cc77b-115">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>

<span data-ttu-id="cc77b-116">Microsoft Cloud App Security позволяет расширить область развертывания.</span><span class="sxs-lookup"><span data-stu-id="cc77b-116">Microsoft Cloud App Security enables you to scope your deployment.</span></span> <span data-ttu-id="cc77b-117">Scoping позволяет выбрать определенные группы пользователей, которые будут отслеживаться для приложений или исключены из мониторинга.</span><span class="sxs-lookup"><span data-stu-id="cc77b-117">Scoping allows you to select certain user groups to be monitored for apps or excluded from monitoring.</span></span> <span data-ttu-id="cc77b-118">Можно включить или исключить группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="cc77b-118">You can include or exclude user groups.</span></span> <span data-ttu-id="cc77b-119">Чтобы расширить область развертывания пилотного развертывания, см. [в поле Scoped Deployment.](/cloud-app-security/scoped-deployment)</span><span class="sxs-lookup"><span data-stu-id="cc77b-119">To scope your pilot deployment, see [Scoped Deployment](/cloud-app-security/scoped-deployment).</span></span>


## <a name="step-2-configure-protection--conditional-access-app-control"></a><span data-ttu-id="cc77b-120">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="cc77b-120">Step 2.</span></span> <span data-ttu-id="cc77b-121">Настройка защиты — управление приложениями условного доступа</span><span class="sxs-lookup"><span data-stu-id="cc77b-121">Configure protection — Conditional Access App Control</span></span>

<span data-ttu-id="cc77b-122">Одной из самых мощных средств защиты, которые можно настроить, является управление приложениями условного доступа.</span><span class="sxs-lookup"><span data-stu-id="cc77b-122">One of the most powerful protections you can configure is Conditional Access App Control.</span></span> <span data-ttu-id="cc77b-123">Это требует интеграции с Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="cc77b-123">This requires integration with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="cc77b-124">Это позволяет применять политики условного доступа, в том числе связанные политики (например, требующие здоровых устройств), для облачных приложений, которые вы санкционировали.</span><span class="sxs-lookup"><span data-stu-id="cc77b-124">It allows you to apply Conditional Access policies, including related policies (like requiring healthy devices), to cloud apps you've sanctioned.</span></span> 

<span data-ttu-id="cc77b-125">Первым шагом к использованию Microsoft Cloud App Security для управления приложениями SaaS является обнаружение этих приложений и добавление их в клиент Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cc77b-125">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="cc77b-126">Если вам нужна помощь в обнаружении, см. [в справке Откройте и управляйте приложениями SaaS в сети.](/cloud-app-security/tutorial-shadow-it)</span><span class="sxs-lookup"><span data-stu-id="cc77b-126">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="cc77b-127">После обнаружения приложений добавьте их в клиент [Azure AD.](/azure/active-directory/manage-apps/add-application-portal)</span><span class="sxs-lookup"><span data-stu-id="cc77b-127">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="cc77b-128">Вы можете начать управлять этими данными, делая следующее:</span><span class="sxs-lookup"><span data-stu-id="cc77b-128">You can begin to manage these by doing the following:</span></span>

- <span data-ttu-id="cc77b-129">Сначала в Azure AD создайте новую политику условного доступа и настройте ее на "Управление приложениями условного доступа".</span><span class="sxs-lookup"><span data-stu-id="cc77b-129">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="cc77b-130">Это перенаправляет запрос на Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="cc77b-130">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="cc77b-131">Вы можете создать одну политику и добавить все приложения SaaS в эту политику.</span><span class="sxs-lookup"><span data-stu-id="cc77b-131">You can create one policy and add all SaaS apps to this policy.</span></span>
- <span data-ttu-id="cc77b-132">Далее в Cloud App Security создайте политики сеанса.</span><span class="sxs-lookup"><span data-stu-id="cc77b-132">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="cc77b-133">Создайте по одной политике для каждого необходимого управления.</span><span class="sxs-lookup"><span data-stu-id="cc77b-133">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="cc77b-134">Дополнительные сведения, в том числе поддерживаемые приложения и клиенты, см. в Microsoft Cloud App Security с управлением приложениями [условного доступа.](/cloud-app-security/proxy-intro-aad)</span><span class="sxs-lookup"><span data-stu-id="cc77b-134">For more information, including supported apps and clients, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span> 

<span data-ttu-id="cc77b-135">Например, политики см. [в Microsoft Cloud App Security для приложений SaaS.](../office-365-security/mcas-saas-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cc77b-135">For example policies, see [Recommended Microsoft Cloud App Security policies for SaaS apps](../office-365-security/mcas-saas-access-policies.md).</span></span> <span data-ttu-id="cc77b-136">Эти политики строятся на [](../office-365-security/microsoft-365-policies-configurations.md) наборе общих политик доступа к удостоверениям и устройствам, которые рекомендуется использовать в качестве отправной точки для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="cc77b-136">These policies build on a set of [common identity and device access policies](../office-365-security/microsoft-365-policies-configurations.md) that are recommended as a starting point for all customers.</span></span> 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a><span data-ttu-id="cc77b-137">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="cc77b-137">Step 3.</span></span> <span data-ttu-id="cc77b-138">Опробуйте возможности — пройдитесь по учебникам по защите среды</span><span class="sxs-lookup"><span data-stu-id="cc77b-138">Try out capabilities — Walk through tutorials for protecting your environment</span></span> 

<span data-ttu-id="cc77b-139">В Microsoft Cloud App Security документации содержится ряд учебных пособий, которые помогут вам обнаружить риски и защитить окружающую среду.</span><span class="sxs-lookup"><span data-stu-id="cc77b-139">The Microsoft Cloud App Security documentation includes a series of tutorials to help you discover risk and protect your environment.</span></span> 

<span data-ttu-id="cc77b-140">Попробуйте Cloud App Security руководства:</span><span class="sxs-lookup"><span data-stu-id="cc77b-140">Try out Cloud App Security tutorials:</span></span>

- [<span data-ttu-id="cc77b-141">Обнаружение подозрительных действий пользователей</span><span class="sxs-lookup"><span data-stu-id="cc77b-141">Detect suspicious user activity</span></span>](/cloud-app-security/tutorial-suspicious-activity)
- [<span data-ttu-id="cc77b-142">Исследование рискованных пользователей</span><span class="sxs-lookup"><span data-stu-id="cc77b-142">Investigate risky users</span></span>](/cloud-app-security/tutorial-ueba)
- [<span data-ttu-id="cc77b-143">Исследование рискованных приложений OAuth</span><span class="sxs-lookup"><span data-stu-id="cc77b-143">Investigate risky OAuth apps</span></span>](/cloud-app-security/investigate-risky-oauth)
- [<span data-ttu-id="cc77b-144">Обнаружение и защита конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="cc77b-144">Discover and protect sensitive information</span></span>](/cloud-app-security/tutorial-dlp)
- [<span data-ttu-id="cc77b-145">Защита любого приложения в организации в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="cc77b-145">Protect any app in your organization in real time</span></span>](/cloud-app-security/tutorial-proxy)
- [<span data-ttu-id="cc77b-146">Блокировка скачивания конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="cc77b-146">Block downloads of sensitive information</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)
- [<span data-ttu-id="cc77b-147">Защита файлов с помощью карантина администратора</span><span class="sxs-lookup"><span data-stu-id="cc77b-147">Protect your files with admin quarantine</span></span>](/cloud-app-security/use-case-admin-quarantine)
- [<span data-ttu-id="cc77b-148">Требуются дополнительные проверки подлинности при рискованных действиях</span><span class="sxs-lookup"><span data-stu-id="cc77b-148">Require step-up authentication upon risky action</span></span>](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a><span data-ttu-id="cc77b-149">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="cc77b-149">Next steps</span></span>

[<span data-ttu-id="cc77b-150">Исследование и реагирование с Microsoft 365 Defender в пилотной среде</span><span class="sxs-lookup"><span data-stu-id="cc77b-150">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>](eval-defender-investigate-respond.md)

<span data-ttu-id="cc77b-151">Возвращайся к обзору [для Оценки Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cc77b-151">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="cc77b-152">Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cc77b-152">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>