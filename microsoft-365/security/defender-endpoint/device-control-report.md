---
title: Защита данных организации с помощью управления устройствами
description: Отслеживайте безопасность данных организации с помощью отчетов по контролю за устройствами.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 47eb80af58c948db5997dc9f5edfa5737a796837
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772369"
---
# <a name="protect-your-organizations-data-with-device-control"></a><span data-ttu-id="d8ba9-103">Защита данных организации с помощью управления устройствами</span><span class="sxs-lookup"><span data-stu-id="d8ba9-103">Protect your organization’s data with device control</span></span>

<span data-ttu-id="d8ba9-104">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="d8ba9-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="d8ba9-105">Управление устройствами Microsoft Defender для конечных точек защищает от потери данных, отслеживая и контролируя использование мультимедиа устройствами в организации, такими как использование съемных устройств хранения и USB-дисков.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-105">Microsoft Defender for Endpoint device control protects against data loss, by monitoring and controlling media use by devices in your organization, such as the use of removable storage devices and USB drives.</span></span>

<span data-ttu-id="d8ba9-106">В отчете управления устройством можно просматривать события, которые связаны с использованием мультимедиа, например:</span><span class="sxs-lookup"><span data-stu-id="d8ba9-106">With the device control report, you can view events that relate to media usage, such as:</span></span>

- <span data-ttu-id="d8ba9-107">**События аудита:** Показывает количество событий аудита, которые происходят при подключении внешних мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-107">**Audit events:** Shows the number of audit events that occur when external media is connected.</span></span>
- <span data-ttu-id="d8ba9-108">**События политики:** Показывает количество событий политики, которые происходят при запуске политики управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-108">**Policy events:** Shows the number of policy events that occur when a device control policy is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="d8ba9-109">Событие аудита для отслеживания использования мультимедиа включено по умолчанию для устройств, включенных в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-109">The audit event to track media usage is enabled by default for devices onboarded to Microsoft Defender for Endpoint.</span></span>

## <a name="understanding-the-audit-events"></a><span data-ttu-id="d8ba9-110">Понимание событий аудита</span><span class="sxs-lookup"><span data-stu-id="d8ba9-110">Understanding the audit events</span></span>

<span data-ttu-id="d8ba9-111">События аудита включают:</span><span class="sxs-lookup"><span data-stu-id="d8ba9-111">The audit events include:</span></span>

- <span data-ttu-id="d8ba9-112">**Установка usb-накопителей и их неподъемная установка:** События аудита, которые создаются при смонтировании или неподъемном usb-накопителе.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-112">**USB drive mount and unmount:** Audit events that are generated when a USB drive is mounted or unmounted.</span></span>
- <span data-ttu-id="d8ba9-113">**PnP:** События аудита plug и Play создаются при подключении съемного хранилища, принтера или Bluetooth мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span></span>

## <a name="monitor-device-control-security"></a><span data-ttu-id="d8ba9-114">Мониторинг безопасности управления устройствами</span><span class="sxs-lookup"><span data-stu-id="d8ba9-114">Monitor device control security</span></span>

<span data-ttu-id="d8ba9-115">Управление устройствами в Microsoft Defender для конечной точки предоставляет администраторам безопасности средства, позволяющие отслеживать безопасность управления устройствами своей организации с помощью отчетов.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-115">Device control in Microsoft Defender for Endpoint empowers security administrators with tools that enable them to track their organization’s device control security through reports.</span></span> <span data-ttu-id="d8ba9-116">Отчет об устройстве можно найти в центре безопасности Microsoft 365, перейдите к отчету > **устройств.**</span><span class="sxs-lookup"><span data-stu-id="d8ba9-116">You can find the device control report in the Microsoft 365 security center by going to **Reports > Device protection**.</span></span>

<span data-ttu-id="d8ba9-117">Карта защиты устройств на панели **мониторинга Отчеты** показывает количество событий аудита, созданных типом мультимедиа, за последние 180 дней.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-117">The Device protection card on the **Reports** dashboard shows the number of audit events generated by media type, over the last 180 days.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8ba9-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span><span class="sxs-lookup"><span data-stu-id="d8ba9-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span></span>

<span data-ttu-id="d8ba9-119">Кнопка **"Просмотр сведений"** отображает больше данных об использовании мультимедиа на странице **отчета об устройстве.**</span><span class="sxs-lookup"><span data-stu-id="d8ba9-119">The **View details** button shows more media usage data in the **device control report** page.</span></span>

<span data-ttu-id="d8ba9-120">На странице предоставляется панель мониторинга с совокупным числом событий на один тип и списком событий.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-120">The page provides a dashboard with aggregated number of events per type and a list of events.</span></span> <span data-ttu-id="d8ba9-121">Администраторы могут фильтровать диапазон времени, имя класса мультимедиа и ID устройства.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-121">Administrators can filter on time range, media class name, and device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8ba9-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span><span class="sxs-lookup"><span data-stu-id="d8ba9-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span></span>

<span data-ttu-id="d8ba9-123">При выборе события появляется вылет, который показывает дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="d8ba9-123">When you select an event, a flyout appears that shows you more information:</span></span>

- <span data-ttu-id="d8ba9-124">**Общие сведения:** Дата, режим действия и политика этого события.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-124">**General details:** Date, Action mode, and the policy of this event.</span></span>
- <span data-ttu-id="d8ba9-125">**Сведения о средствах массовой информации:** Сведения о средствах массовой информации включают имя мультимедиа, имя класса, GUID класса, ID устройства, ID поставщика, том, серийный номер и тип автобуса.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-125">**Media information:** Media information includes Media name, Class name, Class GUID, Device ID, Vendor ID, Volume, Serial number, and Bus type.</span></span>
- <span data-ttu-id="d8ba9-126">**Сведения о расположении:** Имя устройства и MDATP устройства.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-126">**Location details:** Device name and MDATP device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8ba9-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span><span class="sxs-lookup"><span data-stu-id="d8ba9-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span></span>

<span data-ttu-id="d8ba9-128">Чтобы увидеть действия в режиме реального времени для этого средства массовой информации в организации, выберите кнопку **Open Advanced hunting.**</span><span class="sxs-lookup"><span data-stu-id="d8ba9-128">To see real-time activity for this media across the organization, select the **Open Advanced hunting** button.</span></span> <span data-ttu-id="d8ba9-129">Это включает встроенный заранее определенный запрос.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-129">This includes an embedded, pre-defined query.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8ba9-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span><span class="sxs-lookup"><span data-stu-id="d8ba9-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span></span>

<span data-ttu-id="d8ba9-131">Чтобы увидеть безопасность устройства, выберите кнопку **Открыть** страницу устройства на вылете.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-131">To see the security of the device, select the **Open device page** button on the flyout.</span></span> <span data-ttu-id="d8ba9-132">Эта кнопка открывает страницу сущности устройства.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-132">This button opens the device entity page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8ba9-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span><span class="sxs-lookup"><span data-stu-id="d8ba9-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span></span>

## <a name="reporting-delays"></a><span data-ttu-id="d8ba9-134">Задержки с отчетностью</span><span class="sxs-lookup"><span data-stu-id="d8ba9-134">Reporting delays</span></span>

<span data-ttu-id="d8ba9-135">Отчет управления устройством может иметь 12-часовую задержку со времени подключения мультимедиа к моменту отражения события в карте или в списке домена.</span><span class="sxs-lookup"><span data-stu-id="d8ba9-135">The device control report can have a 12-hour delay from the time a media connection occurs to the time the event is reflected in the card or in the domain list.</span></span>
