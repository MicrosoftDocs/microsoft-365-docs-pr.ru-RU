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
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Настройка и управление антивирусом Microsoft Defender с помощью mpcmdrun.exe командной строки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Вы можете выполнять различные антивирусные функции Microsoft Defender с помощью специального средства командной строки **mpcmdrun.exe.** Эта утилита полезна, если необходимо автоматизировать использование антивируса Microsoft Defender. Вы можете найти утилиту `%ProgramFiles%\Windows Defender\MpCmdRun.exe` в . Вы должны запустить его из командной подсказки.

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
| `-?` **или** `-h`   | Отображает все доступные параметры для этого средства |
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
| `-ValidateMapsConnection` | Проверяет, может ли ваша сеть взаимодействовать с облачной службой антивирусной программы Microsoft Defender. Эта команда будет работать только в Windows 10, версии 1703 или выше.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Распространенные ошибки при запуске команд через mpcmdrun.exe 

|Сообщение об ошибке | Возможная причина
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | Антивирусная служба Microsoft Defender отключена. Включить службу и попробовать еще раз. <br>   **Примечание:**  В Windows 10 1909 или старше и Windows Server 2019 или старше служба называлась "Защитник Windows антивируса".|
| `0x80070667` | Вы работаете с командой с компьютера windows `-ValidateMapsConnection` 10 версии 1607 или старше или Windows Server 2016 или старше. Запустите команду с компьютера с Windows 10 версии 1703 или более новой версии, или Windows Server 2019 или более новой.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | Инструмент должен запускаться либо из: или (где может отличаться, так как обновления платформы `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` ежемесячно, за исключением марта)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | Не хватает привилегий. Используйте командную подсказку (cmd.exe) в качестве администратора.|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | Брандмауэр блокирует подключение или проводит проверку SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | Возможные проблемы, связанные с сетью, например проблемы с разрешением имен|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | Брандмауэр блокирует подключение или проводит проверку SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | Брандмауэр блокирует подключение или проводит проверку SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | Брандмауэр блокирует подключение или проводит проверку SSL. |

## <a name="see-also"></a>См. также

- [Настройка функций антивирусной программы в Microsoft Defender](configure-microsoft-defender-antivirus-features.md)
- [Управление антивирусом Microsoft Defender в вашем бизнесе](configuration-management-reference-microsoft-defender-antivirus.md)
- [Справочные темы для средств управления и конфигурации](configuration-management-reference-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)