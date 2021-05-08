---
title: Запуск и настройка запланированных и по запросу сканов
description: Настройка и инициа антивирусная программа в Microsoft Defender проверки на конечных точках в сети.
keywords: сканирование, расписание, настройка, исключения, исключение файлов, исправление, результаты проверки, карантин, удаление угрозы, быстрое сканирование, полное сканирование, антивирусная программа в Microsoft Defender
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
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286249"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a>Настройка, инициирование и проверка результатов антивирусная программа в Microsoft Defender проверки & исправлений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Для настройки антивирусная программа в Microsoft Defender можно использовать групповые политики, powerShell и Windows средства управления (WMI). 

## <a name="in-this-section"></a>Содержание

| Статья | Описание |
|:---|:---|
|[Настройка и проверка исключений файлов, папок и файлов, открытых процессом, в антивирусная программа в Microsoft Defender проверки](configure-exclusions-microsoft-defender-antivirus.md) | Можно исключить файлы (в том числе файлы, измененные заданными процессами) и папки из проверки по запросу, планового сканирования и мониторинга и сканирования защиты в режиме реального времени |
|[Настройка параметров сканирования антивирусной программы в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Вы можете настроить антивирусная программа в Microsoft Defender, чтобы включить в сканирование определенные типы файлов хранения электронной почты, точек архивирования или репаража, а также архивных файлов (например, .zip файлов). Вы также можете включить сканирование сетевых файлов |
|[Настройка исправлений для сканирования](configure-remediation-microsoft-defender-antivirus.md) | Настройка того, антивирусная программа в Microsoft Defender следует делать при обнаружении угрозы, и как долго должны храниться карантинные файлы в папке карантина |
|[Настройка запланированных сканов](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Настройка повторяющихся (запланированных) сканирований, в том числе при их запуске и в качестве полного или быстрого сканирования. |
|[Настройка и запуск сканирования](run-scan-microsoft-defender-antivirus.md) | Запуск и настройка сканирования по запросу с помощью PowerShell, Windows инструментов управления или отдельно на конечных точках с помощью Безопасность Windows приложения |
|[Просмотр результатов сканирования](review-scan-results-microsoft-defender-antivirus.md) | Просмотр результатов сканирования с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или Безопасность Windows приложения |