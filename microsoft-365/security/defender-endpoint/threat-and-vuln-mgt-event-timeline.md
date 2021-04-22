---
title: Хронология событий в управлении угрозами и уязвимостью
description: Временная шкала событий — это лента новостей о рисках, которая позволяет интерпретировать, как вводится риск в организацию и какие меры по ее снижению были смягчаемы.
keywords: Хронология событий, сроки событий Microsoft Defender для конечных точек, шкала событий Microsoft Defender для конечных точек твм, управление угрозами и уязвимостью, Microsoft Defender для Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933485"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="d9ffa-104">Временная шкала событий — управление угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="d9ffa-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9ffa-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d9ffa-105">**Applies to:**</span></span>
- [<span data-ttu-id="d9ffa-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d9ffa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d9ffa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9ffa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d9ffa-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d9ffa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d9ffa-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="d9ffa-110">Временная шкала событий — это лента новостей о рисках, которая помогает интерпретировать, как риск вводится в организацию с помощью новых уязвимостей или эксплойтов.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="d9ffa-111">Можно просмотреть события, которые могут повлиять на риск организации.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="d9ffa-112">Например, вы можете найти новые уязвимости, которые были введены, уязвимости, которые стали эксплуатироваться, использовать, которые были добавлены в набор эксплойтов и другие.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="d9ffa-113">В хронике событий также [](tvm-exposure-score.md) рассказывается история оценки экспозиции и [microsoft Secure Score для](tvm-microsoft-secure-score-devices.md) устройств, чтобы можно было определить причину больших изменений.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="d9ffa-114">События могут повлиять на ваши устройства или оценку для устройств.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="d9ffa-115">Уменьшите воздействие, реась на то, что необходимо устранять, основываясь на приоритетных [рекомендациях по безопасности.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="d9ffa-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="d9ffa-116">Чтобы получить сообщения о новых событиях уязвимости, см. в руб. Настройка уведомлений об уязвимости в [Microsoft Defender для endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="d9ffa-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="d9ffa-117">Перейдите на страницу временной шкалы событий</span><span class="sxs-lookup"><span data-stu-id="d9ffa-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="d9ffa-118">Существует также три точки входа из панели управления угрозами и [уязвимостью:](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="d9ffa-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="d9ffa-119">**Карта оценки экспозиции** организации. Наведите курсор над точками событий в графе "Оценка экспозиции со временем" и выберите "См. все события этого дня".</span><span class="sxs-lookup"><span data-stu-id="d9ffa-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="d9ffa-120">События представляют уязвимости программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="d9ffa-121">**Microsoft Secure Score for Devices:** Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day".</span><span class="sxs-lookup"><span data-stu-id="d9ffa-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="d9ffa-122">События представляют собой новые оценки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="d9ffa-123">**Верхняя карта** событий: Выберите "Показать больше" в нижней части таблицы событий верхней части.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="d9ffa-124">Карта отображает три наиболее важных события за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="d9ffa-125">Важные события могут включать, если событие затрагивает большое количество устройств или является критической уязвимостью.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="d9ffa-126">Оценка экспозиции и microsoft Secure Score для устройств</span><span class="sxs-lookup"><span data-stu-id="d9ffa-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="d9ffa-127">На панели мониторинга управления угрозами и уязвимостями наведите курсор над графиком показателей экспозиции, чтобы просмотреть события уязвимости программного обеспечения с того дня, которые повлияли на ваши устройства.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="d9ffa-128">Наведите курсор над графом Microsoft Secure Score для устройств, чтобы просмотреть новые оценки конфигурации безопасности, влияющие на ваш результат.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="d9ffa-129">Если нет событий, влияющих на устройства или оценку для устройств, то ни одно из них не будет показано.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="d9ffa-130">![Оценка экспозиции ](images/tvm-event-timeline-exposure-score350.png) 
 ![ колеблется Microsoft Secure Score для устройств наведении](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="d9ffa-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="d9ffa-131">Сверлить до событий с этого дня</span><span class="sxs-lookup"><span data-stu-id="d9ffa-131">Drill down to events from that day</span></span>

<span data-ttu-id="d9ffa-132">Выбор show **all events from this day** takes you to the Event timeline page with a custom date range for that day.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![Временная шкала событий, выбранный настраиваемый диапазон дат](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="d9ffa-134">Выберите **настраиваемый** диапазон, чтобы изменить диапазон дат на другой настраиваемый или заранее установленный диапазон времени.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![Параметры диапазона даты даты событий](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="d9ffa-136">Обзор временной шкалы событий</span><span class="sxs-lookup"><span data-stu-id="d9ffa-136">Event timeline overview</span></span>

<span data-ttu-id="d9ffa-137">На странице Временной шкалы событий можно просмотреть всю необходимую информацию, связанную с событием.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="d9ffa-138">Функции:</span><span class="sxs-lookup"><span data-stu-id="d9ffa-138">Features:</span></span>

- <span data-ttu-id="d9ffa-139">Настройка столбцов</span><span class="sxs-lookup"><span data-stu-id="d9ffa-139">Customize columns</span></span>
- <span data-ttu-id="d9ffa-140">Фильтр по типу событий или процентам устройств с влиянием</span><span class="sxs-lookup"><span data-stu-id="d9ffa-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="d9ffa-141">Просмотр 30, 50 или 100 элементов на страницу</span><span class="sxs-lookup"><span data-stu-id="d9ffa-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="d9ffa-142">Два больших числа в верхней части страницы показывают количество новых уязвимостей и уязвимостей, которые можно использовать, а не событий.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="d9ffa-143">Некоторые события могут иметь несколько уязвимостей, а некоторые уязвимости могут иметь несколько событий.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![Страница временной шкалы событий](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="d9ffa-145">Столбцы</span><span class="sxs-lookup"><span data-stu-id="d9ffa-145">Columns</span></span>

- <span data-ttu-id="d9ffa-146">**Дата:** месяц, день, год</span><span class="sxs-lookup"><span data-stu-id="d9ffa-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="d9ffa-147">**Event:** impactful event, including component, type and number of impacted devices</span><span class="sxs-lookup"><span data-stu-id="d9ffa-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="d9ffa-148">**Связанный компонент:** программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="d9ffa-148">**Related component**: software</span></span>
- <span data-ttu-id="d9ffa-149">**Первоначально повлияли устройства:** количество и процент, на которые повлияли устройства, когда это событие первоначально произошло.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="d9ffa-150">Кроме того, можно фильтровать на проценте от общего числа устройств, на которые первоначально повлияли устройства.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="d9ffa-151">**В настоящее время влияет на устройства:** текущее число и процент устройств, которые это событие в настоящее время влияет.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="d9ffa-152">Это поле можно найти, выбрав **столбцы Customize.**</span><span class="sxs-lookup"><span data-stu-id="d9ffa-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="d9ffa-153">**Типы:** отражают события, отпечатав время, которые влияют на результат.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="d9ffa-154">Их можно отфильтровать.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-154">They can be filtered.</span></span>
    - <span data-ttu-id="d9ffa-155">Эксплойт, добавленный в набор эксплойтов</span><span class="sxs-lookup"><span data-stu-id="d9ffa-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="d9ffa-156">Проверка эксплойтов</span><span class="sxs-lookup"><span data-stu-id="d9ffa-156">Exploit was verified</span></span>
    - <span data-ttu-id="d9ffa-157">Новый общедоступный эксплойт</span><span class="sxs-lookup"><span data-stu-id="d9ffa-157">New public exploit</span></span>
    - <span data-ttu-id="d9ffa-158">Новая уязвимость</span><span class="sxs-lookup"><span data-stu-id="d9ffa-158">New vulnerability</span></span>
    - <span data-ttu-id="d9ffa-159">Новая оценка конфигурации</span><span class="sxs-lookup"><span data-stu-id="d9ffa-159">New configuration assessment</span></span>
- <span data-ttu-id="d9ffa-160">**Тенденция показателей:** тенденция оценки экспозиции</span><span class="sxs-lookup"><span data-stu-id="d9ffa-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="d9ffa-161">Значки</span><span class="sxs-lookup"><span data-stu-id="d9ffa-161">Icons</span></span>

<span data-ttu-id="d9ffa-162">Рядом с событиями отображаются следующие значки:</span><span class="sxs-lookup"><span data-stu-id="d9ffa-162">The following icons show up next to events:</span></span>

- ![значок ошибки](images/tvm-black-bug-icon.png) <span data-ttu-id="d9ffa-164">Новый общедоступный эксплойт</span><span class="sxs-lookup"><span data-stu-id="d9ffa-164">New public exploit</span></span>
- ![значок предупреждения об отчете](images/report-warning-icon.png) <span data-ttu-id="d9ffa-166">Опубликована новая уязвимость</span><span class="sxs-lookup"><span data-stu-id="d9ffa-166">New vulnerability was published</span></span>
- ![набор эксплойтов](images/bug-lightning-icon2.png) <span data-ttu-id="d9ffa-168">Эксплойт, найденный в наборе эксплойтов</span><span class="sxs-lookup"><span data-stu-id="d9ffa-168">Exploit found in exploit kit</span></span>
- ![Значок ошибки с значоком предупреждения](images/bug-caution-icon2.png) <span data-ttu-id="d9ffa-170">Проверка эксплойтов</span><span class="sxs-lookup"><span data-stu-id="d9ffa-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="d9ffa-171">Сверлить до определенного события</span><span class="sxs-lookup"><span data-stu-id="d9ffa-171">Drill down to a specific event</span></span>

<span data-ttu-id="d9ffa-172">После выбора события вылет появится со списком сведений и текущих резюме, влияющих на устройства.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="d9ffa-173">Вы можете показать больше резюме или просмотреть связанную рекомендацию.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="d9ffa-174">Стрелка ниже "тенденция оценки" помогает определить, было ли это событие потенциально поднято или понижено для оценки воздействия организации.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="d9ffa-175">Более высокая оценка экспозиции означает, что устройства более уязвимы для эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![Вылет временной шкалы событий](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="d9ffa-177">Оттуда выберите **Перейти к** связанной рекомендации по безопасности, чтобы просмотреть рекомендации, которые касаются новой уязвимости программного обеспечения на странице [рекомендации безопасности](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="d9ffa-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="d9ffa-178">После прочтения сведений о описании и уязвимости в рекомендации по безопасности можно отправить запрос на исправление и отслеживать запрос на странице [исправление.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="d9ffa-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="d9ffa-179">Просмотр временной шкалы событий на страницах программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="d9ffa-179">View Event timelines in software pages</span></span>

<span data-ttu-id="d9ffa-180">Чтобы открыть страницу программного обеспечения, выберите событие > имя гиперссылки программного обеспечения (например, Visual Studio 2017 г.) в разделе "Связанный компонент" в вылете.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="d9ffa-181">Дополнительные новости о страницах программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="d9ffa-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="d9ffa-182">Полная страница будет отображаться со всеми деталями определенного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="d9ffa-183">Мышь над графиком, чтобы увидеть хронологию событий для этого конкретного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![Страница программного обеспечения с графиком событий](images/tvm-event-timeline-software2.png)

<span data-ttu-id="d9ffa-185">Перейдите на вкладку временной шкалы событий, чтобы просмотреть все события, связанные с этим программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="d9ffa-186">Также можно увидеть рекомендации по безопасности, обнаруженные уязвимости, установленные устройства и распространение версий.</span><span class="sxs-lookup"><span data-stu-id="d9ffa-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![Страница программного обеспечения со вкладками Временной шкалы событий](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="d9ffa-188">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="d9ffa-188">Related topics</span></span>

- [<span data-ttu-id="d9ffa-189">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="d9ffa-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d9ffa-190">Панель мониторинга</span><span class="sxs-lookup"><span data-stu-id="d9ffa-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="d9ffa-191">Показатель уязвимости</span><span class="sxs-lookup"><span data-stu-id="d9ffa-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="d9ffa-192">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="d9ffa-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="d9ffa-193">Устранение уязвимостей</span><span class="sxs-lookup"><span data-stu-id="d9ffa-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="d9ffa-194">Инвентаризация программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="d9ffa-194">Software inventory</span></span>](tvm-software-inventory.md)

