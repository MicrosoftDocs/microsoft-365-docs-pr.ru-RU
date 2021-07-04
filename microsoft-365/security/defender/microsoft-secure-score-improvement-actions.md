---
title: Оценка положения в области безопасности с помощью microsoft Secure Score
description: Описывает действия по улучшению показателей безопасности Microsoft в центре Microsoft 365 безопасности.
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
ms.collection: M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: c4d4958c03bee7301465c16fef2cd4ff8adb1722
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288459"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="5472d-104">Оценка позы безопасности с помощью microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="5472d-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5472d-105">Оценка безопасности (Майкрософт) — это измерение уровня безопасности организации. Чем выше она, тем больше действий по укреплению безопасности предпринимает организация.</span><span class="sxs-lookup"><span data-stu-id="5472d-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="5472d-106">Его можно найти в https://security.microsoft.com/securescore центре [Microsoft 365 безопасности.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="5472d-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="5472d-107">Чтобы быстрее найти нужные сведения, действия по улучшению Майкрософт организованы в группы:</span><span class="sxs-lookup"><span data-stu-id="5472d-107">To help you find the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

- <span data-ttu-id="5472d-108">Identity (Azure Active Directory учетные записи & ролей)</span><span class="sxs-lookup"><span data-stu-id="5472d-108">Identity (Azure Active Directory accounts & roles)</span></span>
- <span data-ttu-id="5472d-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices)](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)</span><span class="sxs-lookup"><span data-stu-id="5472d-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
- <span data-ttu-id="5472d-110">Приложения (приложения электронной почты и облачные приложения, включая Office 365 и Microsoft Cloud App Security)</span><span class="sxs-lookup"><span data-stu-id="5472d-110">Apps (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="5472d-111">В недавнем выпуске Microsoft Secure Score была выпущена улучшенная модель оценки, которая временно несовместима с показателем безопасности удостоверений и API Graph API.</span><span class="sxs-lookup"><span data-stu-id="5472d-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="5472d-112">Просмотреть сведения</span><span class="sxs-lookup"><span data-stu-id="5472d-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="5472d-113">На странице Обзор результатов microsoft Secure Score можно просмотреть, как разделять точки между этими группами и какие точки доступны.</span><span class="sxs-lookup"><span data-stu-id="5472d-113">In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available.</span></span> <span data-ttu-id="5472d-114">Вы также можете получить полное представление общего балла, исторического тренда вашего безопасного балла с сравнениями эталонных показателей, а также приоритетные действия по улучшению, которые можно принять для улучшения вашего счета.</span><span class="sxs-lookup"><span data-stu-id="5472d-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![Домашняя страницы Secure Score](../../media/secure-score/secure-score-home-page.png)

## <a name="check-your-current-score"></a><span data-ttu-id="5472d-116">Проверка текущего балла</span><span class="sxs-lookup"><span data-stu-id="5472d-116">Check your current score</span></span>

<span data-ttu-id="5472d-117">Чтобы проверить текущую оценку, перейдите на страницу обзоров microsoft Secure Score и найдите плитку, на которую будет написано **Ваше безопасное количество баллов.**</span><span class="sxs-lookup"><span data-stu-id="5472d-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="5472d-118">Ваш счет будет показан в процентах, а также количество очков, которые вы получили из общего возможного количества баллов.</span><span class="sxs-lookup"><span data-stu-id="5472d-118">Your score will be shown as a percentage, along with the number of points you've achieved out of the total possible points.</span></span>

<span data-ttu-id="5472d-119">Кроме того, если вы выберите кнопку **Включить** рядом со своим счетом, вы можете выбрать различные представления вашего счета.</span><span class="sxs-lookup"><span data-stu-id="5472d-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="5472d-120">Эти различные представления показателей будут отображаться на графике на плитке показателей и диаграмме разбивки точки.</span><span class="sxs-lookup"><span data-stu-id="5472d-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="5472d-121">Ниже баллов можно добавить к представлению общую оценку, чтобы дать вам более полное представление об общем счете:</span><span class="sxs-lookup"><span data-stu-id="5472d-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="5472d-122">**Планируемый результат.** Показать прогнозируемый результат при планировании действий</span><span class="sxs-lookup"><span data-stu-id="5472d-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="5472d-123">**Текущая оценка лицензии.** Показать результат, который можно достичь с помощью текущей лицензии Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5472d-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="5472d-124">**Достижимая оценка:** показать результат, который можно достичь с помощью лицензий Майкрософт и текущей оценки риска</span><span class="sxs-lookup"><span data-stu-id="5472d-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="5472d-125">Это представление будет выглядеть так, если вы включили все возможные представления показателей:</span><span class="sxs-lookup"><span data-stu-id="5472d-125">This view is what it will look like if you've included all possible score views:</span></span>

![Ваша безопасная оценка, включая запланированные оценки, текущую оценку лицензии и достижимую оценку](../../media/secure-score/secure-score-achievable.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="5472d-127">Примите меры для улучшения показателей</span><span class="sxs-lookup"><span data-stu-id="5472d-127">Take action to improve your score</span></span>

<span data-ttu-id="5472d-128">На **вкладке Действия** по улучшению перечислены рекомендации по безопасности, которые адресовывались возможным поверхностям атаки.</span><span class="sxs-lookup"><span data-stu-id="5472d-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="5472d-129">Он также включает их состояние (для решения, запланированного, риска, принятого, разрешенного с помощью третьей стороны, разрешенного путем альтернативного смягчения и завершения).</span><span class="sxs-lookup"><span data-stu-id="5472d-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="5472d-130">Вы можете искать, фильтровать и групповать все действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="5472d-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="5472d-131">Ранжирование</span><span class="sxs-lookup"><span data-stu-id="5472d-131">Ranking</span></span>

<span data-ttu-id="5472d-132">Ранжирование основано на количестве баллов, которые необходимо достичь, сложности реализации, влиянии пользователя и сложности.</span><span class="sxs-lookup"><span data-stu-id="5472d-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="5472d-133">Действия по улучшению с наивысшим ранжом имеют большое количество точек, остающихся с низкой сложностью, влиянием пользователя и сложностью.</span><span class="sxs-lookup"><span data-stu-id="5472d-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="5472d-134">Просмотр сведений о действиях по улучшению</span><span class="sxs-lookup"><span data-stu-id="5472d-134">View improvement action details</span></span>

<span data-ttu-id="5472d-135">При выборе определенного действия по улучшению появляется полная вылетная страница.</span><span class="sxs-lookup"><span data-stu-id="5472d-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

![Пример вылетов действий по улучшению](../../media/secure-score/secure-score-improvement-action-details.png)

<span data-ttu-id="5472d-137">Чтобы завершить действие, у вас есть несколько вариантов:</span><span class="sxs-lookup"><span data-stu-id="5472d-137">To complete the action, you have a few options:</span></span>

- <span data-ttu-id="5472d-138">Выберите **Управление,** чтобы перейти на экран конфигурации и внести изменения.</span><span class="sxs-lookup"><span data-stu-id="5472d-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="5472d-139">Затем вы получите очки, которые стоит действие, видимые в вылете. Обновление баллов обычно займет около 24 часов.</span><span class="sxs-lookup"><span data-stu-id="5472d-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

- <span data-ttu-id="5472d-140">Выберите **Share,** чтобы скопировать прямую ссылку на действие по улучшению.</span><span class="sxs-lookup"><span data-stu-id="5472d-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="5472d-141">Вы также можете выбрать платформу для обмена ссылками, такими как электронная почта, Microsoft Teams или Microsoft Planner.</span><span class="sxs-lookup"><span data-stu-id="5472d-141">You can also choose the platform to share the link, such as email, Microsoft Teams, or Microsoft Planner.</span></span>

<span data-ttu-id="5472d-142">Добавление  примечаний, чтобы отслеживать ход выполнения или что-либо еще, что вы хотите прокомментировать.</span><span class="sxs-lookup"><span data-stu-id="5472d-142">Add **Notes** to keep track of progress or anything else you want to comment on.</span></span> <span data-ttu-id="5472d-143">Если вы добавите собственные **теги** к действию по улучшению, вы можете фильтровать эти теги.</span><span class="sxs-lookup"><span data-stu-id="5472d-143">If you add your own **tags** to the improvement action, you can filter by those tags.</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="5472d-144">Выберите состояние действия по улучшению</span><span class="sxs-lookup"><span data-stu-id="5472d-144">Choose an improvement action status</span></span>

<span data-ttu-id="5472d-145">Выберите все состояния и записи, определенные действию по улучшению.</span><span class="sxs-lookup"><span data-stu-id="5472d-145">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="5472d-146">**Для решения** — вы признаете, что необходимо действие по улучшению, и планируете его решить на определенном этапе в будущем.</span><span class="sxs-lookup"><span data-stu-id="5472d-146">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="5472d-147">Это состояние также применяется к действиям, которые обнаруживаются частично, но не полностью завершены.</span><span class="sxs-lookup"><span data-stu-id="5472d-147">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="5472d-148">**Запланированные** . Существуют конкретные планы по завершению действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="5472d-148">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="5472d-149">**Риск принят** . Безопасность всегда должна быть сбалансирована с юзабью, и не каждая рекомендация будет работать для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="5472d-149">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="5472d-150">В этом случае вы можете принять риск или оставшийся риск, а не принимать меры по улучшению.</span><span class="sxs-lookup"><span data-stu-id="5472d-150">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="5472d-151">Вам не будут даны очки, но действие больше не будет видно в списке действий по улучшению.</span><span class="sxs-lookup"><span data-stu-id="5472d-151">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="5472d-152">Это действие можно просмотреть в истории или отменить в любое время.</span><span class="sxs-lookup"><span data-stu-id="5472d-152">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="5472d-153">**Разрешено** с помощью третьей стороны и разрешено путем альтернативного смягчения **последствий** . Действие по улучшению уже было устранено сторонним приложением или программным обеспечением или внутренним средством.</span><span class="sxs-lookup"><span data-stu-id="5472d-153">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="5472d-154">Вы получите очки, которые стоит действие, так что ваш балл лучше отражает общую осанку безопасности.</span><span class="sxs-lookup"><span data-stu-id="5472d-154">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="5472d-155">Если сторонний или внутренний инструмент больше не покрывает управление, можно выбрать другой статус.</span><span class="sxs-lookup"><span data-stu-id="5472d-155">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="5472d-156">Имейте в виду, что Корпорация Майкрософт не будет иметь видимости в полноте реализации, если действие по улучшению помечено как любой из этих статусов.</span><span class="sxs-lookup"><span data-stu-id="5472d-156">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="5472d-157">Действия по & управление уязвимостями угроз</span><span class="sxs-lookup"><span data-stu-id="5472d-157">Threat & vulnerability management improvement actions</span></span>

<span data-ttu-id="5472d-158">Для действий по улучшению в категории "Устройство" нельзя выбрать статусы.</span><span class="sxs-lookup"><span data-stu-id="5472d-158">For improvement actions in the "Device" category, you can't choose statuses.</span></span> <span data-ttu-id="5472d-159">Вместо этого вам будет направлена [](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) рекомендация по контроль угроз и уязвимостей безопасности в Центр безопасности в Microsoft Defender [для](/windows/security/threat-protection/microsoft-defender-atp/use) принятия действий.</span><span class="sxs-lookup"><span data-stu-id="5472d-159">Instead, you'll be directed to the associated [threat and vulnerability management security recommendation](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="5472d-160">Исключение, которое вы выбираете, и обоснование, которое вы пишете, будет иметь определенный характер для этого портала.</span><span class="sxs-lookup"><span data-stu-id="5472d-160">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="5472d-161">Он не будет присутствовать на портале Microsoft Secure Score.</span><span class="sxs-lookup"><span data-stu-id="5472d-161">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="5472d-162">Завершенные действия по улучшению</span><span class="sxs-lookup"><span data-stu-id="5472d-162">Completed improvement actions</span></span>

<span data-ttu-id="5472d-163">Действия по улучшению имеют состояние "завершено" после достижения всех возможных точек для действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="5472d-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="5472d-164">Завершенные действия по улучшению подтверждены, несмотря на данные Майкрософт, и вы не можете изменить состояние.</span><span class="sxs-lookup"><span data-stu-id="5472d-164">Completed improvement actions are confirmed though Microsoft data, and you can't change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="5472d-165">Оценка сведений и оценка влияния пользователей</span><span class="sxs-lookup"><span data-stu-id="5472d-165">Assess information and review user impact</span></span>

<span data-ttu-id="5472d-166">Раздел под **названием "С** первого взгляда" расскажет вам о категории, атаках, которые она может защитить, и о продукте.</span><span class="sxs-lookup"><span data-stu-id="5472d-166">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="5472d-167">**Влияние пользователя** — это то, что пользователи будут испытывать, если будет принято действие по улучшению, а затронутые пользователи — это люди, которые будут затронуты. </span><span class="sxs-lookup"><span data-stu-id="5472d-167">**User impact** is what the users will experience if the improvement action is enacted, and the **Users affected** are the people who will be impacted.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="5472d-168">Реализация действия по улучшению</span><span class="sxs-lookup"><span data-stu-id="5472d-168">Implement the improvement action</span></span>

<span data-ttu-id="5472d-169">В **разделе Реализация** показаны все необходимые условия, пошаговая реализация действий по улучшению, текущее состояние реализации действия по улучшению и дополнительные ссылки.</span><span class="sxs-lookup"><span data-stu-id="5472d-169">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="5472d-170">К обязательным условиям относятся все необходимые лицензии или действия, которые необходимо завершить до решения проблемы с улучшением.</span><span class="sxs-lookup"><span data-stu-id="5472d-170">Prerequisites include any licenses that are needed or actions to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="5472d-171">Убедитесь, что в лицензии достаточно мест для выполнения действия по улучшению и чтобы эти лицензии применялись к необходимым пользователям.</span><span class="sxs-lookup"><span data-stu-id="5472d-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="5472d-172">Мы ждем ваших отзывов!</span><span class="sxs-lookup"><span data-stu-id="5472d-172">We want to hear from you</span></span>

<span data-ttu-id="5472d-173">Если у вас есть какие-либо проблемы, дайте нам знать, разместив в сообществе [безопасность, конфиденциальность & соответствия](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) требованиям.</span><span class="sxs-lookup"><span data-stu-id="5472d-173">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="5472d-174">Мы отслеживаем сообщество и предоставляем помощь.</span><span class="sxs-lookup"><span data-stu-id="5472d-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="5472d-175">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="5472d-175">Related resources</span></span>

- [<span data-ttu-id="5472d-176">Обзор результатов microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="5472d-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="5472d-177">Отслеживание истории microsoft Secure Score и достижения целей</span><span class="sxs-lookup"><span data-stu-id="5472d-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="5472d-178">Что вскоре появится</span><span class="sxs-lookup"><span data-stu-id="5472d-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="5472d-179">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="5472d-179">What's new</span></span>](microsoft-secure-score-whats-new.md)
