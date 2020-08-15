---
title: Microsoft 365 Network Insights (Предварительная версия)
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
description: Microsoft 365 Network Insights (Предварительная версия)
ms.openlocfilehash: b30af89d480383fdc9011d24409e3b418339c70b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693241"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="78c1b-103">Microsoft 365 Network Insights (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="78c1b-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="78c1b-104">**Сетевая аналитика** — это показатели производительности, полученные от клиента Microsoft 365 и доступные для просмотра только администраторами в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="78c1b-104">**Network insights** are live performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="78c1b-105">Аналитика отображается в центре администрирования Microsoft 365 по адресу <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="78c1b-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="78c1b-106">Insights призваны помочь при проектировании периметров сети для расположений в офисе.</span><span class="sxs-lookup"><span data-stu-id="78c1b-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="78c1b-107">Каждый из них предоставляет сведения о характеристиках производительности для определенной распространенной ситуации для каждого географического расположения, в котором пользователи обращаются к клиенту.</span><span class="sxs-lookup"><span data-stu-id="78c1b-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="78c1b-108">Существует пять сведений о сети, которые могут отображаться для каждого местоположения Office:</span><span class="sxs-lookup"><span data-stu-id="78c1b-108">There are five specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="78c1b-109">Выход сети с обратной допускной подсистемой</span><span class="sxs-lookup"><span data-stu-id="78c1b-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="78c1b-110">Более высокая производительность обнаружено соседних клиентов</span><span class="sxs-lookup"><span data-stu-id="78c1b-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="78c1b-111">Использование неоптимальной передней дверцы службы Exchange Online</span><span class="sxs-lookup"><span data-stu-id="78c1b-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="78c1b-112">Использование неоптимальной передней дверцы службы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="78c1b-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="78c1b-113">Минимальная скорость скачивания из передней дверцы SharePoint</span><span class="sxs-lookup"><span data-stu-id="78c1b-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)

>[!IMPORTANT]
><span data-ttu-id="78c1b-114">Сведения о сети, рекомендации по производительности и оценки в центре администрирования Microsoft 365 в настоящее время находятся в состоянии предварительной версии и доступны только для клиентов Microsoft 365, зарегистрированных в программе предварительного просмотра компонентов.</span><span class="sxs-lookup"><span data-stu-id="78c1b-114">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="78c1b-115">Выход сети с обратной допускной подсистемой</span><span class="sxs-lookup"><span data-stu-id="78c1b-115">Backhauled network egress</span></span>

<span data-ttu-id="78c1b-116">Это значение будет отображаться, если служба Network Insights обнаружит, что расстояние от конкретного пользователя до выхода в сеть превышает 500 миль (800 километров), что указывает на то, что трафик Microsoft 365 передается на распространенное пограничный порт или прокси-сервер Интернета.</span><span class="sxs-lookup"><span data-stu-id="78c1b-116">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="78c1b-117">Это сокращение является сокращенным в некоторых сводных представлениях.</span><span class="sxs-lookup"><span data-stu-id="78c1b-117">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Выход сети с обратной допускной подсистемой](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="78c1b-119">Сценарий</span><span class="sxs-lookup"><span data-stu-id="78c1b-119">What does this mean?</span></span>

<span data-ttu-id="78c1b-120">Это указывает, что расстояние между расположением офиса и выходом сети превышает 500 миль (800 километров).</span><span class="sxs-lookup"><span data-stu-id="78c1b-120">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="78c1b-121">Расположение офиса идентифицируется с помощью непонятного места на клиентском компьютере, а расположение выходного трафика определяется с помощью обратного IP-адреса в базы данных расположения.</span><span class="sxs-lookup"><span data-stu-id="78c1b-121">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="78c1b-122">Если служба расположения Windows отключена на компьютерах, расположение Office может быть неточным.</span><span class="sxs-lookup"><span data-stu-id="78c1b-122">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="78c1b-123">Расположение выхода из сети может быть неточным, если информация о базе данных обратного IP-адреса неточна.</span><span class="sxs-lookup"><span data-stu-id="78c1b-123">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="78c1b-124">Подробные сведения об этом сопоставлении включают расположение Office, предполагаемый процент от общего числа пользователей клиента в расположении, расположение текущего сетевого выхода, релевантность расположения выходных данных, расстояние между расположением и текущей точкой выхода, Дата первого обнаружения условия и Дата разрешения условия.</span><span class="sxs-lookup"><span data-stu-id="78c1b-124">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="78c1b-125">Что делать?</span><span class="sxs-lookup"><span data-stu-id="78c1b-125">What should I do?</span></span>

<span data-ttu-id="78c1b-126">Для этого мы рекомендуем использовать сетевой выход ближе к расположению Office, чтобы обеспечить оптимальную маршрутизацию подключений в глобальную сеть Майкрософт и на ближайшую переднюю дверцу службы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78c1b-126">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="78c1b-127">Если вы развернете доступ к сетевым выходным пользователям для пользователей, вы также можете улучшить производительность в будущем, так как корпорация Майкрософт развертывает в будущем как сетевые точки присутствия, так и передние двери обслуживания Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78c1b-127">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="78c1b-128">Для получения дополнительных сведений о том, как устранить эту проблему, просмотрите раздел исходящих [сетевых подключений локально](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) в [принципах подключения к сети Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="78c1b-128">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="78c1b-129">Более высокая производительность обнаружено соседних клиентов</span><span class="sxs-lookup"><span data-stu-id="78c1b-129">Better performance detected for customers near you</span></span>

<span data-ttu-id="78c1b-130">Это значение будет отображаться, если служба Network Insights обнаружит, что значительное количество клиентов в области Metro имеет лучшую производительность, чем у пользователей в вашей организации в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="78c1b-130">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="78c1b-131">В некоторых сводных представлениях это аббревиатура "Peers".</span><span class="sxs-lookup"><span data-stu-id="78c1b-131">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Относительная производительность сети](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="78c1b-133">Сценарий</span><span class="sxs-lookup"><span data-stu-id="78c1b-133">What does this mean?</span></span>

<span data-ttu-id="78c1b-134">В этом изучении изучается сводная производительность клиентов Microsoft 365 в том же городе, что и это расположение Office.</span><span class="sxs-lookup"><span data-stu-id="78c1b-134">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="78c1b-135">Это представление отображается в том случае, если средняя задержка пользователей составляет 10% выше средней задержки соседних клиентов.</span><span class="sxs-lookup"><span data-stu-id="78c1b-135">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="78c1b-136">Что делать?</span><span class="sxs-lookup"><span data-stu-id="78c1b-136">What should I do?</span></span>

<span data-ttu-id="78c1b-137">Это условие может быть связано с несколькими причинами, включая задержку в корпоративной сети или поставщике услуг Интернета, узких мест или архитектурные проблемы.</span><span class="sxs-lookup"><span data-stu-id="78c1b-137">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="78c1b-138">Проверьте задержку между каждым переходом между сетью Office и текущей передней дверцей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78c1b-138">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="78c1b-139">Дополнительные сведения см. в статье [принципы сетевого подключения Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="78c1b-139">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="78c1b-140">Использование неоптимальной передней дверцы службы Exchange Online</span><span class="sxs-lookup"><span data-stu-id="78c1b-140">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="78c1b-141">Это значение будет отображаться, если служба Network Insights обнаруживает, что пользователи в определенном расположении не подключаются к оптимальной передней дверце службы Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78c1b-141">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="78c1b-142">Эта аналитика сокращена в виде "маршрутизации" в некоторых сводных представлениях.</span><span class="sxs-lookup"><span data-stu-id="78c1b-142">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Неоптимальная Передняя дверца](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="78c1b-144">Сценарий</span><span class="sxs-lookup"><span data-stu-id="78c1b-144">What does this mean?</span></span>

<span data-ttu-id="78c1b-145">Мы перечислим передние двери служб Exchange Online, которые подходят для использования из города местонахождения Office с хорошей производительностью.</span><span class="sxs-lookup"><span data-stu-id="78c1b-145">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="78c1b-146">Если в текущем тесте показывается использование передней дверцы службы Exchange Online, которой нет в этом списке, мы вызываем эту рекомендацию.</span><span class="sxs-lookup"><span data-stu-id="78c1b-146">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="78c1b-147">Что делать?</span><span class="sxs-lookup"><span data-stu-id="78c1b-147">What should I do?</span></span>

<span data-ttu-id="78c1b-148">Использование неоптимальной передней дверцы службы Exchange Online может быть вызвано обратной связи в сети перед выходом в корпоративную сеть, в этом случае мы рекомендуем использовать локальную и прямую сеть.</span><span class="sxs-lookup"><span data-stu-id="78c1b-148">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="78c1b-149">Кроме того, это может быть вызвано использованием удаленного сервера рекурсивного разрешения DNS, в результате чего мы рекомендуем выравнивать рекурсивный сервер сопоставителя DNS с выходом в сеть.</span><span class="sxs-lookup"><span data-stu-id="78c1b-149">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="78c1b-150">Использование неоптимальной передней дверцы службы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="78c1b-150">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="78c1b-151">Это значение будет отображаться, если служба Network Insights обнаружит, что пользователи в определенном расположении не подключаются к ближайшей передней дверце службы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="78c1b-151">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="78c1b-152">Это сокращение сокращается как "АФД" в некоторых сводных представлениях.</span><span class="sxs-lookup"><span data-stu-id="78c1b-152">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Неоптимальная Передняя дверца](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="78c1b-154">Сценарий</span><span class="sxs-lookup"><span data-stu-id="78c1b-154">What does this mean?</span></span>

<span data-ttu-id="78c1b-155">Мы идентифицируем переднюю дверцу службы SharePoint Online, к которой подключается тестовый клиент.</span><span class="sxs-lookup"><span data-stu-id="78c1b-155">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="78c1b-156">Затем в городе местонахождения Office мы сравниваемся с ожидаемой внешней дверце службы SharePoint Online для этого города.</span><span class="sxs-lookup"><span data-stu-id="78c1b-156">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="78c1b-157">Если это не так, мы будем использовать эту рекомендацию.</span><span class="sxs-lookup"><span data-stu-id="78c1b-157">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="78c1b-158">Что делать?</span><span class="sxs-lookup"><span data-stu-id="78c1b-158">What should I do?</span></span>

<span data-ttu-id="78c1b-159">Использование неоптимальной передней дверцы службы SharePoint Online может быть вызвано обратной связи в сети перед выходом в корпоративную сеть, в этом случае мы рекомендуем использовать локальную и прямую сеть.</span><span class="sxs-lookup"><span data-stu-id="78c1b-159">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="78c1b-160">Кроме того, это может быть вызвано использованием удаленного сервера рекурсивного разрешения DNS, в результате чего мы рекомендуем выравнивать рекурсивный сервер сопоставителя DNS с выходом в сеть.</span><span class="sxs-lookup"><span data-stu-id="78c1b-160">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="78c1b-161">Минимальная скорость скачивания из передней дверцы SharePoint</span><span class="sxs-lookup"><span data-stu-id="78c1b-161">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="78c1b-162">Это значение будет отображаться, если служба Network Insights обнаружит, что пропускная способность между определенным расположением Office и SharePoint Online менее 1 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="78c1b-162">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="78c1b-163">Это сокращение сокращается до "пропускная способность" в некоторых сводных представлениях.</span><span class="sxs-lookup"><span data-stu-id="78c1b-163">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="78c1b-164">Сценарий</span><span class="sxs-lookup"><span data-stu-id="78c1b-164">What does this mean?</span></span>

<span data-ttu-id="78c1b-165">Скорость скачивания, которую пользователь может получить из SharePoint Online и фронтальных дверей службы OneDrive для бизнеса, измеряется в мегабайтах в секунду (Мбит/с).</span><span class="sxs-lookup"><span data-stu-id="78c1b-165">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="78c1b-166">Если это значение меньше 1 Мбит/с, мы предоставляем эту информацию.</span><span class="sxs-lookup"><span data-stu-id="78c1b-166">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="78c1b-167">Что делать?</span><span class="sxs-lookup"><span data-stu-id="78c1b-167">What should I do?</span></span>

<span data-ttu-id="78c1b-168">Для повышения скорости загрузки может потребоваться увеличить пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="78c1b-168">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="78c1b-169">Кроме того, может возникнуть перегрузка сети между пользовательскими машинами в расположении Office и внешней дверце службы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="78c1b-169">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="78c1b-170">Иногда это называется перегруженной потерей и позволяет ограничить скорость загрузки, доступную пользователям даже при наличии достаточной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="78c1b-170">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="78c1b-171">Оптимальный сетевой выход для пользователя в Китае</span><span class="sxs-lookup"><span data-stu-id="78c1b-171">China user optimal network egress</span></span>

<span data-ttu-id="78c1b-172">Это представление будет отображаться, если в Организации есть пользователи, подключающиеся к клиенту Microsoft 365 в других географических регионах.</span><span class="sxs-lookup"><span data-stu-id="78c1b-172">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="78c1b-173">Сценарий</span><span class="sxs-lookup"><span data-stu-id="78c1b-173">What does this mean?</span></span>

<span data-ttu-id="78c1b-174">Если в вашей организации есть подключение к частной глобальной сети, рекомендуется настроить сетевую цепь WAN из расположений Office в Китае, в которой есть сетевой выход в Интернет, в любом из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="78c1b-174">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="78c1b-175">Гонконг, САР</span><span class="sxs-lookup"><span data-stu-id="78c1b-175">Hong Kong</span></span>
- <span data-ttu-id="78c1b-176">Япония</span><span class="sxs-lookup"><span data-stu-id="78c1b-176">Japan</span></span>
- <span data-ttu-id="78c1b-177">Тайвань</span><span class="sxs-lookup"><span data-stu-id="78c1b-177">Taiwan</span></span>
- <span data-ttu-id="78c1b-178">Республика Корея</span><span class="sxs-lookup"><span data-stu-id="78c1b-178">South Korea</span></span>
- <span data-ttu-id="78c1b-179">Сингапур</span><span class="sxs-lookup"><span data-stu-id="78c1b-179">Singapore</span></span>
- <span data-ttu-id="78c1b-180">Малайзия</span><span class="sxs-lookup"><span data-stu-id="78c1b-180">Malaysia</span></span>

<span data-ttu-id="78c1b-181">Исходящий трафик из Интернета больше не влияет на производительность, а исходящий трафик в Китае может привести к большим задержкам и проблемам с подключением из-за перегрузки с перекрестными границами.</span><span class="sxs-lookup"><span data-stu-id="78c1b-181">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="78c1b-182">Что делать?</span><span class="sxs-lookup"><span data-stu-id="78c1b-182">What should I do?</span></span>

<span data-ttu-id="78c1b-183">Для получения дополнительных сведений об устранении проблем с производительностью, связанных с этим представлением, ознакомьтесь со статьей [Оптимизация производительности глобального клиента Office 365 для пользователей Китая](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="78c1b-183">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="78c1b-184">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="78c1b-184">Related topics</span></span>

[<span data-ttu-id="78c1b-185">Рекомендации по повышению производительности сети в центре администрирования Microsoft 365 (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="78c1b-185">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="78c1b-186">Оценка сети Microsoft 365 (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="78c1b-186">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="78c1b-187">Проверка подключения Microsoft 365 в центре администрирования M365 (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="78c1b-187">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="78c1b-188">Служба расположения сетевых подключений (Предварительная версия) Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="78c1b-188">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
