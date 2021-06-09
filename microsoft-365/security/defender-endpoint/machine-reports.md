---
title: Отчет о состоянии устройств и соответствия требованиям в Microsoft Defender для конечной точки
description: Отслеживание обнаружения состояния состояния устройства, состояния антивируса, платформы ОС и Windows 10 с помощью отчета о состоянии и соответствии требованиям к устройству
keywords: состояние здоровья, антивирус, платформа ос, версия Windows 10, версия, здоровье, соответствие требованиям, состояние
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 35100a4b8bdaee23c427816450e948ced9ed3191
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860295"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="25326-104">Отчет о состоянии устройств и соответствия требованиям в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="25326-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="25326-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="25326-105">**Applies to:**</span></span>
- [<span data-ttu-id="25326-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="25326-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="25326-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25326-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="25326-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="25326-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="25326-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="25326-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="25326-110">Отчет о состоянии устройств предоставляет сведения о устройствах в организации на высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="25326-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="25326-111">Отчет содержит сведения о состоянии здоровья датчика, состоянии антивируса, платформах ОС и Windows 10 версиях.</span><span class="sxs-lookup"><span data-stu-id="25326-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="25326-112">Панель мониторинга структурирована в два раздела: ![ Изображение отчета об устройстве](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="25326-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="25326-113">Section</span><span class="sxs-lookup"><span data-stu-id="25326-113">Section</span></span> | <span data-ttu-id="25326-114">Описание</span><span class="sxs-lookup"><span data-stu-id="25326-114">Description</span></span>
:---|:---
<span data-ttu-id="25326-115">1</span><span class="sxs-lookup"><span data-stu-id="25326-115">1</span></span> | <span data-ttu-id="25326-116">Тенденции устройства</span><span class="sxs-lookup"><span data-stu-id="25326-116">Device trends</span></span>
<span data-ttu-id="25326-117">2</span><span class="sxs-lookup"><span data-stu-id="25326-117">2</span></span> | <span data-ttu-id="25326-118">Сводка устройств (текущий день)</span><span class="sxs-lookup"><span data-stu-id="25326-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="25326-119">Тенденции устройства</span><span class="sxs-lookup"><span data-stu-id="25326-119">Device trends</span></span> 
<span data-ttu-id="25326-120">По умолчанию в трендах устройств отображаются сведения об устройстве за 30-дневный период, заканчивающийся в последний полный день.</span><span class="sxs-lookup"><span data-stu-id="25326-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="25326-121">Чтобы получить более точное представление о тенденциях, происходящих в вашей организации, вы можете отладить отчетный период, отрегулив показанный период времени.</span><span class="sxs-lookup"><span data-stu-id="25326-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="25326-122">Чтобы настроить период времени, выберите диапазон времени из параметров отсев:</span><span class="sxs-lookup"><span data-stu-id="25326-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="25326-123">30 дней</span><span class="sxs-lookup"><span data-stu-id="25326-123">30 days</span></span>
- <span data-ttu-id="25326-124">3 месяцев</span><span class="sxs-lookup"><span data-stu-id="25326-124">3 months</span></span>
- <span data-ttu-id="25326-125">6 месяцев</span><span class="sxs-lookup"><span data-stu-id="25326-125">6 months</span></span>
- <span data-ttu-id="25326-126">Пользовательские</span><span class="sxs-lookup"><span data-stu-id="25326-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="25326-127">Эти фильтры применяются только в разделе тенденции устройства.</span><span class="sxs-lookup"><span data-stu-id="25326-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="25326-128">Это не влияет на раздел сводки устройств.</span><span class="sxs-lookup"><span data-stu-id="25326-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="25326-129">Сводка устройств</span><span class="sxs-lookup"><span data-stu-id="25326-129">Device summary</span></span> 
<span data-ttu-id="25326-130">В то время как в трендах устройств показаны сведения об устройстве в тренде, в сводке устройства показана информация об устройстве, охватившая текущий день.</span><span class="sxs-lookup"><span data-stu-id="25326-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="25326-131">Данные, отражающиеся в сводной статье, могут быть за 180 дней до текущей даты.</span><span class="sxs-lookup"><span data-stu-id="25326-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="25326-132">Например, если сегодня 27 марта 2019 г., данные сводного раздела будут отражать цифры, начиная с 28 сентября 2018 г. по 27 марта 2019 г.</span><span class="sxs-lookup"><span data-stu-id="25326-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="25326-133">Фильтр, применяемый в разделе тенденции, не применяется в сводной части.</span><span class="sxs-lookup"><span data-stu-id="25326-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="25326-134">Раздел тенденции устройства позволяет сверлить список устройств с соответствующим фильтром, примененным к ней.</span><span class="sxs-lookup"><span data-stu-id="25326-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="25326-135">Например, щелкнув на панели Неактивный в карточке состояния здоровья датчика, вы сможете получить список устройств с результатами, показывающими только устройства, состояние датчика которых неактивно.</span><span class="sxs-lookup"><span data-stu-id="25326-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="25326-136">Атрибуты устройства</span><span class="sxs-lookup"><span data-stu-id="25326-136">Device attributes</span></span>
<span data-ttu-id="25326-137">Отчет состоит из карт, отображает следующие атрибуты устройства:</span><span class="sxs-lookup"><span data-stu-id="25326-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="25326-138">**Состояние здоровья:** показывает сведения о состоянии датчика на устройствах, обеспечивая агрегированное представление устройств, активных, испытывающих нарушения связи, неактивных или не просматривающих данных датчиков.</span><span class="sxs-lookup"><span data-stu-id="25326-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="25326-139">**Состояние антивируса для** Windows 10 устройств: показывает количество устройств и состояние антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="25326-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="25326-140">**Платформы ОС:** показывает распространение платформ ОС, которые существуют в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="25326-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="25326-141">**Windows 10:** показывает распространение Windows 10 устройств и их версий в организации.</span><span class="sxs-lookup"><span data-stu-id="25326-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="25326-142">Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="25326-142">Filter data</span></span>
 
<span data-ttu-id="25326-143">Используйте предоставленные фильтры, чтобы включить или исключить устройства с определенными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="25326-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="25326-144">Можно выбрать несколько фильтров для применения из атрибутов устройства.</span><span class="sxs-lookup"><span data-stu-id="25326-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="25326-145">Эти фильтры применяются **для всех** карт в отчете.</span><span class="sxs-lookup"><span data-stu-id="25326-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="25326-146">Например, чтобы показать данные о Windows 10 устройствах с состоянием здоровья active sensor:</span><span class="sxs-lookup"><span data-stu-id="25326-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="25326-147">В **фильтрах > состояние состояния > Active**.</span><span class="sxs-lookup"><span data-stu-id="25326-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="25326-148">Затем выберите **платформы ОС > Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="25326-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="25326-149">Нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="25326-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="25326-150">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="25326-150">Related topic</span></span>
- [<span data-ttu-id="25326-151">Отчет о защите от угроз</span><span class="sxs-lookup"><span data-stu-id="25326-151">Threat protection report</span></span>](threat-protection-reports.md)
