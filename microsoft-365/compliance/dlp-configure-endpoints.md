---
title: Средства и методы подключения для устройств с Windows 10
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
description: На Windows 10 устройствах, чтобы они могли отправлять данные датчиков в решения Microsoft 365 соответствия требованиям.
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917855"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="be9f8-103">Средства и методы подключения для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="be9f8-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="be9f8-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="be9f8-104">**Applies to:**</span></span>
- [<span data-ttu-id="be9f8-105">Microsoft 365 Предотвращение потери конечных данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="be9f8-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="be9f8-106">Устройства в организации должны быть настроены таким образом, чтобы Microsoft 365 служба предотвращения потери данных конечной точки может получать от них данные датчиков.</span><span class="sxs-lookup"><span data-stu-id="be9f8-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="be9f8-107">Существуют различные методы и средства развертывания, которые можно использовать для настройки устройств в организации.</span><span class="sxs-lookup"><span data-stu-id="be9f8-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="be9f8-108">Поддерживаются следующие средства и методы развертывания:</span><span class="sxs-lookup"><span data-stu-id="be9f8-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="be9f8-109">групповой политики</span><span class="sxs-lookup"><span data-stu-id="be9f8-109">group policy</span></span>
- <span data-ttu-id="be9f8-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="be9f8-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="be9f8-111">Управление мобильными устройствами (включая Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="be9f8-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="be9f8-112">локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="be9f8-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="be9f8-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="be9f8-113">In this section</span></span>
<span data-ttu-id="be9f8-114">Статья</span><span class="sxs-lookup"><span data-stu-id="be9f8-114">Topic</span></span> | <span data-ttu-id="be9f8-115">Описание</span><span class="sxs-lookup"><span data-stu-id="be9f8-115">Description</span></span>
:---|:---
[<span data-ttu-id="be9f8-116">Onboard Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="be9f8-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="be9f8-117">Используйте групповую политику для развертывания пакета конфигурации на устройствах.</span><span class="sxs-lookup"><span data-stu-id="be9f8-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="be9f8-118">На борту Windows устройства с Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="be9f8-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="be9f8-119">Для развертывания пакета конфигурации на устройствах можно использовать версию Microsoft Endpoint Configuration Manager (текущая ветвь) версии 1606 или Microsoft Endpoint Configuration Manager версии 1602 (текущая ветвь).</span><span class="sxs-lookup"><span data-stu-id="be9f8-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="be9f8-120">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="be9f8-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="be9f8-121">Используйте средства управления мобильными устройствами или Microsoft Intune для развертывания пакета конфигурации на устройстве.</span><span class="sxs-lookup"><span data-stu-id="be9f8-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="be9f8-122">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="be9f8-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="be9f8-123">Узнайте, как использовать локальный скрипт для развертывания пакета конфигурации на конечных точках.</span><span class="sxs-lookup"><span data-stu-id="be9f8-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="be9f8-124">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="be9f8-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="be9f8-125">Узнайте, как использовать пакет конфигурации для настройки устройств VDI.</span><span class="sxs-lookup"><span data-stu-id="be9f8-125">Learn how to use the configuration package to configure VDI devices.</span></span>