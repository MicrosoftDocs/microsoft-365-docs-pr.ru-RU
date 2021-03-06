---
title: Включив распознавание протокола для антивирусная программа в Microsoft Defender
description: Включи распознавание протокола для антивирусная программа в Microsoft Defender.
keywords: антивирусная программа в Microsoft Defender, антивирусное программное обеспечение, безопасность, защита, распознавание протоколов
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296493"
---
# <a name="turn-on-protocol-recognition"></a>Включив распознавание протокола 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Этот параметр политики позволяет настроить распознавание протоколов для защиты сети от эксплойтов известных уязвимостей. Если включить или не настроить этот параметр, будет включено распознавание протокола. Если отключить этот параметр, распознавание протокола будет отключено.

## <a name="use-group-policy-to-configure-protocol-recognition"></a>Использование групповой политики для настройки распознавания протоколов

1. На конечной точке управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Перейдите **к административным** шаблонам конфигурации  >    >  **компьютера Windows компонентов**  >  **антивирусная программа в Microsoft Defender**  >  **сетевой системы проверки.** 

3. Выберите **распознавание протокола.** По умолчанию эта политика включена. Если набор **не настроен,** включено определение выхода на пенсию. 

4. Чтобы изменить политику, выберите ссылку **параметра политики** редактирования.

5. Выберите **включено,** а затем выберите **ОК**.

6. Развертывание обновленного объекта групповой политики. См. [консоль управления групповой политикой.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Вы используете объекты групповой политики в помещениях? Узнайте, как они переводятся в облаке. [Анализ объектов локальной групповой политики](/mem/intune/configuration/group-policy-analytics)с помощью аналитики групповой политики в Microsoft Endpoint Manager - Preview . 
  
## <a name="related-articles"></a>Связанные статьи

- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
 
- [Включение облачной защиты](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Создание и развертывание политик противомалярийных программ: служба облачной защиты](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)