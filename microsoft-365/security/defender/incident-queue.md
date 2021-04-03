---
title: Приоритеты инцидентов в Microsoft 365 Defender
description: Узнайте, как фильтровать инциденты из очереди инцидентов в Microsoft 365 Defender
keywords: инцидент, очередь, обзор, устройства, удостоверения, пользователи, почтовый ящик, электронная почта, инциденты
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
ms.openlocfilehash: 5aba1ab4bed0eeb5f6127ab865ceea674e8d5902
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501004"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="7f4c4-104">Приоритеты инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f4c4-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7f4c4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7f4c4-105">**Applies to:**</span></span>
- <span data-ttu-id="7f4c4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f4c4-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="7f4c4-107">Microsoft 365 Defender применяет аналитику корреляции и совмещает все связанные оповещения и расследования из разных продуктов в один инцидент.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="7f4c4-108">Microsoft 365 Defender также вызывает уникальные оповещения о действиях, которые могут быть определены только как вредоносные с учетом конечной видимости, что Microsoft 365 Defender имеет во всем имении и наборе продуктов.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="7f4c4-109">Это представление дает аналитику операций безопасности более широкую историю атак, которая помогает им лучше понимать и решать сложные угрозы в организации.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="7f4c4-110">**Очередь инцидентов** показывает список инцидентов, отмеченных с разных устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="7f4c4-111">Это помогает сортировать инциденты для определения приоритетности и создания обоснованного ответного решения информационной безопасности.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Изображение очереди инцидентов](../../media/incidents-queue.png) 

<span data-ttu-id="7f4c4-113">По умолчанию очередь в центре безопасности Microsoft 365 отображает инциденты, замеченные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="7f4c4-114">Последний инцидент находится в верхней части списка, чтобы вы могли увидеть его в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="7f4c4-115">Очередь инцидентов предоставляет настраиваемые столбцы, которые дают вам видимость различных характеристик инцидента или содержащихся сущностей.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="7f4c4-116">Это поможет вам принять обоснованные решения о приоритете инцидентов для обработки.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="7f4c4-117">Для дополнительной видимости с первого взгляда автоматическое имя инцидента создает имена инцидентов на основе атрибутов оповещения, таких как количество затронутых конечных точек, затронутых пользователей, источников обнаружения или категорий.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="7f4c4-118">Это позволяет быстро понять масштаб инцидента.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="7f4c4-119">Например: *многоэтапный инцидент на нескольких конечных точках, сообщаемой несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="7f4c4-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="7f4c4-120">Инциденты, существовающие до начала автоматического именования инцидентов, не будут иметь их имя изменено.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="7f4c4-121">Очередь инцидентов также предоставляет несколько вариантов фильтрации, которые при применении позволяют выполнить широкий охват всех существующих инцидентов в среде или решить сосредоточиться на конкретном сценарии или угрозе.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="7f4c4-122">Применение фильтров в очереди инцидентов помогает определить, какие инциденты требуют немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="7f4c4-123">Доступные фильтры</span><span class="sxs-lookup"><span data-stu-id="7f4c4-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="7f4c4-124">Кому назначено</span><span class="sxs-lookup"><span data-stu-id="7f4c4-124">Assigned to</span></span>
<span data-ttu-id="7f4c4-125">Вы можете выбрать для показа оповещений, которые назначены вам или обрабатываются с помощью автоматизации.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="7f4c4-126">Категории</span><span class="sxs-lookup"><span data-stu-id="7f4c4-126">Categories</span></span>
<span data-ttu-id="7f4c4-127">Выберите категории, чтобы сосредоточиться на определенных тактиках, методах или компонентах атаки.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="7f4c4-128">Классификация</span><span class="sxs-lookup"><span data-stu-id="7f4c4-128">Classification</span></span>
<span data-ttu-id="7f4c4-129">Фильтрация инцидентов на основе заданной классификации связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="7f4c4-130">Значения включают в себя подлинные оповещения, ложные оповещения или не за набор.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="7f4c4-131">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="7f4c4-131">Data sensitivity</span></span>
<span data-ttu-id="7f4c4-132">Целью некоторых атак является фильтрация конфиденциальных или ценных данных.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="7f4c4-133">Применяя фильтр, чтобы увидеть, были ли вовлечены в происшествие конфиденциальные данные, вы можете быстро определить, была ли потенциально скомпрометирована конфиденциальная информация, и определить приоритетность для устранения этих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="7f4c4-134">Применимо только в случае включения Защиты информации от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="7f4c4-135">Группа устройств</span><span class="sxs-lookup"><span data-stu-id="7f4c4-135">Device group</span></span>
<span data-ttu-id="7f4c4-136">Фильтрация определенных групп устройств.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="7f4c4-137">Состояние исследования</span><span class="sxs-lookup"><span data-stu-id="7f4c4-137">Investigation state</span></span>
<span data-ttu-id="7f4c4-138">Фильтрация инцидентов по статусу автоматического расследования.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="7f4c4-139">Несколько категорий</span><span class="sxs-lookup"><span data-stu-id="7f4c4-139">Multiple categories</span></span> 
<span data-ttu-id="7f4c4-140">Вы можете видеть только инциденты, которые имеют несколько категорий и, следовательно, могут привести к большему ущербу.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="7f4c4-141">Несколько служебных источников</span><span class="sxs-lookup"><span data-stu-id="7f4c4-141">Multiple service sources</span></span> 
<span data-ttu-id="7f4c4-142">Фильтруются только инциденты, содержащие оповещения из разных источников (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span><span class="sxs-lookup"><span data-stu-id="7f4c4-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="7f4c4-143">Платформа ОС</span><span class="sxs-lookup"><span data-stu-id="7f4c4-143">OS platform</span></span>
<span data-ttu-id="7f4c4-144">Ограничить представление очереди инцидентов операционной системой.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="7f4c4-145">Служебные источники</span><span class="sxs-lookup"><span data-stu-id="7f4c4-145">Service sources</span></span>
<span data-ttu-id="7f4c4-146">Выбрав определенный источник, можно сосредоточиться на инцидентах, которые содержат хотя бы одно оповещение из этого выбранного источника.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="7f4c4-147">Severity</span><span class="sxs-lookup"><span data-stu-id="7f4c4-147">Severity</span></span>
<span data-ttu-id="7f4c4-148">Серьезность инцидента указывает на то, как он может повлиять на ваши активы.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="7f4c4-149">Чем больше серьезность, тем больше воздействие и обычно требуется самое непосредственное внимание.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="7f4c4-150">Состояние</span><span class="sxs-lookup"><span data-stu-id="7f4c4-150">Status</span></span>
<span data-ttu-id="7f4c4-151">Чтобы узнать, какие из них активны или решены, вы можете ограничить список инцидентов, отображаемых на основе их состояний.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="7f4c4-152">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7f4c4-152">Next steps</span></span>
<span data-ttu-id="7f4c4-153">После того как вы определили, какому инциденту присваивается наивысший приоритет, вы можете выполнить дополнительные исследования инцидента.</span><span class="sxs-lookup"><span data-stu-id="7f4c4-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="7f4c4-154">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="7f4c4-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="7f4c4-155">См. также</span><span class="sxs-lookup"><span data-stu-id="7f4c4-155">See also</span></span>
- [<span data-ttu-id="7f4c4-156">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="7f4c4-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="7f4c4-157">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="7f4c4-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="7f4c4-158">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="7f4c4-158">Manage incidents</span></span>](manage-incidents.md)
