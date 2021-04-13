---
title: Настройка периода ожидания облачного блока антивирусной программы Microsoft Defender
description: Можно настроить продолжительность блокировки антивируса Microsoft Defender файла в ожидании определения облачности.
keywords: Антивирус Microsoft Defender, антивирусные программы, безопасность, защитник, облако, время ожидания, блок, период, секунд
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691064"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Настройка периода ожидания облачного блока

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Когда антивирус Microsoft Defender находит подозрительный файл, он может запретить его работу во время запросов облачной службы [антивирусов Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)

Период блокировки файла по [](configure-block-at-first-sight-microsoft-defender-antivirus.md) умолчанию составляет 10 секунд. Можно указать дополнительный период времени для ожидания запуска файла. Это может помочь обеспечить достаточно времени для получения надлежащего определения от облачной службы антивирусной программы Microsoft Defender.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Необходимые условия для использования растянутой облачной блокировки

[Блок на первый взгляд,](configure-block-at-first-sight-microsoft-defender-antivirus.md) и его необходимо включить, прежде чем указать расширенный период ожидания.

## <a name="specify-the-extended-timeout-period"></a>Укажите расширенный период ожидания

С помощью групповой политики можно указать расширенный период времени для облачных проверок.

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.

3. Расширь дерево до компонентов Windows > **Microsoft Defender > MpEngine**

4. Дважды **щелкните Настройка расширенной облачной проверки** и убедитесь, что параметр включен. Укажите дополнительное время, чтобы не допустить запуска файла в ожидании определения облака. Вы можете указать дополнительное время в секундах от 1 секунды до 50 секунд. Это время будет добавлено к 10 секундам по умолчанию.

5. Нажмите кнопку **ОК**.

## <a name="related-topics"></a>Статьи по теме

- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Использование антивирусных технологий нового поколения с помощью облачной защиты](cloud-protection-microsoft-defender-antivirus.md)
- [Настройка блока с первого взгляда](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Включить облачную защиту](enable-cloud-protection-microsoft-defender-antivirus.md)