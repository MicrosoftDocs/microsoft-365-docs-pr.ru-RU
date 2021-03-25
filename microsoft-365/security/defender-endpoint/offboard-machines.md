---
title: Offboard devices from the Microsoft Defender ATP service
description: Onboard Windows 10 devices, servers, non-Windows devices from the Microsoft Defender ATP service
keywords: offboarding, microsoft defender for endpoint offboarding, windows atp offboarding
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a95ff5214ea9f696622ea184ece1c5aa9fb3db2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186969"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="02538-104">Offboard devices from the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="02538-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="02538-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="02538-105">**Applies to:**</span></span>
- [<span data-ttu-id="02538-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="02538-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="02538-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02538-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="02538-108">**Платформы**</span><span class="sxs-lookup"><span data-stu-id="02538-108">**Platforms**</span></span>
- <span data-ttu-id="02538-109">macOS</span><span class="sxs-lookup"><span data-stu-id="02538-109">macOS</span></span>
- <span data-ttu-id="02538-110">Linux</span><span class="sxs-lookup"><span data-stu-id="02538-110">Linux</span></span>
- <span data-ttu-id="02538-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="02538-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="02538-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="02538-112">Windows Server 2016</span></span>

><span data-ttu-id="02538-113">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="02538-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="02538-114">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="02538-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="02538-115">Следуйте соответствующим инструкциям в зависимости от предпочтительного метода развертывания.</span><span class="sxs-lookup"><span data-stu-id="02538-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="02538-116">Состояние устройства будет переключаться на [Неактивный](fix-unhealthy-sensors.md#inactive-devices) через 7 дней после отключения.</span><span class="sxs-lookup"><span data-stu-id="02538-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="02538-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span><span class="sxs-lookup"><span data-stu-id="02538-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="02538-118">Профиль устройства (без данных) будет оставаться в списке [устройств](machines-view-overview.md) не более 180 дней.</span><span class="sxs-lookup"><span data-stu-id="02538-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="02538-119">Кроме того, устройства, не активные в течение последних 30 дней, не будут учитываться в [](tvm-exposure-score.md) данных, отражающих оценку воздействия на угрозы и уязвимости организации и оценку microsoft Secure Score для устройств.</span><span class="sxs-lookup"><span data-stu-id="02538-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="02538-120">Чтобы просмотреть только активные устройства, можно фильтровать по состоянию [здоровья,](machines-view-overview.md#health-state) [тегам устройств или](machine-tags.md) [группам машин.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="02538-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="02538-121">Устройства Offboard Windows 10</span><span class="sxs-lookup"><span data-stu-id="02538-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="02538-122">Offboard devices using a local script</span><span class="sxs-lookup"><span data-stu-id="02538-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="02538-123">Offboard devices using Group Policy</span><span class="sxs-lookup"><span data-stu-id="02538-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="02538-124">Offboard devices using Mobile Device Management tools</span><span class="sxs-lookup"><span data-stu-id="02538-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="02538-125">Offboard Servers</span><span class="sxs-lookup"><span data-stu-id="02538-125">Offboard Servers</span></span>
- [<span data-ttu-id="02538-126">Offboard servers</span><span class="sxs-lookup"><span data-stu-id="02538-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="02538-127">Offboard non-Windows devices</span><span class="sxs-lookup"><span data-stu-id="02538-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="02538-128">Offboard non-Windows devices</span><span class="sxs-lookup"><span data-stu-id="02538-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

