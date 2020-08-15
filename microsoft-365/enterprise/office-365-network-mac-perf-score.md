---
title: Оценка сети Microsoft 365 (Предварительная версия)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Оценка сети Microsoft 365 (Предварительная версия)
ms.openlocfilehash: aacbdf73da9552a12bde250e51544f1de533637c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696470"
---
# <a name="microsoft-365-network-assessment-preview"></a><span data-ttu-id="43de4-103">Оценка сети Microsoft 365 (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="43de4-103">Microsoft 365 network assessment (preview)</span></span>

<span data-ttu-id="43de4-104">В центре администрирования Microsoft 365 с подключением к странице Microsoft 365, **оценки сети** прерабатываются статистические сведения о многочисленных метриках производительности сети в снимок работоспособности сети предприятия, представленный значением баллов из 1-100.</span><span class="sxs-lookup"><span data-stu-id="43de4-104">In the Microsoft 365 Admin Center's Connectivity to Microsoft 365 page, **network assessments** distill an aggregate of many network performance metrics into a snapshot of your enterprise network health, represented by a points value from 1 - 100.</span></span> <span data-ttu-id="43de4-105">Оценка сети распространяется как на весь клиент, так и на каждое географическое расположение, из которого пользователи подключаются к клиенту, предоставляя администраторам Microsoft 365 простой способ незамедлительно оценить работоспособность сети предприятия и быстро перейти к подробному отчету по любому глобальному расположению в офисе.</span><span class="sxs-lookup"><span data-stu-id="43de4-105">Network assessments are scoped to both the entire tenant and for each geographic location from which users connect to your tenant, providing Microsoft 365 administrators with an easy way to instantly grasp a gestalt of the enterprise's network health and quickly drill down into a detailed report for any global office location.</span></span>

<span data-ttu-id="43de4-106">Баллы оценки сети — это средняя единица измерения задержки, пропускной способности, скорости загрузки и метрик качества подключения, которые компилируются в реальном времени при просмотре.</span><span class="sxs-lookup"><span data-stu-id="43de4-106">The network assessment points value is an average measurement of latency, bandwidth, download speed and connection quality metrics compiled live at the time they are viewed.</span></span> <span data-ttu-id="43de4-107">Метрики производительности для сетей, принадлежащих корпорации Майкрософт, исключаются из этих измерений, чтобы убедиться, что результаты оценки ненеоднозначны и относятся к корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="43de4-107">Performance metrics for Microsoft-owned networks are excluded from these measurements to ensure that assessment results are unambiguous and specific to the corporate network.</span></span>

![Значение оценки сети](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

<span data-ttu-id="43de4-109">Слишком маленькое значение оценки сети предполагает, что клиенты Microsoft 365 могут испытывать серьезные проблемы с подключением к клиенту или обслуживанием непроизводительного пользовательского интерфейса, в то время как высокое значение указывает правильно настроенную сеть с минимальными проблемами производительности.</span><span class="sxs-lookup"><span data-stu-id="43de4-109">A very low network assessment value suggests that Microsoft 365 clients will have significant problems connecting to the tenant or maintaining a responsive user experience, while a high value indicates a properly configured network with few ongoing performance issues.</span></span> <span data-ttu-id="43de4-110">Значение 80% представляет работоспособную базовую линию, на которой не следует ожидать, что вы не будете получать обычные жалобы пользователей по подключению к Microsoft 365 или скорости ответа из-за производительности сети.</span><span class="sxs-lookup"><span data-stu-id="43de4-110">A value of 80% represents a healthy baseline where you should not expect to receive regular user complaints about Microsoft 365 connectivity or responsiveness due to network performance.</span></span> <span data-ttu-id="43de4-111">По мере появления итеративных улучшений сетевого подключения это значение увеличится вместе с пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="43de4-111">As iterative network connectivity improvements are made, this value will increase along with user experience.</span></span>

>[!IMPORTANT]
><span data-ttu-id="43de4-112">Сведения о сети, рекомендации по производительности и оценки в центре администрирования Microsoft 365 в настоящее время находятся в состоянии предварительной версии и доступны только для клиентов Microsoft 365, зарегистрированных в программе предварительного просмотра компонентов.</span><span class="sxs-lookup"><span data-stu-id="43de4-112">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="network-assessment-panel"></a><span data-ttu-id="43de4-113">Панель оценки сети</span><span class="sxs-lookup"><span data-stu-id="43de4-113">Network assessment panel</span></span>

<span data-ttu-id="43de4-114">Каждая оценка сети, в зависимости от того, находится ли область клиента или к определенному расположению Office, показывает панель с подробными сведениями об оценке.</span><span class="sxs-lookup"><span data-stu-id="43de4-114">Each network assessment, whether scoped to the tenant or to a specific office location, shows a panel with details about the assessment.</span></span> <span data-ttu-id="43de4-115">На этой панели отображается линейчатая диаграмма с оценкой как в процентах, так и в качестве общего количества баллов для каждой рабочей нагрузки компонентов, включая рабочие нагрузки, в которых были получены данные измерения.</span><span class="sxs-lookup"><span data-stu-id="43de4-115">This panel shows a bar chart of the assessment both as a percentage and as the total points for each component workload including only workloads where measurement data was received.</span></span> <span data-ttu-id="43de4-116">Для оценки сети местоположения Office мы также видим тест, который является медианы всех клиентов Microsoft 365, которые сообщают данные в том же городе, что и ваше расположение в офисе.</span><span class="sxs-lookup"><span data-stu-id="43de4-116">For an office location network assessment, we also show a benchmark which is the median of all Microsoft 365 clients that reported data in the same city as your office location.</span></span>

![Пример значения оценки сети](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

<span data-ttu-id="43de4-118">При **разбивке оценки** на панели отображается оценка каждой рабочей нагрузки компонентов.</span><span class="sxs-lookup"><span data-stu-id="43de4-118">The **Assessment breakdown** in the panel shows the assessment for each of the component workloads.</span></span>

<span data-ttu-id="43de4-119">**Журнал оценки** показывает, что за прошлые 30 дней оценки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="43de4-119">The **Assessment history** shows the past 30 days of the assessment and the benchmark.</span></span>

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a><span data-ttu-id="43de4-120">Оценки сети клиента и оценки сети Office</span><span class="sxs-lookup"><span data-stu-id="43de4-120">Tenant network assessments and office location network assessments</span></span>

<span data-ttu-id="43de4-121">Оценка сети измеряет Оформление периметра сети офиса в сети корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="43de4-121">A network assessment measures the design of the network perimeter of an office location to Microsoft's network.</span></span> <span data-ttu-id="43de4-122">Улучшения периметра сети лучше всего подходят для каждого офиса или в том случае, если сетевое подключение объединено, могут возникать улучшения, влияющие на несколько расположений.</span><span class="sxs-lookup"><span data-stu-id="43de4-122">Improvements to the network perimeter is best done at each office location, or where network connectivity is aggregated there may be improvements that impact multiple locations.</span></span>

<span data-ttu-id="43de4-123">Мы отображаем значение оценки сети для всего клиента Microsoft 365 на странице "Обзор сетевой производительности" и определенное значение для каждого обнаруженного расположения Office на странице сводки этого расположения.</span><span class="sxs-lookup"><span data-stu-id="43de4-123">We show a network assessment value for the whole Microsoft 365 tenant on the network performance overview page and a specific value for each detected office location on that location's summary page.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="43de4-124">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="43de4-124">Exchange Online</span></span>

<span data-ttu-id="43de4-125">Для Exchange Online измеряется задержка TCP от клиентского компьютера до сервера переднего плана Exchange.</span><span class="sxs-lookup"><span data-stu-id="43de4-125">For Exchange Online the TCP latency from the client machine to the Exchange front end server is measured.</span></span> <span data-ttu-id="43de4-126">Это может повлиять на расстояние, на которое сеть перемещается по локальной сети и глобальной сети клиентов.</span><span class="sxs-lookup"><span data-stu-id="43de4-126">This can be impacted by the distance the network travels over the customers LAN and WAN.</span></span> <span data-ttu-id="43de4-127">Кроме того, они могут быть затронуты сетевыми промежуточными устройствами или службами, которые отменяют подключение или вызывают повторную отправку пакетов.</span><span class="sxs-lookup"><span data-stu-id="43de4-127">It can also be impacted by network intermediary devices or services which delay the connectivity or cause packets to be resent.</span></span>

## <a name="sharepoint-online"></a><span data-ttu-id="43de4-128">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="43de4-128">SharePoint Online</span></span>

<span data-ttu-id="43de4-129">Для SharePoint Online скорость скачивания, доступная пользователям для доступа к документу, измеряется.</span><span class="sxs-lookup"><span data-stu-id="43de4-129">For SharePoint Online the download speed available for a user to access a document is measured.</span></span> <span data-ttu-id="43de4-130">Это может повлиять на пропускную способность, доступную для сетевых цепей между клиентским компьютером и сетью корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="43de4-130">This can be impacted by the bandwidth available on network circuits between the client machine and Microsoft's network.</span></span> <span data-ttu-id="43de4-131">Кроме того, это часто влияет на перегрузку сети, которая существует в узких местах в сложных сетевых устройствах или в областях с плохим покрытием.</span><span class="sxs-lookup"><span data-stu-id="43de4-131">It is also often impacted by network congestion that exists in bottlenecks in complex network devices or in poor coverage Wi-Fi areas.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="43de4-132">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43de4-132">Microsoft Teams</span></span>

<span data-ttu-id="43de4-133">Для Microsoft Teams качество сети измеряется как задержка UDP, колебание UDP и потеря пакетов UDP.</span><span class="sxs-lookup"><span data-stu-id="43de4-133">For Microsoft Teams the Network quality is measured as UDP latency, UDP jitter, and UDP packet loss.</span></span> <span data-ttu-id="43de4-134">UDP используется для подключения аудио-и видеоконференций для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43de4-134">UDP is used for call and conferencing audio and video media connectivity for Microsoft Teams.</span></span> <span data-ttu-id="43de4-135">Это может затронуть те же факторы, что и для задержки и скорости скачивания в дополнение к разрывам подключений в сетевой поддержке UDP, так как протокол UDP настроен отдельно для более общего протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="43de4-135">This can be impacted by the same factors as for latency and download speed in addition to connectivity gaps in a network's UDP support since UDP is configured separately to the more common TCP protocol.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43de4-136">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="43de4-136">Related topics</span></span>

[<span data-ttu-id="43de4-137">Рекомендации по повышению производительности сети в центре администрирования Microsoft 365 (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="43de4-137">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="43de4-138">Анализ производительности сети Microsoft 365 (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="43de4-138">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="43de4-139">Проверка подключения Microsoft 365 в центре администрирования M365 (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="43de4-139">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="43de4-140">Служба расположения сетевых подключений (Предварительная версия) Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="43de4-140">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
