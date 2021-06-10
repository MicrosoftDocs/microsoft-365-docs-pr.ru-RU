---
title: Включить и настроить антивирусная программа в Microsoft Defender защиты
description: Включить защиту на основе поведения, а также в режиме реального времени в Microsoft Defender AV.
keywords: heuristic, machine-learning, behaviour monitor, real-time protection, always-on, антивирусная программа в Microsoft Defender, antimalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274614"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Настройка поведенческой, эвристической защиты и защиты в режиме реального времени

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

антивирусная программа в Microsoft Defender использует несколько методов для защиты от угроз:

- Облачная защита для мгновенного обнаружения и блокировки новых и возникающих угроз
- Всегда на сканирование, с помощью мониторинга поведения файлов и процессов и других heuristics (также известный как "защита в режиме реального времени")
- Специальные обновления защиты на основе машинного обучения, ручного и автоматизированного анализа больших данных, а также комплексного исследования защиты от угроз

Вы можете настроить, как антивирусная программа в Microsoft Defender эти методы с помощью групповой политики, System Center управление конфигурацией, команды PowerShell и Windows инструментов управления (WMI).

В этом разделе описывается конфигурация для постоянного сканирования, включая обнаружение и блокировку приложений, которые считаются небезопасными, но не могут быть обнаружены в качестве вредоносных программ.

См. [в антивирусная программа в Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) технологий следующего поколения с помощью облачной защиты для обеспечения и настройки антивирусная программа в Microsoft Defender облачной защиты.

## <a name="in-this-section"></a>В этом разделе

 Статья | Описание
---|---
[Обнаружение и блокировка потенциально нежелательных приложений](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Обнаружение и блокировка нежелательных приложений в сети, таких как adware, модификаторы браузера и панели инструментов, а также вредоносные или поддельные антивирусные приложения
[Включить и настроить антивирусная программа в Microsoft Defender защиты](configure-real-time-protection-microsoft-defender-antivirus.md) | Включить и настроить защиту в режиме реального времени, юристику и другие функции антивирусная программа в Microsoft Defender мониторинга