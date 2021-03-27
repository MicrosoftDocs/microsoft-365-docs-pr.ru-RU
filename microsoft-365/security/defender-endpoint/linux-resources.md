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
ms.openlocfilehash: ab5400a197a1f0ac61c8b298a06165d217f44fd1
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394738"
---
# <a name="resources"></a><span data-ttu-id="3cfe1-104">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="3cfe1-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3cfe1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3cfe1-105">**Applies to:**</span></span>
- [<span data-ttu-id="3cfe1-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3cfe1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3cfe1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cfe1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3cfe1-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3cfe1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3cfe1-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="3cfe1-110">Сбор диагностических сведений</span><span class="sxs-lookup"><span data-stu-id="3cfe1-110">Collect diagnostic information</span></span>

<span data-ttu-id="3cfe1-111">Если вы можете воспроизвести проблему, сначала повысить уровень ведения журнала, запустить систему в течение некоторого времени, а затем восстановить уровень ведения журнала по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="3cfe1-112">Повышение уровня ведения журнала:</span><span class="sxs-lookup"><span data-stu-id="3cfe1-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="3cfe1-113">Воспроизвести проблему.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="3cfe1-114">Запустите следующую команду, чтобы выполнить back up Defender для журналов Endpoint.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="3cfe1-115">Файлы будут храниться внутри архива .zip.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="3cfe1-116">Эта команда также распечатает путь файла к резервному копированию после успешной операции:</span><span class="sxs-lookup"><span data-stu-id="3cfe1-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="3cfe1-117">Восстановление уровня ведения журнала:</span><span class="sxs-lookup"><span data-stu-id="3cfe1-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="3cfe1-118">Проблемы с установкой журнала</span><span class="sxs-lookup"><span data-stu-id="3cfe1-118">Log installation issues</span></span>

<span data-ttu-id="3cfe1-119">Если ошибка возникает во время установки, установщик будет сообщать только об общем сбое.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="3cfe1-120">Подробный журнал будет сохранен до `/var/log/microsoft/mdatp_install.log` .</span><span class="sxs-lookup"><span data-stu-id="3cfe1-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="3cfe1-121">Если во время установки вы испытываете проблемы, отправьте нам этот файл, чтобы мы могли помочь диагностировать причину.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="3cfe1-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="3cfe1-122">Uninstall</span></span>

<span data-ttu-id="3cfe1-123">Существует несколько способов удалить Defender для конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-123">There are several ways to uninstall Defender for Endpoint for Linux.</span></span> <span data-ttu-id="3cfe1-124">Если вы используете средство конфигурации, например Puppet, выполните инструкции по деинсталлации пакета для средства конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="3cfe1-125">Ручная отмывка</span><span class="sxs-lookup"><span data-stu-id="3cfe1-125">Manual uninstallation</span></span>

- <span data-ttu-id="3cfe1-126">`sudo yum remove mdatp` для RHEL и вариантов (CentOS и Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="3cfe1-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="3cfe1-127">`sudo zypper remove mdatp` для SLES и вариантов.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="3cfe1-128">`sudo apt-get purge mdatp` для систем Ubuntu и Debian.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="3cfe1-129">Настройка из командной строки</span><span class="sxs-lookup"><span data-stu-id="3cfe1-129">Configure from the command line</span></span>

<span data-ttu-id="3cfe1-130">Из командной строки можно выполнять важные задачи, такие как управление настройками продуктов и запуск сканирования по запросу.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="3cfe1-131">Глобальные параметры</span><span class="sxs-lookup"><span data-stu-id="3cfe1-131">Global options</span></span>

<span data-ttu-id="3cfe1-132">По умолчанию средство командной строки выводит результат в формате, читаемом для человека.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="3cfe1-133">Кроме того, средство также поддерживает вывод результатов в качестве JSON, что полезно для сценариев автоматизации.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="3cfe1-134">Чтобы изменить вывод на JSON, `--output json` передай любую из ниженаводных команд.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="3cfe1-135">Поддерживаемые команды</span><span class="sxs-lookup"><span data-stu-id="3cfe1-135">Supported commands</span></span>

<span data-ttu-id="3cfe1-136">В следующей таблице перечислены команды для некоторых наиболее распространенных сценариев.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="3cfe1-137">Запустите `mdatp help` из терминала, чтобы просмотреть полный список поддерживаемых команд.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="3cfe1-138">Группа</span><span class="sxs-lookup"><span data-stu-id="3cfe1-138">Group</span></span>                 |<span data-ttu-id="3cfe1-139">Сценарий</span><span class="sxs-lookup"><span data-stu-id="3cfe1-139">Scenario</span></span>                                                |<span data-ttu-id="3cfe1-140">Команда</span><span class="sxs-lookup"><span data-stu-id="3cfe1-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="3cfe1-141">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-141">Configuration</span></span>         |<span data-ttu-id="3cfe1-142">Включите/отключите защиту в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="3cfe1-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="3cfe1-143">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-143">Configuration</span></span>         |<span data-ttu-id="3cfe1-144">Включите/отключите мониторинг поведения</span><span class="sxs-lookup"><span data-stu-id="3cfe1-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|<span data-ttu-id="3cfe1-145">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-145">Configuration</span></span>         |<span data-ttu-id="3cfe1-146">Включите/отключите облачную защиту</span><span class="sxs-lookup"><span data-stu-id="3cfe1-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="3cfe1-147">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-147">Configuration</span></span>         |<span data-ttu-id="3cfe1-148">Включите/отключите диагностику продукта</span><span class="sxs-lookup"><span data-stu-id="3cfe1-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="3cfe1-149">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-149">Configuration</span></span>         |<span data-ttu-id="3cfe1-150">Включите/отключите автоматическую отправку образца</span><span class="sxs-lookup"><span data-stu-id="3cfe1-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="3cfe1-151">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-151">Configuration</span></span>         |<span data-ttu-id="3cfe1-152">Включите и отключите пассивный режим AV</span><span class="sxs-lookup"><span data-stu-id="3cfe1-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="3cfe1-153">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-153">Configuration</span></span>         |<span data-ttu-id="3cfe1-154">Добавление или удаление исключения антивируса для расширения файла</span><span class="sxs-lookup"><span data-stu-id="3cfe1-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="3cfe1-155">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-155">Configuration</span></span>         |<span data-ttu-id="3cfe1-156">Добавление или удаление исключения антивируса для файла</span><span class="sxs-lookup"><span data-stu-id="3cfe1-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="3cfe1-157">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-157">Configuration</span></span>         |<span data-ttu-id="3cfe1-158">Добавление или удаление исключения антивируса для каталога</span><span class="sxs-lookup"><span data-stu-id="3cfe1-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="3cfe1-159">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-159">Configuration</span></span>         |<span data-ttu-id="3cfe1-160">Добавление или удаление исключения антивируса для процесса</span><span class="sxs-lookup"><span data-stu-id="3cfe1-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="3cfe1-161">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-161">Configuration</span></span>         |<span data-ttu-id="3cfe1-162">Список всех исключений антивируса</span><span class="sxs-lookup"><span data-stu-id="3cfe1-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="3cfe1-163">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-163">Configuration</span></span>         |<span data-ttu-id="3cfe1-164">Добавление имени угрозы в разрешенный список</span><span class="sxs-lookup"><span data-stu-id="3cfe1-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="3cfe1-165">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-165">Configuration</span></span>         |<span data-ttu-id="3cfe1-166">Удаление имени угрозы из разрешенного списка</span><span class="sxs-lookup"><span data-stu-id="3cfe1-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="3cfe1-167">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-167">Configuration</span></span>         |<span data-ttu-id="3cfe1-168">Список всех разрешенных имен угроз</span><span class="sxs-lookup"><span data-stu-id="3cfe1-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="3cfe1-169">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-169">Configuration</span></span>         |<span data-ttu-id="3cfe1-170">Включив защиту PUA</span><span class="sxs-lookup"><span data-stu-id="3cfe1-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="3cfe1-171">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-171">Configuration</span></span>         |<span data-ttu-id="3cfe1-172">Отключение защиты PUA</span><span class="sxs-lookup"><span data-stu-id="3cfe1-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="3cfe1-173">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3cfe1-173">Configuration</span></span>         |<span data-ttu-id="3cfe1-174">Включим режим аудита для защиты PUA</span><span class="sxs-lookup"><span data-stu-id="3cfe1-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="3cfe1-175">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="3cfe1-175">Diagnostics</span></span>           |<span data-ttu-id="3cfe1-176">Изменение уровня журнала</span><span class="sxs-lookup"><span data-stu-id="3cfe1-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="3cfe1-177">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="3cfe1-177">Diagnostics</span></span>           |<span data-ttu-id="3cfe1-178">Создание журналов диагностики</span><span class="sxs-lookup"><span data-stu-id="3cfe1-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="3cfe1-179">Здравоохранение</span><span class="sxs-lookup"><span data-stu-id="3cfe1-179">Health</span></span>                |<span data-ttu-id="3cfe1-180">Проверка состояния продукта</span><span class="sxs-lookup"><span data-stu-id="3cfe1-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="3cfe1-181">Защита</span><span class="sxs-lookup"><span data-stu-id="3cfe1-181">Protection</span></span>            |<span data-ttu-id="3cfe1-182">Сканирование пути</span><span class="sxs-lookup"><span data-stu-id="3cfe1-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="3cfe1-183">Защита</span><span class="sxs-lookup"><span data-stu-id="3cfe1-183">Protection</span></span>            |<span data-ttu-id="3cfe1-184">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="3cfe1-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="3cfe1-185">Защита</span><span class="sxs-lookup"><span data-stu-id="3cfe1-185">Protection</span></span>            |<span data-ttu-id="3cfe1-186">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="3cfe1-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="3cfe1-187">Защита</span><span class="sxs-lookup"><span data-stu-id="3cfe1-187">Protection</span></span>            |<span data-ttu-id="3cfe1-188">Отмена текущего сканирования по запросу</span><span class="sxs-lookup"><span data-stu-id="3cfe1-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="3cfe1-189">Защита</span><span class="sxs-lookup"><span data-stu-id="3cfe1-189">Protection</span></span>            |<span data-ttu-id="3cfe1-190">Запрос обновления сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="3cfe1-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="3cfe1-191">История защиты</span><span class="sxs-lookup"><span data-stu-id="3cfe1-191">Protection history</span></span>    |<span data-ttu-id="3cfe1-192">Распечатать всю историю защиты</span><span class="sxs-lookup"><span data-stu-id="3cfe1-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="3cfe1-193">История защиты</span><span class="sxs-lookup"><span data-stu-id="3cfe1-193">Protection history</span></span>    |<span data-ttu-id="3cfe1-194">Сведения об угрозах</span><span class="sxs-lookup"><span data-stu-id="3cfe1-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="3cfe1-195">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="3cfe1-195">Quarantine management</span></span> |<span data-ttu-id="3cfe1-196">Список всех карантинов</span><span class="sxs-lookup"><span data-stu-id="3cfe1-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="3cfe1-197">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="3cfe1-197">Quarantine management</span></span> |<span data-ttu-id="3cfe1-198">Удаление всех файлов из карантина</span><span class="sxs-lookup"><span data-stu-id="3cfe1-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="3cfe1-199">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="3cfe1-199">Quarantine management</span></span> |<span data-ttu-id="3cfe1-200">Добавление файла, обнаруженного в качестве угрозы карантину</span><span class="sxs-lookup"><span data-stu-id="3cfe1-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="3cfe1-201">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="3cfe1-201">Quarantine management</span></span> |<span data-ttu-id="3cfe1-202">Удаление файла, обнаруженного в качестве угрозы из карантина</span><span class="sxs-lookup"><span data-stu-id="3cfe1-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="3cfe1-203">Управление карантином</span><span class="sxs-lookup"><span data-stu-id="3cfe1-203">Quarantine management</span></span> |<span data-ttu-id="3cfe1-204">Восстановление файла из карантина</span><span class="sxs-lookup"><span data-stu-id="3cfe1-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="3cfe1-205">Обнаружение и реагирование конечных точек</span><span class="sxs-lookup"><span data-stu-id="3cfe1-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="3cfe1-206">Настройка раннего предварительного просмотра (неиспользована)</span><span class="sxs-lookup"><span data-stu-id="3cfe1-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="3cfe1-207">Обнаружение и реагирование конечных точек</span><span class="sxs-lookup"><span data-stu-id="3cfe1-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="3cfe1-208">Set group-id</span><span class="sxs-lookup"><span data-stu-id="3cfe1-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="3cfe1-209">Обнаружение и реагирование конечных точек</span><span class="sxs-lookup"><span data-stu-id="3cfe1-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="3cfe1-210">Тег Set/Remove, только `GROUP` поддерживаемый</span><span class="sxs-lookup"><span data-stu-id="3cfe1-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="3cfe1-211">Обнаружение и реагирование конечных точек</span><span class="sxs-lookup"><span data-stu-id="3cfe1-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="3cfe1-212">исключения из списка (корневой)</span><span class="sxs-lookup"><span data-stu-id="3cfe1-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="3cfe1-213">Сведения портала Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="3cfe1-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="3cfe1-214">На портале Defender for Endpoint вы увидите две категории сведений:</span><span class="sxs-lookup"><span data-stu-id="3cfe1-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="3cfe1-215">Антивирусные оповещений, в том числе:</span><span class="sxs-lookup"><span data-stu-id="3cfe1-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="3cfe1-216">Severity</span><span class="sxs-lookup"><span data-stu-id="3cfe1-216">Severity</span></span>
  - <span data-ttu-id="3cfe1-217">Тип сканирования</span><span class="sxs-lookup"><span data-stu-id="3cfe1-217">Scan type</span></span>
  - <span data-ttu-id="3cfe1-218">Сведения об устройстве (имя хозяина, идентификатор устройства, идентификатор клиента, версия приложения и тип ОС)</span><span class="sxs-lookup"><span data-stu-id="3cfe1-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="3cfe1-219">Сведения о файле (имя, путь, размер и хаш)</span><span class="sxs-lookup"><span data-stu-id="3cfe1-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="3cfe1-220">Сведения об угрозах (имя, тип и состояние)</span><span class="sxs-lookup"><span data-stu-id="3cfe1-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="3cfe1-221">Сведения об устройстве, в том числе:</span><span class="sxs-lookup"><span data-stu-id="3cfe1-221">Device information, including:</span></span>
  - <span data-ttu-id="3cfe1-222">Идентификатор устройства</span><span class="sxs-lookup"><span data-stu-id="3cfe1-222">Device identifier</span></span>
  - <span data-ttu-id="3cfe1-223">Идентификатор клиента</span><span class="sxs-lookup"><span data-stu-id="3cfe1-223">Tenant identifier</span></span>
  - <span data-ttu-id="3cfe1-224">Версия приложения.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-224">App version</span></span>
  - <span data-ttu-id="3cfe1-225">Hostname (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="3cfe1-225">Hostname</span></span>
  - <span data-ttu-id="3cfe1-226">Тип ОС</span><span class="sxs-lookup"><span data-stu-id="3cfe1-226">OS type</span></span>
  - <span data-ttu-id="3cfe1-227">Версия ОС</span><span class="sxs-lookup"><span data-stu-id="3cfe1-227">OS version</span></span>
  - <span data-ttu-id="3cfe1-228">Компьютерная модель</span><span class="sxs-lookup"><span data-stu-id="3cfe1-228">Computer model</span></span>
  - <span data-ttu-id="3cfe1-229">Архитектура процессора</span><span class="sxs-lookup"><span data-stu-id="3cfe1-229">Processor architecture</span></span>
  - <span data-ttu-id="3cfe1-230">Является ли устройство виртуальной машиной</span><span class="sxs-lookup"><span data-stu-id="3cfe1-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="3cfe1-231">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3cfe1-231">Known issues</span></span>

- <span data-ttu-id="3cfe1-232">На странице компьютерной информации портала Центра безопасности Microsoft Defender можно увидеть "Отсутствие данных датчиков, нарушение связи", даже если продукт работает как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="3cfe1-233">Мы работаем над решением этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="3cfe1-234">Во время входа в систему пользователи не отображаются на портале Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="3cfe1-235">В рассылках SUSE, если установка *libatomic1* не удается, необходимо проверить, зарегистрирована ли ваша ОС:</span><span class="sxs-lookup"><span data-stu-id="3cfe1-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
