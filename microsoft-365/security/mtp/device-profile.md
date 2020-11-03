---
title: Профиль устройства на портале безопасности Microsoft 365
description: Просмотр уровней риска и экспозиции для устройства в Организации. Проанализируйте предыдущие и применяйте угрозы и Защитите устройство с помощью последних обновлений.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, защита от угроз Майкрософт, MTP, центр обеспечения безопасности, пакет ATP для защитника, Office 365 ATP, Azure ATP, страница устройства, профиль устройства, страница компьютера, профиль компьютера
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 3840a6beae3b586fc90420f7813ff6e9d3cc6c60
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843856"
---
# <a name="device-profile-page"></a><span data-ttu-id="f5d82-105">Страница профиля устройства</span><span class="sxs-lookup"><span data-stu-id="f5d82-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5d82-106">Портал безопасности Microsoft 365 предоставляет страницы профилей устройств, поэтому вы можете быстро оценить работоспособность и состояние устройств в сети.</span><span class="sxs-lookup"><span data-stu-id="f5d82-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5d82-107">Страница профиля устройства может слегка различаться в зависимости от того, зарегистрировано ли устройство в защитнике Майкрософт для конечной точки, защитника Майкрософт для удостоверения или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="f5d82-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="f5d82-108">Если устройство зарегистрировано в защитнике Майкрософт для конечной точки, можно также использовать страницу профиля устройства для выполнения некоторых распространенных задач по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="f5d82-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="f5d82-109">Навигация по странице профиля устройства</span><span class="sxs-lookup"><span data-stu-id="f5d82-109">Navigating the device profile page</span></span>

<span data-ttu-id="f5d82-110">Страница профиля разбивается на несколько общих разделов.</span><span class="sxs-lookup"><span data-stu-id="f5d82-110">The profile page is broken up into several broad sections.</span></span>

![Изображение страницы профиля устройства с (1) областью вкладок (2) Боковая панель и (3) действия, выделенные красным цветом](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="f5d82-112">На боковой панели (1) перечислены основные сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="f5d82-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="f5d82-113">Основная область содержимого (2) содержит вкладки, которые можно переключать для просмотра различных типов сведений об устройстве.</span><span class="sxs-lookup"><span data-stu-id="f5d82-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="f5d82-114">Если устройство зарегистрировано в защитнике Майкрософт для конечной точки, также отображается список действий отклика (3).</span><span class="sxs-lookup"><span data-stu-id="f5d82-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="f5d82-115">Действия отклика позволяют выполнять стандартные задачи, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="f5d82-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="f5d82-116">Боковой панели</span><span class="sxs-lookup"><span data-stu-id="f5d82-116">Sidebar</span></span>

<span data-ttu-id="f5d82-117">Рядом с основной областью содержимого страницы профиля устройства отображается боковая панель.</span><span class="sxs-lookup"><span data-stu-id="f5d82-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Изображение вкладки боковой панели для профиля устройства](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="f5d82-119">Боковая панель содержит полное имя и уровень экспозиции устройства.</span><span class="sxs-lookup"><span data-stu-id="f5d82-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="f5d82-120">Кроме того, он предоставляет некоторую важную информацию в небольших подразделах, которые можно переключать в режим открытия или закрытия, например:</span><span class="sxs-lookup"><span data-stu-id="f5d82-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="f5d82-121">**Tags** — любой защитник Майкрософт для конечной точки, защитник Майкрософт для удостоверения или настраиваемые теги, связанные с устройством.</span><span class="sxs-lookup"><span data-stu-id="f5d82-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="f5d82-122">Теги от защитника Майкрософт для удостоверения не подлежат редактированию.</span><span class="sxs-lookup"><span data-stu-id="f5d82-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="f5d82-123">**Сведения о безопасности** — открытые инциденты и активные оповещения.</span><span class="sxs-lookup"><span data-stu-id="f5d82-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="f5d82-124">Устройства, зарегистрированные в защитнике Майкрософт для конечной точки, также будут отображать уровень доступности и уровень риска.</span><span class="sxs-lookup"><span data-stu-id="f5d82-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="f5d82-125">Уровень экспозиции связан с тем, насколько устройство соответствует рекомендациям по обеспечению безопасности, а уровень риска рассчитывается на основе ряда факторов, включая типы и серьезность активных оповещений.</span><span class="sxs-lookup"><span data-stu-id="f5d82-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="f5d82-126">**Сведения об устройстве** — Domain, OS, timestamp для первого постороннего устройства, IP-адреса, ресурсы.</span><span class="sxs-lookup"><span data-stu-id="f5d82-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="f5d82-127">Устройства, зарегистрированные в защитнике Майкрософт для конечной точки, также отображают состояние работоспособности.</span><span class="sxs-lookup"><span data-stu-id="f5d82-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="f5d82-128">Устройства, зарегистрированные в защитнике Майкрософт для удостоверения, будут отображать имя SAM и временную метку при первом создании устройства.</span><span class="sxs-lookup"><span data-stu-id="f5d82-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="f5d82-129">**Активность сети** — метки времени в первый раз и в последний раз, когда устройство было замечено в сети.</span><span class="sxs-lookup"><span data-stu-id="f5d82-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="f5d82-130">**Данные каталога** ( *только для устройств, зарегистрированных в защитнике Майкрософт для удостоверения* ) — флаги [контроля учетных записей](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) , [SPN](https://docs.microsoft.com/windows/win32/ad/service-principal-names)и членство в группах.</span><span class="sxs-lookup"><span data-stu-id="f5d82-130">**Directory data** ( *only for devices enrolled in Microsoft Defender for Identity* ) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="f5d82-131">Действия отклика</span><span class="sxs-lookup"><span data-stu-id="f5d82-131">Response actions</span></span>

<span data-ttu-id="f5d82-132">Действия отклика предоставляют быстрый способ защиты от угроз и анализа угроз.</span><span class="sxs-lookup"><span data-stu-id="f5d82-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Изображение панели действий для профиля устройства](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="f5d82-134">[Действия отклика](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) доступны только в том случае, если устройство зарегистрировано в защитнике Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f5d82-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="f5d82-135">Устройства, зарегистрированные в защитнике Майкрософт для конечной точки, могут отображать различные действия отклика на основе операционной системы и номера версии устройства.</span><span class="sxs-lookup"><span data-stu-id="f5d82-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="f5d82-136">Ниже перечислены действия, доступные на странице профиля устройства.</span><span class="sxs-lookup"><span data-stu-id="f5d82-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="f5d82-137">**Manage tagss** — обновления настраиваемые теги, примененные к этому устройству.</span><span class="sxs-lookup"><span data-stu-id="f5d82-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="f5d82-138">**Изолировать устройство** — изолирует устройство от сети организации, не подключаясь к защитнику Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f5d82-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f5d82-139">Вы можете разрешить запуск Outlook, Teams и Skype для бизнеса, пока устройство изолировано, в целях общения.</span><span class="sxs-lookup"><span data-stu-id="f5d82-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="f5d82-140">**Центр уведомлений** — Просмотр состояния отправленных действий.</span><span class="sxs-lookup"><span data-stu-id="f5d82-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="f5d82-141">Доступно только в том случае, если уже было выбрано другое действие.</span><span class="sxs-lookup"><span data-stu-id="f5d82-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="f5d82-142">**Ограничьте выполнение приложения** — предотвращает запуск приложений, не подписанных корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f5d82-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="f5d82-143">**Запуск антивирусной проверки** — обновление определений антивирусной программы "Защитник Windows" и немедленное выполнение антивирусной проверки.</span><span class="sxs-lookup"><span data-stu-id="f5d82-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="f5d82-144">Выбор между быстрым сканированием или полным сканированием.</span><span class="sxs-lookup"><span data-stu-id="f5d82-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="f5d82-145">**Сбор пакетов для расследования** — сбор сведений об устройстве.</span><span class="sxs-lookup"><span data-stu-id="f5d82-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="f5d82-146">По завершении расследования вы можете скачать его.</span><span class="sxs-lookup"><span data-stu-id="f5d82-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="f5d82-147">**Initiate Live Response Session** — загружает удаленную оболочку на устройстве для [всестороннего расследования по безопасности](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="f5d82-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="f5d82-148">**Initiate автоматизированное исследование** — автоматически [исследует и исправлять угрозы](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span><span class="sxs-lookup"><span data-stu-id="f5d82-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="f5d82-149">Несмотря на то, что вы можете вручную активировать автоматическое расследование для запуска с этой страницы, [некоторые политики оповещений](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) инициируют автоматическое расследование самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f5d82-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="f5d82-150">В **центре уведомлений** отображаются сведения о любых действиях ответа, выполняемых в данный момент.</span><span class="sxs-lookup"><span data-stu-id="f5d82-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="f5d82-151">Раздел "Вкладки"</span><span class="sxs-lookup"><span data-stu-id="f5d82-151">Tabs section</span></span>

<span data-ttu-id="f5d82-152">На вкладках профилей устройств можно переключаться от обзора сведений о системе безопасности устройства и таблиц, содержащих список оповещений.</span><span class="sxs-lookup"><span data-stu-id="f5d82-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="f5d82-153">Устройства, зарегистрированные в защитнике Майкрософт для конечной точки, также будут отображать вкладки, в которых находится временная шкала, список рекомендаций по обеспечению безопасности, перечня программного обеспечения, список обнаруженных уязвимостей и отсутствующие КБ (обновления для системы безопасности).</span><span class="sxs-lookup"><span data-stu-id="f5d82-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="f5d82-154">Вкладка "Обзор"</span><span class="sxs-lookup"><span data-stu-id="f5d82-154">Overview tab</span></span>

<span data-ttu-id="f5d82-155">Вкладка по умолчанию — **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="f5d82-155">The default tab is **Overview**.</span></span> <span data-ttu-id="f5d82-156">Он обеспечивает краткий обзор наиболее важного факта безопасности для устройства.</span><span class="sxs-lookup"><span data-stu-id="f5d82-156">It provides a quick look at the most important security fact about the device.</span></span>

![Изображение вкладки обзора для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="f5d82-158">Здесь вы можете быстро просмотреть активные оповещения устройства и всех пользователей, выполнивших вход в систему.</span><span class="sxs-lookup"><span data-stu-id="f5d82-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="f5d82-159">Если устройство зарегистрировано в защитнике Майкрософт для конечной точки, также будет отображаться уровень риска устройства и все доступные данные по оценкам системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f5d82-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="f5d82-160">Оценки безопасности описывают уровень экспозиции устройства, предоставляют рекомендации по обеспечению безопасности и зависят от уязвимого программного обеспечения и обнаруженных уязвимостей.</span><span class="sxs-lookup"><span data-stu-id="f5d82-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="f5d82-161">Вкладка "оповещения"</span><span class="sxs-lookup"><span data-stu-id="f5d82-161">Alerts tab</span></span>

<span data-ttu-id="f5d82-162">Вкладка **оповещения** содержит список оповещений, которые были созданы на устройстве, от защитника Майкрософт для удостоверения и защитника Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f5d82-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Изображение вкладки "оповещения" для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="f5d82-164">Можно настроить количество отображаемых элементов, а также столбцы, отображаемые для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="f5d82-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="f5d82-165">По умолчанию на странице отображается не более тридцати элементов.</span><span class="sxs-lookup"><span data-stu-id="f5d82-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="f5d82-166">Столбцы на этой вкладке содержат сведения о серьезности угрозы, которое инициировало оповещение, а также состояние, состояние расследования и сведения о том, Кому назначено оповещение.</span><span class="sxs-lookup"><span data-stu-id="f5d82-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="f5d82-167">Столбец " *затронутые сущности* " ссылается на устройство (сущность), профиль которого в данный момент просматривается, а также на другие устройства в сети, на которые влияет эта проблема.</span><span class="sxs-lookup"><span data-stu-id="f5d82-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="f5d82-168">При выборе элемента в этом списке откроется всплывающее окно с дополнительными сведениями о выбранном оповещении.</span><span class="sxs-lookup"><span data-stu-id="f5d82-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="f5d82-169">Этот список можно фильтровать по уровню серьезности, состоянию или Кому назначено оповещение.</span><span class="sxs-lookup"><span data-stu-id="f5d82-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="f5d82-170">Вкладка "временная шкала"</span><span class="sxs-lookup"><span data-stu-id="f5d82-170">Timeline tab</span></span>

<span data-ttu-id="f5d82-171">Вкладка **временная шкала** содержит интерактивный хронологический график всех событий, возникающих на устройстве.</span><span class="sxs-lookup"><span data-stu-id="f5d82-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="f5d82-172">Перемещая выделенную область на диаграмме влево или вправо, вы можете просматривать события в течение разных периодов времени.</span><span class="sxs-lookup"><span data-stu-id="f5d82-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="f5d82-173">Вы также можете выбрать настраиваемый диапазон дат из раскрывающегося меню между интерактивной диаграммой и списком событий.</span><span class="sxs-lookup"><span data-stu-id="f5d82-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="f5d82-174">Под диаграммой представлен список событий для выбранного диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="f5d82-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Изображение вкладки временной шкалы для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="f5d82-176">Количество отображаемых элементов и столбцов в списке можно изменить.</span><span class="sxs-lookup"><span data-stu-id="f5d82-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="f5d82-177">В столбцах по умолчанию перечислены время события, активный пользователь, тип действия, сущности (процессы) и дополнительные сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f5d82-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="f5d82-178">При выборе элемента в этом списке откроется всплывающее окно с графиком сущностей события, в котором показаны родительские и дочерние процессы, участвующие в событии.</span><span class="sxs-lookup"><span data-stu-id="f5d82-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="f5d82-179">Список можно фильтровать по определенному типу события; Например, события в реестре или события Smart Screen.</span><span class="sxs-lookup"><span data-stu-id="f5d82-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="f5d82-180">Этот список также можно экспортировать в CSV-файл для загрузки.</span><span class="sxs-lookup"><span data-stu-id="f5d82-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="f5d82-181">Несмотря на то, что размер файла не ограничен количеством событий, максимальный диапазон времени, который можно выбрать для экспорта, составляет семь дней.</span><span class="sxs-lookup"><span data-stu-id="f5d82-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="f5d82-182">Вкладка "рекомендации по безопасности"</span><span class="sxs-lookup"><span data-stu-id="f5d82-182">Security recommendations tab</span></span>

<span data-ttu-id="f5d82-183">На вкладке **рекомендации по безопасности** перечислены действия, которые можно предпринять для защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="f5d82-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="f5d82-184">При выборе элемента в этом списке откроется раскрывающееся меню, в котором можно получить инструкции по применению рекомендации.</span><span class="sxs-lookup"><span data-stu-id="f5d82-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Изображение вкладки "рекомендации по безопасности" для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="f5d82-186">Как и в предыдущих вкладках, количество элементов, отображаемых на каждой странице, а также отображаемые столбцы, могут быть настроены.</span><span class="sxs-lookup"><span data-stu-id="f5d82-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="f5d82-187">Представление по умолчанию включает столбцы со сведениями о слабых слабых местах безопасности, связанной угрозой, связанным компонентом или программным обеспечением, на которые влияет угроза, и многое другое.</span><span class="sxs-lookup"><span data-stu-id="f5d82-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="f5d82-188">Элементы можно фильтровать по состоянию рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="f5d82-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="f5d82-189">Перечень программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="f5d82-189">Software inventory</span></span>

<span data-ttu-id="f5d82-190">На вкладке **Инвентаризация программного обеспечения** перечислены программное обеспечение, установленное на устройстве.</span><span class="sxs-lookup"><span data-stu-id="f5d82-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Изображение вкладки перечня программного обеспечения для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="f5d82-192">Представление по умолчанию отображает поставщика программного обеспечения, установленного номера версии, количества известных слабых мест программного обеспечения, кода продукта и тегов.</span><span class="sxs-lookup"><span data-stu-id="f5d82-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="f5d82-193">Количество отображаемых элементов и отображаемых столбцов можно изменить.</span><span class="sxs-lookup"><span data-stu-id="f5d82-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="f5d82-194">При выборе элемента в этом списке открывается всплывающее окно с дополнительными сведениями о выбранном программном обеспечении, а также путь и временная метка для последнего найденного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f5d82-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="f5d82-195">Этот список можно фильтровать по коду продукта.</span><span class="sxs-lookup"><span data-stu-id="f5d82-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="f5d82-196">Вкладка обнаруженных уязвимостей</span><span class="sxs-lookup"><span data-stu-id="f5d82-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="f5d82-197">На вкладке **обнаруженные уязвимости** перечислены все распространенные уязвимости и эксплойты (списках CVE), которые могут повлиять на устройство.</span><span class="sxs-lookup"><span data-stu-id="f5d82-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Изображение обнаруженной вкладки уязвимостей для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="f5d82-199">Представление по умолчанию содержит степень серьезности CVE, классификационный показатель уязвимости (CVS), программное обеспечение, связанное с CVE, при публикации CVE, при последнем обновлении и угрозах, связанных с CVE.</span><span class="sxs-lookup"><span data-stu-id="f5d82-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="f5d82-200">Как и в предыдущих вкладках, отображается количество отображаемых элементов и столбцы, которые могут быть настроены.</span><span class="sxs-lookup"><span data-stu-id="f5d82-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="f5d82-201">При выборе элемента в этом списке откроется всплывающее окно с описанием CVE.</span><span class="sxs-lookup"><span data-stu-id="f5d82-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="f5d82-202">Отсутствует КБ</span><span class="sxs-lookup"><span data-stu-id="f5d82-202">Missing KBs</span></span>

<span data-ttu-id="f5d82-203">На вкладке **пропущенные КБ** перечислены обновления Майкрософт, которые еще не были применены к устройству.</span><span class="sxs-lookup"><span data-stu-id="f5d82-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="f5d82-204">"КБ" (вопросы и ответы) — это [статьи базы знаний](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) , описывающие эти обновления; Например, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="f5d82-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Изображение отсутствующей вкладки КБ для профиля устройства](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="f5d82-206">Представление по умолчанию содержит сведения о бюллетенях, содержащих обновления, версию ОС, затронутые продукты, списках CVE, номер статьи базы знаний и теги.</span><span class="sxs-lookup"><span data-stu-id="f5d82-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="f5d82-207">Количество элементов, отображаемых на странице, и отображаемых столбцов, которые могут быть настроены.</span><span class="sxs-lookup"><span data-stu-id="f5d82-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="f5d82-208">При выборе элемента откроется всплывающее окно со ссылкой на обновление.</span><span class="sxs-lookup"><span data-stu-id="f5d82-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f5d82-209">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f5d82-209">Related topics</span></span>

* [<span data-ttu-id="f5d82-210">Обзор защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5d82-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="f5d82-211">Включение защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5d82-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="f5d82-212">Исследование сущностей на устройствах с использованием Live Response</span><span class="sxs-lookup"><span data-stu-id="f5d82-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="f5d82-213">Автоматическое исследование и реагирование (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="f5d82-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
