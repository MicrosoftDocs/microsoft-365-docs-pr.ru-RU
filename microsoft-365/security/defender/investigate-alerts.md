---
title: Исследование оповещений в Microsoft 365 Defender
description: Изучите оповещения, которые можно увидеть на устройствах, пользователях и почтовых ящиках.
keywords: инциденты, оповещения, исследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверение, почтовый ящик, электронная почта, 365, microsoft, m365
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
ms.openlocfilehash: 989574a860bea798c48e077f5633c31eb857e85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500935"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="a44b3-104">Исследование оповещений в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a44b3-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a44b3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a44b3-105">**Applies to:**</span></span>
- <span data-ttu-id="a44b3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a44b3-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="a44b3-107">Оповещения являются основой всех инцидентов и указывают на возникновение вредоносных или подозрительных событий в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="a44b3-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="a44b3-108">Оповещения обычно являются частью более широкой атаки и предоставляют подсказки об инциденте.</span><span class="sxs-lookup"><span data-stu-id="a44b3-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="a44b3-109">В Microsoft 365 Defender связанные оповещения объединяются для формирования инцидентов.</span><span class="sxs-lookup"><span data-stu-id="a44b3-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="a44b3-110">Инциденты всегда обеспечивают более широкий контекст атаки, однако при необходимости более глубокого анализа может быть полезное изучение оповещений.</span><span class="sxs-lookup"><span data-stu-id="a44b3-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="a44b3-111">Использование страниц оповещений в расследованиях</span><span class="sxs-lookup"><span data-stu-id="a44b3-111">Using alert pages in investigations</span></span>

<span data-ttu-id="a44b3-112">На вкладке Оповещения на любой странице инцидента выбор оповещения приводит вас к отдельным страницам оповещений.</span><span class="sxs-lookup"><span data-stu-id="a44b3-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="a44b3-113">Страница оповещений состоит из трех разделов: затронутые активы, история оповещения и области сведений.</span><span class="sxs-lookup"><span data-stu-id="a44b3-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![Изображение примера страницы оповещений](../../media/new-alert-page2.png)

<span data-ttu-id="a44b3-115">На странице оповещений можно выбрать трехточечный значок **(...)** рядом с любым объектом, чтобы можно было видеть доступные действия, такие как открытие определенной страницы активов или определенные действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="a44b3-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="a44b3-116">Анализ затронутых активов</span><span class="sxs-lookup"><span data-stu-id="a44b3-116">Analyze affected assets</span></span>
<span data-ttu-id="a44b3-117">В разделе затронутые активы перечислены почтовые ящики, устройства и пользователи, затронутые этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="a44b3-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="a44b3-118">Выбор любой из карт активов заполняет боковую области данных с информацией, в том числе другие оповещения, которые произошли с участием активов, если таковые есть.</span><span class="sxs-lookup"><span data-stu-id="a44b3-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="a44b3-119">Отслеживание роли оповещения в истории оповещений</span><span class="sxs-lookup"><span data-stu-id="a44b3-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="a44b3-120">В истории оповещений отображаются все активы или сущности, связанные с оповещением в представлении дерева процесса.</span><span class="sxs-lookup"><span data-stu-id="a44b3-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="a44b3-121">Оповещение в заголовке находится в центре внимания при первой посадке на странице выбранного оповещения.</span><span class="sxs-lookup"><span data-stu-id="a44b3-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="a44b3-122">Активы в истории оповещений можно расширить и щелкнуть.</span><span class="sxs-lookup"><span data-stu-id="a44b3-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="a44b3-123">Они предоставляют дополнительные сведения и ускоряют ответ, позволяя вам принимать меры прямо в контексте страницы оповещения.</span><span class="sxs-lookup"><span data-stu-id="a44b3-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="a44b3-124">В разделе история оповещения может содержаться несколько оповещений, при этом дополнительные оповещения, связанные с одним деревом выполнения, отображаются до или после выбранного оповещения.</span><span class="sxs-lookup"><span data-stu-id="a44b3-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="a44b3-125">Просмотр дополнительных сведений об оповещении в области сведений</span><span class="sxs-lookup"><span data-stu-id="a44b3-125">View more alert information in the details pane</span></span>

<span data-ttu-id="a44b3-126">На области сведений сначала показаны сведения об выбранном оповещении, а также сведения и действия, связанные с ним.</span><span class="sxs-lookup"><span data-stu-id="a44b3-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="a44b3-127">Если выбрать какой-либо из затронутых активов или сущностях в истории оповещений, сведения будут меняться, чтобы предоставить контекстную информацию и действия для выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="a44b3-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="a44b3-128">После выбора объекта, интересуемого, области сведений меняются для отображения сведений о выбранном типе сущности, исторических данных, когда она доступна, и вариантов действий по этому объекту непосредственно на странице оповещения.</span><span class="sxs-lookup"><span data-stu-id="a44b3-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="a44b3-129">Управление оповещениями</span><span class="sxs-lookup"><span data-stu-id="a44b3-129">Manage alerts</span></span>

<span data-ttu-id="a44b3-130">После проверки оповещений можно вернуться к начатому оповещению, пометить состояние оповещений как Resolved и классифицировать его как "Ложное оповещение" или "Настоящее оповещение".</span><span class="sxs-lookup"><span data-stu-id="a44b3-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="a44b3-131">Классификация оповещений помогает настроить продукт, чтобы обеспечить более верные оповещения и меньше ложных оповещений.</span><span class="sxs-lookup"><span data-stu-id="a44b3-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="a44b3-132">Один из способов управления оповещениями с помощью тегов.</span><span class="sxs-lookup"><span data-stu-id="a44b3-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="a44b3-133">Возможность тегов для Microsoft Defender для Office 365 постепенно выводится и в настоящее время находится в предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="a44b3-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="a44b3-134">В настоящее время измененные имена тегов применяются только к оповещениям, созданным *после* обновления.</span><span class="sxs-lookup"><span data-stu-id="a44b3-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="a44b3-135">Оповещения, созданные до изменения, не будут отражать обновленное имя тега.</span><span class="sxs-lookup"><span data-stu-id="a44b3-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="a44b3-136">Управление единой очередью оповещения</span><span class="sxs-lookup"><span data-stu-id="a44b3-136">Manage the unified alert queue</span></span>

<span data-ttu-id="a44b3-137">Выбор оповещений в & оповещений в области навигации Центра безопасности Microsoft 365 приводит вас к единой очереди оповещения.</span><span class="sxs-lookup"><span data-stu-id="a44b3-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="a44b3-138">В этом разделе отображаются оповещения из различных решений безопасности Майкрософт, таких как Microsoft Defender для конечной точки, Microsoft Defender для Office 365 и Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a44b3-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![Изображение страницы оповещения образца](../../media/unified-alert-queue.png)

<span data-ttu-id="a44b3-140">Очередь оповещений показывает список оповещений, помеченных в сети.</span><span class="sxs-lookup"><span data-stu-id="a44b3-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="a44b3-141">По умолчанию очередь отображает оповещения, замеченные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="a44b3-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="a44b3-142">Последние оповещений показаны в верхней части списка, помогая сначала увидеть самые последние оповещения.</span><span class="sxs-lookup"><span data-stu-id="a44b3-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="a44b3-143">На момент запуска очередь единичек оповещений будет иметь только 7- дней для microsoft Defender для Office 365 оповещений.</span><span class="sxs-lookup"><span data-stu-id="a44b3-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="a44b3-144">Со временем очередь будет продолжать создаваться.</span><span class="sxs-lookup"><span data-stu-id="a44b3-144">The queue will continue to build over time.</span></span> <span data-ttu-id="a44b3-145">Если перед запуском очереди унифицированных оповещений необходимо переделыть оповещения, используйте очередь оповещений в Центре безопасности [и соответствия](https://protection.office.com/viewalerts)требованиям.</span><span class="sxs-lookup"><span data-stu-id="a44b3-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="a44b3-146">В верхней части навигации можно:</span><span class="sxs-lookup"><span data-stu-id="a44b3-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="a44b3-147">Применение фильтров</span><span class="sxs-lookup"><span data-stu-id="a44b3-147">Apply filters</span></span>
- <span data-ttu-id="a44b3-148">Настройка столбцов для добавления или удаления столбцов</span><span class="sxs-lookup"><span data-stu-id="a44b3-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="a44b3-149">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="a44b3-149">Export data</span></span>

<span data-ttu-id="a44b3-150">Можно также фильтровать оповещения по различным критериям:</span><span class="sxs-lookup"><span data-stu-id="a44b3-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="a44b3-151">Severity</span><span class="sxs-lookup"><span data-stu-id="a44b3-151">Severity</span></span>
- <span data-ttu-id="a44b3-152">Состояние</span><span class="sxs-lookup"><span data-stu-id="a44b3-152">Status</span></span>
- <span data-ttu-id="a44b3-153">Категория</span><span class="sxs-lookup"><span data-stu-id="a44b3-153">Category</span></span>
- <span data-ttu-id="a44b3-154">Источник обнаружения</span><span class="sxs-lookup"><span data-stu-id="a44b3-154">Detection source</span></span>
- <span data-ttu-id="a44b3-155">Политика</span><span class="sxs-lookup"><span data-stu-id="a44b3-155">Policy</span></span>
- <span data-ttu-id="a44b3-156">Влияние активов</span><span class="sxs-lookup"><span data-stu-id="a44b3-156">Impacted assets</span></span>
- <span data-ttu-id="a44b3-157">Первое действие</span><span class="sxs-lookup"><span data-stu-id="a44b3-157">First activity</span></span>
- <span data-ttu-id="a44b3-158">Last activity (Последние действия)</span><span class="sxs-lookup"><span data-stu-id="a44b3-158">Last activity</span></span>


<span data-ttu-id="a44b3-159">Чтобы начать расследование инцидента, читайте в материале [Расследование инцидентов в Microsoft 365 Defender](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="a44b3-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="a44b3-160">См. также</span><span class="sxs-lookup"><span data-stu-id="a44b3-160">See also</span></span>

- [<span data-ttu-id="a44b3-161">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="a44b3-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a44b3-162">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="a44b3-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a44b3-163">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="a44b3-163">Manage incidents</span></span>](manage-incidents.md)
