---
title: Отслеживание и реагирование на возникающие угрозы с помощью аналитики угроз в Microsoft Defender ATP
ms.reviewer: ''
description: Узнайте о возникающих угрозах и методах атаки и о том, как их остановить. Оцените их влияние на организацию и оцените устойчивость организации.
keywords: аналитика угроз, оценка рисков, смягчение последствий ОС, смягчение микрокодов, состояние смягчения последствий
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f532d20e4fb7cfa101eb6b96a89a4dbc4e658956
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076861"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="b1c86-105">Отслеживание и реагирование на возникающие угрозы с помощью аналитики угроз</span><span class="sxs-lookup"><span data-stu-id="b1c86-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1c86-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b1c86-106">**Applies to:**</span></span>
- [<span data-ttu-id="b1c86-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b1c86-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b1c86-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1c86-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b1c86-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b1c86-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b1c86-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b1c86-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b1c86-111">При частом и распространенном распространении более сложных противников и новых угроз очень важно быстро:</span><span class="sxs-lookup"><span data-stu-id="b1c86-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="b1c86-112">Оценка влияния новых угроз</span><span class="sxs-lookup"><span data-stu-id="b1c86-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="b1c86-113">Проверка устойчивости к угрозам или воздействия на них</span><span class="sxs-lookup"><span data-stu-id="b1c86-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="b1c86-114">Определение действий, которые можно принять для остановки или сдерживания угроз</span><span class="sxs-lookup"><span data-stu-id="b1c86-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="b1c86-115">Аналитика угроз — это набор отчетов экспертов microsoft security researchers, охватывающих наиболее актуальные угрозы, в том числе:</span><span class="sxs-lookup"><span data-stu-id="b1c86-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="b1c86-116">Активные субъекты угроз и их кампании</span><span class="sxs-lookup"><span data-stu-id="b1c86-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="b1c86-117">Популярные и новые методы атаки</span><span class="sxs-lookup"><span data-stu-id="b1c86-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="b1c86-118">Критические уязвимости</span><span class="sxs-lookup"><span data-stu-id="b1c86-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="b1c86-119">Общие поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="b1c86-119">Common attack surfaces</span></span>
- <span data-ttu-id="b1c86-120">Распространенные вредоносные программы</span><span class="sxs-lookup"><span data-stu-id="b1c86-120">Prevalent malware</span></span>

<span data-ttu-id="b1c86-121">В каждом отчете содержится подробный анализ угрозы и подробные рекомендации по защите от этой угрозы.</span><span class="sxs-lookup"><span data-stu-id="b1c86-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="b1c86-122">В нее также включены данные из сети, указывающие, активна ли угроза и есть ли у вас применимые средства защиты.</span><span class="sxs-lookup"><span data-stu-id="b1c86-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="b1c86-123">Просмотрите это короткое видео, чтобы узнать больше о том, как аналитика угроз может помочь отслеживать последние угрозы и останавливать их.</span><span class="sxs-lookup"><span data-stu-id="b1c86-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="b1c86-124">Просмотр панели мониторинга аналитики угроз</span><span class="sxs-lookup"><span data-stu-id="b1c86-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="b1c86-125">Панель аналитики угроз — это отличное место для получения отчетов, наиболее важных для организации.</span><span class="sxs-lookup"><span data-stu-id="b1c86-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="b1c86-126">В нем подводятся итоги угроз в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b1c86-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="b1c86-127">**Последние угрозы**— списки недавно опубликованных отчетов об угрозах, а также количество устройств с активными и разрешенными оповещениями.</span><span class="sxs-lookup"><span data-stu-id="b1c86-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="b1c86-128">**Угрозы с высоким уровнем** воздействия — это списки угроз, которые оказали самое большое влияние на организацию.</span><span class="sxs-lookup"><span data-stu-id="b1c86-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="b1c86-129">В этом разделе вычислим угрозы по количеству устройств с активными оповещениями.</span><span class="sxs-lookup"><span data-stu-id="b1c86-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="b1c86-130">**Сводка угроз**— показывает общее влияние отслеживаемой угрозы, показывая количество угроз с активными и разрешенными оповещениями.</span><span class="sxs-lookup"><span data-stu-id="b1c86-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="b1c86-131">Выберите угрозу с панели мониторинга, чтобы просмотреть отчет об этой угрозе.</span><span class="sxs-lookup"><span data-stu-id="b1c86-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![Изображение панели аналитики угроз](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="b1c86-133">Просмотр отчета аналитики угроз</span><span class="sxs-lookup"><span data-stu-id="b1c86-133">View a threat analytics report</span></span>

<span data-ttu-id="b1c86-134">Каждый отчет аналитики угроз содержит сведения в трех разделах: **Обзор,** **отчет** аналитики и **сведения о смягчении последствий.**</span><span class="sxs-lookup"><span data-stu-id="b1c86-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="b1c86-135">Обзор. Быстрое понимание угрозы, оценка ее воздействия и проверка защиты</span><span class="sxs-lookup"><span data-stu-id="b1c86-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="b1c86-136">В **разделе Обзор** представлен предварительный просмотр подробного отчета аналитика.</span><span class="sxs-lookup"><span data-stu-id="b1c86-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="b1c86-137">Он также предоставляет диаграммы, которые подчеркивают влияние угрозы для организации и вашей экспозиции с помощью неправильно сконфигурованных и неоплаченных устройств.</span><span class="sxs-lookup"><span data-stu-id="b1c86-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="b1c86-138">![Изображение раздела обзор отчета аналитики угроз Обзор раздела ](images/ta-overview.png)
 _отчета аналитики угроз_</span><span class="sxs-lookup"><span data-stu-id="b1c86-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="b1c86-139">Оценка влияния на организацию</span><span class="sxs-lookup"><span data-stu-id="b1c86-139">Assess the impact to your organization</span></span>
<span data-ttu-id="b1c86-140">Каждый отчет содержит диаграммы, предназначенные для предоставления сведений о влиянии угрозы на организацию:</span><span class="sxs-lookup"><span data-stu-id="b1c86-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="b1c86-141">**Устройства с оповещениями**— показывают текущее число различных устройств, на которые повлияла угроза.</span><span class="sxs-lookup"><span data-stu-id="b1c86-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="b1c86-142">Устройство классифицируются как **Active,** если существует по крайней  мере  одно оповещение, связанное с этой угрозой, и разрешено, если все оповещения, связанные с угрозой на устройстве, устранены.</span><span class="sxs-lookup"><span data-stu-id="b1c86-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="b1c86-143">**Устройства с оповещениями со временем** показывают количество различных устройств с оповещений **Active** и **Resolved** с течением времени.</span><span class="sxs-lookup"><span data-stu-id="b1c86-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="b1c86-144">Количество разрешенных оповещений указывает, как быстро организация реагирует на оповещения, связанные с угрозой.</span><span class="sxs-lookup"><span data-stu-id="b1c86-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="b1c86-145">В идеале на диаграмме должны быть показаны оповещения, разрешенные в течение нескольких дней.</span><span class="sxs-lookup"><span data-stu-id="b1c86-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="b1c86-146">Проверка устойчивости и осанки безопасности</span><span class="sxs-lookup"><span data-stu-id="b1c86-146">Review security resilience and posture</span></span>
<span data-ttu-id="b1c86-147">Каждый отчет содержит диаграммы, в которых представлен обзор устойчивости организации к данной угрозе:</span><span class="sxs-lookup"><span data-stu-id="b1c86-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="b1c86-148">**Состояние конфигурации безопасности**— показывает количество устройств, которые применили рекомендуемые параметры безопасности, которые могут помочь уменьшить угрозу.</span><span class="sxs-lookup"><span data-stu-id="b1c86-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="b1c86-149">Устройства считаются **Безопасными,**  если они применили все отслеживаемые параметры.</span><span class="sxs-lookup"><span data-stu-id="b1c86-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="b1c86-150">**Состояние исправлений уязвимости**— показывает количество устройств, применяющих обновления или исправления безопасности, которые используют уязвимости, использованные угрозой.</span><span class="sxs-lookup"><span data-stu-id="b1c86-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="b1c86-151">Отчет аналитика: получите экспертную информацию от исследователей безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b1c86-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="b1c86-152">Перейдите в **раздел Отчет аналитика,** чтобы ознакомиться с подробным отчетом эксперта.</span><span class="sxs-lookup"><span data-stu-id="b1c86-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="b1c86-153">В большинстве отчетов подробно описаны цепочки атак, включая тактику и методы, относячимые к базе ATT MITRE&CK, исчерпывающие списки рекомендаций и мощные рекомендации по охоте на угрозы. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b1c86-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="b1c86-154">Дополнительные новости о отчете аналитика</span><span class="sxs-lookup"><span data-stu-id="b1c86-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="b1c86-155">Смягчение последствий: обзор списка смягчения последствий и состояния устройств</span><span class="sxs-lookup"><span data-stu-id="b1c86-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="b1c86-156">В разделе **Mitigations** просмотрите список конкретных рекомендаций, которые помогут повысить устойчивость организации к угрозе.</span><span class="sxs-lookup"><span data-stu-id="b1c86-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="b1c86-157">Список отслеживаемого смягчения включает в себя:</span><span class="sxs-lookup"><span data-stu-id="b1c86-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="b1c86-158">**Обновления безопасности**— развертывание обновлений или исправлений для уязвимостей</span><span class="sxs-lookup"><span data-stu-id="b1c86-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="b1c86-159">**Параметры антивируса Microsoft Defender**</span><span class="sxs-lookup"><span data-stu-id="b1c86-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="b1c86-160">Версия разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="b1c86-160">Security intelligence version</span></span>
  - <span data-ttu-id="b1c86-161">Защита с облачным доставкой</span><span class="sxs-lookup"><span data-stu-id="b1c86-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="b1c86-162">Защита потенциально нежелательного приложения (PUA)</span><span class="sxs-lookup"><span data-stu-id="b1c86-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="b1c86-163">Защита в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="b1c86-163">Real-time protection</span></span>
 
<span data-ttu-id="b1c86-164">Сведения о смягчении последствий в [](next-gen-threat-and-vuln-mgt.md)этом разделе включают данные управления угрозами и уязвимостями, которые также предоставляют подробные сведения о сработок из различных ссылок в отчете.</span><span class="sxs-lookup"><span data-stu-id="b1c86-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="b1c86-165">![Изображение раздела смягчения последствий раздела аналитики угроз в разделе ](images/ta-mitigations.png)
 _Mitigations_ отчета об аналитике угроз</span><span class="sxs-lookup"><span data-stu-id="b1c86-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="b1c86-166">Дополнительные сведения и ограничения отчета</span><span class="sxs-lookup"><span data-stu-id="b1c86-166">Additional report details and limitations</span></span>
<span data-ttu-id="b1c86-167">При использовании отчетов имейте в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="b1c86-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="b1c86-168">Объем данных основан на области управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b1c86-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="b1c86-169">Вы увидите состояние устройств в [группах, к которые можно получить доступ.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b1c86-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="b1c86-170">Диаграммы отражают только отслеживаемые меры по смягчению последствий.</span><span class="sxs-lookup"><span data-stu-id="b1c86-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="b1c86-171">Ознакомьтесь с обзором отчетов о дополнительных смягчениях, которые не показаны в диаграммах.</span><span class="sxs-lookup"><span data-stu-id="b1c86-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="b1c86-172">Смягчение последствий не гарантирует полную устойчивость.</span><span class="sxs-lookup"><span data-stu-id="b1c86-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="b1c86-173">Предоставленные меры по смягчению последствий отражают наилучшие действия, необходимые для повышения устойчивости.</span><span class="sxs-lookup"><span data-stu-id="b1c86-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="b1c86-174">Устройства считаются недоступными, если они не передают данные службе.</span><span class="sxs-lookup"><span data-stu-id="b1c86-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="b1c86-175">Статистика, связанная с антивирусом, основана на параметрах антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b1c86-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="b1c86-176">Устройства с сторонними антивирусными решениями могут отображаться как "открытые".</span><span class="sxs-lookup"><span data-stu-id="b1c86-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1c86-177">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b1c86-177">Related topics</span></span>
- [<span data-ttu-id="b1c86-178">Упреждающий поиск угроз с помощью продвинутой охоты</span><span class="sxs-lookup"><span data-stu-id="b1c86-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="b1c86-179">Понимание раздела отчетов аналитика</span><span class="sxs-lookup"><span data-stu-id="b1c86-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="b1c86-180">Оценка и устранение недостатков и воздействий безопасности</span><span class="sxs-lookup"><span data-stu-id="b1c86-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)