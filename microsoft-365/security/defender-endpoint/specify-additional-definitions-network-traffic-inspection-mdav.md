---
title: Укажите дополнительные наборы определений для проверки сетевого трафика для антивирусная программа в Microsoft Defender
description: Укажите дополнительные наборы определений для проверки сетевого трафика для антивирусная программа в Microsoft Defender.
keywords: антивирусная программа в Microsoft Defender, антивирусное программное обеспечение, безопасность, защитник, проверка сетевого трафика
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300259"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>Укажите дополнительные наборы определений для проверки сетевого трафика

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Дополнительные наборы определений для проверки сетевого трафика можно указать с помощью групповой политики.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>Использование групповой политики для указания дополнительных наборов определений для проверки сетевого трафика

1. На конечной точке управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Перейдите **Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **сетевой системы проверки.** 

3. Выберите **укажите дополнительные наборы определений для проверки сетевого трафика.** По умолчанию эта политика настроена как **Not configured**. 

4. Чтобы изменить политику, выберите ссылку **параметра политики** редактирования.

5. Выберите **включено,** а затем в разделе **Параметры** выберите **Показать ...**.

6. Добавьте записи в список и выберите **ОК.** 

   Каждая запись должна быть указана в качестве пары значения имени, где имя представляет строку представления guID набора определений. Например, набор guID определения, позволяющий включить анализ безопасности тестирования, определяется как: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` . Значение не используется, поэтому мы рекомендуем установить `0` его. 

7. Выберите **ОК** и разверните обновленный объект групповой политики. См. [консоль управления групповой политикой.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Вы используете объекты групповой политики в помещениях? Узнайте, как они переводятся в облаке. [Анализ объектов локальной групповой политики](/mem/intune/configuration/group-policy-analytics)с помощью аналитики групповой политики в Microsoft Endpoint Manager - Preview . 
  
## <a name="related-articles"></a>Связанные статьи

- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
 
- [Включение облачной защиты](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Создание и развертывание политик противомалярийных программ: служба облачной защиты](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)