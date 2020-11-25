---
title: Определение приоритетов инцидентов в защитнике Microsoft 365
description: Узнайте, как отфильтровать инциденты из очереди инцидентов в защитнике Microsoft 365
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
ms.openlocfilehash: e587004fbb3bc6defab985cea9b427f64b3aab35
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409259"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="1fba3-104">Определение приоритетов инцидентов в защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1fba3-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1fba3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1fba3-105">**Applies to:**</span></span>
- <span data-ttu-id="1fba3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fba3-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="1fba3-107">Защитник Microsoft 365 применяет корреляционный анализ и собирает все связанные оповещения и расследования из разных продуктов в один инцидент.</span><span class="sxs-lookup"><span data-stu-id="1fba3-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="1fba3-108">Защитник Microsoft 365 также запускает уникальные оповещения о действиях, которые могут быть идентифицированы только как вредоносные, с учетом того, что защитник Microsoft 365 имеет всю доступную область и набор продуктов.</span><span class="sxs-lookup"><span data-stu-id="1fba3-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="1fba3-109">Это представление дает системе безопасности аналитику более широкие возможности для атаки, что помогает лучше понять и справляться со сложными угрозами в Организации.</span><span class="sxs-lookup"><span data-stu-id="1fba3-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="1fba3-110">**Очередь инцидентов** показывает список инцидентов, отмеченных с разных устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="1fba3-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="1fba3-111">Это помогает сортировать инциденты для определения приоритетности и создания обоснованного ответного решения информационной безопасности.</span><span class="sxs-lookup"><span data-stu-id="1fba3-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Изображение очереди инцидентов](../../media/incidents-queue.png) 

<span data-ttu-id="1fba3-113">По умолчанию в очереди в центре безопасности Microsoft 365 отображаются происшествия, прошедшие за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="1fba3-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="1fba3-114">Самый свежий инцидент находится в верхней части списка, поэтому его можно увидеть первым.</span><span class="sxs-lookup"><span data-stu-id="1fba3-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="1fba3-115">Очередь происшествий предоставляет настраиваемые столбцы, которые позволяют видеть различные характеристики инцидента или вложенных сущностей.</span><span class="sxs-lookup"><span data-stu-id="1fba3-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="1fba3-116">Это помогает принимать обоснованное решение относительно определения приоритета инцидентов для обработки.</span><span class="sxs-lookup"><span data-stu-id="1fba3-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="1fba3-117">Для более удобного отображения, автоматическое именование инцидентов создает имена инцидентов на основе атрибутов оповещений, таких как количество затронутых конечных точек, затронутых пользователей, источники обнаружения или категории.</span><span class="sxs-lookup"><span data-stu-id="1fba3-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="1fba3-118">Это позволяет быстро оценить область инцидента.</span><span class="sxs-lookup"><span data-stu-id="1fba3-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="1fba3-119">Пример: *многоэтапное инциденто на нескольких конечных точках, обнаруженных несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="1fba3-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="1fba3-120">Имена инцидентов, существовавших до развертывания автоматического наименования инцидентов, не будут изменены.</span><span class="sxs-lookup"><span data-stu-id="1fba3-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="1fba3-121">Очередь происшествий также предоставляет несколько параметров фильтрации, которые при применении позволяют выполнить широкое выполнение всех существующих инцидентов в среде или принять решение о конкретном сценарии или угрозе.</span><span class="sxs-lookup"><span data-stu-id="1fba3-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="1fba3-122">Применение фильтров в очереди инцидентов помогает определить, какие инциденты требуют немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="1fba3-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="1fba3-123">Доступные фильтры</span><span class="sxs-lookup"><span data-stu-id="1fba3-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="1fba3-124">Кому назначено</span><span class="sxs-lookup"><span data-stu-id="1fba3-124">Assigned to</span></span>
<span data-ttu-id="1fba3-125">Можно выбрать отображение оповещений, назначенных вам, или тех, которые обрабатываются автоматизацией.</span><span class="sxs-lookup"><span data-stu-id="1fba3-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="1fba3-126">Категории</span><span class="sxs-lookup"><span data-stu-id="1fba3-126">Categories</span></span>
<span data-ttu-id="1fba3-127">Выберите категории, чтобы сосредоточиться на определенных тактиках, методах и компонентах атак.</span><span class="sxs-lookup"><span data-stu-id="1fba3-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="1fba3-128">Классификация</span><span class="sxs-lookup"><span data-stu-id="1fba3-128">Classification</span></span>
<span data-ttu-id="1fba3-129">Фильтрация инцидентов на основе классификаций связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="1fba3-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="1fba3-130">Значения включают в себя истинные оповещения, ложные оповещения или не задано.</span><span class="sxs-lookup"><span data-stu-id="1fba3-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="1fba3-131">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="1fba3-131">Data sensitivity</span></span>
<span data-ttu-id="1fba3-132">Целью некоторых атак является фильтрация конфиденциальных или ценных данных.</span><span class="sxs-lookup"><span data-stu-id="1fba3-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="1fba3-133">Применяя фильтр, чтобы увидеть, были ли вовлечены в происшествие конфиденциальные данные, вы можете быстро определить, была ли потенциально скомпрометирована конфиденциальная информация, и определить приоритетность для устранения этих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="1fba3-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="1fba3-134">Применимо только в случае включения Защиты информации от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1fba3-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="1fba3-135">Группа устройств</span><span class="sxs-lookup"><span data-stu-id="1fba3-135">Device group</span></span>
<span data-ttu-id="1fba3-136">Фильтрация по определенным группам устройств.</span><span class="sxs-lookup"><span data-stu-id="1fba3-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="1fba3-137">Состояние расследования</span><span class="sxs-lookup"><span data-stu-id="1fba3-137">Investigation state</span></span>
<span data-ttu-id="1fba3-138">Фильтрация инцидентов по состоянию автоматического исследования.</span><span class="sxs-lookup"><span data-stu-id="1fba3-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="1fba3-139">Несколько категорий</span><span class="sxs-lookup"><span data-stu-id="1fba3-139">Multiple categories</span></span> 
<span data-ttu-id="1fba3-140">Можно выбрать отображение только тех инцидентов, которые сопоставлены с несколькими категориями, что может привести к более неисправности.</span><span class="sxs-lookup"><span data-stu-id="1fba3-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="1fba3-141">Несколько служебных источников</span><span class="sxs-lookup"><span data-stu-id="1fba3-141">Multiple service sources</span></span> 
<span data-ttu-id="1fba3-142">Filter, чтобы видеть только инциденты, содержащие оповещения из различных источников (защитник Майкрософт для конечной точки, Microsoft Cloud App Security, защитник Майкрософт для идентификации, защитник Майкрософт для Office 365).</span><span class="sxs-lookup"><span data-stu-id="1fba3-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="1fba3-143">Платформа ОС</span><span class="sxs-lookup"><span data-stu-id="1fba3-143">OS platform</span></span>
<span data-ttu-id="1fba3-144">Ограничьте представление очереди инцидентов операционной системой.</span><span class="sxs-lookup"><span data-stu-id="1fba3-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="1fba3-145">Служебные источники</span><span class="sxs-lookup"><span data-stu-id="1fba3-145">Service sources</span></span>
<span data-ttu-id="1fba3-146">Выбрав определенный источник, можно сосредоточиться на инцидентах, которые содержат хотя бы одно оповещение из этого выбранного источника.</span><span class="sxs-lookup"><span data-stu-id="1fba3-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="1fba3-147">Severity</span><span class="sxs-lookup"><span data-stu-id="1fba3-147">Severity</span></span>
<span data-ttu-id="1fba3-148">Степень серьезности инцидента указывает на то, что он может быть связан с ресурсами.</span><span class="sxs-lookup"><span data-stu-id="1fba3-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="1fba3-149">Чем выше степень серьезности, тем больше воздействие и обычно требует немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="1fba3-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="1fba3-150">Состояние</span><span class="sxs-lookup"><span data-stu-id="1fba3-150">Status</span></span>
<span data-ttu-id="1fba3-151">Чтобы узнать, какие из них активны или решены, вы можете ограничить список инцидентов, отображаемых на основе их состояний.</span><span class="sxs-lookup"><span data-stu-id="1fba3-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="1fba3-152">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1fba3-152">Next steps</span></span>
<span data-ttu-id="1fba3-153">После того как вы определили, какому инциденту присваивается наивысший приоритет, вы можете выполнить дополнительные исследования инцидента.</span><span class="sxs-lookup"><span data-stu-id="1fba3-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="1fba3-154">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="1fba3-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="1fba3-155">См. также</span><span class="sxs-lookup"><span data-stu-id="1fba3-155">See also</span></span>
- [<span data-ttu-id="1fba3-156">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="1fba3-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1fba3-157">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="1fba3-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="1fba3-158">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="1fba3-158">Manage incidents</span></span>](manage-incidents.md)
