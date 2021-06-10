---
title: Центр безопасности в Microsoft Defender Панель мониторинга операций безопасности
description: Используйте панель мониторинга для определения устройств, на которых существует риск, отслеживания состояния службы, а также для получения статистики и сведений о устройствах и оповещениях.
keywords: панель мониторинга, оповещений, новые, в процессе выполнения, разрешенные, риск, устройства в опасности, инфекции, отчеты, статистика, диаграммы, графики, здоровье, активные обнаружения вредоносных программ, категория угроз, категории, похититель паролей, вымогателей, эксплойт, угроза, низкая серьезность, активная вредоносная программа
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072950"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="b5d0d-104">Центр безопасности в Microsoft Defender Панель мониторинга операций безопасности</span><span class="sxs-lookup"><span data-stu-id="b5d0d-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b5d0d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b5d0d-105">**Applies to:**</span></span>
- [<span data-ttu-id="b5d0d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b5d0d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="b5d0d-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b5d0d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5d0d-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="b5d0d-109">Панель **мониторинга операций** безопасности — это обнаружение и нейтрализация атак на конечные точки возможности.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="b5d0d-110">Он предоставляет обзор на высоком уровне, где были замечены обнаружения, и основные моменты, в которых необходимы действия реагирования.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="b5d0d-111">Панель мониторинга отображает снимок:</span><span class="sxs-lookup"><span data-stu-id="b5d0d-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="b5d0d-112">Активные оповещения</span><span class="sxs-lookup"><span data-stu-id="b5d0d-112">Active alerts</span></span>
- <span data-ttu-id="b5d0d-113">Устройства в опасности</span><span class="sxs-lookup"><span data-stu-id="b5d0d-113">Devices at risk</span></span>
- <span data-ttu-id="b5d0d-114">Здоровье датчика</span><span class="sxs-lookup"><span data-stu-id="b5d0d-114">Sensor health</span></span>
- <span data-ttu-id="b5d0d-115">Работоспособность службы</span><span class="sxs-lookup"><span data-stu-id="b5d0d-115">Service health</span></span>
- <span data-ttu-id="b5d0d-116">Ежедневные отчеты о устройствах</span><span class="sxs-lookup"><span data-stu-id="b5d0d-116">Daily devices reporting</span></span>
- <span data-ttu-id="b5d0d-117">Активные автоматизированные исследования</span><span class="sxs-lookup"><span data-stu-id="b5d0d-117">Active automated investigations</span></span>
- <span data-ttu-id="b5d0d-118">Статистика автоматизированных расследований</span><span class="sxs-lookup"><span data-stu-id="b5d0d-118">Automated investigations statistics</span></span>
- <span data-ttu-id="b5d0d-119">Пользователи в опасности</span><span class="sxs-lookup"><span data-stu-id="b5d0d-119">Users at risk</span></span>
- <span data-ttu-id="b5d0d-120">Подозрительные действия</span><span class="sxs-lookup"><span data-stu-id="b5d0d-120">Suspicious activities</span></span>


![Панель мониторинга операций безопасности](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="b5d0d-122">Вы можете исследовать и исследовать оповещения и устройства, чтобы быстро определить, если, где и когда в вашей сети произошли подозрительные действия, чтобы помочь вам понять контекст, в котором они появились.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="b5d0d-123">На панели **мониторинга операций безопасности** вы увидите агрегированные события, облегчающие идентификацию важных событий или поведения на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="b5d0d-124">Вы также можете сверлить детализацию событий и низкоуровневых индикаторов.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="b5d0d-125">Он также имеет щелкаемые плитки, которые дают визуальные сигналы об общем состоянии здоровья вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="b5d0d-126">Каждая плитка открывает подробное представление соответствующего обзора.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="b5d0d-127">Активные оповещения</span><span class="sxs-lookup"><span data-stu-id="b5d0d-127">Active alerts</span></span>
<span data-ttu-id="b5d0d-128">Общее число активных оповещений за последние 30 дней в сети можно просмотреть из плитки.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="b5d0d-129">Оповещений сгруппировать в **новые и** **в процессе**.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-129">Alerts are grouped into **New** and **In progress**.</span></span>

![Щелкните каждый срез или серьезность, чтобы увидеть список оповещений за последние 30 дней](images/active-alerts-tile.png)

<span data-ttu-id="b5d0d-131">Каждая группа дополнительно классифицируются в соответствующие уровни серьезности оповещений.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="b5d0d-132">Щелкните число оповещений внутри каждого кольца оповещения, чтобы просмотреть сортировку очереди этой категории **(New** или **In progress).**</span><span class="sxs-lookup"><span data-stu-id="b5d0d-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="b5d0d-133">Дополнительные сведения см. в [обзоре Оповещений.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="b5d0d-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="b5d0d-134">Каждая строка содержит категорию серьезности оповещений и краткое описание оповещения.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="b5d0d-135">Вы можете щелкнуть оповещение, чтобы просмотреть его подробное представление.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="b5d0d-136">Дополнительные сведения см. в обзоре Обзор оповещений и оповещений [Microsoft Defender для конечных](investigate-alerts.md) [точек.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="b5d0d-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="b5d0d-137">Устройства в опасности</span><span class="sxs-lookup"><span data-stu-id="b5d0d-137">Devices at risk</span></span>
<span data-ttu-id="b5d0d-138">На этой плитке показан список устройств с самым большим количеством активных оповещений.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="b5d0d-139">Общее число оповещений для каждого устройства отображается в круге рядом с именем устройства, а затем далее классифицируются по уровням серьезности в дальнем конце плитки (наведите курсор на каждую планку серьезности, чтобы увидеть его метку).</span><span class="sxs-lookup"><span data-stu-id="b5d0d-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![Плитка Устройств с риском показывает список устройств с самым большим числом оповещений и разбивку серьезности оповещений](images/devices-at-risk-tile.png)

<span data-ttu-id="b5d0d-141">Щелкните имя устройства, чтобы узнать подробности об этом устройстве.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="b5d0d-142">Дополнительные сведения см. в [списке Microsoft Defender for Endpoint Devices.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="b5d0d-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="b5d0d-143">Вы также можете щелкнуть список **Устройств** в верхней части плитки, чтобы перейти непосредственно к списку **Устройств,** отсортировали по количеству активных оповещений.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="b5d0d-144">Дополнительные сведения см. в [списке Microsoft Defender for Endpoint Devices.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="b5d0d-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="b5d0d-145">Устройства с сенсорными вопросами</span><span class="sxs-lookup"><span data-stu-id="b5d0d-145">Devices with sensor issues</span></span>
<span data-ttu-id="b5d0d-146">Плитка **Устройств с проблемными** датчиками предоставляет сведения о способности отдельного устройства предоставлять данные датчиков службе Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="b5d0d-147">Он сообщает, сколько устройств требует внимания и помогает выявлять проблемные устройства.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![Устройства с плиткой проблем с датчиками](images/atp-tile-sensor-health.png)

<span data-ttu-id="b5d0d-149">Существует два индикатора состояния, которые предоставляют сведения о количестве устройств, которые должным образом не сообщаются службе:</span><span class="sxs-lookup"><span data-stu-id="b5d0d-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="b5d0d-150">**Неправильное** представление — эти устройства могут частично сообщать данные датчиков службе Microsoft Defender для конечных точек и могут иметь ошибки конфигурации, которые необходимо исправить.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="b5d0d-151">**Неактивные** устройства, которые перестали отчитываться в службе Microsoft Defender для конечных точек более семи дней в прошлом месяце.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="b5d0d-152">При нажатии любой из групп вы будете направлены в список устройств, отфильтрованный в соответствии с вашим выбором.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="b5d0d-153">Дополнительные сведения см. в [дополнительных сведениях, которые см.](check-sensor-status.md) в "Проверить состояние датчика" и ["Исследовать устройства".](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="b5d0d-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="b5d0d-154">Работоспособность службы</span><span class="sxs-lookup"><span data-stu-id="b5d0d-154">Service health</span></span>
<span data-ttu-id="b5d0d-155">Плитка **здоровья** службы информирует вас о том, активна ли служба или есть ли проблемы.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![На плитке здоровья Службы показан общий индикатор службы](images/status-tile.png)

<span data-ttu-id="b5d0d-157">Дополнительные сведения о состоянии службы см. в [веб-сайте Check the Microsoft Defender for Endpoint service health.](service-status.md)</span><span class="sxs-lookup"><span data-stu-id="b5d0d-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="b5d0d-158">Ежедневные отчеты о устройствах</span><span class="sxs-lookup"><span data-stu-id="b5d0d-158">Daily devices reporting</span></span>
<span data-ttu-id="b5d0d-159">Плитка **отчетов** о ежедневных устройствах отображает диаграмму панели, которая представляет количество устройств, ежедневно сообщая о них за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="b5d0d-160">Наведите курсор над отдельными барами на графике, чтобы увидеть точное число устройств, сообщаящих в каждый день.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![Изображение плитки ежедневных устройств, сообщая о них](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="b5d0d-162">Активные автоматизированные исследования</span><span class="sxs-lookup"><span data-stu-id="b5d0d-162">Active automated investigations</span></span>
<span data-ttu-id="b5d0d-163">Общее число автоматических расследований за последние 30 дней в сети можно просмотреть из плитки **Active automated investigations.**</span><span class="sxs-lookup"><span data-stu-id="b5d0d-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="b5d0d-164">Исследования сгруппировали в **Ожидающее действие,** **ожидание устройства** и **запуск.**</span><span class="sxs-lookup"><span data-stu-id="b5d0d-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![Inmage of active automated investigations](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="b5d0d-166">Статистика автоматизированных расследований</span><span class="sxs-lookup"><span data-stu-id="b5d0d-166">Automated investigations statistics</span></span>
<span data-ttu-id="b5d0d-167">На этой плитке показана статистика, связанная с автоматическими расследованиями за последние семь дней.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="b5d0d-168">В нем показано количество завершенных расследований, количество успешно исправленных расследований, среднее время ожидания, необходимое для начала расследования, среднее время, необходимое для устранения оповещений, количество исследованных оповещений и количество часов автоматизации, сэкономленных при обычном ручном расследовании.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![Изображение статистики автоматизированных расследований](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="b5d0d-170">Вы можете **щелкнуть** по автоматическим расследованиям,  исправленным расследованиям и оповещений, исследуемой для перемещения на страницу **Исследования,** фильтруемую соответствующей категорией.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="b5d0d-171">Это позволяет увидеть подробный анализ расследований в контексте.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="b5d0d-172">Пользователи в опасности</span><span class="sxs-lookup"><span data-stu-id="b5d0d-172">Users at risk</span></span>
<span data-ttu-id="b5d0d-173">На плитке показан список учетных записей пользователей с наиболее активными оповещений и количество оповещений высокого, среднего или низкого уровня оповещений.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![Учетные записи пользователей в плитке риска показывают список учетных записей пользователей с самым большим числом оповещений и разбивкой серьезности оповещений](images/atp-users-at-risk.png)

<span data-ttu-id="b5d0d-175">Щелкните учетную запись пользователя, чтобы узнать подробности об учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="b5d0d-176">Дополнительные сведения см. [в дополнительных сведениях: Исследование учетной записи пользователя.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="b5d0d-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="b5d0d-177">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b5d0d-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5d0d-178">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b5d0d-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="b5d0d-179">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b5d0d-179">Related topics</span></span>
- [<span data-ttu-id="b5d0d-180">Понимание портала Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="b5d0d-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="b5d0d-181">Обзор портала</span><span class="sxs-lookup"><span data-stu-id="b5d0d-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="b5d0d-182">Просмотр панели управления & уязвимостей</span><span class="sxs-lookup"><span data-stu-id="b5d0d-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="b5d0d-183">Просмотр панели мониторинга аналитики угроз и рекомендуемые действия по смягчению последствий</span><span class="sxs-lookup"><span data-stu-id="b5d0d-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
