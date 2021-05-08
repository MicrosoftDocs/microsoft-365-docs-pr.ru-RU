---
title: Оценка безопасности (Майкрософт)
description: Описывает microsoft Secure Score в центре Microsoft 365 безопасности, как улучшить осанку безопасности и что могут ожидать администраторы безопасности.
keywords: Microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.technology: m365d
ms.openlocfilehash: 4a2c220cab15751671b9b38c3bb2fda3db12c9e1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245381"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="0bb0d-104">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="0bb0d-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0bb0d-105">Оценка безопасности (Майкрософт) — это измерение уровня безопасности организации. Чем выше она, тем больше действий по укреплению безопасности предпринимает организация.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="0bb0d-106">Его можно найти в https://security.microsoft.com/securescore центре [Microsoft 365 безопасности.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="0bb0d-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="0bb0d-107">Следуя рекомендациям по оценке безопасности, вы сможете защитить организацию от угроз.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="0bb0d-108">С централизованной панели мониторинга в центре Microsoft 365 организации могут отслеживать и работать над безопасностью Microsoft 365 удостоверений, приложений и устройств.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="0bb0d-109">Оценка безопасности (Майкрософт) помогает организациям:</span><span class="sxs-lookup"><span data-stu-id="0bb0d-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="0bb0d-110">Отчитываться о текущем состоянии безопасности организации.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="0bb0d-111">Повысить уровень безопасности за счет повышенной способности к обнаружению, видимости, рекомендаций и управления.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="0bb0d-112">Сравнивать данные организации с контрольными показателями и разработать систему ключевых показателей производительности (KPI).</span><span class="sxs-lookup"><span data-stu-id="0bb0d-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="0bb0d-113">Организации получают доступ к надежным визуализациям показателей и тенденций, интеграции с другими продуктами Майкрософт, сопоставлению показателей с аналогичными организациями и многое другое.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="0bb0d-114">Оценка также может отражать, когда сторонние решения рассмотрели рекомендуемые действия.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Домашняя страницы Secure Score](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a><span data-ttu-id="0bb0d-116">Как это работает</span><span class="sxs-lookup"><span data-stu-id="0bb0d-116">How it works</span></span>

<span data-ttu-id="0bb0d-117">Вам даются очки для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="0bb0d-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="0bb0d-118">Настройка рекомендуемых функций безопасности</span><span class="sxs-lookup"><span data-stu-id="0bb0d-118">Configuring recommended security features</span></span>
- <span data-ttu-id="0bb0d-119">Выполнение задач, связанных с безопасностью</span><span class="sxs-lookup"><span data-stu-id="0bb0d-119">Doing security-related tasks</span></span>
- <span data-ttu-id="0bb0d-120">Решение действия по улучшению с помощью сторонних приложений или программного обеспечения или альтернативного смягчения</span><span class="sxs-lookup"><span data-stu-id="0bb0d-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="0bb0d-121">Некоторые действия по улучшению дают очки только при полном заполнении.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="0bb0d-122">Некоторые дают частичные очки, если они завершены для некоторых устройств или пользователей.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="0bb0d-123">Если вы не можете или не хотите принимать одно из действий по улучшению, вы можете принять риск или оставшийся риск.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="0bb0d-124">Если у вас есть лицензия на один из поддерживаемых продуктов Майкрософт, вы увидите рекомендации для этих продуктов.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="0bb0d-125">Мы покажем полный набор возможных улучшений для продукта независимо от выпуска лицензии, подписки или плана.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="0bb0d-126">Таким образом, вы сможете понять лучшие методы безопасности и улучшить свои оценки.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="0bb0d-127">Ваша абсолютная позиция безопасности, представленная службой Secure Score, остается одинаковой независимо от того, какие лицензии у организации имеются для определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="0bb0d-128">Помните, что необходимо всегда находить баланс между безопасностью и удобством работы, поэтому не все рекомендации подойдут для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="0bb0d-129">Ваша оценка обновляется в режиме реального времени, чтобы отражать сведения, представленные на страницах визуализаций и действий по улучшению.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="0bb0d-130">Secure Score также синхронизируется ежедневно, чтобы получать системные данные о достигнутых баллах для каждого действия.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="0bb0d-131">Ключевые сценарии</span><span class="sxs-lookup"><span data-stu-id="0bb0d-131">Key scenarios</span></span>

- [<span data-ttu-id="0bb0d-132">Проверка текущего балла</span><span class="sxs-lookup"><span data-stu-id="0bb0d-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="0bb0d-133">Сравните свой счет с организациями, как ваша</span><span class="sxs-lookup"><span data-stu-id="0bb0d-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="0bb0d-134">Просмотр действий по улучшению и решение плана действий</span><span class="sxs-lookup"><span data-stu-id="0bb0d-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="0bb0d-135">Инициировать потоки работы для расследования или реализации</span><span class="sxs-lookup"><span data-stu-id="0bb0d-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="0bb0d-136">Как засмеяются действия по улучшению</span><span class="sxs-lookup"><span data-stu-id="0bb0d-136">How improvement actions are scored</span></span>

<span data-ttu-id="0bb0d-137">Каждое действие по улучшению стоит 10 баллов или меньше, и большинство из них забиты двоичным способом.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="0bb0d-138">Если реализовать действие по улучшению, например создать новую политику или включить определенный параметр, вы получите 100% баллов.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="0bb0d-139">Для других действий по улучшению очки даются в процентах от общей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="0bb0d-140">Например, в действии по улучшению указывается, что вы получаете 10 баллов, защищая всех пользователей с помощью многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="0bb0d-141">У вас только 50 из 100 пользователей защищены, поэтому вы получите частичный балл в 5 баллов (50 защищенных / 100 всего \* 10 max pts = 5 баллов).</span><span class="sxs-lookup"><span data-stu-id="0bb0d-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="0bb0d-142">Продукты, включенные в secure Score</span><span class="sxs-lookup"><span data-stu-id="0bb0d-142">Products included in Secure Score</span></span>

<span data-ttu-id="0bb0d-143">В настоящее время существуют рекомендации для следующих продуктов:</span><span class="sxs-lookup"><span data-stu-id="0bb0d-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="0bb0d-144">Microsoft 365 (включая Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="0bb0d-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="0bb0d-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0bb0d-145">Azure Active Directory</span></span>
- <span data-ttu-id="0bb0d-146">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0bb0d-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="0bb0d-147">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="0bb0d-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="0bb0d-148">Безопасность облачных приложений</span><span class="sxs-lookup"><span data-stu-id="0bb0d-148">Cloud App Security</span></span>
- <span data-ttu-id="0bb0d-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0bb0d-149">Microsoft Teams</span></span>

<span data-ttu-id="0bb0d-150">Рекомендации для других продуктов безопасности скоро.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="0bb0d-151">Рекомендации не охватывают все поверхности атаки, связанные с каждым продуктом, но они хороший базовый уровень.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="0bb0d-152">Вы также можете отметить действия по улучшению, охватываемых стороной или альтернативной мерой смягчения.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="0bb0d-153">Параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0bb0d-153">Security defaults</span></span>

<span data-ttu-id="0bb0d-154">Microsoft Secure Score обновила действия по улучшению для поддержки Azure Active Directory безопасности в [Azure Active Directory,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)что упрощает защиту организации с заранее настроенными настройками безопасности для распространенных атак.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="0bb0d-155">Если включить по умолчанию безопасность, вам будут награждаться полные баллы за следующие действия по улучшению:</span><span class="sxs-lookup"><span data-stu-id="0bb0d-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="0bb0d-156">Убедитесь, что все пользователи могут выполнить многофакторную проверку подлинности для безопасного доступа (9 баллов)</span><span class="sxs-lookup"><span data-stu-id="0bb0d-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="0bb0d-157">Требуется MFA для административных ролей (10 баллов)</span><span class="sxs-lookup"><span data-stu-id="0bb0d-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="0bb0d-158">Включить политику для блокировки устаревшей проверки подлинности (7 баллов)</span><span class="sxs-lookup"><span data-stu-id="0bb0d-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="0bb0d-159">По умолчанию для безопасности включаются функции безопасности, которые обеспечивают аналогичную безопасность действиям по улучшению "политики риска для входов" и "политики риска пользователей".</span><span class="sxs-lookup"><span data-stu-id="0bb0d-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="0bb0d-160">Вместо настройки этих политик поверх по умолчанию безопасности рекомендуется обновить их состояния до "Разрешено с помощью альтернативного смягчения".</span><span class="sxs-lookup"><span data-stu-id="0bb0d-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="0bb0d-161">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="0bb0d-161">Required permissions</span></span>

<span data-ttu-id="0bb0d-162">Чтобы получить разрешение на доступ к Microsoft Secure Score, вам должна быть назначена одна из следующих ролей в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="0bb0d-163">Чтение и написание ролей</span><span class="sxs-lookup"><span data-stu-id="0bb0d-163">Read and write roles</span></span>

<span data-ttu-id="0bb0d-164">С помощью доступа к чтениям и записи можно вносить изменения и напрямую взаимодействовать с Secure Score.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="0bb0d-165">Вы также можете назначить доступ только для чтения другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="0bb0d-166">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="0bb0d-166">Global administrator</span></span>
* <span data-ttu-id="0bb0d-167">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="0bb0d-167">Security administrator</span></span>
* <span data-ttu-id="0bb0d-168">Администратор Exchange</span><span class="sxs-lookup"><span data-stu-id="0bb0d-168">Exchange administrator</span></span>
* <span data-ttu-id="0bb0d-169">Администратор SharePoint</span><span class="sxs-lookup"><span data-stu-id="0bb0d-169">SharePoint administrator</span></span>
* <span data-ttu-id="0bb0d-170">Администратор учетной записи</span><span class="sxs-lookup"><span data-stu-id="0bb0d-170">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="0bb0d-171">Роли только для чтения</span><span class="sxs-lookup"><span data-stu-id="0bb0d-171">Read-only roles</span></span>

<span data-ttu-id="0bb0d-172">При доступе только для чтения вы не сможете изменить состояние или заметки для действия по улучшению, изменить зоны оценки или изменить настраиваемые сравнения.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-172">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="0bb0d-173">Администратор службы поддержки</span><span class="sxs-lookup"><span data-stu-id="0bb0d-173">Helpdesk administrator</span></span>
* <span data-ttu-id="0bb0d-174">Администратор пользователей</span><span class="sxs-lookup"><span data-stu-id="0bb0d-174">User administrator</span></span>
* <span data-ttu-id="0bb0d-175">Администратор служб</span><span class="sxs-lookup"><span data-stu-id="0bb0d-175">Service administrator</span></span>
* <span data-ttu-id="0bb0d-176">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="0bb0d-176">Security reader</span></span>
* <span data-ttu-id="0bb0d-177">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="0bb0d-177">Security operator</span></span>
* <span data-ttu-id="0bb0d-178">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="0bb0d-178">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="0bb0d-179">Осведомленность о рисках</span><span class="sxs-lookup"><span data-stu-id="0bb0d-179">Risk awareness</span></span>

<span data-ttu-id="0bb0d-180">Microsoft Secure Score — это числовая сводка о вашей позиции безопасности, основанная на конфигурациях системы, поведении пользователей и других измерениях, связанных с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-180">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="0bb0d-181">Это не абсолютное измерение вероятности нарушения системы или данных.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-181">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="0bb0d-182">Скорее, он представляет степень, в которой вы приняли элементы управления безопасностью в среде Майкрософт, которые могут помочь компенсировать риск нарушения.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-182">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="0bb0d-183">Ни одна служба в Интернете не защищена от нарушений безопасности, и оценка безопасности не должна быть интерпретируется как гарантия от нарушения безопасности любым способом.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-183">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="0bb0d-184">Мы ждем ваших отзывов!</span><span class="sxs-lookup"><span data-stu-id="0bb0d-184">We want to hear from you</span></span>

<span data-ttu-id="0bb0d-185">Если у вас есть какие-либо проблемы, дайте нам знать, разместив в сообществе [безопасность, конфиденциальность & соответствия](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) требованиям.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-185">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="0bb0d-186">Мы отслеживаем сообщество и предоставляем помощь.</span><span class="sxs-lookup"><span data-stu-id="0bb0d-186">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="0bb0d-187">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="0bb0d-187">Related resources</span></span>

- [<span data-ttu-id="0bb0d-188">Доступ к состоянию безопасности</span><span class="sxs-lookup"><span data-stu-id="0bb0d-188">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="0bb0d-189">Отслеживание истории microsoft Secure Score и достижения целей</span><span class="sxs-lookup"><span data-stu-id="0bb0d-189">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="0bb0d-190">Что вскоре появится</span><span class="sxs-lookup"><span data-stu-id="0bb0d-190">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="0bb0d-191">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="0bb0d-191">What's new</span></span>](microsoft-secure-score-whats-new.md)