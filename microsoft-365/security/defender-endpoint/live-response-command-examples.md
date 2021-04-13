---
title: Примеры команд Live response
description: Научитесь запускать базовые или расширенные команды живого ответа для Microsoft Defender для конечной точки и см. примеры использования.
keywords: например, команда, cli, удаленный, оболочка, подключение, live, ответ, в режиме реального времени, команда, скрипт, исправление, охота, экспорт, журнал, падение, скачивание, файл
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f08f20753a1f0926abbbce01fe97f20ef1c07f2c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689094"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="1ffc3-104">Примеры команд Live response</span><span class="sxs-lookup"><span data-stu-id="1ffc3-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1ffc3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1ffc3-105">**Applies to:**</span></span>
- [<span data-ttu-id="1ffc3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1ffc3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1ffc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ffc3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1ffc3-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1ffc3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1ffc3-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="1ffc3-110">Узнайте об общих командах, используемых в живом отклике, и см. примеры их обычного использования.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="1ffc3-111">В зависимости от роли, предоставленной вам, можно запускать базовые или расширенные команды живого ответа.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="1ffc3-112">Дополнительные сведения о базовых и расширенных командах см. в см. в руб. Исследование сущностями на [устройствах с использованием живого ответа.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="1ffc3-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="1ffc3-113">анализ</span><span class="sxs-lookup"><span data-stu-id="1ffc3-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="1ffc3-114">подключения</span><span class="sxs-lookup"><span data-stu-id="1ffc3-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="1ffc3-115">dir</span><span class="sxs-lookup"><span data-stu-id="1ffc3-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="1ffc3-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="1ffc3-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="1ffc3-117">findfile</span><span class="sxs-lookup"><span data-stu-id="1ffc3-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="1ffc3-118">getfile</span><span class="sxs-lookup"><span data-stu-id="1ffc3-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="1ffc3-119">Следующие типы файлов **не могут** быть загружены с помощью этой команды в Live Response:</span><span class="sxs-lookup"><span data-stu-id="1ffc3-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="1ffc3-120">Reparse point files</span><span class="sxs-lookup"><span data-stu-id="1ffc3-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="1ffc3-121">Sparse files</span><span class="sxs-lookup"><span data-stu-id="1ffc3-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="1ffc3-122">Пустые файлы</span><span class="sxs-lookup"><span data-stu-id="1ffc3-122">Empty files</span></span>
> * <span data-ttu-id="1ffc3-123">Виртуальные файлы или файлы, которые не полностью представлены локально</span><span class="sxs-lookup"><span data-stu-id="1ffc3-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="1ffc3-124">Эти типы **файлов поддерживаются** [PowerShell.](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="1ffc3-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="1ffc3-125">Используйте PowerShell в качестве альтернативы, если у вас возникли проблемы с использованием этой команды из live Response.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="1ffc3-126">processes</span><span class="sxs-lookup"><span data-stu-id="1ffc3-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="1ffc3-127">putfile</span><span class="sxs-lookup"><span data-stu-id="1ffc3-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="1ffc3-128">реестр</span><span class="sxs-lookup"><span data-stu-id="1ffc3-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="1ffc3-129">исправление</span><span class="sxs-lookup"><span data-stu-id="1ffc3-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="1ffc3-130">запуск</span><span class="sxs-lookup"><span data-stu-id="1ffc3-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```
>[!NOTE]
>
> <span data-ttu-id="1ffc3-131">Для длительных команд, таких как **'run'** или **getfile',** для выполнения этого действия в фоновом режиме может потребоваться использовать символ '' в конце **&** команды.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-131">For long running commands such as '**run**' or '**getfile**', you may want to use the '**&**' symbol at the end of the command to perform that action in the background.</span></span>
> <span data-ttu-id="1ffc3-132">Это позволит продолжить изучение компьютера и вернуться к фоновой команде при использовании базовой [команды](live-response.md#basic-commands)**fg**.</span><span class="sxs-lookup"><span data-stu-id="1ffc3-132">This will allow you to continue investigating the machine and return to the background command when done using '**fg**' [basic command](live-response.md#basic-commands).</span></span>
>
## <a name="scheduledtask"></a><span data-ttu-id="1ffc3-133">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="1ffc3-133">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="1ffc3-134">отмена</span><span class="sxs-lookup"><span data-stu-id="1ffc3-134">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

