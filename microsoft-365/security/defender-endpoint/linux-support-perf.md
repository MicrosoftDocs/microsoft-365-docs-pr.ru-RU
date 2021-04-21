---
title: Устранение неполадок с производительностью для Microsoft Defender для конечной точки в Linux
description: Устранение неполадок в конечной точке Microsoft Defender на Linux.
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
ms.openlocfilehash: 5aaa95ef8202f3d0957113d8f20a39e4d3840227
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903990"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="845d9-104">Устранение неполадок с производительностью для Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="845d9-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="845d9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="845d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="845d9-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="845d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="845d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="845d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="845d9-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="845d9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="845d9-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="845d9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="845d9-110">В этой статье приводится ряд общих действий, которые можно использовать для сужение проблем производительности, связанных с Defender для конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="845d9-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="845d9-111">Защита в режиме реального времени (RTP) — это функция Defender for Endpoint для Linux, которая непрерывно отслеживает и защищает устройство от угроз.</span><span class="sxs-lookup"><span data-stu-id="845d9-111">Real-time protection (RTP) is a feature of Defender for Endpoint for Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="845d9-112">Он состоит из мониторинга файлов и процессов и других процессов.</span><span class="sxs-lookup"><span data-stu-id="845d9-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="845d9-113">В зависимости от запущенных приложений и характеристик устройства вы можете испытывать неоптимальную производительность при запуске Defender для Конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="845d9-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint for Linux.</span></span> <span data-ttu-id="845d9-114">В частности, приложения или системные процессы, которые имеют доступ ко многим ресурсам в течение короткого времени, могут привести к проблеме производительности в Defender for Endpoint для Linux.</span><span class="sxs-lookup"><span data-stu-id="845d9-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="845d9-115">Перед **началом убедитесь, что другие** продукты безопасности в настоящее время не работают на устройстве.</span><span class="sxs-lookup"><span data-stu-id="845d9-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="845d9-116">Несколько продуктов безопасности могут конфликтовть и влиять на производительность хостов.</span><span class="sxs-lookup"><span data-stu-id="845d9-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="845d9-117">Для устранения неполадок и устранения этих проблем можно использовать следующие действия:</span><span class="sxs-lookup"><span data-stu-id="845d9-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="845d9-118">Отключать защиту в режиме реального времени с помощью одного из следующих методов и наблюдать, повышается ли производительность.</span><span class="sxs-lookup"><span data-stu-id="845d9-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="845d9-119">Этот подход помогает сузить, вносит ли Defender для Конечной точки для Linux вклад в проблемы производительности.</span><span class="sxs-lookup"><span data-stu-id="845d9-119">This approach helps narrow down whether Defender for Endpoint for Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="845d9-120">Если устройство не управляется организацией, защита в режиме реального времени может быть отключена из командной строки:</span><span class="sxs-lookup"><span data-stu-id="845d9-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="845d9-121">Если устройство управляется организацией, защита в режиме реального времени может быть отключена администратором с помощью инструкций в Наборе предпочтений для Защитника для конечной точки [для Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="845d9-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="845d9-122">Если проблема производительности сохраняется во время отключения защиты в режиме реального времени, ее происхождение может быть компонентом обнаружения конечной точки и ответа.</span><span class="sxs-lookup"><span data-stu-id="845d9-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="845d9-123">В этом случае обратитесь в службу поддержки клиентов для получения дополнительных инструкций и смягчения последствий.</span><span class="sxs-lookup"><span data-stu-id="845d9-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="845d9-124">Чтобы найти приложения, которые запускают наибольшее большинство сканов, можно использовать статистику в режиме реального времени, собранную Defender для конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="845d9-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="845d9-125">Эта функция доступна в версии 100.90.70 или более новой версии.</span><span class="sxs-lookup"><span data-stu-id="845d9-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="845d9-126">Эта функция включена по умолчанию на `Dogfood` `InsiderFast` каналах и каналах.</span><span class="sxs-lookup"><span data-stu-id="845d9-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="845d9-127">Если вы используете другой канал обновления, эту функцию можно включить из командной строки:</span><span class="sxs-lookup"><span data-stu-id="845d9-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="845d9-128">Эта функция требует включения защиты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="845d9-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="845d9-129">Чтобы проверить состояние защиты в режиме реального времени, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="845d9-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="845d9-130">Убедитесь, `real_time_protection_enabled` что запись `true` .</span><span class="sxs-lookup"><span data-stu-id="845d9-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="845d9-131">В противном случае запустите следующую команду, чтобы включить ее:</span><span class="sxs-lookup"><span data-stu-id="845d9-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="845d9-132">Чтобы собрать текущую статистику, запустите:</span><span class="sxs-lookup"><span data-stu-id="845d9-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="845d9-133">Использование (примечание двойной тире) гарантирует, что формат вывода ```--output json``` готов к разметки.</span><span class="sxs-lookup"><span data-stu-id="845d9-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="845d9-134">На выходе этой команды будут отсканироваться все процессы и связанные с ними действия сканирования.</span><span class="sxs-lookup"><span data-stu-id="845d9-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="845d9-135">В вашей системе Linux скачайте образец parser Python **high_cpu_parser.py** с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="845d9-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="845d9-136">Выход этой команды должен быть похож на следующие:</span><span class="sxs-lookup"><span data-stu-id="845d9-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="845d9-137">Далее введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="845d9-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="845d9-138">Вывод выше — это список основных участников проблем производительности.</span><span class="sxs-lookup"><span data-stu-id="845d9-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="845d9-139">Первый столбец — идентификатор процесса (PID), второй — имя процесса te, а последний — число отсканированных файлов, отсортированных по воздействию.</span><span class="sxs-lookup"><span data-stu-id="845d9-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="845d9-140">Например, выход команды будет чем-то похожим на ниже:</span><span class="sxs-lookup"><span data-stu-id="845d9-140">For example, the output of the command will be something like the below:</span></span> 

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

    <span data-ttu-id="845d9-141">Чтобы повысить производительность Defender для конечной точки для Linux, найдите точку с самым высоким числом под строкой и добавьте для нее `Total files scanned` исключение.</span><span class="sxs-lookup"><span data-stu-id="845d9-141">To improve the performance of Defender for Endpoint for Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="845d9-142">Дополнительные сведения см. в [дополнительных сведениях: Настройка и проверка исключений для Defender для конечной точки для Linux.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="845d9-142">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="845d9-143">Приложение хранит статистику в памяти и отслеживает активность файлов только с момента ее начала и включения защиты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="845d9-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="845d9-144">Процессы, запущенные до или во время отключения защиты в режиме реального времени, не учитываются.</span><span class="sxs-lookup"><span data-stu-id="845d9-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="845d9-145">Кроме того, учитываются только события, которые вызвали сканирование.</span><span class="sxs-lookup"><span data-stu-id="845d9-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="845d9-146">Настройте конечную точку Microsoft Defender на Linux с исключениями для процессов или расположения дисков, которые способствуют повышению производительности и повторной защите в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="845d9-146">Configure Microsoft Defender Endpoint on Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="845d9-147">Дополнительные сведения см. в [выпуске Настройка и проверка исключений для Microsoft Defender для конечной точки для Linux.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="845d9-147">For more information, see [Configure and validate exclusions for Microsoft Defender for Endpoint for Linux](linux-exclusions.md).</span></span>
