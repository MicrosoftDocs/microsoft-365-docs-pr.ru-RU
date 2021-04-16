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
ms.openlocfilehash: 8acd8d85826d7bda399c03cc60f2806af954c6c3
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861607"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="bef6c-104">Приоритеты инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bef6c-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bef6c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bef6c-105">**Applies to:**</span></span>
- <span data-ttu-id="bef6c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bef6c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bef6c-107">Microsoft 365 Defender применяет аналитику корреляции и агрегизирует связанные оповещения и автоматические расследования из разных продуктов в инцидент.</span><span class="sxs-lookup"><span data-stu-id="bef6c-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="bef6c-108">Microsoft 365 Defender также вызывает уникальные оповещения о действиях, которые могут быть определены только как вредоносные, учитывая всю заметную видимость, которую Microsoft 365 Defender имеет во всем наборе продуктов.</span><span class="sxs-lookup"><span data-stu-id="bef6c-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="bef6c-109">Это представление предоставляет аналитикам безопасности более широкую историю атак, которая помогает им лучше понимать и решать сложные угрозы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bef6c-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="bef6c-110">В **очереди Incident** показана коллекция инцидентов, созданных на устройствах, пользователях и почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="bef6c-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="bef6c-111">Это помогает сортировать инциденты для определения приоритетности и создания обоснованного ответного решения информационной безопасности.</span><span class="sxs-lookup"><span data-stu-id="bef6c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="bef6c-112">Вы получаете очередь инцидентов из & оповещений > **инцидентов** при быстром запуске центра безопасности Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="bef6c-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Пример очереди инцидента":::

<span data-ttu-id="bef6c-114">По умолчанию очередь инцидентов в центре безопасности Microsoft 365 отображает инциденты, замеченные за последние шесть месяцев.</span><span class="sxs-lookup"><span data-stu-id="bef6c-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="bef6c-115">Последний инцидент находится в верхней части списка, чтобы вы могли увидеть его в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="bef6c-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="bef6c-116">Очередь инцидентов имеет настраиваемые столбцы (выберите столбцы **Выберите),** которые дают вам видимость в различных характеристиках инцидента или влияние сущностей.</span><span class="sxs-lookup"><span data-stu-id="bef6c-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="bef6c-117">Это поможет вам принять обоснованные решения о приоритете инцидентов для анализа.</span><span class="sxs-lookup"><span data-stu-id="bef6c-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="bef6c-118">Для дополнительной видимости с первого взгляда автоматическое имя инцидента создает имена инцидентов на основе атрибутов оповещения, таких как количество затронутых конечных точек, затронутых пользователей, источников обнаружения или категорий.</span><span class="sxs-lookup"><span data-stu-id="bef6c-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="bef6c-119">Это позволяет быстро понять масштаб инцидента.</span><span class="sxs-lookup"><span data-stu-id="bef6c-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="bef6c-120">Например: *многоэтапный инцидент на нескольких конечных точках, сообщаемой несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="bef6c-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="bef6c-121">Инциденты, существовающие до начала автоматического именования инцидентов, не будут иметь их имя изменено.</span><span class="sxs-lookup"><span data-stu-id="bef6c-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="bef6c-122">Очередь инцидентов также предоставляет несколько вариантов фильтрации, которые при применении позволяют выполнить широкий охват всех существующих инцидентов в среде или решить сосредоточиться на конкретном сценарии или угрозе.</span><span class="sxs-lookup"><span data-stu-id="bef6c-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="bef6c-123">Применение фильтров в очереди инцидентов помогает определить, какие инциденты требуют немедленного внимания.</span><span class="sxs-lookup"><span data-stu-id="bef6c-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="bef6c-124">Доступные фильтры</span><span class="sxs-lookup"><span data-stu-id="bef6c-124">Available filters</span></span>

<span data-ttu-id="bef6c-125">Из очереди инцидентов по умолчанию можно выбрать **фильтры** для просмотра области Фильтры, из которой можно просмотреть фильтрованный набор инцидентов.</span><span class="sxs-lookup"><span data-stu-id="bef6c-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="bef6c-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="bef6c-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Пример области фильтров для очереди инцидента":::

<span data-ttu-id="bef6c-128">В этой таблице перечислены доступные имена фильтров.</span><span class="sxs-lookup"><span data-stu-id="bef6c-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="bef6c-129">Имя фильтра</span><span class="sxs-lookup"><span data-stu-id="bef6c-129">Filter name</span></span> | <span data-ttu-id="bef6c-130">Описание</span><span class="sxs-lookup"><span data-stu-id="bef6c-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="bef6c-131">Кому назначено</span><span class="sxs-lookup"><span data-stu-id="bef6c-131">Assigned to</span></span> | <span data-ttu-id="bef6c-132">Вы можете выбрать для показа оповещений, которые назначены вам или обрабатываются с помощью автоматизации.</span><span class="sxs-lookup"><span data-stu-id="bef6c-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="bef6c-133">Категории</span><span class="sxs-lookup"><span data-stu-id="bef6c-133">Categories</span></span> | <span data-ttu-id="bef6c-134">Выберите категории, чтобы сосредоточиться на определенных тактиках, методах или компонентах атаки.</span><span class="sxs-lookup"><span data-stu-id="bef6c-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="bef6c-135">Классификация</span><span class="sxs-lookup"><span data-stu-id="bef6c-135">Classification</span></span> | <span data-ttu-id="bef6c-136">Фильтрация инцидентов на основе заданной классификации связанных оповещений.</span><span class="sxs-lookup"><span data-stu-id="bef6c-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="bef6c-137">Значения включают в себя подлинные оповещения, ложные оповещения или не за набор.</span><span class="sxs-lookup"><span data-stu-id="bef6c-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="bef6c-138">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="bef6c-138">Data sensitivity</span></span> | <span data-ttu-id="bef6c-139">Целью некоторых атак является фильтрация конфиденциальных или ценных данных.</span><span class="sxs-lookup"><span data-stu-id="bef6c-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="bef6c-140">Применяя фильтр, чтобы увидеть, были ли вовлечены в происшествие конфиденциальные данные, вы можете быстро определить, была ли потенциально скомпрометирована конфиденциальная информация, и определить приоритетность для устранения этих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="bef6c-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="bef6c-141">Применимо только в случае включения Защиты информации от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bef6c-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="bef6c-142">Группа устройств</span><span class="sxs-lookup"><span data-stu-id="bef6c-142">Device group</span></span> | <span data-ttu-id="bef6c-143">Фильтрация определенных групп устройств.</span><span class="sxs-lookup"><span data-stu-id="bef6c-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="bef6c-144">Состояние исследования</span><span class="sxs-lookup"><span data-stu-id="bef6c-144">Investigation state</span></span> | <span data-ttu-id="bef6c-145">Фильтрация инцидентов по статусу автоматического расследования.</span><span class="sxs-lookup"><span data-stu-id="bef6c-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="bef6c-146">Несколько категорий</span><span class="sxs-lookup"><span data-stu-id="bef6c-146">Multiple categories</span></span> | <span data-ttu-id="bef6c-147">Вы можете видеть только инциденты, которые имеют несколько категорий и, следовательно, могут привести к большему ущербу.</span><span class="sxs-lookup"><span data-stu-id="bef6c-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="bef6c-148">Несколько служебных источников</span><span class="sxs-lookup"><span data-stu-id="bef6c-148">Multiple service sources</span></span>  | <span data-ttu-id="bef6c-149">Фильтруются только инциденты, содержащие оповещения из разных источников (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span><span class="sxs-lookup"><span data-stu-id="bef6c-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="bef6c-150">Платформа ОС</span><span class="sxs-lookup"><span data-stu-id="bef6c-150">OS platform</span></span> | <span data-ttu-id="bef6c-151">Ограничить представление очереди инцидентов операционной системой.</span><span class="sxs-lookup"><span data-stu-id="bef6c-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="bef6c-152">Служебные источники</span><span class="sxs-lookup"><span data-stu-id="bef6c-152">Service sources</span></span> | <span data-ttu-id="bef6c-153">Выбрав определенный источник, можно сосредоточиться на инцидентах, которые содержат хотя бы одно оповещение из этого выбранного источника.</span><span class="sxs-lookup"><span data-stu-id="bef6c-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="bef6c-154">Severity</span><span class="sxs-lookup"><span data-stu-id="bef6c-154">Severity</span></span> | <span data-ttu-id="bef6c-155">Серьезность инцидента указывает на то, как он может повлиять на ваши активы.</span><span class="sxs-lookup"><span data-stu-id="bef6c-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="bef6c-156">Чем больше серьезность, тем больше воздействие и обычно требуется самое непосредственное внимание.</span><span class="sxs-lookup"><span data-stu-id="bef6c-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="bef6c-157">Состояние</span><span class="sxs-lookup"><span data-stu-id="bef6c-157">Status</span></span> | <span data-ttu-id="bef6c-158">Чтобы узнать, какие из них активны или решены, вы можете ограничить список инцидентов, отображаемых на основе их состояний.</span><span class="sxs-lookup"><span data-stu-id="bef6c-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="bef6c-159">Рабочий процесс реагирования на инциденты</span><span class="sxs-lookup"><span data-stu-id="bef6c-159">Incident response workflow</span></span>

<span data-ttu-id="bef6c-160">Вот типичный рабочий процесс для реагирования на инциденты:</span><span class="sxs-lookup"><span data-stu-id="bef6c-160">Here is the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="bef6c-161">Определение и определение наиболее приоритетных инцидентов для расследования и разрешения.</span><span class="sxs-lookup"><span data-stu-id="bef6c-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="bef6c-162">Для каждого инцидента с высоким приоритетом приступить к [расследованию:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="bef6c-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="bef6c-163">а.</span><span class="sxs-lookup"><span data-stu-id="bef6c-163">a.</span></span> <span data-ttu-id="bef6c-164">Просмотреть сводку инцидента, чтобы понять его область, какие объекты затронуты, и серьезность (вкладка **Сводка).**</span><span class="sxs-lookup"><span data-stu-id="bef6c-164">View the summary of the incident to understand it's scope, what entities are affected, and severity (the **Summary** tab).</span></span>

   <span data-ttu-id="bef6c-165">б.</span><span class="sxs-lookup"><span data-stu-id="bef6c-165">b.</span></span> <span data-ttu-id="bef6c-166">Начните поиск оповещений, чтобы понять их происхождение, область и серьезность (вкладка **Оповещения).**</span><span class="sxs-lookup"><span data-stu-id="bef6c-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="bef6c-167">в.</span><span class="sxs-lookup"><span data-stu-id="bef6c-167">c.</span></span> <span data-ttu-id="bef6c-168">При необходимости соберем сведения о устройствах, пользователях и почтовых ящиках (вкладки **Devices,** **Users** и **Mailboxes).**</span><span class="sxs-lookup"><span data-stu-id="bef6c-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="bef6c-169">г.</span><span class="sxs-lookup"><span data-stu-id="bef6c-169">d.</span></span> <span data-ttu-id="bef6c-170">Узнайте, как Защитник Microsoft 365 автоматически разрешил некоторые оповещения (вкладка **Исследования).**</span><span class="sxs-lookup"><span data-stu-id="bef6c-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="bef6c-171">д.</span><span class="sxs-lookup"><span data-stu-id="bef6c-171">e.</span></span> <span data-ttu-id="bef6c-172">При необходимости используйте сведения в наборе данных для инцидента для получения дополнительных сведений (вкладка **Evidence and Response).**</span><span class="sxs-lookup"><span data-stu-id="bef6c-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

<span data-ttu-id="bef6c-173">При расследовании необходимо иметь дело с:</span><span class="sxs-lookup"><span data-stu-id="bef6c-173">As you investigate, you should be concerned with:</span></span>

- <span data-ttu-id="bef6c-174">Сдерживание. Уменьшение любого дополнительного влияния на клиента.</span><span class="sxs-lookup"><span data-stu-id="bef6c-174">Containment: Reducing any additional impact on your tenant.</span></span>
- <span data-ttu-id="bef6c-175">Ликвидация. Устранение угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="bef6c-175">Eradication: Removing the security threat.</span></span>
- <span data-ttu-id="bef6c-176">Восстановление. Восстановление ресурсов клиента до состояния, в который они находились до атаки.</span><span class="sxs-lookup"><span data-stu-id="bef6c-176">Recovery: Restoring your tenant resources to the state they were in before the attack.</span></span>

<span data-ttu-id="bef6c-177">После устранения инцидента усвойте момент, чтобы узнать из него:</span><span class="sxs-lookup"><span data-stu-id="bef6c-177">After you resolve the incident, take a moment to learn from it to:</span></span>

- <span data-ttu-id="bef6c-178">Понимание типа атаки и ее воздействия.</span><span class="sxs-lookup"><span data-stu-id="bef6c-178">Understand the type of the attack and its impact.</span></span>
- <span data-ttu-id="bef6c-179">Исследование атаки в сообществе безопасности для тенденции атаки безопасности.</span><span class="sxs-lookup"><span data-stu-id="bef6c-179">Research the attack in the security community for a security attack trend.</span></span>
- <span data-ttu-id="bef6c-180">Вспомните рабочий процесс, используемый для устранения инцидента и обновления стандартных процессов и книг воспроизведения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="bef6c-180">Recall the workflow you used to resolve the incident and update your standard workflows and playbooks as needed.</span></span>

<span data-ttu-id="bef6c-181">Вот сводка основного процесса.</span><span class="sxs-lookup"><span data-stu-id="bef6c-181">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="Основной процесс расследования инцидентов":::

## <a name="next-step"></a><span data-ttu-id="bef6c-183">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="bef6c-183">Next step</span></span>

<span data-ttu-id="bef6c-184">После того как вы определите, какой инцидент требует наивысшего приоритета, выберите его и приступить к [расследованию.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="bef6c-184">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bef6c-185">См. также</span><span class="sxs-lookup"><span data-stu-id="bef6c-185">See also</span></span>
- [<span data-ttu-id="bef6c-186">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="bef6c-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="bef6c-187">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="bef6c-187">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="bef6c-188">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="bef6c-188">Manage incidents</span></span>](manage-incidents.md)
