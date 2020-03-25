---
title: Исследование инцидентов в Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1883f61f50dad9b601329369bf180ddecba70138
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928966"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="e952e-104">Исследование инцидентов в Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e952e-104">Investigate incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="e952e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e952e-105">**Applies to:**</span></span>

- <span data-ttu-id="e952e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e952e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e952e-107">Microsoft Threat Protection объединяет все связанные оповещения, ресурсы, расследования и свидетельства для ваших устройств, пользователей и почтовых ящиков, чтобы предоставить полную картину атаки.</span><span class="sxs-lookup"><span data-stu-id="e952e-107">Microsoft Threat Protection aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="e952e-108">Расследование оповещений, затрагивающих вашу сеть, понимание их значения, сбор свидетельств, связанных с происшествиями для создания эффективного плана исправления.</span><span class="sxs-lookup"><span data-stu-id="e952e-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="e952e-109">Исследование инцидента</span><span class="sxs-lookup"><span data-stu-id="e952e-109">Investigate an incident</span></span>

1. <span data-ttu-id="e952e-110">Выберите инцидент в очереди инцидентов.</span><span class="sxs-lookup"><span data-stu-id="e952e-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="e952e-111">Откроется боковая панель, на которой будет показана важная информация: состояние, важность, категории и затронутые объекты.</span><span class="sxs-lookup"><span data-stu-id="e952e-111">This opens a side panel and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Изображение боковой панели инцидента](../../media/incident-side-panel.png)

2. <span data-ttu-id="e952e-113">Выберите **Открыть страницу инцидента**.</span><span class="sxs-lookup"><span data-stu-id="e952e-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="e952e-114">Будет открыта страница инцидента, содержащая дополнительные сведения об инциденте, комментарии, действия и вкладки ("Обзор", "Оповещения", "Устройства", "Пользователи", "Исследования" и "Свидетельство").</span><span class="sxs-lookup"><span data-stu-id="e952e-114">This opens the incident page where you'll find more information incident details, comments and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="e952e-115">Ознакомьтесь с информаций об оповещениях, устройствах, пользователях и других объектах, связанных с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e952e-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="e952e-116">Обзор инцидента</span><span class="sxs-lookup"><span data-stu-id="e952e-116">Incident overview</span></span>

<span data-ttu-id="e952e-117">На странице обзора содержится краткий набор основных сведений об инциденте.</span><span class="sxs-lookup"><span data-stu-id="e952e-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Изображение страницы "Обзор" инцидента](../../media/incidents-overview.png)

<span data-ttu-id="e952e-119">С помощю категорий атаки можно получить наглядное и цифровое представление о том, как развивалась атака в отношении каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="e952e-119">The attack categories give you visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="e952e-120">Как и другие продукты безопасности корпорации Майкрософт, решение Microsoft Threat Protection взаимодействует с платформой [MITRE ATT&CK&trade;](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="e952e-120">As with other Microsoft security products, Microsoft Threat Protection is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="e952e-121">В разделе "Область" находится список основных ресурсов, затронутых этим инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e952e-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="e952e-122">Если есть какая-либо конкретная информация о ресурсе, например уровень риска, приоритет исследования или любые отметки ресурсов, вся эта информация также будет отображаться в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e952e-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="e952e-123">На временной шкале оповещений можно увидеть хронологический порядок оповещений, а также причины связи этих оповещений с этим инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e952e-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="e952e-124">Наконец, в разделе свидетельства приводится сводная информация о том, сколько различных артефактов входят в инцидент, и об их состоянии исправления. Благодаря этому вы сможете сразу понять, нужны ли какие-либо действия с вашей стороны.</span><span class="sxs-lookup"><span data-stu-id="e952e-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="e952e-125">Этот обзор поможет провести первоначальное рассмотрение инцидента и определить его основные характеристики, требующие внимания.</span><span class="sxs-lookup"><span data-stu-id="e952e-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="e952e-126">Оповещения</span><span class="sxs-lookup"><span data-stu-id="e952e-126">Alerts</span></span>

<span data-ttu-id="e952e-127">Вы можете просмотреть все оповещения, связанные с инцидентом, и прочую информацию об оповещениях, включая их важность, источник (Azure ATP, расширенная защита от угроз в Microsoft Defender, Office 365 ATP) и причину их объединения.</span><span class="sxs-lookup"><span data-stu-id="e952e-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Azure ATP, Microsoft Defender ATP , Office  365 ATP) and the reason they were linked together.</span></span>

![Изображение страницы "Оповещения" инцидента](../../media/incident-alerts.png)

<span data-ttu-id="e952e-129">По умолчанию оповещения перечислены в хронологическом порядке, чтобы можно было сразу определить, как атака развивалась со временем.</span><span class="sxs-lookup"><span data-stu-id="e952e-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="e952e-130">Если щелкнуть каждое оповещение, откроется страница соответствующего оповещения с подробной информацией.</span><span class="sxs-lookup"><span data-stu-id="e952e-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="e952e-131">Устройства</span><span class="sxs-lookup"><span data-stu-id="e952e-131">Devices</span></span>

<span data-ttu-id="e952e-132">На вкладке устройств перечислены все устройства, на которых отображаются оповещения, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e952e-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="e952e-133">Если щелкнуть название компьютера, на котором была произведена атака, откроется страница компьютера, где можно увидеть все сработавшие оповещения и связанные с ними события для удобства исследования.</span><span class="sxs-lookup"><span data-stu-id="e952e-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Изображение вкладки "Компьютеры" инцидента](../../media/incident-machines.png)

<span data-ttu-id="e952e-135">Если выбрать вкладку "Временная шкала", можно прокрутить временную шкалу компьютера и просмотреть все события и поведение на компьютере в хронологическом порядке вместе с оповещениями.</span><span class="sxs-lookup"><span data-stu-id="e952e-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="e952e-136">Пользователи</span><span class="sxs-lookup"><span data-stu-id="e952e-136">Users</span></span>

<span data-ttu-id="e952e-137">Отображение пользователей, связанных с данным инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e952e-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="e952e-138">Если щелкнуть имя пользователя, откроется страница этого пользователя в Cloud App Security, где можно провести дальнейшее исследование.</span><span class="sxs-lookup"><span data-stu-id="e952e-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Изображение вкладки "Пользователи" инцидента](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="e952e-140">Почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="e952e-140">Mailboxes</span></span>

<span data-ttu-id="e952e-141">Здесь отображаются почтовые ящики, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="e952e-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="e952e-142">Если нужно провести углубленное исследование, выберите оповещение, связанное с почтой: откроется решение Office 365 Advanced Threat Protection, где можно выполнить действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="e952e-142">To do further investigative work, selecting the mail related alert will open Office 365 Advanced Threat Protection where you can take remediation actions.</span></span>

![Изображение вкладки "Почтовый ящик" инцидента](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="e952e-144">Исследования</span><span class="sxs-lookup"><span data-stu-id="e952e-144">Investigations</span></span>

<span data-ttu-id="e952e-145">Выберите **расследования** , чтобы увидеть все автоматические расследования, инициированные оповещениями в этом инциденте.</span><span class="sxs-lookup"><span data-stu-id="e952e-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="e952e-146">В зависимости от настройки автоматических исследований в Microsoft Defender ATP и Office 365 Advanced Threat Protection исследования выполнят действия исправления или будут ожидать утверждения этих действий аналитиком.</span><span class="sxs-lookup"><span data-stu-id="e952e-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender ATP and Office 365 Advanced Threat Protection.</span></span>

![Изображение вкладки "Исследования" инцидента](../../media/incident-investigations.png)

<span data-ttu-id="e952e-148">Выберите исследование, чтобы перейти на страницу сведений об исследовании для получения подробной информации об исследовании и о состоянии исправления.</span><span class="sxs-lookup"><span data-stu-id="e952e-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="e952e-149">Если в ходе исследования есть какие-либо действия, ожидающие утверждения, они будут отображаться на вкладке "Ожидающие выполнения действия". Можно выполнить действие в составе исправления инцидента.</span><span class="sxs-lookup"><span data-stu-id="e952e-149">If there are any actions pending for approval as part of the investigation they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="e952e-150">Свидетельство</span><span class="sxs-lookup"><span data-stu-id="e952e-150">Evidence</span></span>

<span data-ttu-id="e952e-151">Microsoft Threat Protection автоматически исследует все поддерживаемые события и подозрительные объекты в оповещениях, предоставляет автоматические ответы и информацию о важных файлах, процессах, службах, сообщениях электронной почты и т. д.</span><span class="sxs-lookup"><span data-stu-id="e952e-151">Microsoft Threat Protection automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with auto-response and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="e952e-152">Это помогает быстро обнаруживать и блокировать потенциальные угрозы в составе инцидента.</span><span class="sxs-lookup"><span data-stu-id="e952e-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Изображение вкладки "Свидетельства" инцидента](../../media/incident-evidence.png)

<span data-ttu-id="e952e-154">Для каждого проанализированного объекта принимается решение ("Вредоносный", "Подозрительный", "Чистый") и устанавливается состояние исправление.</span><span class="sxs-lookup"><span data-stu-id="e952e-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="e952e-155">Это поможет понять состояние исправления всего инцидента и последующие действия, необходимые для дальнейшего исправления.</span><span class="sxs-lookup"><span data-stu-id="e952e-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e952e-156">См. также</span><span class="sxs-lookup"><span data-stu-id="e952e-156">Related topics</span></span>

- [<span data-ttu-id="e952e-157">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="e952e-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e952e-158">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="e952e-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e952e-159">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="e952e-159">Manage incidents</span></span>](manage-incidents.md)

