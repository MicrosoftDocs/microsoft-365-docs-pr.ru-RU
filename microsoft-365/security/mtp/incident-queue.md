---
title: Приоритет инцидентов в Microsoft 365 Defender
description: Узнайте, как фильтровать инциденты из очереди инцидентов в Microsoft 365 Defender
keywords: инцидент, очередь, обзор, устройства, удостоверения, пользователи, почтовый ящик, электронная почта, инциденты
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929298"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="5beed-104">Приоритет инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5beed-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5beed-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5beed-105">**Applies to:**</span></span>
- <span data-ttu-id="5beed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5beed-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="5beed-107">Защитник Microsoft 365 применяет аналитику корреляции и собирает все связанные оповещения и расследования из разных продуктов в один инцидент.</span><span class="sxs-lookup"><span data-stu-id="5beed-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="5beed-108">Microsoft 365 Defender также вызывает уникальные оповещения о действиях, которые могут быть определены как вредоносные с учетом всей видимости, которую Защитник Microsoft 365 имеет во всем поместии и наборе продуктов.</span><span class="sxs-lookup"><span data-stu-id="5beed-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="5beed-109">Это представление дает аналитику операций безопасности более широкую историю атак, которая помогает им лучше понять и справиться со сложными угрозами в организации.</span><span class="sxs-lookup"><span data-stu-id="5beed-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="5beed-110">**Очередь инцидентов** показывает список инцидентов, отмеченных с разных устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="5beed-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="5beed-111">Это помогает сортировать инциденты для определения приоритетности и создания обоснованного ответного решения информационной безопасности.</span><span class="sxs-lookup"><span data-stu-id="5beed-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Изображение очереди инцидентов](../../media/incidents-queue.png) 

<span data-ttu-id="5beed-113">По умолчанию в очереди в Центре безопасности Microsoft 365 отображаются инциденты за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="5beed-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="5beed-114">Последний инцидент находится в верхней части списка, чтобы вы могли увидеть его в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="5beed-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="5beed-115">Очередь инцидентов предоставляет настраиваемые столбцы, которые дают возможность наглядно показать различные характеристики инцидента или содержащихся сущностей.</span><span class="sxs-lookup"><span data-stu-id="5beed-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="5beed-116">Это помогает принимать обоснованные решения относительно приоритетов инцидентов, которые необходимо обработать.</span><span class="sxs-lookup"><span data-stu-id="5beed-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="5beed-117">Для быстрой наглядности автоматическое именовка инцидентов создает имена инцидентов на основе атрибутов оповещений, таких как количество затронутых конечных точек, затронутых пользователей, источники обнаружения или категории.</span><span class="sxs-lookup"><span data-stu-id="5beed-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="5beed-118">Это позволяет быстро понять область инцидента.</span><span class="sxs-lookup"><span data-stu-id="5beed-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="5beed-119">Например: *многоэтапный инцидент на нескольких конечных точках, о чем сообщили несколько источников.*</span><span class="sxs-lookup"><span data-stu-id="5beed-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="5beed-120">Имена инцидентов, которые существовали до автоматического именования инцидентов, не будут изменены.</span><span class="sxs-lookup"><span data-stu-id="5beed-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="5beed-121">Очередь инцидентов также предоставляет несколько параметров фильтрации, которые при применении позволяют выполнить широкую очистку всех существующих инцидентов в вашей среде или решить сосредоточиться на конкретном сценарии или угрозе.</span><span class="sxs-lookup"><span data-stu-id="5beed-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="5beed-122">Применение фильтров в очереди инцидентов помогает определить, какие инциденты требуют немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="5beed-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="5beed-123">Доступные фильтры</span><span class="sxs-lookup"><span data-stu-id="5beed-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="5beed-124">Кому назначено</span><span class="sxs-lookup"><span data-stu-id="5beed-124">Assigned to</span></span>
<span data-ttu-id="5beed-125">Вы можете показывать оповещения, которые назначены вам или обрабатываются автоматизацией.</span><span class="sxs-lookup"><span data-stu-id="5beed-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="5beed-126">Категории</span><span class="sxs-lookup"><span data-stu-id="5beed-126">Categories</span></span>
<span data-ttu-id="5beed-127">Выберите категории, чтобы сосредоточиться на определенных методиках, методах или компонентах атак.</span><span class="sxs-lookup"><span data-stu-id="5beed-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="5beed-128">Классификация</span><span class="sxs-lookup"><span data-stu-id="5beed-128">Classification</span></span>
<span data-ttu-id="5beed-129">Фильтрация инцидентов на основе заданной классификации связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="5beed-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="5beed-130">Значения включают в себя истинные оповещения, ложные или не установленные.</span><span class="sxs-lookup"><span data-stu-id="5beed-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="5beed-131">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="5beed-131">Data sensitivity</span></span>
<span data-ttu-id="5beed-132">Целью некоторых атак является фильтрация конфиденциальных или ценных данных.</span><span class="sxs-lookup"><span data-stu-id="5beed-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="5beed-133">Применяя фильтр, чтобы увидеть, были ли вовлечены в происшествие конфиденциальные данные, вы можете быстро определить, была ли потенциально скомпрометирована конфиденциальная информация, и определить приоритетность для устранения этих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="5beed-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="5beed-134">Применимо только в случае включения Защиты информации от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5beed-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="5beed-135">Группа устройств</span><span class="sxs-lookup"><span data-stu-id="5beed-135">Device group</span></span>
<span data-ttu-id="5beed-136">Фильтрация по определенным группам устройств.</span><span class="sxs-lookup"><span data-stu-id="5beed-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="5beed-137">Состояние исследования</span><span class="sxs-lookup"><span data-stu-id="5beed-137">Investigation state</span></span>
<span data-ttu-id="5beed-138">Фильтрация инцидентов по статусу автоматического исследования.</span><span class="sxs-lookup"><span data-stu-id="5beed-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="5beed-139">Несколько категорий</span><span class="sxs-lookup"><span data-stu-id="5beed-139">Multiple categories</span></span> 
<span data-ttu-id="5beed-140">Вы можете увидеть только инциденты, которые были сонесен с несколькими категориями и, следовательно, могут привести к большему ущербу.</span><span class="sxs-lookup"><span data-stu-id="5beed-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="5beed-141">Несколько служебных источников</span><span class="sxs-lookup"><span data-stu-id="5beed-141">Multiple service sources</span></span> 
<span data-ttu-id="5beed-142">Фильтрация позволяет отфильтровать только инциденты, содержащие оповещения из разных источников (Microsoft Defender для конечной точки, Microsoft Cloud App Security, Microsoft Defender для удостоверений, Microsoft Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="5beed-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="5beed-143">Платформа ОС</span><span class="sxs-lookup"><span data-stu-id="5beed-143">OS platform</span></span>
<span data-ttu-id="5beed-144">Ограничить представление очереди инцидентов операционной системой.</span><span class="sxs-lookup"><span data-stu-id="5beed-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="5beed-145">Служебные источники</span><span class="sxs-lookup"><span data-stu-id="5beed-145">Service sources</span></span>
<span data-ttu-id="5beed-146">Выбрав определенный источник, можно сосредоточиться на инцидентах, которые содержат хотя бы одно оповещение из этого выбранного источника.</span><span class="sxs-lookup"><span data-stu-id="5beed-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="5beed-147">Severity</span><span class="sxs-lookup"><span data-stu-id="5beed-147">Severity</span></span>
<span data-ttu-id="5beed-148">Серьезность инцидента указывает, как он может повлиять на ваши активы.</span><span class="sxs-lookup"><span data-stu-id="5beed-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="5beed-149">Чем выше степень серьезности, тем больше влияние и, как правило, требуется наиболее непосредственное внимание.</span><span class="sxs-lookup"><span data-stu-id="5beed-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="5beed-150">Состояние</span><span class="sxs-lookup"><span data-stu-id="5beed-150">Status</span></span>
<span data-ttu-id="5beed-151">Чтобы узнать, какие из них активны или решены, вы можете ограничить список инцидентов, отображаемых на основе их состояний.</span><span class="sxs-lookup"><span data-stu-id="5beed-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="5beed-152">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5beed-152">Next steps</span></span>
<span data-ttu-id="5beed-153">После того как вы определили, какому инциденту присваивается наивысший приоритет, вы можете выполнить дополнительные исследования инцидента.</span><span class="sxs-lookup"><span data-stu-id="5beed-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="5beed-154">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="5beed-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="5beed-155">См. также</span><span class="sxs-lookup"><span data-stu-id="5beed-155">See also</span></span>
- [<span data-ttu-id="5beed-156">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="5beed-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5beed-157">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="5beed-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5beed-158">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="5beed-158">Manage incidents</span></span>](manage-incidents.md)
