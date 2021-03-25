---
title: Устранение неполадок с производительностью atP Microsoft Defender для Mac
description: Устранение неполадок с производительностью в ATP Microsoft Defender для Mac.
keywords: Microsoft, defender, atp, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f6dd5681dfafd069a4c52f72e1dc1733584283a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185913"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Устранение неполадок с производительностью для Microsoft Defender для конечной точки для Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки для Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

В этом разделе приводится ряд общих действий, которые можно использовать для сужение проблем производительности, связанных с Microsoft Defender для конечной точки для Mac.

Защита в режиме реального времени (RTP) — это функция Microsoft Defender для конечной точки для Mac, которая непрерывно отслеживает и защищает устройство от угроз. Он состоит из мониторинга файлов и процессов и других процессов.

В зависимости от запущенных приложений и характеристик устройства вы можете испытывать неоптимальную производительность при запуске Microsoft Defender для конечной точки для Mac. В частности, приложения или системные процессы, которые имеют доступ к многим ресурсам в течение короткого времени, могут привести к проблеме производительности в Microsoft Defender для конечной точки для Mac.

Для устранения неполадок и устранения этих проблем можно использовать следующие действия:

1. Отключать защиту в режиме реального времени с помощью одного из следующих методов и наблюдать, повышается ли производительность. Этот подход помогает сузить, вносит ли Microsoft Defender для Конечной точки для Mac вклад в проблемы производительности.

    Если устройство не управляется организацией, защита в режиме реального времени может быть отключена с помощью одного из следующих вариантов:

    - Из пользовательского интерфейса. Откройте Microsoft Defender для конечной точки для Mac и перейдите к **управлению настройками.**

      ![Управление скриншотом защиты в режиме реального времени](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - Из терминала. В целях безопасности эта операция требует высоты.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    Если устройство управляется организацией, защита в режиме реального времени может быть отключена администратором с помощью инструкций в наборе предпочтений [для Microsoft Defender для конечной](mac-preferences.md)точки для Mac.

2. Откройте finder и перейдите **к**  >  **утилитам приложений**. Откройте **монитор активности** и проанализируйте, какие приложения используют ресурсы в вашей системе. Типичные примеры включают обновление программного обеспечения и компиляторы.

3. Настройка Microsoft Defender для конечной точки для Mac с исключениями для процессов или расположения дисков, которые способствуют повышению производительности и повторной защите в режиме реального времени.

    Сведения см. в материале Настройка и проверка [исключений для Microsoft Defender для конечной точки для Mac.](mac-exclusions.md)
