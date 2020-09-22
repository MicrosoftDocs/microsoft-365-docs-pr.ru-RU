---
title: Оценка безопасности (Майкрософт)
description: В этой статье описывается уровень безопасности Майкрософт в центре безопасности Майкрософт 365, объясняется, как оптимизировать безопасность и какие администраторы могут ожидать.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, Оценка безопасности, центр безопасности, действия по улучшению
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: b378288637baa5b51f74fb63d8c8da33ac5e148f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196195"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="89365-104">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="89365-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="89365-105">Microsoft Secure Score — это измерение степени безопасности Организации с большим номером, указывающим дополнительные действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="89365-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="89365-106">Его можно найти https://security.microsoft.com/securescore в [центре безопасности Microsoft 365](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="89365-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="89365-107">Следуя рекомендациям по оценке безопасности, можно защитить организацию от угроз.</span><span class="sxs-lookup"><span data-stu-id="89365-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="89365-108">С помощью централизованной панели мониторинга в центре безопасности Майкрософт 365 организации могут отслеживать и работать с безопасностью удостоверений, данных, приложений, устройств и инфраструктуры Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89365-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="89365-109">Оценка безопасности помогает организациям:</span><span class="sxs-lookup"><span data-stu-id="89365-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="89365-110">Отчет по текущему состоянию уровня безопасности Организации.</span><span class="sxs-lookup"><span data-stu-id="89365-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="89365-111">Улучшите обеспечение безопасности, предоставляя возможность обнаружения, отображения, рекомендаций и контроля.</span><span class="sxs-lookup"><span data-stu-id="89365-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="89365-112">Сравните со показателями производительности и создайте ключевые индикаторы производительности (KPI).</span><span class="sxs-lookup"><span data-stu-id="89365-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="89365-113">Организации получают доступ к надежным визуализациям показателей и тенденций, интеграции с другими продуктами Майкрософт, сравнению оценок с похожими организациями и многое другое.</span><span class="sxs-lookup"><span data-stu-id="89365-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="89365-114">Оценка также может отражать, когда сторонние решения решают Рекомендуемые действия.</span><span class="sxs-lookup"><span data-stu-id="89365-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Домашняя страница оценки безопасности](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="89365-116">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="89365-116">How it works</span></span>

<span data-ttu-id="89365-117">Вы задаюте баллы для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="89365-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="89365-118">Настройка рекомендуемых функций безопасности</span><span class="sxs-lookup"><span data-stu-id="89365-118">Configuring recommended security features</span></span>
- <span data-ttu-id="89365-119">Выполнение задач, связанных с безопасностью</span><span class="sxs-lookup"><span data-stu-id="89365-119">Performing security-related tasks</span></span>
- <span data-ttu-id="89365-120">Устранение действия по улучшению с приложением или программным обеспечением стороннего производителя или альтернативным снижением</span><span class="sxs-lookup"><span data-stu-id="89365-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="89365-121">Некоторые действия по улучшению приводят к отрезкам только при полном завершении.</span><span class="sxs-lookup"><span data-stu-id="89365-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="89365-122">Некоторые точки могут быть неполными, если они выполнены для некоторых устройств или пользователей.</span><span class="sxs-lookup"><span data-stu-id="89365-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="89365-123">Если вы не можете или не хотите использовать одно из действий по улучшению, вы можете принять риск или оставшийся риск.</span><span class="sxs-lookup"><span data-stu-id="89365-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="89365-124">Если у вас есть лицензия на один из поддерживаемых продуктов корпорации Майкрософт, вы увидите рекомендации для этих продуктов.</span><span class="sxs-lookup"><span data-stu-id="89365-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="89365-125">Мы покажем вам полный набор возможных усовершенствований для продукта независимо от выпуска лицензии, подписки или плана.</span><span class="sxs-lookup"><span data-stu-id="89365-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="89365-126">Таким образом, вы можете ознакомиться с рекомендациями по обеспечению безопасности и увеличить рейтинг.</span><span class="sxs-lookup"><span data-stu-id="89365-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="89365-127">Абсолютная безопасность, представленная показателем безопасности, остается без изменений, независимо от того, какие лицензии у вашей организации принадлежат определенному продукту.</span><span class="sxs-lookup"><span data-stu-id="89365-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="89365-128">Имейте в виду, что безопасность должна быть сбалансирована с удобством использования, а не все рекомендации могут работать в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="89365-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="89365-129">Ваш рейтинг обновляется в режиме реального времени, чтобы отразить информацию, представленную на страницах зрительных образов и действий по улучшению.</span><span class="sxs-lookup"><span data-stu-id="89365-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="89365-130">Показатель безопасности также синхронизируется ежедневно, чтобы получать системные данные о полученных баллах для каждого действия.</span><span class="sxs-lookup"><span data-stu-id="89365-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="89365-131">Основные сценарии</span><span class="sxs-lookup"><span data-stu-id="89365-131">Key scenarios</span></span>

- [<span data-ttu-id="89365-132">Проверка текущего показателя</span><span class="sxs-lookup"><span data-stu-id="89365-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="89365-133">Сравните свой рейтинг с организациями, такими как ваши</span><span class="sxs-lookup"><span data-stu-id="89365-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="89365-134">Просмотр действий по улучшению и выбор плана действий</span><span class="sxs-lookup"><span data-stu-id="89365-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="89365-135">Инициация рабочих потоков для изучения или реализации</span><span class="sxs-lookup"><span data-stu-id="89365-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="89365-136">Интеграция центра безопасности Microsoft 365 и ServiceNow</span><span class="sxs-lookup"><span data-stu-id="89365-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="89365-137">Как оцениваются действия по улучшению</span><span class="sxs-lookup"><span data-stu-id="89365-137">How improvement actions are scored</span></span>

<span data-ttu-id="89365-138">Каждое действие по улучшению стоит не более 10 баллов, а большинство — в двоичном виде.</span><span class="sxs-lookup"><span data-stu-id="89365-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="89365-139">Если вы реализуете действие улучшения, например создание новой политики или включение определенного параметра, вы получаете 100% точек.</span><span class="sxs-lookup"><span data-stu-id="89365-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="89365-140">Для других действий по улучшению точки задаются в процентах от общей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="89365-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="89365-141">Например, действие по улучшению дает 10 баллов, защищая всех пользователей с многофакторной проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="89365-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="89365-142">Общее количество защищенных пользователей составляет 50 из 100, поэтому вы получите частичный показатель из 5 баллов (всего 50 защита/100 \* 10 ПТС = 5 ПТС).</span><span class="sxs-lookup"><span data-stu-id="89365-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="89365-143">Продукты, включенные в надежный рейтинг</span><span class="sxs-lookup"><span data-stu-id="89365-143">Products included in Secure Score</span></span>

<span data-ttu-id="89365-144">В настоящее время существуют рекомендации для Microsoft 365 (включая Exchange Online), Azure Active Directory, Office Defender ATP, Azure ATP и Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="89365-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="89365-145">Рекомендации по другим продуктам безопасности скоро будут доступны.</span><span class="sxs-lookup"><span data-stu-id="89365-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="89365-146">Рекомендации не охватывают все области атак, связанные с каждым продуктом, но они являются хорошим базовым планом.</span><span class="sxs-lookup"><span data-stu-id="89365-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="89365-147">Вы также можете пометить действия по улучшению, как это описано сторонним производителем или альтернативным снижением.</span><span class="sxs-lookup"><span data-stu-id="89365-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="89365-148">Параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="89365-148">Security defaults</span></span>

<span data-ttu-id="89365-149">Microsoft Security Score обновил действия по улучшению для поддержки параметров [безопасности по умолчанию в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), что облегчит защиту Организации с помощью предварительно настроенных параметров безопасности для распространенных атак.</span><span class="sxs-lookup"><span data-stu-id="89365-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="89365-150">Если включен параметр безопасности по умолчанию, будут выделены полные баллы для следующих действий по улучшению:</span><span class="sxs-lookup"><span data-stu-id="89365-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="89365-151">Убедитесь, что все пользователи могут выполнять многофакторную проверку подлинности для безопасного доступа (9 точек).</span><span class="sxs-lookup"><span data-stu-id="89365-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="89365-152">Требовать использование MFA для административных ролей (10 точек)</span><span class="sxs-lookup"><span data-stu-id="89365-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="89365-153">Включение политики для блокирования устаревшей проверки подлинности (7 точек)</span><span class="sxs-lookup"><span data-stu-id="89365-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="89365-154">По умолчанию параметры безопасности включают функции безопасности, обеспечивающие подобную безопасность для действий по улучшению "Политика риска входа" и "Политика риска пользователей".</span><span class="sxs-lookup"><span data-stu-id="89365-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="89365-155">Вместо настройки этих политик на основе значений по умолчанию для безопасности рекомендуется обновить их состояния на "устранение с помощью альтернативного способа устранения".</span><span class="sxs-lookup"><span data-stu-id="89365-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="89365-156">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="89365-156">Required permissions</span></span>

<span data-ttu-id="89365-157">Чтобы получить доступ к показателю безопасности Майкрософт, необходимо назначить одну из следующих ролей в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="89365-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="89365-158">Чтение и запись ролей</span><span class="sxs-lookup"><span data-stu-id="89365-158">Read and write roles</span></span>

<span data-ttu-id="89365-159">Доступ для чтения и записи позволяет вносить изменения и напрямую взаимодействовать с рейтингом безопасности.</span><span class="sxs-lookup"><span data-stu-id="89365-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="89365-160">Вы также можете назначить доступ только для чтения другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="89365-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="89365-161">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="89365-161">Global administrator</span></span>
* <span data-ttu-id="89365-162">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="89365-162">Security administrator</span></span>
* <span data-ttu-id="89365-163">Администратор Exchange</span><span class="sxs-lookup"><span data-stu-id="89365-163">Exchange administrator</span></span>
* <span data-ttu-id="89365-164">администратор SharePoint.</span><span class="sxs-lookup"><span data-stu-id="89365-164">SharePoint administrator</span></span>
* <span data-ttu-id="89365-165">Администратор учетной записи</span><span class="sxs-lookup"><span data-stu-id="89365-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="89365-166">Роли, предназначенные только для чтения</span><span class="sxs-lookup"><span data-stu-id="89365-166">Read-only roles</span></span>

<span data-ttu-id="89365-167">При доступе только для чтения вы не можете изменять состояние или примечания для действий по улучшению, изменения зон оценок и изменения пользовательских сравнений.</span><span class="sxs-lookup"><span data-stu-id="89365-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="89365-168">Администратор службы поддержки</span><span class="sxs-lookup"><span data-stu-id="89365-168">Helpdesk administrator</span></span>
* <span data-ttu-id="89365-169">Администратор пользователей</span><span class="sxs-lookup"><span data-stu-id="89365-169">User administrator</span></span>
* <span data-ttu-id="89365-170">Администратор служб</span><span class="sxs-lookup"><span data-stu-id="89365-170">Service administrator</span></span>
* <span data-ttu-id="89365-171">Читатель безопасности</span><span class="sxs-lookup"><span data-stu-id="89365-171">Security reader</span></span>
* <span data-ttu-id="89365-172">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="89365-172">Security operator</span></span>
* <span data-ttu-id="89365-173">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="89365-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="89365-174">Осведомленность о рисках</span><span class="sxs-lookup"><span data-stu-id="89365-174">Risk awareness</span></span>

<span data-ttu-id="89365-175">Microsoft Secure Score — это численная сводка по обеспечению безопасности в соответствии с конфигурацией системы, поведением пользователей и другими измерениями, связанными с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="89365-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="89365-176">Это не абсолютное измерение того, насколько вероятнее всего нарушается система или данные.</span><span class="sxs-lookup"><span data-stu-id="89365-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="89365-177">Вместо этого он представляет собой область, в которой вы настроили элементы управления безопасностью в среде Майкрософт, которые могут способствовать ослаблению риска нарушения.</span><span class="sxs-lookup"><span data-stu-id="89365-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="89365-178">Веб-служба не полностью защищена от нарушений безопасности, а контрольный показатель не должен интерпретироваться каким-либо способом нарушения безопасности.</span><span class="sxs-lookup"><span data-stu-id="89365-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="89365-179">Мы хотим услышать вас</span><span class="sxs-lookup"><span data-stu-id="89365-179">We want to hear from you</span></span>

<span data-ttu-id="89365-180">Если у вас возникли какие – либо проблемы, сообщите нам о публикации в разделе [безопасность, конфиденциальность & соответствие требованиям](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="89365-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="89365-181">Мы отслеживаем сообщество и предоставите вам помощь.</span><span class="sxs-lookup"><span data-stu-id="89365-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="89365-182">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="89365-182">Related resources</span></span>

- [<span data-ttu-id="89365-183">Оценка уровня безопасности</span><span class="sxs-lookup"><span data-stu-id="89365-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="89365-184">Отслеживание журнала оценки безопасности Майкрософт и соответствующих целей</span><span class="sxs-lookup"><span data-stu-id="89365-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="89365-185">Что вскоре появится</span><span class="sxs-lookup"><span data-stu-id="89365-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="89365-186">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="89365-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
