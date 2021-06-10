---
title: Настройка и проверка исключений на основе расширения, имени или расположения
description: Исключить файлы из антивирусная программа в Microsoft Defender на основе расширения файла, имени файла или расположения.
keywords: исключения, файлы, расширение, тип файла, имя папки, имя файла, сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 3d65275d504ece4ac298558e660fa70c32a76d06
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274536"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>Настройка и проверка исключений в зависимости от расположения расширения файлов и папок

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> антивирусная программа в Microsoft Defender исключений не применяются к другим возможностям Microsoft Defender для конечных точек, в том числе обнаружение и нейтрализация атак на конечные точки [(EDR),](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)правилам уменьшения поверхности атаки [(ASR)](/microsoft-365/security/defender-endpoint/attack-surface-reduction)и управляемому доступу к папкам. [](/microsoft-365/security/defender-endpoint/controlled-folders) Файлы, исключаемые с помощью методов, описанных в этой статье, по-прежнему могут вызывать EDR оповещения и другие обнаружения. Чтобы исключить файлы в широком масштабе, добавьте их в настраиваемые индикаторы Microsoft Defender для [конечных точек.](/microsoft-365/security/defender-endpoint/manage-indicators)

## <a name="exclusion-lists"></a>Списки исключений

Некоторые файлы можно исключить из антивирусная программа в Microsoft Defender, изменяя списки исключений. **Как правило, вам не нужно** применять исключения . антивирусная программа в Microsoft Defender включает множество автоматических исключений, основанных на известных действиях операционной системы и типичных файлах управления, например используемых в управлении предприятиями, управлении базами данных и других корпоративных сценариях и ситуациях.

> [!NOTE]
> Исключения применяются и к обнаружениям потенциально нежелательных приложений (PUA).

> [!NOTE]
> Автоматические исключения применяются только к Windows Server 2016 и выше. Эти исключения не видны в приложении Безопасность Windows и в PowerShell.

В этой статье описывается настройка списков исключений для файлов и папок. См. [Рекомендации для определения исключений](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) перед определением списков исключений.

| Исключения | Примеры | Список исключений |
|:---|:---|:---|
|Любой файл с определенным расширением | Все файлы с указанным расширением в любом месте на компьютере. <p> Допустимый синтаксис: `.test` и `test`  | Исключения расширения |
|Любой файл в определенной папке | Все файлы в `c:\test\sample` папке | Исключения файлов и папок |
| Определенный файл в определенной папке | Только `c:\sample\sample.test` файл | Исключения файлов и папок |
| Определенный процесс | Исполняемый файл `c:\test\process.exe` | Исключения файлов и папок |

Списки исключений имеют следующие характеристики:

- Исключения папок применяются к всем файлам и папочкам в этой папке, если подмостки не является точкой репара. Раздельные подмостки точки репаража должны быть исключены отдельно.
- Расширения файлов применяются к любому имени файла с определенным расширением, если путь или папка не определены.

> [!IMPORTANT]
> - Использование подкардов, таких как звездочка ( ) изменит интерпретировать правила \* исключения. Сведения о [том,](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) как работают подкарды, см. в разделе Использование подкардов в пути имени файла и пути к папке или в разделе списки исключений расширения.
> - Нельзя исключать отметь сетевые диски. Необходимо указать фактический сетевой путь.
> - Папки, которые являются точками репаража, созданными после антивирусная программа в Microsoft Defender службы и добавленными в список исключений, не будут включены. Необходимо перезапустить службу (перезапустив Windows), чтобы новые точки репаража были признаны допустимой целью исключения.

Чтобы исключить файлы, открытые определенным процессом, см. в руб. Настройка и проверка исключений для файлов, [открытых процессами.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

Исключения применяются к [запланированным](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [проверкам,](run-scan-microsoft-defender-antivirus.md)проверкам по запросу и защите [в режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Изменения списка исключений, внесенные с помощью групповой **политики,** будут показываться в списках в [Безопасность Windows приложении.](microsoft-defender-security-center-antivirus.md)
> Изменения, внесенные в **Безопасность Windows, не будут показываться** в списках групповой политики.

По умолчанию локальные изменения, внесенные в списки (пользователями с привилегиями администратора, включая изменения, внесенные с PowerShell и WMI), будут объединены со списками в качестве определенных (и развернутых) групповой политикой, диспетчером конфигурации или Intune. Списки групповой политики имеют приоритет при конфликте.

Можно настроить [слияние](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) локальных и глобальных списков исключений, чтобы разрешить локальным изменениям переопределять параметры управляемого развертывания.

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>Настройка списка исключений на основе имени папки или расширения файла

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>Используйте Intune для настройки исключений из расширения файла, имени файла, папки или расширения файлов

См. следующие статьи:
- [Настройка параметров ограничения устройств в Microsoft Intune](/intune/device-restrictions-configure)
- [антивирусная программа в Microsoft Defender параметров ограничения устройств для Windows 10 в Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>Использование Диспетчер конфигурации для настройки исключений из расширения файлов, имени, папки или файла

Сведения [о настройке](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) Microsoft Endpoint Manager (текущая ветвь) см. в материале "Создание и развертывание политик противомалярийных программ: параметры исключения".

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>Использование групповой политики для настройки исключений папок или расширений файлов

>[!NOTE]
>Если вы указываете полностью квалифицированный путь к файлу, то исключается только этот файл. Если папка определена в исключении, все файлы и подтеки в этой папке исключены.

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**

3. Расширь **дерево до Windows компонентов**  >  **антивирусная программа в Microsoft Defender**  >  **исключений.**

4. Откройте параметр **"Исключения пути"** для редактирования и добавьте исключения.

    1. Установите параметр **Включено**.
    1. В разделе **Параметры** нажмите **кнопку Показать**.
    1. Укажите каждую папку по своей строке в столбце **Имя значения.**
    1. Если вы указываете файл, убедитесь, что вы введите полностью квалифицированный путь к файлу, включая письмо диска, путь папки, имя файла и расширение. Введите **0** в **столбце Значение.**

5. Нажмите кнопку **OK**.

6. Откройте параметр **Исключения расширения для** редактирования и добавьте исключения.

    1. Установите параметр **Включено**.
    1. В разделе **Параметры** выберите **Показать**.
    1. Введите каждое расширение файла по своей строке в столбце **Имя значения.**  Введите **0** в **столбце Значение.**

7. Нажмите кнопку **OK**.

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>Использование cmdlets PowerShell для настройки исключений из расширения файла, имени файла, папки или расширения файлов

Использование PowerShell для добавления или удаления исключений для файлов на основе расширения, расположения или имени файла требует сочетания трех cmdlets и соответствующего параметра списка исключений. Все командлеты находятся в модуле [Defender.](/powershell/module/defender/)

Формат для cmdlets следующим образом:

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

Разрешено `<cmdlet>` следующее:

| Действие конфигурации | Cmdlet PowerShell |
|:---|:---|
|Создание или переописывание списка | `Set-MpPreference` |
|Добавление в список | `Add-MpPreference` |
|Удаление элемента из списка | `Remove-MpPreference` |

Разрешено `<exclusion list>` следующее:

| Тип исключения | Параметр PowerShell |
|:---|:---|
| Все файлы с указанным расширением файла | `-ExclusionExtension` |
| Все файлы в папке (включая файлы в подуправлениях) или определенный файл | `-ExclusionPath` |

> [!IMPORTANT]
> Если вы создали список, с помощью или с помощью `Set-MpPreference` `Add-MpPreference` cmdlet снова `Set-MpPreference` переопишет существующий список.

Например, следующий фрагмент кода приведет к антивирусная программа в Microsoft Defender, чтобы исключить любой файл с `.test` расширением файла:

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>Используйте Windows управления (WMI) для настройки исключений из файла, папок или расширений файлов

Используйте [ **методы Set,** **Add** и **Remove** **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) класса для следующих свойств:

```WMI
ExclusionExtension
ExclusionPath
```

Использование **набора,** **добавления** и  удаления аналогично их аналогам в PowerShell: `Set-MpPreference` , и `Add-MpPreference` `Remove-MpPreference` .

Дополнительные сведения см. [в Защитник Windows API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>Используйте приложение Безопасность Windows для настройки исключений из расширения файла, имени файла, папки или расширения файлов

Дополнительные [исключения см. в Безопасность Windows для](microsoft-defender-security-center-antivirus.md) инструкций.

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Использование подмастерьев в пути имени файла и пути папок или списках исключений расширения

Вы можете использовать звездочки, знак вопросов или переменные среды (например) в качестве подкардов при определении элементов в списке исключения пути к файлу или `*` `?` имени `%ALLUSERSPROFILE%` папки. Способ интерпретации этих подкардов отличается от обычного использования в других приложениях и языках. Ознакомьтесь с этим разделом, чтобы понять их определенные ограничения.

> [!IMPORTANT]
> Существуют основные ограничения и сценарии использования для этих подкардов:
> - Использование переменной среды ограничено переменными машин и теми, которые применимы к процессам, запущенным в качестве учетной записи NT AUTHORITY\SYSTEM.
> - Нельзя использовать под диктовую карточку на месте буквы диска.
> - Звездочка в `*` исключении папки стоит на месте для одной папки. Используйте несколько экземпляров, чтобы указать несколько вложенных `\*\` папок с неустановленными именами.

В следующей таблице описывается, как можно использовать поддиальды, и приводится несколько примеров.


|Подстановочный знак  |Примеры  |
|:---------|:---------|
|`*` (звездочка) <p> В **включениях** имен файлов и расширений файлов звездочка заменяет любое количество символов и применяется только к файлам в последней папке, определенной в аргументе. <p> В **исключениях папок** звездочка заменяет одну папку. Используйте несколько `*` со срезами папок, `\` чтобы указать несколько вложенных папок. После совпадения числа папок с wild carded и именными именами все подмостки также включаются.   | `C:\MyData\*.txt` включает в себя `C:\MyData\notes.txt` <p> `C:\somepath\*\Data` включает в себя любой файл `C:\somepath\Archives\Data` и его подмостки, `C:\somepath\Authorized\Data` а также подмостки <p> `C:\Serv\*\*\Backup` включает в себя любой файл, `C:\Serv\Primary\Denied\Backup` его подмостки и `C:\Serv\Secondary\Allowed\Backup` подмостки     |
|`?` (знак вопроса)  <p> В **включениях имен** файлов и расширений файлов знак вопроса заменяет один символ и применяется только к файлам в последней папке, определенной в аргументе. <p> В **исключениях папок** знак вопроса заменяет один символ в имени папки. После совпадения числа папок с wild carded и именными именами все подмостки также включаются.   |`C:\MyData\my?.zip` включает в себя `C:\MyData\my1.zip` <p> `C:\somepath\?\Data` включает любой файл и `C:\somepath\P\Data` его подмостки  <p> `C:\somepath\test0?\Data` включит любой файл `C:\somepath\test01\Data` и его подмостки          |
|Переменные среды <p> Определяемая переменная заполняется как путь при оценке исключения.          |`%ALLUSERSPROFILE%\CustomLogFiles` будет включать в себя `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`         |
        

> [!IMPORTANT]
> Если смешать аргумент исключения файлов с аргументом исключения папок, правила будут останавливаться на совпадении аргументов файлов в подгруппах и не будут искать совпадения файлов в подмостках.
> Например, можно исключить все файлы, которые начинаются с "даты" в папках и `c:\data\final\marked` `c:\data\review\marked` с помощью аргумента правила `c:\data\*\marked\date*` .
> Этот аргумент, однако, не будет соответствовать любым файлам в подмостки под `c:\data\final\marked` или `c:\data\review\marked` .

<a id="review"></a>

### <a name="system-environment-variables"></a>Переменные системной среды

В следующей таблице перечислены и описываются переменные среды учетной записи системы. 

| Эта переменная среды системы... | Перенаправление на это |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | C:\ProgramData\Start Menu\Programs |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a>Просмотр списка исключений

Элементы из списка исключений можно получить с помощью одного из следующих методов:
- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- MpCmdRun
- PowerShell
- [Безопасность Windows приложение](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
>Изменения списка исключений, внесенные с помощью групповой **политики,** будут показываться в списках в [Безопасность Windows приложении.](microsoft-defender-security-center-antivirus.md)
>
>Изменения, внесенные в **Безопасность Windows, не будут показываться** в списках групповой политики.

Если вы используете PowerShell, вы можете получить список двумя способами:

- Извлечение состояния всех антивирусная программа в Microsoft Defender личных предпочтений. Каждый список отображается в отдельных строках, но элементы в каждом списке объединены в ту же строку.
- Напишите состояние всех предпочтений переменной и используйте эту переменную для вызова только заинтересованного списка. Каждое использование `Add-MpPreference` записано на новую строку.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Проверка списка исключений с помощью MpCmdRun

Чтобы проверить исключения с помощью выделенного средства [командной строки ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)mpcmdrun.exe, используйте следующую команду:

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
>Проверка исключений с помощью MpCmdRun антивирусная программа в Microsoft Defender camp версии 4.18.1812.3 (выпущена в декабре 2018 г.) или более поздней версии.

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Просмотрите список исключений вместе со всеми другими антивирусная программа в Microsoft Defender с помощью PowerShell

Используйте следующий cmdlet:

```PowerShell
Get-MpPreference
```

В следующем примере выделяются элементы, содержащиеся в `ExclusionExtension` списке:

![Выход PowerShell для Get-MpPreference списка исключений наряду с другими предпочтениями](images/defender/wdav-powershell-get-exclusions-all.png)

Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Извлечение определенного списка исключений с помощью PowerShell

Используйте следующий фрагмент кода (введите каждую строку в качестве отдельной команды); замените **WDAVprefs** любой меткой, которая будет называться переменной:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

В следующем примере список делится на новые строки для каждого использования `Add-MpPreference` cmdlet:

![Выход PowerShell, показывающий только записи в списке исключений](images/defender/wdav-powershell-get-exclusions-variable.png)

Дополнительные сведения см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Проверка списков исключений в тестовом файле EICAR

Вы можете проверить, работают ли списки исключений с помощью PowerShell с помощью cmdlet или класса .NET WebClient для скачивания `Invoke-WebRequest` тестового файла.

В следующем фрагменте PowerShell *замените* test.txtфайлом, соответствующим правилам исключения. Например, если вы исключили `.testing` расширение, замените `test.txt` `test.testing` . Если вы тестируете путь, убедитесь, что вы запустите этот кодлет в этом пути.

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

Если антивирусная программа в Microsoft Defender сообщает о вредоносных программах, то правило не работает. Если нет отчета о вредоносных программах и загруженный файл существует, то исключение работает. Вы можете открыть файл, чтобы подтвердить, что содержимое будет таким же, как описано на веб-сайте [тестового файла EICAR.](http://www.eicar.org/86-0-Intended-use.html)

Вы также можете использовать следующий код PowerShell, который вызывает класс .NET WebClient, чтобы скачать тестовый файл , как и в cmdlet; заменитьc:\test.txtфайлом, который соответствует правилу, которое вы `Invoke-WebRequest` проверяете: 

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

Если у вас нет доступа к Интернету, вы можете создать собственный тестовый файл EICAR, написав строку EICAR в новый текстовый файл со следующей командой PowerShell:

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

Вы также можете скопировать строку в пустой текстовый файл и попытаться сохранить ее с именем файла или в папке, вы пытаетсяе исключить.

## <a name="related-topics"></a>Статьи по теме

- [Настройка и проверка исключений в антивирусная программа в Microsoft Defender сканирования](configure-exclusions-microsoft-defender-antivirus.md)
- [Настройка и проверка исключений для файлов, открытых процессами](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Настройка антивирусная программа в Microsoft Defender исключений на Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Распространенные ошибки, которых следует избегать при определении исключений](common-exclusion-mistakes-microsoft-defender-antivirus.md)
