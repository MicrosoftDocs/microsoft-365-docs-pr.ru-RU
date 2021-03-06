---
title: Настройка исключений для файлов, открытых определенными процессами
description: Вы можете исключить файлы из сканирования, если они были открыты определенным процессом.
keywords: антивирусная программа в Microsoft Defender, процесс, исключение, файлы, проверки
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 0470f4f03ba5fd6fc768a1e652f51b8c44207107
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925559"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>Настройка исключений для файлов, открытых процессами


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Можно исключить файлы, открытые определенными процессами, из антивирусная программа в Microsoft Defender проверки. См. [Рекомендации для определения исключений](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) перед определением списков исключений.

В этой статье описывается настройка списков исключений. 

## <a name="examples-of-exclusions"></a>Примеры исключений

|Исключения | Пример |
|---|---|
|Любой файл на компьютере, открываемом любым процессом с определенным именем файла | При `test.exe` указании исключены файлы, открытые по: <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|Любой файл на компьютере, открываемом любым процессом в определенной папке | При `c:\test\sample\*` указании исключены файлы, открытые по:<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|Любой файл на компьютере, открытый определенным процессом в определенной папке | Указание `c:\test\process.exe` исключит файлы, открытые только `c:\test\process.exe` |


При добавлении процесса в список исключений процесса антивирусная программа в Microsoft Defender файлы, открытые этим процессом, независимо от того, где находятся файлы. Однако сам процесс будет отсканирован, если он не будет добавлен в список [исключений файлов.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

Исключения применяются только к защите и мониторингу в режиме реального времени в [режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md) Они не применяются к запланированным проверкам или проверкам по запросу.

Изменения, внесенные с групповой политикой в списки исключений, будут показываться в списках в [Безопасность Windows приложении.](microsoft-defender-security-center-antivirus.md)  Однако изменения, внесенные в Безопасность Windows, **не будут указаны** в списках групповой политики.

Можно добавить, удалить и просмотреть списки исключений в групповой политике, Microsoft Endpoint Configuration Manager, Microsoft Intune и в приложении Безопасность Windows, а также использовать подгруппы для дальнейшей настройки списков.

Для настройки списков исключений, включая просмотр списков, можно также использовать cmdlets PowerShell и WMI.

По умолчанию локальные изменения, внесенные в списки (пользователями с привилегиями администратора; изменения, внесенные с PowerShell и WMI), будут объединены со списками в качестве определенных (и развернутых) групповой политикой, диспетчером конфигурации или Intune. Списки групповой политики будут иметь приоритет в случае конфликтов.

Можно настроить [слияние](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) локальных и глобальных списков исключений, чтобы разрешить локальным изменениям переопределять параметры управляемого развертывания.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>Настройка списка исключений для файлов, открытых указанными процессами

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Используйте Microsoft Intune, чтобы исключить файлы, открытые указанными процессами, из сканов

Дополнительные сведения см. в статьях [Настройка параметров ограничения устройств в Microsoft Intune](/intune/device-restrictions-configure) и [Параметры ограничений устройств антивирусной программы в Microsoft Defender для Windows 10 в Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Используйте Microsoft Endpoint Manager, чтобы исключить файлы, открытые указанными процессами, из сканирований

Сведения [о настройке](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) Microsoft Endpoint Manager (текущая ветвь) см. в материале "Создание и развертывание политик противомалярийных программ: параметры исключения".

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Использование групповой политики для исключения файлов, открытых указанными процессами из сканов

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.

3. Расширь **дерево до Windows компонентов > антивирусная программа в Microsoft Defender > исключений.**

4. Дважды **щелкните исключения процесса** и добавьте исключения:

    1. Установите параметр **Включено**.
    2. В разделе **Параметры** щелкните **Показать...**.
    3. Введите каждый процесс по своей строке в столбце **Имя значения.** В примере см. таблицу различных типов исключений процессов.  Введите **0** в **столбце Значение** для всех процессов.

5. Нажмите кнопку **ОК**.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Чтобы исключить файлы, открытые указанными процессами, из сканов используйте cmdlets PowerShell

Использование PowerShell для добавления или удаления исключений для файлов, открытых процессами, требует сочетания трех cmdlets с `-ExclusionProcess` параметром. Все командлеты находятся в модуле [Defender.](/powershell/module/defender/)

Формат для cmdlets:

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

Разрешено \<cmdlet> следующее:

|Действие конфигурации | Cmdlet PowerShell |
|---|---|
|Создание или переописывание списка | `Set-MpPreference` |
|Добавление в список | `Add-MpPreference` |
|Удаление элементов из списка | `Remove-MpPreference` |

>[!IMPORTANT]
>Если вы создали список, с помощью или с помощью `Set-MpPreference` `Add-MpPreference` cmdlet снова `Set-MpPreference` переопишет существующий список.

Например, следующий фрагмент кода приведет к тому, что сканы av Microsoft Defender исключают любой файл, открытый указанным процессом:

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Дополнительные сведения о том, как использовать PowerShell с антивирусная программа в Microsoft Defender, см. в рублях Управление антивирусными программами с помощью cmdlets и [антивирусная программа в Microsoft Defender](/powershell/module/defender)PowerShell.

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Используйте Windows управления (WMI), чтобы исключить файлы, открытые указанными процессами, из сканирований

Используйте [ **методы Set,** **Add** и **Remove** **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) класса для следующих свойств:

```WMI
ExclusionProcess
```

Использование **набора,** **добавления** и  удаления аналогично их аналогам в PowerShell: `Set-MpPreference` , и `Add-MpPreference` `Remove-MpPreference` .

Дополнительные сведения и разрешенные параметры см. в Защитник Windows [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Используйте приложение Безопасность Windows, чтобы исключить файлы, открытые указанными процессами, из сканирования

Дополнительные [исключения см. в Безопасность Windows для](microsoft-defender-security-center-antivirus.md) инструкций.

## <a name="use-wildcards-in-the-process-exclusion-list"></a>Использование подкардов в списке исключений процесса

Использование подкардов в списке исключений процессов отличается от использования в других списках исключений.

В частности, нельзя использовать знак вопроса () подкард, а подпольную звездочку () можно использовать только в конце `?` `*` полного пути. При определении элементов в списке исключений процесса можно использовать переменные среды (например) в качестве `%ALLUSERSPROFILE%` поддиальдов.

В следующей таблице описывается, как можно использовать подкарды в списке исключений процесса:

|Подстановочный знак | Пример использования | Примеры совпадений |
|:---|:---|:---|
|`*` (звездочка) <br/><br/> Заменяет любое количество символов | `C:\MyData\*` | Любой файл, открытый `C:\MyData\file.exe` |
|Переменные среды <br/><br/> Заопределенная переменная заполняется как путь при оценке исключения | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | Любой файл, открытый `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>Просмотр списка исключений

Элементы из списка исключений можно получить с помощью MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure) [или приложения Безопасность Windows.](microsoft-defender-security-center-antivirus.md)

Если вы используете PowerShell, вы можете получить список двумя способами:

- Извлечение состояния всех антивирусная программа в Microsoft Defender личных предпочтений. Каждый из списков будет отображаться по отдельным строкам, но элементы в каждом списке будут объединены в ту же строку.
- Напишите состояние всех предпочтений переменной и используйте эту переменную для вызова только заинтересованного списка. Каждое использование `Add-MpPreference` записано на новую строку.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Проверка списка исключений с помощью MpCmdRun

Чтобы проверить исключения с помощью выделенного средства [командной строки ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)mpcmdrun.exe, используйте следующую команду:

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> Проверка исключений с помощью MpCmdRun антивирусная программа в Microsoft Defender camp версии 4.18.1812.3 (выпущена в декабре 2018 г.) или более поздней версии.


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Просмотрите список исключений вместе со всеми другими антивирусная программа в Microsoft Defender с помощью PowerShell

Используйте следующий cmdlet:

```PowerShell
Get-MpPreference
```

Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender).

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Извлечение определенного списка исключений с помощью PowerShell

Используйте следующий фрагмент кода (введите каждую строку в качестве отдельной команды); замените **WDAVprefs** любой меткой, которая будет называться переменной:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender).

## <a name="related-articles"></a>Связанные статьи

- [Настройка и проверка исключений в антивирусная программа в Microsoft Defender сканирования](configure-exclusions-microsoft-defender-antivirus.md)
- [Настройка и проверка исключений на основе имени, расширения и расположения папки](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Настройка антивирусная программа в Microsoft Defender исключений на Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Распространенные ошибки, которых следует избегать при определении исключений](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Настройка, инициирование и проверка результатов антивирусная программа в Microsoft Defender и исправлений](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
