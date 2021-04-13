---
title: Уязвимости в организации — управление угрозами и уязвимостями
description: Списки распространенных уязвимостей и уязвимостей (CVE) ID слабых мест, найденных в программном обеспечении, запущенного в вашей организации. Обнаружено возможностями управления угрозами и уязвимостью Microsoft Defender для конечных точек.
keywords: mdatp threat &, threat and vulnerability management, mdatp tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0f573b2425764876e877de44555691979a0e1fcf
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689405"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="fd1e9-105">Уязвимости в организации — управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="fd1e9-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fd1e9-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fd1e9-106">**Applies to:**</span></span>
- [<span data-ttu-id="fd1e9-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fd1e9-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fd1e9-108">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="fd1e9-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="fd1e9-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd1e9-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fd1e9-110">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="fd1e9-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fd1e9-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="fd1e9-112">Управление угрозами и уязвимостями использует те же сигналы в защите конечной точки Defender для конечной точки Для сканирования и обнаружения уязвимостей.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="fd1e9-113">На **странице "Недостатки"** перечислены уязвимости программного обеспечения, на которые могут быть выставлены устройства, перечисляя общий ID уязвимостей и воздействий (CVE).</span><span class="sxs-lookup"><span data-stu-id="fd1e9-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="fd1e9-114">Вы также можете просмотреть степень серьезности, оценку системы оценки общей уязвимости (CVSS), распространенность в организации, соответствующие нарушения, сведения об угрозах и другие.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="fd1e9-115">Если для уязвимости не назначен официальный CVE-ID, имя уязвимости назначено управлением угрозами и уязвимостью.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="fd1e9-116">Чтобы получить сообщения о новых событиях уязвимости, см. в руб. Настройка уведомлений об уязвимости в [Microsoft Defender для endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="fd1e9-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="fd1e9-117">Перейдите на страницу "Слабые места"</span><span class="sxs-lookup"><span data-stu-id="fd1e9-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="fd1e9-118">Доступ к странице Недостатки несколько различных способов:</span><span class="sxs-lookup"><span data-stu-id="fd1e9-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="fd1e9-119">Выбор **слабых мест** из меню навигации по управлению угрозами и уязвимостью в [Центре безопасности Защитника Майкрософт](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fd1e9-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="fd1e9-120">Глобальный поиск</span><span class="sxs-lookup"><span data-stu-id="fd1e9-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="fd1e9-121">Меню навигации</span><span class="sxs-lookup"><span data-stu-id="fd1e9-121">Navigation menu</span></span>

<span data-ttu-id="fd1e9-122">Перейдите в меню навигации по управлению угрозами и уязвимостями и выберите **Недостатки,** чтобы открыть список резюме.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="fd1e9-123">Уязвимости в глобальном поиске</span><span class="sxs-lookup"><span data-stu-id="fd1e9-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="fd1e9-124">Перейдите в глобальное выпадаемое меню поиска.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="fd1e9-125">Выберите **ИД** уязвимости и ключа в ИД "Общие уязвимости и воздействия" (CVE), который вы ищете, а затем выберите значок поиска.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="fd1e9-126">Страница **"Слабые** места" открывается сведениями CVE, которые вы ищете.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="fd1e9-127">![Глобальное поле поиска с выбранным параметром "уязвимость" и примером CVE.](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="fd1e9-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="fd1e9-128">Выберите CVE, чтобы открыть панель вылетов с дополнительными сведениями, в том числе описанием уязвимости, сведениями, сведениями об угрозах и выставленными устройствами.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="fd1e9-129">Чтобы увидеть остальные уязвимости на странице **Недостатки,** введите CVE, а затем выберите поиск.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="fd1e9-130">Обзор слабых сторон</span><span class="sxs-lookup"><span data-stu-id="fd1e9-130">Weaknesses overview</span></span>

<span data-ttu-id="fd1e9-131">Исправление уязвимостей на открытых устройствах, чтобы снизить риск для ваших активов и организации.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="fd1e9-132">Если **столбец Exposed Devices** показывает 0, это означает, что вы не подвержены риску.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![Страница "Слабые места".](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="fd1e9-134">Сведения о нарушениях и угрозах</span><span class="sxs-lookup"><span data-stu-id="fd1e9-134">Breach and threat insights</span></span>

<span data-ttu-id="fd1e9-135">Просмотр всех связанных с этим нарушений и представлений об угрозах в столбце **Угроза,** когда значки окрашены в красный цвет.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="fd1e9-136">Всегда приоритизуйте рекомендации, связанные с текущими угрозами.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="fd1e9-137">Эти рекомендации отмечены значком "Понимание ![ угрозы" Простой рисунок красной ошибки.](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="fd1e9-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="fd1e9-138">и значок ![ проницательности нарушения Простой рисунок стрелки, поразив ](images/tvm_alert_icon.png) цель. .</span><span class="sxs-lookup"><span data-stu-id="fd1e9-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="fd1e9-139">Значок анализа нарушений выделяется при обнаружении уязвимости в организации.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="fd1e9-140">![Пример текста анализа нарушений, который может показываться при наведении на значок.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="fd1e9-141">В этой статье говорится, что "возможное активное оповещение связано с этой рекомендацией.](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="fd1e9-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="fd1e9-142">Значок сведения об угрозах выделяется, если в уязвимости, обнаруженной в организации, имеются связанные эксплойты.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="fd1e9-143">Наведении на значок показывает, является ли угроза частью набора эксплойтов или подключена к определенным расширенным устойчивым кампаниям или группам действий.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="fd1e9-144">При наличии имеется ссылка на отчет Threat Analytics с новостями об эксплуатации, раскрытием информации или связанными с ними советами по безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![Сведения об угрозах, которые могут показываться при наведении на значок.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="fd1e9-147">Получение информации об уязвимости</span><span class="sxs-lookup"><span data-stu-id="fd1e9-147">Gain vulnerability insights</span></span>

<span data-ttu-id="fd1e9-148">Если выбрать CVE, панель вылетов откроется дополнительными сведениями, такими как описание уязвимости, сведения, сведения об угрозах и выставленные устройства.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="fd1e9-149">Категория "ФУНКЦИЯ ОС" показана в соответствующих сценариях</span><span class="sxs-lookup"><span data-stu-id="fd1e9-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="fd1e9-150">Вы можете перейти к связанной рекомендации по безопасности для каждого CVE с выставленным устройством</span><span class="sxs-lookup"><span data-stu-id="fd1e9-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![Пример пролета слабых сторон.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="fd1e9-152">Программное обеспечение, которое не поддерживается</span><span class="sxs-lookup"><span data-stu-id="fd1e9-152">Software that isn't supported</span></span>

<span data-ttu-id="fd1e9-153">CvEs для программного обеспечения, которое в настоящее время не поддерживается управлением & уязвимостей, по-прежнему присутствует на странице Weaknesses.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="fd1e9-154">Поскольку программное обеспечение не поддерживается, доступны будут только ограниченные данные.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="fd1e9-155">Сведения об открытых устройствах не будут доступны для резюме с неподтверченным программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="fd1e9-156">Фильтруя неподтверченное программное обеспечение, выбрав параметр "Недоступный" в разделе "Подверженные устройствам".</span><span class="sxs-lookup"><span data-stu-id="fd1e9-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![Фильтр устройств, подвергаемой воздействию.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="fd1e9-158">Просмотр записей об общих уязвимостях и воздействиях (CVE) в других местах</span><span class="sxs-lookup"><span data-stu-id="fd1e9-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="fd1e9-159">Верхнее уязвимое программное обеспечение на панели мониторинга</span><span class="sxs-lookup"><span data-stu-id="fd1e9-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="fd1e9-160">Перейдите к панели мониторинга управления угрозами и [уязвимостью](tvm-dashboard-insights.md) и прокрутите вниз к **виджету верхнего уязвимого программного** обеспечения.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="fd1e9-161">Вы увидите количество уязвимостей, найденных в каждом программном обеспечении, а также сведения об угрозах и представление на высоком уровне экспозиции устройства с течением времени.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![Top vulnerable software card with four columns: software, weaknesses, threats, exposed devices.](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="fd1e9-163">Выберите программное обеспечение, которое необходимо исследовать, чтобы перейти на страницу сверления.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="fd1e9-164">Выберите **вкладку Обнаруженные уязвимости.**</span><span class="sxs-lookup"><span data-stu-id="fd1e9-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="fd1e9-165">Выберите уязвимость, которую необходимо исследовать, чтобы получить дополнительные сведения о деталях уязвимости</span><span class="sxs-lookup"><span data-stu-id="fd1e9-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Обзор сверлить Windows Server 2019.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="fd1e9-167">Обнаружение уязвимостей на странице устройства</span><span class="sxs-lookup"><span data-stu-id="fd1e9-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="fd1e9-168">Просмотр связанных сведений о недостатках на странице устройства.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="fd1e9-169">Перейдите к панели меню навигации Центра безопасности Microsoft Defender, а затем выберите значок устройства.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="fd1e9-170">Откроется **страница списка Устройств.**</span><span class="sxs-lookup"><span data-stu-id="fd1e9-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="fd1e9-171">На странице **Список устройств** выберите имя устройства, которое необходимо исследовать.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![Список устройств с выбранным устройством для исследования.](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="fd1e9-173">Страница устройства откроется с подробными сведениями и вариантами ответа для устройства, которое необходимо исследовать.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="fd1e9-174">Выберите **обнаруженные уязвимости.**</span><span class="sxs-lookup"><span data-stu-id="fd1e9-174">Select **Discovered vulnerabilities**.</span></span>

    ![Страница устройства с подробными сведениями и вариантами ответа.](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="fd1e9-176">Выберите уязвимость, которую необходимо исследовать, чтобы открыть панель вылетов с данными CVE, такими как: описание уязвимости, анализ угроз и логика обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="fd1e9-177">Логика обнаружения CVE</span><span class="sxs-lookup"><span data-stu-id="fd1e9-177">CVE Detection logic</span></span>

<span data-ttu-id="fd1e9-178">Как и данные программного обеспечения, теперь мы показывем логику обнаружения, которую мы применили на устройстве, чтобы указать, что оно уязвимо.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="fd1e9-179">Новый раздел называется "Логика обнаружения" (в любой обнаруженной уязвимости на странице устройства) и показывает логику обнаружения и источник.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="fd1e9-180">Категория "ФУНКЦИЯ ОС" также показана в соответствующих сценариях.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="fd1e9-181">CVE влияет на устройства с уязвимой ОС только в том случае, если включен определенный компонент ОС.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="fd1e9-182">Допустим, Windows Server 2019 имеет уязвимость в компоненте DNS.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="fd1e9-183">С помощью этой новой возможности мы прикрепим этот CVE только к устройствам Windows Server 2019 с возможностью DNS, включенной в их ОС.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![Пример логики обнаружения, в котором перечислены программное обеспечение, обнаруженное на устройстве и КБ.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="fd1e9-185">Неточность отчета</span><span class="sxs-lookup"><span data-stu-id="fd1e9-185">Report inaccuracy</span></span>

<span data-ttu-id="fd1e9-186">Сообщаем о ложном срабатыве, когда вы видите какие-либо расплывчатые, неточные или неполные сведения.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="fd1e9-187">Вы также можете сообщить о рекомендациях по безопасности, которые уже исправлены.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="fd1e9-188">Откройте CVE на странице Недостатки.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="fd1e9-189">Выберите **неточность** Отчета и откроется поле для вылетов.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="fd1e9-190">Выберите категорию неточности из выпадаемого меню и заполните адрес электронной почты и сведения о неточности.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="fd1e9-191">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-191">Select **Submit**.</span></span> <span data-ttu-id="fd1e9-192">Ваши отзывы немедленно отправляются специалистам по управлению угрозами и уязвимостями.</span><span class="sxs-lookup"><span data-stu-id="fd1e9-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fd1e9-193">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fd1e9-193">Related articles</span></span>

- [<span data-ttu-id="fd1e9-194">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="fd1e9-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="fd1e9-195">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="fd1e9-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="fd1e9-196">Инвентаризация программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="fd1e9-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="fd1e9-197">Панель мониторинга аналитики</span><span class="sxs-lookup"><span data-stu-id="fd1e9-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="fd1e9-198">Просмотр и организация списка конечных устройств Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="fd1e9-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
