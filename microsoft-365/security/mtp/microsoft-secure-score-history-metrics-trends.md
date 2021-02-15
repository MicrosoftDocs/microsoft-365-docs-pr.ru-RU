---
title: Отслеживание истории оценки безопасности (Майкрософт) и обеспечение достижения целей
description: Получите представление о действиях, которые повлияли на оценку безопасности (Майкрософт). Обнаружение тенденций и настройка целей.
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
ms.openlocfilehash: c9af6a3ae6f461acfd2968897223446641d5cf09
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925676"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a><span data-ttu-id="503b7-105">Отслеживание истории оценки безопасности (Майкрософт) и обеспечение достижения целей</span><span class="sxs-lookup"><span data-stu-id="503b7-105">Track your Microsoft Secure Score history and meet goals</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="503b7-106">[Оценка безопасности (Майкрософт)](microsoft-secure-score.md) — это показатель уровня безопасности организации, где большее число указывает на дополнительные действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="503b7-106">[Microsoft Secure Score](microsoft-secure-score.md) is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="503b7-107">Его можно найти в Центре безопасности https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="503b7-107">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a><span data-ttu-id="503b7-108">Получение информации о действиях, которые повлияли на оценку</span><span class="sxs-lookup"><span data-stu-id="503b7-108">Gain insights into activity that has affected your score</span></span>

<span data-ttu-id="503b7-109">Просматривайте график показателей организации со временем на вкладке **"История".**</span><span class="sxs-lookup"><span data-stu-id="503b7-109">View a graph of your organization's score over time in the **History** tab.</span></span>

<span data-ttu-id="503b7-110">Под графиком находится список всех действий в выбранном диапазоне времени и их атрибутов, таких как итоговые точки и категории.</span><span class="sxs-lookup"><span data-stu-id="503b7-110">Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="503b7-111">Вы можете настроить диапазон дат и фильтровать их по категориям.</span><span class="sxs-lookup"><span data-stu-id="503b7-111">You can customize a date range and filter by category.</span></span>

![История действий](../../media/secure-score/secure-score-history-activity.png)

<span data-ttu-id="503b7-113">Если выбрать действие по улучшению, связанное с действием, появится полный flyout действия улучшения.</span><span class="sxs-lookup"><span data-stu-id="503b7-113">If you select the improvement action associated with an activity, the full improvement action flyout will appear.</span></span>

<span data-ttu-id="503b7-114">Чтобы просмотреть всю историю определенного действия по улучшению, выберите ссылку на историю во flyout.</span><span class="sxs-lookup"><span data-stu-id="503b7-114">To view all history for that specific improvement action, select the history link in the flyout.</span></span>

![История действий по улучшению](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a><span data-ttu-id="503b7-116">Обнаружение тенденций и настройка целей</span><span class="sxs-lookup"><span data-stu-id="503b7-116">Discover trends and set goals</span></span>

<span data-ttu-id="503b7-117">На **вкладке "Метрики & тенденций"** имеется несколько графиков и диаграмм, которые дают больше информации о тенденциях и устанавливают цели.</span><span class="sxs-lookup"><span data-stu-id="503b7-117">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="503b7-118">Вы можете установить диапазон дат для всей страницы визуализаций.</span><span class="sxs-lookup"><span data-stu-id="503b7-118">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="503b7-119">Визуализации включают:</span><span class="sxs-lookup"><span data-stu-id="503b7-119">The visualizations include:</span></span>

* <span data-ttu-id="503b7-120">**Зона "Оценка безопасности"** — настраивается на основе целей организации и определений диапазонов показателей "хороший", "ОК" и "Плохой".</span><span class="sxs-lookup"><span data-stu-id="503b7-120">**Your Secure Score zone** - Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="503b7-121">**Тенденция регрессии** — временная шкала точек, которые были регрессивными из-за изменений конфигурации, пользователя или устройства.</span><span class="sxs-lookup"><span data-stu-id="503b7-121">**Regression trend** - A timeline of points that have regressed because of configuration, user, or device changes.</span></span>  
* <span data-ttu-id="503b7-122">**Тенденция сравнения** : сравнение оценки безопасности в организации с предыдущими.</span><span class="sxs-lookup"><span data-stu-id="503b7-122">**Comparison trend** - How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="503b7-123">Это представление может включать строки, представляющие среднюю оценку организаций с одинаковым количеством мест и настраиваемого представления сравнения, которое можно настроить.</span><span class="sxs-lookup"><span data-stu-id="503b7-123">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="503b7-124">**Тенденция принятия рисков** — временная шкала действий по улучшению, помеченная как "принятый риск".</span><span class="sxs-lookup"><span data-stu-id="503b7-124">**Risk acceptance trend** - Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="503b7-125">**Изменение оценки** — количество достигнутого числа баллов, регрессии баллов и изменение вашего счета в указанном диапазоне дат.</span><span class="sxs-lookup"><span data-stu-id="503b7-125">**Score changes** - The number of points achieved, points regressed, and changes to your score in the specified date range.</span></span>

### <a name="compare-your-score-to-organizations-like-yours"></a><span data-ttu-id="503b7-126">Сравнение показателей с организациями, например вашей</span><span class="sxs-lookup"><span data-stu-id="503b7-126">Compare your score to organizations like yours</span></span>

<span data-ttu-id="503b7-127">Существует два места для сравнения показателей с похожими на вас организациями.</span><span class="sxs-lookup"><span data-stu-id="503b7-127">There are two places to see how your score compares to organizations that are similar to you.</span></span> <span data-ttu-id="503b7-128">На обеих диаграммах можно выбрать "Управление **сравнениями",** чтобы просмотреть и изменить сведения организации.</span><span class="sxs-lookup"><span data-stu-id="503b7-128">In both charts, you can select **Manage comparisons** to view and edit your organization's information.</span></span> <span data-ttu-id="503b7-129">Вы также можете создать собственное сравнение на основе отрасли, размера организации, лицензий и регионов.</span><span class="sxs-lookup"><span data-stu-id="503b7-129">You can also create a custom comparison based on industry, organization size, licenses, and regions.</span></span>

#### <a name="comparison-bar-chart"></a><span data-ttu-id="503b7-130">Диаграмма сравнения</span><span class="sxs-lookup"><span data-stu-id="503b7-130">Comparison bar chart</span></span>

<span data-ttu-id="503b7-131">Диаграмма сравнения — это вкладка **"Обзор".** Наведите курсор на диаграмму, чтобы просмотреть оценку и возможность оценки.</span><span class="sxs-lookup"><span data-stu-id="503b7-131">The comparison bar chart is the **Overview** tab. Hover over the chart to view the score and score opportunity.</span></span> <span data-ttu-id="503b7-132">Данные сравнения анонимизируются, поэтому мы не знаем точно, какие другие клиенты находятся в наборе.</span><span class="sxs-lookup"><span data-stu-id="503b7-132">The comparison data is anonymized so we don’t know exactly which others tenants are in the mix.</span></span>

![Диаграмма результатов аналогичной организации](../../media/secure-score/secure-score-comparison-bar.png)

- <span data-ttu-id="503b7-134">**Такие организации, как** ваша: средняя оценка других клиентов (при условии, что у нас есть не менее пяти или более клиентов для сравнения), которые соответствуют следующим критериям:</span><span class="sxs-lookup"><span data-stu-id="503b7-134">**Organizations like yours**: an average score of other tenants (provided we have at least five or more tenants to compare) that qualify with the following criteria:</span></span>
    1. <span data-ttu-id="503b7-135">Та же отрасль</span><span class="sxs-lookup"><span data-stu-id="503b7-135">Same industry</span></span>
    2. <span data-ttu-id="503b7-136">Одинаковый размер организации</span><span class="sxs-lookup"><span data-stu-id="503b7-136">Same organization size</span></span>
    3. <span data-ttu-id="503b7-137">Все регионы</span><span class="sxs-lookup"><span data-stu-id="503b7-137">All regions</span></span>
    4. <span data-ttu-id="503b7-138">Используемые продукты Майкрософт на 80 % похожи</span><span class="sxs-lookup"><span data-stu-id="503b7-138">Microsoft products used are 80% similar</span></span>
    5. <span data-ttu-id="503b7-139">Возможность (максимальная оценка, которую может получить текущая лицензия) в диапазоне 20 % от клиента</span><span class="sxs-lookup"><span data-stu-id="503b7-139">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

- <span data-ttu-id="503b7-140">**Настраиваемые сравнения**: необходимо настроить, выбрав **управление** сравнением на основе следующих критериев:</span><span class="sxs-lookup"><span data-stu-id="503b7-140">**Custom Comparison**: needs to be set up by selecting **Manage Comparison** based on the following criteria:</span></span>
    1. <span data-ttu-id="503b7-141">Выбранные отрасли</span><span class="sxs-lookup"><span data-stu-id="503b7-141">Selected industry(s)</span></span>
    2. <span data-ttu-id="503b7-142">Выбранные размеры организации</span><span class="sxs-lookup"><span data-stu-id="503b7-142">Selected organization size(s)</span></span>
    3. <span data-ttu-id="503b7-143">Выбранные регионы</span><span class="sxs-lookup"><span data-stu-id="503b7-143">Selected region(s)</span></span>
    4. <span data-ttu-id="503b7-144">Выбранные лицензии</span><span class="sxs-lookup"><span data-stu-id="503b7-144">Selected license(s)</span></span>
    5. <span data-ttu-id="503b7-145">Используемые продукты Майкрософт на 80 % похожи</span><span class="sxs-lookup"><span data-stu-id="503b7-145">Microsoft products used are 80% similar</span></span>
    6. <span data-ttu-id="503b7-146">Возможность (максимальный показатель, который может быть достигнут текущей лицензией) в диапазоне 20 % от клиента</span><span class="sxs-lookup"><span data-stu-id="503b7-146">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

<span data-ttu-id="503b7-147">Если вы сделали настраиваемый выбор, но результаты имеют менее пяти других клиентов, с чем можно сравнить, вы увидите "Недоступны из-за ограниченных данных".</span><span class="sxs-lookup"><span data-stu-id="503b7-147">If you've made a custom selection but the results have less than five other tenants that we can compare against, you'll see “Not available due to limited data”.</span></span>

#### <a name="comparison-trend"></a><span data-ttu-id="503b7-148">Тенденция сравнения</span><span class="sxs-lookup"><span data-stu-id="503b7-148">Comparison trend</span></span>

<span data-ttu-id="503b7-149">На **вкладке "Метрики & тенденций"** поимите, как оценка безопасности организации со временем будет сравниваться с другими.</span><span class="sxs-lookup"><span data-stu-id="503b7-149">In the **Metrics & trends** tab, view how your organization's Secure Score compares to others' over time.</span></span>

![График результатов аналогичной организации со временем](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="503b7-151">Мы ждем ваших отзывов!</span><span class="sxs-lookup"><span data-stu-id="503b7-151">We want to hear from you</span></span>

<span data-ttu-id="503b7-152">Если у вас есть какие-либо проблемы, дайте нам знать, опубликовав в сообществе по [безопасности, & соответствия требованиям.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="503b7-152">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="503b7-153">Мы отслеживаем сообщество и предоставляем помощь.</span><span class="sxs-lookup"><span data-stu-id="503b7-153">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="503b7-154">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="503b7-154">Related resources</span></span>

- [<span data-ttu-id="503b7-155">Обзор оценки безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="503b7-155">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="503b7-156">Оценка уровня безопасности</span><span class="sxs-lookup"><span data-stu-id="503b7-156">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="503b7-157">Что вскоре появится</span><span class="sxs-lookup"><span data-stu-id="503b7-157">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="503b7-158">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="503b7-158">What's new</span></span>](microsoft-secure-score-whats-new.md)
