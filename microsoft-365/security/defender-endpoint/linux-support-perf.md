---
title: Устранение неполадок с производительностью для Microsoft Defender для конечной точки для Linux
description: Устранение неполадок в конечной точке Microsoft Defender для Linux.
keywords: Microsoft, defender, atp, linux, performance
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cb43fd383606ab26ba2688ad5704bb7653e82a7f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860343"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Устранение неполадок с производительностью для Microsoft Defender для конечной точки в Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

В этой статье приводится ряд общих действий, которые можно использовать для сужение проблем производительности, связанных с Defender для конечной точки для Linux.

Защита в режиме реального времени (RTP) — это функция Defender for Endpoint для Linux, которая непрерывно отслеживает и защищает устройство от угроз. Он состоит из мониторинга файлов и процессов и других процессов.

В зависимости от запущенных приложений и характеристик устройства вы можете испытывать неоптимальную производительность при запуске Defender для Конечной точки для Linux. В частности, приложения или системные процессы, которые имеют доступ ко многим ресурсам в течение короткого времени, могут привести к проблеме производительности в Defender for Endpoint для Linux.

Перед **началом убедитесь, что другие** продукты безопасности в настоящее время не работают на устройстве. Несколько продуктов безопасности могут конфликтовть и влиять на производительность хостов.

Для устранения неполадок и устранения этих проблем можно использовать следующие действия:

1. Отключать защиту в режиме реального времени с помощью одного из следующих методов и наблюдать, повышается ли производительность. Этот подход помогает сузить, вносит ли Defender для Конечной точки для Linux вклад в проблемы производительности.

    Если устройство не управляется организацией, защита в режиме реального времени может быть отключена из командной строки:

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    Если устройство управляется организацией, защита в режиме реального времени может быть отключена администратором с помощью инструкций в Наборе предпочтений для Защитника для конечной точки [для Linux.](linux-preferences.md)

    Если проблема производительности сохраняется во время отключения защиты в режиме реального времени, ее происхождение может быть компонентом обнаружения конечной точки и ответа. В этом случае обратитесь в службу поддержки клиентов для получения дополнительных инструкций и смягчения последствий.

2. Чтобы найти приложения, которые запускают наибольшее большинство сканов, можно использовать статистику в режиме реального времени, собранную Defender для конечной точки для Linux.

    > [!NOTE]
    > Эта функция доступна в версии 100.90.70 или более новой версии.

    Эта функция включена по умолчанию на `Dogfood` `InsiderFast` каналах и каналах. Если вы используете другой канал обновления, эту функцию можно включить из командной строки:
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    Эта функция требует включения защиты в режиме реального времени. Чтобы проверить состояние защиты в режиме реального времени, запустите следующую команду:

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    Убедитесь, `real_time_protection_enabled` что запись `true` . В противном случае запустите следующую команду, чтобы включить ее:

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    Чтобы собрать текущую статистику, запустите:

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > Использование (примечание двойной тире) гарантирует, что формат вывода ```--output json``` готов к разметки.

    На выходе этой команды будут отсканироваться все процессы и связанные с ними действия сканирования.

3. В вашей системе Linux скачайте образец parser Python **high_cpu_parser.py** с помощью команды:

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    Выход этой команды должен быть похож на следующие:

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. Далее введите следующие команды:

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      Вывод выше — это список основных участников проблем производительности. Первый столбец — идентификатор процесса (PID), второй — имя процесса te, а последний — число отсканированных файлов, отсортированных по воздействию.
    Например, выход команды будет чем-то похожим на ниже: 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    Чтобы повысить производительность Defender для конечной точки для Linux, найдите точку с самым высоким числом под строкой и добавьте для нее `Total files scanned` исключение. Дополнительные сведения см. в [дополнительных сведениях: Настройка и проверка исключений для Defender для конечной точки для Linux.](linux-exclusions.md)

    >[!NOTE]
    > Приложение хранит статистику в памяти и отслеживает активность файлов только с момента ее начала и включения защиты в режиме реального времени. Процессы, запущенные до или во время отключения защиты в режиме реального времени, не учитываются. Кроме того, учитываются только события, которые вызвали сканирование.

5. Настройка ATP Microsoft Defender для Linux с исключениями для процессов или расположения дисков, которые способствуют повышению производительности и повторной защите в режиме реального времени.

    Дополнительные сведения см. в [выпуске Настройка и проверка исключений для Microsoft Defender ATP для Linux.](linux-exclusions.md)
