---
title: Включить и настроить функции защиты от антивируса Microsoft Defender
description: Включить защиту на основе поведения, а также в режиме реального времени в Microsoft Defender AV.
keywords: heuristic, machine-learning, behaviour monitor, real-time protection, always-on, Microsoft Defender Antivirus, antimalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 9fc51682b659670a21c3c293ea8996beb228802a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765075"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Настройка поведенческой, эвристической защиты и защиты в режиме реального времени

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Антивирус Microsoft Defender использует несколько методов для защиты от угроз:

- Облачная защита для мгновенного обнаружения и блокировки новых и возникающих угроз
- Всегда на сканирование, с помощью мониторинга поведения файлов и процессов и других heuristics (также известный как "защита в режиме реального времени")
- Специальные обновления защиты на основе машинного обучения, ручного и автоматизированного анализа больших данных, а также комплексного исследования защиты от угроз

Можно настроить, как антивирус Microsoft Defender использует эти методы с помощью групповой политики, управления конфигурацией центра систем, cmdlets PowerShell и инструментов управления Windows (WMI).

В этом разделе описывается конфигурация для постоянного сканирования, включая обнаружение и блокировку приложений, которые считаются небезопасными, но не могут быть обнаружены в качестве вредоносных программ.

См. в рубке Использование антивирусных технологий [Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) следующего поколения с помощью облачной защиты для обеспечения и настройки облачной защиты антивирусной программы Microsoft Defender.

## <a name="in-this-section"></a>В этом разделе

 Статья | Описание
---|---
[Обнаружение и блокировка потенциально нежелательных приложений](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Обнаружение и блокировка нежелательных приложений в сети, таких как adware, модификаторы браузера и панели инструментов, а также вредоносные или поддельные антивирусные приложения
[Включить и настроить возможности защиты от антивируса Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md) | Включить и настроить функции мониторинга антивирусных вирусов Microsoft Defender в режиме реального времени, а также другие функции мониторинга вирусов, которые всегда на стороне Microsoft Defender.