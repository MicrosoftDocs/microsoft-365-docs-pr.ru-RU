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
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a>Средства и методы входящей миграции для устройств с Windows 10 (Предварительная версия)

**Область применения:**
- [Защита от потери данных (DLP) Microsoft 365 Endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about)

Устройства в Организации должны быть настроены таким образом, чтобы служба защиты от потери данных (Microsoft 365 Endpoint) могла получать от них данные датчиков. Существуют различные методы и средства развертывания, которые можно использовать для настройки устройств в Организации.

Поддерживаются следующие средства и методы развертывания:

- Групповая политика
- Microsoft Endpoint Configuration Manager
- Управление мобильными устройствами (включая Microsoft Intune)
- локальный скрипт

## <a name="in-this-section"></a>В этом разделе
Статья | Описание
:---|:---
[Встроенные устройства с Windows 10 с помощью групповой политики](dlp-configure-endpoints-gp.md) | Используйте групповую политику для развертывания пакета конфигурации на устройствах.
[Встроенные устройства с Windows с помощью диспетчера конфигураций конечных точек Майкрософт](dlp-configure-endpoints-sccm.md) | Для развертывания пакета конфигурации на устройствах можно использовать Microsoft Endpoint Configuration Manager (Текущая ветвь) версии 1606 или Microsoft Endpoint Configuration Manager (Текущая ветвь) версии 1602 или более ранней версии.
[Встроенные устройства с Windows 10 с помощью средств управления мобильными устройствами](dlp-configure-endpoints-mdm.md) | Используйте средства управления мобильными устройствами или Microsoft Intune, чтобы развернуть пакет конфигурации на устройстве.
[Встроенные устройства с Windows 10 с помощью локального сценария](dlp-configure-endpoints-script.md) | Узнайте, как использовать локальный скрипт для развертывания пакета конфигурации в конечных точках.
[Встроенные устройства неустойчивой инфраструктуры виртуальных рабочих столов (VDI)](dlp-configure-endpoints-vdi.md) | Узнайте, как использовать пакет конфигурации для настройки устройств VDI.
