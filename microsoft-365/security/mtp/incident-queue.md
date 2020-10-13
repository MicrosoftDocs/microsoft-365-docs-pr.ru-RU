---
title: Определение приоритетности инцидентов в службе Защиты от угроз (Майкрософт)
description: Узнайте, каким образом определять приоритетность инцидентов в очереди происшествий в службе Защиты от угроз (Майкрософт)
keywords: инцидент, очередь, обзор, устройства, удостоверения, пользователи, почтовый ящик, электронная почта, инциденты
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 382cfd374c40d0c5a0dd7d7705281bd56263d8b8
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430827"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="44f3b-104">Определение приоритетности инцидентов в службе Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="44f3b-104">Prioritize incidents in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="44f3b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="44f3b-105">**Applies to:**</span></span>
- <span data-ttu-id="44f3b-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="44f3b-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="44f3b-107">Защита от угроз (Майкрософт) применяет аналитику корреляции и агрегирует все связанные оповещения и исследования от различных продуктов в один инцидент.</span><span class="sxs-lookup"><span data-stu-id="44f3b-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="44f3b-108">Кроме того, служба Защиты от угроз (Майкрософт) активирует уникальные оповещения для действий, которые можно определить только как вредоносные на основании полного контроля, который имеется у службы защиты от угроз (Майкрософт) над всеми ресурсами и наборами продуктов.</span><span class="sxs-lookup"><span data-stu-id="44f3b-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="44f3b-109">Таким образом, служба Защиты от угроз (Майкрософт) сужает обширную историю атаки, позволяя аналитику по обеспечению безопасности понимать и работать с комплексными угрозами в организации.</span><span class="sxs-lookup"><span data-stu-id="44f3b-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="44f3b-110">**Очередь инцидентов** показывает список инцидентов, отмеченных с разных устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="44f3b-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="44f3b-111">Это помогает сортировать инциденты для определения приоритетности и создания обоснованного ответного решения информационной безопасности.</span><span class="sxs-lookup"><span data-stu-id="44f3b-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Изображение очереди инцидентов](../../media/incidents-queue.png) 

<span data-ttu-id="44f3b-113">По умолчанию в очереди в центре безопасности Microsoft 365 отображаются инциденты, замеченные за последние 30 дней, причем самый последний инцидент отображается вверху списка, позволяя вам сначала увидеть самые последние инциденты.</span><span class="sxs-lookup"><span data-stu-id="44f3b-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="44f3b-114">В очереди инцидентов отображаются настраиваемые столбцы, позволяющие понять различные характеристики инцидента или вложенных объектов, что поможет вам принять обоснованное решение об определении приоритетности в отношении обрабатываемых инцидентов.</span><span class="sxs-lookup"><span data-stu-id="44f3b-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="44f3b-115">Для дополнительной прозрачности при автоматическом именовании инцидентов создаются имена инцидентов на основе атрибутов оповещений, таких как количество затронутых конечных точек, затронутых пользователей, источников обнаружения или категорий.</span><span class="sxs-lookup"><span data-stu-id="44f3b-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="44f3b-116">Это позволяет быстро оценить область инцидента.</span><span class="sxs-lookup"><span data-stu-id="44f3b-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="44f3b-117">Пример: *многоэтапное инциденто на нескольких конечных точках, обнаруженных несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="44f3b-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="44f3b-118">Имена инцидентов, существовавших до развертывания автоматического наименования инцидентов, не будут изменены.</span><span class="sxs-lookup"><span data-stu-id="44f3b-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="44f3b-119">Очередь инцидентов также предоставляет несколько вариантов фильтрации, которые можно использовать для выбора широкой очистки всех существующих инцидентов в вашей среде либо для того, чтобы сосредоточиться на определенных сценариях или угрозах.</span><span class="sxs-lookup"><span data-stu-id="44f3b-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="44f3b-120">Применение фильтров в очереди инцидентов помогает определить, какие инциденты требуют немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="44f3b-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="44f3b-121">Доступные фильтры</span><span class="sxs-lookup"><span data-stu-id="44f3b-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="44f3b-122">Состояние</span><span class="sxs-lookup"><span data-stu-id="44f3b-122">Status</span></span>
<span data-ttu-id="44f3b-123">Чтобы узнать, какие из них активны или решены, вы можете ограничить список инцидентов, отображаемых на основе их состояний.</span><span class="sxs-lookup"><span data-stu-id="44f3b-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="44f3b-124">Степень серьезности</span><span class="sxs-lookup"><span data-stu-id="44f3b-124">Severity</span></span>
<span data-ttu-id="44f3b-125">Серьезность инцидента указывает на его воздействие на ваши активы.</span><span class="sxs-lookup"><span data-stu-id="44f3b-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="44f3b-126">Чем выше уровень серьезности, тем больше это воздействие, что, как правило, требует немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="44f3b-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="44f3b-127">Присвоено (владелец)</span><span class="sxs-lookup"><span data-stu-id="44f3b-127">Assigned to (owner)</span></span>
<span data-ttu-id="44f3b-128">Вы можете отфильтровать список, выбрав по назначению кому-либо или выбрав те, которые назначены вам.</span><span class="sxs-lookup"><span data-stu-id="44f3b-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="44f3b-129">Множественные оповещения</span><span class="sxs-lookup"><span data-stu-id="44f3b-129">Multiple alerts</span></span> 
<span data-ttu-id="44f3b-130">Отфильтруйте, чтобы просмотреть только те инциденты, в которых есть несколько оповещений.</span><span class="sxs-lookup"><span data-stu-id="44f3b-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="44f3b-131">Это может быть признаком для атаки, которая является более сложной или прогрессирующей в поэтапной атаке.</span><span class="sxs-lookup"><span data-stu-id="44f3b-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="44f3b-132">Несколько служебных источников</span><span class="sxs-lookup"><span data-stu-id="44f3b-132">Multiple service sources</span></span> 
<span data-ttu-id="44f3b-133">Отфильтруйте, чтобы видеть только инциденты, содержащие оповещения из различных источников (Расширенная защита от угроз в Microsoft Defender, Microsoft Cloud App Security, Расширенная защита от угроз в Azure, Расширенная защита от угроз в Office 365)</span><span class="sxs-lookup"><span data-stu-id="44f3b-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="44f3b-134">Служебные источники</span><span class="sxs-lookup"><span data-stu-id="44f3b-134">Service sources</span></span>
<span data-ttu-id="44f3b-135">Выбрав определенный источник, можно сосредоточиться на инцидентах, которые содержат хотя бы одно оповещение из этого выбранного источника.</span><span class="sxs-lookup"><span data-stu-id="44f3b-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="44f3b-136">Несколько категорий</span><span class="sxs-lookup"><span data-stu-id="44f3b-136">Multiple categories</span></span> 
<span data-ttu-id="44f3b-137">Вы можете просмотреть только те инциденты, которые были сопоставлены с несколькими категориями поэтапной атаки и потенциально могут привести к большему ущербу.</span><span class="sxs-lookup"><span data-stu-id="44f3b-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="44f3b-138">Категории</span><span class="sxs-lookup"><span data-stu-id="44f3b-138">Categories</span></span>
<span data-ttu-id="44f3b-139">Выберите определенные категории для фокусирования на определенном этапе в поэтапной атаке</span><span class="sxs-lookup"><span data-stu-id="44f3b-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="44f3b-140">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="44f3b-140">Data sensitivity</span></span>
<span data-ttu-id="44f3b-141">Целью некоторых атак является фильтрация конфиденциальных или ценных данных.</span><span class="sxs-lookup"><span data-stu-id="44f3b-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="44f3b-142">Применяя фильтр, чтобы увидеть, были ли вовлечены в происшествие конфиденциальные данные, вы можете быстро определить, была ли потенциально скомпрометирована конфиденциальная информация, и определить приоритетность для устранения этих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="44f3b-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="44f3b-143">Применимо только в случае включения Защиты информации от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="44f3b-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="44f3b-144">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="44f3b-144">Next steps</span></span>
<span data-ttu-id="44f3b-145">После того как вы определили, какому инциденту присваивается наивысший приоритет, вы можете выполнить дополнительные исследования инцидента.</span><span class="sxs-lookup"><span data-stu-id="44f3b-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="44f3b-146">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="44f3b-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="44f3b-147">См. также</span><span class="sxs-lookup"><span data-stu-id="44f3b-147">Related topics</span></span>
- [<span data-ttu-id="44f3b-148">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="44f3b-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="44f3b-149">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="44f3b-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="44f3b-150">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="44f3b-150">Manage incidents</span></span>](manage-incidents.md)
