---
title: Устранение неполадок с производительностью для Microsoft Defender для конечной точки на macOS
description: Устранение неполадок с производительностью в Microsoft Defender для конечной точки на macOS.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, performance
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
ms.openlocfilehash: 623717e7b1a3149dbccf07d32200820a7f9083cb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934253"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Устранение неполадок с производительностью для Microsoft Defender для конечной точки на macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки в macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

В этом разделе приводится ряд общих действий, которые можно использовать для сужение проблем производительности, связанных с Microsoft Defender для конечной точки на macOS.

Защита в режиме реального времени (RTP) — это функция Microsoft Defender для конечной точки на macOS, которая непрерывно отслеживает и защищает устройство от угроз. Он состоит из мониторинга файлов и процессов и других процессов.

В зависимости от запущенных приложений и характеристик устройства при запуске Microsoft Defender для конечной точки на macOS может возникнуть неоптимиальная производительность. В частности, приложения или системные процессы, которые имеют доступ к многим ресурсам в течение короткого времени, могут привести к проблеме производительности в Microsoft Defender для конечной точки на macOS.

Для устранения неполадок и устранения этих проблем можно использовать следующие действия:

1. Отключать защиту в режиме реального времени с помощью одного из следующих методов и наблюдать, повышается ли производительность. Этот подход помогает сузить, вносит ли Microsoft Defender для конечной точки на macOS вклад в проблемы производительности.

      Если устройство не управляется организацией, защита в режиме реального времени может быть отключена с помощью одного из следующих вариантов:

    - Из пользовательского интерфейса. Откройте Microsoft Defender для конечной точки на macOS и перейдите к **управлению настройками.**

      ![Управление скриншотом защиты в режиме реального времени](images/mdatp-36-rtp.png)

    - Из терминала. В целях безопасности эта операция требует высоты.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      Если устройство управляется организацией, защита в режиме реального времени может быть отключена администратором с помощью инструкций в наборе предпочтений для Microsoft Defender для конечной точки на [macOS.](mac-preferences.md)
      
      Если проблема производительности сохраняется во время отключения защиты в режиме реального времени, ее происхождение может быть компонентом обнаружения конечной точки и ответа. В этом случае обратитесь в службу поддержки клиентов для получения дополнительных инструкций и смягчения последствий.

2. Откройте finder и перейдите **к**  >  **утилитам приложений**. Откройте **монитор активности** и проанализируйте, какие приложения используют ресурсы в вашей системе. Типичные примеры включают обновление программного обеспечения и компиляторы.

1. Чтобы найти приложения, запускающие наибольшее сканировать, можно использовать статистику в режиме реального времени, собранную Defender для конечной точки на Mac.

      > [!NOTE]
      > Эта функция доступна в версии 100.90.70 или более новой версии.
      Эта функция включена по умолчанию на **каналах Dogfood** и **InsiderFast.** Если вы используете другой канал обновления, эту функцию можно включить из командной строки:
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      Эта функция требует включения защиты в режиме реального времени. Чтобы проверить состояние защиты в режиме реального времени, запустите следующую команду:

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    Убедитесь, **что real_time_protection_enabled** запись верна. В противном случае запустите следующую команду, чтобы включить ее:

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      Чтобы собрать текущую статистику, запустите:

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      > [!NOTE]
      > Использование **json --output** (обратите внимание на двойной тир) обеспечивает готовность формата вывода к разметки.
      На выходе этой команды будут отсканироваться все процессы и связанные с ними действия сканирования.

1. В системе Mac скачайте образец анализара Python high_cpu_parser.py с помощью команды:

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    Выход этой команды должен быть похож на следующие:

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. Далее введите следующие команды:

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      Вывод выше — это список основных участников проблем производительности. Первый столбец — идентификатор процесса (PID), второй — имя процесса te, а последний — число отсканированных файлов, отсортированных по воздействию.

      Например, выход команды будет чем-то похожим на ниже:

      ```output
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

      Чтобы повысить производительность Defender для конечной точки на Mac, найдите точку с самым высоким номером в строке Total files scanned и добавьте исключение для него. Дополнительные сведения см. в [дополнительных сведениях: Настройка и проверка исключений для Defender для конечной точки в Linux.](linux-exclusions.md)

      > [!NOTE]
      > Приложение хранит статистику в памяти и отслеживает активность файлов только с момента ее начала и включения защиты в режиме реального времени. Процессы, запущенные до или во время отключения защиты в режиме реального времени, не учитываются. Кроме того, учитываются только события, которые вызвали сканирование.
      > 
1. Настройка Microsoft Defender для конечной точки на macOS с исключениями для процессов или расположения дисков, которые способствуют проблеме производительности и повторно включить защиту в режиме реального времени.

     Подробнее см. в материале Настройка и проверка [исключений для Microsoft Defender для конечной точки на macOS.](mac-exclusions.md)
