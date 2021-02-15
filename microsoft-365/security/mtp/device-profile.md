---
title: Профиль устройства на портале безопасности Microsoft 365
description: Просмотр уровней риска и экспозиции для устройства в организации. Проанализируйте прошлые и присутствующие угрозы и защитите устройство с помощью последних обновлений.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, Защита от угроз (Майкрософт), MTP, Центр безопасности, ATP в Microsoft Defender, Office 365 ATP, Azure ATP, страница устройства, профиль устройства, страница компьютера, профиль компьютера
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929578"
---
# <a name="device-profile-page"></a><span data-ttu-id="1a73a-105">Страница профиля устройства</span><span class="sxs-lookup"><span data-stu-id="1a73a-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1a73a-106">Портал безопасности Microsoft 365 предоставляет страницы профилей устройств, что позволяет быстро оценить состояние и состояние устройств в сети.</span><span class="sxs-lookup"><span data-stu-id="1a73a-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a73a-107">Страница профиля устройства может немного отличаться в зависимости от того, зарегистрировать ли устройство в Microsoft Defender для конечной точки, Microsoft Defender для удостоверений или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="1a73a-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="1a73a-108">Если устройство зарегистрировать в Microsoft Defender для конечной точки, вы также можете использовать страницу профиля устройства для выполнения некоторых распространенных задач безопасности.</span><span class="sxs-lookup"><span data-stu-id="1a73a-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="1a73a-109">Навигация по странице профиля устройства</span><span class="sxs-lookup"><span data-stu-id="1a73a-109">Navigating the device profile page</span></span>

<span data-ttu-id="1a73a-110">Страница профиля разбита на несколько общих разделов.</span><span class="sxs-lookup"><span data-stu-id="1a73a-110">The profile page is broken up into several broad sections.</span></span>

![Изображение страницы профиля устройства с областью вкладок (1) (2) боковой панелью и (3) действиями, выделенной красным цветом](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="1a73a-112">На боковой панели (1) перечислены основные сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="1a73a-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="1a73a-113">Основная область содержимого (2) содержит вкладки, через которые можно перегонать для просмотра различных типов сведений об устройстве.</span><span class="sxs-lookup"><span data-stu-id="1a73a-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="1a73a-114">Если устройство зарегистрировать в Microsoft Defender для конечной точки, вы также увидите список ответных действий (3).</span><span class="sxs-lookup"><span data-stu-id="1a73a-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="1a73a-115">Действия реагирования позволяют выполнять распространенные задачи, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="1a73a-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="1a73a-116">Боковая панель</span><span class="sxs-lookup"><span data-stu-id="1a73a-116">Sidebar</span></span>

<span data-ttu-id="1a73a-117">Рядом с основной областью содержимого страницы профиля устройства находится боковая панель.</span><span class="sxs-lookup"><span data-stu-id="1a73a-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Изображение боковой вкладки для профиля устройства](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="1a73a-119">На боковой панели перечислены полное имя устройства и уровень экспозиции.</span><span class="sxs-lookup"><span data-stu-id="1a73a-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="1a73a-120">Кроме того, он предоставляет некоторые важные базовые сведения в небольших подмесяхах, которые можно переглушить открытыми или закрытыми, например:</span><span class="sxs-lookup"><span data-stu-id="1a73a-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="1a73a-121">**Теги** — любой Microsoft Defender для конечной точки, Microsoft Defender для удостоверений или настраиваемые теги, связанные с устройством.</span><span class="sxs-lookup"><span data-stu-id="1a73a-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="1a73a-122">Теги из Microsoft Defender для удостоверений невозможно редактировать.</span><span class="sxs-lookup"><span data-stu-id="1a73a-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="1a73a-123">**Сведения о безопасности** — открытые инциденты и активные оповещения.</span><span class="sxs-lookup"><span data-stu-id="1a73a-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="1a73a-124">Устройства, зарегистрированные в Microsoft Defender для конечной точки, также будут отображать уровень экспозиции и уровень риска.</span><span class="sxs-lookup"><span data-stu-id="1a73a-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="1a73a-125">Уровень экспозиции зависит от того, насколько устройство соответствует рекомендациям по безопасности, а уровень риска рассчитывается на основе ряда факторов, включая типы и серьезность активных оповещений.</span><span class="sxs-lookup"><span data-stu-id="1a73a-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="1a73a-126">**Сведения об** устройстве: домен, ОС, временная пометь о том, когда устройство было впервые видно, IP-адреса, ресурсы.</span><span class="sxs-lookup"><span data-stu-id="1a73a-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="1a73a-127">Устройства, зарегистрированные в Microsoft Defender для конечной точки, также отображают состояние состояния здоровья.</span><span class="sxs-lookup"><span data-stu-id="1a73a-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="1a73a-128">На устройствах, зарегистрированных в Microsoft Defender для удостоверений, будет отображаться имя SAM и временная идентификация времени создания устройства.</span><span class="sxs-lookup"><span data-stu-id="1a73a-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="1a73a-129">**Сетевое действие** — метки времени в первый раз и в последний раз, когда устройство было видно в сети.</span><span class="sxs-lookup"><span data-stu-id="1a73a-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="1a73a-130">**Данные каталога** (только для устройств, зарегистрированных в *Microsoft Defender для удостоверений)*— флаги [UAC,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names)и членство в группах.</span><span class="sxs-lookup"><span data-stu-id="1a73a-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="1a73a-131">Действия реагирования</span><span class="sxs-lookup"><span data-stu-id="1a73a-131">Response actions</span></span>

<span data-ttu-id="1a73a-132">Ответные действия предоставляют быстрый способ защиты от угроз и их анализа.</span><span class="sxs-lookup"><span data-stu-id="1a73a-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Изображение панели действий для профиля устройства](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="1a73a-134">[Ответные](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) действия доступны, только если устройство зарегистрировать в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1a73a-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="1a73a-135">На устройствах, зарегистрированных в Microsoft Defender для конечной точки, может отображаться разное количество ответных действий в зависимости от ОС и номера версии устройства.</span><span class="sxs-lookup"><span data-stu-id="1a73a-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="1a73a-136">На странице профиля устройства доступны следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1a73a-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="1a73a-137">**Управление тегами** — обновляет пользовательские теги, примененные к этому устройству.</span><span class="sxs-lookup"><span data-stu-id="1a73a-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="1a73a-138">**Изолировать устройство** — изолирует устройство от сети организации, сохраняя подключение к Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1a73a-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1a73a-139">Вы можете разрешить запуск Outlook, Teams и Skype для бизнеса в изолированном устройстве в целях связи.</span><span class="sxs-lookup"><span data-stu-id="1a73a-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="1a73a-140">**Центр действий** — просмотр состояния отправленных действий.</span><span class="sxs-lookup"><span data-stu-id="1a73a-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="1a73a-141">Доступно только в том случае, если уже выбрано другое действие.</span><span class="sxs-lookup"><span data-stu-id="1a73a-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="1a73a-142">**Ограничение выполнения приложения** — предотвращает запуск приложений, не подписанных корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1a73a-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="1a73a-143">**Запуск антивирусной проверки** — обновление Защитник Windows определений антивирусной программы и немедленное запуск антивирусной проверки.</span><span class="sxs-lookup"><span data-stu-id="1a73a-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="1a73a-144">Выберите "Быстрая проверка" или "Полная проверка".</span><span class="sxs-lookup"><span data-stu-id="1a73a-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="1a73a-145">**Сбор пакета исследования** — собирает сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="1a73a-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="1a73a-146">После завершения исследования вы можете скачать его.</span><span class="sxs-lookup"><span data-stu-id="1a73a-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="1a73a-147">**Инициировать сеанс** live Response Session — загружает удаленную оболочку на устройство для углубленного изучения [безопасности.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="1a73a-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="1a73a-148">**Инициировать автоматическое** исследование — автоматически изучает и устраняет [угрозы.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</span><span class="sxs-lookup"><span data-stu-id="1a73a-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="1a73a-149">Хотя на этой странице можно запустить автоматические исследования [вручную,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) некоторые политики оповещений запускают автоматические расследования самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="1a73a-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="1a73a-150">**Центр действий** — отображает сведения о любых действиях ответа, которые в настоящее время запущены.</span><span class="sxs-lookup"><span data-stu-id="1a73a-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="1a73a-151">Раздел "Вкладки"</span><span class="sxs-lookup"><span data-stu-id="1a73a-151">Tabs section</span></span>

<span data-ttu-id="1a73a-152">Вкладки профиля устройства позволяют перевести обзор сведений о безопасности устройства и таблиц, содержащих список оповещений.</span><span class="sxs-lookup"><span data-stu-id="1a73a-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="1a73a-153">Устройства, зарегистрированные в Microsoft Defender для конечной точки, также будут отображать вкладки с временной шкалой, списком рекомендаций по безопасности, инвентаризацией программного обеспечения, списком обнаруженных уязвимостей и отсутствующих КБ (обновления для системы безопасности).</span><span class="sxs-lookup"><span data-stu-id="1a73a-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="1a73a-154">Вкладка "Обзор"</span><span class="sxs-lookup"><span data-stu-id="1a73a-154">Overview tab</span></span>

<span data-ttu-id="1a73a-155">Вкладка по умолчанию — **"Обзор".**</span><span class="sxs-lookup"><span data-stu-id="1a73a-155">The default tab is **Overview**.</span></span> <span data-ttu-id="1a73a-156">Он позволяет быстро и быстро и быстро получить самые важные данные о безопасности устройства.</span><span class="sxs-lookup"><span data-stu-id="1a73a-156">It provides a quick look at the most important security fact about the device.</span></span>

![Изображение вкладки "Обзор" для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="1a73a-158">Здесь вы можете быстро и быстро посмотреть активные оповещения устройства и всех пользователей, во время входа в систему.</span><span class="sxs-lookup"><span data-stu-id="1a73a-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="1a73a-159">Если устройство зарегистрировать в Microsoft Defender для конечной точки, вы также увидите уровень риска устройства и все доступные данные об оценках безопасности.</span><span class="sxs-lookup"><span data-stu-id="1a73a-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="1a73a-160">Оценки безопасности описывают степень уязвимости устройства, предоставляют рекомендации по безопасности, а также перечисляют затронутное программное обеспечение и обнаруженные уязвимости.</span><span class="sxs-lookup"><span data-stu-id="1a73a-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="1a73a-161">Вкладка "Оповещения"</span><span class="sxs-lookup"><span data-stu-id="1a73a-161">Alerts tab</span></span>

<span data-ttu-id="1a73a-162">Вкладка **"Оповещения"** содержит список оповещений, которые были выпущены на устройстве как из Microsoft Defender для удостоверений, так и из Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1a73a-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Изображение вкладки оповещений для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="1a73a-164">Можно настроить количество отображаемых элементов, а также столбцы, отображаемые для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="1a73a-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="1a73a-165">По умолчанию в списке 30 элементов на страницу.</span><span class="sxs-lookup"><span data-stu-id="1a73a-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="1a73a-166">Столбцы на этой вкладке содержат сведения о степени серьезности угрозы, которая вызвала оповещение, а также о состоянии, состоянии исследования и о том, кому назначено оповещение.</span><span class="sxs-lookup"><span data-stu-id="1a73a-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="1a73a-167">Столбец *затронутых сущностей* относится к устройству (объекту), профиль которого вы просматриваете в данный момент, а также к другим устройствам в вашей сети, которые затронуты.</span><span class="sxs-lookup"><span data-stu-id="1a73a-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="1a73a-168">При выборе элемента из этого списка откроется элемент, содержащий дополнительные сведения об выбранном оповещении.</span><span class="sxs-lookup"><span data-stu-id="1a73a-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="1a73a-169">Этот список можно отфильтровать по степени серьезности, состоянии или по назначенной оповещению.</span><span class="sxs-lookup"><span data-stu-id="1a73a-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="1a73a-170">Вкладка "Временная шкала"</span><span class="sxs-lookup"><span data-stu-id="1a73a-170">Timeline tab</span></span>

<span data-ttu-id="1a73a-171">Вкладка **"Временная** шкала" содержит интерактивную хронологическую диаграмму всех событий, которые вызываются на устройстве.</span><span class="sxs-lookup"><span data-stu-id="1a73a-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="1a73a-172">Перемещая выделенную область диаграммы влево или вправо, вы можете просматривать события в разные периоды времени.</span><span class="sxs-lookup"><span data-stu-id="1a73a-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="1a73a-173">Вы также можете выбрать пользовательский диапазон дат из меню в выпадающим меню между интерактивной диаграммой и списком событий.</span><span class="sxs-lookup"><span data-stu-id="1a73a-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="1a73a-174">Под диаграммой находится список событий для выбранного диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="1a73a-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Изображение вкладки временной шкалы для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="1a73a-176">Количество отображаемых элементов и столбцов в списке можно настроить.</span><span class="sxs-lookup"><span data-stu-id="1a73a-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="1a73a-177">В столбцах по умолчанию перечисляется время события, активный пользователь, тип действия, сущности (процессы) и дополнительные сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="1a73a-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="1a73a-178">При выборе элемента из этого списка откроется элемент, отображающий граф сущностями события, в котором показаны родительские и потомковые процессы, участвующие в событии.</span><span class="sxs-lookup"><span data-stu-id="1a73a-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="1a73a-179">Список может быть отфильтрован по определенному типу события; например, события реестра или события smart Screen.</span><span class="sxs-lookup"><span data-stu-id="1a73a-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="1a73a-180">Список также можно экспортировать в CSV-файл для скачивания.</span><span class="sxs-lookup"><span data-stu-id="1a73a-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="1a73a-181">Несмотря на то что файл не ограничен числом событий, максимальный диапазон времени, который можно экспортировать, составляет семь дней.</span><span class="sxs-lookup"><span data-stu-id="1a73a-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="1a73a-182">Вкладка "Рекомендации по безопасности"</span><span class="sxs-lookup"><span data-stu-id="1a73a-182">Security recommendations tab</span></span>

<span data-ttu-id="1a73a-183">На **вкладке "Рекомендации по безопасности"** перечислены действия, которые можно принять для защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="1a73a-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="1a73a-184">При выборе элемента в этом списке откроется элемент, в котором можно получить инструкции по ее применении.</span><span class="sxs-lookup"><span data-stu-id="1a73a-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Изображение вкладки "Рекомендации по безопасности" для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="1a73a-186">Как и в предыдущих вкладок, можно настроить количество элементов, отображаемых на странице, а также отображаемые столбцы.</span><span class="sxs-lookup"><span data-stu-id="1a73a-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="1a73a-187">Представление по умолчанию содержит столбцы, в которых подробно рассматриваются недостатки безопасности, связанная угроза, связанный компонент или программное обеспечение, затронутые угрозой, и другие.</span><span class="sxs-lookup"><span data-stu-id="1a73a-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="1a73a-188">Элементы могут фильтроваться по статусу рекомендации.</span><span class="sxs-lookup"><span data-stu-id="1a73a-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="1a73a-189">Перечень программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="1a73a-189">Software inventory</span></span>

<span data-ttu-id="1a73a-190">На **вкладке "Инвентаризация** программного обеспечения" перечислены программы, установленные на устройстве.</span><span class="sxs-lookup"><span data-stu-id="1a73a-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Изображение вкладки "Инвентаризация программного обеспечения" для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="1a73a-192">В представлении по умолчанию отображается поставщик программного обеспечения, установленный номер версии, количество известных недостатков программного обеспечения, анализ угроз, код продукта и теги.</span><span class="sxs-lookup"><span data-stu-id="1a73a-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="1a73a-193">Количество отображаемых элементов и отображаемых столбцов можно настроить.</span><span class="sxs-lookup"><span data-stu-id="1a73a-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="1a73a-194">При выборе элемента из этого списка откроется элемент, содержащий более подробные сведения о выбранном программном обеспечении, а также путь и временную запамяти в последний раз, когда программное обеспечение было найдено.</span><span class="sxs-lookup"><span data-stu-id="1a73a-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="1a73a-195">Этот список можно отфильтровать по коду продукта.</span><span class="sxs-lookup"><span data-stu-id="1a73a-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="1a73a-196">Вкладка "Обнаруженные уязвимости"</span><span class="sxs-lookup"><span data-stu-id="1a73a-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="1a73a-197">На **вкладке "Обнаруженные уязвимости"** перечислены все распространенные уязвимости и эксплойты, которые могут повлиять на устройство.</span><span class="sxs-lookup"><span data-stu-id="1a73a-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Изображение вкладки "Обнаруженные уязвимости" для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="1a73a-199">В представлении по умолчанию перечислены степень серьезности CVE, общий показатель уязвимости (CVS), программное обеспечение, связанное с CVE, при публикации CVE, время последнего обновления CVE и угрозы, связанные с CVE.</span><span class="sxs-lookup"><span data-stu-id="1a73a-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="1a73a-200">Как и в предыдущих вкладок, можно настроить количество отображаемых элементов и отображаемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="1a73a-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="1a73a-201">При выборе элемента из этого списка откроется элемент, описывающий CVE.</span><span class="sxs-lookup"><span data-stu-id="1a73a-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="1a73a-202">Отсутствующие КБ</span><span class="sxs-lookup"><span data-stu-id="1a73a-202">Missing KBs</span></span>

<span data-ttu-id="1a73a-203">На **вкладке "Отсутствующие КБ"** перечислены все обновления Майкрософт, которые еще не были применены к устройству.</span><span class="sxs-lookup"><span data-stu-id="1a73a-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="1a73a-204">"Базы знаний" — [это](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) статьи базы знаний, в которых описываются эти обновления; например, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="1a73a-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Изображение отсутствующих вкладок кб для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="1a73a-206">В представлении по умолчанию содержится бюллетень, содержащий обновления, версию ОС, затронутые продукты, адресованные CVEs, номер КБ и теги.</span><span class="sxs-lookup"><span data-stu-id="1a73a-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="1a73a-207">Количество элементов, отображаемых на странице, и отображаемых столбцов, можно настроить.</span><span class="sxs-lookup"><span data-stu-id="1a73a-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="1a73a-208">При выборе элемента откроется элемент, ссылающийся на обновление.</span><span class="sxs-lookup"><span data-stu-id="1a73a-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1a73a-209">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="1a73a-209">Related topics</span></span>

* [<span data-ttu-id="1a73a-210">Обзор Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a73a-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="1a73a-211">Включить Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a73a-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="1a73a-212">Исследование сущностями на устройствах с помощью прямого ответа</span><span class="sxs-lookup"><span data-stu-id="1a73a-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="1a73a-213">Автоматизированное исследование и реагирование на них (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="1a73a-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
