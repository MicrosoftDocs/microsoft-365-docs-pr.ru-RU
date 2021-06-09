---
title: Аналитика аккумулятора
description: Отчет, в который показаны данные о прогнозируемом сроке службы батареи и главных потребителей электроэнергии
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739831"
---
# <a name="battery-insights"></a><span data-ttu-id="b0c77-104">Аналитика аккумулятора</span><span class="sxs-lookup"><span data-stu-id="b0c77-104">Battery insights</span></span>
<span data-ttu-id="b0c77-105">В этом представлении метрики использования питания, батареи и приложений для компьютеры, управляемые Майкрософт устройств.</span><span class="sxs-lookup"><span data-stu-id="b0c77-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b0c77-106">Для этих целей приложение считается "в использовании", если оно запущено и находится в фокусе.</span><span class="sxs-lookup"><span data-stu-id="b0c77-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="b0c77-107">Чтобы просмотреть данные об использовании, выберите **вкладку Battery.**</span><span class="sxs-lookup"><span data-stu-id="b0c77-107">To view usage data, select the **Battery** tab.</span></span>

![Области батареи: прогнозируемый срок службы батареи на одну модель устройства в левом верхнем слева, верхние потребители энергии (по приложению) в верхнем правом, таблица insights в нижней части.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="b0c77-110">Прогнозируемый срок службы батареи</span><span class="sxs-lookup"><span data-stu-id="b0c77-110">Predicted battery life</span></span>

<span data-ttu-id="b0c77-111">В области **предсказания времени автономной** работы мы предоставляем прогнозы ожидаемого времени автономной работы для устройств, организованные моделью устройства.</span><span class="sxs-lookup"><span data-stu-id="b0c77-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c77-112">Эти данные получены из использования энергии выборки, времени использования <em></em> и емкости батареи из случайного выбора устройств в развертывании компьютеры, управляемые Майкрософт, которые также сообщают данные.</span><span class="sxs-lookup"><span data-stu-id="b0c77-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="b0c77-113">В таблице содержится прогнозируемый срок службы батареи (в часах), средний срок службы батареи для тех же моделей в других компьютеры, управляемые Майкрософт развертываниях, а также количество устройств, сообщив об этих данных в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="b0c77-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="b0c77-114">Сортировать данные, выбрав заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="b0c77-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="b0c77-115">Лучшие потребители энергии</span><span class="sxs-lookup"><span data-stu-id="b0c77-115">Top energy consumers</span></span>

<span data-ttu-id="b0c77-116">В области **"Лучшие потребители** энергии" вы найдете приложения в среде, которые потребляют больше всего энергии в миллиВатт-часах (мВт/ч).</span><span class="sxs-lookup"><span data-stu-id="b0c77-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="b0c77-117">Показано, что приложения находятся на определенном устройстве, которое вы выбираете в разделе Предсказано время **автономной** работы слева.</span><span class="sxs-lookup"><span data-stu-id="b0c77-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="b0c77-118">Например, чтобы увидеть потребление в приложении для устройств Microsoft Surface Book 2, выберите строку в области автономной работы.</span><span class="sxs-lookup"><span data-stu-id="b0c77-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="b0c77-119">Если вы не выбираете любую модель, показанные данные потребления приложений доступны для всех приложений, для которые у нас есть данные для коллективного использования.</span><span class="sxs-lookup"><span data-stu-id="b0c77-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="b0c77-120">Для каждого приложения цветные сегменты показывают распределение энергопотребления приложения среди этих категорий:</span><span class="sxs-lookup"><span data-stu-id="b0c77-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="b0c77-121">ЦП</span><span class="sxs-lookup"><span data-stu-id="b0c77-121">CPU</span></span>
- <span data-ttu-id="b0c77-122">Дисплей</span><span class="sxs-lookup"><span data-stu-id="b0c77-122">Display</span></span>
- <span data-ttu-id="b0c77-123">Сеть</span><span class="sxs-lookup"><span data-stu-id="b0c77-123">Network</span></span>
- <span data-ttu-id="b0c77-124">Другое</span><span class="sxs-lookup"><span data-stu-id="b0c77-124">Other</span></span>

<span data-ttu-id="b0c77-125">"Другие" могут включать потребление энергии различными источниками, такими как дисковая активность, использование мобильной широкополосной связи и потеря энергии из-за внутреннего сопротивления.</span><span class="sxs-lookup"><span data-stu-id="b0c77-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="b0c77-126">Это представление можно отфильтровать, чтобы показывать только приложения переднего плана, фоновые приложения или оба с помощью меню в правом верхнем справа.</span><span class="sxs-lookup"><span data-stu-id="b0c77-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="b0c77-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span><span class="sxs-lookup"><span data-stu-id="b0c77-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="b0c77-128">Аналитика</span><span class="sxs-lookup"><span data-stu-id="b0c77-128">Insights</span></span>

<span data-ttu-id="b0c77-129">В **области Insights** показаны три основных потребителей энергии в категориях ЦП и сети.</span><span class="sxs-lookup"><span data-stu-id="b0c77-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="b0c77-130">Эти элементы потребляют более высокую, чем в среднем, энергию по сравнению со всеми компьютеры, управляемые Майкрософт развертываниями.</span><span class="sxs-lookup"><span data-stu-id="b0c77-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="b0c77-131">Мы не показывем ресурс отображения, так как он сильно зависит от времени использования устройства и параметров яркости экрана.</span><span class="sxs-lookup"><span data-stu-id="b0c77-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="b0c77-132">Дополнительные сведения выберите списки в столбце **Сведения.**</span><span class="sxs-lookup"><span data-stu-id="b0c77-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="b0c77-133">Оптимизация батареи</span><span class="sxs-lookup"><span data-stu-id="b0c77-133">Battery optimization</span></span>

<span data-ttu-id="b0c77-134">Windows 10 предлагает множество [параметров](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) устройств для повышения энергопотребления и увеличения времени автономной работы компьютеры, управляемые Майкрософт устройств.</span><span class="sxs-lookup"><span data-stu-id="b0c77-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b0c77-135">Некоторые из этих параметров могут Windows других функциональных возможностей, поэтому вам также придется учитывать другие факторы, такие как роль устройства в организации.</span><span class="sxs-lookup"><span data-stu-id="b0c77-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="b0c77-136">Windows поддерживает список этих советов по экономии [батареи.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="b0c77-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="b0c77-137">Пользователи могут самостоятельно настраивать некоторые параметры без необходимости повышения или поддержки администратора.</span><span class="sxs-lookup"><span data-stu-id="b0c77-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="b0c77-138">Другие параметры требуют поддержки от ИТ-администратора организации.</span><span class="sxs-lookup"><span data-stu-id="b0c77-138">Other settings require support from your organization's IT administrator.</span></span>
