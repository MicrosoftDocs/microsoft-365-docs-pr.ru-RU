---
title: Средства и методы подключения для устройств с Windows 10
description: Onboard Windows 10 devices so that they can send sensor data to the Microsoft Defender ATP sensor
keywords: Onboard Windows 10 devices, group policy, endpoint configuration manager, mobile device management, local script, GP, sccm, mdm, intune
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
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165541"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="70de8-104">Средства и методы подключения для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="70de8-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="70de8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="70de8-105">**Applies to:**</span></span>
- [<span data-ttu-id="70de8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="70de8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="70de8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70de8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="70de8-108">Предотвращение потери данных конечной точки Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="70de8-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="70de8-109">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="70de8-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="70de8-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="70de8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="70de8-111">Устройства в организации должны быть настроены таким образом, чтобы служба Defender для конечных точек может получать от них данные датчиков.</span><span class="sxs-lookup"><span data-stu-id="70de8-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="70de8-112">Существуют различные методы и средства развертывания, которые можно использовать для настройки устройств в организации.</span><span class="sxs-lookup"><span data-stu-id="70de8-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="70de8-113">Поддерживаются следующие средства и методы развертывания:</span><span class="sxs-lookup"><span data-stu-id="70de8-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="70de8-114">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="70de8-114">Group Policy</span></span>
- <span data-ttu-id="70de8-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="70de8-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="70de8-116">Управление мобильными устройствами (включая Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="70de8-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="70de8-117">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="70de8-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="70de8-118">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="70de8-118">In this section</span></span>
<span data-ttu-id="70de8-119">Статья</span><span class="sxs-lookup"><span data-stu-id="70de8-119">Topic</span></span> | <span data-ttu-id="70de8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="70de8-120">Description</span></span>
:---|:---
[<span data-ttu-id="70de8-121">На борту устройств Windows 10 с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="70de8-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="70de8-122">Используйте групповую политику для развертывания пакета конфигурации на устройствах.</span><span class="sxs-lookup"><span data-stu-id="70de8-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="70de8-123">На борту устройств Windows с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="70de8-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="70de8-124">Для развертывания пакета конфигурации на устройствах можно использовать версию 1606 Microsoft Endpoint Manager (текущая ветвь) или Microsoft Endpoint Manager (текущая ветвь).</span><span class="sxs-lookup"><span data-stu-id="70de8-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="70de8-125">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="70de8-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="70de8-126">Используйте средства управления мобильными устройствами или Microsoft Intune для развертывания пакета конфигурации на устройстве.</span><span class="sxs-lookup"><span data-stu-id="70de8-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="70de8-127">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="70de8-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="70de8-128">Узнайте, как использовать локальный скрипт для развертывания пакета конфигурации на конечных точках.</span><span class="sxs-lookup"><span data-stu-id="70de8-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="70de8-129">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="70de8-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="70de8-130">Узнайте, как использовать пакет конфигурации для настройки устройств VDI.</span><span class="sxs-lookup"><span data-stu-id="70de8-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="70de8-131">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="70de8-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="70de8-132">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="70de8-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
