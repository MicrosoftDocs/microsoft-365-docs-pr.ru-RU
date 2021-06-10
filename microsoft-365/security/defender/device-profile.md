---
title: Профиль устройства на Microsoft 365 портале безопасности
description: Просмотр уровней риска и экспозиции для устройства в организации. Анализ прошлых и нынешних угроз и защита устройства с помощью последних обновлений.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, Microsoft 365 Defender, центр безопасности, Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Defender для identity, страница устройства, профиль устройства, страница машины, профиль машины
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 8e2788fd9163a27b41bd3788facf5fc9623b0543
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935669"
---
# <a name="device-profile-page"></a><span data-ttu-id="b5686-105">Страница профиля устройства</span><span class="sxs-lookup"><span data-stu-id="b5686-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b5686-106">Портал Microsoft 365 безопасности предоставляет страницы профилей устройств, чтобы можно было быстро оценить состояние и состояние устройств в сети.</span><span class="sxs-lookup"><span data-stu-id="b5686-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5686-107">Страница профиля устройства может отображаться несколько иначе в зависимости от того, зарегистрировано ли устройство в Microsoft Defender for Endpoint, Microsoft Defender for Identity или в обеих.</span><span class="sxs-lookup"><span data-stu-id="b5686-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="b5686-108">Если устройство зарегистрировали в Microsoft Defender для конечной точки, вы также можете использовать страницу профиля устройства для выполнения некоторых общих задач безопасности.</span><span class="sxs-lookup"><span data-stu-id="b5686-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="b5686-109">Навигация по странице профиля устройства</span><span class="sxs-lookup"><span data-stu-id="b5686-109">Navigating the device profile page</span></span>

<span data-ttu-id="b5686-110">Страница профиля разбита на несколько широких разделов.</span><span class="sxs-lookup"><span data-stu-id="b5686-110">The profile page is broken up into several broad sections.</span></span>

![Изображение страницы профиля устройства с областью (1) Tab (2) боковой панели и (3) Действия выделены красным цветом](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="b5686-112">На боковой панели (1) перечислены основные сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="b5686-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="b5686-113">Основная область контента (2) содержит вкладки, которые можно перенабежка, чтобы просмотреть различные виды информации об устройстве.</span><span class="sxs-lookup"><span data-stu-id="b5686-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="b5686-114">Если устройство зарегистрировали в Microsoft Defender для конечной точки, вы также увидите список ответных действий (3).</span><span class="sxs-lookup"><span data-stu-id="b5686-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="b5686-115">Действия реагирования позволяют выполнять общие задачи, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="b5686-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="b5686-116">Боковая панель</span><span class="sxs-lookup"><span data-stu-id="b5686-116">Sidebar</span></span>

<span data-ttu-id="b5686-117">Рядом с основной областью контента страницы профиля устройства является боковая панель.</span><span class="sxs-lookup"><span data-stu-id="b5686-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Изображение вкладки боковой панели для профиля устройства](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="b5686-119">На боковой панели перечислены полное имя и уровень экспозиции устройства.</span><span class="sxs-lookup"><span data-stu-id="b5686-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="b5686-120">В нем также содержится ряд важных базовых сведений в небольших подсекциях, которые можно торгуть открытыми или закрытыми, например:</span><span class="sxs-lookup"><span data-stu-id="b5686-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="b5686-121">**Теги** — любой защитник Майкрософт для конечной точки, защитник Майкрософт для удостоверений или пользовательские теги, связанные с устройством.</span><span class="sxs-lookup"><span data-stu-id="b5686-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="b5686-122">Теги из Microsoft Defender для identity не редактируемы.</span><span class="sxs-lookup"><span data-stu-id="b5686-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="b5686-123">**Сведения о безопасности** . Открытые инциденты и активные оповещения.</span><span class="sxs-lookup"><span data-stu-id="b5686-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="b5686-124">Устройства, зарегистрированные в Microsoft Defender для конечной точки, также будут отображать уровень экспозиции и уровень риска.</span><span class="sxs-lookup"><span data-stu-id="b5686-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="b5686-125">Уровень экспозиции зависит от того, насколько устройство соответствует рекомендациям по безопасности, а уровень риска рассчитывается на основе ряда факторов, включая типы и серьезность активных оповещений.</span><span class="sxs-lookup"><span data-stu-id="b5686-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="b5686-126">**Сведения об** устройстве — домен, ОС, период времени, когда устройство было впервые замечено, IP-адреса, ресурсы.</span><span class="sxs-lookup"><span data-stu-id="b5686-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="b5686-127">Устройства, зарегистрированные в Microsoft Defender для конечной точки, также отображают состояние здоровья.</span><span class="sxs-lookup"><span data-stu-id="b5686-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="b5686-128">Устройства, зарегистрированные в Microsoft Defender for Identity, будут отображать имя пользователя и время создания устройства.</span><span class="sxs-lookup"><span data-stu-id="b5686-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="b5686-129">**Сетевое действие** — в первый раз и последний раз устройство было замечено в сети.</span><span class="sxs-lookup"><span data-stu-id="b5686-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="b5686-130">**Данные каталога** (только для устройств, зарегистрированных в *Microsoft Defender for Identity)*— флаги [UAC,](/windows/security/identity-protection/user-account-control/user-account-control-overview) [spNs](/windows/win32/ad/service-principal-names)и членство в группах.</span><span class="sxs-lookup"><span data-stu-id="b5686-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="b5686-131">Действия реагирования</span><span class="sxs-lookup"><span data-stu-id="b5686-131">Response actions</span></span>

<span data-ttu-id="b5686-132">Действия реагирования предоставляют быстрый способ защиты от угроз и анализа.</span><span class="sxs-lookup"><span data-stu-id="b5686-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Изображение панели действий для профиля устройства](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="b5686-134">[Действия реагирования](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) доступны только в том случае, если устройство зарегистрировали в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b5686-134">[Response actions](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="b5686-135">Устройства, зарегистрированные в Microsoft Defender для конечной точки, могут отображать различные числа ответных действий в зависимости от оси устройства и номера версии.</span><span class="sxs-lookup"><span data-stu-id="b5686-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="b5686-136">Действия, доступные на странице профиля устройства, включают:</span><span class="sxs-lookup"><span data-stu-id="b5686-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="b5686-137">**Управление тегами** . Обновляет пользовательские теги, примененные к этому устройству.</span><span class="sxs-lookup"><span data-stu-id="b5686-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="b5686-138">**Изолировать устройство** — изолирует устройство от сети организации, сохраняя его подключенным к Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b5686-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b5686-139">Вы можете разрешить Outlook, Teams и Skype для бизнеса, пока устройство изолировано, в целях связи.</span><span class="sxs-lookup"><span data-stu-id="b5686-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="b5686-140">**Центр действий** — просмотр состояния отправленных действий.</span><span class="sxs-lookup"><span data-stu-id="b5686-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="b5686-141">Доступно только в том случае, если уже выбрано другое действие.</span><span class="sxs-lookup"><span data-stu-id="b5686-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="b5686-142">**Ограничение выполнения приложения** — предотвращает запуск приложений, не подписанных Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b5686-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="b5686-143">**Запуск антивирусной проверки** — обновления антивирусная программа определений и немедленно выполняется антивирусное сканирование.</span><span class="sxs-lookup"><span data-stu-id="b5686-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="b5686-144">Выберите между быстрым сканированием или полным сканированием.</span><span class="sxs-lookup"><span data-stu-id="b5686-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="b5686-145">**Сбор пакета исследований** — сбор сведений об устройстве.</span><span class="sxs-lookup"><span data-stu-id="b5686-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="b5686-146">По завершению расследования его можно скачать.</span><span class="sxs-lookup"><span data-stu-id="b5686-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="b5686-147">**Инициировать сеанс живого ответа** — загружает удаленную оболочку на устройство для углубленного [расследования безопасности.](/microsoft-365/security/defender-endpoint/live-response)</span><span class="sxs-lookup"><span data-stu-id="b5686-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](/microsoft-365/security/defender-endpoint/live-response).</span></span>
* <span data-ttu-id="b5686-148">**Инициировать автоматическое** расследование — [автоматически расследует и устраняет угрозы.](../office-365-security/office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="b5686-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](../office-365-security/office-365-air.md).</span></span> <span data-ttu-id="b5686-149">Хотя с этой страницы можно запускать автоматические [](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) расследования вручную, некоторые политики оповещения запускают автоматические расследования самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="b5686-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="b5686-150">**Центр действий** — отображает сведения о любых действиях реагирования, которые в настоящее время запущены.</span><span class="sxs-lookup"><span data-stu-id="b5686-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="b5686-151">Раздел "Вкладки"</span><span class="sxs-lookup"><span data-stu-id="b5686-151">Tabs section</span></span>

<span data-ttu-id="b5686-152">Вкладки профилей устройств позволяют с помощью обзора сведений о безопасности устройства и таблиц, содержащих список оповещений.</span><span class="sxs-lookup"><span data-stu-id="b5686-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="b5686-153">Устройства, зарегистрированные в Microsoft Defender для конечной точки, также будут отображать вкладки с временной шкалой, списком рекомендаций по безопасности, инвентаризацией программного обеспечения, списком обнаруженных уязвимостей и отсутствующих ЦБ (обновления безопасности).</span><span class="sxs-lookup"><span data-stu-id="b5686-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="b5686-154">Вкладка Обзор</span><span class="sxs-lookup"><span data-stu-id="b5686-154">Overview tab</span></span>

<span data-ttu-id="b5686-155">Вкладка по умолчанию **— Обзор**.</span><span class="sxs-lookup"><span data-stu-id="b5686-155">The default tab is **Overview**.</span></span> <span data-ttu-id="b5686-156">Он позволяет быстро и быстро взглянуть на наиболее важные аспекты безопасности устройства.</span><span class="sxs-lookup"><span data-stu-id="b5686-156">It provides a quick look at the most important security fact about the device.</span></span>

![Изображение вкладки обзор для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="b5686-158">Здесь вы можете получить быстрый обзор активных оповещений устройства и любых в настоящее время зарегистрированных на пользователях.</span><span class="sxs-lookup"><span data-stu-id="b5686-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="b5686-159">Если устройство зарегистрировано в Microsoft Defender для конечной точки, вы также увидите уровень риска устройства и все доступные данные о оценках безопасности.</span><span class="sxs-lookup"><span data-stu-id="b5686-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="b5686-160">Оценки безопасности описывают уровень экспозиции устройства, предоставляют рекомендации по безопасности, а также перечисляют затрагиваемую программу и обнаруженные уязвимости.</span><span class="sxs-lookup"><span data-stu-id="b5686-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="b5686-161">Вкладка Оповещений</span><span class="sxs-lookup"><span data-stu-id="b5686-161">Alerts tab</span></span>

<span data-ttu-id="b5686-162">Вкладка **Alerts** содержит список оповещений, поднятых на устройстве, как из Microsoft Defender для удостоверений, так и от Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b5686-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Изображение вкладки оповещений для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="b5686-164">Можно настроить количество отображаемых элементов, а также количество столбцов для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="b5686-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="b5686-165">По умолчанию необходимо перечислить тридцать элементов на страницу.</span><span class="sxs-lookup"><span data-stu-id="b5686-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="b5686-166">Столбцы на этой вкладке содержат сведения о серьезности угрозы, которая вызвала оповещение, а также о состоянии, состоянии расследования и о том, кому было назначено предупреждение.</span><span class="sxs-lookup"><span data-stu-id="b5686-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="b5686-167">Столбец *затронутых сущностей* относится к устройству (объекту), профиль которого вы в настоящее время просматриваете, а также к любым другим устройствам в вашей сети, которые затронуты.</span><span class="sxs-lookup"><span data-stu-id="b5686-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="b5686-168">Выбор элемента из этого списка откроет вылет, содержащий дополнительные сведения о выбранном оповещении.</span><span class="sxs-lookup"><span data-stu-id="b5686-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="b5686-169">Этот список можно отфильтровать по строгости, статусу или по назначенной оповещению.</span><span class="sxs-lookup"><span data-stu-id="b5686-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="b5686-170">Вкладка Timeline</span><span class="sxs-lookup"><span data-stu-id="b5686-170">Timeline tab</span></span>

<span data-ttu-id="b5686-171">Вкладка **Timeline** включает интерактивную хронологическую диаграмму всех событий, поднятых на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b5686-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="b5686-172">Перемещая выделенную область диаграммы влево или вправо, можно просматривать события в разные периоды времени.</span><span class="sxs-lookup"><span data-stu-id="b5686-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="b5686-173">Вы также можете выбрать настраиваемый диапазон дат из выпадаемого меню между интерактивной диаграммой и списком событий.</span><span class="sxs-lookup"><span data-stu-id="b5686-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="b5686-174">Ниже диаграммы приведен список событий для выбранного диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="b5686-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Изображение вкладки Timeline для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="b5686-176">Количество отображаемых элементов и столбцы в списке могут быть настроены.</span><span class="sxs-lookup"><span data-stu-id="b5686-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="b5686-177">Столбцы по умолчанию перечисляют время события, активный пользователь, тип действия, сущности (процессы) и дополнительные сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="b5686-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="b5686-178">Выбор элемента из этого списка откроет вылет, отображающий график сущностями событий, показывающий родительские и детские процессы, участвующие в событии.</span><span class="sxs-lookup"><span data-stu-id="b5686-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="b5686-179">Список можно отфильтровать по определенному типу события; например, события реестра или события smart Screen.</span><span class="sxs-lookup"><span data-stu-id="b5686-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="b5686-180">Список также можно экспортировать в CSV-файл для скачивания.</span><span class="sxs-lookup"><span data-stu-id="b5686-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="b5686-181">Несмотря на то, что файл не ограничен количеством событий, максимальный диапазон времени, который можно экспортировать, — семь дней.</span><span class="sxs-lookup"><span data-stu-id="b5686-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="b5686-182">Вкладка рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="b5686-182">Security recommendations tab</span></span>

<span data-ttu-id="b5686-183">В **вкладке Рекомендации по безопасности** перечислены действия, которые можно принять для защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="b5686-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="b5686-184">Выбор элемента в этом списке откроет вылет, где можно получить инструкции по применении рекомендации.</span><span class="sxs-lookup"><span data-stu-id="b5686-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Изображение вкладки рекомендаций по безопасности для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="b5686-186">Как и в предыдущих вкладок, можно настроить количество элементов, отображаемых на странице, а также те столбцы, которые видны.</span><span class="sxs-lookup"><span data-stu-id="b5686-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="b5686-187">Представление по умолчанию включает столбцы, в которых подробно рассматриваются недостатки безопасности, связанная угроза, связанный компонент или программное обеспечение, затронутые угрозой, и другие.</span><span class="sxs-lookup"><span data-stu-id="b5686-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="b5686-188">Элементы можно фильтровать по статусу рекомендации.</span><span class="sxs-lookup"><span data-stu-id="b5686-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="b5686-189">Перечень программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="b5686-189">Software inventory</span></span>

<span data-ttu-id="b5686-190">Вкладка **инвентаризации программного** обеспечения содержит списки программного обеспечения, установленного на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b5686-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Изображение вкладки инвентаризации программного обеспечения для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="b5686-192">Представление по умолчанию отображает поставщика программного обеспечения, установленный номер версии, количество известных недостатков программного обеспечения, сведения об угрозах, код продукта и теги.</span><span class="sxs-lookup"><span data-stu-id="b5686-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="b5686-193">Количество отображаемых элементов и столбцов может быть настроено.</span><span class="sxs-lookup"><span data-stu-id="b5686-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="b5686-194">Выбор элемента из этого списка открывает вылет, содержащий дополнительные сведения о выбранном программном обеспечении, а также путь и время последнего открытия программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b5686-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="b5686-195">Этот список можно отфильтровать по коду продукта.</span><span class="sxs-lookup"><span data-stu-id="b5686-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="b5686-196">Вкладка Обнаруженные уязвимости</span><span class="sxs-lookup"><span data-stu-id="b5686-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="b5686-197">На **вкладке "Обнаруженные уязвимости"** перечислены все распространенные уязвимости и эксплойты (CVEs), которые могут повлиять на устройство.</span><span class="sxs-lookup"><span data-stu-id="b5686-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Изображение вкладки обнаруженных уязвимостей для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="b5686-199">В представлении по умолчанию перечислены серьезность CVE, общей оценки уязвимости (CVS), программного обеспечения, связанного с CVE, когда CVE был опубликован, когда CVE был последним обновлением, и угрозы, связанные с CVE.</span><span class="sxs-lookup"><span data-stu-id="b5686-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="b5686-200">Как и в предыдущих вкладок, можно настроить количество отображаемых элементов и видимых столбцов.</span><span class="sxs-lookup"><span data-stu-id="b5686-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="b5686-201">Выбор элемента из этого списка откроет вылет, описывающий CVE.</span><span class="sxs-lookup"><span data-stu-id="b5686-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="b5686-202">Отсутствующие KBs</span><span class="sxs-lookup"><span data-stu-id="b5686-202">Missing KBs</span></span>

<span data-ttu-id="b5686-203">На **вкладке Missing KBs** перечислены все обновления Майкрософт, которые еще не были применены к устройству.</span><span class="sxs-lookup"><span data-stu-id="b5686-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="b5686-204">Речь идет о статьях [Базы](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) знаний, в которых описываются эти обновления; например, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="b5686-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Изображение отсутствующих вкладок kbs для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="b5686-206">В представлении по умолчанию перечислены бюллетень, содержащий обновления, версию ОС, затронутые продукты, адрес резюме, номер КБ и теги.</span><span class="sxs-lookup"><span data-stu-id="b5686-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="b5686-207">Количество элементов, отображаемых на странице и отображаемых столбцов, можно настроить.</span><span class="sxs-lookup"><span data-stu-id="b5686-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="b5686-208">При выборе элемента откроется флайер, ссылающийся на обновление.</span><span class="sxs-lookup"><span data-stu-id="b5686-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5686-209">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b5686-209">Related topics</span></span>

* [<span data-ttu-id="b5686-210">Microsoft 365 Обзор defender</span><span class="sxs-lookup"><span data-stu-id="b5686-210">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
* [<span data-ttu-id="b5686-211">Включение Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5686-211">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
* [<span data-ttu-id="b5686-212">Исследование сущностями на устройствах с помощью живого ответа</span><span class="sxs-lookup"><span data-stu-id="b5686-212">Investigate entities on devices, using live response</span></span>](../defender-endpoint/live-response.md)
* [<span data-ttu-id="b5686-213">Автоматическое расследование и ответ (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="b5686-213">Automated investigation and response (AIR) in Office 365</span></span>](../office-365-security/office-365-air.md)
