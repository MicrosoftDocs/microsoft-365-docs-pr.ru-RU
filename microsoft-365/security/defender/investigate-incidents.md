---
title: Анализ инцидентов в Microsoft 365 Defender
description: Анализ инцидентов, связанных с устройствами, пользователями и почтовыми ящиками.
keywords: инциденты, инциденты, анализ, ответ, машины, устройства, пользователи, удостоверения, почта, электронная почта, почтовый ящик, исследование, график, доказательства
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
ms.openlocfilehash: 72e1efb8a06fb7fa64b83ab6522fe4cdcfd1a73e
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259640"
---
# <a name="analyze-incidents-in-microsoft-365-defender"></a><span data-ttu-id="3992c-104">Анализ инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3992c-104">Analyze incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3992c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3992c-105">**Applies to:**</span></span>

- <span data-ttu-id="3992c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3992c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3992c-107">Microsoft 365 Defender совмещает все связанные оповещения, активы, расследования и доказательства на всех устройствах, пользователях и почтовых ящиках в инцидент, чтобы дать вам полный обзор всей ширины атаки.</span><span class="sxs-lookup"><span data-stu-id="3992c-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="3992c-108">В случае инцидента вы анализируете оповещения, влияющие на сеть, понимаете, что они означают, и совмещают данные, чтобы можно было разработать эффективный план устранения.</span><span class="sxs-lookup"><span data-stu-id="3992c-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-analysis"></a><span data-ttu-id="3992c-109">Первоначальный анализ</span><span class="sxs-lookup"><span data-stu-id="3992c-109">Initial analysis</span></span>

<span data-ttu-id="3992c-110">Прежде чем погрузиться в подробности, взгляните на свойства и сводку инцидента.</span><span class="sxs-lookup"><span data-stu-id="3992c-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="3992c-111">Вы можете начать с выбора инцидента из столбца контрольных меток.</span><span class="sxs-lookup"><span data-stu-id="3992c-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="3992c-112">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="3992c-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Пример выбора инцидента из столбца контрольных меток":::

<span data-ttu-id="3992c-114">При этом откроется сводная область с ключевыми сведениями об инциденте, такими как серьезность, кому она назначена, и категориями [ATT MITRE &trade;&CK](https://attack.mitre.org/) для инцидента.</span><span class="sxs-lookup"><span data-stu-id="3992c-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="3992c-115">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="3992c-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Пример сводной области для инцидента":::

<span data-ttu-id="3992c-117">Здесь вы можете выбрать страницу **Открытый инцидент**.</span><span class="sxs-lookup"><span data-stu-id="3992c-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="3992c-118">Это открывает главную страницу инцидента, на которой вы найдете дополнительные сводные сведения и вкладки для оповещений, устройств, пользователей, расследований и доказательств.</span><span class="sxs-lookup"><span data-stu-id="3992c-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="3992c-119">Вы также можете открыть главную страницу инцидента, выбрав имя инцидента из очереди инцидента.</span><span class="sxs-lookup"><span data-stu-id="3992c-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="3992c-120">Аннотация</span><span class="sxs-lookup"><span data-stu-id="3992c-120">Summary</span></span>

<span data-ttu-id="3992c-121">На **странице Сводка** вы можете получить снимок в верхней части, чтобы заметить об инциденте.</span><span class="sxs-lookup"><span data-stu-id="3992c-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Пример страницы Сводка для инцидента в центре Microsoft 365 безопасности":::

<span data-ttu-id="3992c-123">Категории атак дают визуальное и числовую представление о том, как продвинулась атака в отношении цепочки убийств.</span><span class="sxs-lookup"><span data-stu-id="3992c-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="3992c-124">Как и другие продукты безопасности Майкрософт, Microsoft 365 Defender соответствует структуре [ATT MITRE&&trade; CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="3992c-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="3992c-125">В разделе "Область" находится список основных ресурсов, затронутых этим инцидентом.</span><span class="sxs-lookup"><span data-stu-id="3992c-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="3992c-126">Если есть какая-либо конкретная информация о ресурсе, например уровень риска, приоритет исследования или любые отметки ресурсов, вся эта информация также будет отображаться в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="3992c-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="3992c-127">Хронология оповещений позволяет заглянуть в хронологический порядок, в котором произошли оповещения, а также причины, по которым эти оповещения связаны с этим инцидентом.</span><span class="sxs-lookup"><span data-stu-id="3992c-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="3992c-128">И последнее — в разделе доказательств приводится сводка о том, сколько различных артефактов было включено в инцидент и их состояние по исправлению, поэтому можно сразу определить, требуется ли вам какое-либо действие.</span><span class="sxs-lookup"><span data-stu-id="3992c-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="3992c-129">Этот обзор может помочь в начальной триаже инцидента, предоставляя представление о верхних характеристиках инцидента, которые вы должны знать.</span><span class="sxs-lookup"><span data-stu-id="3992c-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="3992c-130">Оповещения</span><span class="sxs-lookup"><span data-stu-id="3992c-130">Alerts</span></span>

<span data-ttu-id="3992c-131">На **вкладке Alert** можно просмотреть очередь оповещения о оповещениях, связанных с инцидентом, и другие сведения о них, такие как:</span><span class="sxs-lookup"><span data-stu-id="3992c-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="3992c-132">Серьезность.</span><span class="sxs-lookup"><span data-stu-id="3992c-132">Severity.</span></span>
- <span data-ttu-id="3992c-133">Объекты, которые были вовлечены в оповещение.</span><span class="sxs-lookup"><span data-stu-id="3992c-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="3992c-134">Источник оповещений (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="3992c-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="3992c-135">Причина, по которой они были связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="3992c-135">The reason they were linked together.</span></span>

<span data-ttu-id="3992c-136">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="3992c-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Пример страницы Оповещений об инциденте":::

<span data-ttu-id="3992c-138">По умолчанию оповещений упорядочено в хронологическом порядке, чтобы вы могли видеть, как со временем разыгрался инцидент.</span><span class="sxs-lookup"><span data-stu-id="3992c-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="3992c-139">Выбор каждого оповещения ведет вас на главную страницу оповещений, где можно провести углубленный анализ этого оповещения.</span><span class="sxs-lookup"><span data-stu-id="3992c-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth analysis of that alert.</span></span> 

<span data-ttu-id="3992c-140">Узнайте, как использовать очереди оповещения и страницы оповещения в [анализе оповещений](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3992c-140">Learn how to use the alert queue and alert pages in [analyze alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="3992c-141">Devices</span><span class="sxs-lookup"><span data-stu-id="3992c-141">Devices</span></span>

<span data-ttu-id="3992c-142">На **вкладке Devices** перечислены все устройства, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="3992c-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="3992c-143">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="3992c-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Пример страницы Устройства для инцидента":::

<span data-ttu-id="3992c-145">Вы можете выбрать контрольную отметку для устройства, чтобы увидеть сведения об устройстве, данные каталога, активные оповещения и войти в систему пользователей.</span><span class="sxs-lookup"><span data-stu-id="3992c-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="3992c-146">Выберите имя устройства, чтобы увидеть сведения об устройстве в инвентаризации устройств Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="3992c-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Пример страницы устройств для Microsoft Defender для конечных точек":::

<span data-ttu-id="3992c-148">На странице устройства можно собрать дополнительные сведения об устройстве, такие как все оповещения, сроки и рекомендации по безопасности.</span><span class="sxs-lookup"><span data-stu-id="3992c-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="3992c-149">Например, на вкладке **Timeline** можно прокрутку временной шкалы машины и просмотреть все события и поведения, наблюдаемые на машине в хронологическом порядке, вперемесив с поднятыми оповещениями.</span><span class="sxs-lookup"><span data-stu-id="3992c-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="3992c-150">Вы можете делать проверки по запросу на странице устройства.</span><span class="sxs-lookup"><span data-stu-id="3992c-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="3992c-151">В центре Microsoft 365 выберите конечные точки **> устройства.**</span><span class="sxs-lookup"><span data-stu-id="3992c-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="3992c-152">Выберите устройство с оповещениями, а затем запустите антивирусное сканирование.</span><span class="sxs-lookup"><span data-stu-id="3992c-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="3992c-153">Действия, например антивирусное сканирование, отслеживаются и видны на странице **инвентаризации** устройств.</span><span class="sxs-lookup"><span data-stu-id="3992c-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="3992c-154">Дополнительные дополнительные результаты см. [в антивирусная программа в Microsoft Defender run антивирусная программа в Microsoft Defender на устройствах.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)</span><span class="sxs-lookup"><span data-stu-id="3992c-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="3992c-155">Пользователи</span><span class="sxs-lookup"><span data-stu-id="3992c-155">Users</span></span>

<span data-ttu-id="3992c-156">Вкладка **"Пользователи"** перечисляет всех пользователей, которые были идентифицированы как часть инцидента или связанные с ним.</span><span class="sxs-lookup"><span data-stu-id="3992c-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="3992c-157">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="3992c-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Пример страницы &quot;Пользователи&quot; для инцидента":::

<span data-ttu-id="3992c-159">Вы можете выбрать контрольную отметку для пользователя, чтобы увидеть сведения об угрозе учетной записи пользователя, экспозиции и контактных данных.</span><span class="sxs-lookup"><span data-stu-id="3992c-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="3992c-160">Выберите имя пользователя, чтобы увидеть дополнительные сведения о учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="3992c-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="3992c-161">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="3992c-161">Mailboxes</span></span>

<span data-ttu-id="3992c-162">На **вкладке Почтовые** ящики перечислены все почтовые ящики, которые были идентифицированы как часть или связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="3992c-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="3992c-163">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="3992c-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Пример страницы почтовых ящиков для инцидента":::

<span data-ttu-id="3992c-165">Вы можете выбрать контрольный знак для почтового ящика, чтобы увидеть список активных оповещений.</span><span class="sxs-lookup"><span data-stu-id="3992c-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="3992c-166">Выберите имя почтового ящика, чтобы увидеть дополнительные сведения о почтовом ящике на странице Explorer для Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="3992c-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="3992c-167">Исследования</span><span class="sxs-lookup"><span data-stu-id="3992c-167">Investigations</span></span>

<span data-ttu-id="3992c-168">На **вкладке "Исследования"** перечислены все автоматические расследования, инициированные оповещениями в этом инциденте.</span><span class="sxs-lookup"><span data-stu-id="3992c-168">The **Investigations** tab lists all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="3992c-169">Исследования будут выполнять действия по исправлению или ждать утверждения действий аналитиком в зависимости от настройки автоматических расследований для выполнения в Microsoft Defender для конечной точки и Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="3992c-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Пример страницы Исследования для инцидента":::

<span data-ttu-id="3992c-171">Выберите исследование, чтобы перейти на страницу сведений об исследовании для получения подробной информации об исследовании и о состоянии исправления.</span><span class="sxs-lookup"><span data-stu-id="3992c-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="3992c-172">Если в рамках расследования ожидаются какие-либо действия, ожидающих утверждения, они будут отображаться на вкладке Ожидающих действий. Примите меры в рамках устранения инцидентов.</span><span class="sxs-lookup"><span data-stu-id="3992c-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="3992c-173">Доказательства и ответы</span><span class="sxs-lookup"><span data-stu-id="3992c-173">Evidence and Response</span></span>

<span data-ttu-id="3992c-174">На **вкладке Evidence and Response** показаны все поддерживаемые события и подозрительные объекты в оповещениях об инциденте.</span><span class="sxs-lookup"><span data-stu-id="3992c-174">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="3992c-175">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="3992c-175">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Пример страницы &quot;Доказательства и ответы&quot; для инцидента":::

<span data-ttu-id="3992c-177">Microsoft 365 Defender автоматически исследует все поддерживаемые инцидентами события и подозрительные объекты в оповещении, предоставляя вам сведения о важных сообщениях электронной почты, файлах, процессах, службах, IP-адресах и других.</span><span class="sxs-lookup"><span data-stu-id="3992c-177">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="3992c-178">Это позволяет быстро обнаруживать и блокировать потенциальные угрозы в инциденте.</span><span class="sxs-lookup"><span data-stu-id="3992c-178">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="3992c-179">Каждая из проанализированных сущностями отмечена приговором (Вредоносный, Подозрительный, Чистый) и состоянием исправлений.</span><span class="sxs-lookup"><span data-stu-id="3992c-179">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="3992c-180">Это поможет вам понять состояние восстановления всего инцидента и дальнейшие действия.</span><span class="sxs-lookup"><span data-stu-id="3992c-180">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="3992c-181">Graph (в предварительном просмотре)</span><span class="sxs-lookup"><span data-stu-id="3992c-181">Graph (in Preview)</span></span>

<span data-ttu-id="3992c-182">С помощью новой **вкладки Graph** (в предварительном просмотре) вы можете увидеть:</span><span class="sxs-lookup"><span data-stu-id="3992c-182">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="3992c-183">Подключение оповещений к сеяным активам в организации.</span><span class="sxs-lookup"><span data-stu-id="3992c-183">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="3992c-184">Какие сущности связаны с оповещениями и тем, как они являются частью истории атаки.</span><span class="sxs-lookup"><span data-stu-id="3992c-184">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="3992c-185">Оповещений об инциденте.</span><span class="sxs-lookup"><span data-stu-id="3992c-185">The alerts for the incident.</span></span>

<span data-ttu-id="3992c-186">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="3992c-186">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="Пример страницы Graph для инцидента":::

<span data-ttu-id="3992c-188">График инцидентов позволяет быстро понять всю область атаки, подключив различные подозрительные объекты, которые являются частью атаки, с связанными с ними активами, такими как пользователи, устройства и почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="3992c-188">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="3992c-189">Теперь вы можете понять, как атака распространилась по сети со временем, где она началась, и как далеко прошла атака.</span><span class="sxs-lookup"><span data-stu-id="3992c-189">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3992c-190">См. также</span><span class="sxs-lookup"><span data-stu-id="3992c-190">Related topics</span></span>

- [<span data-ttu-id="3992c-191">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="3992c-191">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="3992c-192">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="3992c-192">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="3992c-193">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="3992c-193">Manage incidents</span></span>](manage-incidents.md)

