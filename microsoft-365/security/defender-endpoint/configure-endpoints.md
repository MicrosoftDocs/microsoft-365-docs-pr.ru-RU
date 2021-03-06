---
title: Средства и методы подключения для устройств с Windows 10
description: На Windows 10 устройствах, чтобы они могли отправлять данные датчика в датчик Microsoft Defender для конечной точки
keywords: Onboard Windows 10, групповой политики, диспетчер конфигурации конечной точки, управление мобильными устройствами, локальный скрипт, GP, sccm, mdm, intune
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
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Средства и методы подключения для устройств с Windows 10

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365 Предотвращение потери конечных данных (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365 Управление рисками изнутри](/microsoft-365/compliance/insider-risk-management)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Устройства в организации должны быть настроены таким образом, чтобы служба Defender для конечных точек может получать от них данные датчиков. Существуют различные методы и средства развертывания, которые можно использовать для настройки устройств в организации.

Поддерживаются следующие средства и методы развертывания:

- Групповая политика
- Microsoft Endpoint Configuration Manager
- Управление мобильными устройствами (включая Microsoft Intune)
- Локальный скрипт

## <a name="in-this-section"></a>В этом разделе
Статья | Описание
:---|:---
[Onboard Windows 10 с помощью групповой политики](configure-endpoints-gp.md) | Используйте групповую политику для развертывания пакета конфигурации на устройствах.
[На борту Windows устройства с Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) | Для развертывания пакета конфигурации на устройствах можно использовать версию Microsoft Endpoint Manager версии 1606 или Microsoft Endpoint Manager версии 1602 (текущая ветвь).
[Подключение устройств Windows 10 с помощью средств управления мобильными устройствами](configure-endpoints-mdm.md) | Используйте средства управления мобильными устройствами или Microsoft Intune для развертывания пакета конфигурации на устройстве.
[Подключение устройств Windows 10 с помощью локального сценария](configure-endpoints-script.md) | Узнайте, как использовать локальный скрипт для развертывания пакета конфигурации на конечных точках.
[Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)](configure-endpoints-vdi.md) | Узнайте, как использовать пакет конфигурации для настройки устройств VDI.


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
