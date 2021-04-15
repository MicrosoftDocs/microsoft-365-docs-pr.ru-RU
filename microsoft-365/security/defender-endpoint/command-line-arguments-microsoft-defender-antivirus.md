---
title: Используйте командную строку для управления антивирусом Microsoft Defender
description: Запустите антивирусную проверку Microsoft Defender и настройте защиту следующего поколения с помощью специальной службы командной строки.
keywords: выполнить сканирование защитника Windows, выполнить антивирусное сканирование из командной строки, выполнить сканирование защитника windows из командной строки, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 1b357f7c1e02211f3949383a380666cb7444f814
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764631"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="3fd88-104">Настройка и управление антивирусом Microsoft Defender с помощью mpcmdrun.exe командной строки</span><span class="sxs-lookup"><span data-stu-id="3fd88-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3fd88-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3fd88-105">**Applies to:**</span></span>

- [<span data-ttu-id="3fd88-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3fd88-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3fd88-107">Вы можете выполнять различные антивирусные функции Microsoft Defender с помощью специального средства командной строки **mpcmdrun.exe.**</span><span class="sxs-lookup"><span data-stu-id="3fd88-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="3fd88-108">Эта утилита полезна, если необходимо автоматизировать использование антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3fd88-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="3fd88-109">Вы можете найти утилиту `%ProgramFiles%\Windows Defender\MpCmdRun.exe` в .</span><span class="sxs-lookup"><span data-stu-id="3fd88-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="3fd88-110">Вы должны запустить его из командной подсказки.</span><span class="sxs-lookup"><span data-stu-id="3fd88-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="3fd88-111">Может потребоваться открыть версию командной подсказки на уровне администратора.</span><span class="sxs-lookup"><span data-stu-id="3fd88-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="3fd88-112">При поиске **командной подсказки** в меню Пуск выберите **Выполнить в качестве администратора.**</span><span class="sxs-lookup"><span data-stu-id="3fd88-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="3fd88-113">Если вы работаете с обновленной версией платформы Защитника Майкрософт, запустите ее из `**MpCmdRun**` следующего расположения: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="3fd88-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="3fd88-114">Утилита имеет следующие команды:</span><span class="sxs-lookup"><span data-stu-id="3fd88-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="3fd88-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="3fd88-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="3fd88-116">Команда</span><span class="sxs-lookup"><span data-stu-id="3fd88-116">Command</span></span>  | <span data-ttu-id="3fd88-117">Описание</span><span class="sxs-lookup"><span data-stu-id="3fd88-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="3fd88-118">`-?` **или** `-h`</span><span class="sxs-lookup"><span data-stu-id="3fd88-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="3fd88-119">Отображает все доступные параметры для этого средства</span><span class="sxs-lookup"><span data-stu-id="3fd88-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="3fd88-120">Сканирование вредоносного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="3fd88-120">Scans for malicious software.</span></span> <span data-ttu-id="3fd88-121">Значения для **ScanType:** **0** По умолчанию, в соответствии с конфигурацией, **-1** Быстрое сканирование, **-2** Полное сканирование, **-3** Файл и пользовательский просмотр каталога.</span><span class="sxs-lookup"><span data-stu-id="3fd88-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="3fd88-122">CpuThrottling будет соблюдать регулирование настроенного ЦП из политики</span><span class="sxs-lookup"><span data-stu-id="3fd88-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="3fd88-123">Начало отслеживания диагностики</span><span class="sxs-lookup"><span data-stu-id="3fd88-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="3fd88-124">Собирает сведения о поддержке.</span><span class="sxs-lookup"><span data-stu-id="3fd88-124">Collects support information.</span></span> <span data-ttu-id="3fd88-125">Сведения о[сборе диагностических данных](collect-diagnostic-data.md)см. в</span><span class="sxs-lookup"><span data-stu-id="3fd88-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="3fd88-126">То `-GetFiles` же, что и , но выводит во временную папку DiagTrack</span><span class="sxs-lookup"><span data-stu-id="3fd88-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="3fd88-127">Восстановление установленного интеллекта безопасности в предыдущей копии резервного копирования или в исходном наборе по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3fd88-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="3fd88-128">Удаляет только динамически загруженный интеллект безопасности</span><span class="sxs-lookup"><span data-stu-id="3fd88-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="3fd88-129">Восстановление предыдущего установленного двигателя</span><span class="sxs-lookup"><span data-stu-id="3fd88-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="3fd88-130">Проверка новых обновлений службы безопасности</span><span class="sxs-lookup"><span data-stu-id="3fd88-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="3fd88-131">Восстановление или перечисление на карантин элемента (ы)</span><span class="sxs-lookup"><span data-stu-id="3fd88-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="3fd88-132">Загружает динамический интеллект безопасности</span><span class="sxs-lookup"><span data-stu-id="3fd88-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="3fd88-133">Списки загруженной динамической разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="3fd88-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="3fd88-134">Удаляет динамический интеллект безопасности</span><span class="sxs-lookup"><span data-stu-id="3fd88-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="3fd88-135">Проверяет, исключен ли путь</span><span class="sxs-lookup"><span data-stu-id="3fd88-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="3fd88-136">Проверяет, может ли ваша сеть взаимодействовать с облачной службой антивирусной программы Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3fd88-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="3fd88-137">Эта команда будет работать только в Windows 10, версии 1703 или выше.</span><span class="sxs-lookup"><span data-stu-id="3fd88-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="3fd88-138">Распространенные ошибки при запуске команд через mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="3fd88-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="3fd88-139">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="3fd88-139">Error message</span></span> | <span data-ttu-id="3fd88-140">Возможная причина</span><span class="sxs-lookup"><span data-stu-id="3fd88-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="3fd88-141">Антивирусная служба Microsoft Defender отключена.</span><span class="sxs-lookup"><span data-stu-id="3fd88-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="3fd88-142">Включить службу и попробовать еще раз.</span><span class="sxs-lookup"><span data-stu-id="3fd88-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="3fd88-143">**Примечание:**  В Windows 10 1909 или старше и Windows Server 2019 или старше служба называлась "Защитник Windows антивируса".</span><span class="sxs-lookup"><span data-stu-id="3fd88-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="3fd88-144">Вы работаете с командой с компьютера windows `-ValidateMapsConnection` 10 версии 1607 или старше или Windows Server 2016 или старше.</span><span class="sxs-lookup"><span data-stu-id="3fd88-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="3fd88-145">Запустите команду с компьютера с Windows 10 версии 1703 или более новой версии, или Windows Server 2019 или более новой.</span><span class="sxs-lookup"><span data-stu-id="3fd88-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="3fd88-146">Инструмент должен запускаться либо из: или (где может отличаться, так как обновления платформы `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` ежемесячно, за исключением марта)</span><span class="sxs-lookup"><span data-stu-id="3fd88-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="3fd88-147">Не хватает привилегий.</span><span class="sxs-lookup"><span data-stu-id="3fd88-147">Not enough privileges.</span></span> <span data-ttu-id="3fd88-148">Используйте командную подсказку (cmd.exe) в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="3fd88-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="3fd88-149">Брандмауэр блокирует подключение или проводит проверку SSL.</span><span class="sxs-lookup"><span data-stu-id="3fd88-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="3fd88-150">Возможные проблемы, связанные с сетью, например проблемы с разрешением имен</span><span class="sxs-lookup"><span data-stu-id="3fd88-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="3fd88-151">Брандмауэр блокирует подключение или проводит проверку SSL.</span><span class="sxs-lookup"><span data-stu-id="3fd88-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="3fd88-152">Брандмауэр блокирует подключение или проводит проверку SSL.</span><span class="sxs-lookup"><span data-stu-id="3fd88-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="3fd88-153">Брандмауэр блокирует подключение или проводит проверку SSL.</span><span class="sxs-lookup"><span data-stu-id="3fd88-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3fd88-154">См. также</span><span class="sxs-lookup"><span data-stu-id="3fd88-154">See also</span></span>

- [<span data-ttu-id="3fd88-155">Настройка функций антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3fd88-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="3fd88-156">Управление антивирусом Microsoft Defender в вашем бизнесе</span><span class="sxs-lookup"><span data-stu-id="3fd88-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3fd88-157">Справочные темы для средств управления и конфигурации</span><span class="sxs-lookup"><span data-stu-id="3fd88-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3fd88-158">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="3fd88-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)