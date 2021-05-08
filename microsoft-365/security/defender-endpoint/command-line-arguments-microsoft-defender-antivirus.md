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
ms.date: 03/19/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 85fb60d8d4504ba3a4aa8744c1183d094da01a9b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274752"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Настройка и управление антивирусная программа в Microsoft Defender с помощью mpcmdrun.exe командной строки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Вы можете выполнять различные антивирусная программа в Microsoft Defender с помощью выделенного средства командной строки **mpcmdrun.exe.** Эта утилита полезна для автоматизации антивирусная программа в Microsoft Defender использования. Вы можете найти утилиту `%ProgramFiles%\Windows Defender\MpCmdRun.exe` в . Вы должны запустить его из командной подсказки.

> [!NOTE]
> Может потребоваться открыть версию командной подсказки на уровне администратора. При поиске **командной подсказки** в меню Пуск выберите **Выполнить в качестве администратора.**
> Если вы работаете с обновленной версией платформы Защитника Майкрософт, запустите ее из `**MpCmdRun**` следующего расположения: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .

Утилита имеет следующие команды:

```console
MpCmdRun.exe [command] [-options]
```
Пример:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| Команда  | Описание   |
|:----|:----|
| `-?`**или**`-h`   | Отображает все доступные параметры для этого средства |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Сканирование вредоносного программного обеспечения. Значения для **ScanType:** **0** По умолчанию, в соответствии с конфигурацией, **-1** Быстрое сканирование, **-2** Полное сканирование, **-3** Файл и пользовательский просмотр каталога.  CpuThrottling будет соблюдать регулирование настроенного ЦП из политики |
| `-Trace [-Grouping #] [-Level #]` | Начало отслеживания диагностики |
| `-GetFiles [-SupportLogLocation <path>]` | Собирает сведения о поддержке. Сведения о[сборе диагностических данных](collect-diagnostic-data.md)см. в  |
| `-GetFilesDiagTrack`  | То `-GetFiles` же, что и , но выводит во временную папку DiagTrack |
| `-RemoveDefinitions [-All]` | Восстановление установленного интеллекта безопасности в предыдущей копии резервного копирования или в исходном наборе по умолчанию |
| `-RemoveDefinitions [-DynamicSignatures]` | Удаляет только динамически загруженный интеллект безопасности |
| `-RemoveDefinitions [-Engine]` | Восстановление предыдущего установленного двигателя |
| `-SignatureUpdate [-UNC \| -MMPC]` | Проверка новых обновлений службы безопасности |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | Восстановление или перечисление на карантин элемента (ы) |
| `-AddDynamicSignature [-Path]` | Загружает динамический интеллект безопасности |
| `-ListAllDynamicSignatures` | Списки загруженной динамической разведки безопасности |
| `-RemoveDynamicSignature [-SignatureSetID]` | Удаляет динамический интеллект безопасности |
| `-CheckExclusion -path <path>` | Проверяет, исключен ли путь |
| `-ValidateMapsConnection` | Проверяет, может ли ваша сеть взаимодействовать с антивирусная программа в Microsoft Defender облачной службой. Эта команда будет работать только на Windows 10 версии 1703 или выше.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Распространенные ошибки при запуске команд через mpcmdrun.exe 

|Сообщение об ошибке | Возможная причина
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | Служба антивирусная программа в Microsoft Defender отключена. Включить службу и попробовать еще раз. <br>   **Примечание:**  В Windows 10 1909 и Windows Server 2019 или старше служба называлась "антивирусная программа ".|
| `0x80070667` | Вы работаете с командой с компьютера, который Windows 10 версии 1607 или старше или Windows Server 2016 `-ValidateMapsConnection` старше. Запустите команду с компьютера, Windows 10 версии 1703 или более новой, или Windows Server 2019 или более новой.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | Инструмент должен запускаться либо из: или (где может отличаться, так как обновления платформы `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` ежемесячно, за исключением марта)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | Не хватает привилегий. Используйте командную подсказку (cmd.exe) в качестве администратора.|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | Брандмауэр блокирует подключение или проводит проверку SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | Возможные проблемы, связанные с сетью, например проблемы с разрешением имен|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | Брандмауэр блокирует подключение или проводит проверку SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | Брандмауэр блокирует подключение или проводит проверку SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | Брандмауэр блокирует подключение или проводит проверку SSL. |

## <a name="see-also"></a>См. также

- [Настройка функций антивирусной программы в Microsoft Defender](configure-microsoft-defender-antivirus-features.md)
- [Управление антивирусная программа в Microsoft Defender бизнесом](configuration-management-reference-microsoft-defender-antivirus.md)
- [Справочные темы для средств управления и конфигурации](configuration-management-reference-microsoft-defender-antivirus.md)
- [антивирусная программа в Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)