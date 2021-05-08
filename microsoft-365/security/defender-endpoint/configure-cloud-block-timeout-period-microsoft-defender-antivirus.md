---
title: Настройка периода антивирусная программа в Microsoft Defender облачного блока
description: Вы можете настроить срок, антивирусная программа в Microsoft Defender будет блокировать работу файла в ожидании определения облака.
keywords: антивирусная программа в Microsoft Defender, antimalware, security, defender, cloud, timeout, block, period, seconds
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
ms.openlocfilehash: 02b8ee1c73116718d771847a43d6334e0723bd5c
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275314"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Настройка времени ожидания блокировки облака

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Когда антивирусная программа в Microsoft Defender обнаруживает подозрительный файл, он может запретить его работу во время запроса облачной [службы антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)

Период блокировки файла по [](configure-block-at-first-sight-microsoft-defender-antivirus.md) умолчанию составляет 10 секунд. Можно указать дополнительный период времени для ожидания запуска файла. Это может помочь обеспечить достаточно времени для получения надлежащего определения от антивирусная программа в Microsoft Defender облачной службы.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Необходимые условия для использования растянутой облачной блокировки

[Блок на первый взгляд,](configure-block-at-first-sight-microsoft-defender-antivirus.md) и его необходимо включить, прежде чем указать расширенный период ожидания.

## <a name="specify-the-extended-timeout-period"></a>Укажите расширенный период ожидания

С помощью групповой политики можно указать расширенный период времени для облачных проверок.

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.

3. Расширение дерева до **Windows компонентов > антивирусная программа в Microsoft Defender > MpEngine**

4. Дважды **щелкните Настройка расширенной облачной проверки** и убедитесь, что параметр включен. Укажите дополнительное время, чтобы не допустить запуска файла в ожидании определения облака. Вы можете указать дополнительное время в секундах от 1 секунды до 50 секунд. Это время будет добавлено к 10 секундам по умолчанию.

5. Нажмите кнопку **ОК**.

## <a name="related-topics"></a>Статьи по теме

- [антивирусная программа в Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Использование антивирусных технологий нового поколения с помощью облачной защиты](cloud-protection-microsoft-defender-antivirus.md)
- [Настройка блока с первого взгляда](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Включить облачную защиту](enable-cloud-protection-microsoft-defender-antivirus.md)