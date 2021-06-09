---
title: Настройка антивирусная программа в Microsoft Defender с WMI
description: Узнайте, как настроить и управлять антивирусная программа в Microsoft Defender с помощью скриптов WMI для получения, изменения и обновления параметров в Microsoft Defender для конечной точки.
keywords: wmi, скрипты, инструменты управления Windows, конфигурация
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764067"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Использование Windows инструментов управления (WMI) для настройки и управления антивирусная программа в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Windows Инструментарий управления (WMI) — это интерфейс скриптов, который позволяет извлекать, изменять и обновлять параметры.

Узнайте больше о WMI в [библиотеке Microsoft Developer Network администрирования системы](/windows/win32/wmisdk/wmi-start-page).

антивирусная программа в Microsoft Defender имеет ряд определенных классов WMI, которые можно использовать для выполнения большинства тех же функций, что и групповые политики и другие средства управления. Многие классы аналогичны [cmdlets Defender PowerShell.](use-powershell-cmdlets-microsoft-defender-antivirus.md)

Справочная [библиотека поставщиков msDN Защитник Windows WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) перечисляет доступные классы WMI для антивирусная программа в Microsoft Defender и включает примеры сценариев.

Изменения, внесенные в WMI, повлияют на локальные параметры конечной точки, где эти изменения развернуты или внесены. Это означает, что развертывание политики с помощью групповой политики, Microsoft Endpoint Configuration Manager или Microsoft Intune может переписать изменения, внесенные с помощью WMI. 

Можно настроить параметры, которые можно переопределять локально, с помощью [переопределеемых локальных политик.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Статьи по теме

- [Справочные темы для средств управления и конфигурации](configuration-management-reference-microsoft-defender-antivirus.md)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)