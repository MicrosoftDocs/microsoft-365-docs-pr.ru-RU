---
title: Рекомендации по безопасности с помощью управления угрозами и уязвимостями
description: В управлении угрозами и уязвимостью получите рекомендации по безопасности, которые можно использовать в качестве приоритета с помощью угрозы, вероятности нарушения и значения.
keywords: Управление угрозами и уязвимостью, рекомендация по безопасности microsoft Defender для endpoint tvm, рекомендация по кибербезопасности, рекомендация по безопасности
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
ms.openlocfilehash: af22bac911339de9c2e02df24a77c1889a33d43a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933737"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="3fa9b-104">Рекомендации по безопасности — управление угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="3fa9b-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3fa9b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3fa9b-105">**Applies to:**</span></span>

- [<span data-ttu-id="3fa9b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3fa9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3fa9b-107">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="3fa9b-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3fa9b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3fa9b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3fa9b-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3fa9b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3fa9b-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="3fa9b-111">Слабые стороны кибербезопасности, выявленные в организации, сооружаются с рекомендациями по безопасности, которые можно действовать, и приоритизируются по их воздействию.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="3fa9b-112">Рекомендации с приоритетами помогают сократить время для устранения или устранения уязвимостей и обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="3fa9b-113">Каждая рекомендация по безопасности включает действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="3fa9b-114">Чтобы помочь в управлении задачами, рекомендации также можно отправить с помощью Microsoft Intune и Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="3fa9b-115">При изменениях ландшафта угроз рекомендация также изменяется по мере непрерывного сбора сведений из среды.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="3fa9b-116">Чтобы получить сообщения о новых событиях уязвимости, см. в руб. Настройка уведомлений об уязвимости в [Microsoft Defender для endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="3fa9b-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="3fa9b-117">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="3fa9b-117">How it works</span></span>

<span data-ttu-id="3fa9b-118">Каждое устройство в организации засмеяно на основе трех важных факторов, которые помогают клиентам сосредоточиться на правильных вещах в нужное время.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="3fa9b-119">**Threat** — характеристики уязвимостей и эксплойтов в устройствах организации и истории нарушений.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="3fa9b-120">На основе этих факторов рекомендации по безопасности показывают соответствующие ссылки на активные оповещения, текущие кампании угроз и соответствующие аналитические отчеты об угрозах.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="3fa9b-121">**Вероятность нарушения** — осанка безопасности и устойчивость организации к угрозам</span><span class="sxs-lookup"><span data-stu-id="3fa9b-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="3fa9b-122">**Бизнес-значение** — активы, критически важные процессы и интеллектуальные свойства вашей организации</span><span class="sxs-lookup"><span data-stu-id="3fa9b-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="3fa9b-123">Перейдите на страницу Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="3fa9b-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="3fa9b-124">Доступ к странице Рекомендации по безопасности можно найти несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="3fa9b-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="3fa9b-125">Меню навигации по управлению угрозами и уязвимостью в [Центре безопасности Защитника Майкрософт](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3fa9b-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="3fa9b-126">Рекомендации по безопасности в панели управления [угрозами и уязвимостью](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="3fa9b-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="3fa9b-127">Просмотр соответствующих рекомендаций по безопасности в следующих местах:</span><span class="sxs-lookup"><span data-stu-id="3fa9b-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="3fa9b-128">Страница программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="3fa9b-128">Software page</span></span>
- <span data-ttu-id="3fa9b-129">Страница устройства</span><span class="sxs-lookup"><span data-stu-id="3fa9b-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="3fa9b-130">Меню навигации</span><span class="sxs-lookup"><span data-stu-id="3fa9b-130">Navigation menu</span></span>

<span data-ttu-id="3fa9b-131">Перейдите к меню навигации по управлению угрозами и уязвимостями и выберите **рекомендации по безопасности.**</span><span class="sxs-lookup"><span data-stu-id="3fa9b-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="3fa9b-132">На странице содержится список рекомендаций по безопасности для угроз и уязвимостей, найденных в организации.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="3fa9b-133">Рекомендации по безопасности в панели управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="3fa9b-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="3fa9b-134">В данный день в качестве администратора безопасности вы [](tvm-dashboard-insights.md) можете взглянуть на панель [](tvm-exposure-score.md) мониторинга управления угрозами и уязвимостью, чтобы увидеть оценку экспозиции рядом с показателем microsoft [Secure Score для устройств.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="3fa9b-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="3fa9b-135">Цель состоит в **том,** чтобы снизить степень  уязвимости вашей организации и повысить безопасность устройств организации, чтобы быть более устойчивыми к атакам угроз кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="3fa9b-136">Верхний список рекомендаций по безопасности поможет вам достичь этой цели.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-136">The top security recommendations list can help you achieve that goal.</span></span>

![Пример карточки Рекомендации по безопасности с четырьмя рекомендациями по безопасности.](images/top-security-recommendations350.png)

<span data-ttu-id="3fa9b-138">В верхних рекомендациях по безопасности перечисляются возможности улучшения, приоритизированные на основе важных факторов, упомянутых в предыдущем разделе, — угрозы, вероятности нарушения и значения.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="3fa9b-139">Выбор рекомендации поможет вам найти дополнительные сведения на странице рекомендации по безопасности.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="3fa9b-140">Обзор рекомендаций по безопасности</span><span class="sxs-lookup"><span data-stu-id="3fa9b-140">Security recommendations overview</span></span>

<span data-ttu-id="3fa9b-141">Просмотр рекомендаций, количество найденных слабых мест, связанных компонентов, анализ угроз, количество выставленных устройств, состояние, тип исправлений, действия по исправлению, влияние на оценку экспозиции и Microsoft Secure Score для устройств и связанные теги.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="3fa9b-142">Цвет диаграммы **подверженных устройств** изменяется по мере изменения тренда.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="3fa9b-143">Если количество выставленных устройств растет, цвет меняется на красный.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="3fa9b-144">Если количество выставленных устройств уменьшится, цвет графа изменится на зеленый.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="3fa9b-145">Управление угрозами и уязвимостью показывает устройства, которые использовались до **30 дней** назад.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="3fa9b-146">Это отличается от остальной части Microsoft Defender для конечной точки, где если устройство не используется более 7 дней, оно имеет статус "Неактивно".</span><span class="sxs-lookup"><span data-stu-id="3fa9b-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![Пример посадочной страницы для рекомендаций по безопасности.](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="3fa9b-148">Значки</span><span class="sxs-lookup"><span data-stu-id="3fa9b-148">Icons</span></span>

<span data-ttu-id="3fa9b-149">Полезные значки также быстро обращают ваше внимание на:</span><span class="sxs-lookup"><span data-stu-id="3fa9b-149">Useful icons also quickly call your attention to:</span></span>
- ![стрелка, попав в цель](images/tvm_alert_icon.png) <span data-ttu-id="3fa9b-151">возможные активные оповещения</span><span class="sxs-lookup"><span data-stu-id="3fa9b-151">possible active alerts</span></span>
- ![красный баг](images/tvm_bug_icon.png) <span data-ttu-id="3fa9b-153">связанные общедоступные эксплойты</span><span class="sxs-lookup"><span data-stu-id="3fa9b-153">associated public exploits</span></span>
- ![лампочка](images/tvm_insight_icon.png) <span data-ttu-id="3fa9b-155">рекомендации</span><span class="sxs-lookup"><span data-stu-id="3fa9b-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="3fa9b-156">Ознакомьтесь с вариантами рекомендаций по безопасности</span><span class="sxs-lookup"><span data-stu-id="3fa9b-156">Explore security recommendation options</span></span>

<span data-ttu-id="3fa9b-157">Выберите рекомендации по безопасности, которые необходимо исследовать или обработать.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-157">Select the security recommendation that you want to investigate or process.</span></span>

![Пример страницы вылетов рекомендаций по безопасности.](images/secrec-flyouteolsw.png)

<span data-ttu-id="3fa9b-159">Из вылета можно выбрать любой из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="3fa9b-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="3fa9b-160">**Откройте страницу** программного обеспечения . Откройте страницу программного обеспечения, чтобы получить дополнительный контекст для программного обеспечения и его распространения.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="3fa9b-161">Эти сведения могут включать контекст угроз, связанные рекомендации, обнаруженные недостатки, количество открытых устройств, обнаруженные уязвимости, имена и подробные сведения о устройствах с установленным программным обеспечением и распространение версий.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="3fa9b-162">[**Параметры исправлений**](tvm-remediation.md) . Отправьте запрос на исправление для открытия билета в Microsoft Intune для ИТ-администратора для выбора и адреса.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="3fa9b-163">Отслеживание действия по исправлению на странице Исправление.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="3fa9b-164">[**Параметры исключения**](tvm-exception.md) . Отправка исключения, обоснование и задайте продолжительность исключения, если вы еще не можете устранять проблему.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="3fa9b-165">При изменении программного обеспечения на устройстве обычно требуется 2 часа для отражения данных на портале безопасности.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="3fa9b-166">Однако иногда это может занять больше времени.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="3fa9b-167">Изменение конфигурации может занять от 4 до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="3fa9b-168">Исследование изменений в экспозиции или воздействии устройств</span><span class="sxs-lookup"><span data-stu-id="3fa9b-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="3fa9b-169">Если происходит большой скачок количества открытых устройств или резкое увеличение влияния на оценку воздействия на организацию и microsoft Secure Score для устройств, то эту рекомендацию по безопасности стоит и расследовать.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="3fa9b-170">Выберите страницу рекомендации и **откройте программное обеспечение**</span><span class="sxs-lookup"><span data-stu-id="3fa9b-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="3fa9b-171">Выберите **вкладку Timeline Event** для просмотра всех событий, связанных с этим программным обеспечением, таких как новые уязвимости или новые общедоступные эксплойты.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="3fa9b-172">Дополнительные информацию о временной шкале событий</span><span class="sxs-lookup"><span data-stu-id="3fa9b-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="3fa9b-173">Решение о том, как решить проблему увеличения или воздействия вашей организации, например отправку запроса на исправление</span><span class="sxs-lookup"><span data-stu-id="3fa9b-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="3fa9b-174">Запрос на исправление</span><span class="sxs-lookup"><span data-stu-id="3fa9b-174">Request remediation</span></span>

<span data-ttu-id="3fa9b-175">Возможность устранения угроз и устранения уязвимостей устраняет разрыв между администраторами безопасности и ИТ-службами с помощью рабочего процесса запроса на исправление.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="3fa9b-176">Администраторы безопасности, такие как вы, могут запрашивать у  ИТ-администратора исправление уязвимости со страницы рекомендации по безопасности в Intune.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="3fa9b-177">Дополнительные возможности устранения</span><span class="sxs-lookup"><span data-stu-id="3fa9b-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="3fa9b-178">Запрос на исправление</span><span class="sxs-lookup"><span data-stu-id="3fa9b-178">How to request remediation</span></span>

<span data-ttu-id="3fa9b-179">Выберите рекомендацию по безопасности, для чего необходимо запросить исправление, а затем выберите **параметры исправлений.**</span><span class="sxs-lookup"><span data-stu-id="3fa9b-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="3fa9b-180">Заполните форму и выберите **отправку запроса**.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="3fa9b-181">Перейдите на [**страницу**](tvm-remediation.md) Исправление, чтобы просмотреть состояние запроса на исправление.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="3fa9b-182">Узнайте больше о том, как запросить исправление</span><span class="sxs-lookup"><span data-stu-id="3fa9b-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="3fa9b-183">Файл для исключения</span><span class="sxs-lookup"><span data-stu-id="3fa9b-183">File for exception</span></span>

<span data-ttu-id="3fa9b-184">В качестве альтернативы запросу на исправление, если рекомендация на данный момент не актуальна, можно создать исключения для рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="3fa9b-185">Дополнительные новости об исключениях</span><span class="sxs-lookup"><span data-stu-id="3fa9b-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="3fa9b-186">Исключение могут добавлять только пользователи с разрешениями "обработка исключений".</span><span class="sxs-lookup"><span data-stu-id="3fa9b-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="3fa9b-187">[Узнайте больше о ролях RBAC.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="3fa9b-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="3fa9b-188">Когда создается исключение для рекомендации, рекомендация больше не активна.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="3fa9b-189">Состояние рекомендации будет изменяться на **полное исключение или** **частичное** исключение (по группе устройств).</span><span class="sxs-lookup"><span data-stu-id="3fa9b-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="3fa9b-190">Создание исключения</span><span class="sxs-lookup"><span data-stu-id="3fa9b-190">How to create an exception</span></span>

<span data-ttu-id="3fa9b-191">Выберите рекомендацию по безопасности, для чего необходимо создать исключение, а затем выберите **параметры Исключения.**</span><span class="sxs-lookup"><span data-stu-id="3fa9b-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

![Отображение расположения кнопки "Параметры исключений" в вылете рекомендации по безопасности.](images/tvm-exception-options.png)

<span data-ttu-id="3fa9b-193">Заполните форму и отправьте.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-193">Fill out the form and submit.</span></span> <span data-ttu-id="3fa9b-194">Чтобы просмотреть все исключения (текущие и [](tvm-remediation.md) прошлые), перейдите  на страницу Исправление в меню Управления [](tvm-exception.md#create-an-exception) & уязвимостей и выберите вкладку **Исключения.** Дополнительные возможности создания исключения</span><span class="sxs-lookup"><span data-stu-id="3fa9b-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="3fa9b-195">Неточность отчета</span><span class="sxs-lookup"><span data-stu-id="3fa9b-195">Report inaccuracy</span></span>

<span data-ttu-id="3fa9b-196">Вы можете сообщить о ложном срабатыве, если вы увидите какие-либо расплывчатые, неточные, неполные или уже исправленные сведения о рекомендациях безопасности.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="3fa9b-197">Откройте рекомендацию по безопасности.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="3fa9b-198">Выберите три точки рядом с рекомендациями по безопасности, которые необходимо сообщить, а затем выберите **неточность Отчета.**</span><span class="sxs-lookup"><span data-stu-id="3fa9b-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![Отображение того, где кнопка "Отчет о неточности" находится в вылете рекомендации по безопасности.](images/report-inaccuracy500.png)

3. <span data-ttu-id="3fa9b-200">На поле вылетов выберите категорию неточности из выпадаемого меню, заполните адрес электронной почты и сведения о неточности.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="3fa9b-201">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-201">Select **Submit**.</span></span> <span data-ttu-id="3fa9b-202">Ваши отзывы немедленно отправляются специалистам по управлению угрозами и уязвимостями.</span><span class="sxs-lookup"><span data-stu-id="3fa9b-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3fa9b-203">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3fa9b-203">Related articles</span></span>

- [<span data-ttu-id="3fa9b-204">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="3fa9b-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3fa9b-205">Панель мониторинга</span><span class="sxs-lookup"><span data-stu-id="3fa9b-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="3fa9b-206">Показатель уязвимости</span><span class="sxs-lookup"><span data-stu-id="3fa9b-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="3fa9b-207">Оценка безопасности (Майкрософт) для устройств</span><span class="sxs-lookup"><span data-stu-id="3fa9b-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="3fa9b-208">Устранение уязвимостей</span><span class="sxs-lookup"><span data-stu-id="3fa9b-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="3fa9b-209">Создание и просмотр исключений для рекомендаций по безопасности</span><span class="sxs-lookup"><span data-stu-id="3fa9b-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="3fa9b-210">Временная шкала события</span><span class="sxs-lookup"><span data-stu-id="3fa9b-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
