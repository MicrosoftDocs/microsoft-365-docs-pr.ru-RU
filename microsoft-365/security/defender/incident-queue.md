---
title: Приоритеты инцидентов в Microsoft 365 Defender
description: Узнайте, как фильтровать инциденты из очереди инцидентов в Microsoft 365 Defender
keywords: инцидент, очередь, обзор, устройства, удостоверения, пользователи, почтовый ящик, электронная почта, инциденты, анализ, ответ
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
ms.openlocfilehash: dba96a43f976353251b5530233667933088f6f29
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594089"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="b08b0-104">Приоритеты инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b08b0-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b08b0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b08b0-105">**Applies to:**</span></span>
- <span data-ttu-id="b08b0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b08b0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b08b0-107">Microsoft 365 Defender применяет аналитику корреляции и совмещает связанные оповещения и автоматические расследования из различных продуктов в инцидент.</span><span class="sxs-lookup"><span data-stu-id="b08b0-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="b08b0-108">Microsoft 365 Defender также вызывает уникальные оповещения о действиях, которые могут быть определены только как вредоносные с учетом конечной видимости, Microsoft 365 Defender имеет во всем наборе продуктов.</span><span class="sxs-lookup"><span data-stu-id="b08b0-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="b08b0-109">Это представление предоставляет аналитикам безопасности более широкую историю атак, которая помогает им лучше понимать и решать сложные угрозы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b08b0-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="b08b0-110">В **очереди Incident** показана коллекция инцидентов, созданных на устройствах, пользователях и почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="b08b0-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="b08b0-111">Это помогает сортировать инциденты для определения приоритетности и создания обоснованного ответного решения информационной безопасности.</span><span class="sxs-lookup"><span data-stu-id="b08b0-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="b08b0-112">Вы получаете очередь инцидентов из & оповещения > **инцидентов** при быстром запуске центра Microsoft 365 безопасности [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b08b0-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="b08b0-113">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="b08b0-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Пример очереди инцидента":::

<span data-ttu-id="b08b0-115">В **разделе Последние инциденты** и оповещения показан график количества полученных предупреждений и инцидентов, созданных за последние 24 часа.</span><span class="sxs-lookup"><span data-stu-id="b08b0-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="b08b0-116">По умолчанию очередь инцидентов в центре Microsoft 365 отображает инциденты, замеченные за последние шесть месяцев.</span><span class="sxs-lookup"><span data-stu-id="b08b0-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="b08b0-117">Последний инцидент находится в верхней части списка, чтобы вы могли увидеть его в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="b08b0-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="b08b0-118">Очередь инцидентов имеет настраиваемые столбцы (выберите столбцы **Выберите),** которые дают вам видимость в различных характеристиках инцидента или влияние сущностей.</span><span class="sxs-lookup"><span data-stu-id="b08b0-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="b08b0-119">Это поможет вам принять обоснованные решения о приоритете инцидентов для анализа.</span><span class="sxs-lookup"><span data-stu-id="b08b0-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="b08b0-120">Для дополнительной видимости с первого взгляда автоматическое имя инцидента создает имена инцидентов на основе атрибутов оповещения, таких как количество затронутых конечных точек, затронутых пользователей, источников обнаружения или категорий.</span><span class="sxs-lookup"><span data-stu-id="b08b0-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="b08b0-121">Это позволяет быстро понять масштаб инцидента.</span><span class="sxs-lookup"><span data-stu-id="b08b0-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="b08b0-122">Например: *многоэтапный инцидент на нескольких конечных точках, сообщаемой несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="b08b0-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="b08b0-123">Инциденты, существовающие до начала автоматического именования инцидентов, не будут иметь их имя изменено.</span><span class="sxs-lookup"><span data-stu-id="b08b0-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="b08b0-124">Очередь инцидентов также предоставляет несколько вариантов фильтрации, которые при применении позволяют выполнить широкий охват всех существующих инцидентов в среде или решить сосредоточиться на конкретном сценарии или угрозе.</span><span class="sxs-lookup"><span data-stu-id="b08b0-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="b08b0-125">Применение фильтров в очереди инцидентов помогает определить, какие инциденты требуют немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="b08b0-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="b08b0-126">Доступные фильтры</span><span class="sxs-lookup"><span data-stu-id="b08b0-126">Available filters</span></span>

<span data-ttu-id="b08b0-127">Из очереди инцидентов по умолчанию можно выбрать **фильтры** для просмотра области Фильтры, из которой можно просмотреть фильтрованный набор инцидентов.</span><span class="sxs-lookup"><span data-stu-id="b08b0-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="b08b0-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="b08b0-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Пример области фильтров для очереди инцидента":::

<span data-ttu-id="b08b0-130">В этой таблице перечислены доступные имена фильтров.</span><span class="sxs-lookup"><span data-stu-id="b08b0-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="b08b0-131">Имя фильтра</span><span class="sxs-lookup"><span data-stu-id="b08b0-131">Filter name</span></span> | <span data-ttu-id="b08b0-132">Описание</span><span class="sxs-lookup"><span data-stu-id="b08b0-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="b08b0-133">Кому назначено</span><span class="sxs-lookup"><span data-stu-id="b08b0-133">Assigned to</span></span> | <span data-ttu-id="b08b0-134">Вы можете выбрать для показа оповещений, которые назначены вам или обрабатываются с помощью автоматизации.</span><span class="sxs-lookup"><span data-stu-id="b08b0-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="b08b0-135">Категории</span><span class="sxs-lookup"><span data-stu-id="b08b0-135">Categories</span></span> | <span data-ttu-id="b08b0-136">Выберите категории, чтобы сосредоточиться на определенных тактиках, методах или компонентах атаки.</span><span class="sxs-lookup"><span data-stu-id="b08b0-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="b08b0-137">Классификация</span><span class="sxs-lookup"><span data-stu-id="b08b0-137">Classification</span></span> | <span data-ttu-id="b08b0-138">Фильтрация инцидентов на основе заданной классификации связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="b08b0-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="b08b0-139">Значения включают в себя подлинные оповещения, ложные оповещения или не за набор.</span><span class="sxs-lookup"><span data-stu-id="b08b0-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="b08b0-140">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="b08b0-140">Data sensitivity</span></span> | <span data-ttu-id="b08b0-141">Целью некоторых атак является фильтрация конфиденциальных или ценных данных.</span><span class="sxs-lookup"><span data-stu-id="b08b0-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="b08b0-142">Применяя фильтр, чтобы увидеть, были ли вовлечены в происшествие конфиденциальные данные, вы можете быстро определить, была ли потенциально скомпрометирована конфиденциальная информация, и определить приоритетность для устранения этих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="b08b0-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="b08b0-143">Применимо только в случае включения Защиты информации от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b08b0-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="b08b0-144">Группа устройств</span><span class="sxs-lookup"><span data-stu-id="b08b0-144">Device group</span></span> | <span data-ttu-id="b08b0-145">Фильтрация определенных групп устройств.</span><span class="sxs-lookup"><span data-stu-id="b08b0-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="b08b0-146">Состояние исследования</span><span class="sxs-lookup"><span data-stu-id="b08b0-146">Investigation state</span></span> | <span data-ttu-id="b08b0-147">Фильтрация инцидентов по статусу автоматического расследования.</span><span class="sxs-lookup"><span data-stu-id="b08b0-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="b08b0-148">Несколько категорий</span><span class="sxs-lookup"><span data-stu-id="b08b0-148">Multiple categories</span></span> | <span data-ttu-id="b08b0-149">Вы можете видеть только инциденты, которые имеют несколько категорий и, следовательно, могут привести к большему ущербу.</span><span class="sxs-lookup"><span data-stu-id="b08b0-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="b08b0-150">Несколько служебных источников</span><span class="sxs-lookup"><span data-stu-id="b08b0-150">Multiple service sources</span></span>  | <span data-ttu-id="b08b0-151">Фильтровать только для просмотров инцидентов, содержащих оповещения из разных источников (Microsoft Defender для конечной точки, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="b08b0-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="b08b0-152">Платформа ОС</span><span class="sxs-lookup"><span data-stu-id="b08b0-152">OS platform</span></span> | <span data-ttu-id="b08b0-153">Ограничить представление очереди инцидентов операционной системой.</span><span class="sxs-lookup"><span data-stu-id="b08b0-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="b08b0-154">Служебные источники</span><span class="sxs-lookup"><span data-stu-id="b08b0-154">Service sources</span></span> | <span data-ttu-id="b08b0-155">Выбрав определенный источник, можно сосредоточиться на инцидентах, которые содержат хотя бы одно оповещение из этого выбранного источника.</span><span class="sxs-lookup"><span data-stu-id="b08b0-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="b08b0-156">Серьезность</span><span class="sxs-lookup"><span data-stu-id="b08b0-156">Severity</span></span> | <span data-ttu-id="b08b0-157">Серьезность инцидента указывает на то, как он может повлиять на ваши активы.</span><span class="sxs-lookup"><span data-stu-id="b08b0-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="b08b0-158">Чем больше серьезность, тем больше воздействие и обычно требуется самое непосредственное внимание.</span><span class="sxs-lookup"><span data-stu-id="b08b0-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="b08b0-159">Состояние</span><span class="sxs-lookup"><span data-stu-id="b08b0-159">Status</span></span> | <span data-ttu-id="b08b0-160">Чтобы узнать, какие из них активны или решены, вы можете ограничить список инцидентов, отображаемых на основе их состояний.</span><span class="sxs-lookup"><span data-stu-id="b08b0-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-steps"></a><span data-ttu-id="b08b0-161">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="b08b0-161">Next steps</span></span>

<span data-ttu-id="b08b0-162">После того как вы определите, какой инцидент требует наивысшего приоритета, выберите его и:</span><span class="sxs-lookup"><span data-stu-id="b08b0-162">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="b08b0-163">[Управление](manage-incidents.md) свойствами инцидента для тегов, назначений, немедленного разрешения ложных срабатываний и комментариев.</span><span class="sxs-lookup"><span data-stu-id="b08b0-163">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="b08b0-164">Начните [свое расследование](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="b08b0-164">Begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b08b0-165">См. также</span><span class="sxs-lookup"><span data-stu-id="b08b0-165">See also</span></span>
- [<span data-ttu-id="b08b0-166">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="b08b0-166">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b08b0-167">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="b08b0-167">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="b08b0-168">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="b08b0-168">Manage incidents</span></span>](manage-incidents.md)
