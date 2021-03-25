---
title: Ресурсы для ATP Защитника Майкрософт для Mac
description: Ресурсы для MICROSOFT Defender ATP для Mac, в том числе как удалить его, как собирать журналы диагностики, команды CLI и известные проблемы с продуктом.
keywords: Microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 37d31fe93a849871e7da92fff521b6a75beac531
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187641"
---
# <a name="resources-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="0bef8-104">Ресурсы для Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="0bef8-104">Resources for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0bef8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0bef8-105">**Applies to:**</span></span>
- [<span data-ttu-id="0bef8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0bef8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0bef8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0bef8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0bef8-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0bef8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0bef8-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0bef8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="0bef8-110">Сбор диагностических сведений</span><span class="sxs-lookup"><span data-stu-id="0bef8-110">Collecting diagnostic information</span></span>

<span data-ttu-id="0bef8-111">Если вы можете воспроизвести проблему, увеличите уровень ведения журнала, запустите систему в течение некоторого времени и восстановите уровень ведения журнала по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0bef8-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="0bef8-112">Повышение уровня ведения журнала:</span><span class="sxs-lookup"><span data-stu-id="0bef8-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="0bef8-113">Воспроизведение проблемы</span><span class="sxs-lookup"><span data-stu-id="0bef8-113">Reproduce the problem</span></span>

3. <span data-ttu-id="0bef8-114">Запустите `sudo mdatp diagnostic create` для поддержки журналов Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="0bef8-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="0bef8-115">Файлы будут храниться в архиве .zip.</span><span class="sxs-lookup"><span data-stu-id="0bef8-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="0bef8-116">Эта команда также распечатает путь файла к резервному копированию после успешной операции.</span><span class="sxs-lookup"><span data-stu-id="0bef8-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="0bef8-117">По умолчанию журналы диагностики сохраняются до `/Library/Application Support/Microsoft/Defender/wdavdiag/` .</span><span class="sxs-lookup"><span data-stu-id="0bef8-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="0bef8-118">Чтобы изменить каталог, в котором сохраняются диагностические журналы, перейдите в приведенную ниже команду, заменив `--path [directory]` `[directory]` нужный каталог.</span><span class="sxs-lookup"><span data-stu-id="0bef8-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="0bef8-119">Восстановление уровня ведения журнала:</span><span class="sxs-lookup"><span data-stu-id="0bef8-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="0bef8-120">Проблемы с установкой журнала</span><span class="sxs-lookup"><span data-stu-id="0bef8-120">Logging installation issues</span></span>

<span data-ttu-id="0bef8-121">Если ошибка возникает во время установки, установщик будет сообщать только об общем сбое.</span><span class="sxs-lookup"><span data-stu-id="0bef8-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="0bef8-122">Подробный журнал будет сохранен до `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="0bef8-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="0bef8-123">Если во время установки вы испытываете проблемы, отправьте нам этот файл, чтобы мы могли помочь диагностировать причину.</span><span class="sxs-lookup"><span data-stu-id="0bef8-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="0bef8-124">Uninstalling</span><span class="sxs-lookup"><span data-stu-id="0bef8-124">Uninstalling</span></span>

<span data-ttu-id="0bef8-125">Существует несколько способов удалить Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="0bef8-125">There are several ways to uninstall Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="0bef8-126">Обратите внимание, что, несмотря на то, что централизованный централизованный отмывок доступен в JAMF, он еще не доступен для Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="0bef8-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="0bef8-127">Интерактивная деинсталлация</span><span class="sxs-lookup"><span data-stu-id="0bef8-127">Interactive uninstallation</span></span>

- <span data-ttu-id="0bef8-128">Open **Finder > приложения**.</span><span class="sxs-lookup"><span data-stu-id="0bef8-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="0bef8-129">Щелкните правой **кнопкой мыши по atP Microsoft Defender > Move to Trash**.</span><span class="sxs-lookup"><span data-stu-id="0bef8-129">Right click on **Microsoft Defender ATP > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="0bef8-130">Из командной строки</span><span class="sxs-lookup"><span data-stu-id="0bef8-130">From the command line</span></span>

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="0bef8-131">Настройка из командной строки</span><span class="sxs-lookup"><span data-stu-id="0bef8-131">Configuring from the command line</span></span>

<span data-ttu-id="0bef8-132">Из командной строки можно выполнять важные задачи, такие как управление настройками продуктов и сканы по запросу.</span><span class="sxs-lookup"><span data-stu-id="0bef8-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="0bef8-133">Группа</span><span class="sxs-lookup"><span data-stu-id="0bef8-133">Group</span></span>        |<span data-ttu-id="0bef8-134">Сценарий</span><span class="sxs-lookup"><span data-stu-id="0bef8-134">Scenario</span></span>                                   |<span data-ttu-id="0bef8-135">Команда</span><span class="sxs-lookup"><span data-stu-id="0bef8-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="0bef8-136">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-136">Configuration</span></span>|<span data-ttu-id="0bef8-137">Включите/отключите защиту в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="0bef8-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="0bef8-138">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-138">Configuration</span></span>|<span data-ttu-id="0bef8-139">Включите/отключите облачную защиту</span><span class="sxs-lookup"><span data-stu-id="0bef8-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="0bef8-140">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-140">Configuration</span></span>|<span data-ttu-id="0bef8-141">Включите/отключите диагностику продукта</span><span class="sxs-lookup"><span data-stu-id="0bef8-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="0bef8-142">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-142">Configuration</span></span>|<span data-ttu-id="0bef8-143">Включите/отключите автоматическую отправку образца</span><span class="sxs-lookup"><span data-stu-id="0bef8-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="0bef8-144">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-144">Configuration</span></span>|<span data-ttu-id="0bef8-145">Добавление имени угрозы в разрешенный список</span><span class="sxs-lookup"><span data-stu-id="0bef8-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="0bef8-146">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-146">Configuration</span></span>|<span data-ttu-id="0bef8-147">Удаление имени угрозы из разрешенного списка</span><span class="sxs-lookup"><span data-stu-id="0bef8-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="0bef8-148">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-148">Configuration</span></span>|<span data-ttu-id="0bef8-149">Список всех разрешенных имен угроз</span><span class="sxs-lookup"><span data-stu-id="0bef8-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="0bef8-150">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-150">Configuration</span></span>|<span data-ttu-id="0bef8-151">Включив защиту PUA</span><span class="sxs-lookup"><span data-stu-id="0bef8-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="0bef8-152">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-152">Configuration</span></span>|<span data-ttu-id="0bef8-153">Отключение защиты PUA</span><span class="sxs-lookup"><span data-stu-id="0bef8-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="0bef8-154">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-154">Configuration</span></span>|<span data-ttu-id="0bef8-155">Включим режим аудита для защиты PUA</span><span class="sxs-lookup"><span data-stu-id="0bef8-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="0bef8-156">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0bef8-156">Configuration</span></span>|<span data-ttu-id="0bef8-157">Включите/отключите passiveMode</span><span class="sxs-lookup"><span data-stu-id="0bef8-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="0bef8-158">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="0bef8-158">Diagnostics</span></span>  |<span data-ttu-id="0bef8-159">Изменение уровня журнала</span><span class="sxs-lookup"><span data-stu-id="0bef8-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="0bef8-160">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="0bef8-160">Diagnostics</span></span>  |<span data-ttu-id="0bef8-161">Создание журналов диагностики</span><span class="sxs-lookup"><span data-stu-id="0bef8-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="0bef8-162">Здравоохранение</span><span class="sxs-lookup"><span data-stu-id="0bef8-162">Health</span></span>       |<span data-ttu-id="0bef8-163">Проверка состояния продукта</span><span class="sxs-lookup"><span data-stu-id="0bef8-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="0bef8-164">Здравоохранение</span><span class="sxs-lookup"><span data-stu-id="0bef8-164">Health</span></span>       |<span data-ttu-id="0bef8-165">Проверка атрибута spefic product</span><span class="sxs-lookup"><span data-stu-id="0bef8-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="0bef8-166">Защита</span><span class="sxs-lookup"><span data-stu-id="0bef8-166">Protection</span></span>   |<span data-ttu-id="0bef8-167">Сканирование пути</span><span class="sxs-lookup"><span data-stu-id="0bef8-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="0bef8-168">Защита</span><span class="sxs-lookup"><span data-stu-id="0bef8-168">Protection</span></span>   |<span data-ttu-id="0bef8-169">Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="0bef8-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="0bef8-170">Защита</span><span class="sxs-lookup"><span data-stu-id="0bef8-170">Protection</span></span>   |<span data-ttu-id="0bef8-171">Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="0bef8-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="0bef8-172">Защита</span><span class="sxs-lookup"><span data-stu-id="0bef8-172">Protection</span></span>   |<span data-ttu-id="0bef8-173">Отмена текущего сканирования по запросу</span><span class="sxs-lookup"><span data-stu-id="0bef8-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="0bef8-174">Защита</span><span class="sxs-lookup"><span data-stu-id="0bef8-174">Protection</span></span>   |<span data-ttu-id="0bef8-175">Запрос обновления сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="0bef8-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="0bef8-176">EDR</span><span class="sxs-lookup"><span data-stu-id="0bef8-176">EDR</span></span>          |<span data-ttu-id="0bef8-177">Добавление тега группы на устройство.</span><span class="sxs-lookup"><span data-stu-id="0bef8-177">Add group tag to device.</span></span> <span data-ttu-id="0bef8-178">Теги EDR используются для управления группами устройств.</span><span class="sxs-lookup"><span data-stu-id="0bef8-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="0bef8-179">Дополнительные сведения можно получить на сайте https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="0bef8-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="0bef8-180">EDR</span><span class="sxs-lookup"><span data-stu-id="0bef8-180">EDR</span></span>          |<span data-ttu-id="0bef8-181">Удаление тега группы с устройства</span><span class="sxs-lookup"><span data-stu-id="0bef8-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="0bef8-182">EDR</span><span class="sxs-lookup"><span data-stu-id="0bef8-182">EDR</span></span>          |<span data-ttu-id="0bef8-183">Добавление группового ID</span><span class="sxs-lookup"><span data-stu-id="0bef8-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="0bef8-184">Как включить автозаполнение</span><span class="sxs-lookup"><span data-stu-id="0bef8-184">How to enable autocompletion</span></span>

<span data-ttu-id="0bef8-185">Чтобы включить автозаполнение в bash, запустите следующую команду и перезапустите сеанс Терминала:</span><span class="sxs-lookup"><span data-stu-id="0bef8-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="0bef8-186">Чтобы включить автозаполнение в zsh:</span><span class="sxs-lookup"><span data-stu-id="0bef8-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="0bef8-187">Проверьте, включена ли автокомплектация на устройстве:</span><span class="sxs-lookup"><span data-stu-id="0bef8-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="0bef8-188">Если в предыдущей команде не производится какой-либо выход, можно включить автозаполнение с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="0bef8-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="0bef8-189">Запустите следующие команды, чтобы включить автозаполнение для Microsoft Defender для конечной точки для Mac и перезапустить сеанс Терминала:</span><span class="sxs-lookup"><span data-stu-id="0bef8-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint for Mac and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="0bef8-190">Клиент Microsoft Defender для каталога карантина конечных точек</span><span class="sxs-lookup"><span data-stu-id="0bef8-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="0bef8-191">`/Library/Application Support/Microsoft/Defender/quarantine/` содержит файлы, которые находятся на `mdatp` карантине.</span><span class="sxs-lookup"><span data-stu-id="0bef8-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="0bef8-192">Файлы названы в честь отслеживания угроз.</span><span class="sxs-lookup"><span data-stu-id="0bef8-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="0bef8-193">Текущий trackingIds показан с `mdatp threat list` .</span><span class="sxs-lookup"><span data-stu-id="0bef8-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="0bef8-194">Сведения портала Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="0bef8-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="0bef8-195">[Возможности EDR](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)для macOS уже прибыли, в блоге Microsoft Defender for Endpoint, содержит подробные указания о том, чего ожидать в Центре безопасности конечных точек Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0bef8-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>