---
title: Используйте командную строку для управления антивирусная программа в Microsoft Defender
description: Выполнить антивирусная программа в Microsoft Defender проверки и настроить защиту следующего поколения с помощью специальной командной строки.
keywords: выполнить сканирование защитника Windows, выполнить антивирусное сканирование из командной строки, выполнить сканирование защитника windows из командной строки, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538907"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="4fdb2-104">Настройка и управление антивирусная программа в Microsoft Defender с помощью mpcmdrun.exe командной строки</span><span class="sxs-lookup"><span data-stu-id="4fdb2-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="4fdb2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4fdb2-105">**Applies to:**</span></span>

- [<span data-ttu-id="4fdb2-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4fdb2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4fdb2-107">Вы можете выполнять различные антивирусная программа в Microsoft Defender с помощью выделенного средства командной строки **mpcmdrun.exe.**</span><span class="sxs-lookup"><span data-stu-id="4fdb2-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="4fdb2-108">Эта утилита полезна для автоматизации антивирусная программа в Microsoft Defender использования.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="4fdb2-109">Вы можете найти утилиту `%ProgramFiles%\Windows Defender\MpCmdRun.exe` в .</span><span class="sxs-lookup"><span data-stu-id="4fdb2-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="4fdb2-110">Вы должны запустить его из командной подсказки.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="4fdb2-111">Может потребоваться открыть версию командной подсказки на уровне администратора.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="4fdb2-112">При поиске **командной подсказки** в меню Пуск выберите **Выполнить в качестве администратора.**</span><span class="sxs-lookup"><span data-stu-id="4fdb2-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="4fdb2-113">Если вы работаете с обновленной версией платформы Защитника Майкрософт, запустите ее из `**MpCmdRun**` следующего расположения: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` .</span><span class="sxs-lookup"><span data-stu-id="4fdb2-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span>
> <span data-ttu-id="4fdb2-114">Дополнительные сведения о платформе антивирусных программ см. в антивирусная программа в Microsoft Defender [обновления и базовые версии.](manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4fdb2-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="4fdb2-115">Утилита MpCmdRun использует следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4fdb2-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="4fdb2-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="4fdb2-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="4fdb2-117">Команда</span><span class="sxs-lookup"><span data-stu-id="4fdb2-117">Command</span></span>  | <span data-ttu-id="4fdb2-118">Описание</span><span class="sxs-lookup"><span data-stu-id="4fdb2-118">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="4fdb2-119">`-?`**или**`-h`</span><span class="sxs-lookup"><span data-stu-id="4fdb2-119">`-?` **or** `-h`</span></span>   | <span data-ttu-id="4fdb2-120">Отображает все доступные параметры для этого средства</span><span class="sxs-lookup"><span data-stu-id="4fdb2-120">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="4fdb2-121">Сканирование вредоносного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-121">Scans for malicious software.</span></span> <span data-ttu-id="4fdb2-122">Значения для **ScanType:**</span><span class="sxs-lookup"><span data-stu-id="4fdb2-122">Values for **ScanType** are:</span></span><p><span data-ttu-id="4fdb2-123">**0** По умолчанию в соответствии с конфигурацией</span><span class="sxs-lookup"><span data-stu-id="4fdb2-123">**0** Default, according to your configuration</span></span><p><span data-ttu-id="4fdb2-124">**-1** Быстрое сканирование</span><span class="sxs-lookup"><span data-stu-id="4fdb2-124">**-1** Quick scan</span></span><p><span data-ttu-id="4fdb2-125">**-2** Полное сканирование</span><span class="sxs-lookup"><span data-stu-id="4fdb2-125">**-2** Full scan</span></span><p><span data-ttu-id="4fdb2-126">**-3** Настраиваемая проверка файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-126">**-3** File and directory custom scan.</span></span><p><span data-ttu-id="4fdb2-127">CpuThrottling будет соблюдать регулирование настроенного ЦП из политики</span><span class="sxs-lookup"><span data-stu-id="4fdb2-127">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="4fdb2-128">Начало отслеживания диагностики</span><span class="sxs-lookup"><span data-stu-id="4fdb2-128">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="4fdb2-129">Собирает сведения о поддержке.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-129">Collects support information.</span></span> <span data-ttu-id="4fdb2-130">Сведения о[сборе диагностических данных](collect-diagnostic-data.md)см. в</span><span class="sxs-lookup"><span data-stu-id="4fdb2-130">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="4fdb2-131">То `-GetFiles` же, что и , но выводит во временную папку DiagTrack</span><span class="sxs-lookup"><span data-stu-id="4fdb2-131">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="4fdb2-132">Восстановление установленного интеллекта безопасности в предыдущей копии резервного копирования или в исходном наборе по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4fdb2-132">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="4fdb2-133">Удаляет только динамически загруженный интеллект безопасности</span><span class="sxs-lookup"><span data-stu-id="4fdb2-133">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="4fdb2-134">Восстановление предыдущего установленного двигателя</span><span class="sxs-lookup"><span data-stu-id="4fdb2-134">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="4fdb2-135">Проверка новых обновлений службы безопасности</span><span class="sxs-lookup"><span data-stu-id="4fdb2-135">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="4fdb2-136">Восстановление или перечисление на карантин элемента (ы)</span><span class="sxs-lookup"><span data-stu-id="4fdb2-136">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="4fdb2-137">Загружает динамический интеллект безопасности</span><span class="sxs-lookup"><span data-stu-id="4fdb2-137">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="4fdb2-138">Списки загруженной динамической разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="4fdb2-138">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="4fdb2-139">Удаляет динамический интеллект безопасности</span><span class="sxs-lookup"><span data-stu-id="4fdb2-139">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="4fdb2-140">Проверяет, исключен ли путь</span><span class="sxs-lookup"><span data-stu-id="4fdb2-140">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="4fdb2-141">Проверяет, может ли ваша сеть взаимодействовать с антивирусная программа в Microsoft Defender облачной службой.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-141">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="4fdb2-142">Эта команда будет работать только на Windows 10 версии 1703 или выше.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-142">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="4fdb2-143">Распространенные ошибки при запуске команд через mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="4fdb2-143">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="4fdb2-144">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="4fdb2-144">Error message</span></span> | <span data-ttu-id="4fdb2-145">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="4fdb2-145">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="4fdb2-146">Служба антивирусная программа в Microsoft Defender отключена.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-146">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="4fdb2-147">Включить службу и попробовать еще раз.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-147">Enable the service and try again.</span></span> <br>   <span data-ttu-id="4fdb2-148">**Примечание:**  В Windows 10 1909 и Windows Server 2019 или старше служба называлась службой *антивирусная программа .*</span><span class="sxs-lookup"><span data-stu-id="4fdb2-148">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called the *Windows Defender Antivirus* service.</span></span>|
| `0x80070667` | <span data-ttu-id="4fdb2-149">Вы работаете с командой с компьютера, который Windows 10 версии 1607 или старше или Windows Server 2016 `-ValidateMapsConnection` старше.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-149">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="4fdb2-150">Запустите команду с компьютера, Windows 10 версии 1703 или более новой, или Windows Server 2019 или более новой.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-150">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="4fdb2-151">Инструмент должен запускаться либо из: или (где может отличаться, так как обновления платформы `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` ежемесячно, за исключением марта)</span><span class="sxs-lookup"><span data-stu-id="4fdb2-151">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="4fdb2-152">Не хватает привилегий.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-152">Not enough privileges.</span></span> <span data-ttu-id="4fdb2-153">Используйте командную подсказку (cmd.exe) в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-153">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="4fdb2-154">Брандмауэр блокирует подключение или проводит проверку SSL.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-154">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="4fdb2-155">Возможные проблемы, связанные с сетью, например проблемы с разрешением имен</span><span class="sxs-lookup"><span data-stu-id="4fdb2-155">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="4fdb2-156">Брандмауэр блокирует подключение или проводит проверку SSL.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-156">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="4fdb2-157">Брандмауэр блокирует подключение или проводит проверку SSL.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-157">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="4fdb2-158">Брандмауэр блокирует подключение или проводит проверку SSL.</span><span class="sxs-lookup"><span data-stu-id="4fdb2-158">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4fdb2-159">См. также</span><span class="sxs-lookup"><span data-stu-id="4fdb2-159">See also</span></span>

- [<span data-ttu-id="4fdb2-160">Настройка функций антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4fdb2-160">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="4fdb2-161">Управление антивирусная программа в Microsoft Defender бизнесом</span><span class="sxs-lookup"><span data-stu-id="4fdb2-161">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4fdb2-162">Справочные темы для средств управления и конфигурации</span><span class="sxs-lookup"><span data-stu-id="4fdb2-162">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4fdb2-163">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="4fdb2-163">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)