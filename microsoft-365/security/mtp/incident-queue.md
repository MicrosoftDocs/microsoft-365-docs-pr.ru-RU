---
title: Определение приоритетов инцидентов в защитнике Microsoft 365
description: Узнайте, как определить приоритет инцидентов из очереди инцидентов в защитнике Microsoft 365
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
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846716"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="7b15b-104">Определение приоритетов инцидентов в защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b15b-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7b15b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7b15b-105">**Applies to:**</span></span>
- <span data-ttu-id="7b15b-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b15b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="7b15b-107">Защитник Microsoft 365 применяет корреляционный анализ и собирает все связанные оповещения и расследования из разных продуктов в один инцидент.</span><span class="sxs-lookup"><span data-stu-id="7b15b-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="7b15b-108">Защитник Microsoft 365 также запускает уникальные оповещения о действиях, которые могут быть идентифицированы только как вредоносные, с учетом того, что защитник Microsoft 365 имеет всю доступную область и набор продуктов.</span><span class="sxs-lookup"><span data-stu-id="7b15b-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="7b15b-109">Таким образом, защитник Microsoft 365 закадрово более широкое описание атак, позволяя аналитикам системы безопасности освоить и справляться со сложными угрозами в Организации.</span><span class="sxs-lookup"><span data-stu-id="7b15b-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="7b15b-110">**Очередь инцидентов** показывает список инцидентов, отмеченных с разных устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="7b15b-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="7b15b-111">Это помогает сортировать инциденты для определения приоритетности и создания обоснованного ответного решения информационной безопасности.</span><span class="sxs-lookup"><span data-stu-id="7b15b-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Изображение очереди инцидентов](../../media/incidents-queue.png) 

<span data-ttu-id="7b15b-113">По умолчанию в очереди в центре безопасности Microsoft 365 отображаются инциденты, замеченные за последние 30 дней, причем самый последний инцидент отображается вверху списка, позволяя вам сначала увидеть самые последние инциденты.</span><span class="sxs-lookup"><span data-stu-id="7b15b-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="7b15b-114">В очереди инцидентов отображаются настраиваемые столбцы, позволяющие понять различные характеристики инцидента или вложенных объектов, что поможет вам принять обоснованное решение об определении приоритетности в отношении обрабатываемых инцидентов.</span><span class="sxs-lookup"><span data-stu-id="7b15b-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="7b15b-115">Для дополнительной прозрачности при автоматическом именовании инцидентов создаются имена инцидентов на основе атрибутов оповещений, таких как количество затронутых конечных точек, затронутых пользователей, источников обнаружения или категорий.</span><span class="sxs-lookup"><span data-stu-id="7b15b-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="7b15b-116">Это позволяет быстро оценить область инцидента.</span><span class="sxs-lookup"><span data-stu-id="7b15b-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="7b15b-117">Пример: *многоэтапное инциденто на нескольких конечных точках, обнаруженных несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="7b15b-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="7b15b-118">Имена инцидентов, существовавших до развертывания автоматического наименования инцидентов, не будут изменены.</span><span class="sxs-lookup"><span data-stu-id="7b15b-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="7b15b-119">Очередь инцидентов также предоставляет несколько вариантов фильтрации, которые можно использовать для выбора широкой очистки всех существующих инцидентов в вашей среде либо для того, чтобы сосредоточиться на определенных сценариях или угрозах.</span><span class="sxs-lookup"><span data-stu-id="7b15b-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="7b15b-120">Применение фильтров в очереди инцидентов помогает определить, какие инциденты требуют немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="7b15b-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="7b15b-121">Доступные фильтры</span><span class="sxs-lookup"><span data-stu-id="7b15b-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="7b15b-122">Состояние</span><span class="sxs-lookup"><span data-stu-id="7b15b-122">Status</span></span>
<span data-ttu-id="7b15b-123">Чтобы узнать, какие из них активны или решены, вы можете ограничить список инцидентов, отображаемых на основе их состояний.</span><span class="sxs-lookup"><span data-stu-id="7b15b-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="7b15b-124">Степень серьезности</span><span class="sxs-lookup"><span data-stu-id="7b15b-124">Severity</span></span>
<span data-ttu-id="7b15b-125">Серьезность инцидента указывает на его воздействие на ваши активы.</span><span class="sxs-lookup"><span data-stu-id="7b15b-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="7b15b-126">Чем выше уровень серьезности, тем больше это воздействие, что, как правило, требует немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="7b15b-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="7b15b-127">Присвоено (владелец)</span><span class="sxs-lookup"><span data-stu-id="7b15b-127">Assigned to (owner)</span></span>
<span data-ttu-id="7b15b-128">Вы можете отфильтровать список, выбрав по назначению кому-либо или выбрав те, которые назначены вам.</span><span class="sxs-lookup"><span data-stu-id="7b15b-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="7b15b-129">Множественные оповещения</span><span class="sxs-lookup"><span data-stu-id="7b15b-129">Multiple alerts</span></span> 
<span data-ttu-id="7b15b-130">Отфильтруйте, чтобы просмотреть только те инциденты, в которых есть несколько оповещений.</span><span class="sxs-lookup"><span data-stu-id="7b15b-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="7b15b-131">Это может быть признаком для атаки, которая является более сложной или прогрессирующей в поэтапной атаке.</span><span class="sxs-lookup"><span data-stu-id="7b15b-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="7b15b-132">Несколько служебных источников</span><span class="sxs-lookup"><span data-stu-id="7b15b-132">Multiple service sources</span></span> 
<span data-ttu-id="7b15b-133">Filter, чтобы видеть только инциденты, содержащие оповещения из различных источников (защитник Майкрософт для конечной точки, Microsoft Cloud App Security, защитник Майкрософт для идентификации, защитник Майкрософт для Office 365)</span><span class="sxs-lookup"><span data-stu-id="7b15b-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365)</span></span>
### <a name="service-sources"></a><span data-ttu-id="7b15b-134">Служебные источники</span><span class="sxs-lookup"><span data-stu-id="7b15b-134">Service sources</span></span>
<span data-ttu-id="7b15b-135">Выбрав определенный источник, можно сосредоточиться на инцидентах, которые содержат хотя бы одно оповещение из этого выбранного источника.</span><span class="sxs-lookup"><span data-stu-id="7b15b-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="7b15b-136">Несколько категорий</span><span class="sxs-lookup"><span data-stu-id="7b15b-136">Multiple categories</span></span> 
<span data-ttu-id="7b15b-137">Вы можете просмотреть только те инциденты, которые были сопоставлены с несколькими категориями поэтапной атаки и потенциально могут привести к большему ущербу.</span><span class="sxs-lookup"><span data-stu-id="7b15b-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="7b15b-138">Категории</span><span class="sxs-lookup"><span data-stu-id="7b15b-138">Categories</span></span>
<span data-ttu-id="7b15b-139">Выберите определенные категории для фокусирования на определенном этапе в поэтапной атаке</span><span class="sxs-lookup"><span data-stu-id="7b15b-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="7b15b-140">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="7b15b-140">Data sensitivity</span></span>
<span data-ttu-id="7b15b-141">Целью некоторых атак является фильтрация конфиденциальных или ценных данных.</span><span class="sxs-lookup"><span data-stu-id="7b15b-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="7b15b-142">Применяя фильтр, чтобы увидеть, были ли вовлечены в происшествие конфиденциальные данные, вы можете быстро определить, была ли потенциально скомпрометирована конфиденциальная информация, и определить приоритетность для устранения этих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="7b15b-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="7b15b-143">Применимо только в случае включения Защиты информации от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7b15b-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="7b15b-144">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7b15b-144">Next steps</span></span>
<span data-ttu-id="7b15b-145">После того как вы определили, какому инциденту присваивается наивысший приоритет, вы можете выполнить дополнительные исследования инцидента.</span><span class="sxs-lookup"><span data-stu-id="7b15b-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="7b15b-146">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="7b15b-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="7b15b-147">См. также</span><span class="sxs-lookup"><span data-stu-id="7b15b-147">Related topics</span></span>
- [<span data-ttu-id="7b15b-148">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="7b15b-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="7b15b-149">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="7b15b-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="7b15b-150">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="7b15b-150">Manage incidents</span></span>](manage-incidents.md)
