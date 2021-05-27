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
ms.openlocfilehash: 4957c92cb95464213cce4a81ded07de166468c73
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689017"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="9dfe5-104">Исследование оповещений в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9dfe5-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9dfe5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9dfe5-105">**Applies to:**</span></span>
- <span data-ttu-id="9dfe5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9dfe5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9dfe5-107">Оповещения являются основой всех инцидентов и указывают на возникновение вредоносных или подозрительных событий в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="9dfe5-108">Оповещения обычно являются частью более широкой атаки и предоставляют подсказки об инциденте.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="9dfe5-109">В Microsoft 365 Defender связанные оповещения объединяются для формирования [инцидентов.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9dfe5-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="9dfe5-110">Инциденты всегда обеспечивают более широкий контекст атаки, однако анализ оповещений может быть полезным при необходимости более глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="9dfe5-111">Очередь **оповещений** показывает текущий набор оповещений.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="9dfe5-112">Вы получаете очередь оповещений из & оповещения > оповещения о быстром запуске центра безопасности Microsoft 365[(security.microsoft.com).](https://security.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="9dfe5-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Пример очереди оповещений":::

<span data-ttu-id="9dfe5-114">Здесь отображаются оповещения из различных решений безопасности Майкрософт, таких как Microsoft Defender для конечной точки, Microsoft Defender для Office 365 и Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="9dfe5-115">По умолчанию очередь оповещений в центре Microsoft 365 безопасности отображает новые и ходовые оповещения за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="9dfe5-116">Последнее оповещение находится в верхней части списка, чтобы вы могли увидеть его в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="9dfe5-117">Из очереди оповещений по умолчанию можно выбрать фильтры, чтобы увидеть области **Фильтры,** из которой можно указать подмножество оповещений. </span><span class="sxs-lookup"><span data-stu-id="9dfe5-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="9dfe5-118">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Пример области фильтров для очереди оповещений":::

<span data-ttu-id="9dfe5-120">Вы можете фильтровать оповещения в соответствии с этими критериями:</span><span class="sxs-lookup"><span data-stu-id="9dfe5-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="9dfe5-121">Серьезность</span><span class="sxs-lookup"><span data-stu-id="9dfe5-121">Severity</span></span>
- <span data-ttu-id="9dfe5-122">Состояние</span><span class="sxs-lookup"><span data-stu-id="9dfe5-122">Status</span></span>
- <span data-ttu-id="9dfe5-123">Категория</span><span class="sxs-lookup"><span data-stu-id="9dfe5-123">Category</span></span>
- <span data-ttu-id="9dfe5-124">Источник обнаружения</span><span class="sxs-lookup"><span data-stu-id="9dfe5-124">Detection source</span></span>
- <span data-ttu-id="9dfe5-125">Теги</span><span class="sxs-lookup"><span data-stu-id="9dfe5-125">Tags</span></span>
- <span data-ttu-id="9dfe5-126">Политика</span><span class="sxs-lookup"><span data-stu-id="9dfe5-126">Policy</span></span>
- <span data-ttu-id="9dfe5-127">Влияние активов</span><span class="sxs-lookup"><span data-stu-id="9dfe5-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="9dfe5-128">Анализ оповещений</span><span class="sxs-lookup"><span data-stu-id="9dfe5-128">Analyze an alert</span></span>

<span data-ttu-id="9dfe5-129">Чтобы увидеть главную страницу оповещения, выберите имя оповещений.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="9dfe5-130">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Пример страницы сведений оповещений в центре Microsoft 365 безопасности":::

<span data-ttu-id="9dfe5-132">Вы также можете выбрать действие **"Откройте главную страницу** оповещения" из области **Управление оповещениями.**</span><span class="sxs-lookup"><span data-stu-id="9dfe5-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="9dfe5-133">Страница оповещения состоит из этих разделов:</span><span class="sxs-lookup"><span data-stu-id="9dfe5-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="9dfe5-134">История оповещения, которая является цепочкой событий и оповещений, связанных с этим оповещением в хронологическом порядке</span><span class="sxs-lookup"><span data-stu-id="9dfe5-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="9dfe5-135">Сводные сведения</span><span class="sxs-lookup"><span data-stu-id="9dfe5-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Пример страницы сведений оповещений в центре Microsoft 365 безопасности":::

<span data-ttu-id="9dfe5-137">На странице оповещений можно выбрать эллипсы **(... )** рядом с любым объектом, чтобы увидеть доступные действия, например открытие страницы оповещения или привязка оповещения к другому инциденту.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="alert-sources"></a><span data-ttu-id="9dfe5-138">Источники оповещений</span><span class="sxs-lookup"><span data-stu-id="9dfe5-138">Alert sources</span></span>
<span data-ttu-id="9dfe5-139">Microsoft 365 Оповещения defender могут приходить из таких решений, как Microsoft Defender для конечной точки, Microsoft Defender для Office 365 и Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-139">Microsoft 365 Defender alerts may come from solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft Cloud App Security.</span></span> <span data-ttu-id="9dfe5-140">В оповещении можно заметить оповещений с предварительно заранее.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-140">You may notice alerts with prepended characters in the alert.</span></span> <span data-ttu-id="9dfe5-141">В следующей таблице содержится руководство, помогая понять сопоставление источников оповещений на основе предоплащенного символа в оповещении.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-141">The following table provides guidance to help you understand the mapping of alert sources based on the prepended character on the alert.</span></span>

> [!NOTE]
> - <span data-ttu-id="9dfe5-142">Предоплащенные GUID-интерфейсы являются специфическими только для унифицированных интерфейсов, таких как очередь единой очереди оповещений, страница унифицированных оповещений, единое расследование и единая проверка.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-142">The prepended GUIDs are specific only to unified experiences such as unified alerts queue, unified alerts page, unified investigation, and unified incident.</span></span><br>
> - <span data-ttu-id="9dfe5-143">Предоплаченный символ не меняет GUID оповещений.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-143">The prepended character does not change the GUID of the alert.</span></span> <span data-ttu-id="9dfe5-144">Единственным изменением GUID является предоплаченный компонент.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-144">The only change to the GUID is the prepended component.</span></span><br>


<span data-ttu-id="9dfe5-145">Источник оповещений</span><span class="sxs-lookup"><span data-stu-id="9dfe5-145">Alert source</span></span> | <span data-ttu-id="9dfe5-146">Предопланенный символ</span><span class="sxs-lookup"><span data-stu-id="9dfe5-146">Prepended character</span></span> 
:---|:---
<span data-ttu-id="9dfe5-147">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="9dfe5-147">Microsoft Defender for Office 365</span></span> | `fa{GUID}` <br> <span data-ttu-id="9dfe5-148">Пример: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="9dfe5-148">Example: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="9dfe5-149">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9dfe5-149">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="9dfe5-150">`da` или `ed` для пользовательских оповещений об обнаружении</span><span class="sxs-lookup"><span data-stu-id="9dfe5-150">`da` or `ed` for custom detection alerts</span></span> <br> 
<span data-ttu-id="9dfe5-151">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="9dfe5-151">Microsoft Defender for Identity</span></span> | `aa{GUID}` <br> <span data-ttu-id="9dfe5-152">Пример: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="9dfe5-152">Example: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="9dfe5-153">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9dfe5-153">Microsoft Cloud App Security</span></span> |`ca{GUID}` <br> <span data-ttu-id="9dfe5-154">Пример: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="9dfe5-154">Example: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 



### <a name="analyze-affected-assets"></a><span data-ttu-id="9dfe5-155">Анализ затронутых активов</span><span class="sxs-lookup"><span data-stu-id="9dfe5-155">Analyze affected assets</span></span>

<span data-ttu-id="9dfe5-156">В **разделе Действия,** принятые, имеется список затронутых активов, таких как почтовые ящики, устройства и пользователи, затронутые этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-156">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="9dfe5-157">Вы также можете выбрать Просмотр в центре **действий,** чтобы просмотреть вкладку **История** центра действий в центре Microsoft 365 безопасности. </span><span class="sxs-lookup"><span data-stu-id="9dfe5-157">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="9dfe5-158">Отслеживание роли оповещения в истории оповещений</span><span class="sxs-lookup"><span data-stu-id="9dfe5-158">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="9dfe5-159">В истории оповещений отображаются все активы или сущности, связанные с оповещением в представлении дерева процесса.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-159">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="9dfe5-160">Оповещение в заголовке находится в центре внимания при первой посадке на странице выбранного оповещения.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-160">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="9dfe5-161">Активы в истории оповещений можно расширить и щелкнуть.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-161">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="9dfe5-162">Они предоставляют дополнительные сведения и ускоряют ответ, позволяя вам действовать прямо в контексте страницы оповещений.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-162">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="9dfe5-163">В разделе история оповещения может содержаться несколько оповещений, при этом дополнительные оповещения, связанные с одним деревом выполнения, отображаются до или после выбранного оповещения.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-163">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="9dfe5-164">Просмотр дополнительных сведений об оповещении на странице подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9dfe5-164">View more alert information on the details page</span></span>

<span data-ttu-id="9dfe5-165">На странице подробные сведения показаны сведения об выбранном оповещении с подробными сведениями и действиями, связанными с ним.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-165">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="9dfe5-166">Если выбрать какой-либо из затронутых активов или сущностях в истории оповещения, страница подробных сведений изменяется, чтобы предоставить контекстную информацию и действия для выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-166">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="9dfe5-167">После выбора объекта, интересуемого, страница сведений изменяется, чтобы отображать сведения о выбранном типе объекта, исторические сведения, когда она доступна, и варианты действий по этому объекту непосредственно на странице оповещение.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-167">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="9dfe5-168">Управление оповещениями</span><span class="sxs-lookup"><span data-stu-id="9dfe5-168">Manage alerts</span></span>

<span data-ttu-id="9dfe5-169">Чтобы управлять оповещением, выберите оповещение в очереди оповещений в строке, чтобы увидеть области **управления оповещениями.**</span><span class="sxs-lookup"><span data-stu-id="9dfe5-169">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="9dfe5-170">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-170">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Пример сводной области оповещений":::

<span data-ttu-id="9dfe5-172">В **области управления** оповещениями можно указать:</span><span class="sxs-lookup"><span data-stu-id="9dfe5-172">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="9dfe5-173">Состояние оповещений (New, Resolved, In progress).</span><span class="sxs-lookup"><span data-stu-id="9dfe5-173">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="9dfe5-174">Классификация оповещений (Not set, True alert, False Alert).</span><span class="sxs-lookup"><span data-stu-id="9dfe5-174">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="9dfe5-175">Для классификации как истинного оповещения тип угрозы для оповещений в **поле Определение.**</span><span class="sxs-lookup"><span data-stu-id="9dfe5-175">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="9dfe5-176">Комментарий к оповещению.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-176">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="9dfe5-177">Один из способов управления оповещениями с помощью тегов.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-177">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="9dfe5-178">Возможность тегов для Microsoft Defender для Office 365 постепенно выводится и в настоящее время находится в предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-178">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="9dfe5-179">В настоящее время измененные имена тегов применяются только к оповещениям, созданным *после* обновления.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-179">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="9dfe5-180">Оповещения, созданные до изменения, не будут отражать обновленное имя тега.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-180">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="9dfe5-181">На этой области вы также можете выполнить эти дополнительные действия:</span><span class="sxs-lookup"><span data-stu-id="9dfe5-181">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="9dfe5-182">Откройте главную страницу оповещений</span><span class="sxs-lookup"><span data-stu-id="9dfe5-182">Open the main alert page</span></span>
- <span data-ttu-id="9dfe5-183">Обратитесь к эксперту по угрозам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9dfe5-183">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="9dfe5-184">Просмотр отправки</span><span class="sxs-lookup"><span data-stu-id="9dfe5-184">View submission</span></span>
- <span data-ttu-id="9dfe5-185">Ссылка на другой инцидент</span><span class="sxs-lookup"><span data-stu-id="9dfe5-185">Link to another incident</span></span>
- <span data-ttu-id="9dfe5-186">См. оповещение в временной шкале</span><span class="sxs-lookup"><span data-stu-id="9dfe5-186">See the alert in a timeline</span></span>
- <span data-ttu-id="9dfe5-187">Создание правила подавления</span><span class="sxs-lookup"><span data-stu-id="9dfe5-187">Create a suppression rule</span></span>

<span data-ttu-id="9dfe5-188">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-188">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Пример действий по оповещению в центре Microsoft 365 безопасности":::

<span data-ttu-id="9dfe5-190">Список дополнительных действий зависит от типа оповещения.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-190">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="9dfe5-191">Устранение оповещений</span><span class="sxs-lookup"><span data-stu-id="9dfe5-191">Resolve an alert</span></span>

<span data-ttu-id="9dfe5-192">После того, как вы закончили анализ оповещения и его  можно разрешить, перейдите в области Управления оповещения для оповещения и  пометить его состояние как **Разрешено** и классифицировать его как ложное оповещение или true **оповещения**.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-192">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="9dfe5-193">Для истинных оповещений укажите тип угрозы оповещений в поле **Определение.**</span><span class="sxs-lookup"><span data-stu-id="9dfe5-193">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="9dfe5-194">Классификация оповещений и указание их определения помогает настроить Microsoft 365 Defender, чтобы обеспечить больше истинных оповещений и меньше ложных оповещений.</span><span class="sxs-lookup"><span data-stu-id="9dfe5-194">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9dfe5-195">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9dfe5-195">Next steps</span></span>

<span data-ttu-id="9dfe5-196">По мере необходимости для инцидентов в процессе продолжайте [расследование.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="9dfe5-196">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9dfe5-197">См. также</span><span class="sxs-lookup"><span data-stu-id="9dfe5-197">See also</span></span>

- [<span data-ttu-id="9dfe5-198">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="9dfe5-198">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="9dfe5-199">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="9dfe5-199">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="9dfe5-200">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="9dfe5-200">Investigate incidents</span></span>](investigate-incidents.md)
