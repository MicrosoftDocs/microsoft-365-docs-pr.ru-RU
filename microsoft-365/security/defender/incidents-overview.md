---
title: Инциденты в Microsoft 365 Defender
description: Изучите инциденты, замеченные на устройствах, пользователях и почтовых ящиках на Microsoft 365 Defender портале.
keywords: инциденты, оповещения, исследование, анализ, ответ, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверения, почтовый ящик, электронная почта, 365, Microsoft, m365, реагирование на инциденты, кибератака
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
ms.openlocfilehash: b6830c77a0c5cc93ea202844a8793c5f69f07650
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028527"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="c0e10-104">Инциденты в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0e10-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c0e10-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c0e10-105">**Applies to:**</span></span>
- <span data-ttu-id="c0e10-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0e10-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="c0e10-107">Хотите попробовать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="c0e10-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="c0e10-108">Вы можете [оценить его в лабораторной среде](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) или [запустить пилотный проект в производственной среде](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="c0e10-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="c0e10-109">Инцидент в Microsoft 365 Defender — это коллекция коррелирующих оповещений и связанных данных, которые составляют историю атаки.</span><span class="sxs-lookup"><span data-stu-id="c0e10-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="c0e10-110">Microsoft 365 службы и приложения создают оповещения при обнаружении подозрительного или вредоносного события или действия.</span><span class="sxs-lookup"><span data-stu-id="c0e10-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="c0e10-111">Отдельные оповещения предоставляют ценные подсказки о завершенной или продолжающейся атаке.</span><span class="sxs-lookup"><span data-stu-id="c0e10-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="c0e10-112">Однако в атаках обычно используются различные методы для различных типов сущностями, например устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="c0e10-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="c0e10-113">Результатом является несколько оповещений для нескольких сущностями в клиенте.</span><span class="sxs-lookup"><span data-stu-id="c0e10-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="c0e10-114">Поскольку сведение отдельных оповещений вместе для получения сведений об атаке может быть сложным и трудоемким, Microsoft 365 Defender автоматически агрегировать оповещения и связанные с ними сведения в инцидент.</span><span class="sxs-lookup"><span data-stu-id="c0e10-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Как Microsoft 365 Defender соотносится события из сущностями с инцидентом":::

<span data-ttu-id="c0e10-116">Просмотрите этот краткий обзор инцидентов в Microsoft 365 Defender (4 минуты).</span><span class="sxs-lookup"><span data-stu-id="c0e10-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="c0e10-117">Группировка связанных оповещений в инцидент дает полное представление об атаке.</span><span class="sxs-lookup"><span data-stu-id="c0e10-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="c0e10-118">Например, вы можете увидеть:</span><span class="sxs-lookup"><span data-stu-id="c0e10-118">For example, you can see:</span></span>

- <span data-ttu-id="c0e10-119">Где началась атака.</span><span class="sxs-lookup"><span data-stu-id="c0e10-119">Where the attack started.</span></span>
- <span data-ttu-id="c0e10-120">Какие тактики были использованы.</span><span class="sxs-lookup"><span data-stu-id="c0e10-120">What tactics were used.</span></span>
- <span data-ttu-id="c0e10-121">Как далеко атака прошла в клиента.</span><span class="sxs-lookup"><span data-stu-id="c0e10-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="c0e10-122">Масштабы атаки, такие как количество устройств, пользователей и почтовых ящиков, пострадали.</span><span class="sxs-lookup"><span data-stu-id="c0e10-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="c0e10-123">Все данные, связанные с атакой.</span><span class="sxs-lookup"><span data-stu-id="c0e10-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="c0e10-124">Если [включено,](m365d-enable.md)Microsoft 365 Defender автоматически [исследовать](m365d-autoir.md) и устранять оповещения с помощью автоматизации и искусственного интеллекта.</span><span class="sxs-lookup"><span data-stu-id="c0e10-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="c0e10-125">Вы также можете выполнить дополнительные действия по исправлению для устранения атаки.</span><span class="sxs-lookup"><span data-stu-id="c0e10-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c0e10-126">Инциденты и оповещения на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="c0e10-126">Incidents and alerts in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="c0e10-127">Вы управляете инцидентами из & оповещения **> инцидентов** при быстром запуске портала Microsoft 365 Defender [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c0e10-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="c0e10-128">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="c0e10-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Страница Инциденты на портале Microsoft 365 Defender":::

<span data-ttu-id="c0e10-130">При выборе имени инцидента отображается сводка об инциденте и предоставляется доступ к вкладкам с дополнительной информацией.</span><span class="sxs-lookup"><span data-stu-id="c0e10-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Пример страницы Сводка инцидента на портале Microsoft 365 Defender":::

<span data-ttu-id="c0e10-132">Дополнительные вкладки для инцидента:</span><span class="sxs-lookup"><span data-stu-id="c0e10-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="c0e10-133">Оповещения</span><span class="sxs-lookup"><span data-stu-id="c0e10-133">Alerts</span></span> 

  <span data-ttu-id="c0e10-134">Все оповещения, связанные с инцидентом, и их сведения.</span><span class="sxs-lookup"><span data-stu-id="c0e10-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="c0e10-135">Устройства</span><span class="sxs-lookup"><span data-stu-id="c0e10-135">Devices</span></span>

  <span data-ttu-id="c0e10-136">Все устройства, которые были идентифицированы как часть или связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="c0e10-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="c0e10-137">Пользователи</span><span class="sxs-lookup"><span data-stu-id="c0e10-137">Users</span></span>

  <span data-ttu-id="c0e10-138">Все пользователи, которые были идентифицированы как часть или связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="c0e10-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="c0e10-139">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="c0e10-139">Mailboxes</span></span>

  <span data-ttu-id="c0e10-140">Все почтовые ящики, которые были идентифицированы как часть или связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="c0e10-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="c0e10-141">Исследования</span><span class="sxs-lookup"><span data-stu-id="c0e10-141">Investigations</span></span>

  <span data-ttu-id="c0e10-142">Все [автоматические расследования,](m365d-autoir.md) инициированные оповещениями об инциденте.</span><span class="sxs-lookup"><span data-stu-id="c0e10-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="c0e10-143">Доказательства и ответы</span><span class="sxs-lookup"><span data-stu-id="c0e10-143">Evidence and Response</span></span>

  <span data-ttu-id="c0e10-144">Все поддерживаемые события и подозрительные объекты в оповещении об инциденте.</span><span class="sxs-lookup"><span data-stu-id="c0e10-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="c0e10-145">Graph (в предварительном просмотре)</span><span class="sxs-lookup"><span data-stu-id="c0e10-145">Graph (in preview)</span></span>

  <span data-ttu-id="c0e10-146">Фигура, показывающая подключение оповещений к сеяным активам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c0e10-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="c0e10-147">Вот связь между инцидентом и его данными и вкладками инцидента на Microsoft 365 Defender портале.</span><span class="sxs-lookup"><span data-stu-id="c0e10-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Связь инцидента и его данных с вкладками инцидента на портале Microsoft 365 Defender":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="c0e10-149">Пример рабочего процесса реагирования на инциденты для Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0e10-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="c0e10-150">Вот пример рабочего процесса для реагирования на инциденты в Microsoft 365 с Microsoft 365 Defender портала.</span><span class="sxs-lookup"><span data-stu-id="c0e10-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Пример рабочего процесса реагирования на инциденты для Microsoft 365":::

<span data-ttu-id="c0e10-152">На постоянной основе определите наиболее приоритетные инциденты для анализа и разрешения в очереди инцидента и подготовь их к реагированию.</span><span class="sxs-lookup"><span data-stu-id="c0e10-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="c0e10-153">Это сочетание:</span><span class="sxs-lookup"><span data-stu-id="c0e10-153">This is a combination of:</span></span>

- <span data-ttu-id="c0e10-154">[Определение наиболее](incident-queue.md) приоритетных инцидентов путем фильтрации и сортировки очереди инцидентов.</span><span class="sxs-lookup"><span data-stu-id="c0e10-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="c0e10-155">[Управление инцидентами](manage-incidents.md) путем изменения названия, назначения их аналитику и добавления тегов и комментариев.</span><span class="sxs-lookup"><span data-stu-id="c0e10-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="c0e10-156">Для каждого инцидента приступить к расследованию и анализу атак [и оповещений:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="c0e10-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   1. <span data-ttu-id="c0e10-157">Просмотреть сводку инцидента, чтобы понять его область и серьезность и какие объекты затронуты (вкладка **Сводка).**</span><span class="sxs-lookup"><span data-stu-id="c0e10-157">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   1. <span data-ttu-id="c0e10-158">Приступить к анализу оповещений, чтобы понять их происхождение, область и серьезность (вкладка **Оповещения).**</span><span class="sxs-lookup"><span data-stu-id="c0e10-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   1. <span data-ttu-id="c0e10-159">При необходимости соберем сведения о устройствах, пользователях и почтовых ящиках (вкладки **Devices,** **Users** и **Mailboxes).**</span><span class="sxs-lookup"><span data-stu-id="c0e10-159">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   1. <span data-ttu-id="c0e10-160">Узнайте, Microsoft 365 Defender [автоматическое](m365d-autoir.md) решение некоторых оповещений (вкладка **Исследования).**</span><span class="sxs-lookup"><span data-stu-id="c0e10-160">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   1. <span data-ttu-id="c0e10-161">При необходимости используйте сведения в наборе данных для инцидента для получения дополнительных сведений (вкладка **Evidence and Response).**</span><span class="sxs-lookup"><span data-stu-id="c0e10-161">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="c0e10-162">После или во время анализа выполните сдерживание, чтобы уменьшить любое дополнительное влияние атаки и устранение угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="c0e10-162">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="c0e10-163">Насколько это возможно, восстановите после атаки, восстановив ресурсы клиента до состояния, в который они были до инцидента.</span><span class="sxs-lookup"><span data-stu-id="c0e10-163">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="c0e10-164">[Устранение](manage-incidents.md#resolve-an-incident) инцидента и у вас будет время для обучения после инцидента:</span><span class="sxs-lookup"><span data-stu-id="c0e10-164">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="c0e10-165">Понимание типа атаки и ее воздействия.</span><span class="sxs-lookup"><span data-stu-id="c0e10-165">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="c0e10-166">Исследование атаки в [Threat Analytics](threat-analytics.md) и сообществе безопасности для тенденции атаки безопасности.</span><span class="sxs-lookup"><span data-stu-id="c0e10-166">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="c0e10-167">Вспомните рабочий процесс, используемый для устранения инцидента и обновления стандартных процессов, процессов, политик и книг по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="c0e10-167">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="c0e10-168">Определите, нужны ли изменения в конфигурации безопасности и реализуйте их.</span><span class="sxs-lookup"><span data-stu-id="c0e10-168">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="c0e10-169">Если вы не в новинку [](incidents-overview.md) для анализа безопасности, см. в предисловии к ответу на первый инцидент для получения дополнительных сведений и пошаговую проверку примера инцидента.</span><span class="sxs-lookup"><span data-stu-id="c0e10-169">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

<span data-ttu-id="c0e10-170">Дополнительные сведения о реагировании на инциденты в продуктах Майкрософт см. [в этой статье.](/security/compass/incident-response-overview)</span><span class="sxs-lookup"><span data-stu-id="c0e10-170">For more information about incident response across Microsoft products, see [this article](/security/compass/incident-response-overview).</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="c0e10-171">Пример операций безопасности для Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0e10-171">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="c0e10-172">Вот пример операций безопасности (SecOps) для Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c0e10-172">Here's an example of security operations (SecOps) for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Пример операций безопасности для Microsoft 365 Defender":::

<span data-ttu-id="c0e10-174">Ежедневные задачи могут включать:</span><span class="sxs-lookup"><span data-stu-id="c0e10-174">Daily tasks can include:</span></span>

- <span data-ttu-id="c0e10-175">[Управление инцидентами](manage-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="c0e10-175">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="c0e10-176">Проверка [действий автоматического расследования и реагирования (AIR)](m365d-action-center.md) в Центре действий</span><span class="sxs-lookup"><span data-stu-id="c0e10-176">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="c0e10-177">Обзор последней [аналитики угроз](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="c0e10-177">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="c0e10-178">[Реагирование](investigate-incidents.md) на инциденты</span><span class="sxs-lookup"><span data-stu-id="c0e10-178">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="c0e10-179">Ежемесячные задачи могут включать:</span><span class="sxs-lookup"><span data-stu-id="c0e10-179">Monthly tasks can include:</span></span>

- <span data-ttu-id="c0e10-180">Просмотр [параметров AIR](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="c0e10-180">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="c0e10-181">Проверка [безопасной оценки](microsoft-secure-score-improvement-actions.md) [и управления & уязвимостей](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="c0e10-181">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="c0e10-182">Отчеты в цепочке управления ИТ-безопасностью</span><span class="sxs-lookup"><span data-stu-id="c0e10-182">Reporting to your IT security management chain</span></span>

<span data-ttu-id="c0e10-183">Ежеквартные задачи могут включать отчет и сводку результатов безопасности для главного сотрудника по информационной безопасности (CISO).</span><span class="sxs-lookup"><span data-stu-id="c0e10-183">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="c0e10-184">Ежегодные задачи могут включать проведение крупных инцидентов или нарушений для проверки персонала, систем и процессов.</span><span class="sxs-lookup"><span data-stu-id="c0e10-184">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="c0e10-185">Ежедневные, ежемесячные, квартальные и ежегодные задачи можно использовать для обновления или уточнения процессов, политик и конфигураций безопасности.</span><span class="sxs-lookup"><span data-stu-id="c0e10-185">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

### <a name="secops-resources-across-microsoft-products"></a><span data-ttu-id="c0e10-186">Ресурсы SecOps для продуктов Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c0e10-186">SecOps resources across Microsoft products</span></span>

<span data-ttu-id="c0e10-187">Дополнительные сведения о SecOps в продуктах Корпорации Майкрософт см. в этих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="c0e10-187">For more information about SecOps across Microsoft's products, see these resources:</span></span>

- [<span data-ttu-id="c0e10-188">Capabilities</span><span class="sxs-lookup"><span data-stu-id="c0e10-188">Capabilities</span></span>](/security/compass/security-operations-capabilities)
- [<span data-ttu-id="c0e10-189">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="c0e10-189">Best practices</span></span>](/security/compass/security-operations)
- [<span data-ttu-id="c0e10-190">Видео и слайды</span><span class="sxs-lookup"><span data-stu-id="c0e10-190">Videos and slides</span></span>](/security/compass/security-operations-videos-and-decks)

## <a name="next-steps"></a><span data-ttu-id="c0e10-191">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c0e10-191">Next steps</span></span>

<span data-ttu-id="c0e10-192">**Если вы не в новинку** для анализа безопасности и реагирования на инциденты:</span><span class="sxs-lookup"><span data-stu-id="c0e10-192">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="c0e10-193">См. в обзоре Respond [to your first incident walkthrough,](first-incident-overview.md) чтобы получить экскурсию по обычному процессу анализа, исправлений и после инцидента на портале Microsoft 365 Defender с примером атаки.</span><span class="sxs-lookup"><span data-stu-id="c0e10-193">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 Defender portal with an example attack.</span></span>

<span data-ttu-id="c0e10-194">**Если у вас есть опыт** анализа безопасности и реагирования на инциденты:</span><span class="sxs-lookup"><span data-stu-id="c0e10-194">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="c0e10-195">Начало работы с очередью инцидента со страницы **Инциденты** портала Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c0e10-195">Get started with the incident queue from the **Incidents** page of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="c0e10-196">Отсюда вы можете:</span><span class="sxs-lookup"><span data-stu-id="c0e10-196">From here, you can:</span></span>

  - <span data-ttu-id="c0e10-197">Узнайте, какие инциденты следует [приоритизировать](incident-queue.md) в зависимости от серьезности и других факторов.</span><span class="sxs-lookup"><span data-stu-id="c0e10-197">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="c0e10-198">[Управление инцидентами,](manage-incidents.md)которые включают переименование, назначение, классификацию и добавление тегов и комментариев на основе рабочего процесса управления инцидентами.</span><span class="sxs-lookup"><span data-stu-id="c0e10-198">[Manage incidents](manage-incidents.md), which includes renaming, assigning, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="c0e10-199">Выполните [расследования](investigate-incidents.md) инцидентов.</span><span class="sxs-lookup"><span data-stu-id="c0e10-199">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="c0e10-200">В этих [книгах ответов на инциденты](/security/compass/incident-response-playbooks) см. подробные рекомендации по фишингу, спрею паролей и атакам на предоставление согласия на предоставление приложений.</span><span class="sxs-lookup"><span data-stu-id="c0e10-200">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

