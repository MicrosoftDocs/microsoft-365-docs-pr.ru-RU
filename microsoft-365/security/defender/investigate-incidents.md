---
title: Расследование инцидентов в Microsoft 365 Defender
description: Анализ инцидентов, связанных с устройствами, пользователями и почтовыми ящиками.
keywords: инцидент, инциденты, компьютеры, устройства, пользователи, удостоверения, почта, электронная почта, почтовый ящик, исследование, график, свидетельство
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
ms.openlocfilehash: a6c7e7e920d18d9d8bf29d71d317008ea0c37bbf
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592100"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="f26ba-104">Расследование инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f26ba-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f26ba-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f26ba-105">**Applies to:**</span></span>

- <span data-ttu-id="f26ba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f26ba-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f26ba-107">Microsoft 365 Defender агрегирует все связанные оповещения, активы, расследования и доказательства на всех устройствах, пользователях и почтовых ящиках, чтобы получить полный обзор всей ширины атаки.</span><span class="sxs-lookup"><span data-stu-id="f26ba-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="f26ba-108">Расследование оповещений, затрагивающих вашу сеть, понимание их значения, сбор свидетельств, связанных с происшествиями для создания эффективного плана исправления.</span><span class="sxs-lookup"><span data-stu-id="f26ba-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="f26ba-109">Исследование инцидента</span><span class="sxs-lookup"><span data-stu-id="f26ba-109">Investigate an incident</span></span>

1. <span data-ttu-id="f26ba-110">Выберите инцидент в очереди инцидентов.</span><span class="sxs-lookup"><span data-stu-id="f26ba-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="f26ba-111">Боковая панель открывает и предоставляет предварительный просмотр важных сведений, таких как состояние, серьезность, категории и пострадавшие сущности.</span><span class="sxs-lookup"><span data-stu-id="f26ba-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Изображение боковой панели инцидента](../../media/incident-side-panel.png)

2. <span data-ttu-id="f26ba-113">Выберите **Открыть страницу инцидента**.</span><span class="sxs-lookup"><span data-stu-id="f26ba-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="f26ba-114">Это открывает страницу инцидента, на которой вы найдете дополнительные сведения об инцидентах, комментариях и действиях, вкладки (обзор, оповещения, устройства, пользователи, расследования, доказательства).</span><span class="sxs-lookup"><span data-stu-id="f26ba-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="f26ba-115">Ознакомьтесь с информаций об оповещениях, устройствах, пользователях и других объектах, связанных с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="f26ba-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="f26ba-116">Обзор инцидента</span><span class="sxs-lookup"><span data-stu-id="f26ba-116">Incident overview</span></span>

<span data-ttu-id="f26ba-117">На странице обзора содержится краткий набор основных сведений об инциденте.</span><span class="sxs-lookup"><span data-stu-id="f26ba-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Изображение страницы "Обзор" инцидента](../../media/incidents-overview.png)

<span data-ttu-id="f26ba-119">Категории атак дают визуальное и числовую представление о том, как продвинулась атака в отношении цепочки убийств.</span><span class="sxs-lookup"><span data-stu-id="f26ba-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="f26ba-120">Как и другие продукты безопасности Майкрософт, Microsoft 365 Defender соответствует структуре [ATT MITRE&&trade; CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="f26ba-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="f26ba-121">В разделе "Область" находится список основных ресурсов, затронутых этим инцидентом.</span><span class="sxs-lookup"><span data-stu-id="f26ba-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="f26ba-122">Если есть какая-либо конкретная информация о ресурсе, например уровень риска, приоритет исследования или любые отметки ресурсов, вся эта информация также будет отображаться в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f26ba-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="f26ba-123">На временной шкале оповещений можно увидеть хронологический порядок оповещений, а также причины связи этих оповещений с этим инцидентом.</span><span class="sxs-lookup"><span data-stu-id="f26ba-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="f26ba-124">Наконец, в разделе свидетельства приводится сводная информация о том, сколько различных артефактов входят в инцидент, и об их состоянии исправления. Благодаря этому вы сможете сразу понять, нужны ли какие-либо действия с вашей стороны.</span><span class="sxs-lookup"><span data-stu-id="f26ba-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="f26ba-125">Этот обзор поможет провести первоначальное рассмотрение инцидента и определить его основные характеристики, требующие внимания.</span><span class="sxs-lookup"><span data-stu-id="f26ba-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="f26ba-126">Оповещения</span><span class="sxs-lookup"><span data-stu-id="f26ba-126">Alerts</span></span>

<span data-ttu-id="f26ba-127">Вы можете просмотреть все оповещения, связанные с инцидентом, и другие сведения о них, такие как серьезность, объекты, которые были вовлечены в оповещение, источник оповещений (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) и причину их связи.</span><span class="sxs-lookup"><span data-stu-id="f26ba-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Изображение страницы "Оповещения" инцидента](../../media/incident-alerts.png)

<span data-ttu-id="f26ba-129">По умолчанию оповещения перечислены в хронологическом порядке, чтобы можно было сразу определить, как атака развивалась со временем.</span><span class="sxs-lookup"><span data-stu-id="f26ba-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="f26ba-130">Нажатие на каждое оповещение приведет вас к соответствующей странице оповещения, на которой можно провести углубленное исследование этого оповещения.</span><span class="sxs-lookup"><span data-stu-id="f26ba-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="f26ba-131">Узнайте, как использовать страницы оповещений и единую очередь оповещения в [расследовании оповещений](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f26ba-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="f26ba-132">Устройства</span><span class="sxs-lookup"><span data-stu-id="f26ba-132">Devices</span></span>

<span data-ttu-id="f26ba-133">На вкладке устройств перечислены все устройства, на которых отображаются оповещения, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="f26ba-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="f26ba-134">Если щелкнуть название компьютера, на котором была произведена атака, откроется страница компьютера, где можно увидеть все сработавшие оповещения и связанные с ними события для удобства исследования.</span><span class="sxs-lookup"><span data-stu-id="f26ba-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Изображение вкладки "Компьютеры" инцидента](../../media/incident-machines.png)

<span data-ttu-id="f26ba-136">Если выбрать вкладку "Временная шкала", можно прокрутить временную шкалу компьютера и просмотреть все события и поведение на компьютере в хронологическом порядке вместе с оповещениями.</span><span class="sxs-lookup"><span data-stu-id="f26ba-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="f26ba-137">Вы можете делать проверки по запросу на странице устройства.</span><span class="sxs-lookup"><span data-stu-id="f26ba-137">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="f26ba-138">В центре безопасности Microsoft 365 выберите **инвентаризацию устройств.**</span><span class="sxs-lookup"><span data-stu-id="f26ba-138">In the Microsoft 365 security center, choose **Device inventory**.</span></span> <span data-ttu-id="f26ba-139">Выберите устройство с оповещениями, а затем запустите антивирусное сканирование.</span><span class="sxs-lookup"><span data-stu-id="f26ba-139">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="f26ba-140">Действия, например антивирусное сканирование, отслеживаются и видны на странице **инвентаризации** устройств.</span><span class="sxs-lookup"><span data-stu-id="f26ba-140">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="f26ba-141">Дополнительные дополнительные результаты см. в [веб-сайте Run Microsoft Defender Antivirus scan on devices.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)</span><span class="sxs-lookup"><span data-stu-id="f26ba-141">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>


## <a name="users"></a><span data-ttu-id="f26ba-142">Пользователи</span><span class="sxs-lookup"><span data-stu-id="f26ba-142">Users</span></span>

<span data-ttu-id="f26ba-143">Отображение пользователей, связанных с данным инцидентом.</span><span class="sxs-lookup"><span data-stu-id="f26ba-143">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="f26ba-144">Если щелкнуть имя пользователя, откроется страница этого пользователя в Cloud App Security, где можно провести дальнейшее исследование.</span><span class="sxs-lookup"><span data-stu-id="f26ba-144">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Изображение вкладки "Пользователи" инцидента](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="f26ba-146">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="f26ba-146">Mailboxes</span></span>

<span data-ttu-id="f26ba-147">Здесь отображаются почтовые ящики, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="f26ba-147">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="f26ba-148">Для дальнейших следственных действий выбор оповещения, связанного с почтой, откроет Microsoft Defender для Office 365, где можно принять меры по исправлению.</span><span class="sxs-lookup"><span data-stu-id="f26ba-148">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Изображение вкладки "Почтовый ящик" инцидента](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="f26ba-150">Исследования</span><span class="sxs-lookup"><span data-stu-id="f26ba-150">Investigations</span></span>

<span data-ttu-id="f26ba-151">Выберите **исследование,** чтобы увидеть все автоматические расследования, инициированные оповещениями в этом инциденте.</span><span class="sxs-lookup"><span data-stu-id="f26ba-151">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="f26ba-152">Расследования будут выполнять действия по исправлению или ждать утверждения действий аналитиком в зависимости от настройки автоматических расследований для выполнения в Microsoft Defender для конечной точки и Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="f26ba-152">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Изображение вкладки "Исследования" инцидента](../../media/incident-investigations.png)

<span data-ttu-id="f26ba-154">Выберите исследование, чтобы перейти на страницу сведений об исследовании для получения подробной информации об исследовании и о состоянии исправления.</span><span class="sxs-lookup"><span data-stu-id="f26ba-154">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="f26ba-155">Если в рамках расследования ожидаются какие-либо действия, ожидающих утверждения, они будут отображаться на вкладке Ожидающих действий. Примите меры в рамках устранения инцидентов.</span><span class="sxs-lookup"><span data-stu-id="f26ba-155">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="f26ba-156">Свидетельство</span><span class="sxs-lookup"><span data-stu-id="f26ba-156">Evidence</span></span>

<span data-ttu-id="f26ba-157">Microsoft 365 Defender автоматически исследует все поддерживаемые инцидентами события и подозрительные объекты в оповещении, предоставляя автоответчи и сведения о важных файлах, процессах, службах, электронных письмах и других.</span><span class="sxs-lookup"><span data-stu-id="f26ba-157">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="f26ba-158">Это помогает быстро обнаруживать и блокировать потенциальные угрозы в составе инцидента.</span><span class="sxs-lookup"><span data-stu-id="f26ba-158">This helps quickly detect and block potential threats in the incident.</span></span>

![Изображение вкладки "Свидетельства" инцидента](../../media/incident-evidence.png)

<span data-ttu-id="f26ba-160">Для каждого проанализированного объекта принимается решение ("Вредоносный", "Подозрительный", "Чистый") и устанавливается состояние исправление.</span><span class="sxs-lookup"><span data-stu-id="f26ba-160">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="f26ba-161">Это поможет понять состояние исправления всего инцидента и последующие действия, необходимые для дальнейшего исправления.</span><span class="sxs-lookup"><span data-stu-id="f26ba-161">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f26ba-162">См. также</span><span class="sxs-lookup"><span data-stu-id="f26ba-162">Related topics</span></span>

- [<span data-ttu-id="f26ba-163">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="f26ba-163">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f26ba-164">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="f26ba-164">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="f26ba-165">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="f26ba-165">Manage incidents</span></span>](manage-incidents.md)

