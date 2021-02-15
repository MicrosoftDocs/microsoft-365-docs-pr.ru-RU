---
title: Средства и методы для устройств с Windows 10 (предварительная версия)
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
description: Вметь устройства с Windows 10, чтобы они могли отправлять данные датчиков в решения по обеспечению соответствия требованиям Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769646"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a>Средства и методы для устройств с Windows 10 (предварительная версия)

**Область применения:**
- [Предотвращение потери данных конечной точки Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

Устройства в вашей организации должны быть настроены таким образом, чтобы служба защиты от потери данных конечной точки Microsoft 365 может получать от них данные датчиков. Существуют различные методы и средства развертывания, которые можно использовать для настройки устройств в организации.

Поддерживаются следующие средства и методы развертывания:

- групповая политика
- Microsoft Endpoint Configuration Manager
- Управление мобильными устройствами (включая Microsoft Intune)
- локальный сценарий

## <a name="in-this-section"></a>В этом разделе
Статья | Описание
:---|:---
[Ветвь устройств с Windows 10 с помощью групповой политики](dlp-configure-endpoints-gp.md) | Используйте групповую политику для развертывания пакета конфигурации на устройствах.
[Ветвь устройств с Windows с помощью Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Для развертывания пакета конфигурации на устройствах можно использовать Microsoft Endpoint Configuration Manager (current branch) версии 1606 или Microsoft Endpoint Configuration Manager (current branch) версии 1602 или более ранней версии.
[Подключение устройств Windows 10 с помощью средств управления мобильными устройствами](dlp-configure-endpoints-mdm.md) | Используйте средства управления мобильными устройствами или Microsoft Intune для развертывания пакета конфигурации на устройстве.
[Подключение устройств Windows 10 с помощью локального сценария](dlp-configure-endpoints-script.md) | Узнайте, как использовать локальный сценарий для развертывания пакета конфигурации на конечных точках.
[Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)](dlp-configure-endpoints-vdi.md) | Узнайте, как использовать пакет конфигурации для настройки устройств VDI.
