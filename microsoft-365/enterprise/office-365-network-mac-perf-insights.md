---
title: Microsoft 365 Network Insights
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
description: Microsoft 365 Network Insights
ms.openlocfilehash: 10b1c66a8f9aae555c2841b2b290f341bec3c7ec
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470572"
---
# <a name="microsoft-365-network-insights"></a><span data-ttu-id="99ee6-103">Microsoft 365 Network Insights</span><span class="sxs-lookup"><span data-stu-id="99ee6-103">Microsoft 365 Network Insights</span></span>

<span data-ttu-id="99ee6-104">**Сетевые сведения** — это показатели производительности, собранные Microsoft 365 клиента, и доступные для просмотра только административными пользователями в клиенте.</span><span class="sxs-lookup"><span data-stu-id="99ee6-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="99ee6-105">Сведения отображаются в центре администрирования Microsoft 365 на <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="99ee6-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="99ee6-106">Сведения предназначены для разработки периметров сети для расположения офисов.</span><span class="sxs-lookup"><span data-stu-id="99ee6-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="99ee6-107">Каждое представление содержит подробные сведения о характеристиках производительности для определенной общей проблемы для каждого географического расположения, в котором пользователи имеют доступ к вашему клиенту.</span><span class="sxs-lookup"><span data-stu-id="99ee6-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="99ee6-108">Существует шесть конкретных сетевых данных, которые могут быть показаны для каждого расположения офиса:</span><span class="sxs-lookup"><span data-stu-id="99ee6-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="99ee6-109">Откат сетевой регрессии</span><span class="sxs-lookup"><span data-stu-id="99ee6-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="99ee6-110">Устройство-посредник сети</span><span class="sxs-lookup"><span data-stu-id="99ee6-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="99ee6-111">Улучшение производительности, обнаруженное для клиентов, близких к вам</span><span class="sxs-lookup"><span data-stu-id="99ee6-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="99ee6-112">Использование не оптимальной Exchange Online входной двери службы</span><span class="sxs-lookup"><span data-stu-id="99ee6-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="99ee6-113">Использование не оптимальной входной двери SharePoint online-службы</span><span class="sxs-lookup"><span data-stu-id="99ee6-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="99ee6-114">Низкая скорость загрузки SharePoint входной двери</span><span class="sxs-lookup"><span data-stu-id="99ee6-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="99ee6-115">Оптимальное сетевое отступление пользователей Китая</span><span class="sxs-lookup"><span data-stu-id="99ee6-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="99ee6-116">Существует два сетевых анализа уровня клиента, которые могут быть показаны для клиента.</span><span class="sxs-lookup"><span data-stu-id="99ee6-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="99ee6-117">Они также отображаются на страницах показателей производительности:</span><span class="sxs-lookup"><span data-stu-id="99ee6-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="99ee6-118">Exchange подключений, на которые влияют проблемы с подключением</span><span class="sxs-lookup"><span data-stu-id="99ee6-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="99ee6-119">SharePoint подключений, на которые влияют проблемы с подключением</span><span class="sxs-lookup"><span data-stu-id="99ee6-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="99ee6-120">Сведения о сети, рекомендации по производительности и оценки в центре администрирования Microsoft 365 в настоящее время находятся в состоянии предварительного просмотра и доступны только для Microsoft 365 клиентов, которые были зарегистрированы в программе предварительного просмотра функций.</span><span class="sxs-lookup"><span data-stu-id="99ee6-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="99ee6-121">Откат сетевой регрессии</span><span class="sxs-lookup"><span data-stu-id="99ee6-121">Backhauled network egress</span></span>

<span data-ttu-id="99ee6-122">Это представление будет отображаться, если служба сетевых анализов обнаруживает, что расстояние от заданного расположения пользователя до сетевого регресса превышает 500 миль (800 километров), что указывает на то, что Microsoft 365 трафик возвращается на обычное устройство или прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="99ee6-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="99ee6-123">Это представление сокращено как "Egress" в некоторых сводных представлениях.</span><span class="sxs-lookup"><span data-stu-id="99ee6-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="99ee6-124">![Откат сетевой регрессии](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="99ee6-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="99ee6-125">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="99ee6-125">What does this mean?</span></span>

<span data-ttu-id="99ee6-126">Это определяет, что расстояние между расположением офиса и сетевой отступной составляет более 500 миль (800 километров).</span><span class="sxs-lookup"><span data-stu-id="99ee6-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="99ee6-127">Расположение офиса определено запутывающим расположением клиентской машины, а расположение сетевого отступа определено с помощью обратного IP-адреса в базах данных расположения.</span><span class="sxs-lookup"><span data-stu-id="99ee6-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="99ee6-128">Расположение офиса может быть неточным, если Windows службы расположения отключены на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="99ee6-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="99ee6-129">Расположение сетевого отступа может быть неточным, если сведения базы данных об обратном IP-адресе неточны.</span><span class="sxs-lookup"><span data-stu-id="99ee6-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="99ee6-130">Сведения для этого анализа включают расположение офиса, предполагаемый процент от общего пользователя клиента в расположении, текущее расположение отступа сети, релевантность расположения отступа, расстояние между расположением и текущей точкой выхода, дату первого обнаружения условия и дату решения условия.</span><span class="sxs-lookup"><span data-stu-id="99ee6-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="99ee6-131">Что делать?</span><span class="sxs-lookup"><span data-stu-id="99ee6-131">What should I do?</span></span>

<span data-ttu-id="99ee6-132">Для этого мы рекомендуем отойти от сети ближе к расположению офиса, чтобы обеспечить оптимальное маршрутное подключение к глобальной сети Майкрософт и к ближайшей Microsoft 365 входной двери службы.</span><span class="sxs-lookup"><span data-stu-id="99ee6-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="99ee6-133">Если сеть близка к расположениям офисов пользователей, это также позволяет повысить производительность в будущем, так как Корпорация Майкрософт расширяет точки присутствия сети и Microsoft 365 двери службы в будущем.</span><span class="sxs-lookup"><span data-stu-id="99ee6-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="99ee6-134">Дополнительные сведения об устранении этой [](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) проблемы см. в Egress сетевых подключений в [Office 365 Network Connectivity Principles.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="99ee6-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="99ee6-135">Устройство-посредник сети</span><span class="sxs-lookup"><span data-stu-id="99ee6-135">Network intermediary device</span></span>

<span data-ttu-id="99ee6-136">Это представление будет отображаться, если мы обнаруживаем устройства между пользователями и сетью Майкрософт, которые могут повлиять на Office 365 пользователей.</span><span class="sxs-lookup"><span data-stu-id="99ee6-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="99ee6-137">Рекомендуется обходить их для определенных Microsoft 365 сетевого трафика, предназначенного для центра обработки данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="99ee6-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="99ee6-138">Эта рекомендация дополнительно описана в Microsoft 365 [сетевых принципов](microsoft-365-network-connectivity-principles.md)подключения.</span><span class="sxs-lookup"><span data-stu-id="99ee6-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="99ee6-139">Одним из промежуточных данных сети является разрыв sS Office 365 L и проверка при перехвате и расшифровке критически важных конечных точек Exchange, SharePoint и Teams с помощью сетевых промежуточных устройств.</span><span class="sxs-lookup"><span data-stu-id="99ee6-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="99ee6-140">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="99ee6-140">What does this mean?</span></span>

<span data-ttu-id="99ee6-141">Сетевые промежуточные устройства, такие как прокси-серверы, VPN и устройства для предотвращения потери данных, могут влиять на производительность и стабильность Microsoft 365 клиентов, где трафик является промежуточным.</span><span class="sxs-lookup"><span data-stu-id="99ee6-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="99ee6-142">Что делать?</span><span class="sxs-lookup"><span data-stu-id="99ee6-142">What should I do?</span></span>

<span data-ttu-id="99ee6-143">Настройка устройства-посредника сети, обнаруженного для обхода обработки для Microsoft 365 сетевого трафика.</span><span class="sxs-lookup"><span data-stu-id="99ee6-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="99ee6-144">Улучшение производительности, обнаруженное для клиентов, близких к вам</span><span class="sxs-lookup"><span data-stu-id="99ee6-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="99ee6-145">Это представление будет отображаться, если служба сетевых анализов обнаруживает, что значительное число клиентов в вашем районе метро имеют лучшую производительность, чем пользователи в вашей организации в этом расположении офиса.</span><span class="sxs-lookup"><span data-stu-id="99ee6-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="99ee6-146">Это представление сокращено как "Peers" в некоторых сводных представлениях.</span><span class="sxs-lookup"><span data-stu-id="99ee6-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="99ee6-147">![Относительная производительность сети](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="99ee6-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="99ee6-148">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="99ee6-148">What does this mean?</span></span>

<span data-ttu-id="99ee6-149">В этом анализе рассматривается совокупная производительность Microsoft 365 в том же городе, что и в этом расположении офиса.</span><span class="sxs-lookup"><span data-stu-id="99ee6-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="99ee6-150">Это представление отображается, если средняя задержка пользователей на 10% превышает среднюю задержку соседних клиентов.</span><span class="sxs-lookup"><span data-stu-id="99ee6-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="99ee6-151">Что делать?</span><span class="sxs-lookup"><span data-stu-id="99ee6-151">What should I do?</span></span>

<span data-ttu-id="99ee6-152">Это условие может быть обусловлено многими причинами, включая задержку в корпоративной сети или isP, узкие места или проблемы с проектированием архитектуры.</span><span class="sxs-lookup"><span data-stu-id="99ee6-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="99ee6-153">Изучите задержку между каждым переходом в маршруте между офисной сетью и текущей Microsoft 365 входной двери.</span><span class="sxs-lookup"><span data-stu-id="99ee6-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="99ee6-154">Дополнительные сведения см. [в Microsoft 365 сетевых принципов](microsoft-365-network-connectivity-principles.md)подключения.</span><span class="sxs-lookup"><span data-stu-id="99ee6-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="99ee6-155">Использование не оптимальной Exchange Online входной двери службы</span><span class="sxs-lookup"><span data-stu-id="99ee6-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="99ee6-156">Это представление будет отображаться, если служба сетевых анализов обнаруживает, что пользователи в определенном расположении не подключаются к оптимальной Exchange Online входной двери службы.</span><span class="sxs-lookup"><span data-stu-id="99ee6-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="99ee6-157">В некоторых сводных представлениях это представление сокращено как "Маршрутка".</span><span class="sxs-lookup"><span data-stu-id="99ee6-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="99ee6-158">![Не оптимальная входная дверь EXO](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="99ee6-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="99ee6-159">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="99ee6-159">What does this mean?</span></span>

<span data-ttu-id="99ee6-160">Мы перечисляем Exchange Online входные двери службы, которые подходят для использования из города расположения офиса с хорошей производительностью.</span><span class="sxs-lookup"><span data-stu-id="99ee6-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="99ee6-161">Если в текущем тесте показана Exchange Online входная дверь службы, не в этом списке, мы вызовите эту рекомендацию.</span><span class="sxs-lookup"><span data-stu-id="99ee6-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="99ee6-162">Что делать?</span><span class="sxs-lookup"><span data-stu-id="99ee6-162">What should I do?</span></span>

<span data-ttu-id="99ee6-163">Использование не оптимальной входной двери Exchange Online службы может быть вызвано сетевым задним ходом перед отступлением корпоративной сети, в этом случае рекомендуется локальный и прямой выход из сети.</span><span class="sxs-lookup"><span data-stu-id="99ee6-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="99ee6-164">Это также может быть вызвано использованием удаленного сервера DNS Recursive Resolver, в этом случае мы рекомендуем привести сервер DNS Recursive Resolver в соответствие с сетевой регрессией.</span><span class="sxs-lookup"><span data-stu-id="99ee6-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="99ee6-165">Использование не оптимальной входной двери SharePoint online-службы</span><span class="sxs-lookup"><span data-stu-id="99ee6-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="99ee6-166">Это представление будет отображаться, если служба сетевых анализов обнаруживает, что пользователи в определенном расположении не подключаются к ближайшей SharePoint входной двери службы Online.</span><span class="sxs-lookup"><span data-stu-id="99ee6-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="99ee6-167">Это представление сокращено как "Afd" в некоторых сводных представлениях.</span><span class="sxs-lookup"><span data-stu-id="99ee6-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="99ee6-168">![Не оптимальная входная дверь SPO](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="99ee6-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="99ee6-169">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="99ee6-169">What does this mean?</span></span>

<span data-ttu-id="99ee6-170">Мы определяем SharePoint входную дверь службы Online, к которую подключается тестовый клиент.</span><span class="sxs-lookup"><span data-stu-id="99ee6-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="99ee6-171">Затем для города расположения офиса мы сравниваем это с ожидаемой SharePoint входной двери службы Online для этого города.</span><span class="sxs-lookup"><span data-stu-id="99ee6-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="99ee6-172">Если он не совпадает, мы делайте эту рекомендацию.</span><span class="sxs-lookup"><span data-stu-id="99ee6-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="99ee6-173">Что делать?</span><span class="sxs-lookup"><span data-stu-id="99ee6-173">What should I do?</span></span>

<span data-ttu-id="99ee6-174">Использование входной двери SharePoint сетевой службы может быть вызвано сетевым задним ходом перед отступлением корпоративной сети, в этом случае рекомендуется локальный и прямой выход из сети.</span><span class="sxs-lookup"><span data-stu-id="99ee6-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="99ee6-175">Это также может быть вызвано использованием удаленного сервера DNS Recursive Resolver, в этом случае мы рекомендуем привести сервер DNS Recursive Resolver в соответствие с сетевой регрессией.</span><span class="sxs-lookup"><span data-stu-id="99ee6-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="99ee6-176">Низкая скорость загрузки SharePoint входной двери</span><span class="sxs-lookup"><span data-stu-id="99ee6-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="99ee6-177">Это представление будет отображаться, если служба сетевых анализов обнаруживает, что пропускная способность между определенным расположением офиса и SharePoint Online составляет менее 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="99ee6-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="99ee6-178">Это представление сокращено как "Пропускная способность" в некоторых сводных представлениях.</span><span class="sxs-lookup"><span data-stu-id="99ee6-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="99ee6-179">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="99ee6-179">What does this mean?</span></span>

<span data-ttu-id="99ee6-180">Скорость загрузки, которую пользователь может получить из SharePoint и OneDrive для бизнеса службы, измеряется в мегабайтах в секунду (MBps).</span><span class="sxs-lookup"><span data-stu-id="99ee6-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="99ee6-181">Если это значение меньше 1 MBps, мы предоставляем эту информацию.</span><span class="sxs-lookup"><span data-stu-id="99ee6-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="99ee6-182">Что делать?</span><span class="sxs-lookup"><span data-stu-id="99ee6-182">What should I do?</span></span>

<span data-ttu-id="99ee6-183">Для повышения скорости скачивания может потребоваться увеличить пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="99ee6-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="99ee6-184">Кроме того, может возникнуть перегрузка сети между пользовательскими машинами в расположении офиса и SharePoint входной двери службы Online.</span><span class="sxs-lookup"><span data-stu-id="99ee6-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="99ee6-185">Иногда это называется застойной потерей и ограничивает скорость скачивания, доступную пользователям, даже если доступна достаточную пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="99ee6-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="99ee6-186">Оптимальное сетевое отступление пользователей Китая</span><span class="sxs-lookup"><span data-stu-id="99ee6-186">China user optimal network egress</span></span>

<span data-ttu-id="99ee6-187">Это представление будет отображаться, если в вашей организации есть пользователи в Китае, подключающиеся к Microsoft 365 в других географических расположениях.</span><span class="sxs-lookup"><span data-stu-id="99ee6-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="99ee6-188">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="99ee6-188">What does this mean?</span></span>

<span data-ttu-id="99ee6-189">Если ваша организация имеет частное подключение к сети WAN, рекомендуется настроить сеть WAN-схемы из офисных точек в Китае, которая имеет сетевой отступ к Интернету в любом из следующих местоположений:</span><span class="sxs-lookup"><span data-stu-id="99ee6-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="99ee6-190">Гонконг, САР</span><span class="sxs-lookup"><span data-stu-id="99ee6-190">Hong Kong</span></span>
- <span data-ttu-id="99ee6-191">Япония</span><span class="sxs-lookup"><span data-stu-id="99ee6-191">Japan</span></span>
- <span data-ttu-id="99ee6-192">Тайвань</span><span class="sxs-lookup"><span data-stu-id="99ee6-192">Taiwan</span></span>
- <span data-ttu-id="99ee6-193">Южная Корея</span><span class="sxs-lookup"><span data-stu-id="99ee6-193">South Korea</span></span>
- <span data-ttu-id="99ee6-194">Сингапур</span><span class="sxs-lookup"><span data-stu-id="99ee6-194">Singapore</span></span>
- <span data-ttu-id="99ee6-195">Малайзия</span><span class="sxs-lookup"><span data-stu-id="99ee6-195">Malaysia</span></span>

<span data-ttu-id="99ee6-196">Отходить от пользователей интернет будет гораздо дальше, чем эти расположения, что приведет к снижению производительности, а в Китае это может привести к высокой задержке и возникновению проблем с подключением из-за перегрузки на границе.</span><span class="sxs-lookup"><span data-stu-id="99ee6-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="99ee6-197">Что делать?</span><span class="sxs-lookup"><span data-stu-id="99ee6-197">What should I do?</span></span>

<span data-ttu-id="99ee6-198">Дополнительные сведения о том, как устранить проблемы производительности, связанные с этим представлением, см. в Microsoft 365 глобальной оптимизации производительности клиентов [для пользователей Китая.](microsoft-365-networking-china.md)</span><span class="sxs-lookup"><span data-stu-id="99ee6-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="99ee6-199">Exchange подключений, на которые влияют проблемы с подключением</span><span class="sxs-lookup"><span data-stu-id="99ee6-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="99ee6-200">Это представление будет показывать, когда 50% или более из выборки подключений влияют.</span><span class="sxs-lookup"><span data-stu-id="99ee6-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="99ee6-201">Влияние определяется оценкой Exchange ниже 60% для каждого примера.</span><span class="sxs-lookup"><span data-stu-id="99ee6-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="99ee6-202">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="99ee6-202">What does this mean?</span></span>

<span data-ttu-id="99ee6-203">Это указывает на то, что большинство пользователей, скорее всего, испытывают проблемы с пользовательским опытом с подключением Outlook к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="99ee6-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="99ee6-204">Процент примеров, скорее всего, представляет процент пользователей, которые показывают ниже 60 баллов.</span><span class="sxs-lookup"><span data-stu-id="99ee6-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="99ee6-205">Что делать?</span><span class="sxs-lookup"><span data-stu-id="99ee6-205">What should I do?</span></span>

<span data-ttu-id="99ee6-206">Включить видимость подключения к сети расположения офиса, если вы еще этого не сделали.</span><span class="sxs-lookup"><span data-stu-id="99ee6-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="99ee6-207">Необходимо определить, какие офисы оказывают влияние из-за плохой сетевой связи, которая влияет на Exchange, и найти способы улучшения периметра сети в каждом из них, связывающих пользователей с сетью Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="99ee6-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="99ee6-208">SharePoint подключений, на которые влияют проблемы с подключением</span><span class="sxs-lookup"><span data-stu-id="99ee6-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="99ee6-209">Это представление будет показывать, когда 50% или более из выборки подключений влияют.</span><span class="sxs-lookup"><span data-stu-id="99ee6-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="99ee6-210">Влияние определяется оценкой SharePoint ниже 40% для каждого примера.</span><span class="sxs-lookup"><span data-stu-id="99ee6-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="99ee6-211">Что это означает?</span><span class="sxs-lookup"><span data-stu-id="99ee6-211">What does this mean?</span></span>

<span data-ttu-id="99ee6-212">Это указывает на то, что большинство пользователей, скорее всего, испытывают проблемы с пользовательским опытом с SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="99ee6-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="99ee6-213">Процент примеров, скорее всего, представляет процент пользователей, которые показывают ниже 40 баллов.</span><span class="sxs-lookup"><span data-stu-id="99ee6-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="99ee6-214">Что делать?</span><span class="sxs-lookup"><span data-stu-id="99ee6-214">What should I do?</span></span>

<span data-ttu-id="99ee6-215">Включить видимость подключения к сети расположения офиса, если вы еще этого не сделали.</span><span class="sxs-lookup"><span data-stu-id="99ee6-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="99ee6-216">Необходимо определить, какие офисы оказывают влияние из-за плохой сетевой связи, которая влияет на SharePoint, и найти способы улучшения периметра сети в каждом из них, связывающих пользователей с сетью Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="99ee6-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="99ee6-217">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="99ee6-217">Related topics</span></span>

[<span data-ttu-id="99ee6-218">Подключение к сети в центре администрирования Microsoft 365 (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="99ee6-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="99ee6-219">Microsoft 365 сети (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="99ee6-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="99ee6-220">Microsoft 365 для тестирования подключения к сети (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="99ee6-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="99ee6-221">Microsoft 365 Службы расположения сетевых подключений (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="99ee6-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
