---
title: Microsoft 365 Network Connectivity Location Services (предварительная версия)
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
description: Microsoft 365 Network Connectivity Location Services (предварительная версия)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200785"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a><span data-ttu-id="63079-103">Microsoft 365 Network Connectivity Location Services (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="63079-103">Microsoft 365 Network Connectivity Location Services (preview)</span></span>

<span data-ttu-id="63079-104">Центр администрирования Microsoft 365 теперь отображает network **Insights и** рекомендации по производительности, которые являются показателями производительности, собранными из клиента Microsoft 365 и доступными для просмотра только администраторами в клиенте.</span><span class="sxs-lookup"><span data-stu-id="63079-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics collected from your Microsoft 365 tenant and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="63079-105">Организационное сетевое подключение разработано для каждого расположения офиса через сетевой перенаправление в Интернет.</span><span class="sxs-lookup"><span data-stu-id="63079-105">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="63079-106">Клиентские подключения Microsoft 365 используют этот маршрут, а затем через Интернет к серверам microsoft service front door servers.</span><span class="sxs-lookup"><span data-stu-id="63079-106">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="63079-107">Определение местоположений офисов — это ключ к возможности показать эти сетевые данные.</span><span class="sxs-lookup"><span data-stu-id="63079-107">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="63079-108">Расположение в измерениях сети</span><span class="sxs-lookup"><span data-stu-id="63079-108">Location in network measurements</span></span>

<span data-ttu-id="63079-109">Администратор организации может включить расположение в показатели сети, используемые этой функцией.</span><span class="sxs-lookup"><span data-stu-id="63079-109">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="63079-110">Это позволяет автоматически обнаруживть город, в котором расположен каждый офис.</span><span class="sxs-lookup"><span data-stu-id="63079-110">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="63079-111">Сведения о расположении не точны и запутыются до 300 м и классифицируются по городам.</span><span class="sxs-lookup"><span data-stu-id="63079-111">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="63079-112">Во время записи расположения на устройстве с  Windows на панели инструментов будет показываться значок "Расположение в использовании", и администраторам может потребоваться уведомить пользователей об этом.</span><span class="sxs-lookup"><span data-stu-id="63079-112">At the time when location is captured on a Windows device it will show a **Location In-Use** icon in the tool tray and administrators may want to notify users of this.</span></span> <span data-ttu-id="63079-113">При такой обработке расположение обрабатывается как расположение офиса организации, а не как расположение человека или устройства.</span><span class="sxs-lookup"><span data-stu-id="63079-113">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="63079-114">В этих обнаруженных городах расположений офисов могут быть показаны сетевые данные.</span><span class="sxs-lookup"><span data-stu-id="63079-114">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="63079-115">Если требуется большая точность рекомендаций, администратор может ввести конкретные адреса расположения офиса, и вместо них будут агрегироваться сетевые данные.</span><span class="sxs-lookup"><span data-stu-id="63079-115">If greater accuracy of recommendations is desired, an administrator can enter specific office location addresses and the network insights will be aggregated to those instead.</span></span> <span data-ttu-id="63079-116">Расположения Office нельзя агрегировать более чем на 300 метров.</span><span class="sxs-lookup"><span data-stu-id="63079-116">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="63079-117">Расположение в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63079-117">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="63079-118">В Центре администрирования Microsoft 365 элементы управления картой Bing используются, чтобы показать расположение офисов организации и топологию периметра сети для выбранного расположения офиса.</span><span class="sxs-lookup"><span data-stu-id="63079-118">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are and to show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="63079-119">Когда администратор добавляет сведения об определенных адресах для офисов, карты Bing также используются для подсказок адресов для упростить ввод данных.</span><span class="sxs-lookup"><span data-stu-id="63079-119">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="63079-120">Условия использования</span><span class="sxs-lookup"><span data-stu-id="63079-120">Terms of Use</span></span>

<span data-ttu-id="63079-121">Любой контент, предоставляемый через карты Bing, включая геокоды, может использоваться только в продукте, через который предоставляется контент.</span><span class="sxs-lookup"><span data-stu-id="63079-121">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="63079-122">Использование клиентом служб расположения в Центре администрирования Microsoft 365 на сфере карт Bing регулируется условиями использования карт _Bing,_ доступными на сайте и в Заявлении о конфиденциальности Корпорации Майкрософт. <https://go.microsoft.com/?linkid=9710837> <https://go.microsoft.com/fwlink/?LinkID=248686.></span><span class="sxs-lookup"><span data-stu-id="63079-122">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the _Microsoft Privacy Statement_ available at <https://go.microsoft.com/fwlink/?LinkID=248686.></span></span>

<span data-ttu-id="63079-123">Эта функция, предоставляемая с помощью карт Bing, также поддерживается **технологией Here Technologies.**</span><span class="sxs-lookup"><span data-stu-id="63079-123">This feature, provided through Bing Maps, is also supported by **Here Technologies**.</span></span> <span data-ttu-id="63079-124">Как карты Bing используют службы определения местоположения, предоставляемые технологией Here Technologies, регулируются условиями _службы here Technologies,_ доступными в <https://legal.here.com/en-gb/terms> .</span><span class="sxs-lookup"><span data-stu-id="63079-124">How Bing Maps leverages location services provided by Here Technologies is governed by the _Here Technologies Service Terms_ available at <https://legal.here.com/en-gb/terms>.</span></span>

## <a name="related-topics"></a><span data-ttu-id="63079-125">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="63079-125">Related topics</span></span>

[<span data-ttu-id="63079-126">Сетевое подключение в Центре администрирования Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="63079-126">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="63079-127">Анализ производительности сети Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="63079-127">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="63079-128">Оценка сети Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="63079-128">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="63079-129">Тест подключения Microsoft 365 в Центре администрирования M365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="63079-129">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
