---
title: Offboard devices from the Microsoft Defender for Endpoint service
description: Onboard Windows 10, servers, non-Windows устройств из службы Microsoft Defender для конечных точек
keywords: offboarding, Microsoft Defender for Endpoint offboarding, offboarding
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
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934157"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Offboard devices from the Microsoft Defender for Endpoint service

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Платформы**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Следуйте соответствующим инструкциям в зависимости от предпочтительного метода развертывания.

>[!NOTE]
> Состояние устройства будет переключаться на [Неактивный](fix-unhealthy-sensors.md#inactive-devices) через 7 дней после отключения. <br> Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires. <br>
> Профиль устройства (без данных) будет оставаться в списке [устройств](machines-view-overview.md) не более 180 дней.
> Кроме того, устройства, не активные в течение последних 30 дней, не будут учитываться [](tvm-exposure-score.md) в данных, отражающих оценку контроль угроз и уязвимостей и microsoft Secure Score для устройств. <br>
> Чтобы просмотреть только активные устройства, можно фильтровать по состоянию [здоровья,](machines-view-overview.md#health-state) [тегам устройств или](machine-tags.md) [группам машин.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Устройства offboard Windows 10
- [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Offboard devices using Group Policy](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Offboard devices using Mobile Device Management tools](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Offboard Servers
- [Offboard servers](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Offboard non-Windows устройств
- [Offboard non-Windows устройств](configure-endpoints-non-windows.md#offboard-non-windows-devices)

