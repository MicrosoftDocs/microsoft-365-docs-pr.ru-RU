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
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789091"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Настройка времени ожидания блокировки облака

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Когда антивирусная программа в Microsoft Defender обнаруживает подозрительный файл, он может запретить его работу во время запроса облачной [службы антивирусная программа в Microsoft Defender.](cloud-protection-microsoft-defender-antivirus.md)

Период блокировки файла по умолчанию [составляет](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10 секунд. Если вы администратор безопасности, вы можете указать больше времени, чтобы дождаться запуска файла. Расширение периода ожидания облачного блока может помочь обеспечить достаточно времени для получения надлежащего определения от антивирусная программа в Microsoft Defender облачной службы.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Необходимые условия для использования растянутой облачной блокировки

[Блок на первый взгляд,](configure-block-at-first-sight-microsoft-defender-antivirus.md) и его необходимо включить, прежде чем указать расширенный период ожидания.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>Укажите расширенный период ожидания с помощью Microsoft Endpoint Manager

Вы можете указать период ожидания облачного блока с политикой безопасности [конечной](/mem/intune/protect/endpoint-security-policy)точки в Microsoft Endpoint Manager .

1. Перейдите в центр администрирования Endpoint Manager [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) () и войдите.

2. Выберите **безопасность конечных точек,** а затем в **статье Управление**, выберите **антивирус**.

3. Выберите (или создайте) антивирусную политику.

4. В разделе **Параметры конфигурации** расширим **облачную защиту.** Затем в поле Расширенное время в секундах **в облаке Defender** укажите больше времени, в секундах, от 1 секунды до 50 секунд. Все, что вы указываете, добавляется к 10 секундам по умолчанию.

5. (Этот шаг необязателен) Внести любые другие изменения в антивирусную политику. (Нужна помощь? См. [Параметры для антивирусная программа в Microsoft Defender политики в Microsoft Intune.)](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)

6. Выберите **Далее** и завершите настройку политики.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>Укажите расширенный период ожидания с помощью групповой политики

С помощью групповой политики можно указать расширенный период времени для облачных проверок.

1. На компьютере управления групповой политикой откройте консоль [управления групповой политикой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.

3. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**

3. Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **MpEngine**.

4. Дважды **щелкните Настройка расширенной облачной проверки** и убедитесь, что параметр включен. 

   Укажите дополнительное время, чтобы не допустить запуска файла в ожидании определения облака. Укажите дополнительное время в секундах от 1 секунды до 50 секунд. Все, что вы указываете, добавляется к 10 секундам по умолчанию.

5. Нажмите кнопку **ОК**.

 