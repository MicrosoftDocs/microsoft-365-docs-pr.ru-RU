---
title: Microsoft 365 Network Insights (предварительная версия)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (предварительная версия)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055477"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="fbc2c-103">Microsoft 365 Network Insights (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fbc2c-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="fbc2c-104">**Данные о сети —** это показатели производительности, собранные из клиента Microsoft 365 и доступные для просмотра только пользователями администраторов в клиенте.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="fbc2c-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="fbc2c-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="fbc2c-106">Анализ помогает при проектировании сетевых периметров для местоположений офисов.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="fbc2c-107">Каждая информация предоставляет подробные сведения о характеристиках производительности для конкретной общей проблемы для каждого географического расположения, в котором пользователи имеют доступ к вашему арендатору.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="fbc2c-108">Существует шесть определенных сетевых данных, которые могут быть показаны для каждого расположения офиса:</span><span class="sxs-lookup"><span data-stu-id="fbc2c-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="fbc2c-109">Откат сетевого экскурса</span><span class="sxs-lookup"><span data-stu-id="fbc2c-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="fbc2c-110">Устройство-посредник сети</span><span class="sxs-lookup"><span data-stu-id="fbc2c-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="fbc2c-111">Более емкие показатели производительности для клиентов, которые рядом с вами</span><span class="sxs-lookup"><span data-stu-id="fbc2c-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="fbc2c-112">Использование не оптимальной службы Exchange Online переднего входа</span><span class="sxs-lookup"><span data-stu-id="fbc2c-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="fbc2c-113">Использование не оптимальной входной точки службы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fbc2c-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="fbc2c-114">Низкая скорость скачивания из переднего входа SharePoint</span><span class="sxs-lookup"><span data-stu-id="fbc2c-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="fbc2c-115">Оптимальный сетевой эксгрим для пользователей Китая</span><span class="sxs-lookup"><span data-stu-id="fbc2c-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="fbc2c-116">Существует два анализа сети на уровне клиента, которые могут быть показаны для клиента.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="fbc2c-117">Они также отображаются на страницах показателей создания.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="fbc2c-118">Примеры подключений Exchange, на которые влияют проблемы с подключением</span><span class="sxs-lookup"><span data-stu-id="fbc2c-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="fbc2c-119">Примеры подключений SharePoint, на которые влияют проблемы с подключением</span><span class="sxs-lookup"><span data-stu-id="fbc2c-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="fbc2c-120">Анализ сети, рекомендации по производительности и оценки в Центре администрирования Microsoft 365 в настоящее время находятся в состоянии предварительной версии и доступны только для клиентов Microsoft 365, которые зарегистрированы в программе предварительного просмотра функций.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="fbc2c-121">Откат сетевого экскурса</span><span class="sxs-lookup"><span data-stu-id="fbc2c-121">Backhauled network egress</span></span>

<span data-ttu-id="fbc2c-122">Эта информация будет отображаться, если служба анализа сети обнаружит, что расстояние от заданного расположения пользователя до сетевого трафика превышает 500 метров (800 метров), что указывает на то, что трафик Microsoft 365 возвращается на общее устройство или прокси-сервер Интернета.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="fbc2c-123">В некоторых сводных представлениях это представление сокращено как "Egress".</span><span class="sxs-lookup"><span data-stu-id="fbc2c-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Откат сетевого экскурса](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="fbc2c-125">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-125">What does this mean?</span></span>

<span data-ttu-id="fbc2c-126">Это определяет, что расстояние между расположением офиса и сетевым игресом превышает 500 метров (800 метров).</span><span class="sxs-lookup"><span data-stu-id="fbc2c-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="fbc2c-127">Расположение офиса идентифицировано запутавленным расположением клиентского компьютера, а расположение сетевого выпада из сети — обратным IP-адресом в базах данных расположений.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="fbc2c-128">Расположение офиса может быть неточным, если службы расположения Windows отключены на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="fbc2c-129">Если данные базы данных обратных IP-адресов неточны, расположение сетевого адреса может быть неточным.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="fbc2c-130">Сведения для этой аналитики включают расположение офиса, примерный процент от общего числа пользователей клиента в расположении, текущее расположение выхода из сети, релевантность расположения выхода, расстояние между расположением и текущей точкой выхода, дату первого обнаружения условия и дату разрешения условия.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fbc2c-131">Что делать?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-131">What should I do?</span></span>

<span data-ttu-id="fbc2c-132">Для получения этой информации мы рекомендуем ближе к местоположению офиса ближе к месту расположения сети, чтобы подключение оптимально перенаступит к глобальной сети Майкрософт и к ближайшему входу в службу Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="fbc2c-133">При закрытии сетевого входа в расположения офисов пользователей также можно повысить производительность в будущем, так как Корпорация Майкрософт расширяет точки присутствия сети и входные точки службы Microsoft 365 в будущем.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="fbc2c-134">Дополнительные сведения о том, как устранить эту проблему, см. в локальных сетевых подключениях [egress](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) в office [365 Network Connectivity Principles.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="fbc2c-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="fbc2c-135">Устройство-посредник сети</span><span class="sxs-lookup"><span data-stu-id="fbc2c-135">Network intermediary device</span></span>

<span data-ttu-id="fbc2c-136">Эта информация будет отображаться, если мы обнаружили устройства между вашими пользователями и сетью Майкрософт, которые могут повлиять на пользовательский интерфейс Office 365.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="fbc2c-137">Рекомендуется обходить их для определенного сетевого трафика Microsoft 365, предназначенного для центра обработки данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="fbc2c-138">Эта рекомендация также описана в принципах сетевого подключения [Microsoft 365](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="fbc2c-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fbc2c-139">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-139">What does this mean?</span></span>

<span data-ttu-id="fbc2c-140">Устройства-посредники сети, такие как прокси-серверы, VPN и устройства защиты от потери данных, могут влиять на производительность и стабильность клиентов Microsoft 365, где трафик является промежуточным.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fbc2c-141">Что делать?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-141">What should I do?</span></span>

<span data-ttu-id="fbc2c-142">Настройте промежуточное сетевое устройство, которое было обнаружено для обхода обработки сетевого трафика Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="fbc2c-143">Более емкие показатели производительности для клиентов, которые рядом с вами</span><span class="sxs-lookup"><span data-stu-id="fbc2c-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="fbc2c-144">Эта информация будет отображаться, если служба анализа сети обнаружит, что значительное количество клиентов в вашей области имеет более качественую производительность, чем пользователи в вашей организации в этом офисе.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="fbc2c-145">В некоторых сводных представлениях это представление сокращено как "Одноранговая информация".</span><span class="sxs-lookup"><span data-stu-id="fbc2c-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Относительная производительность сети](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="fbc2c-147">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-147">What does this mean?</span></span>

<span data-ttu-id="fbc2c-148">Эта информация проверяет совокупную производительность клиентов Microsoft 365 в одном городе с этим офисом.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="fbc2c-149">Эта информация отображается, если средняя задержка пользователей на 10 % больше средней задержки для соседних клиентов.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fbc2c-150">Что делать?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-150">What should I do?</span></span>

<span data-ttu-id="fbc2c-151">Это условие может быть обусловлено множеством причин, в том числе задержкой в корпоративной сети или isP, узкими местами или вопросами проектирования архитектуры.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="fbc2c-152">Проверьте задержку между каждым прыжком в маршруте между сетью Office и текущей входной линией Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="fbc2c-153">Дополнительные сведения см. в сведениях о принципах [сетевого подключения Microsoft 365.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="fbc2c-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="fbc2c-154">Использование не оптимальной службы Exchange Online переднего входа</span><span class="sxs-lookup"><span data-stu-id="fbc2c-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="fbc2c-155">Эта информация будет отображаться, если служба анализа сети обнаружит, что пользователи в определенном расположении не подключаются к оптимальной входной окне службы Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="fbc2c-156">В некоторых сводных представлениях это представление сокращено как "Маршруты".</span><span class="sxs-lookup"><span data-stu-id="fbc2c-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Не оптимальный вход в EXO](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="fbc2c-158">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-158">What does this mean?</span></span>

<span data-ttu-id="fbc2c-159">Мы перечисляем входные стижки службы Exchange Online, которые подходят для использования из города офисов с хорошей производительностью.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="fbc2c-160">Если в текущем тесте показано использование переднего входа службы Exchange Online в этом списке, мы вызовите эту рекомендацию.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fbc2c-161">Что делать?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-161">What should I do?</span></span>

<span data-ttu-id="fbc2c-162">Использование не оптимального входа службы Exchange Online может быть вызвано выходом сети перед выходом корпоративной сети, в этом случае рекомендуется локальный и прямой выход из сети.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="fbc2c-163">Это также может быть вызвано использованием удаленного сервера рекурсивного разрешения DNS, в этом случае мы рекомендуем привязывать DNS-сервер рекурсивного разрешения с сетевым перегресом.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="fbc2c-164">Использование не оптимальной входной точки службы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fbc2c-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="fbc2c-165">Эта информация будет отображаться, если служба анализа сети обнаружит, что пользователи в определенном расположении не подключаются к ближайшему входу в службу SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="fbc2c-166">В некоторых сводных представлениях эта информация сокращена как "Afd".</span><span class="sxs-lookup"><span data-stu-id="fbc2c-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Не оптимальный вход в SPO](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="fbc2c-168">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-168">What does this mean?</span></span>

<span data-ttu-id="fbc2c-169">Мы определяем входную точку службы SharePoint Online, к которую подключается тестовый клиент.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="fbc2c-170">Затем для города расположения офиса мы сравниваем это с ожидаемым входным входом в службу SharePoint Online для этого города.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="fbc2c-171">Если оно не совпадает, мы делайте эту рекомендацию.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fbc2c-172">Что делать?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-172">What should I do?</span></span>

<span data-ttu-id="fbc2c-173">Использование не оптимальной входной точки службы SharePoint Online может быть вызвано выходом сети из сети перед выходом корпоративной сети, в этом случае рекомендуется локальный и прямой выход из сети.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="fbc2c-174">Это также может быть вызвано использованием удаленного сервера рекурсивного разрешения DNS, в этом случае мы рекомендуем привязывать DNS-сервер рекурсивного разрешения с сетевым перегресом.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="fbc2c-175">Низкая скорость скачивания из переднего входа SharePoint</span><span class="sxs-lookup"><span data-stu-id="fbc2c-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="fbc2c-176">Эта информация будет отображаться, если служба анализа сети обнаружит, что пропускная способность между конкретным расположением офиса и SharePoint Online составляет менее 1 Мбайт/с.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="fbc2c-177">В некоторых сводных представлениях это представление сокращено как "Пропускная способность".</span><span class="sxs-lookup"><span data-stu-id="fbc2c-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fbc2c-178">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-178">What does this mean?</span></span>

<span data-ttu-id="fbc2c-179">Скорость скачивания, которую пользователь может получить из SharePoint Online и переднего входа службы OneDrive для бизнеса, измеряется в мегабайтах в секунду (MBps).</span><span class="sxs-lookup"><span data-stu-id="fbc2c-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="fbc2c-180">Если это значение меньше 1 MBps, мы предоставляем эту информацию.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fbc2c-181">Что делать?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-181">What should I do?</span></span>

<span data-ttu-id="fbc2c-182">Чтобы повысить скорость скачивания, может потребоваться увеличить пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="fbc2c-183">Кроме того, может возникнуть перегрузка сети между компьютерами пользователей в расположении офиса и входе в службу SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="fbc2c-184">Это иногда называется застойной потерей и ограничивает скорость скачивания, доступную пользователям, даже если доступна достаточная пропускная способность.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="fbc2c-185">Оптимальный сетевой эксгрим для пользователей Китая</span><span class="sxs-lookup"><span data-stu-id="fbc2c-185">China user optimal network egress</span></span>

<span data-ttu-id="fbc2c-186">Эта информация будет отображаться, если пользователи вашей организации в Китае подключаются к вашему арендатору Microsoft 365 в других географических расположениях.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="fbc2c-187">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-187">What does this mean?</span></span>

<span data-ttu-id="fbc2c-188">Если в вашей организации есть частное подключение к WAN, мы рекомендуем настроить сетевую сеть WAN из офисов в Китае, которая имеет сетевой доступ к Интернету в любом из следующих мест:</span><span class="sxs-lookup"><span data-stu-id="fbc2c-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="fbc2c-189">Гонконг, САР</span><span class="sxs-lookup"><span data-stu-id="fbc2c-189">Hong Kong</span></span>
- <span data-ttu-id="fbc2c-190">Япония</span><span class="sxs-lookup"><span data-stu-id="fbc2c-190">Japan</span></span>
- <span data-ttu-id="fbc2c-191">Тайвань</span><span class="sxs-lookup"><span data-stu-id="fbc2c-191">Taiwan</span></span>
- <span data-ttu-id="fbc2c-192">Южная Корея</span><span class="sxs-lookup"><span data-stu-id="fbc2c-192">South Korea</span></span>
- <span data-ttu-id="fbc2c-193">Сингапур</span><span class="sxs-lookup"><span data-stu-id="fbc2c-193">Singapore</span></span>
- <span data-ttu-id="fbc2c-194">Малайзия</span><span class="sxs-lookup"><span data-stu-id="fbc2c-194">Malaysia</span></span>

<span data-ttu-id="fbc2c-195">При более позднем отсечении от пользователей, чем в этих расположениях, будет снижена производительность, а при этом в Китае могут возникнуть проблемы с высокой задержкой и подключением из-за перегрузки границы.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fbc2c-196">Что делать?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-196">What should I do?</span></span>

<span data-ttu-id="fbc2c-197">Дополнительные сведения о том, как устранить проблемы с производительностью, связанные с этой информацией, см. в глобальной оптимизации производительности клиентов [Microsoft 365](microsoft-365-networking-china.md)для пользователей Китая.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="fbc2c-198">Примеры подключений Exchange, на которые влияют проблемы с подключением</span><span class="sxs-lookup"><span data-stu-id="fbc2c-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="fbc2c-199">Эта информация будет показывать, когда влияет 50 % или более подключений с образцами.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="fbc2c-200">Влияние определяется оценкой Exchange ниже 60 % для каждого примера.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fbc2c-201">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-201">What does this mean?</span></span>

<span data-ttu-id="fbc2c-202">Это указывает на то, что у большинства пользователей могут быть проблемы с пользовательским интерфейсом при подключении Outlook к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="fbc2c-203">Процент примеров, скорее всего, представляет процент пользователей, которые показывают меньше 60 баллов.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="fbc2c-204">Что делать?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-204">What should I do?</span></span>

<span data-ttu-id="fbc2c-205">В случае, если это еще не сделано, в случае, если вы еще не сделали этого, в сети расположения Office.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="fbc2c-206">Вы хотите определить, на какие офисы влияет плохое сетевое подключение, которое влияет на Exchange, и найти способы улучшения периметра сети на каждом из них, который подключает пользователей к сети Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="fbc2c-207">Примеры подключений SharePoint, на которые влияют проблемы с подключением</span><span class="sxs-lookup"><span data-stu-id="fbc2c-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="fbc2c-208">Эта информация будет показывать, когда влияет 50% или более подключений с образцами.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="fbc2c-209">Влияние определяется оценкой SharePoint ниже 40 % для каждого примера.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fbc2c-210">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-210">What does this mean?</span></span>

<span data-ttu-id="fbc2c-211">Это указывает на то, что большинство пользователей, скорее всего, столкнулись с проблемой с интерфейсом пользователя в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="fbc2c-212">Процент примеров, скорее всего, представляет процент пользователей, которые показывают менее 40 баллов.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="fbc2c-213">Что делать?</span><span class="sxs-lookup"><span data-stu-id="fbc2c-213">What should I do?</span></span>

<span data-ttu-id="fbc2c-214">В случае, если это еще не сделано, в случае, если вы еще не сделали этого, в сети расположения Office.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="fbc2c-215">Вы хотите определить, на какие офисы влияет плохое сетевое подключение, которое влияет на SharePoint, и найти способы улучшения периметра сети на каждом из них, который подключает пользователей к сети Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fbc2c-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fbc2c-216">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="fbc2c-216">Related topics</span></span>

[<span data-ttu-id="fbc2c-217">Сетевое подключение в Центре администрирования Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fbc2c-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="fbc2c-218">Оценка сети Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fbc2c-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="fbc2c-219">Средство проверки сетевого подключения Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fbc2c-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="fbc2c-220">Microsoft 365 Network Connectivity Location Services (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fbc2c-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
