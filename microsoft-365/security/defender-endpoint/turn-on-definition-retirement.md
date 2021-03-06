---
title: Включим выход на пенсию определения для антивирусная программа в Microsoft Defender
description: Включим выход на пенсию определения для антивирусная программа в Microsoft Defender.
keywords: антивирусная программа в Microsoft Defender, antimalware, security, defender, definition retirement
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903808"
---
# <a name="turn-on-definition-retirement"></a>Включив выход на пенсию определения

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Вы можете настроить определение выхода на пенсию с помощью групповой политики. Определение выхода на пенсию проверяет, есть ли на компьютере необходимые обновления безопасности, необходимые для защиты от определенной уязвимости. Если система не уязвима для эксплойтов, обнаруженных определением, то это определение является "отмененным". Если все сведения о безопасности для заданного протокола будут отменены, этот протокол больше не будет размыт. Включение этой функции помогает повысить производительность. На компьютере, который обновляется со всеми последними обновлениями безопасности, защита сети не повлияет на производительность сети.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Использование групповой политики для настройки выхода на пенсию определения

1. На конечной точке управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Перейдите **к административным** шаблонам конфигурации  >    >  **компьютера Windows компонентов**  >  **антивирусная программа в Microsoft Defender**  >  **сетевой системы проверки.** 

3. Выберите **включив выход на пенсию определения.** По умолчанию эта политика включена. Если набор **не настроен,** включено определение выхода на пенсию. 

4. Чтобы изменить политику, выберите ссылку **параметра политики** редактирования.

5. Выберите **включено,** а затем выберите **ОК**.

6. Развертывание обновленного объекта групповой политики. См. [консоль управления групповой политикой.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Вы используете объекты групповой политики в помещениях? Узнайте, как они переводятся в облаке. [Анализ объектов локальной групповой политики](/mem/intune/configuration/group-policy-analytics)с помощью аналитики групповой политики в Microsoft Endpoint Manager - Preview . 
  
