---
title: Средства и методы входящей миграции для устройств с Windows 10 (Предварительная версия)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Встроенные устройства с Windows 10, позволяющие отправлять данные датчиков в решения для обеспечения соответствия требованиям Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769646"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="5db81-103">Средства и методы входящей миграции для устройств с Windows 10 (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5db81-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="5db81-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5db81-104">**Applies to:**</span></span>
- [<span data-ttu-id="5db81-105">Защита от потери данных (DLP) Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="5db81-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="5db81-106">Устройства в Организации должны быть настроены таким образом, чтобы служба защиты от потери данных (Microsoft 365 Endpoint) могла получать от них данные датчиков.</span><span class="sxs-lookup"><span data-stu-id="5db81-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="5db81-107">Существуют различные методы и средства развертывания, которые можно использовать для настройки устройств в Организации.</span><span class="sxs-lookup"><span data-stu-id="5db81-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="5db81-108">Поддерживаются следующие средства и методы развертывания:</span><span class="sxs-lookup"><span data-stu-id="5db81-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="5db81-109">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="5db81-109">group policy</span></span>
- <span data-ttu-id="5db81-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5db81-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="5db81-111">Управление мобильными устройствами (включая Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="5db81-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="5db81-112">локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="5db81-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5db81-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5db81-113">In this section</span></span>
<span data-ttu-id="5db81-114">Статья</span><span class="sxs-lookup"><span data-stu-id="5db81-114">Topic</span></span> | <span data-ttu-id="5db81-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5db81-115">Description</span></span>
:---|:---
[<span data-ttu-id="5db81-116">Встроенные устройства с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5db81-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="5db81-117">Используйте групповую политику для развертывания пакета конфигурации на устройствах.</span><span class="sxs-lookup"><span data-stu-id="5db81-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="5db81-118">Встроенные устройства с Windows с помощью диспетчера конфигураций конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5db81-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="5db81-119">Для развертывания пакета конфигурации на устройствах можно использовать Microsoft Endpoint Configuration Manager (Текущая ветвь) версии 1606 или Microsoft Endpoint Configuration Manager (Текущая ветвь) версии 1602 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="5db81-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="5db81-120">Встроенные устройства с Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="5db81-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="5db81-121">Используйте средства управления мобильными устройствами или Microsoft Intune, чтобы развернуть пакет конфигурации на устройстве.</span><span class="sxs-lookup"><span data-stu-id="5db81-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="5db81-122">Встроенные устройства с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="5db81-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="5db81-123">Узнайте, как использовать локальный скрипт для развертывания пакета конфигурации в конечных точках.</span><span class="sxs-lookup"><span data-stu-id="5db81-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="5db81-124">Встроенные устройства неустойчивой инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="5db81-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="5db81-125">Узнайте, как использовать пакет конфигурации для настройки устройств VDI.</span><span class="sxs-lookup"><span data-stu-id="5db81-125">Learn how to use the configuration package to configure VDI devices.</span></span>
