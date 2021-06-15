---
title: Включить и настроить антивирусная программа в Microsoft Defender защиты
description: Включить защиту на основе поведения, а также в режиме реального времени в Microsoft Defender AV.
keywords: heuristic, machine-learning, behaviour monitor, real-time protection, always-on, антивирусная программа в Microsoft Defender, antimalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925567"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Настройка поведенческой, эвристической защиты и защиты в режиме реального времени


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
