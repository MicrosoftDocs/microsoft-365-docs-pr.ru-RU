---
title: Запуск и настройка запланированных и по запросу сканов
description: Настройка и инициа антивирусная программа в Microsoft Defender проверки на конечных точках в сети.
keywords: сканирование, расписание, настройка, исключения, исключение файлов, исправление, результаты проверки, карантин, удаление угрозы, быстрое сканирование, полное сканирование, антивирусная программа в Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 31dbfa2ac6d5537f6d42c0bad612be5ef059368d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275280"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Настройка, инициирование и проверка результатов антивирусная программа в Microsoft Defender и исправлений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Для настройки антивирусная программа в Microsoft Defender можно использовать групповые политики, powerShell и Windows средства управления (WMI). 

## <a name="in-this-section"></a>В этом разделе

Статья | Описание
---|---
[Настройка и проверка исключений файлов, папок и файлов, открытых процессом, в антивирусная программа в Microsoft Defender проверки](configure-exclusions-microsoft-defender-antivirus.md) | Можно исключить файлы (в том числе файлы, измененные заданными процессами) и папки из проверки по запросу, планового сканирования и мониторинга и сканирования защиты в режиме реального времени
[Настройка параметров сканирования антивирусной программы в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Вы можете настроить антивирусная программа в Microsoft Defender, чтобы включить в сканирование определенные типы файлов хранения электронной почты, точек архивирования или репаража, а также архивных файлов (например, .zip файлов). Вы также можете включить сканирование сетевых файлов
[Настройка исправлений для сканирования](configure-remediation-microsoft-defender-antivirus.md) | Настройка того, антивирусная программа в Microsoft Defender следует делать при обнаружении угрозы, и как долго должны храниться карантинные файлы в папке карантина
[Настройка запланированных сканов](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Настройка повторяющихся (запланированных) сканирований, в том числе при их запуске и в качестве полного или быстрого сканирования.
[Настройка и запуск сканирования](run-scan-microsoft-defender-antivirus.md) | Запуск и настройка сканирования по запросу с помощью PowerShell, Windows инструментов управления или отдельно на конечных точках с помощью Безопасность Windows приложения
[Просмотр результатов сканирования](review-scan-results-microsoft-defender-antivirus.md) | Просмотр результатов сканирования с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или Безопасность Windows приложения