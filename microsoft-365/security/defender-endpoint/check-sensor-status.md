---
title: Проверка состояния состояния датчика в Microsoft Defender для конечной точки
description: Проверьте состояние датчика на устройствах, чтобы определить, какие из них неправильно сконфигурировали, неактивны или не сообщают данные датчика.
keywords: датчик, состояние датчика, неправильное, неактивное, отсутствие данных датчиков, данных датчиков, нарушенная связь, связь
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904168"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="e2ff7-104">Проверка состояния состояния датчика в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e2ff7-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2ff7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e2ff7-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2ff7-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e2ff7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e2ff7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2ff7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e2ff7-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e2ff7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e2ff7-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="e2ff7-110">Плитка **Устройств с проблемными датчиками** находится на панели мониторинга операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="e2ff7-111">На этой плитке содержатся сведения о способности отдельного устройства предоставлять данные датчиков и обмениваться информаций со службой Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="e2ff7-112">На этой плитке указано, скольким устройствам требуется внимание. Вы можете удобно выявлять проблемные устройства и принимать меры для устранения известных проблем.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="e2ff7-113">На плитке есть два индикатора состояния, которые предоставляют сведения о количестве устройств, которые не сообщают службе должным образом:</span><span class="sxs-lookup"><span data-stu-id="e2ff7-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="e2ff7-114">**Неправильно сконфигурация** . Эти устройства могут частично сообщать данные датчика службе Defender для конечной точки и могут иметь ошибки конфигурации, которые необходимо исправить.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="e2ff7-115">**Неактивные** устройства, которые перестали сообщать в службу Защитник для конечных точек более семи дней в прошлом месяце.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="e2ff7-116">Щелкнув любую из групп, вы направите в **список Устройств,** фильтрующийся по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![Снимок экрана устройств с плиткой проблем с датчиками](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="e2ff7-118">В **списке Устройств** можно фильтровать список состояния здоровья по следующему состоянию:</span><span class="sxs-lookup"><span data-stu-id="e2ff7-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="e2ff7-119">**Active** — устройства, активно отчитываватся в службе Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="e2ff7-120">**Неправильно сконфигурация** . Эти устройства могут частично сообщать данные датчиков службе Defender для конечной точки, но имеют ошибки конфигурации, которые необходимо исправить.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="e2ff7-121">На устройствах с неверной конфигурацией могут быть следующие проблемы (как по отдельности, так и вместе):</span><span class="sxs-lookup"><span data-stu-id="e2ff7-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="e2ff7-122">**Нет данных датчика** . Устройства перестали отправлять данные датчиков.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="e2ff7-123">С устройства можно инициировать ограниченный набор оповещений.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="e2ff7-124">**Нарушение связи** . Способность к общению с устройством нарушается.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="e2ff7-125">При этом могут не работать такие функции как отправка файлов для подробного анализа, блокирование файлов, изоляция устройства от сети, а также другие действия, для которых требуется обмен информацией с устройством.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="e2ff7-126">**Неактивные** устройства, которые перестали сообщать об этом службе Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="e2ff7-127">Вы также можете скачать весь список в формате CSV с помощью **функции Экспорт.**</span><span class="sxs-lookup"><span data-stu-id="e2ff7-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="e2ff7-128">Дополнительные сведения о фильтрах см. в [обзоре и организации списка Устройств.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e2ff7-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="e2ff7-129">Экспорт списка в формате CSV для отображения неотобраченных данных.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="e2ff7-130">CSV-файл будет включать все устройства в организации, независимо от любой фильтрации, применяемой в самом представлении, и может занять значительное время для скачивания в зависимости от размера организации.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![Снимок экрана страницы списка Устройств](images/atp-devices-list-page.png)

<span data-ttu-id="e2ff7-132">Сведения об устройстве можно просматривать при нажатии на неправильное или неактивное устройство.</span><span class="sxs-lookup"><span data-stu-id="e2ff7-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="e2ff7-133">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="e2ff7-133">Related topic</span></span>
- [<span data-ttu-id="e2ff7-134">Исправление нездоровых датчиков в Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e2ff7-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
