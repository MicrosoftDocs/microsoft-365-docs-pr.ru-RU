---
title: Исследование устройств в списке устройств ATP Defender для защитника конечной точки
description: Изучите затронутые устройства, просмотрев оповещения, сведения о сетевом подключении, добавив теги и группы устройств и проверив состояние службы.
keywords: устройства, теги, группы, конечная точка, очередь оповещений, оповещений, имя устройства, домен, последний вид, внутренний IP, активные оповещения, категория угроз, фильтр, сортировка, проверка оповещений, сеть, подключение, тип, кража паролей, вымогателей, эксплойт, угроза, низкая серьезность, здоровье службы
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8f5415b6337d21b780a75a192a565078a6cacc06
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185735"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="405ba-104">Исследование устройств в списке Устройств конечных точек Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="405ba-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="405ba-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="405ba-105">**Applies to:**</span></span>
- [<span data-ttu-id="405ba-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="405ba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="405ba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="405ba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="405ba-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="405ba-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="405ba-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="405ba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="405ba-110">Изучите сведения о предупреждении, поднятом на определенном устройстве, чтобы определить другие действия или события, которые могут быть связаны с предупреждением или потенциальной областью нарушения.</span><span class="sxs-lookup"><span data-stu-id="405ba-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="405ba-111">В рамках процесса расследования или ответа можно собрать пакет исследований с устройства.</span><span class="sxs-lookup"><span data-stu-id="405ba-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="405ba-112">Вот как: [сбор пакета исследований с устройств.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)</span><span class="sxs-lookup"><span data-stu-id="405ba-112">Here's how: [Collect investigation package from devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="405ba-113">Вы можете щелкнуть по затронутым устройствам всякий раз, когда увидите их на портале, чтобы открыть подробный отчет об этом устройстве.</span><span class="sxs-lookup"><span data-stu-id="405ba-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="405ba-114">Затронутые устройства определены в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="405ba-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="405ba-115">Список устройств</span><span class="sxs-lookup"><span data-stu-id="405ba-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="405ba-116">Очередь оповещений</span><span class="sxs-lookup"><span data-stu-id="405ba-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="405ba-117">Панель мониторинга операций безопасности</span><span class="sxs-lookup"><span data-stu-id="405ba-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="405ba-118">Любое отдельное оповещение</span><span class="sxs-lookup"><span data-stu-id="405ba-118">Any individual alert</span></span>
- <span data-ttu-id="405ba-119">Любое представление отдельных сведений о файле</span><span class="sxs-lookup"><span data-stu-id="405ba-119">Any individual file details view</span></span>
- <span data-ttu-id="405ba-120">Представление любых IP-адресов или сведений о домене</span><span class="sxs-lookup"><span data-stu-id="405ba-120">Any IP address or domain details view</span></span>

<span data-ttu-id="405ba-121">При расследовании конкретного устройства вы увидите:</span><span class="sxs-lookup"><span data-stu-id="405ba-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="405ba-122">Сведения о устройстве</span><span class="sxs-lookup"><span data-stu-id="405ba-122">Device details</span></span>
- <span data-ttu-id="405ba-123">Действия реагирования</span><span class="sxs-lookup"><span data-stu-id="405ba-123">Response actions</span></span>
- <span data-ttu-id="405ba-124">Вкладки (обзор, оповещения, сроки, рекомендации по безопасности, инвентаризация программного обеспечения, обнаруженные уязвимости, отсутствующие ЦБ)</span><span class="sxs-lookup"><span data-stu-id="405ba-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="405ba-125">Карты (активные оповещения, зарегистрированные на пользователях, оценка безопасности)</span><span class="sxs-lookup"><span data-stu-id="405ba-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Изображение представления устройства](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="405ba-127">Сведения о устройстве</span><span class="sxs-lookup"><span data-stu-id="405ba-127">Device details</span></span>

<span data-ttu-id="405ba-128">В разделе сведения об устройстве содержится информация, например, о состоянии домена, ОС и состояния здоровья устройства.</span><span class="sxs-lookup"><span data-stu-id="405ba-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="405ba-129">Если на устройстве доступен пакет исследований, вы увидите ссылку, которая позволяет скачать пакет.</span><span class="sxs-lookup"><span data-stu-id="405ba-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="405ba-130">Действия реагирования</span><span class="sxs-lookup"><span data-stu-id="405ba-130">Response actions</span></span>

<span data-ttu-id="405ba-131">Действия ответа, которые запускают по верхней части определенной страницы устройства и включают в себя:</span><span class="sxs-lookup"><span data-stu-id="405ba-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="405ba-132">Управление тегами</span><span class="sxs-lookup"><span data-stu-id="405ba-132">Manage tags</span></span>
- <span data-ttu-id="405ba-133">Изолировать устройство</span><span class="sxs-lookup"><span data-stu-id="405ba-133">Isolate device</span></span>
- <span data-ttu-id="405ba-134">Ограничение выполнения приложения</span><span class="sxs-lookup"><span data-stu-id="405ba-134">Restrict app execution</span></span>
- <span data-ttu-id="405ba-135">Запуск антивирусного сканирования</span><span class="sxs-lookup"><span data-stu-id="405ba-135">Run antivirus scan</span></span>
- <span data-ttu-id="405ba-136">Сбор пакета расследований</span><span class="sxs-lookup"><span data-stu-id="405ba-136">Collect investigation package</span></span>
- <span data-ttu-id="405ba-137">Инициировать сеанс живого ответа</span><span class="sxs-lookup"><span data-stu-id="405ba-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="405ba-138">Инициировать автоматическое расследование</span><span class="sxs-lookup"><span data-stu-id="405ba-138">Initiate automated investigation</span></span>
- <span data-ttu-id="405ba-139">Обратитесь к эксперту по угрозам</span><span class="sxs-lookup"><span data-stu-id="405ba-139">Consult a threat expert</span></span>
- <span data-ttu-id="405ba-140">Центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="405ba-140">Action center</span></span>

<span data-ttu-id="405ba-141">Действия реагирования можно принимать в центре действий, на определенной странице устройства или на определенной странице файла.</span><span class="sxs-lookup"><span data-stu-id="405ba-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="405ba-142">Дополнительные сведения о том, как действовать на устройстве, см. в этой информации. [](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="405ba-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="405ba-143">Дополнительные сведения см. в [дополнительных сведениях о том, как исследовать объекты пользователей.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="405ba-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="405ba-144">Вкладки</span><span class="sxs-lookup"><span data-stu-id="405ba-144">Tabs</span></span>

<span data-ttu-id="405ba-145">Вкладки предоставляют соответствующие сведения о безопасности и предотвращении угроз, связанные с устройством.</span><span class="sxs-lookup"><span data-stu-id="405ba-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="405ba-146">На каждой вкладке можно настроить столбцы, которые показаны, выбрав столбцы **Customize** из панели над заголовками столбцов.</span><span class="sxs-lookup"><span data-stu-id="405ba-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="405ba-147">Обзор</span><span class="sxs-lookup"><span data-stu-id="405ba-147">Overview</span></span>
<span data-ttu-id="405ba-148">На **вкладке Обзор** отображаются [карточки](#cards) для активных оповещений, зарегистрированных в пользователях, и оценки безопасности.</span><span class="sxs-lookup"><span data-stu-id="405ba-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Изображение вкладки обзор на странице устройства](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="405ba-150">Оповещения</span><span class="sxs-lookup"><span data-stu-id="405ba-150">Alerts</span></span>

<span data-ttu-id="405ba-151">Вкладка **Alerts** содержит список оповещений, связанных с устройством.</span><span class="sxs-lookup"><span data-stu-id="405ba-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="405ba-152">Этот список является фильтрованной [](alerts-queue.md)версией очереди оповещений и показывает краткое описание оповещения, серьезности (высокая, средняя, низкая, информационная), состояния в очереди (новое, в процессе выполнения, разрешено), классификации (не установлено, ложное оповещение, истинное оповещение), состояния расследования, категории оповещения, который обращается к оповещению и последней активности.</span><span class="sxs-lookup"><span data-stu-id="405ba-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="405ba-153">Вы также можете фильтровать оповещения.</span><span class="sxs-lookup"><span data-stu-id="405ba-153">You can also filter the alerts.</span></span>

![Изображение оповещений, связанных с устройством](images/alerts-device.png)

<span data-ttu-id="405ba-155">Когда выбран значок круга слева от оповещений, появляется вылет.</span><span class="sxs-lookup"><span data-stu-id="405ba-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="405ba-156">На этой панели можно управлять оповещением и просматривать дополнительные сведения, такие как номер инцидента и связанные устройства.</span><span class="sxs-lookup"><span data-stu-id="405ba-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="405ba-157">Одновременно можно выбрать несколько оповещений.</span><span class="sxs-lookup"><span data-stu-id="405ba-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="405ba-158">Чтобы просмотреть полное представление оповещений, включая график инцидентов и дерево процессов, выберите название оповещений.</span><span class="sxs-lookup"><span data-stu-id="405ba-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="405ba-159">Временная шкала</span><span class="sxs-lookup"><span data-stu-id="405ba-159">Timeline</span></span>

<span data-ttu-id="405ba-160">Вкладка **Timeline** предоставляет хронологическое представление событий и связанных с ними оповещений, которые наблюдались на устройстве.</span><span class="sxs-lookup"><span data-stu-id="405ba-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="405ba-161">Это поможет вам соотнести все события, файлы и IP-адреса по отношению к устройству.</span><span class="sxs-lookup"><span data-stu-id="405ba-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="405ba-162">Временная шкала также позволяет выборочно сверлить события, которые произошли в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="405ba-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="405ba-163">Можно просмотреть временную последовательность событий, произошедших на устройстве за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="405ba-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="405ba-164">Для дальнейшего управления представлением можно фильтровать группы событий или настраивать столбцы.</span><span class="sxs-lookup"><span data-stu-id="405ba-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="405ba-165">Чтобы отобразить события брандмауэра, необходимо включить политику аудита, см. в статью [Подключение платформы фильтрации аудита.](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection)</span><span class="sxs-lookup"><span data-stu-id="405ba-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="405ba-166">Брандмауэр охватывает следующие события</span><span class="sxs-lookup"><span data-stu-id="405ba-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="405ba-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) — остановлена служба брандмауэра</span><span class="sxs-lookup"><span data-stu-id="405ba-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="405ba-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) — приложение, заблокированное при приеме входящих подключений в сети</span><span class="sxs-lookup"><span data-stu-id="405ba-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="405ba-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) — заблокированное подключение</span><span class="sxs-lookup"><span data-stu-id="405ba-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Изображение временной шкалы устройства с событиями](images/timeline-device.png)

<span data-ttu-id="405ba-171">Некоторые функции включают в себя:</span><span class="sxs-lookup"><span data-stu-id="405ba-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="405ba-172">Поиск определенных событий</span><span class="sxs-lookup"><span data-stu-id="405ba-172">Search for specific events</span></span>
  - <span data-ttu-id="405ba-173">Используйте панели поиска для поиска определенных событий временной шкалы.</span><span class="sxs-lookup"><span data-stu-id="405ba-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="405ba-174">Фильтрация событий с определенной даты</span><span class="sxs-lookup"><span data-stu-id="405ba-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="405ba-175">Выберите значок календаря в верхней левой части таблицы, чтобы отображать события за прошедший день, неделю, 30 дней или настраиваемый диапазон.</span><span class="sxs-lookup"><span data-stu-id="405ba-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="405ba-176">По умолчанию установлена временная шкала устройства, которая отображает события за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="405ba-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="405ba-177">Используйте временную шкалу, чтобы перейти к определенному моменту времени, выделив раздел.</span><span class="sxs-lookup"><span data-stu-id="405ba-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="405ba-178">Стрелки на временной шкале выявляют автоматизированные исследования</span><span class="sxs-lookup"><span data-stu-id="405ba-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="405ba-179">Экспорт подробных событий временной шкалы устройств</span><span class="sxs-lookup"><span data-stu-id="405ba-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="405ba-180">Экспорт временной шкалы устройства для текущей даты или определенного диапазона дат до семи дней.</span><span class="sxs-lookup"><span data-stu-id="405ba-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="405ba-181">Дополнительные сведения о некоторых событиях предоставляются в разделе **Дополнительные сведения.**</span><span class="sxs-lookup"><span data-stu-id="405ba-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="405ba-182">Эти сведения зависят от типа события, например:</span><span class="sxs-lookup"><span data-stu-id="405ba-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="405ba-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span><span class="sxs-lookup"><span data-stu-id="405ba-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="405ba-184">Обнаружена активная угроза — обнаружение угрозы произошло во время запуска угрозы.</span><span class="sxs-lookup"><span data-stu-id="405ba-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="405ba-185">Исправление не удалось — попытка устранения обнаруженной угрозы была вызвана, но не удалась</span><span class="sxs-lookup"><span data-stu-id="405ba-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="405ba-186">Исправление успешно — обнаруженная угроза была остановлена и очищена</span><span class="sxs-lookup"><span data-stu-id="405ba-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="405ba-187">Предупреждение, обходить стороной пользователя — Защитник Windows SmartScreen было отклонено и переопределено пользователем.</span><span class="sxs-lookup"><span data-stu-id="405ba-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="405ba-188">Обнаружен подозрительный скрипт — обнаружен потенциально вредоносный сценарий</span><span class="sxs-lookup"><span data-stu-id="405ba-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="405ba-189">Категория оповещений — если событие привело к генерации оповещений, предоставляется категория оповещений ("Лайтальное движение", например).</span><span class="sxs-lookup"><span data-stu-id="405ba-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="405ba-190">Сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="405ba-190">Event details</span></span>
<span data-ttu-id="405ba-191">Выберите событие, чтобы просмотреть соответствующие сведения об этом событии.</span><span class="sxs-lookup"><span data-stu-id="405ba-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="405ba-192">Панель отображает общие сведения о событиях.</span><span class="sxs-lookup"><span data-stu-id="405ba-192">A panel displays to show general event information.</span></span> <span data-ttu-id="405ba-193">Когда применимы и доступны данные, также отображается график, на котором показаны связанные сущности и их связи.</span><span class="sxs-lookup"><span data-stu-id="405ba-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="405ba-194">Чтобы дополнительно инспектировать события и связанные [](advanced-hunting-overview.md) с ними события, можно быстро выполнить расширенный запрос на охоту, выбрав **Hunt для связанных событий.**</span><span class="sxs-lookup"><span data-stu-id="405ba-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="405ba-195">Запрос возвращает выбранное событие и список других событий, произошедших примерно в одно и то же время на той же конечной точке.</span><span class="sxs-lookup"><span data-stu-id="405ba-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Изображение панели сведений о событии](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="405ba-197">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="405ba-197">Security recommendations</span></span>

<span data-ttu-id="405ba-198">**Рекомендации по безопасности создаются** в Microsoft Defender для функции управления & уязвимостей в [конечной](tvm-dashboard-insights.md) точке.</span><span class="sxs-lookup"><span data-stu-id="405ba-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="405ba-199">Выбор рекомендации покажет панель, на которой можно просмотреть соответствующие сведения, такие как описание рекомендации и потенциальные риски, связанные с ее непринятия.</span><span class="sxs-lookup"><span data-stu-id="405ba-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="405ba-200">Подробные [сведения см. в](tvm-security-recommendation.md) рекомендации по безопасности.</span><span class="sxs-lookup"><span data-stu-id="405ba-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Изображение вкладки рекомендации по безопасности](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="405ba-202">Перечень программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="405ba-202">Software inventory</span></span>

<span data-ttu-id="405ba-203">Вкладка **инвентаризации** программного обеспечения позволяет просматривать программное обеспечение на устройстве, а также любые слабые стороны или угрозы.</span><span class="sxs-lookup"><span data-stu-id="405ba-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="405ba-204">Выбор имени программного обеспечения позволит вам просмотреть рекомендации по безопасности, обнаруженные уязвимости, установленные устройства и распространение версий.</span><span class="sxs-lookup"><span data-stu-id="405ba-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="405ba-205">Сведения [о инвентаризации программного](tvm-software-inventory.md) обеспечения</span><span class="sxs-lookup"><span data-stu-id="405ba-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Изображение вкладки инвентаризации программного обеспечения](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="405ba-207">Обнаруженные уязвимости</span><span class="sxs-lookup"><span data-stu-id="405ba-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="405ba-208">На **вкладке "Обнаруженные уязвимости"** показано имя, серьезность и сведения об угрозах обнаруженных уязвимостей на устройстве.</span><span class="sxs-lookup"><span data-stu-id="405ba-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="405ba-209">При выборе определенных уязвимостей покажут описание и сведения.</span><span class="sxs-lookup"><span data-stu-id="405ba-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![Изображение вкладки обнаруженных уязвимостей](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="405ba-211">Отсутствующие KBs</span><span class="sxs-lookup"><span data-stu-id="405ba-211">Missing KBs</span></span>
<span data-ttu-id="405ba-212">На **вкладке Missing KBs** перечислены отсутствующие обновления безопасности для устройства.</span><span class="sxs-lookup"><span data-stu-id="405ba-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Изображение отсутствующих вкладок kbs](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="405ba-214">Карточки</span><span class="sxs-lookup"><span data-stu-id="405ba-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="405ba-215">Активные оповещения</span><span class="sxs-lookup"><span data-stu-id="405ba-215">Active alerts</span></span>

<span data-ttu-id="405ba-216">На **карточке Advanced Threat Protection** Azure будет отображаться высокоуровневый обзор оповещений, связанных с устройством и уровнем риска, если вы включили функцию ATP Azure и есть активные оповещений.</span><span class="sxs-lookup"><span data-stu-id="405ba-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Azure ATP feature, and there are any active alerts.</span></span> <span data-ttu-id="405ba-217">Дополнительные сведения можно получить в упражнении "Оповещение".</span><span class="sxs-lookup"><span data-stu-id="405ba-217">More information is available in the "Alerts" drill down.</span></span>

![Изображение карты активных оповещений](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="405ba-219">Необходимо включить интеграцию в Azure ATP и Defender для конечной точки, чтобы использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="405ba-219">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="405ba-220">В Defender for Endpoint вы можете включить эту функцию в расширенных функциях.</span><span class="sxs-lookup"><span data-stu-id="405ba-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="405ba-221">Дополнительные сведения о том, как включить расширенные функции, см. в дополнительных [сведениях.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="405ba-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="405ba-222">Вход в систему пользователей</span><span class="sxs-lookup"><span data-stu-id="405ba-222">Logged on users</span></span>

<span data-ttu-id="405ba-223">В **карточке** входа в систему пользователей показано, сколько пользователей вошел в систему за последние 30 дней, а также наиболее и наименее часто используемых пользователей.</span><span class="sxs-lookup"><span data-stu-id="405ba-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="405ba-224">Выбор ссылки "См. все пользователи" открывает области сведений, которая отображает сведения, такие как тип пользователя, войти в тип, и когда пользователь был первым и последним видел.</span><span class="sxs-lookup"><span data-stu-id="405ba-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="405ba-225">Дополнительные сведения см. в [дополнительных сведениях о том, как исследовать объекты пользователей.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="405ba-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Изображение области пользовательских сведений](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="405ba-227">Оценки безопасности</span><span class="sxs-lookup"><span data-stu-id="405ba-227">Security assessments</span></span>

<span data-ttu-id="405ba-228">Карта **оценки безопасности показывает** общий уровень экспозиции, рекомендации по безопасности, установленное программное обеспечение и обнаруженные уязвимости.</span><span class="sxs-lookup"><span data-stu-id="405ba-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="405ba-229">Уровень экспозиции устройства определяется совокупным воздействием ожидающих рекомендаций по безопасности.</span><span class="sxs-lookup"><span data-stu-id="405ba-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Изображение карты оценки безопасности](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="405ba-231">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="405ba-231">Related topics</span></span>

- [<span data-ttu-id="405ba-232">Просмотр и организация очереди оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="405ba-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="405ba-233">Управление оповещениями Защитника Майкрософт для конечных точек</span><span class="sxs-lookup"><span data-stu-id="405ba-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="405ba-234">Исследование оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="405ba-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="405ba-235">Исследование файла, связанного с предупреждением Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="405ba-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="405ba-236">Исследование IP-адреса, связанного с оповещением Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="405ba-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="405ba-237">Исследование домена, связанного с предупреждением Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="405ba-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="405ba-238">Исследование учетной записи пользователя в Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="405ba-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="405ba-239">Рекомендация по безопасности</span><span class="sxs-lookup"><span data-stu-id="405ba-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="405ba-240">Перечень программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="405ba-240">Software inventory</span></span>](tvm-software-inventory.md)
