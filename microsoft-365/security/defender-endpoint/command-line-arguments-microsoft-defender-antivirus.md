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
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 25f038846f9dd9855823382d4e1babcf0547fed6
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636174"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Настройка и управление антивирусная программа в Microsoft Defender с помощью mpcmdrun.exe командной строки

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Вы можете выполнять различные функции в антивирусная программа в Microsoft Defender с помощью выделенного средства командной строки **mpcmdrun.exe.** Эта утилита полезна для автоматизации антивирусная программа в Microsoft Defender задач. Вы можете найти утилиту `%ProgramFiles%\Windows Defender\MpCmdRun.exe` в . Запустите его из командной подсказки.

> [!TIP]
> Может потребоваться открыть версию командной подсказки на уровне администратора. При поиске **командной подсказки** в меню Пуск выберите **Выполнить в качестве администратора.** Если вы работаете с обновленной версией платформы Защитника Майкрософт, запустите ее из `MpCmdRun` следующего расположения: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` . Дополнительные сведения о платформе антивирусных программ см. в антивирусная программа в Microsoft Defender [обновления и базовые версии.](manage-updates-baselines-microsoft-defender-antivirus.md)

Утилита MpCmdRun использует следующий синтаксис:

```console
MpCmdRun.exe [command] [-options]
```

Пример:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

В нашем примере утилита MpCmdRun запускает полное антивирусное сканирование на устройстве.

## <a name="commands"></a>Команды

| Команда  | Описание   |
|:----|:----|
| `-?`**или**`-h`   | Отображает все доступные параметры для средства MpCmdRun |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Сканирование вредоносного программного обеспечения. Значения для **ScanType:**<p>**0** По умолчанию в соответствии с конфигурацией<p>**1 Быстрое** сканирование<p>**2** Полное сканирование<p>**3 Пользовательское** сканирование файлов и каталогов.<p>CpuThrottling выполняется в соответствии с конфигурациями политики |
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

В следующей таблице перечислены распространенные ошибки, которые могут возникать при использовании средства MpCmdRun.

|Сообщение об ошибке | Возможная причина |
|:----|:----|
| **Не удалось проверитьMapsConnection (800106BA)** **или 0x800106BA** | Служба антивирусная программа в Microsoft Defender отключена. Включить службу и попробовать еще раз. Если вам нужна помощь по повторному антивирусная программа в Microsoft Defender, см. в антивирусная программа в Microsoft Defender [reinstall/enable.](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)<p>   **TIP**  В Windows 10 1909 г. и старше Windows Server 2019 или старше служба ранее называлась *антивирусная программа .* |
| **0x80070667** | Вы работаете с командой с компьютера, который Windows 10 версии 1607 или старше или Windows Server 2016 `-ValidateMapsConnection` старше. Запустите команду с компьютера, Windows 10 версии 1703 или более новой, или Windows Server 2019 или более новой.|
| **MpCmdRun не распознается как внутренняя или внешняя команда, оперативная программа или пакетный файл.** | Средство должно запускаться либо из одного, либо из (где может отличаться, так как обновления платформы ежемесячно, за `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` исключением марта)|
| **ValidateMapsConnection не удалось установить подключение к MAPS (hr=800700005 httpcode=450)** | Команда была предпринята с использованием недостаточных привилегий. Используйте командную подсказку (cmd.exe) в качестве администратора.|
| **ValidateMapsConnection не удалось установить подключение к MAPS (hr=80070006 httpcode=451)** | Брандмауэр блокирует подключение или проводит проверку SSL. |
| **ValidateMapsConnection не удалось установить подключение к MAPS (hr=80004005 httpcode=450)** | Возможные проблемы, связанные с сетью, например проблемы с разрешением имен|
| **ПроверкаMapsConnection не удалось установить подключение к MAPS (hr=0x80508015** | Брандмауэр блокирует подключение или проводит проверку SSL. |
| **ПроверкаMapsConnection не удалось установить подключение к MAPS (hr=800722F0D** | Брандмауэр блокирует подключение или проводит проверку SSL. |
| **ValidateMapsConnection не удалось установить подключение к MAPS (hr=80072EE7 httpcode=451)** | Брандмауэр блокирует подключение или проводит проверку SSL. |

## <a name="see-also"></a>См. также

- [Настройка функций антивирусной программы в Microsoft Defender](configure-microsoft-defender-antivirus-features.md)
- [Настройка и проверка сетевого подключения антивирусной программы в Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md)
- [Справочные темы для средств управления и конфигурации](configuration-management-reference-microsoft-defender-antivirus.md)
