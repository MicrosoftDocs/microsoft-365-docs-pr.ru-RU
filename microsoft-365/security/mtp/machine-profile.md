---
title: Профиль компьютера на портале безопасности Microsoft 365
description: Просмотр уровней риска и экспозиции для устройства в Организации. Проанализируйте предыдущие и применяйте угрозы и Защитите компьютер последними обновлениями.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, защита от угроз Майкрософт, MTP, центр безопасности, пакет ATP ATP, Office 365 ATP, Azure ATP, страница компьютера, список компьютеров, профиль компьютера
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
ms.openlocfilehash: 7ab3f63008c65fca1a99128cc6f11f83bc86b2b4
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857698"
---
# <a name="machine-profile-page"></a><span data-ttu-id="c7d40-105">Страница профиля компьютера</span><span class="sxs-lookup"><span data-stu-id="c7d40-105">Machine profile page</span></span>

<span data-ttu-id="c7d40-106">Портал безопасности Microsoft 365 предоставляет страницы профиля компьютера, поэтому вы можете оценить работоспособность и состояние устройств в сети.</span><span class="sxs-lookup"><span data-stu-id="c7d40-106">The Microsoft 365 security portal provides you with Machine profile pages, so you can assess the health and status of devices on your network.</span></span> <span data-ttu-id="c7d40-107">Каждая страница профиля компьютера содержит обширную информацию об устройстве.</span><span class="sxs-lookup"><span data-stu-id="c7d40-107">Each Machine profile page contains a wealth of information about the device.</span></span>

<span data-ttu-id="c7d40-108">Вы можете просмотреть подробные сведения о выполняемом программном обеспечении, событиях и событиях безопасности, а также найти ссылки на релевантные пакеты программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c7d40-108">You can review in-depth information about what software it is running, any past and present security events or alerts, and find links to relevant software patches.</span></span>

<span data-ttu-id="c7d40-109">Вы также можете использовать профиль компьютера для выполнения распространенных задач, связанных с безопасностью, и быстро просмотреть основные сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="c7d40-109">You can also use the Machine profile to perform common security-related tasks, and quickly review basic details about the device.</span></span>

## <a name="navigating-the-machine-profile-page"></a><span data-ttu-id="c7d40-110">Навигация на странице профиля компьютера</span><span class="sxs-lookup"><span data-stu-id="c7d40-110">Navigating the Machine profile page</span></span>

<span data-ttu-id="c7d40-111">Доступ к странице профиля компьютера осуществляется путем непосредственного выбора имени устройства в списке компьютеров или с помощью кнопки **открыть компьютер** в меню список компьютеров.</span><span class="sxs-lookup"><span data-stu-id="c7d40-111">The Machine profile page can be accessed by directly selecting a device name on the Machines list or by choosing **Open Machine page** on the Machines list flyout.</span></span>

<span data-ttu-id="c7d40-112">После открытия страницы вы обнаружите, что она разбивается на три раздела.</span><span class="sxs-lookup"><span data-stu-id="c7d40-112">Once you have the page open, you'll find that it is broken up into three sections.</span></span>

![Изображение страницы профиля компьютера с (1) областью вкладок (2) Боковая панель и (3) действия, выделенные красным цветом](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

<span data-ttu-id="c7d40-114">Основная область содержимого (1) содержит семь вкладок, которые можно переключать для просмотра различных типов сведений о компьютере.</span><span class="sxs-lookup"><span data-stu-id="c7d40-114">The main content area (1) contains seven tabs that you can toggle through to view different kinds of information about the machine.</span></span>

<span data-ttu-id="c7d40-115">На боковой панели (2) приведены основные сведения о компьютере.</span><span class="sxs-lookup"><span data-stu-id="c7d40-115">The sidebar (2) lists basic details about the machine.</span></span>

<span data-ttu-id="c7d40-116">Кроме того, существуют действия ответа, доступные в заголовке (3) до боковой панели и основных разделов содержимого.</span><span class="sxs-lookup"><span data-stu-id="c7d40-116">There are also response actions available in a header (3) before the sidebar and main content sections.</span></span> <span data-ttu-id="c7d40-117">Вы можете использовать действия, указанные в этом заголовке, для выполнения распространенных задач, связанных с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="c7d40-117">You can use the actions in this header to perform common security-related tasks.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="c7d40-118">Раздел "Вкладки"</span><span class="sxs-lookup"><span data-stu-id="c7d40-118">Tabs section</span></span>

<span data-ttu-id="c7d40-119">Вкладки профиля компьютера позволяют переключать общие сведения о безопасности компьютера и таблицы, содержащие список оповещений, временной шкалы, список рекомендаций по безопасности, инвентаризации программного обеспечения, список обнаруженных уязвимостей и отсутствие КБ (обновления для системы безопасности).</span><span class="sxs-lookup"><span data-stu-id="c7d40-119">The Machine profile tabs allow you to toggle through an overview of security details about the machine, and tables containing a list of alerts, a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="c7d40-120">Вкладка "Обзор"</span><span class="sxs-lookup"><span data-stu-id="c7d40-120">Overview tab</span></span>

<span data-ttu-id="c7d40-121">Вкладка по умолчанию — **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="c7d40-121">The default tab is **Overview**.</span></span> <span data-ttu-id="c7d40-122">Он обеспечивает краткий обзор наиболее важного факта безопасности для устройства.</span><span class="sxs-lookup"><span data-stu-id="c7d40-122">It provides a quick look at the most important security fact about the device.</span></span>

![Изображение вкладки обзора для профиля компьютера](../../media/mtp-machine-profile/overview.png)

<span data-ttu-id="c7d40-124">Здесь вы можете найти диаграмму с уровнем риска и активными оповещениями, любыми вошедшими в систему пользователями, кратким списком наиболее и наименее часто работающих пользователей, а также оценками безопасности, подробно описывающими уровень доступности устройства, рекомендации по безопасности, уязвимое программное обеспечение и обнаруженные уязвимости.</span><span class="sxs-lookup"><span data-stu-id="c7d40-124">Here, you can find a chart of the device's risk level and active alerts, any currently logged on users, a brief list of most and least frequent users, and security assessments that detail the device's exposure level, security recommendations, affected software, and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="c7d40-125">Вкладка "оповещения"</span><span class="sxs-lookup"><span data-stu-id="c7d40-125">Alerts tab</span></span>

<span data-ttu-id="c7d40-126">Вкладка **оповещения** содержит список оповещений, зарегистрированных на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c7d40-126">The **Alerts** tab contains a list of alerts that have been reported on the device.</span></span>

![Изображение вкладки "оповещения" для профиля компьютера](../../media/mtp-machine-profile/alerts.png)

<span data-ttu-id="c7d40-128">Можно настроить количество отображаемых элементов, а также столбцы, отображаемые для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="c7d40-128">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="c7d40-129">По умолчанию в список задается по 30 элементов на страницу, а для отображения включается 11 столбцов.</span><span class="sxs-lookup"><span data-stu-id="c7d40-129">The default behavior is to list 30 items per page, and have 11 columns toggled on to display.</span></span>

<span data-ttu-id="c7d40-130">Столбцы на этой вкладке содержат сведения о серьезности угрозы, которое инициировало оповещение, а также состояние расследования, состояние расследования и лицо, которому назначено оповещение.</span><span class="sxs-lookup"><span data-stu-id="c7d40-130">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who if anyone the alert has been assigned to.</span></span>

<span data-ttu-id="c7d40-131">Столбец " *затронутые сущности* " ссылается на компьютер (объект), профиль которого в данный момент просматривается, а также все остальные машины в вашей сети, на которые влияет эта проблема.</span><span class="sxs-lookup"><span data-stu-id="c7d40-131">The *impacted entities* column refers to the machine (entity) whose profile you are currently viewing, plus any other machines in your network that are affected.</span></span>

<span data-ttu-id="c7d40-132">При выборе элемента в этом списке откроется ссылка на выбранное оповещение.</span><span class="sxs-lookup"><span data-stu-id="c7d40-132">Selecting an item from this list will open a link to the selected alert.</span></span>

<span data-ttu-id="c7d40-133">Этот список можно фильтровать по уровню серьезности, состоянию или уполномоченному.</span><span class="sxs-lookup"><span data-stu-id="c7d40-133">This list can be filtered by severity, status, or assignee.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="c7d40-134">Вкладка "временная шкала"</span><span class="sxs-lookup"><span data-stu-id="c7d40-134">Timeline tab</span></span>

<span data-ttu-id="c7d40-135">Вкладка **временная шкала** содержит интерактивный хронологический график событий, возникающих на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c7d40-135">The **Timeline** tab includes a interactive, chronological chart of events raised on the device.</span></span> <span data-ttu-id="c7d40-136">Перемещая выделенную область диаграммы, вы можете просматривать события в разных диапазонах времени.</span><span class="sxs-lookup"><span data-stu-id="c7d40-136">By moving the highlighted area of the chart, you can view events over different ranges of time.</span></span> <span data-ttu-id="c7d40-137">Вы также можете ввести настраиваемый диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="c7d40-137">You can also type in a custom range of dates.</span></span>

<span data-ttu-id="c7d40-138">Под диаграммой представлен список событий для выбранного диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="c7d40-138">Below the chart is a list of events for the selected range of dates.</span></span>

![Изображение вкладки временной шкалы для профиля компьютера](../../media/mtp-machine-profile/timeline.png)

<span data-ttu-id="c7d40-140">Количество отображаемых элементов и столбцов в списке можно изменить.</span><span class="sxs-lookup"><span data-stu-id="c7d40-140">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="c7d40-141">В столбцах по умолчанию перечислены время события, активный пользователь, тип действия, сущности (процессы) и дополнительные сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="c7d40-141">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="c7d40-142">При выборе элемента в списке откроется всплывающее окно с графиком сущностей события, в котором показаны родительские и дочерние процессы, вызвавшие событие.</span><span class="sxs-lookup"><span data-stu-id="c7d40-142">Selecting an item from the list will open a flyout displaying an Event entities graph, showing the parent and child processes that triggered the event.</span></span>

<span data-ttu-id="c7d40-143">Этот список можно фильтровать по определенному типу события; Например, события в реестре или события Smart Screen.</span><span class="sxs-lookup"><span data-stu-id="c7d40-143">This list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="c7d40-144">Вкладка "рекомендации по безопасности"</span><span class="sxs-lookup"><span data-stu-id="c7d40-144">Security recommendations tab</span></span>

<span data-ttu-id="c7d40-145">На вкладке **рекомендации по безопасности** перечислены действия, которые можно предпринять для защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="c7d40-145">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="c7d40-146">При выборе элемента в этом списке откроется раскрывающееся меню, в котором можно получить инструкции по применению рекомендации.</span><span class="sxs-lookup"><span data-stu-id="c7d40-146">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Изображение вкладки "рекомендации по обеспечению безопасности" для профиля компьютера](../../media/mtp-machine-profile/security-recs.png)

<span data-ttu-id="c7d40-148">Как и на предыдущих вкладках, количество элементов, отображаемых на странице, и столбцы, которые могут быть настроены.</span><span class="sxs-lookup"><span data-stu-id="c7d40-148">As with the previous tabs, the number of items displayed per page and which columns are visible can be customized.</span></span>

<span data-ttu-id="c7d40-149">Представление по умолчанию включает столбцы со сведениями о слабых слабых местах безопасности, связанной угрозой, связанным компонентом или программным обеспечением, на которые влияет угроза, и многое другое.</span><span class="sxs-lookup"><span data-stu-id="c7d40-149">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="c7d40-150">Элементы можно фильтровать по состоянию рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="c7d40-150">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="c7d40-151">Перечень программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="c7d40-151">Software inventory</span></span>

<span data-ttu-id="c7d40-152">На вкладке **Инвентаризация программного обеспечения** перечислены программное обеспечение, установленное на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c7d40-152">The **Software inventory** tab lists software installed on the device.</span></span>

![Изображение вкладки перечня программного обеспечения для профиля компьютера](../../media/mtp-machine-profile/software-inventory.png)

<span data-ttu-id="c7d40-154">Представление по умолчанию отображает поставщика программного обеспечения, установленного номера версии, количества известных слабых мест программного обеспечения, кода продукта и тегов.</span><span class="sxs-lookup"><span data-stu-id="c7d40-154">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="c7d40-155">Количество отображаемых элементов и отображаемых столбцов можно изменить.</span><span class="sxs-lookup"><span data-stu-id="c7d40-155">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="c7d40-156">При выборе элемента в этом списке открывается всплывающее окно с дополнительными сведениями о выбранном программном обеспечении, а также путь и временная метка для последнего найденного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c7d40-156">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="c7d40-157">Этот список можно фильтровать по коду продукта.</span><span class="sxs-lookup"><span data-stu-id="c7d40-157">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="c7d40-158">Вкладка обнаруженных уязвимостей</span><span class="sxs-lookup"><span data-stu-id="c7d40-158">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="c7d40-159">На вкладке **обнаруженные уязвимости** перечислены все распространенные уязвимости и эксплойты (списках CVE), которые могут повлиять на устройство.</span><span class="sxs-lookup"><span data-stu-id="c7d40-159">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Изображение обнаруженной вкладки уязвимостей для профиля компьютера](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

<span data-ttu-id="c7d40-161">Представление по умолчанию содержит степень серьезности CVE, классификационный показатель уязвимости (CVS), программное обеспечение, связанное с CVE, при публикации CVE, при последнем обновлении и угрозах, связанных с CVE.</span><span class="sxs-lookup"><span data-stu-id="c7d40-161">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="c7d40-162">Как и в предыдущих вкладках, отображается количество отображаемых элементов и столбцы, которые могут быть настроены.</span><span class="sxs-lookup"><span data-stu-id="c7d40-162">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="c7d40-163">При выборе элемента в этом списке откроется всплывающее окно с описанием CVE.</span><span class="sxs-lookup"><span data-stu-id="c7d40-163">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="c7d40-164">Отсутствует КБ</span><span class="sxs-lookup"><span data-stu-id="c7d40-164">Missing KBs</span></span>

<span data-ttu-id="c7d40-165">На вкладке **пропущенные КБ** перечислены обновления Майкрософт, которые еще не были применены к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c7d40-165">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the machine.</span></span> <span data-ttu-id="c7d40-166">"КБ" (вопросы и ответы) — это [статьи базы знаний](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) , описывающие эти обновления; Например, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="c7d40-166">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Изображение отсутствующей вкладки КБ для профиля компьютера](../../media/mtp-machine-profile/missing-kbs.PNG)

<span data-ttu-id="c7d40-168">Представление по умолчанию содержит сведения о бюллетенях, содержащих обновления, версию ОС, затронутые продукты, списках CVE, номер статьи базы знаний и теги.</span><span class="sxs-lookup"><span data-stu-id="c7d40-168">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="c7d40-169">Количество элементов, отображаемых на странице, и отображаемых столбцов, которые могут быть настроены.</span><span class="sxs-lookup"><span data-stu-id="c7d40-169">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="c7d40-170">При выборе элемента откроется всплывающее окно со ссылкой на обновление.</span><span class="sxs-lookup"><span data-stu-id="c7d40-170">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="sidebar"></a><span data-ttu-id="c7d40-171">Боковой панели</span><span class="sxs-lookup"><span data-stu-id="c7d40-171">Sidebar</span></span>

<span data-ttu-id="c7d40-172">Рядом с основной областью содержимого страницы профиля компьютера находится боковая панель.</span><span class="sxs-lookup"><span data-stu-id="c7d40-172">Beside the main content area of the Machine profile page is the sidebar.</span></span>

![Изображение вкладки боковой панели для профиля компьютера](../../media/mtp-machine-profile/sidebar.png)

<span data-ttu-id="c7d40-174">Боковая панель предоставляет некоторую важную информацию в небольших подразделах, которые можно переключать при открытии или закрытии:</span><span class="sxs-lookup"><span data-stu-id="c7d40-174">The sidebar provides some important basic information in small subsections which can be toggled open or closed:</span></span>

* <span data-ttu-id="c7d40-175">**Tags** — все теги, связанные с устройством</span><span class="sxs-lookup"><span data-stu-id="c7d40-175">**Tags** - Any tags associated with the device</span></span>
* <span data-ttu-id="c7d40-176">**Сведения о безопасности** : открытые инциденты, активные оповещения, уровень экспозиции и уровень риска</span><span class="sxs-lookup"><span data-stu-id="c7d40-176">**Security info** - Open incidents, active alerts, exposure level and risk level</span></span>
* <span data-ttu-id="c7d40-177">**Сведения об устройствах** : домен, ОС, группа активов, состояние работоспособности, чувствительность к данным и IP-адреса</span><span class="sxs-lookup"><span data-stu-id="c7d40-177">**Device details** - Domain, OS, Asset group, health state, data sensitivity, and IP addresses</span></span>
* <span data-ttu-id="c7d40-178">**Активность сети** — метки времени в первый раз и в последний раз, когда устройство просмотрелось в сети.</span><span class="sxs-lookup"><span data-stu-id="c7d40-178">**Network activity** - Timestamps for the first time and last time the device was seen on the network</span></span>

<span data-ttu-id="c7d40-179">Этот раздел также включает имя и уровень доступности устройства, а также значок, указывающий, активен ли он в данный момент в сети.</span><span class="sxs-lookup"><span data-stu-id="c7d40-179">This section also includes the name and exposure level of the device, and an icon to indicate if it is currently active on the network.</span></span>

## <a name="response-actions"></a><span data-ttu-id="c7d40-180">Действия отклика</span><span class="sxs-lookup"><span data-stu-id="c7d40-180">Response actions</span></span>

<span data-ttu-id="c7d40-181">Действия отклика предоставляют быстрый способ защиты от угроз и анализа угроз.</span><span class="sxs-lookup"><span data-stu-id="c7d40-181">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Изображение вкладки боковой панели для профиля компьютера](../../media/mtp-machine-profile/actions.PNG)

<span data-ttu-id="c7d40-183">Ниже перечислены действия, которые можно использовать для ответа.</span><span class="sxs-lookup"><span data-stu-id="c7d40-183">The response actions available to you here include:</span></span>

* <span data-ttu-id="c7d40-184">**Manage tagss** — обновления настраиваемые теги, примененные к этому устройству.</span><span class="sxs-lookup"><span data-stu-id="c7d40-184">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="c7d40-185">**Изоляция компьютера** изолирует компьютер от сети организации, не подключаясь к Advanced Threat Protection в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c7d40-185">**Isolate machine** - Isolates the machine from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="c7d40-186">Вы можете разрешить запуск Outlook, Teams и Skype для бизнеса, пока компьютер изолирован, в целях общения.</span><span class="sxs-lookup"><span data-stu-id="c7d40-186">You can choose to allow Outlook, Teams, and Skype for Business to run while the machine is isolated, for communication purposes.</span></span>
* <span data-ttu-id="c7d40-187">**Ограничьте выполнение приложения** — запрещает приложениям, которые не подписаны корпорацией Майкрософт на выполнение</span><span class="sxs-lookup"><span data-stu-id="c7d40-187">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running</span></span>
* <span data-ttu-id="c7d40-188">**Запуск антивирусной проверки** — обновление определений антивирусной программы "Защитник Windows" и немедленное выполнение антивирусной проверки.</span><span class="sxs-lookup"><span data-stu-id="c7d40-188">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="c7d40-189">Выбор между быстрым сканированием или полным сканированием.</span><span class="sxs-lookup"><span data-stu-id="c7d40-189">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="c7d40-190">**Сбор пакетов для расследования** — сбор сведений о компьютере.</span><span class="sxs-lookup"><span data-stu-id="c7d40-190">**Collect investigation package** - Gathers information about the machine.</span></span> <span data-ttu-id="c7d40-191">По завершении расследования вы можете скачать его.</span><span class="sxs-lookup"><span data-stu-id="c7d40-191">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="c7d40-192">**Initiate Live Response Session** — загружает удаленную оболочку на компьютере для [всестороннего расследования по безопасности](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="c7d40-192">**Initiate Live Response session** - Loads a remote shell on the machine for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="c7d40-193">**Initiate автоматизированное исследование** — автоматически [исследует и исправлять угрозы](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span><span class="sxs-lookup"><span data-stu-id="c7d40-193">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="c7d40-194">Несмотря на то, что вы можете вручную активировать автоматическое расследование для запуска с этой страницы, [некоторые политики оповещений](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) инициируют автоматическое расследование самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="c7d40-194">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="c7d40-195">**Центр уведомлений** — Просмотр состояния отправленных действий.</span><span class="sxs-lookup"><span data-stu-id="c7d40-195">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="c7d40-196">Доступно только в том случае, если уже было выбрано другое действие.</span><span class="sxs-lookup"><span data-stu-id="c7d40-196">Only available if another action has already been selected.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c7d40-197">См. также</span><span class="sxs-lookup"><span data-stu-id="c7d40-197">Related topics</span></span>

* [<span data-ttu-id="c7d40-198">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c7d40-198">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="c7d40-199">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c7d40-199">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="c7d40-200">Исследование сущностей на компьютерах с помощью Live Response</span><span class="sxs-lookup"><span data-stu-id="c7d40-200">Investigate entities on machines using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="c7d40-201">Автоматическое исследование и реагирование (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="c7d40-201">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
