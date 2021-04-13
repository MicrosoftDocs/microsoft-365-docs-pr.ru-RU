---
title: Распространенные ошибки, которые следует избегать при определении исключений
description: Избегайте распространенных ошибок при определении исключений для антивирусного сканирования Microsoft Defender.
keywords: исключения, файлы, расширение, тип файла, имя папки, имя файла, сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d14e37c8f3cfdfe8d88bfd4e255a431fbb8d6d41
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691079"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Распространенные ошибки, которые следует избегать при определении исключений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Список исключений можно определить для элементов, которые не нужно проверять антивирусу Microsoft Defender. Такие исключенные элементы могут содержать угрозы, которые делают ваше устройство уязвимым. 

В этой статье описываются некоторые распространенные ошибки, которые следует избегать при определении исключений. 

Перед определением списков исключений см. [рекомендации по определению исключений.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>Исключение некоторых доверенных элементов

Некоторые файлы, типы файлов, папки или процессы не должны быть исключены из сканирования, даже если вы уверены, что они не являются вредоносными. 

Не определять исключений для расположения папок, расширений файлов и процессов, перечисленных в следующей таблице:

| Расположения папок | Расширение файла | Процессы |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> Вы можете исключить типы файлов, например , или если в вашей среде есть современное современное программное обеспечение со строгой политикой обновления для обработки любых `.gif` `.jpg` `.jpeg` `.png` уязвимостей.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Использование только имени файла в списке исключений

Вредоносные программы могут иметь то же имя, что и файл, который вы доверяете и хотите исключить из сканирования. Поэтому, чтобы избежать исключения потенциальной вредоносной программы из сканирования, используйте полностью квалифицированный путь к файлу, который вы хотите исключить, а не использовать только имя файла. Например, если вы хотите исключить сканирование, используйте полный путь к `Filename.exe` файлу, например `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Использование единого списка исключений для нескольких рабочих нагрузок сервера

Не используйте единый список исключений для определения исключений для нескольких рабочих нагрузок сервера. Разделите исключения для различных рабочих нагрузок приложений или служб на несколько списков исключений. Например, список исключений для рабочей нагрузки IIS Server должен быть отличается от списка исключений для SQL Server рабочей нагрузки.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Использование неправильных переменных среды в качестве подстройки в пути имени файла и пути к папке или списках исключений расширения

Антивирусная служба Microsoft Defender выполняется в системных контекстах с помощью учетной записи LocalSystem, что означает, что она получает информацию из переменной системной среды, а не из переменной среды пользователя. Использование переменных среды в качестве под диктовки в списках исключений ограничено системными переменными и теми, которые применимы к процессам, запущенным в качестве учетной записи NT AUTHORITY\SYSTEM. Поэтому при добавлении антивирусной папки Microsoft Defender и исключений процесса не используйте переменные среды пользователя в качестве подкард. Полный список переменных системной среды см. в таблице в статье [Параметры](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) среды Системы.

Сведения [о](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) том, как использовать подкарды в списках исключений файлов и папок или списки исключений для расширения, см. в руб.

## <a name="related-articles"></a>Статьи по теме

- [Настройка и проверка исключений в антивирусных проверках Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)
- [Настройка и проверка исключений в зависимости от расположения расширения файлов и папок](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Настройка и проверка исключений для файлов, открытых процессами](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Настройка исключений антивируса Microsoft Defender на Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
