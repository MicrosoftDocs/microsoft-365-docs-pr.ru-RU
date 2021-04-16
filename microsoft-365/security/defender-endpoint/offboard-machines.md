---
title: Offboard devices from the Microsoft Defender for Endpoint service
description: Onboard Windows 10 devices, servers, non-Windows devices from the Microsoft Defender for Endpoint service
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
ms.openlocfilehash: 18c708904e0fbfceafa2aeb387ffa9ce26e83c87
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861135"
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
> Кроме того, устройства, не активные в течение последних 30 дней, не будут учитываться в [](tvm-exposure-score.md) данных, отражающих оценку воздействия на угрозы и уязвимости организации и оценку microsoft Secure Score для устройств. <br>
> Чтобы просмотреть только активные устройства, можно фильтровать по состоянию [здоровья,](machines-view-overview.md#health-state) [тегам устройств или](machine-tags.md) [группам машин.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Устройства Offboard Windows 10
- [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Offboard devices using Group Policy](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Offboard devices using Mobile Device Management tools](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Offboard Servers
- [Offboard servers](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Offboard non-Windows devices
- [Offboard non-Windows devices](configure-endpoints-non-windows.md#offboard-non-windows-devices)

