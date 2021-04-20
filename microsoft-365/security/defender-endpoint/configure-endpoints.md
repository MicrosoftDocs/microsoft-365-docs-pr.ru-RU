---
title: Средства и методы подключения для устройств с Windows 10
description: Onboard Windows 10 devices so that they can send sensor data to the Microsoft Defender for Endpoint sensor
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
ms.openlocfilehash: f1ef2670a1ca749e0a2f1ebc96300d4eca043bf8
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892833"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="21a42-104">Средства и методы подключения для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="21a42-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="21a42-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="21a42-105">**Applies to:**</span></span>
- [<span data-ttu-id="21a42-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="21a42-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="21a42-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21a42-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="21a42-108">Предотвращение потери данных конечной точки Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="21a42-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="21a42-109">Управление рисками для инсайдеров Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="21a42-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="21a42-110">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="21a42-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="21a42-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="21a42-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="21a42-112">Устройства в организации должны быть настроены таким образом, чтобы служба Defender для конечных точек может получать от них данные датчиков.</span><span class="sxs-lookup"><span data-stu-id="21a42-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="21a42-113">Существуют различные методы и средства развертывания, которые можно использовать для настройки устройств в организации.</span><span class="sxs-lookup"><span data-stu-id="21a42-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="21a42-114">Поддерживаются следующие средства и методы развертывания:</span><span class="sxs-lookup"><span data-stu-id="21a42-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="21a42-115">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="21a42-115">Group Policy</span></span>
- <span data-ttu-id="21a42-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="21a42-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="21a42-117">Управление мобильными устройствами (включая Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="21a42-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="21a42-118">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="21a42-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="21a42-119">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="21a42-119">In this section</span></span>
<span data-ttu-id="21a42-120">Статья</span><span class="sxs-lookup"><span data-stu-id="21a42-120">Topic</span></span> | <span data-ttu-id="21a42-121">Описание</span><span class="sxs-lookup"><span data-stu-id="21a42-121">Description</span></span>
:---|:---
[<span data-ttu-id="21a42-122">На борту устройств Windows 10 с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="21a42-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="21a42-123">Используйте групповую политику для развертывания пакета конфигурации на устройствах.</span><span class="sxs-lookup"><span data-stu-id="21a42-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="21a42-124">На борту устройств Windows с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="21a42-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="21a42-125">Для развертывания пакета конфигурации на устройствах можно использовать версию 1606 Microsoft Endpoint Manager (текущая ветвь) или Microsoft Endpoint Manager (текущая ветвь).</span><span class="sxs-lookup"><span data-stu-id="21a42-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="21a42-126">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="21a42-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="21a42-127">Используйте средства управления мобильными устройствами или Microsoft Intune для развертывания пакета конфигурации на устройстве.</span><span class="sxs-lookup"><span data-stu-id="21a42-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="21a42-128">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="21a42-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="21a42-129">Узнайте, как использовать локальный скрипт для развертывания пакета конфигурации на конечных точках.</span><span class="sxs-lookup"><span data-stu-id="21a42-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="21a42-130">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="21a42-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="21a42-131">Узнайте, как использовать пакет конфигурации для настройки устройств VDI.</span><span class="sxs-lookup"><span data-stu-id="21a42-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="21a42-132">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="21a42-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="21a42-133">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="21a42-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
