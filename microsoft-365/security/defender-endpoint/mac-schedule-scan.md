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
ms.openlocfilehash: 4694ff0c0d0892b9261e61683654dfb58dfd724b
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394769"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="8d0cb-104">Расписание сканирования с помощью Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="8d0cb-104">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8d0cb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8d0cb-105">**Applies to:**</span></span>
- [<span data-ttu-id="8d0cb-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8d0cb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8d0cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d0cb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8d0cb-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8d0cb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8d0cb-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="8d0cb-110">Хотя вы можете начать сканирование угрозы в любое время с помощью Microsoft Defender для конечной точки, ваше предприятие может воспользоваться запланированными или приученными проверками.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="8d0cb-111">Например, вы можете запланировать сканирование для запуска в начале каждого рабочего дня или недели.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="8d0cb-112">Расписание сканирования с *запуском*</span><span class="sxs-lookup"><span data-stu-id="8d0cb-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="8d0cb-113">Вы можете создать расписание  сканирования с помощью запущенного daemon на устройстве macOS.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="8d0cb-114">В следующем коде показана схема, используемая для расписания сканирования.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="8d0cb-115">Откройте текстовый редактор и используйте этот пример в качестве руководства для собственного запланированного файла сканирования.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="8d0cb-116">Дополнительные сведения о формате *файлов .plist,* используемом здесь, см. в материалах [о](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) файлах списка свойств информации на официальном веб-сайте разработчика Apple.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

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

2. <span data-ttu-id="8d0cb-117">Сохраните файл *как com.microsoft.wdav.schedquickscan.plist*.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="8d0cb-118">Чтобы выполнить полное сканирование вместо быстрого сканирования, измените строку 12, чтобы использовать параметр вместо (например) и сохранить файл как `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **полный** scan.plist* вместо *com.microsoft.wdav.sched **quick** scan.plist*.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="8d0cb-119">Open **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="8d0cb-120">Введите следующие команды для загрузки файла:</span><span class="sxs-lookup"><span data-stu-id="8d0cb-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="8d0cb-121">Запланированное сканирование будет запускаться в дату, время и частоту, определенные в p-list.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="8d0cb-122">В примере проверка выполняется в 2:00 каждую пятницу.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="8d0cb-123">Значение `Weekday` использует `StartCalendarInterval` integer, чтобы указать пятый день недели или пятницу.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="8d0cb-124">Агенты, *выполненные с запуском,* не будут выполняться в запланированное время во время сна устройства.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="8d0cb-125">Вместо этого они будут запускаться после возобновления работы устройства из режима сна.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="8d0cb-126">Если устройство отключено, сканирование будет работать в течение следующего запланированного времени сканирования.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="8d0cb-127">Запланируйте сканирование с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="8d0cb-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="8d0cb-128">Вы также можете запланировать сканирование с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="8d0cb-129">Сценарий [runMDATPQuickScan.sh,](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) доступный в [скриптах для Microsoft Defender для конечной](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) точки, сохранится при возобновлении работы устройства из режима сна.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="8d0cb-130">Дополнительные инструкции по использованию этого скрипта на устройствах macOS см. в [intune.](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-130">See [Use shell scripts on macOS devices in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
