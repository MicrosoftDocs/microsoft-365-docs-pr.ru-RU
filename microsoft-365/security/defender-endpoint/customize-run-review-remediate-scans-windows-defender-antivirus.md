---
title: Запуск и настройка запланированных и по запросу сканов
description: Настройка и инициирование антивирусных сканов Microsoft Defender в конечных точках сети.
keywords: сканирование, расписание, настройка, исключения, исключение файлов, исправление, результаты проверки, карантин, удаление угрозы, быстрое сканирование, полное сканирование, антивирус Microsoft Defender
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
ms.openlocfilehash: f3e0cc7ffccf02e24b9746d539a44d3a72810ead
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765675"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a>Настройка, инициирование и проверка результатов проверки антивируса Microsoft Defender & исправлений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Для настройки антивирусных сканов Microsoft Defender можно использовать инструменты групповой политики, PowerShell и Windows Management Instrumentation (WMI). 

## <a name="in-this-section"></a>Содержание

| Статья | Описание |
|:---|:---|
|[Настройка и проверка исключений файлов, папок и открытых процессом файлов в антивирусных проверках Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md) | Можно исключить файлы (в том числе файлы, измененные заданными процессами) и папки из проверки по запросу, планового сканирования и мониторинга и сканирования защиты в режиме реального времени |
|[Настройка параметров сканирования антивирусной программы в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Можно настроить антивирус Microsoft Defender, чтобы включить в сканирование определенные типы файлов хранения электронной почты, точек архивирования или репара и архивных файлов (например, файлов zip). Вы также можете включить сканирование сетевых файлов |
|[Настройка исправлений для сканирования](configure-remediation-microsoft-defender-antivirus.md) | Настройка того, что должен делать антивирус Microsoft Defender при обнаружении угрозы, и как долго должны храниться карантинные файлы в папке карантина |
|[Настройка запланированных сканов](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Настройка повторяющихся (запланированных) сканирований, в том числе при их запуске и в качестве полного или быстрого сканирования. |
|[Настройка и запуск сканирования](run-scan-microsoft-defender-antivirus.md) | Запуск и настройка сканирования по запросу с помощью PowerShell, инструментов управления Windows или отдельно на конечных точках с помощью приложения Безопасности Windows |
|[Просмотр результатов сканирования](review-scan-results-microsoft-defender-antivirus.md) | Просмотрите результаты сканирования с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или приложения безопасности Windows |