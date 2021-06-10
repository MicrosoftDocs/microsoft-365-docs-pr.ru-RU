---
title: Аппаратная изоляция (Windows 10)
ms.reviewer: ''
description: Узнайте, как аппаратная изоляция в Windows 10 помогает бороться с вредоносными программами.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b3babf858ac19e70119a2dc6a58b25359f1b05c1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842990"
---
# <a name="hardware-based-isolation-in-windows-10"></a>Аппаратная изоляция в Windows 10

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Аппаратная изоляция помогает защитить целостность системы в Windows 10 и интегрирована с Microsoft Defender для конечной точки. 

| Возможность | Описание |
|------------|-------------|
| [Application Guard в Защитнике Windows](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | Application Guard защищает устройство от расширенных атак, сохраняя производительность. С помощью уникального аппаратного подхода к изоляции цель состоит в том, чтобы изолировать ненадеженные веб-сайты и документы PDF в легком контейнере, отделенном от операционной системы через родной Windows Hypervisor. Если ненастоячивый сайт или pdf-документ окажется вредоносным, он по-прежнему остается в защищенном контейнере Application Guard, сохраняя защиту настольного компьютера и злоумышленника от корпоративных данных. |
| [Защитник Windows System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | System Guard защищает и поддерживает целостность системы при запуске и после ее запуска, а также проверяет целостность системы с помощью проверки.  |

