---
title: Использование меток конфиденциальности для определения приоритетов реагирования на инциденты
description: Узнайте, как использовать метки конфиденциальности для приоритетов и расследования инцидентов
keywords: сведения, защита, данные, потери, предотвращение, метки, dlp, инциденты, расследование, расследование
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: bff490edcc79bc8f96e65c8b27586ca8b54e5bce
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186129"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="c5fca-104">Использование меток конфиденциальности для определения приоритетов реагирования на инциденты</span><span class="sxs-lookup"><span data-stu-id="c5fca-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c5fca-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c5fca-105">**Applies to:**</span></span>
- [<span data-ttu-id="c5fca-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c5fca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c5fca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5fca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c5fca-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c5fca-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c5fca-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c5fca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="c5fca-110">Типичный расширенный жизненный цикл сохраняемой угрозы включает эксфильтрация данных.</span><span class="sxs-lookup"><span data-stu-id="c5fca-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="c5fca-111">При инциденте с безопасностью важно иметь возможность приоритизировать расследования, в которых конфиденциальные файлы могут быть под угрозой, чтобы корпоративные данные и сведения были защищены.</span><span class="sxs-lookup"><span data-stu-id="c5fca-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="c5fca-112">Defender for Endpoint позволяет значительно упростить приоритеты инцидентов безопасности с помощью меток конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="c5fca-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="c5fca-113">Метки конфиденциальности быстро выявляют инциденты, которые могут включать устройства с конфиденциальной информацией, например конфиденциальной информацией.</span><span class="sxs-lookup"><span data-stu-id="c5fca-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="c5fca-114">Расследование инцидентов с конфиденциальными данными</span><span class="sxs-lookup"><span data-stu-id="c5fca-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="c5fca-115">Узнайте, как использовать метки конфиденциальности данных для приоритетов расследования инцидентов.</span><span class="sxs-lookup"><span data-stu-id="c5fca-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="c5fca-116">Метки обнаруживаются для Windows 10 версии 1809 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="c5fca-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="c5fca-117">В Центр безопасности в Microsoft Defender выберите **Инциденты**.</span><span class="sxs-lookup"><span data-stu-id="c5fca-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="c5fca-118">Прокрутите вправо, чтобы увидеть столбец **"Чувствительность к данным".**</span><span class="sxs-lookup"><span data-stu-id="c5fca-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="c5fca-119">В этом столбце отражены метки чувствительности, которые были замечены на устройствах, связанных с инцидентами, что указывает на то, может ли инцидент повлиять на конфиденциальные файлы.</span><span class="sxs-lookup"><span data-stu-id="c5fca-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![Изображение столбца чувствительности к данным](images/data-sensitivity-column.png)

    <span data-ttu-id="c5fca-121">Можно также фильтровать на основе **чувствительности к данным**</span><span class="sxs-lookup"><span data-stu-id="c5fca-121">You can also filter based on **Data sensitivity**</span></span> 

    ![Изображение фильтра чувствительности к данным](images/data-sensitivity-filter.png)

3. <span data-ttu-id="c5fca-123">Откройте страницу инцидента для дальнейшего расследования.</span><span class="sxs-lookup"><span data-stu-id="c5fca-123">Open the incident page to further investigate.</span></span>

    ![Изображение сведений о странице инцидента](images/incident-page.png)

4. <span data-ttu-id="c5fca-125">Выберите **вкладку Devices,** чтобы определить устройства, хранимые файлы с метками конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="c5fca-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![Изображение вкладки устройства](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="c5fca-127">Выберите устройства, на которых хранятся конфиденциальные данные и которые будут искать в временной шкале, чтобы определить, какие файлы могут повлиять, затем примите соответствующие меры для обеспечения защиты данных.</span><span class="sxs-lookup"><span data-stu-id="c5fca-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="c5fca-128">Вы можете сузить события, показанные на временной шкале устройства, ища метки чувствительности к данным.</span><span class="sxs-lookup"><span data-stu-id="c5fca-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="c5fca-129">При этом будут показываться только события, связанные с файлами с именем метки.</span><span class="sxs-lookup"><span data-stu-id="c5fca-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![Изображение временной шкалы устройства с суженными результатами поиска на основе метки](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="c5fca-131">Эти точки данных также выявляются с помощью "DeviceFileEvents" в продвинутой охоте, что позволяет расширенным запросам и обнаружению расписания учитывать метки чувствительности и состояние защиты файлов.</span><span class="sxs-lookup"><span data-stu-id="c5fca-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
