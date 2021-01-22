---
title: Оценка безопасности (Майкрософт)
description: В этой статье описывается оценка безопасности (Майкрософт) в Центре безопасности Microsoft 365, как повысить уровень безопасности и чего могут ожидать администраторы безопасности.
keywords: оценка безопасности Майкрософт, оценка безопасности, оценка безопасности Office 365, оценка безопасности Майкрософт, Центр безопасности Microsoft 365, действия по улучшению
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: a0f4307cc0ed42a8ed53cdeefdb0a7b32eb36d35
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930586"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="b0246-104">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b0246-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b0246-105">Оценка безопасности (Майкрософт) — это показатель уровня безопасности организации, где большее число указывает на дополнительные действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="b0246-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="b0246-106">Его можно найти в Центре безопасности https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="b0246-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="b0246-107">Следуя рекомендациям по оценке безопасности, можно защитить организацию от угроз.</span><span class="sxs-lookup"><span data-stu-id="b0246-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="b0246-108">С помощью централизованной панели мониторинга в Центре безопасности Microsoft 365 организации могут отслеживать и работать над безопасностью удостоверений, приложений и устройств Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0246-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="b0246-109">Оценка безопасности помогает организациям:</span><span class="sxs-lookup"><span data-stu-id="b0246-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="b0246-110">Отчет о текущем состоянии безопасности организации.</span><span class="sxs-lookup"><span data-stu-id="b0246-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="b0246-111">Повышение уровня безопасности путем обеспечения возможности обнаружения, видимости, рекомендаций и контроля.</span><span class="sxs-lookup"><span data-stu-id="b0246-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="b0246-112">Сравнение с контрольными показателями и создание ключевых показателей эффективности.</span><span class="sxs-lookup"><span data-stu-id="b0246-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="b0246-113">Организации получают доступ к надежной визуализации метрик и тенденций, интеграции с другими продуктами Майкрософт, сравнения показателей с аналогичными организациями и многое другое.</span><span class="sxs-lookup"><span data-stu-id="b0246-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="b0246-114">Этот показатель также может отражать, когда сторонние решения рассмотрели рекомендуемые действия.</span><span class="sxs-lookup"><span data-stu-id="b0246-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Домашняя страницы "Оценка безопасности"](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="b0246-116">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="b0246-116">How it works</span></span>

<span data-ttu-id="b0246-117">Вам даются баллы для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="b0246-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="b0246-118">Настройка рекомендуемых функций безопасности</span><span class="sxs-lookup"><span data-stu-id="b0246-118">Configuring recommended security features</span></span>
- <span data-ttu-id="b0246-119">Выполнение задач, связанных с безопасностью</span><span class="sxs-lookup"><span data-stu-id="b0246-119">Doing security-related tasks</span></span>
- <span data-ttu-id="b0246-120">Устранение действий по улучшению со сторонним приложением или программным обеспечением или альтернативное решение</span><span class="sxs-lookup"><span data-stu-id="b0246-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="b0246-121">Некоторые действия по улучшению дают баллы только после полного завершения.</span><span class="sxs-lookup"><span data-stu-id="b0246-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="b0246-122">Некоторые из них дают частичные точки, если они завершены для некоторых устройств или пользователей.</span><span class="sxs-lookup"><span data-stu-id="b0246-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="b0246-123">Если вы не можете или не хотите принять одно из действий по улучшению, вы можете принять на себя риск или оставшийся риск.</span><span class="sxs-lookup"><span data-stu-id="b0246-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="b0246-124">Если у вас есть лицензия на один из поддерживаемых продуктов Майкрософт, вы увидите рекомендации по этим продуктам.</span><span class="sxs-lookup"><span data-stu-id="b0246-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="b0246-125">Мы покажем полный набор возможных улучшений для продукта независимо от выпуска лицензии, подписки или плана.</span><span class="sxs-lookup"><span data-stu-id="b0246-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="b0246-126">Таким образом, вы сможете понять советы по обеспечению безопасности и улучшить свой показатель.</span><span class="sxs-lookup"><span data-stu-id="b0246-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="b0246-127">Ваш абсолютный режим безопасности, представленный оценкой безопасности, остается таким же, независимо от того, какие лицензии у вашей организации есть для определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="b0246-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="b0246-128">Помните, что безопасность должна быть сбалансирована с доступностью, и не все рекомендации могут работать в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="b0246-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="b0246-129">Оценка обновляется в режиме реального времени, чтобы отразить информацию, представленную на страницах визуализаций и действий по улучшению.</span><span class="sxs-lookup"><span data-stu-id="b0246-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="b0246-130">Оценка безопасности также синхронизируется ежедневно для получения системных данных о полученных баллах для каждого действия.</span><span class="sxs-lookup"><span data-stu-id="b0246-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="b0246-131">Основные сценарии</span><span class="sxs-lookup"><span data-stu-id="b0246-131">Key scenarios</span></span>

- [<span data-ttu-id="b0246-132">Проверка текущей оценки</span><span class="sxs-lookup"><span data-stu-id="b0246-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="b0246-133">Сравнение показателей с организациями, например вашей</span><span class="sxs-lookup"><span data-stu-id="b0246-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="b0246-134">Просмотр действий по улучшению и решение плана действий</span><span class="sxs-lookup"><span data-stu-id="b0246-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="b0246-135">Инициировать потоки работы для изучения или реализации</span><span class="sxs-lookup"><span data-stu-id="b0246-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="b0246-136">Как зассмеяются действия по улучшению</span><span class="sxs-lookup"><span data-stu-id="b0246-136">How improvement actions are scored</span></span>

<span data-ttu-id="b0246-137">Каждое действие по улучшению стоит не более 10 баллов, и большинство из них засмеяются двоичным способом.</span><span class="sxs-lookup"><span data-stu-id="b0246-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="b0246-138">Если реализовать действие по улучшению, например создать новую политику или включить определенный параметр, вы получите 100 % баллов.</span><span class="sxs-lookup"><span data-stu-id="b0246-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="b0246-139">Для других действий по улучшению точки даются в процентах от общей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b0246-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="b0246-140">Например, действие улучшения указывает, что вы получаете 10 баллов, защищая всех пользователей с помощью многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b0246-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="b0246-141">Вы защищаете только 50 из 100 всех пользователей, поэтому вы получите частичный показатель в 5 баллов (50 защищенных / 100 всего \* 10 макс. pts = 5 pts).</span><span class="sxs-lookup"><span data-stu-id="b0246-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="b0246-142">Продукты, включенные в оценку безопасности</span><span class="sxs-lookup"><span data-stu-id="b0246-142">Products included in Secure Score</span></span>

<span data-ttu-id="b0246-143">В настоящее время существуют рекомендации для следующих продуктов:</span><span class="sxs-lookup"><span data-stu-id="b0246-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="b0246-144">Microsoft 365 (включая Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="b0246-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="b0246-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b0246-145">Azure Active Directory</span></span>
- <span data-ttu-id="b0246-146">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b0246-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="b0246-147">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="b0246-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="b0246-148">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b0246-148">Cloud App Security</span></span>

<span data-ttu-id="b0246-149">Рекомендации по другим продуктам безопасности будут готовы в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="b0246-149">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="b0246-150">Рекомендации охватывают не все поверхности атаки, связанные с каждым продуктом, но они хорошо за основу.</span><span class="sxs-lookup"><span data-stu-id="b0246-150">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="b0246-151">Вы также можете пометить действия по улучшению, охватываемых сторонними или альтернативными мерами.</span><span class="sxs-lookup"><span data-stu-id="b0246-151">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="b0246-152">Параметры безопасности по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b0246-152">Security defaults</span></span>

<span data-ttu-id="b0246-153">Оценка безопасности (Майкрософт) обновила действия по улучшению для поддержки стандартных параметров безопасности [в Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)что упрощает защиту организации с помощью предварительно настроенных параметров безопасности для распространенных атак.</span><span class="sxs-lookup"><span data-stu-id="b0246-153">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="b0246-154">Если включить настройки безопасности по умолчанию, вам будут присвоены полные баллы за следующие действия по улучшению:</span><span class="sxs-lookup"><span data-stu-id="b0246-154">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="b0246-155">Убедитесь, что все пользователи могут пройти многофакторную проверку подлинности для безопасного доступа (9 баллов)</span><span class="sxs-lookup"><span data-stu-id="b0246-155">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="b0246-156">Требовать MFA для административных ролей (10 баллов)</span><span class="sxs-lookup"><span data-stu-id="b0246-156">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="b0246-157">Включить политику для блокировки устаревшей проверки подлинности (7 баллов)</span><span class="sxs-lookup"><span data-stu-id="b0246-157">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="b0246-158">Значения по умолчанию для системы безопасности включают функции безопасности, которые обеспечивают аналогичные действия по улучшению "политики риска для входов" и "политики риска для пользователей".</span><span class="sxs-lookup"><span data-stu-id="b0246-158">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="b0246-159">Вместо того чтобы настраивать эти политики поверх стандартных параметров безопасности, мы рекомендуем обновить их состояние до "Разрешено с помощью альтернативной меры защиты".</span><span class="sxs-lookup"><span data-stu-id="b0246-159">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="b0246-160">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="b0246-160">Required permissions</span></span>

<span data-ttu-id="b0246-161">Чтобы иметь разрешение на доступ к оценке безопасности (Майкрософт), вам должна быть назначена одна из следующих ролей в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b0246-161">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="b0246-162">Чтение и написание ролей</span><span class="sxs-lookup"><span data-stu-id="b0246-162">Read and write roles</span></span>

<span data-ttu-id="b0246-163">С помощью доступа на чтение и записи вы можете вносить изменения и напрямую взаимодействовать с оценкой безопасности.</span><span class="sxs-lookup"><span data-stu-id="b0246-163">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="b0246-164">Вы также можете назначить доступ только для чтения другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="b0246-164">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="b0246-165">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="b0246-165">Global administrator</span></span>
* <span data-ttu-id="b0246-166">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="b0246-166">Security administrator</span></span>
* <span data-ttu-id="b0246-167">Администратор Exchange</span><span class="sxs-lookup"><span data-stu-id="b0246-167">Exchange administrator</span></span>
* <span data-ttu-id="b0246-168">Администратор SharePoint</span><span class="sxs-lookup"><span data-stu-id="b0246-168">SharePoint administrator</span></span>
* <span data-ttu-id="b0246-169">Администратор учетной записи</span><span class="sxs-lookup"><span data-stu-id="b0246-169">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="b0246-170">Роли только для чтения</span><span class="sxs-lookup"><span data-stu-id="b0246-170">Read-only roles</span></span>

<span data-ttu-id="b0246-171">При доступе только для чтения вы не можете изменять состояние или заметки для действия по улучшению, изменять зоны показателей или настраиваемые сравнения.</span><span class="sxs-lookup"><span data-stu-id="b0246-171">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="b0246-172">Администратор службы поддержки</span><span class="sxs-lookup"><span data-stu-id="b0246-172">Helpdesk administrator</span></span>
* <span data-ttu-id="b0246-173">Администратор пользователей</span><span class="sxs-lookup"><span data-stu-id="b0246-173">User administrator</span></span>
* <span data-ttu-id="b0246-174">Администратор служб</span><span class="sxs-lookup"><span data-stu-id="b0246-174">Service administrator</span></span>
* <span data-ttu-id="b0246-175">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="b0246-175">Security reader</span></span>
* <span data-ttu-id="b0246-176">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="b0246-176">Security operator</span></span>
* <span data-ttu-id="b0246-177">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="b0246-177">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="b0246-178">Осведомленность о рисках</span><span class="sxs-lookup"><span data-stu-id="b0246-178">Risk awareness</span></span>

<span data-ttu-id="b0246-179">Оценка безопасности (Майкрософт) — это числовая сводка о состоянии безопасности на основе конфигураций системы, поведения пользователей и других показателей безопасности.</span><span class="sxs-lookup"><span data-stu-id="b0246-179">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="b0246-180">Это не абсолютное измерение вероятности нарушения безопасности системы или данных.</span><span class="sxs-lookup"><span data-stu-id="b0246-180">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="b0246-181">Он представляет степень, до которой в среде Майкрософт были приняты меры безопасности, которые могут помочь снизить риск нарушения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b0246-181">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="b0246-182">Ни одна веб-служба не защищена от нарушений безопасности, и оценку безопасности не следует интерпретировать как гарантии нарушения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b0246-182">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="b0246-183">Мы ждем ваших отзывов!</span><span class="sxs-lookup"><span data-stu-id="b0246-183">We want to hear from you</span></span>

<span data-ttu-id="b0246-184">Если у вас есть какие-либо проблемы, дайте нам знать, опубликовав в сообществе по [безопасности, & соответствия требованиям.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="b0246-184">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="b0246-185">Мы отслеживаем сообщество и предоставляем помощь.</span><span class="sxs-lookup"><span data-stu-id="b0246-185">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="b0246-186">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="b0246-186">Related resources</span></span>

- [<span data-ttu-id="b0246-187">Оценка уровня безопасности</span><span class="sxs-lookup"><span data-stu-id="b0246-187">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="b0246-188">Отслеживание истории оценки безопасности (Майкрософт) и обеспечение достижения целей</span><span class="sxs-lookup"><span data-stu-id="b0246-188">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="b0246-189">Что вскоре появится</span><span class="sxs-lookup"><span data-stu-id="b0246-189">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="b0246-190">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="b0246-190">What's new</span></span>](microsoft-secure-score-whats-new.md)
