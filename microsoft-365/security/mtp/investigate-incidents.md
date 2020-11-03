---
title: Исследование происшествий в защитнике Microsoft 365
description: Анализ инцидентов, связанных с устройствами, пользователями и почтовыми ящиками.
keywords: инцидент, инциденты, компьютеры, устройства, пользователи, удостоверения, почта, электронная почта, почтовый ящик, исследование, график, свидетельство
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
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846752"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="e3069-104">Исследование происшествий в защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e3069-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e3069-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e3069-105">**Applies to:**</span></span>

- <span data-ttu-id="e3069-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e3069-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e3069-107">Защитник Microsoft 365 собирает все связанные оповещения, активы, расследования и доказательства из своих устройств, пользователей и почтовых ящиков, чтобы получить исчерпывающий вид всего набора атак.</span><span class="sxs-lookup"><span data-stu-id="e3069-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="e3069-108">Расследование оповещений, затрагивающих вашу сеть, понимание их значения, сбор свидетельств, связанных с происшествиями для создания эффективного плана исправления.</span><span class="sxs-lookup"><span data-stu-id="e3069-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="e3069-109">Исследование инцидента</span><span class="sxs-lookup"><span data-stu-id="e3069-109">Investigate an incident</span></span>

1. <span data-ttu-id="e3069-110">Выберите инцидент в очереди инцидентов.</span><span class="sxs-lookup"><span data-stu-id="e3069-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="e3069-111">Откроется боковая панель, в которой приводится предварительный просмотр важной информации, такой как состояние, серьезность, категории и затронутые сущности.</span><span class="sxs-lookup"><span data-stu-id="e3069-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Изображение боковой панели инцидента](../../media/incident-side-panel.png)

2. <span data-ttu-id="e3069-113">Выберите **Открыть страницу инцидента**.</span><span class="sxs-lookup"><span data-stu-id="e3069-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="e3069-114">Откроется страница инцидента, на которой вы найдете дополнительные сведения об инциденте, комментарии и действия, а также вкладки (обзор, оповещения, устройства, пользователи, расследования, свидетельство).</span><span class="sxs-lookup"><span data-stu-id="e3069-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="e3069-115">Ознакомьтесь с информаций об оповещениях, устройствах, пользователях и других объектах, связанных с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e3069-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="e3069-116">Обзор инцидента</span><span class="sxs-lookup"><span data-stu-id="e3069-116">Incident overview</span></span>

<span data-ttu-id="e3069-117">На странице обзора содержится краткий набор основных сведений об инциденте.</span><span class="sxs-lookup"><span data-stu-id="e3069-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Изображение страницы "Обзор" инцидента](../../media/incidents-overview.png)

<span data-ttu-id="e3069-119">С помощью категорий атак вы получите визуальное и числовое представление того, как продвигается атака в цепочке аннулирования.</span><span class="sxs-lookup"><span data-stu-id="e3069-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="e3069-120">Как и в случае с другими продуктами безопасности Майкрософт, защитник Microsoft 365 выровнен по [МИТРЕ ATT&а &trade; ](https://attack.mitre.org/) Framework.</span><span class="sxs-lookup"><span data-stu-id="e3069-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="e3069-121">В разделе "Область" находится список основных ресурсов, затронутых этим инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e3069-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="e3069-122">Если есть какая-либо конкретная информация о ресурсе, например уровень риска, приоритет исследования или любые отметки ресурсов, вся эта информация также будет отображаться в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e3069-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="e3069-123">На временной шкале оповещений можно увидеть хронологический порядок оповещений, а также причины связи этих оповещений с этим инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e3069-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="e3069-124">Наконец, в разделе свидетельства приводится сводная информация о том, сколько различных артефактов входят в инцидент, и об их состоянии исправления. Благодаря этому вы сможете сразу понять, нужны ли какие-либо действия с вашей стороны.</span><span class="sxs-lookup"><span data-stu-id="e3069-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="e3069-125">Этот обзор поможет провести первоначальное рассмотрение инцидента и определить его основные характеристики, требующие внимания.</span><span class="sxs-lookup"><span data-stu-id="e3069-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="e3069-126">Оповещения</span><span class="sxs-lookup"><span data-stu-id="e3069-126">Alerts</span></span>

<span data-ttu-id="e3069-127">Вы можете просмотреть все оповещения, связанные с инцидентом, и другие сведения о них, такие как серьезность, объекты, которые участвовали в оповещении, источник оповещений (Microsoft Defender для удостоверения, защитник Майкрософт для конечной точки, защитник Майкрософт для Office 365) и причины, по которым они были связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="e3069-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Изображение страницы "Оповещения" инцидента](../../media/incident-alerts.png)

<span data-ttu-id="e3069-129">По умолчанию оповещения перечислены в хронологическом порядке, чтобы можно было сразу определить, как атака развивалась со временем.</span><span class="sxs-lookup"><span data-stu-id="e3069-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="e3069-130">При нажатии на каждое оповещение откроется соответствующая страница оповещения, на которой можно провести глубокое исследование этого оповещения.</span><span class="sxs-lookup"><span data-stu-id="e3069-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="e3069-131">Устройства</span><span class="sxs-lookup"><span data-stu-id="e3069-131">Devices</span></span>

<span data-ttu-id="e3069-132">На вкладке устройств перечислены все устройства, на которых отображаются оповещения, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e3069-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="e3069-133">Если щелкнуть название компьютера, на котором была произведена атака, откроется страница компьютера, где можно увидеть все сработавшие оповещения и связанные с ними события для удобства исследования.</span><span class="sxs-lookup"><span data-stu-id="e3069-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Изображение вкладки "Компьютеры" инцидента](../../media/incident-machines.png)

<span data-ttu-id="e3069-135">Если выбрать вкладку "Временная шкала", можно прокрутить временную шкалу компьютера и просмотреть все события и поведение на компьютере в хронологическом порядке вместе с оповещениями.</span><span class="sxs-lookup"><span data-stu-id="e3069-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="e3069-136">Пользователи</span><span class="sxs-lookup"><span data-stu-id="e3069-136">Users</span></span>

<span data-ttu-id="e3069-137">Отображение пользователей, связанных с данным инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e3069-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="e3069-138">Если щелкнуть имя пользователя, откроется страница этого пользователя в Cloud App Security, где можно провести дальнейшее исследование.</span><span class="sxs-lookup"><span data-stu-id="e3069-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Изображение вкладки "Пользователи" инцидента](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="e3069-140">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="e3069-140">Mailboxes</span></span>

<span data-ttu-id="e3069-141">Здесь отображаются почтовые ящики, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e3069-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="e3069-142">Чтобы продолжить работу, при выборе оповещения, связанного с почтой, будет открыто приложение Microsoft Defender для Office 365, в котором можно выполнить действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="e3069-142">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Изображение вкладки "Почтовый ящик" инцидента](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="e3069-144">Исследования</span><span class="sxs-lookup"><span data-stu-id="e3069-144">Investigations</span></span>

<span data-ttu-id="e3069-145">Выберите **расследования** , чтобы увидеть все автоматические расследования, инициированные оповещениями в этом инциденте.</span><span class="sxs-lookup"><span data-stu-id="e3069-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="e3069-146">Исследование выполнит действия по исправлению или дождитесь утверждения специалистом, в зависимости от того, как вы настроили автоматическое исследование действий в защитнике Майкрософт для конечной точки и защитника для Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3069-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Изображение вкладки "Исследования" инцидента](../../media/incident-investigations.png)

<span data-ttu-id="e3069-148">Выберите исследование, чтобы перейти на страницу сведений об исследовании для получения подробной информации об исследовании и о состоянии исправления.</span><span class="sxs-lookup"><span data-stu-id="e3069-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="e3069-149">Если в ходе расследования имеются какие – либо действия, ожидающие утверждения, они будут отображаться на вкладке "ожидающие действия". Выполнение действий в рамках исправления инцидентов.</span><span class="sxs-lookup"><span data-stu-id="e3069-149">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="e3069-150">Свидетельство</span><span class="sxs-lookup"><span data-stu-id="e3069-150">Evidence</span></span>

<span data-ttu-id="e3069-151">Защитник Microsoft 365 автоматически исследует все поддерживаемые события и подозрительные объекты в оповещениях, предоставляя пользователю автоматические ответы и сведения о важных файлах, процессах, службах, сообщениях электронной почты и многом другими.</span><span class="sxs-lookup"><span data-stu-id="e3069-151">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="e3069-152">Это помогает быстро обнаруживать и блокировать потенциальные угрозы в составе инцидента.</span><span class="sxs-lookup"><span data-stu-id="e3069-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Изображение вкладки "Свидетельства" инцидента](../../media/incident-evidence.png)

<span data-ttu-id="e3069-154">Для каждого проанализированного объекта принимается решение ("Вредоносный", "Подозрительный", "Чистый") и устанавливается состояние исправление.</span><span class="sxs-lookup"><span data-stu-id="e3069-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="e3069-155">Это поможет понять состояние исправления всего инцидента и последующие действия, необходимые для дальнейшего исправления.</span><span class="sxs-lookup"><span data-stu-id="e3069-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e3069-156">См. также</span><span class="sxs-lookup"><span data-stu-id="e3069-156">Related topics</span></span>

- [<span data-ttu-id="e3069-157">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="e3069-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e3069-158">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="e3069-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e3069-159">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="e3069-159">Manage incidents</span></span>](manage-incidents.md)

