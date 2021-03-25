---
title: Отчет о состоянии и соблюдении требований к устройству в ATP Защитника Майкрософт
description: Отслеживание обнаружения состояния состояния устройства, состояния антивируса, платформы ОС и версий Windows 10 с помощью отчета о состоянии и соответствии требованиям к устройству
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
ms.openlocfilehash: 5229ba068672035c2dce3afee1919f9c2d7f9e44
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186453"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a826d-104">Отчет о состоянии устройств и соответствия требованиям в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a826d-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a826d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a826d-105">**Applies to:**</span></span>
- [<span data-ttu-id="a826d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a826d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a826d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a826d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="a826d-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a826d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a826d-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a826d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a826d-110">Отчет о состоянии устройств предоставляет сведения о устройствах в организации на высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="a826d-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="a826d-111">Отчет содержит сведения о состоянии здоровья датчика, состоянии антивируса, платформах ОС и версиях Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a826d-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="a826d-112">Панель мониторинга структурирована в два раздела: ![ Изображение отчета об устройстве](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="a826d-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="a826d-113">Раздел</span><span class="sxs-lookup"><span data-stu-id="a826d-113">Section</span></span> | <span data-ttu-id="a826d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a826d-114">Description</span></span>
:---|:---
<span data-ttu-id="a826d-115">1</span><span class="sxs-lookup"><span data-stu-id="a826d-115">1</span></span> | <span data-ttu-id="a826d-116">Тенденции устройства</span><span class="sxs-lookup"><span data-stu-id="a826d-116">Device trends</span></span>
<span data-ttu-id="a826d-117">2</span><span class="sxs-lookup"><span data-stu-id="a826d-117">2</span></span> | <span data-ttu-id="a826d-118">Сводка устройств (текущий день)</span><span class="sxs-lookup"><span data-stu-id="a826d-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="a826d-119">Тенденции устройства</span><span class="sxs-lookup"><span data-stu-id="a826d-119">Device trends</span></span> 
<span data-ttu-id="a826d-120">По умолчанию в трендах устройств отображаются сведения об устройстве за 30-дневный период, заканчивающийся в последний полный день.</span><span class="sxs-lookup"><span data-stu-id="a826d-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="a826d-121">Чтобы получить более точное представление о тенденциях, происходящих в вашей организации, вы можете отладить отчетный период, отрегулив показанный период времени.</span><span class="sxs-lookup"><span data-stu-id="a826d-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="a826d-122">Чтобы настроить период времени, выберите диапазон времени из параметров отсев:</span><span class="sxs-lookup"><span data-stu-id="a826d-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="a826d-123">30 дней</span><span class="sxs-lookup"><span data-stu-id="a826d-123">30 days</span></span>
- <span data-ttu-id="a826d-124">3 месяцев</span><span class="sxs-lookup"><span data-stu-id="a826d-124">3 months</span></span>
- <span data-ttu-id="a826d-125">6 месяцев</span><span class="sxs-lookup"><span data-stu-id="a826d-125">6 months</span></span>
- <span data-ttu-id="a826d-126">Пользовательские</span><span class="sxs-lookup"><span data-stu-id="a826d-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="a826d-127">Эти фильтры применяются только в разделе тенденции устройства.</span><span class="sxs-lookup"><span data-stu-id="a826d-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="a826d-128">Это не влияет на раздел сводки устройств.</span><span class="sxs-lookup"><span data-stu-id="a826d-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="a826d-129">Сводка устройств</span><span class="sxs-lookup"><span data-stu-id="a826d-129">Device summary</span></span> 
<span data-ttu-id="a826d-130">В то время как в трендах устройств показаны сведения об устройстве в тренде, в сводке устройства показана информация об устройстве, охватившая текущий день.</span><span class="sxs-lookup"><span data-stu-id="a826d-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="a826d-131">Данные, отражающиеся в сводной статье, могут быть за 180 дней до текущей даты.</span><span class="sxs-lookup"><span data-stu-id="a826d-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="a826d-132">Например, если сегодня 27 марта 2019 г., данные сводного раздела будут отражать цифры, начиная с 28 сентября 2018 г. по 27 марта 2019 г.</span><span class="sxs-lookup"><span data-stu-id="a826d-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="a826d-133">Фильтр, применяемый в разделе тенденции, не применяется в сводной части.</span><span class="sxs-lookup"><span data-stu-id="a826d-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="a826d-134">Раздел тенденции устройства позволяет сверлить список устройств с соответствующим фильтром, примененным к ней.</span><span class="sxs-lookup"><span data-stu-id="a826d-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="a826d-135">Например, щелкнув на панели Неактивный в карточке состояния здоровья датчика, вы сможете получить список устройств с результатами, показывающими только устройства, состояние датчика которых неактивно.</span><span class="sxs-lookup"><span data-stu-id="a826d-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="a826d-136">Атрибуты устройства</span><span class="sxs-lookup"><span data-stu-id="a826d-136">Device attributes</span></span>
<span data-ttu-id="a826d-137">Отчет состоит из карт, отображает следующие атрибуты устройства:</span><span class="sxs-lookup"><span data-stu-id="a826d-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="a826d-138">**Состояние здоровья:** показывает сведения о состоянии датчика на устройствах, обеспечивая агрегированное представление устройств, активных, испытывающих нарушения связи, неактивных или не просматривающих данных датчиков.</span><span class="sxs-lookup"><span data-stu-id="a826d-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="a826d-139">**Состояние антивируса для активных устройств с Windows 10:** показывает количество устройств и состояние антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a826d-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="a826d-140">**Платформы ОС:** показывает распространение платформ ОС, которые существуют в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a826d-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="a826d-141">**Windows 10 версии**: показывает распространение устройств Windows 10 и их версий в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a826d-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="a826d-142">Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="a826d-142">Filter data</span></span>
 
<span data-ttu-id="a826d-143">Используйте предоставленные фильтры, чтобы включить или исключить устройства с определенными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="a826d-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="a826d-144">Можно выбрать несколько фильтров для применения из атрибутов устройства.</span><span class="sxs-lookup"><span data-stu-id="a826d-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="a826d-145">Эти фильтры применяются **для всех** карт в отчете.</span><span class="sxs-lookup"><span data-stu-id="a826d-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="a826d-146">Например, чтобы показать данные о устройствах с Windows 10 с состоянием здоровья активных датчиков:</span><span class="sxs-lookup"><span data-stu-id="a826d-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="a826d-147">В **фильтрах > состояние состояния > Active**.</span><span class="sxs-lookup"><span data-stu-id="a826d-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="a826d-148">Затем выберите **платформы ОС > Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="a826d-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="a826d-149">Нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a826d-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="a826d-150">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="a826d-150">Related topic</span></span>
- [<span data-ttu-id="a826d-151">Отчет о защите от угроз</span><span class="sxs-lookup"><span data-stu-id="a826d-151">Threat protection report</span></span>](threat-protection-reports.md)
