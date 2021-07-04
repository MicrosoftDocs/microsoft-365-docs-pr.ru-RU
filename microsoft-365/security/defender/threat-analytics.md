---
title: Отслеживание возникающих угроз и реагирование на них с помощью аналитики угроз
ms.reviewer: ''
description: Узнайте о возникающих угрозах и методах атаки и о том, как их остановить. Оцените их влияние на организацию и оцените устойчивость организации.
keywords: аналитика угроз, оценка рисков, Microsoft 365 Defender, M365D, состояние смягчения, безопасная конфигурация, Microsoft Defender для Office 365, аналитика угроз Microsoft Defender для Office 365, аналитика угроз MDO, интегрированные данные аналитики угроз MDE и MDO, интеграция данных аналитики угроз, интегрированная Microsoft 365 Defender аналитика угроз
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c03dfef28744e2ee565c25d921902b8d11ecb7a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290247"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="8394d-105">Отслеживание возникающих угроз и реагирование на них с помощью аналитики угроз</span><span class="sxs-lookup"><span data-stu-id="8394d-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8394d-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8394d-106">**Applies to:**</span></span>
- <span data-ttu-id="8394d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8394d-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="8394d-108">Хотите попробовать Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="8394d-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="8394d-109">Вы можете [оценить его в лабораторной среде](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) или [запустить пилотный проект в производственной среде](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="8394d-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="8394d-110">Аналитика угроз — это наше решение для анализа угроз в продукте от экспертных исследователей безопасности Майкрософт, предназначенное для обеспечения максимальной эффективности групп безопасности при решении возникающих угроз, в том числе:</span><span class="sxs-lookup"><span data-stu-id="8394d-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="8394d-111">Активные субъекты угроз и их кампании</span><span class="sxs-lookup"><span data-stu-id="8394d-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="8394d-112">Популярные и новые методы атаки</span><span class="sxs-lookup"><span data-stu-id="8394d-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="8394d-113">Критические уязвимости</span><span class="sxs-lookup"><span data-stu-id="8394d-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="8394d-114">Общие поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="8394d-114">Common attack surfaces</span></span>
- <span data-ttu-id="8394d-115">Распространенные вредоносные программы</span><span class="sxs-lookup"><span data-stu-id="8394d-115">Prevalent malware</span></span>

<span data-ttu-id="8394d-116">Просмотрите это короткое видео, чтобы узнать больше о том, как аналитика угроз может помочь отслеживать последние угрозы и останавливать их.</span><span class="sxs-lookup"><span data-stu-id="8394d-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="8394d-117">Вы можете получить доступ к аналитике угроз либо с верхней левой стороны панели навигации Microsoft 365 портала безопасности, либо с выделенной карты мониторинга, на которой показаны главные угрозы в вашей организации. Получение видимости активных или текущих кампаний и знание действий с помощью аналитики угроз может помочь оснастить команду операций безопасности обоснованными решениями.</span><span class="sxs-lookup"><span data-stu-id="8394d-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![Изображение панели аналитики угроз](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="8394d-119">_Где получить доступ к аналитике угроз_</span><span class="sxs-lookup"><span data-stu-id="8394d-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="8394d-120">При частом и распространенном распространении более сложных противников и новых угроз очень важно быстро:</span><span class="sxs-lookup"><span data-stu-id="8394d-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="8394d-121">Определение и реагирование на возникающие угрозы</span><span class="sxs-lookup"><span data-stu-id="8394d-121">Identify and react to emerging threats</span></span>
- <span data-ttu-id="8394d-122">Узнайте, находятся ли вы в настоящее время под атакой</span><span class="sxs-lookup"><span data-stu-id="8394d-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="8394d-123">Оценка влияния угрозы для ваших активов</span><span class="sxs-lookup"><span data-stu-id="8394d-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="8394d-124">Проверка устойчивости к угрозам или воздействия на них</span><span class="sxs-lookup"><span data-stu-id="8394d-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="8394d-125">Определите меры по смягчению последствий, восстановлению или предотвращению, которые можно принять для остановки или сдерживания угроз.</span><span class="sxs-lookup"><span data-stu-id="8394d-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="8394d-126">В каждом отчете содержится анализ отслеживаемой угрозы и подробное руководство по защите от этой угрозы.</span><span class="sxs-lookup"><span data-stu-id="8394d-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="8394d-127">В нее также включены данные из сети, указывающие, активна ли угроза и есть ли у вас применимые средства защиты.</span><span class="sxs-lookup"><span data-stu-id="8394d-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="8394d-128">Просмотр панели мониторинга аналитики угроз</span><span class="sxs-lookup"><span data-stu-id="8394d-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="8394d-129">Панель мониторинга аналитики угроз[(security.microsoft.com/threatanalytics3)](https://security.microsoft.com/threatanalytics3)выделяет отчеты, наиболее релевантные для организации.</span><span class="sxs-lookup"><span data-stu-id="8394d-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="8394d-130">В нем подводятся итоги угроз в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="8394d-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="8394d-131">**Последние угрозы**— списки недавно опубликованных или обновленных отчетов об угрозах, а также количество активных и разрешенных оповещений.</span><span class="sxs-lookup"><span data-stu-id="8394d-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="8394d-132">**Угрозы с высоким уровнем** воздействия — это списки угроз, которые наиболее сильно влияют на организацию.</span><span class="sxs-lookup"><span data-stu-id="8394d-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="8394d-133">В этом разделе сначала перечислены угрозы с наивысшим числом активных и разрешенных оповещений.</span><span class="sxs-lookup"><span data-stu-id="8394d-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="8394d-134">**Сводка угроз**— обеспечивает общее влияние всех отслеживаемой угрозы, показывая количество угроз с активными и разрешенными оповещениями.</span><span class="sxs-lookup"><span data-stu-id="8394d-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="8394d-135">Выберите угрозу с панели мониторинга, чтобы просмотреть отчет об этой угрозе.</span><span class="sxs-lookup"><span data-stu-id="8394d-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![Снимок экрана панели аналитики угроз](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="8394d-137">_Панель мониторинга аналитики угроз. Вы также можете щелкнуть значок Поиска для ключа в ключевом слове, связанном с отчетом аналитики угроз, который вы хотите прочитать._</span><span class="sxs-lookup"><span data-stu-id="8394d-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="8394d-138">Просмотр отчета аналитики угроз</span><span class="sxs-lookup"><span data-stu-id="8394d-138">View a threat analytics report</span></span>

<span data-ttu-id="8394d-139">Каждый отчет аналитики угроз содержит сведения в нескольких разделах:</span><span class="sxs-lookup"><span data-stu-id="8394d-139">Each threat analytics report provides information in several sections:</span></span>

- [<span data-ttu-id="8394d-140">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="8394d-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses)
- [<span data-ttu-id="8394d-141">**Отчет аналитика**</span><span class="sxs-lookup"><span data-stu-id="8394d-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="8394d-142">**Связанные инциденты**</span><span class="sxs-lookup"><span data-stu-id="8394d-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="8394d-143">**Влияние активов**</span><span class="sxs-lookup"><span data-stu-id="8394d-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="8394d-144">**Предотвратимые попытки электронной почты**</span><span class="sxs-lookup"><span data-stu-id="8394d-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="8394d-145">**Смягчение последствий**</span><span class="sxs-lookup"><span data-stu-id="8394d-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="8394d-146">Обзор. Быстрое понимание угрозы, оценка ее воздействия и проверка защиты</span><span class="sxs-lookup"><span data-stu-id="8394d-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="8394d-147">В **разделе Обзор** представлен предварительный просмотр подробного отчета аналитика.</span><span class="sxs-lookup"><span data-stu-id="8394d-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="8394d-148">Он также предоставляет диаграммы, которые подчеркивают влияние угрозы для организации и вашей экспозиции с помощью неправильно сконфигурованных и неоплаченных устройств.</span><span class="sxs-lookup"><span data-stu-id="8394d-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![Изображение раздела обзор отчета аналитики угроз](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="8394d-150">_Обзор раздела отчета аналитики угроз_</span><span class="sxs-lookup"><span data-stu-id="8394d-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="8394d-151">Оценка влияния на организацию</span><span class="sxs-lookup"><span data-stu-id="8394d-151">Assess impact on your organization</span></span>

<span data-ttu-id="8394d-152">Каждый отчет содержит диаграммы, предназначенные для предоставления сведений о влиянии угрозы на организацию:</span><span class="sxs-lookup"><span data-stu-id="8394d-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>

- <span data-ttu-id="8394d-153">**Связанные инциденты**— это обзор воздействия отслеживаемой угрозы для организации с помощью следующих данных:</span><span class="sxs-lookup"><span data-stu-id="8394d-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="8394d-154">Количество активных оповещений и количество связанных с ними активных инцидентов</span><span class="sxs-lookup"><span data-stu-id="8394d-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="8394d-155">Серьезность активных инцидентов</span><span class="sxs-lookup"><span data-stu-id="8394d-155">Severity of active incidents</span></span>
- <span data-ttu-id="8394d-156">**Оповещения со временем**— показывает количество связанных оповещений **Active** и **Resolved** с течением времени.</span><span class="sxs-lookup"><span data-stu-id="8394d-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="8394d-157">Количество разрешенных оповещений указывает, как быстро организация реагирует на оповещения, связанные с угрозой.</span><span class="sxs-lookup"><span data-stu-id="8394d-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="8394d-158">В идеале на диаграмме должны быть показаны оповещения, разрешенные в течение нескольких дней.</span><span class="sxs-lookup"><span data-stu-id="8394d-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="8394d-159">**Влияние активов**— показывает количество различных устройств и учетных записей электронной почты (почтовых ящиков), которые в настоящее время имеют по крайней мере одно активное оповещение, связанное с отслеживаемой угрозой.</span><span class="sxs-lookup"><span data-stu-id="8394d-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="8394d-160">Оповещения срабатывает для почтовых ящиков, которые получали сообщения угрозы.</span><span class="sxs-lookup"><span data-stu-id="8394d-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="8394d-161">Просмотрите политики на уровне организаций и пользователей для переопределей, которые вызывают доставку электронных сообщений с угрозами.</span><span class="sxs-lookup"><span data-stu-id="8394d-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="8394d-162">**Предотвратимые** попытки электронной почты — показывает количество сообщений электронной почты за последние семь дней, которые были заблокированы перед доставкой или доставлены в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="8394d-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="8394d-163">Проверка устойчивости и осанки безопасности</span><span class="sxs-lookup"><span data-stu-id="8394d-163">Review security resilience and posture</span></span>

<span data-ttu-id="8394d-164">Каждый отчет содержит диаграммы, в которых представлен обзор устойчивости организации к данной угрозе:</span><span class="sxs-lookup"><span data-stu-id="8394d-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>

- <span data-ttu-id="8394d-165">**Состояние безопасной конфигурации**— отображает количество устройств с неправильными настройками безопасности.</span><span class="sxs-lookup"><span data-stu-id="8394d-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="8394d-166">Применение рекомендуемых параметров безопасности для смягчения угрозы.</span><span class="sxs-lookup"><span data-stu-id="8394d-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="8394d-167">Устройства считаются **Безопасными,**  если они применили все отслеживаемые параметры.</span><span class="sxs-lookup"><span data-stu-id="8394d-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="8394d-168">**Состояние исправления уязвимости**— показывает количество уязвимых устройств.</span><span class="sxs-lookup"><span data-stu-id="8394d-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="8394d-169">Применение обновлений или исправлений безопасности для устранения уязвимостей, использованных угрозой.</span><span class="sxs-lookup"><span data-stu-id="8394d-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

#### <a name="view-reports-per-threat-tags"></a><span data-ttu-id="8394d-170">Просмотр отчетов по тегам угроз</span><span class="sxs-lookup"><span data-stu-id="8394d-170">View reports per threat tags</span></span>

<span data-ttu-id="8394d-171">Вы можете фильтровать список отчетов об угрозах и просматривать наиболее релевантные отчеты в соответствии с определенным тегом угрозы (категория) или типом отчета.</span><span class="sxs-lookup"><span data-stu-id="8394d-171">You can filter the threat report list and view the most relevant reports according to a specific threat tag (category) or a report type.</span></span>

- <span data-ttu-id="8394d-172">**Теги угроз** помогают просматривать наиболее релевантные отчеты в соответствии с определенной категорией угроз.</span><span class="sxs-lookup"><span data-stu-id="8394d-172">**Threat tags**—assist you in viewing the most relevant reports according to a specific threat category.</span></span> <span data-ttu-id="8394d-173">Например, все отчеты, связанные с программой-вымогателями.</span><span class="sxs-lookup"><span data-stu-id="8394d-173">For example, all reports related to ransomware.</span></span>
- <span data-ttu-id="8394d-174">**Типы отчетов**— помогают просматривать наиболее релевантные отчеты в соответствии с определенным типом отчета.</span><span class="sxs-lookup"><span data-stu-id="8394d-174">**Report types**—assist you in viewing the most relevant reports according to a specific report type.</span></span> <span data-ttu-id="8394d-175">Например, все отчеты, которые охватывают инструменты и методы.</span><span class="sxs-lookup"><span data-stu-id="8394d-175">For example, all reports that cover tools and techniques.</span></span> 
- <span data-ttu-id="8394d-176">**Фильтры** помогают эффективно просматривать список отчетов об угрозах и фильтровать представление на основе определенного тега угрозы или типа отчета.</span><span class="sxs-lookup"><span data-stu-id="8394d-176">**Filters**—assist you in efficiently reviewing the threat report list and filtering the view based on a specific threat tag or report type.</span></span> <span data-ttu-id="8394d-177">Например, просмотрите все отчеты об угрозах, относящиеся к категории вымогателей, или отчеты об угрозах, которые охватывают уязвимости.</span><span class="sxs-lookup"><span data-stu-id="8394d-177">For example, review all threat reports related to ransomware category, or threat reports that cover vulnerabilities.</span></span>

##### <a name="how-does-it-work"></a><span data-ttu-id="8394d-178">Как это работает?</span><span class="sxs-lookup"><span data-stu-id="8394d-178">How does it work?</span></span>

<span data-ttu-id="8394d-179">Группа microsoft Threat Intelligence добавила теги угроз в каждый отчет об угрозах:</span><span class="sxs-lookup"><span data-stu-id="8394d-179">The Microsoft Threat Intelligence team has added threat tags to each threat report:</span></span>

- <span data-ttu-id="8394d-180">Теперь доступны четыре тега угрозы:</span><span class="sxs-lookup"><span data-stu-id="8394d-180">Four threat tags are now available:</span></span>
  - <span data-ttu-id="8394d-181">Вымогателей</span><span class="sxs-lookup"><span data-stu-id="8394d-181">Ransomware</span></span>
  - <span data-ttu-id="8394d-182">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="8394d-182">Phishing</span></span>
  - <span data-ttu-id="8394d-183">Уязвимость</span><span class="sxs-lookup"><span data-stu-id="8394d-183">Vulnerability</span></span>
  - <span data-ttu-id="8394d-184">Группа действий</span><span class="sxs-lookup"><span data-stu-id="8394d-184">Activity group</span></span>
- <span data-ttu-id="8394d-185">Теги угроз представлены в верхней части страницы аналитики угроз с счетчиками количества доступных отчетов под каждым тегом.</span><span class="sxs-lookup"><span data-stu-id="8394d-185">Threat tags are presented at the top of the threat analytics page, with counters for the number of available reports under each tag.</span></span>

  ![теги угроз](../../media/threat-analytics/ta-threattags-mtp.png)

- <span data-ttu-id="8394d-187">Список также можно сортировать по тегам угроз:</span><span class="sxs-lookup"><span data-stu-id="8394d-187">The list can also be sorted by threat tags:</span></span>

  ![lists](../../media/threat-analytics//ta-taglist-mtp.png)

- <span data-ttu-id="8394d-189">Фильтры доступны для каждого тега угрозы и типа отчета:</span><span class="sxs-lookup"><span data-stu-id="8394d-189">Filters are available per threat tag and report type:</span></span>

  ![фильтры](../../media/threat-analytics/ta-threattag-filters-mtp.png)

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="8394d-191">Отчет аналитика: получите экспертную информацию от исследователей безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8394d-191">Analyst report: Get expert insight from Microsoft security researchers</span></span>

<span data-ttu-id="8394d-192">В разделе **Отчет аналитика** ознакомьтесь с подробным отчетом эксперта.</span><span class="sxs-lookup"><span data-stu-id="8394d-192">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="8394d-193">В большинстве отчетов подробно описаны цепочки атак, включая тактику и методы, относячимые к базе ATT MITRE&CK, исчерпывающие списки рекомендаций и мощные рекомендации по охоте на угрозы. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8394d-193">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="8394d-194">Дополнительные новости о отчете аналитика</span><span class="sxs-lookup"><span data-stu-id="8394d-194">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="8394d-195">Связанные инциденты: просмотр и управление связанными инцидентами</span><span class="sxs-lookup"><span data-stu-id="8394d-195">Related incidents: View and manage related incidents</span></span>

<span data-ttu-id="8394d-196">На **вкладке Связанные инциденты** содержится список всех инцидентов, связанных с отслеживаемой угрозой.</span><span class="sxs-lookup"><span data-stu-id="8394d-196">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="8394d-197">Вы можете назначать инциденты или управлять оповещениями, связанными с каждым инцидентом.</span><span class="sxs-lookup"><span data-stu-id="8394d-197">You can assign incidents or manage alerts linked to each incident.</span></span> 


![Изображение раздела связанных инцидентов отчета аналитики угроз](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="8394d-199">_Раздел связанных инцидентов отчета аналитики угроз_</span><span class="sxs-lookup"><span data-stu-id="8394d-199">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="8394d-200">Влияние активов: получить список устройств и почтовых ящиков с влиянием</span><span class="sxs-lookup"><span data-stu-id="8394d-200">Impacted assets: Get list of impacted devices and mailboxes</span></span>

<span data-ttu-id="8394d-201">Актив считается затронутым, если он зависит от активного, неурегулированного оповещения.</span><span class="sxs-lookup"><span data-stu-id="8394d-201">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="8394d-202">На **вкладке Impacted assets** перечислены следующие типы активов с влиянием:</span><span class="sxs-lookup"><span data-stu-id="8394d-202">The **Impacted assets** tab lists the following types of impacted assets:</span></span>

- <span data-ttu-id="8394d-203">**Влияли устройства**— конечные точки с неурегулированными оповещениями Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="8394d-203">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="8394d-204">Как правило, эти оповещений повещают об известных индикаторах и действиях угроз.</span><span class="sxs-lookup"><span data-stu-id="8394d-204">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="8394d-205">**Повлияли почтовые ящики**— почтовые ящики, которые получили сообщения электронной почты, которые вызвали Microsoft Defender для Office 365 оповещений.</span><span class="sxs-lookup"><span data-stu-id="8394d-205">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="8394d-206">В то время как большинство сообщений, которые вызывают оповещения, как правило, блокируют, политики на уровне пользователя или организации могут переопределять фильтры.</span><span class="sxs-lookup"><span data-stu-id="8394d-206">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![Изображение раздела "Влияние активов" отчета аналитики угроз](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="8394d-208">_Раздел "Влияние на активы" отчета об аналитике угроз_</span><span class="sxs-lookup"><span data-stu-id="8394d-208">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="8394d-209">Предотвратимые попытки электронной почты: просмотр заблокированных или нежелательных сообщений угрозы</span><span class="sxs-lookup"><span data-stu-id="8394d-209">Prevented email attempts: View blocked or junked threat emails</span></span>

<span data-ttu-id="8394d-210">Microsoft Defender для Office 365 обычно блокирует сообщения электронной почты с известными индикаторами угроз, включая вредоносные ссылки или вложения.</span><span class="sxs-lookup"><span data-stu-id="8394d-210">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="8394d-211">В некоторых случаях механизмы активной фильтрации, проверяющие подозрительный контент, вместо этого отправляют сообщения угрозы в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="8394d-211">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="8394d-212">В любом случае вероятность запуска кода вредоносных программ на устройстве снижается.</span><span class="sxs-lookup"><span data-stu-id="8394d-212">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="8394d-213">В **вкладке "Предотвратить** попытки электронной почты" перечислены все электронные сообщения, которые были заблокированы перед доставкой или отправлены в папку нежелательной почты Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="8394d-213">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![Изображение раздела предотвратимые попытки электронной почты отчета аналитики угроз](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="8394d-215">_Раздел Предотвращение попыток электронной почты отчета аналитики угроз_</span><span class="sxs-lookup"><span data-stu-id="8394d-215">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="8394d-216">Смягчение последствий: обзор списка смягчения последствий и состояния устройств</span><span class="sxs-lookup"><span data-stu-id="8394d-216">Mitigations: Review list of mitigations and the status of your devices</span></span>

<span data-ttu-id="8394d-217">В разделе **Mitigations** просмотрите список конкретных рекомендаций, которые помогут повысить устойчивость организации к угрозе.</span><span class="sxs-lookup"><span data-stu-id="8394d-217">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="8394d-218">Список отслеживаемого смягчения включает в себя:</span><span class="sxs-lookup"><span data-stu-id="8394d-218">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="8394d-219">**Обновления безопасности —** развертывание поддерживаемых обновлений безопасности программного обеспечения для уязвимостей, найденных на бортовых устройствах</span><span class="sxs-lookup"><span data-stu-id="8394d-219">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="8394d-220">**Поддерживаемые конфигурации безопасности**</span><span class="sxs-lookup"><span data-stu-id="8394d-220">**Supported security configurations**</span></span>
  - <span data-ttu-id="8394d-221">Облачная защита</span><span class="sxs-lookup"><span data-stu-id="8394d-221">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="8394d-222">Защита потенциально нежелательного приложения (PUA)</span><span class="sxs-lookup"><span data-stu-id="8394d-222">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="8394d-223">Защита в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="8394d-223">Real-time protection</span></span>

<span data-ttu-id="8394d-224">Сведения о смягчении последствий в этом разделе включают данные из [контроль угроз и уязвимостей,](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)которые также предоставляют подробные сведения о сверлении из различных ссылок в отчете.</span><span class="sxs-lookup"><span data-stu-id="8394d-224">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

![Изображение раздела смягчения последствий отчета аналитики угроз, в котором показаны сведения о безопасной конфигурации](../../media/threat-analytics/ta_mitigations_mtp.png)

![Изображение раздела смягчения последствий отчета аналитики угроз, в котором показаны сведения об уязвимости](../../media/threat-analytics/ta_mitigations_mtp2.png)

<span data-ttu-id="8394d-227">_Раздел "Смягчение последствий" отчета об аналитике угроз_</span><span class="sxs-lookup"><span data-stu-id="8394d-227">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="8394d-228">Дополнительные сведения и ограничения отчета</span><span class="sxs-lookup"><span data-stu-id="8394d-228">Additional report details and limitations</span></span>

> [!NOTE]
> <span data-ttu-id="8394d-229">В рамках единой системы безопасности аналитика угроз теперь доступна не только для Microsoft Defender для конечной точки, но и для Microsoft Defender для Office владельцев лицензий E5.</span><span class="sxs-lookup"><span data-stu-id="8394d-229">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
>
> <span data-ttu-id="8394d-230">Если вы не используете портал Microsoft 365 безопасности (Microsoft 365 Defender), вы также можете увидеть сведения об отчете (без microsoft Defender для Office данных) на портале Центр безопасности в Microsoft Defender (Microsoft Defender для конечной точки).</span><span class="sxs-lookup"><span data-stu-id="8394d-230">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span>

<span data-ttu-id="8394d-231">Чтобы получить доступ к отчету аналитики угроз, необходимы определенные роли и разрешения.</span><span class="sxs-lookup"><span data-stu-id="8394d-231">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="8394d-232">Подробные сведения см. в пользовательских ролях в [области управления доступом на основе ролей Microsoft 365 Defender.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8394d-232">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>

- <span data-ttu-id="8394d-233">Чтобы просмотреть данные оповещений, инцидентов или сеяных активов, необходимо иметь разрешения в Microsoft Defender для Office или Microsoft Defender для данных оповещений endpoint или обоих.</span><span class="sxs-lookup"><span data-stu-id="8394d-233">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
- <span data-ttu-id="8394d-234">Чтобы просмотреть предотвратимые попытки электронной почты, необходимо иметь разрешения в Microsoft Defender для Office данных охоты.</span><span class="sxs-lookup"><span data-stu-id="8394d-234">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
- <span data-ttu-id="8394d-235">Чтобы просмотреть сведения о смягчении последствий, необходимо иметь разрешения на контроль угроз и уязвимостей данных в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8394d-235">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="8394d-236">При анализе данных аналитики угроз помните следующие факторы:</span><span class="sxs-lookup"><span data-stu-id="8394d-236">When looking at the threat analytics data, remember the following factors:</span></span>

- <span data-ttu-id="8394d-237">Диаграммы отражают только отслеживаемые меры по смягчению последствий.</span><span class="sxs-lookup"><span data-stu-id="8394d-237">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="8394d-238">Ознакомьтесь с обзором отчетов о дополнительных смягчениях, которые не показаны в диаграммах.</span><span class="sxs-lookup"><span data-stu-id="8394d-238">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="8394d-239">Смягчение последствий не гарантирует полную устойчивость.</span><span class="sxs-lookup"><span data-stu-id="8394d-239">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="8394d-240">Предоставленные меры по смягчению последствий отражают наилучшие действия, необходимые для повышения устойчивости.</span><span class="sxs-lookup"><span data-stu-id="8394d-240">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="8394d-241">Устройства считаются недоступными, если они не передают данные службе.</span><span class="sxs-lookup"><span data-stu-id="8394d-241">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="8394d-242">Статистика, связанная с антивирусом, основана на антивирусная программа в Microsoft Defender параметров.</span><span class="sxs-lookup"><span data-stu-id="8394d-242">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="8394d-243">Устройства с сторонними антивирусными решениями могут отображаться как "открытые".</span><span class="sxs-lookup"><span data-stu-id="8394d-243">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="8394d-244">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8394d-244">Related topics</span></span>

- [<span data-ttu-id="8394d-245">Упреждающий поиск угроз с помощью продвинутой охоты</span><span class="sxs-lookup"><span data-stu-id="8394d-245">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="8394d-246">Понимание раздела отчетов аналитика</span><span class="sxs-lookup"><span data-stu-id="8394d-246">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="8394d-247">Оценка и устранение недостатков и воздействий безопасности</span><span class="sxs-lookup"><span data-stu-id="8394d-247">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
