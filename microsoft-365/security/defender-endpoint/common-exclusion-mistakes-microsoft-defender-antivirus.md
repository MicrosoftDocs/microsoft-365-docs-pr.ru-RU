---
title: Распространенные ошибки, которых следует избегать при определении исключений
description: Избегайте распространенных ошибок при определении исключений для антивирусная программа в Microsoft Defender сканирования.
keywords: исключения, файлы, расширение, тип файла, имя папки, имя файла, сканирование
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/15/2021
ms.openlocfilehash: f9ca83fcfba4b79898a0fed527e38947a4c230d6
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950135"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Распространенные ошибки, которых следует избегать при определении исключений

Список исключений можно определить для элементов, которые не антивирусная программа в Microsoft Defender проверки. Такие исключенные элементы могут содержать угрозы, которые делают ваше устройство уязвимым. В этой статье описываются некоторые распространенные ошибки, которые следует избегать при определении исключений. 

Перед определением списков исключений [см. Рекомендации для определения исключений.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>Исключение некоторых доверенных элементов

Некоторые файлы, типы файлов, папки или процессы не должны быть исключены из сканирования, даже если вы уверены, что они не являются вредоносными. 

Не определять исключения для расположения папок, расширений файлов и процессов, перечисленных в следующих разделах:
- Расположения папок
- Расширение файла
- Процессы

### <a name="folder-locations"></a>Расположения папок

Как правило, не следует определять исключения для следующих расположения папок:

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Обратите внимание на следующее** исключение для SharePoint: Исключите использование антивирусной защиты на уровне файлов в `C:\Users\ServiceAccount\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Обратите внимание на следующее** исключение для SharePoint: Исключите использование антивирусной защиты на уровне файлов в `C:\Users\Default\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a>Расширение файла

В общем, не определять исключений для следующих расширений файлов:

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a>Процессы 

Как правило, не следует определять исключения для следующих процессов:

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`

`dotnet.exe`

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

> [!NOTE]
> Вы можете исключить типы файлов, например , или если в вашей среде есть современное современное программное обеспечение со строгой политикой обновления для обработки любых `.gif` `.jpg` `.jpeg` `.png` уязвимостей.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Использование только имени файла в списке исключений

Вредоносные программы могут иметь то же имя, что и файл, который вы доверяете и хотите исключить из сканирования. Поэтому, чтобы избежать исключения потенциальной вредоносной программы из сканирования, используйте полностью квалифицированный путь к файлу, который вы хотите исключить, а не использовать только имя файла. Например, если вы хотите исключить сканирование, используйте полный путь к `Filename.exe` файлу, например `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Использование единого списка исключений для нескольких рабочих нагрузок сервера

Не используйте единый список исключений для определения исключений для нескольких рабочих нагрузок сервера. Разделите исключения для различных рабочих нагрузок приложений или служб на несколько списков исключений. Например, список исключений для рабочей нагрузки IIS Server должен быть отличается от списка исключений для SQL Server рабочей нагрузки.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Использование неправильных переменных среды в качестве подстройки в пути имени файла и пути к папке или списках исключений расширения

антивирусная программа в Microsoft Defender Служба выполняется в системной среде с помощью учетной записи LocalSystem, что означает, что она получает информацию из переменной системной среды, а не из переменной среды пользователя. Использование переменных среды в качестве под диктовки в списках исключений ограничено системными переменными и теми, которые применимы к процессам, запущенным в качестве учетной записи NT AUTHORITY\SYSTEM. Поэтому при добавлении антивирусная программа в Microsoft Defender и исключений процесса не используйте переменные среды пользователя в качестве поддиам. Полный список переменных системной среды см. в таблице в статье [Параметры](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) среды Системы.

Сведения [о](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) том, как использовать подкарды в списках исключений файлов и папок или списки исключений для расширения, см. в руб.

