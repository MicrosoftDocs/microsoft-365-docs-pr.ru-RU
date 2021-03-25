---
title: Расписание сканирования с помощью MDATP для macOS
description: Узнайте, как запланировать автоматическое время сканирования atP Microsoft Defender в macOS, чтобы лучше защитить активы организации.
keywords: Microsoft, defender, atp, mac, scans, antivirus
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
ms.openlocfilehash: 4151513874d295e3033b1ed365f10fb576c4ac18
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074470"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a>Расписание сканирования с помощью Microsoft Defender для конечной точки для Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Хотя вы можете начать сканирование угрозы в любое время с помощью Microsoft Defender для конечной точки, ваше предприятие может воспользоваться запланированными или приученными проверками. Например, вы можете запланировать сканирование для запуска в начале каждого рабочего дня или недели. 

## <a name="schedule-a-scan-with-launchd"></a>Расписание сканирования с *запуском*

Вы можете создать расписание  сканирования с помощью запущенного daemon на устройстве macOS.

1. В следующем коде показана схема, используемая для расписания сканирования. Откройте текстовый редактор и используйте этот пример в качестве руководства для собственного запланированного файла сканирования.

    Дополнительные сведения о формате *файлов .plist,* используемом здесь, см. в материалах [о](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) файлах списка свойств информации на официальном веб-сайте разработчика Apple.

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. Сохраните файл *как com.microsoft.wdav.schedquickscan.plist*.

    > [!TIP]
    > Чтобы выполнить полное сканирование вместо быстрого сканирования, измените строку 12, чтобы использовать параметр вместо (например) и сохранить файл как `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **полный** scan.plist* вместо *com.microsoft.wdav.sched **quick** scan.plist*.

3. Open **Terminal**.
4. Введите следующие команды для загрузки файла:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. Запланированное сканирование будет запускаться в дату, время и частоту, определенные в p-list. В примере проверка выполняется в 2:00 каждую пятницу. 

    Значение `Weekday` использует `StartCalendarInterval` integer, чтобы указать пятый день недели или пятницу.

 > [!IMPORTANT]
 > Агенты, *выполненные с запуском,* не будут выполняться в запланированное время во время сна устройства. Вместо этого они будут запускаться после возобновления работы устройства из режима сна.
 >
 > Если устройство отключено, сканирование будет работать в течение следующего запланированного времени сканирования.

## <a name="schedule-a-scan-with-intune"></a>Запланируйте сканирование с помощью Intune

Вы также можете запланировать сканирование с помощью Microsoft Intune. Сценарий [runMDATPQuickScan.sh,](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) доступный в [скриптах для Microsoft Defender для конечной](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) точки, сохранится при возобновлении работы устройства из режима сна. 

Дополнительные инструкции по использованию этого скрипта на устройствах macOS см. в [intune.](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts)
