---
title: Инвентаризация программного обеспечения в управлении угрозами и уязвимостью
description: На странице инвентаризации программного обеспечения для microsoft Defender для управления угрозами и уязвимостями Endpoint показано, сколько недостатков и уязвимостей было обнаружено в программном обеспечении.
keywords: Управление угрозами и уязвимостью, Microsoft Defender для конечной точки, инвентаризация программного обеспечения Microsoft Defender для конечной точки, microsoft Defender for Endpoint threat &, Microsoft Defender for Endpoint threat & software inventory, Microsoft Defender for Endpoint tvm software inventory, tvm software inventory
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
ms.openlocfilehash: 0d270760cfed965c8190668afcdb1cc25223d2b1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933725"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a><span data-ttu-id="a256d-104">Инвентаризация программного обеспечения — управление угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="a256d-104">Software inventory - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a256d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a256d-105">**Applies to:**</span></span>
- [<span data-ttu-id="a256d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a256d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a256d-107">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="a256d-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a256d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a256d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a256d-109">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a256d-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a256d-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a256d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="a256d-111">Инвентаризация программного обеспечения в управлении угрозами и уязвимостями — это список известных программ в вашей организации с официальными перечисляниями общей платформы [(CPE).](https://nvd.nist.gov/products/cpe)</span><span class="sxs-lookup"><span data-stu-id="a256d-111">The software inventory in threat and vulnerability management is a list of known software in your organization with official [Common Platform Enumerations (CPE)](https://nvd.nist.gov/products/cpe).</span></span> <span data-ttu-id="a256d-112">Программные продукты без официального cpE не имеют опубликованных уязвимостей.</span><span class="sxs-lookup"><span data-stu-id="a256d-112">Software products without an official CPE don’t have vulnerabilities published.</span></span> <span data-ttu-id="a256d-113">Он также включает в себя такие сведения, как имя поставщика, количество слабых мест, угроз и количество выставленных устройств.</span><span class="sxs-lookup"><span data-stu-id="a256d-113">It also includes details such as the name of the vendor, number of weaknesses, threats, and number of exposed devices.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="a256d-114">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="a256d-114">How it works</span></span>

<span data-ttu-id="a256d-115">В области обнаружения мы будем использовать тот же набор сигналов, который отвечает за оценку обнаружения и уязвимости в Microsoft Defender для обнаружения конечных точек и возможностей [реагирования.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="a256d-115">In the field of discovery, we're leveraging the same set of signals that is responsible for detection and vulnerability assessment in [Microsoft Defender for Endpoint detection and response capabilities](overview-endpoint-detection-response.md).</span></span>

<span data-ttu-id="a256d-116">Так как это реальное время, за считанные минуты вы увидите сведения об уязвимости по мере их обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a256d-116">Since it's real time, in a matter of minutes, you'll see vulnerability information as they get discovered.</span></span> <span data-ttu-id="a256d-117">Двигатель автоматически получает сведения из нескольких каналов безопасности.</span><span class="sxs-lookup"><span data-stu-id="a256d-117">The engine automatically grabs information from multiple security feeds.</span></span> <span data-ttu-id="a256d-118">На самом деле вы увидите, подключено ли определенное программное обеспечение к кампании угроз в прямом эфире.</span><span class="sxs-lookup"><span data-stu-id="a256d-118">In fact, you'll see if a particular software is connected to a live threat campaign.</span></span> <span data-ttu-id="a256d-119">Он также предоставляет ссылку на отчет Threat Analytics, как только он будет доступен.</span><span class="sxs-lookup"><span data-stu-id="a256d-119">It also provides a link to a Threat Analytics report soon as it's available.</span></span>

## <a name="navigate-to-the-software-inventory-page"></a><span data-ttu-id="a256d-120">Перейдите на страницу инвентаризации программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="a256d-120">Navigate to the Software inventory page</span></span>

<span data-ttu-id="a256d-121">Доступ к странице инвентаризации  программного обеспечения, выбрав инвентаризацию программного обеспечения из меню навигации по управлению угрозами и уязвимостью в Центре безопасности [Microsoft Defender.](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a256d-121">Access the Software inventory page by selecting **Software inventory** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md).</span></span>

<span data-ttu-id="a256d-122">Просмотр программного обеспечения на определенных устройствах на отдельных страницах устройств из [списка устройств.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a256d-122">View software on specific devices in the individual devices pages from the [devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="a256d-123">Если вы ищете программное обеспечение с помощью глобального поиска Microsoft Defender для конечных точек, не забудьте поместить подчеркивать вместо пространства.</span><span class="sxs-lookup"><span data-stu-id="a256d-123">If you search for software using the Microsoft Defender for Endpoint global search, make sure to put an underscore instead of a space.</span></span> <span data-ttu-id="a256d-124">Например, для наилучших результатов поиска вместо "Windows 10" windows_10".</span><span class="sxs-lookup"><span data-stu-id="a256d-124">For example, for the best search results you'd write "windows_10" instead of "Windows 10".</span></span>

## <a name="software-inventory-overview"></a><span data-ttu-id="a256d-125">Обзор инвентаризации программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="a256d-125">Software inventory overview</span></span>

<span data-ttu-id="a256d-126">Страница **инвентаризации** программного обеспечения открывается со списком программного обеспечения, установленного в сети, включая имя поставщика, найденные недостатки, связанные с ними угрозы, выставленные устройства, влияние на оценку экспозиции и теги.</span><span class="sxs-lookup"><span data-stu-id="a256d-126">The **Software inventory** page opens with a list of software installed in your network, including the vendor name, weaknesses found, threats associated with them, exposed devices, impact to exposure score, and tags.</span></span>

<span data-ttu-id="a256d-127">Вы можете фильтровать представление списка на основе слабых мест, найденных в программном обеспечении, связанных с ними угроз, а также тегов, например, достиг ли программное обеспечение конечной поддержки.</span><span class="sxs-lookup"><span data-stu-id="a256d-127">You can filter the list view based on weaknesses found in the software, threats associated with them, and tags like whether the software has reached end-of-support.</span></span>

![Пример посадочной страницы для инвентаризации программного обеспечения.](images/tvm-software-inventory.png)

<span data-ttu-id="a256d-129">Выберите программное обеспечение, которое необходимо исследовать.</span><span class="sxs-lookup"><span data-stu-id="a256d-129">Select the software that you want to investigate.</span></span> <span data-ttu-id="a256d-130">Панель вылетов откроется с более компактным представлением сведений на странице.</span><span class="sxs-lookup"><span data-stu-id="a256d-130">A flyout panel will open with a more compact view of the information on the page.</span></span> <span data-ttu-id="a256d-131">Вы можете погрузиться глубже в исследование и выбрать страницу **Open software** или пометить любые технические несоответствия, выбрав неточность **Отчета.**</span><span class="sxs-lookup"><span data-stu-id="a256d-131">You can either dive deeper into the investigation and select **Open software page**, or flag any technical inconsistencies by selecting **Report inaccuracy**.</span></span>

### <a name="software-that-isnt-supported"></a><span data-ttu-id="a256d-132">Программное обеспечение, которое не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a256d-132">Software that isn't supported</span></span>

<span data-ttu-id="a256d-133">Программное обеспечение, которое в настоящее время не поддерживается управлением & уязвимостей, может присутствовать на странице инвентаризации программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="a256d-133">Software that isn't currently supported by threat & vulnerability management may be present in the Software inventory page.</span></span> <span data-ttu-id="a256d-134">Так как она не поддерживается, доступны будут только ограниченные данные.</span><span class="sxs-lookup"><span data-stu-id="a256d-134">Because it is not supported, only limited data will be available.</span></span> <span data-ttu-id="a256d-135">Фильтруя неподтверченное программное обеспечение с помощью параметра "Недоступный" в разделе "Слабость".</span><span class="sxs-lookup"><span data-stu-id="a256d-135">Filter by unsupported software with the "Not available" option in the "Weakness" section.</span></span>

![Неподтверченный программный фильтр.](images/tvm-unsupported-software-filter.png)

<span data-ttu-id="a256d-137">Ниже указывается, что программное обеспечение не поддерживается:</span><span class="sxs-lookup"><span data-stu-id="a256d-137">The following indicates that a software is not supported:</span></span>

- <span data-ttu-id="a256d-138">Поле Недостатки показывает "Недоступный"</span><span class="sxs-lookup"><span data-stu-id="a256d-138">Weaknesses field shows "Not available"</span></span>
- <span data-ttu-id="a256d-139">В поле выставленных устройств показана тире</span><span class="sxs-lookup"><span data-stu-id="a256d-139">Exposed devices field shows a dash</span></span>
- <span data-ttu-id="a256d-140">Информационный текст, добавленный в боковой панели и на странице программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="a256d-140">Informational text added in side panel and in software page</span></span>
- <span data-ttu-id="a256d-141">На странице программного обеспечения не будут иметься рекомендации по безопасности, обнаруженные уязвимости или разделы временной шкалы событий</span><span class="sxs-lookup"><span data-stu-id="a256d-141">The software page won't have the security recommendations, discovered vulnerabilities, or event timeline sections</span></span>

<span data-ttu-id="a256d-142">В настоящее время продукты без CPE не показаны на странице инвентаризации программного обеспечения, только в инвентаризации программного обеспечения уровня устройства.</span><span class="sxs-lookup"><span data-stu-id="a256d-142">Currently, products without a CPE are not shown in the software inventory page, only in the device level software inventory.</span></span>

## <a name="software-inventory-on-devices"></a><span data-ttu-id="a256d-143">Инвентаризация программного обеспечения на устройствах</span><span class="sxs-lookup"><span data-stu-id="a256d-143">Software inventory on devices</span></span>

<span data-ttu-id="a256d-144">Из панели навигации Центра безопасности Microsoft Defender перейдите в список **[Устройств.](machines-view-overview.md)**</span><span class="sxs-lookup"><span data-stu-id="a256d-144">From the Microsoft Defender Security Center navigation panel, go to the **[Devices list](machines-view-overview.md)**.</span></span> <span data-ttu-id="a256d-145">Выберите имя устройства, чтобы открыть страницу устройства (например,  Computer1), а затем выберите вкладку инвентаризации программного обеспечения, чтобы увидеть список всех известных программ, присутствующих на устройстве.</span><span class="sxs-lookup"><span data-stu-id="a256d-145">Select the name of a device to open the device page (like Computer1), then select the **Software inventory** tab to see a list of all the known software present on the device.</span></span> <span data-ttu-id="a256d-146">Выберите определенную запись программного обеспечения, чтобы открыть вылет с дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="a256d-146">Select a specific software entry to open the flyout with more information.</span></span>

<span data-ttu-id="a256d-147">Программное обеспечение может быть видно на уровне устройства, даже если оно в настоящее время не поддерживается управлением угрозами и уязвимостью.</span><span class="sxs-lookup"><span data-stu-id="a256d-147">Software may be visible at the device level even if it is currently not supported by threat and vulnerability management.</span></span> <span data-ttu-id="a256d-148">Однако будут доступны только ограниченные данные.</span><span class="sxs-lookup"><span data-stu-id="a256d-148">However, only limited data will be available.</span></span> <span data-ttu-id="a256d-149">Вы узнаете, не является ли программное обеспечение неподтверченным, так как оно будет говорить "Недоступны" в столбце "Слабость".</span><span class="sxs-lookup"><span data-stu-id="a256d-149">You'll know if software is unsupported because it will say "Not available" in the "Weakness" column.</span></span>

<span data-ttu-id="a256d-150">Программное обеспечение без CPE также может показываться в этом инвентаре определенного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="a256d-150">Software with no CPE can also show up under this device specific software inventory.</span></span>

### <a name="software-evidence"></a><span data-ttu-id="a256d-151">Доказательства программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="a256d-151">Software evidence</span></span>

<span data-ttu-id="a256d-152">См. данные о том, где мы обнаружили определенное программное обеспечение на устройстве из реестра, диска или обоих. Его можно найти на любом устройстве в инвентаре программного обеспечения устройства.</span><span class="sxs-lookup"><span data-stu-id="a256d-152">See evidence of where we detected a specific software on a device from the registry, disk, or both.You can find it on any device in the device software inventory.</span></span>

<span data-ttu-id="a256d-153">Выберите имя программного обеспечения, чтобы открыть флайер, и посмотрите раздел под названием "Software Evidence".</span><span class="sxs-lookup"><span data-stu-id="a256d-153">Select a software name to open the flyout, and look for the section called "Software Evidence."</span></span>

![Пример доказательства программного обеспечения Windows 10 из списка устройств, показывающий путь реестра доказательств программного обеспечения.](images/tvm-software-evidence.png)

## <a name="software-pages"></a><span data-ttu-id="a256d-155">Страницы программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="a256d-155">Software pages</span></span>

<span data-ttu-id="a256d-156">Страницы программного обеспечения можно просмотреть несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="a256d-156">You can view software pages a few different ways:</span></span>

- <span data-ttu-id="a256d-157">Страница инвентаризации программного обеспечения > выберите имя программного > **Выберите** страницу открытого программного обеспечения в вылете</span><span class="sxs-lookup"><span data-stu-id="a256d-157">Software inventory page > Select a software name > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="a256d-158">[Страница рекомендации по](tvm-security-recommendation.md) безопасности > выберите > **выберите** открытую страницу программного обеспечения в вылете</span><span class="sxs-lookup"><span data-stu-id="a256d-158">[Security recommendations page](tvm-security-recommendation.md) > Select a recommendation > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="a256d-159">[Страница временной](threat-and-vuln-mgt-event-timeline.md) шкалы событий > Выберите событие > Выберите имя гиперссылкой программного обеспечения (например, Visual Studio 2017 г.) в разделе "Связанный компонент" в вылете</span><span class="sxs-lookup"><span data-stu-id="a256d-159">[Event timeline page](threat-and-vuln-mgt-event-timeline.md) > Select an event > Select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout</span></span>

 <span data-ttu-id="a256d-160">Полная страница будет отображаться со всеми сведениями о определенном программном обеспечении и следующей информацией:</span><span class="sxs-lookup"><span data-stu-id="a256d-160">A full page will appear with all the details of a specific software and the following information:</span></span>

- <span data-ttu-id="a256d-161">Боковая панель с сведениями о поставщике, распространенность программного обеспечения в организации (включая количество установленных на нем устройств, а также открытые устройства, которые не исправлены), доступ и использование, а также влияние на оценку экспозиции.</span><span class="sxs-lookup"><span data-stu-id="a256d-161">Side panel with vendor information, prevalence of the software in the organization (including number of devices it's installed on, and exposed devices that aren't patched), whether and exploit is available, and impact to your exposure score.</span></span>
- <span data-ttu-id="a256d-162">Визуализации данных с указанием количества и серьезности уязвимостей и неправильной оценки.</span><span class="sxs-lookup"><span data-stu-id="a256d-162">Data visualizations showing the number of, and severity of, vulnerabilities and misconfigurations.</span></span> <span data-ttu-id="a256d-163">Кроме того, графики с количеством выставленных устройств.</span><span class="sxs-lookup"><span data-stu-id="a256d-163">Also, graphs with the number of exposed devices.</span></span>
- <span data-ttu-id="a256d-164">Вкладки, показывающие такие сведения, как:</span><span class="sxs-lookup"><span data-stu-id="a256d-164">Tabs showing information such as:</span></span>
    - <span data-ttu-id="a256d-165">Соответствующие рекомендации по безопасности для выявленных недостатков и уязвимостей.</span><span class="sxs-lookup"><span data-stu-id="a256d-165">Corresponding security recommendations for the weaknesses and vulnerabilities identified.</span></span>
    - <span data-ttu-id="a256d-166">Именуются резюме обнаруженных уязвимостей.</span><span class="sxs-lookup"><span data-stu-id="a256d-166">Named CVEs of discovered vulnerabilities.</span></span>
    - <span data-ttu-id="a256d-167">Устройства с установленным программным обеспечением (наряду с именем устройства, доменом, ОС и другими).</span><span class="sxs-lookup"><span data-stu-id="a256d-167">Devices that have the software installed (along with device name, domain, OS, and more).</span></span>
    - <span data-ttu-id="a256d-168">Список версий программного обеспечения (включая количество устройств, на которых установлена версия, количество обнаруженных уязвимостей и имена установленных устройств).</span><span class="sxs-lookup"><span data-stu-id="a256d-168">Software version list (including number of devices the version is installed on, the number of discovered vulnerabilities, and the names of the installed devices).</span></span>

    ![Страница примера программного обеспечения для Visual Studio 2017 с подробными сведениями о программном обеспечении, недостатками, выставленными устройствами и другими.](images/tvm-software-page-example.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="a256d-170">Неточность отчета</span><span class="sxs-lookup"><span data-stu-id="a256d-170">Report inaccuracy</span></span>

<span data-ttu-id="a256d-171">Сообщаем о ложном срабатыве, когда вы видите какие-либо расплывчатые, неточные или неполные сведения.</span><span class="sxs-lookup"><span data-stu-id="a256d-171">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="a256d-172">Вы также можете сообщить о рекомендациях по безопасности, которые уже исправлены.</span><span class="sxs-lookup"><span data-stu-id="a256d-172">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="a256d-173">Откройте вылет программного обеспечения на странице инвентаризации программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="a256d-173">Open the software flyout on the Software inventory page.</span></span>
2. <span data-ttu-id="a256d-174">Выберите **неточность отчета.**</span><span class="sxs-lookup"><span data-stu-id="a256d-174">Select **Report inaccuracy**.</span></span>
3. <span data-ttu-id="a256d-175">Из области вылетов выберите категорию неточности из выпадаемого меню, заполните адрес электронной почты и сведения о неточности.</span><span class="sxs-lookup"><span data-stu-id="a256d-175">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details about the inaccuracy.</span></span>
4. <span data-ttu-id="a256d-176">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="a256d-176">Select **Submit**.</span></span> <span data-ttu-id="a256d-177">Ваши отзывы немедленно отправляются специалистам по управлению угрозами и уязвимостями.</span><span class="sxs-lookup"><span data-stu-id="a256d-177">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a256d-178">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a256d-178">Related articles</span></span>

- [<span data-ttu-id="a256d-179">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="a256d-179">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a256d-180">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="a256d-180">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="a256d-181">Временная шкала события</span><span class="sxs-lookup"><span data-stu-id="a256d-181">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
- [<span data-ttu-id="a256d-182">Просмотр и организация списка конечных устройств Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="a256d-182">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
