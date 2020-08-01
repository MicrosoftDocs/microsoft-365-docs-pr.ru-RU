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
# <a name="battery-insights"></a><span data-ttu-id="f752c-103">Аналитика аккумулятора</span><span class="sxs-lookup"><span data-stu-id="f752c-103">Battery insights</span></span>
<span data-ttu-id="f752c-104">Это представление предоставляет метрики энергопотребления, аккумулятора и использования приложений для настольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f752c-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f752c-105">В этих целях приложение считается "используемым", если оно работает и в фокусе.</span><span class="sxs-lookup"><span data-stu-id="f752c-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="f752c-106">Чтобы просмотреть данные об использовании, перейдите на вкладку **батарея** .</span><span class="sxs-lookup"><span data-stu-id="f752c-106">To view usage data, select the **Battery** tab.</span></span>

![Область батареи: прогнозируемый срок работы батареи на модель устройства в верхнем левом углу, в верхнем левом углу, в таблице "сведения" в нижней части.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="f752c-109">Прогнозируемый срок работы батареи</span><span class="sxs-lookup"><span data-stu-id="f752c-109">Predicted battery life</span></span>

<span data-ttu-id="f752c-110">В области **предполагаемой длительности работы батареи** мы предоставляем прогноз для предполагаемого времени работы батарей для устройств, организованных по модели устройств.</span><span class="sxs-lookup"><span data-stu-id="f752c-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="f752c-111">Эти данные извлекаются из-за выборки энергопотребления, времени использования и мощности аккумулятора из случайного <em>выбора</em> устройств в управляемом развертывании настольных систем Майкрософт, которые также сообщают о данных.</span><span class="sxs-lookup"><span data-stu-id="f752c-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="f752c-112">Таблица предоставляет прогнозируемый срок работы батареи (в часах), среднее время работы от аккумулятора для тех же моделей в других управляемых настольных системах Майкрософт, а также количество устройств, сообщающих эти данные в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="f752c-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="f752c-113">Отсортируйте данные, выбрав заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="f752c-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="f752c-114">Топ потребителей</span><span class="sxs-lookup"><span data-stu-id="f752c-114">Top energy consumers</span></span>

<span data-ttu-id="f752c-115">В области **Топ потребителей** вы найдете приложения в вашей среде, которые потребляют наибольшую энергию в милливатт-hours (МВХ).</span><span class="sxs-lookup"><span data-stu-id="f752c-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="f752c-116">Отображаемые приложения относятся к конкретному устройству, которое выбирается в разделе **предполагаемая продолжительность работы батарей** слева.</span><span class="sxs-lookup"><span data-stu-id="f752c-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="f752c-117">Например, чтобы увидеть потребление для каждого приложения для устройств контактной книги Майкрософт 2, выберите эту строку в области срок действия аккумулятора.</span><span class="sxs-lookup"><span data-stu-id="f752c-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="f752c-118">Если вы не выбираете какую-либо модель, отображаются данные о потреблении для всех приложений, которые у нас есть данные для совместного использования.</span><span class="sxs-lookup"><span data-stu-id="f752c-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="f752c-119">Для каждого приложения цветные сегменты показывают, как вы распределяете использование энергии приложением в следующих категориях:</span><span class="sxs-lookup"><span data-stu-id="f752c-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="f752c-120">ЦП</span><span class="sxs-lookup"><span data-stu-id="f752c-120">CPU</span></span>
- <span data-ttu-id="f752c-121">Отображение</span><span class="sxs-lookup"><span data-stu-id="f752c-121">Display</span></span>
- <span data-ttu-id="f752c-122">Сеть</span><span class="sxs-lookup"><span data-stu-id="f752c-122">Network</span></span>
- <span data-ttu-id="f752c-123">Другое</span><span class="sxs-lookup"><span data-stu-id="f752c-123">Other</span></span>

<span data-ttu-id="f752c-124">"Другое" может включать энергопотребление в различных источниках, таких как активность диска, использование мобильного широкополосного подключения и энергия, потеряющая доступ к внутренним сопротивлением.</span><span class="sxs-lookup"><span data-stu-id="f752c-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="f752c-125">Вы можете отфильтровать это представление, чтобы отображались только фоновые приложения, фоновые приложения или и то, и другое, с помощью меню в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="f752c-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="f752c-126">Приложения переднего плана — это те, у которых есть взаимодействие с пользователем за последние 28 дней, например, выбор чего-нибудь с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="f752c-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="f752c-127">Аналитика</span><span class="sxs-lookup"><span data-stu-id="f752c-127">Insights</span></span>

<span data-ttu-id="f752c-128">Область **Insights** показывает самых трех потребителей Energy Energy в категориях ЦП и сети.</span><span class="sxs-lookup"><span data-stu-id="f752c-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="f752c-129">В сравнении со всеми развертываниями на настольных компьютерах Майкрософт используются эти элементы выше среднего.</span><span class="sxs-lookup"><span data-stu-id="f752c-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="f752c-130">Ресурс Display не отображается, так как он сильно зависит от времени использования устройств и параметров яркости экрана.</span><span class="sxs-lookup"><span data-stu-id="f752c-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="f752c-131">Для получения дополнительных сведений выберите вхождения в столбце **сведения** .</span><span class="sxs-lookup"><span data-stu-id="f752c-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="f752c-132">Оптимизация заряда батареи</span><span class="sxs-lookup"><span data-stu-id="f752c-132">Battery optimization</span></span>

<span data-ttu-id="f752c-133">Windows 10 предлагает множество [параметров устройств](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) для улучшения энергопотребления и увеличения времени работы батарей для настольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f752c-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f752c-134">Некоторые из этих параметров могут привести к снижению числа других функций Windows, поэтому необходимо учитывать другие факторы, такие как роль устройства в Организации.</span><span class="sxs-lookup"><span data-stu-id="f752c-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="f752c-135">Поддержка Windows поддерживает список этих [советов по экономии заряда](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span><span class="sxs-lookup"><span data-stu-id="f752c-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="f752c-136">Пользователи могут настраивать некоторые параметры самостоятельно, не требуя повышения прав или поддержки администратора.</span><span class="sxs-lookup"><span data-stu-id="f752c-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="f752c-137">Для других параметров требуется поддержка ИТ ИТ ИТ администратора.</span><span class="sxs-lookup"><span data-stu-id="f752c-137">Other settings require support from your organization's IT administrator.</span></span>
