---
title: Исследование оповещений в Microsoft 365 Defender
description: Изучите оповещения, которые можно увидеть на устройствах, пользователях и почтовых ящиках.
keywords: инциденты, оповещения, исследование, анализ, ответ, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверения, почтовый ящик, электронная почта, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b9bbe058042a49586e8515fde85371b1487e8d25
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297132"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="e1df0-104">Исследование оповещений в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1df0-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e1df0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e1df0-105">**Applies to:**</span></span>
- <span data-ttu-id="e1df0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1df0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e1df0-107">Оповещения являются основой всех инцидентов и указывают на возникновение вредоносных или подозрительных событий в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="e1df0-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="e1df0-108">Оповещения обычно являются частью более широкой атаки и предоставляют подсказки об инциденте.</span><span class="sxs-lookup"><span data-stu-id="e1df0-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="e1df0-109">В Microsoft 365 Defender связанные оповещения объединяются для формирования [инцидентов.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1df0-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="e1df0-110">Инциденты всегда обеспечивают более широкий контекст атаки, однако анализ оповещений может быть полезным при необходимости более глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="e1df0-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="e1df0-111">Очередь **оповещений** показывает текущий набор оповещений.</span><span class="sxs-lookup"><span data-stu-id="e1df0-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="e1df0-112">Вы получаете очередь оповещений из & оповещения > оповещения о быстром запуске центра безопасности Microsoft 365[(security.microsoft.com).](https://security.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="e1df0-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Пример очереди оповещений":::

<span data-ttu-id="e1df0-114">Здесь отображаются оповещения из различных решений безопасности Майкрософт, таких как Microsoft Defender для конечной точки, Microsoft Defender для Office 365 и Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e1df0-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="e1df0-115">По умолчанию очередь оповещений в центре Microsoft 365 безопасности отображает новые и ходовые оповещения за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="e1df0-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="e1df0-116">Последнее оповещение находится в верхней части списка, чтобы вы могли увидеть его в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="e1df0-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="e1df0-117">Из очереди оповещений по умолчанию можно выбрать фильтры, чтобы увидеть области **Фильтры,** из которой можно указать подмножество оповещений. </span><span class="sxs-lookup"><span data-stu-id="e1df0-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="e1df0-118">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e1df0-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Пример области фильтров для очереди оповещений":::

<span data-ttu-id="e1df0-120">Вы можете фильтровать оповещения в соответствии с этими критериями:</span><span class="sxs-lookup"><span data-stu-id="e1df0-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="e1df0-121">Серьезность</span><span class="sxs-lookup"><span data-stu-id="e1df0-121">Severity</span></span>
- <span data-ttu-id="e1df0-122">Состояние</span><span class="sxs-lookup"><span data-stu-id="e1df0-122">Status</span></span>
- <span data-ttu-id="e1df0-123">Категория</span><span class="sxs-lookup"><span data-stu-id="e1df0-123">Category</span></span>
- <span data-ttu-id="e1df0-124">Источник обнаружения</span><span class="sxs-lookup"><span data-stu-id="e1df0-124">Detection source</span></span>
- <span data-ttu-id="e1df0-125">Теги</span><span class="sxs-lookup"><span data-stu-id="e1df0-125">Tags</span></span>
- <span data-ttu-id="e1df0-126">Политика</span><span class="sxs-lookup"><span data-stu-id="e1df0-126">Policy</span></span>
- <span data-ttu-id="e1df0-127">Влияние активов</span><span class="sxs-lookup"><span data-stu-id="e1df0-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="e1df0-128">Анализ оповещений</span><span class="sxs-lookup"><span data-stu-id="e1df0-128">Analyze an alert</span></span>

<span data-ttu-id="e1df0-129">Чтобы увидеть главную страницу оповещения, выберите имя оповещений.</span><span class="sxs-lookup"><span data-stu-id="e1df0-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="e1df0-130">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e1df0-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Пример страницы сведений оповещений в центре Microsoft 365 безопасности":::

<span data-ttu-id="e1df0-132">Вы также можете выбрать действие **"Откройте главную страницу** оповещения" из области **Управление оповещениями.**</span><span class="sxs-lookup"><span data-stu-id="e1df0-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="e1df0-133">Страница оповещения состоит из этих разделов:</span><span class="sxs-lookup"><span data-stu-id="e1df0-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="e1df0-134">История оповещений</span><span class="sxs-lookup"><span data-stu-id="e1df0-134">Alert story</span></span>
- <span data-ttu-id="e1df0-135">Действия, принятые (в том числе с влиянием на активы)</span><span class="sxs-lookup"><span data-stu-id="e1df0-135">Actions taken (including impacted assets)</span></span>
- <span data-ttu-id="e1df0-136">Связанные события</span><span class="sxs-lookup"><span data-stu-id="e1df0-136">Related events</span></span>
- <span data-ttu-id="e1df0-137">Сводные сведения</span><span class="sxs-lookup"><span data-stu-id="e1df0-137">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Пример страницы сведений оповещений в центре Microsoft 365 безопасности":::

<span data-ttu-id="e1df0-139">На всей странице оповещений можно выбрать эллипсы **(... )** рядом с любым объектом, чтобы увидеть доступные действия, например открытие определенной страницы активов или принятие определенных действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="e1df0-139">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the specific asset page or taking specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="e1df0-140">Анализ затронутых активов</span><span class="sxs-lookup"><span data-stu-id="e1df0-140">Analyze affected assets</span></span>

<span data-ttu-id="e1df0-141">В **разделе Действия,** принятые, имеется список затронутых активов, таких как почтовые ящики, устройства и пользователи, затронутые этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="e1df0-141">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="e1df0-142">Вы также можете выбрать Просмотр в центре **действий,** чтобы просмотреть вкладку **История** центра действий в центре Microsoft 365 безопасности. </span><span class="sxs-lookup"><span data-stu-id="e1df0-142">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="e1df0-143">Отслеживание роли оповещения в истории оповещений</span><span class="sxs-lookup"><span data-stu-id="e1df0-143">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="e1df0-144">В истории оповещений отображаются все активы или сущности, связанные с оповещением в представлении дерева процесса.</span><span class="sxs-lookup"><span data-stu-id="e1df0-144">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="e1df0-145">Оповещение в заголовке находится в центре внимания при первой посадке на странице выбранного оповещения.</span><span class="sxs-lookup"><span data-stu-id="e1df0-145">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="e1df0-146">Активы в истории оповещений можно расширить и щелкнуть.</span><span class="sxs-lookup"><span data-stu-id="e1df0-146">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="e1df0-147">Они предоставляют дополнительные сведения и ускоряют ответ, позволяя вам действовать прямо в контексте страницы оповещений.</span><span class="sxs-lookup"><span data-stu-id="e1df0-147">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="e1df0-148">В разделе история оповещения может содержаться несколько оповещений, при этом дополнительные оповещения, связанные с одним деревом выполнения, отображаются до или после выбранного оповещения.</span><span class="sxs-lookup"><span data-stu-id="e1df0-148">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="e1df0-149">Просмотр дополнительных сведений об оповещении на странице подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e1df0-149">View more alert information on the details page</span></span>

<span data-ttu-id="e1df0-150">На странице подробные сведения показаны сведения об выбранном оповещении с подробными сведениями и действиями, связанными с ним.</span><span class="sxs-lookup"><span data-stu-id="e1df0-150">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="e1df0-151">Если выбрать какой-либо из затронутых активов или сущностях в истории оповещения, страница подробных сведений изменяется, чтобы предоставить контекстную информацию и действия для выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="e1df0-151">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="e1df0-152">После выбора объекта, интересуемого, страница сведений изменяется, чтобы отображать сведения о выбранном типе объекта, исторические сведения, когда она доступна, и варианты действий по этому объекту непосредственно на странице оповещение.</span><span class="sxs-lookup"><span data-stu-id="e1df0-152">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="e1df0-153">Управление оповещениями</span><span class="sxs-lookup"><span data-stu-id="e1df0-153">Manage alerts</span></span>

<span data-ttu-id="e1df0-154">Чтобы управлять оповещением, выберите оповещение в очереди оповещений в строке, чтобы увидеть области **управления оповещениями.**</span><span class="sxs-lookup"><span data-stu-id="e1df0-154">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="e1df0-155">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e1df0-155">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Пример сводной области оповещений":::

<span data-ttu-id="e1df0-157">В **области управления** оповещениями можно указать:</span><span class="sxs-lookup"><span data-stu-id="e1df0-157">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="e1df0-158">Состояние оповещений (New, Resolved, In progress).</span><span class="sxs-lookup"><span data-stu-id="e1df0-158">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="e1df0-159">Классификация оповещений (Not set, True alert, False Alert).</span><span class="sxs-lookup"><span data-stu-id="e1df0-159">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="e1df0-160">Для классификации как истинного оповещения тип угрозы для оповещений в **поле Определение.**</span><span class="sxs-lookup"><span data-stu-id="e1df0-160">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="e1df0-161">Комментарий к оповещению.</span><span class="sxs-lookup"><span data-stu-id="e1df0-161">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="e1df0-162">Один из способов управления оповещениями с помощью тегов.</span><span class="sxs-lookup"><span data-stu-id="e1df0-162">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="e1df0-163">Возможность тегов для Microsoft Defender для Office 365 постепенно выводится и в настоящее время находится в предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="e1df0-163">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="e1df0-164">В настоящее время измененные имена тегов применяются только к оповещениям, созданным *после* обновления.</span><span class="sxs-lookup"><span data-stu-id="e1df0-164">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="e1df0-165">Оповещения, созданные до изменения, не будут отражать обновленное имя тега.</span><span class="sxs-lookup"><span data-stu-id="e1df0-165">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="e1df0-166">На этой области вы также можете выполнить эти дополнительные действия:</span><span class="sxs-lookup"><span data-stu-id="e1df0-166">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="e1df0-167">Откройте главную страницу оповещений</span><span class="sxs-lookup"><span data-stu-id="e1df0-167">Open the main alert page</span></span>
- <span data-ttu-id="e1df0-168">Обратитесь к эксперту по угрозам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e1df0-168">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="e1df0-169">Просмотр отправки</span><span class="sxs-lookup"><span data-stu-id="e1df0-169">View submission</span></span>
- <span data-ttu-id="e1df0-170">Ссылка на другой инцидент</span><span class="sxs-lookup"><span data-stu-id="e1df0-170">Link to another incident</span></span>
- <span data-ttu-id="e1df0-171">См. оповещение в временной шкале</span><span class="sxs-lookup"><span data-stu-id="e1df0-171">See the alert in a timeline</span></span>
- <span data-ttu-id="e1df0-172">Создание правила подавления</span><span class="sxs-lookup"><span data-stu-id="e1df0-172">Create a suppression rule</span></span>

<span data-ttu-id="e1df0-173">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e1df0-173">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Пример действий по оповещению в центре Microsoft 365 безопасности":::

<span data-ttu-id="e1df0-175">Список дополнительных действий зависит от типа оповещения.</span><span class="sxs-lookup"><span data-stu-id="e1df0-175">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="e1df0-176">Устранение оповещений</span><span class="sxs-lookup"><span data-stu-id="e1df0-176">Resolve an alert</span></span>

<span data-ttu-id="e1df0-177">После того, как вы закончили анализ оповещения и его  можно разрешить, перейдите в области Управления оповещения для оповещения и  пометить его состояние как **Разрешено** и классифицировать его как ложное оповещение или true **оповещения**.</span><span class="sxs-lookup"><span data-stu-id="e1df0-177">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="e1df0-178">Для истинных оповещений укажите тип угрозы оповещений в поле **Определение.**</span><span class="sxs-lookup"><span data-stu-id="e1df0-178">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="e1df0-179">Классификация оповещений и указание их определения помогает настроить Microsoft 365 Defender, чтобы обеспечить больше истинных оповещений и меньше ложных оповещений.</span><span class="sxs-lookup"><span data-stu-id="e1df0-179">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e1df0-180">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="e1df0-180">Next steps</span></span>

<span data-ttu-id="e1df0-181">По мере необходимости для инцидентов в процессе продолжайте [расследование.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="e1df0-181">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1df0-182">См. также</span><span class="sxs-lookup"><span data-stu-id="e1df0-182">See also</span></span>

- [<span data-ttu-id="e1df0-183">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="e1df0-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e1df0-184">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="e1df0-184">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="e1df0-185">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="e1df0-185">Investigate incidents</span></span>](investigate-incidents.md)
