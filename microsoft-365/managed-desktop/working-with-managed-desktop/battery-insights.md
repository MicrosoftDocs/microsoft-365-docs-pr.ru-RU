---
title: Аналитика аккумулятора
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529843"
---
# <a name="battery-insights"></a><span data-ttu-id="9816f-103">Аналитика аккумулятора</span><span class="sxs-lookup"><span data-stu-id="9816f-103">Battery insights</span></span>
<span data-ttu-id="9816f-104">Это представление предоставляет показатели использования питания, заряда батареи и приложений для настольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9816f-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9816f-105">Для этих целей приложение считается "в использовании", если оно запущено и находится в фокусе.</span><span class="sxs-lookup"><span data-stu-id="9816f-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="9816f-106">Чтобы просмотреть данные об использовании, выберите вкладку **"Аккумулятор".**</span><span class="sxs-lookup"><span data-stu-id="9816f-106">To view usage data, select the **Battery** tab.</span></span>

![Battery pane: predicted battery life per device model in upper left, top energy consumers (by app) in upper right, insights table across the bottom.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="9816f-109">Прогнозируемый срок работы батареи</span><span class="sxs-lookup"><span data-stu-id="9816f-109">Predicted battery life</span></span>

<span data-ttu-id="9816f-110">В области **"Прогнозируемый срок работы батареи"** мы предоставляем прогнозирование ожидаемого времени работы батареи на ваших устройствах, упростив их по модели устройства.</span><span class="sxs-lookup"><span data-stu-id="9816f-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="9816f-111">Эти данные являются производными от использования энергии выборки, <em></em> времени использования и емкости батареи из случайного выбора устройств в развертывании компьютеров, управляемых Майкрософт, которые также сообщают данные.</span><span class="sxs-lookup"><span data-stu-id="9816f-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="9816f-112">В таблице приводится прогнозируемый срок работы батареи (в часах), среднее время работы батареи для тех же моделей в других развертываниях компьютеров, управляемых Майкрософт, а также количество устройств, которые сообщают эти данные в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="9816f-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="9816f-113">Сортировать данные, выбирая заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="9816f-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="9816f-114">Лучшие потребители энергии</span><span class="sxs-lookup"><span data-stu-id="9816f-114">Top energy consumers</span></span>

<span data-ttu-id="9816f-115">В области **"Самые распространенные** потребители энергии" вы найдете приложения в своей среде, которые потребляют больше всего энергии в милливатт-часах (mWh).</span><span class="sxs-lookup"><span data-stu-id="9816f-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="9816f-116">Приложения, показанные для каждого конкретного устройства, выбираются в разделе **"Прогнозируемый** срок работы батареи" слева.</span><span class="sxs-lookup"><span data-stu-id="9816f-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="9816f-117">Например, чтобы увидеть, как приложение использует устройства Microsoft Surface Book 2, выберите эту строку в области заряда батареи.</span><span class="sxs-lookup"><span data-stu-id="9816f-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="9816f-118">Если вы не выберете ни одной модели, данные о потреблении приложений будут показаны для всех приложений, у нас есть данные для совместной обработки.</span><span class="sxs-lookup"><span data-stu-id="9816f-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="9816f-119">Цветные сегменты для каждого приложения показывают распределение энергопотребления приложения между этими категориями:</span><span class="sxs-lookup"><span data-stu-id="9816f-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="9816f-120">ЦП</span><span class="sxs-lookup"><span data-stu-id="9816f-120">CPU</span></span>
- <span data-ttu-id="9816f-121">Отображение</span><span class="sxs-lookup"><span data-stu-id="9816f-121">Display</span></span>
- <span data-ttu-id="9816f-122">Сеть</span><span class="sxs-lookup"><span data-stu-id="9816f-122">Network</span></span>
- <span data-ttu-id="9816f-123">Другое</span><span class="sxs-lookup"><span data-stu-id="9816f-123">Other</span></span>

<span data-ttu-id="9816f-124">"Другое" может включать потребление энергии различными источниками, такими как активность диска, использование мобильного широкополосного подключения и потеря энергии для внутреннего устойчивости.</span><span class="sxs-lookup"><span data-stu-id="9816f-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="9816f-125">Вы можете отфильтровать это представление, чтобы показывать только приложения переднего плана, фоновые приложения или и то, и другое с помощью меню в правом верхнем.</span><span class="sxs-lookup"><span data-stu-id="9816f-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="9816f-126">Приложения переднего плана — это приложения, которые взаимодействовали с пользователем в течение последних 28 дней, например для выбора чего-либо с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="9816f-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="9816f-127">Аналитика</span><span class="sxs-lookup"><span data-stu-id="9816f-127">Insights</span></span>

<span data-ttu-id="9816f-128">Область **"Insights"** показывает три основных потребителей энергии в категориях ЦП и сети.</span><span class="sxs-lookup"><span data-stu-id="9816f-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="9816f-129">Эти элементы потребляют больше энергии, чем в среднем, по сравнению со всеми развертываниями компьютеров, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9816f-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="9816f-130">Мы не отображаем ресурс дисплея, так как он сильно зависит от времени использования устройства и параметров яркости экрана.</span><span class="sxs-lookup"><span data-stu-id="9816f-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="9816f-131">Выберите листинги в столбце **"Сведения"** для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="9816f-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="9816f-132">Оптимизация батареи</span><span class="sxs-lookup"><span data-stu-id="9816f-132">Battery optimization</span></span>

<span data-ttu-id="9816f-133">Windows 10 предлагает множество [параметров](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) устройств для повышения энергопотребления и повышения заряда батареи на настольных устройствах, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9816f-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9816f-134">Некоторые из этих параметров могут уменьшить другие функциональные возможности Windows, поэтому вам также придется учитывать другие факторы, такие как роль устройства в организации.</span><span class="sxs-lookup"><span data-stu-id="9816f-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="9816f-135">Поддержка Windows поддерживает список этих советов по экономии [заряда.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="9816f-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="9816f-136">Пользователи могут самостоятельно настраивать некоторые параметры без повышения прав администратора или поддержки.</span><span class="sxs-lookup"><span data-stu-id="9816f-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="9816f-137">Другие параметры требуют поддержки ИТ-администратора организации.</span><span class="sxs-lookup"><span data-stu-id="9816f-137">Other settings require support from your organization's IT administrator.</span></span>
