---
title: AtP Защитника Майкрософт для ресурсов Linux
ms.reviewer: ''
description: Описывает ресурсы atP Microsoft Defender для Linux, в том числе, как удалить его, как собирать диагностические журналы, команды CLI и известные проблемы с продуктом.
keywords: Microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 7196053ffef3dffc3c737d0df26a5d12bdfe8a4c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187761"
---
# <a name="resources"></a><span data-ttu-id="aa1b3-104">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="aa1b3-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aa1b3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="aa1b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa1b3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="aa1b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa1b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa1b3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aa1b3-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="aa1b3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aa1b3-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="aa1b3-110">Сбор диагностических сведений</span><span class="sxs-lookup"><span data-stu-id="aa1b3-110">Collect diagnostic information</span></span>

<span data-ttu-id="aa1b3-111">Если вы можете воспроизвести проблему, сначала повысить уровень ведения журнала, запустить систему в течение некоторого времени, а затем восстановить уровень ведения журнала по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="aa1b3-112">Повышение уровня ведения журнала:</span><span class="sxs-lookup"><span data-stu-id="aa1b3-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="aa1b3-113">Воспроизвести проблему.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="aa1b3-114">Запустите следующую команду, чтобы выполнить back up Defender для журналов Endpoint.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="aa1b3-115">Файлы будут храниться внутри архива .zip.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="aa1b3-116">Эта команда также распечатает путь файла к резервному копированию после успешной операции:</span><span class="sxs-lookup"><span data-stu-id="aa1b3-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="aa1b3-117">Восстановление уровня ведения журнала:</span><span class="sxs-lookup"><span data-stu-id="aa1b3-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="aa1b3-118">Проблемы с установкой журнала</span><span class="sxs-lookup"><span data-stu-id="aa1b3-118">Log installation issues</span></span>

<span data-ttu-id="aa1b3-119">Если ошибка возникает во время установки, установщик будет сообщать только об общем сбое.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="aa1b3-120">Подробный журнал будет сохранен до `/var/log/microsoft/mdatp_install.log` .</span><span class="sxs-lookup"><span data-stu-id="aa1b3-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="aa1b3-121">Если во время установки вы испытываете проблемы, отправьте нам этот файл, чтобы мы могли помочь диагностировать причину.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="aa1b3-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="aa1b3-122">Uninstall</span></span>

<span data-ttu-id="aa1b3-123">Существует несколько способов удалить Defender для конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-123">There are several ways to uninstall Defender for Endpoint for Linux.</span></span> <span data-ttu-id="aa1b3-124">Если вы используете средство конфигурации, например Puppet, выполните инструкции по деинсталлации пакета для средства конфигурации.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="aa1b3-125">Ручная отмывка</span><span class="sxs-lookup"><span data-stu-id="aa1b3-125">Manual uninstallation</span></span>

- <span data-ttu-id="aa1b3-126">`sudo yum remove mdatp` для RHEL и вариантов (CentOS и Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="aa1b3-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="aa1b3-127">`sudo zypper remove mdatp` для SLES и вариантов.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="aa1b3-128">`sudo apt-get purge mdatp` для систем Ubuntu и Debian.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="aa1b3-129">Настройка из командной строки</span><span class="sxs-lookup"><span data-stu-id="aa1b3-129">Configure from the command line</span></span>

<span data-ttu-id="aa1b3-130">Из командной строки можно выполнять важные задачи, такие как управление настройками продуктов и запуск сканирования по запросу.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="aa1b3-131">Глобальные параметры</span><span class="sxs-lookup"><span data-stu-id="aa1b3-131">Global options</span></span>

<span data-ttu-id="aa1b3-132">По умолчанию средство командной строки выводит результат в формате, читаемом для человека.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="aa1b3-133">Кроме того, средство также поддерживает вывод результатов в качестве JSON, что полезно для сценариев автоматизации.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="aa1b3-134">Чтобы изменить вывод на JSON, `--output json` передай любую из ниженаводных команд.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="aa1b3-135">Поддерживаемые команды</span><span class="sxs-lookup"><span data-stu-id="aa1b3-135">Supported commands</span></span>

<span data-ttu-id="aa1b3-136">В следующей таблице перечислены команды для некоторых наиболее распространенных сценариев.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="aa1b3-137">Запустите `mdatp help` из терминала, чтобы просмотреть полный список поддерживаемых команд.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="aa1b3-138">Группа</span><span class="sxs-lookup"><span data-stu-id="aa1b3-138">Group</span></span>                 |<span data-ttu-id="aa1b3-139">Сценарий</span><span class="sxs-lookup"><span data-stu-id="aa1b3-139">Scenario</span></span>                                                |<span data-ttu-id="aa1b3-140">Команда</span><span class="sxs-lookup"><span data-stu-id="aa1b3-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="aa1b3-141">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-141">Configuration</span></span>         |<span data-ttu-id="aa1b3-142">Включите/отключите защиту в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="aa1b3-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="aa1b3-143">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-143">Configuration</span></span>         |<span data-ttu-id="aa1b3-144">Включите/отключите облачную защиту</span><span class="sxs-lookup"><span data-stu-id="aa1b3-144">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="aa1b3-145">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-145">Configuration</span></span>         |<span data-ttu-id="aa1b3-146">Включите/отключите диагностику продукта</span><span class="sxs-lookup"><span data-stu-id="aa1b3-146">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="aa1b3-147">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-147">Configuration</span></span>         |<span data-ttu-id="aa1b3-148">Включите/отключите автоматическую отправку образца</span><span class="sxs-lookup"><span data-stu-id="aa1b3-148">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="aa1b3-149">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-149">Configuration</span></span>         |<span data-ttu-id="aa1b3-150">Включите и отключите пассивный режим AV</span><span class="sxs-lookup"><span data-stu-id="aa1b3-150">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="aa1b3-151">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-151">Configuration</span></span>         |<span data-ttu-id="aa1b3-152">Добавление или удаление исключения антивируса для расширения файла</span><span class="sxs-lookup"><span data-stu-id="aa1b3-152">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="aa1b3-153">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-153">Configuration</span></span>         |<span data-ttu-id="aa1b3-154">Добавление или удаление исключения антивируса для файла</span><span class="sxs-lookup"><span data-stu-id="aa1b3-154">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="aa1b3-155">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-155">Configuration</span></span>         |<span data-ttu-id="aa1b3-156">Добавление или удаление исключения антивируса для каталога</span><span class="sxs-lookup"><span data-stu-id="aa1b3-156">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="aa1b3-157">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-157">Configuration</span></span>         |<span data-ttu-id="aa1b3-158">Добавление или удаление исключения антивируса для процесса</span><span class="sxs-lookup"><span data-stu-id="aa1b3-158">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="aa1b3-159">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-159">Configuration</span></span>         |<span data-ttu-id="aa1b3-160">Список всех исключений антивируса</span><span class="sxs-lookup"><span data-stu-id="aa1b3-160">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="aa1b3-161">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-161">Configuration</span></span>         |<span data-ttu-id="aa1b3-162">Добавление имени угрозы в разрешенный список</span><span class="sxs-lookup"><span data-stu-id="aa1b3-162">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="aa1b3-163">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-163">Configuration</span></span>         |<span data-ttu-id="aa1b3-164">Удаление имени угрозы из разрешенного списка</span><span class="sxs-lookup"><span data-stu-id="aa1b3-164">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="aa1b3-165">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-165">Configuration</span></span>         |<span data-ttu-id="aa1b3-166">Список всех разрешенных имен угроз</span><span class="sxs-lookup"><span data-stu-id="aa1b3-166">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="aa1b3-167">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-167">Configuration</span></span>         |<span data-ttu-id="aa1b3-168">Включив защиту PUA</span><span class="sxs-lookup"><span data-stu-id="aa1b3-168">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="aa1b3-169">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-169">Configuration</span></span>         |<span data-ttu-id="aa1b3-170">Отключение защиты PUA</span><span class="sxs-lookup"><span data-stu-id="aa1b3-170">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="aa1b3-171">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="aa1b3-171">Configuration</span></span>         |<span data-ttu-id="aa1b3-172">Включим режим аудита для защиты PUA</span><span class="sxs-lookup"><span data-stu-id="aa1b3-172">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="aa1b3-173">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="aa1b3-173">Diagnostics</span></span>           |<span data-ttu-id="aa1b3-174">Изменение уровня журнала</span><span class="sxs-lookup"><span data-stu-id="aa1b3-174">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="aa1b3-175">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="aa1b3-175">Diagnostics</span></span>           |<span data-ttu-id="aa1b3-176">Создание журналов диагностики</span><span class="sxs-lookup"><span data-stu-id="aa1b3-176">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="aa1b3-177">Здравоохранение</span><span class="sxs-lookup"><span data-stu-id="aa1b3-177">Health</span></span>                |<span data-ttu-id="aa1b3-178">Проверка состояния продукта</span><span class="sxs-lookup"><span data-stu-id="aa1b3-178">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="aa1b3-179">Защита</span><span class="sxs-lookup"><span data-stu-id="aa1b3-179">Protection</span></span>            |<span data-ttu-id="aa1b3-180">Сканирование пути</span><span class="sxs-lookup"><span data-stu-id="aa1b3-180">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="aa1b3-181">Защита</span><span class="sxs-lookup"><span data-stu-id="aa1b3-181">Protection</span></span>            |<span data-ttu-id="aa1b3-182">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="aa1b3-182">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="aa1b3-183">Защита</span><span class="sxs-lookup"><span data-stu-id="aa1b3-183">Protection</span></span>            |<span data-ttu-id="aa1b3-184">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="aa1b3-184">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="aa1b3-185">Защита</span><span class="sxs-lookup"><span data-stu-id="aa1b3-185">Protection</span></span>            |<span data-ttu-id="aa1b3-186">Отмена текущего сканирования по запросу</span><span class="sxs-lookup"><span data-stu-id="aa1b3-186">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="aa1b3-187">Защита</span><span class="sxs-lookup"><span data-stu-id="aa1b3-187">Protection</span></span>            |<span data-ttu-id="aa1b3-188">Запрос обновления сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="aa1b3-188">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="aa1b3-189">История защиты</span><span class="sxs-lookup"><span data-stu-id="aa1b3-189">Protection history</span></span>    |<span data-ttu-id="aa1b3-190">Распечатать всю историю защиты</span><span class="sxs-lookup"><span data-stu-id="aa1b3-190">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="aa1b3-191">История защиты</span><span class="sxs-lookup"><span data-stu-id="aa1b3-191">Protection history</span></span>    |<span data-ttu-id="aa1b3-192">Сведения об угрозах</span><span class="sxs-lookup"><span data-stu-id="aa1b3-192">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="aa1b3-193">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="aa1b3-193">Quarantine management</span></span> |<span data-ttu-id="aa1b3-194">Список всех карантинов</span><span class="sxs-lookup"><span data-stu-id="aa1b3-194">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="aa1b3-195">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="aa1b3-195">Quarantine management</span></span> |<span data-ttu-id="aa1b3-196">Удаление всех файлов из карантина</span><span class="sxs-lookup"><span data-stu-id="aa1b3-196">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="aa1b3-197">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="aa1b3-197">Quarantine management</span></span> |<span data-ttu-id="aa1b3-198">Добавление файла, обнаруженного в качестве угрозы карантину</span><span class="sxs-lookup"><span data-stu-id="aa1b3-198">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="aa1b3-199">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="aa1b3-199">Quarantine management</span></span> |<span data-ttu-id="aa1b3-200">Удаление файла, обнаруженного в качестве угрозы из карантина</span><span class="sxs-lookup"><span data-stu-id="aa1b3-200">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="aa1b3-201">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="aa1b3-201">Quarantine management</span></span> |<span data-ttu-id="aa1b3-202">Восстановление файла из карантина</span><span class="sxs-lookup"><span data-stu-id="aa1b3-202">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="aa1b3-203">Обнаружение и реагирование конечных точек</span><span class="sxs-lookup"><span data-stu-id="aa1b3-203">Endpoint Detection and Response</span></span> |<span data-ttu-id="aa1b3-204">Настройка раннего предварительного просмотра (неиспользована)</span><span class="sxs-lookup"><span data-stu-id="aa1b3-204">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="aa1b3-205">Обнаружение и реагирование конечных точек</span><span class="sxs-lookup"><span data-stu-id="aa1b3-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="aa1b3-206">Set group-id</span><span class="sxs-lookup"><span data-stu-id="aa1b3-206">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="aa1b3-207">Обнаружение и реагирование конечных точек</span><span class="sxs-lookup"><span data-stu-id="aa1b3-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="aa1b3-208">Тег Set/Remove, только `GROUP` поддерживаемый</span><span class="sxs-lookup"><span data-stu-id="aa1b3-208">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="aa1b3-209">Обнаружение и реагирование конечных точек</span><span class="sxs-lookup"><span data-stu-id="aa1b3-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="aa1b3-210">исключения из списка (корневой)</span><span class="sxs-lookup"><span data-stu-id="aa1b3-210">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="aa1b3-211">Сведения портала Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="aa1b3-211">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="aa1b3-212">На портале Defender for Endpoint вы увидите две категории сведений:</span><span class="sxs-lookup"><span data-stu-id="aa1b3-212">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="aa1b3-213">Антивирусные оповещений, в том числе:</span><span class="sxs-lookup"><span data-stu-id="aa1b3-213">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="aa1b3-214">Severity</span><span class="sxs-lookup"><span data-stu-id="aa1b3-214">Severity</span></span>
  - <span data-ttu-id="aa1b3-215">Тип сканирования</span><span class="sxs-lookup"><span data-stu-id="aa1b3-215">Scan type</span></span>
  - <span data-ttu-id="aa1b3-216">Сведения об устройстве (имя хозяина, идентификатор устройства, идентификатор клиента, версия приложения и тип ОС)</span><span class="sxs-lookup"><span data-stu-id="aa1b3-216">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="aa1b3-217">Сведения о файле (имя, путь, размер и хаш)</span><span class="sxs-lookup"><span data-stu-id="aa1b3-217">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="aa1b3-218">Сведения об угрозах (имя, тип и состояние)</span><span class="sxs-lookup"><span data-stu-id="aa1b3-218">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="aa1b3-219">Сведения об устройстве, в том числе:</span><span class="sxs-lookup"><span data-stu-id="aa1b3-219">Device information, including:</span></span>
  - <span data-ttu-id="aa1b3-220">Идентификатор устройства</span><span class="sxs-lookup"><span data-stu-id="aa1b3-220">Device identifier</span></span>
  - <span data-ttu-id="aa1b3-221">Идентификатор клиента</span><span class="sxs-lookup"><span data-stu-id="aa1b3-221">Tenant identifier</span></span>
  - <span data-ttu-id="aa1b3-222">Версия приложения.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-222">App version</span></span>
  - <span data-ttu-id="aa1b3-223">Hostname (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="aa1b3-223">Hostname</span></span>
  - <span data-ttu-id="aa1b3-224">Тип ОС</span><span class="sxs-lookup"><span data-stu-id="aa1b3-224">OS type</span></span>
  - <span data-ttu-id="aa1b3-225">Версия ОС</span><span class="sxs-lookup"><span data-stu-id="aa1b3-225">OS version</span></span>
  - <span data-ttu-id="aa1b3-226">Компьютерная модель</span><span class="sxs-lookup"><span data-stu-id="aa1b3-226">Computer model</span></span>
  - <span data-ttu-id="aa1b3-227">Архитектура процессора</span><span class="sxs-lookup"><span data-stu-id="aa1b3-227">Processor architecture</span></span>
  - <span data-ttu-id="aa1b3-228">Является ли устройство виртуальной машиной</span><span class="sxs-lookup"><span data-stu-id="aa1b3-228">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa1b3-229">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="aa1b3-229">Known issues</span></span>

- <span data-ttu-id="aa1b3-230">На странице компьютерной информации портала Центра безопасности Microsoft Defender можно увидеть "Отсутствие данных датчиков, нарушение связи", даже если продукт работает как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-230">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="aa1b3-231">Мы работаем над решением этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-231">We are working on addressing this issue.</span></span>
- <span data-ttu-id="aa1b3-232">Во время входа в систему пользователи не отображаются на портале Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aa1b3-232">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="aa1b3-233">В рассылках SUSE, если установка *libatomic1* не удается, необходимо проверить, зарегистрирована ли ваша ОС:</span><span class="sxs-lookup"><span data-stu-id="aa1b3-233">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
