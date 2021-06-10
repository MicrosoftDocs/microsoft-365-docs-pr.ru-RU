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
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Средства и методы подключения для устройств с Windows 10

**Область применения:**
- [Microsoft 365 Предотвращение потери конечных данных (DLP)](./endpoint-dlp-learn-about.md)

Устройства в организации должны быть настроены таким образом, чтобы Microsoft 365 служба предотвращения потери данных конечной точки может получать от них данные датчиков. Существуют различные методы и средства развертывания, которые можно использовать для настройки устройств в организации.

Поддерживаются следующие средства и методы развертывания:

- групповой политики
- Microsoft Endpoint Configuration Manager
- Управление мобильными устройствами (включая Microsoft Intune)
- локальный скрипт

## <a name="in-this-section"></a>В этом разделе
Статья | Описание
:---|:---
[Onboard Windows 10 с помощью групповой политики](dlp-configure-endpoints-gp.md) | Используйте групповую политику для развертывания пакета конфигурации на устройствах.
[На борту Windows устройства с Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Для развертывания пакета конфигурации на устройствах можно использовать версию Microsoft Endpoint Configuration Manager (текущая ветвь) версии 1606 или Microsoft Endpoint Configuration Manager версии 1602 (текущая ветвь).
[Подключение устройств Windows 10 с помощью средств управления мобильными устройствами](dlp-configure-endpoints-mdm.md) | Используйте средства управления мобильными устройствами или Microsoft Intune для развертывания пакета конфигурации на устройстве.
[Подключение устройств Windows 10 с помощью локального сценария](dlp-configure-endpoints-script.md) | Узнайте, как использовать локальный скрипт для развертывания пакета конфигурации на конечных точках.
[Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)](dlp-configure-endpoints-vdi.md) | Узнайте, как использовать пакет конфигурации для настройки устройств VDI.