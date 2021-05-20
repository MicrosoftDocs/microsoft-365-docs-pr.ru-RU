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
ms.date: 05/17/2021
ms.openlocfilehash: d10343538c995534878196cc57092c37fd2dcf7b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538067"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="70b0d-104">Распространенные ошибки, которых следует избегать при определении исключений</span><span class="sxs-lookup"><span data-stu-id="70b0d-104">Common mistakes to avoid when defining exclusions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="70b0d-105">Список исключений можно определить для элементов, которые не антивирусная программа в Microsoft Defender проверки.</span><span class="sxs-lookup"><span data-stu-id="70b0d-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="70b0d-106">Такие исключенные элементы могут содержать угрозы, которые делают ваше устройство уязвимым.</span><span class="sxs-lookup"><span data-stu-id="70b0d-106">Such excluded items could contain threats that make your device vulnerable.</span></span> 

<span data-ttu-id="70b0d-107">В этой статье описываются некоторые распространенные ошибки, которые следует избегать при определении исключений.</span><span class="sxs-lookup"><span data-stu-id="70b0d-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="70b0d-108">Перед определением списков исключений [см. Рекомендации для определения исключений.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="70b0d-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="70b0d-109">Исключение некоторых доверенных элементов</span><span class="sxs-lookup"><span data-stu-id="70b0d-109">Excluding certain trusted items</span></span>

<span data-ttu-id="70b0d-110">Некоторые файлы, типы файлов, папки или процессы не должны быть исключены из сканирования, даже если вы уверены, что они не являются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="70b0d-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="70b0d-111">Не определять исключения для расположения папок, расширений файлов и процессов, перечисленных в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="70b0d-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="70b0d-112">Расположения папок</span><span class="sxs-lookup"><span data-stu-id="70b0d-112">Folder locations</span></span>
- <span data-ttu-id="70b0d-113">Расширение файла</span><span class="sxs-lookup"><span data-stu-id="70b0d-113">File extensions</span></span>
- <span data-ttu-id="70b0d-114">Процессы</span><span class="sxs-lookup"><span data-stu-id="70b0d-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="70b0d-115">Расположения папок</span><span class="sxs-lookup"><span data-stu-id="70b0d-115">Folder locations</span></span>

<span data-ttu-id="70b0d-116">Как правило, не следует определять исключения для следующих расположения папок:</span><span class="sxs-lookup"><span data-stu-id="70b0d-116">In general, do not define exclusions for the following folder locations:</span></span>

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

<span data-ttu-id="70b0d-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Обратите внимание на следующее** исключение для SharePoint: Исключите использование антивирусной защиты на уровне файлов в `C:\Users\ServiceAccount\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="70b0d-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="70b0d-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Обратите внимание на следующее** исключение для SharePoint: Исключите использование антивирусной защиты на уровне файлов в `C:\Users\Default\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="70b0d-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

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

### <a name="file-extensions"></a><span data-ttu-id="70b0d-119">Расширение файла</span><span class="sxs-lookup"><span data-stu-id="70b0d-119">File extensions</span></span>

<span data-ttu-id="70b0d-120">В общем, не определять исключений для следующих расширений файлов:</span><span class="sxs-lookup"><span data-stu-id="70b0d-120">In general, do not define exclusions for the following file extensions:</span></span>

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

### <a name="processes"></a><span data-ttu-id="70b0d-121">Процессы</span><span class="sxs-lookup"><span data-stu-id="70b0d-121">Processes</span></span> 

<span data-ttu-id="70b0d-122">Как правило, не следует определять исключения для следующих процессов:</span><span class="sxs-lookup"><span data-stu-id="70b0d-122">In general, do not define exclusions for the following processes:</span></span>

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
> <span data-ttu-id="70b0d-123">Вы можете исключить типы файлов, например , или если в вашей среде есть современное современное программное обеспечение со строгой политикой обновления для обработки любых `.gif` `.jpg` `.jpeg` `.png` уязвимостей.</span><span class="sxs-lookup"><span data-stu-id="70b0d-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="70b0d-124">Использование только имени файла в списке исключений</span><span class="sxs-lookup"><span data-stu-id="70b0d-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="70b0d-125">Вредоносные программы могут иметь то же имя, что и файл, который вы доверяете и хотите исключить из сканирования.</span><span class="sxs-lookup"><span data-stu-id="70b0d-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="70b0d-126">Поэтому, чтобы избежать исключения потенциальной вредоносной программы из сканирования, используйте полностью квалифицированный путь к файлу, который вы хотите исключить, а не использовать только имя файла.</span><span class="sxs-lookup"><span data-stu-id="70b0d-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="70b0d-127">Например, если вы хотите исключить сканирование, используйте полный путь к `Filename.exe` файлу, например `C:\program files\contoso\Filename.exe` .</span><span class="sxs-lookup"><span data-stu-id="70b0d-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="70b0d-128">Использование единого списка исключений для нескольких рабочих нагрузок сервера</span><span class="sxs-lookup"><span data-stu-id="70b0d-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="70b0d-129">Не используйте единый список исключений для определения исключений для нескольких рабочих нагрузок сервера.</span><span class="sxs-lookup"><span data-stu-id="70b0d-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="70b0d-130">Разделите исключения для различных рабочих нагрузок приложений или служб на несколько списков исключений.</span><span class="sxs-lookup"><span data-stu-id="70b0d-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="70b0d-131">Например, список исключений для рабочей нагрузки IIS Server должен быть отличается от списка исключений для SQL Server рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="70b0d-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="70b0d-132">Использование неправильных переменных среды в качестве подстройки в пути имени файла и пути к папке или списках исключений расширения</span><span class="sxs-lookup"><span data-stu-id="70b0d-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="70b0d-133">антивирусная программа в Microsoft Defender Служба выполняется в системной среде с помощью учетной записи LocalSystem, что означает, что она получает информацию из переменной системной среды, а не из переменной среды пользователя.</span><span class="sxs-lookup"><span data-stu-id="70b0d-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="70b0d-134">Использование переменных среды в качестве под диктовки в списках исключений ограничено системными переменными и теми, которые применимы к процессам, запущенным в качестве учетной записи NT AUTHORITY\SYSTEM.</span><span class="sxs-lookup"><span data-stu-id="70b0d-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="70b0d-135">Поэтому при добавлении антивирусная программа в Microsoft Defender и исключений процесса не используйте переменные среды пользователя в качестве поддиам.</span><span class="sxs-lookup"><span data-stu-id="70b0d-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="70b0d-136">Полный список переменных системной среды см. в таблице в статье [Параметры](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) среды Системы.</span><span class="sxs-lookup"><span data-stu-id="70b0d-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="70b0d-137">Сведения [о](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) том, как использовать подкарды в списках исключений файлов и папок или списки исключений для расширения, см. в руб.</span><span class="sxs-lookup"><span data-stu-id="70b0d-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

## <a name="related-articles"></a><span data-ttu-id="70b0d-138">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="70b0d-138">Related articles</span></span>

- [<span data-ttu-id="70b0d-139">Настройка и проверка исключений в антивирусная программа в Microsoft Defender сканирования</span><span class="sxs-lookup"><span data-stu-id="70b0d-139">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="70b0d-140">Настройка и проверка исключений в зависимости от расположения расширения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="70b0d-140">Configure and validate exclusions based on file extension and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="70b0d-141">Настройка и проверка исключений для файлов, открытых процессами</span><span class="sxs-lookup"><span data-stu-id="70b0d-141">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="70b0d-142">Настройка антивирусная программа в Microsoft Defender исключений на Windows Server</span><span class="sxs-lookup"><span data-stu-id="70b0d-142">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
