---
title: Рекомендации по тестовой упаковке
description: Просмотрите рекомендации по тестовой упаковке
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323047"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="db253-103">Рекомендации по тестовой упаковке</span><span class="sxs-lookup"><span data-stu-id="db253-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="db253-104">1. Ссылки на сценарий</span><span class="sxs-lookup"><span data-stu-id="db253-104">1.   Script referencing</span></span>

<span data-ttu-id="db253-105">При отправке .zip на портал мы отмывем все содержимое этого файла в корневую папку.</span><span class="sxs-lookup"><span data-stu-id="db253-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="db253-106">Чтобы сделать эту первиченную операцию по откаживке, не нужно писать код.</span><span class="sxs-lookup"><span data-stu-id="db253-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="db253-107">Вы также можете ссылаться на любой файл в .zip с помощью пути относительно почтового файла, загруженного.</span><span class="sxs-lookup"><span data-stu-id="db253-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="db253-108">В приведенной ниже примере мы покажем, как можно ссылаться на ваши binaries/scripts из поля ввода на вкладке Задачи. Текст в синем цвете должен быть введен в поле **путь скрипта** **без кавычка.**</span><span class="sxs-lookup"><span data-stu-id="db253-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="db253-109">Важно, чтобы вы знали о содержимом в почтовом файле перед его отправкой.</span><span class="sxs-lookup"><span data-stu-id="db253-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="db253-110">Часто при прорезыве папки локализованная машина создает основную папку под почтовым файлом.</span><span class="sxs-lookup"><span data-stu-id="db253-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="db253-111">В этом случае ссылки будут показаны в жирном **шрифте** ниже:</span><span class="sxs-lookup"><span data-stu-id="db253-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="db253-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="db253-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="db253-113">ScriptX.ps1 — **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="db253-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="db253-114">Script.ps1 — **"Contoso_App_Folder/folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="db253-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="db253-115">В других случаях почтовый файл может иметь файлы или содержимое прямо под ним, то есть нет папки 2-го уровня:</span><span class="sxs-lookup"><span data-stu-id="db253-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="db253-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="db253-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="db253-117">ScriptX.ps1 — **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="db253-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="db253-118">Script.ps1 — **"folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="db253-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="db253-119">2. Выполнение сценария</span><span class="sxs-lookup"><span data-stu-id="db253-119">2.   Script execution</span></span>

<span data-ttu-id="db253-120">**Тесты out-of-Box:** Пакет приложений должен содержать не менее трех скриптов PowerShell, которые будут выполнять без присмотра установку, запуск и закрытие приложения и его зависимостей.</span><span class="sxs-lookup"><span data-stu-id="db253-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="db253-121">Каждый скрипт должен обрабатывать проверку собственных необходимых условий, проверку успешности, а также очистку после себя (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="db253-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="db253-122">**Функциональные тесты:** Пакет приложений должен содержать по крайней мере один скрипт PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db253-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="db253-123">Если предоставлено несколько сценариев, сценарии выполняются в последовательности отправки, а сбой в определенном скрипте остановит выполнение последующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="db253-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="db253-124">Требования к скриптам</span><span class="sxs-lookup"><span data-stu-id="db253-124">Script requirements</span></span>

<span data-ttu-id="db253-125">• PowerShell Версия 5.1+</span><span class="sxs-lookup"><span data-stu-id="db253-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="db253-126">• Без присмотра выполнение</span><span class="sxs-lookup"><span data-stu-id="db253-126">•   Unattended execution</span></span>    

<span data-ttu-id="db253-127">• Код возврата ошибок</span><span class="sxs-lookup"><span data-stu-id="db253-127">•   Error return code</span></span>               

<span data-ttu-id="db253-128">• Проверка успешности</span><span class="sxs-lookup"><span data-stu-id="db253-128">•   Validate success</span></span>            

<span data-ttu-id="db253-129">• Ведение журнала для скрипта определенной папки журнала</span><span class="sxs-lookup"><span data-stu-id="db253-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="db253-130">Для успешного выполнения в тестовом конвейере каждый сценарий должен выполняться полностью без присмотра.</span><span class="sxs-lookup"><span data-stu-id="db253-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="db253-131">Скрипты должны возвращать "0" при успешном завершении и коде ошибки без нуля, если ошибка возникает во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="db253-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="db253-132">Каждый скрипт должен проверить, успешно ли он выполнился.</span><span class="sxs-lookup"><span data-stu-id="db253-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="db253-133">Например,</span><span class="sxs-lookup"><span data-stu-id="db253-133">E.g.</span></span> <span data-ttu-id="db253-134">сценарий установки должен проверять наличие определенных двоичных и/или ключей реестра в системе после завершения выполнения двоичного установки для обеспечения с разумной степенью уверенности в успешности установки.</span><span class="sxs-lookup"><span data-stu-id="db253-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="db253-135">Это необходимо для правильной диагностики ошибок во время тестового запуска, например, не удается успешно установить приложение и не удается запустить его.</span><span class="sxs-lookup"><span data-stu-id="db253-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="db253-136">**Избегайте следующих:** Скрипты не должны перезагружать машину, если требуется перезагрузка, укажите это во время загрузки скриптов.</span><span class="sxs-lookup"><span data-stu-id="db253-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="db253-137">3. Коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="db253-137">3.   Log collection</span></span>

<span data-ttu-id="db253-138">Каждый скрипт должен выводить все журналы, которые он создает, в папку с именем ```logs``` .</span><span class="sxs-lookup"><span data-stu-id="db253-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="db253-139">Все папки с именем каталога будут скопированы и представлены для ```logs``` скачивания на ```Test Results``` странице.</span><span class="sxs-lookup"><span data-stu-id="db253-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="db253-140">Например, сценарий установки (который может быть расположен в каталоге **App/scripts/install)** может выводить журналы в: **журналы/install.log,** так что окончательный журнал будет по адресу: **Apps/scripts/install/log/install.log**</span><span class="sxs-lookup"><span data-stu-id="db253-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="db253-141">Система подберет файл вместе с другими файлами в других папках и ```install.log``` ```logs``` соберет его для скачивания.</span><span class="sxs-lookup"><span data-stu-id="db253-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="db253-142">4. Разнонабные приложения</span><span class="sxs-lookup"><span data-stu-id="db253-142">4.   Application binaries</span></span>

<span data-ttu-id="db253-143">Все файлы и зависимости должны быть включены в единый почтовый файл.</span><span class="sxs-lookup"><span data-stu-id="db253-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="db253-144">Они должны включать все необходимое для установки приложения (например, установщик приложения); если приложение имеет зависимость от каких-либо фреймворков, таких как .NET Core/Standard или платформа .NET Framework, они должны быть включены в файл и правильно ссылаться в предоставленных скриптах.</span><span class="sxs-lookup"><span data-stu-id="db253-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="db253-145">Загруженный почтовый файл не может иметь пробелы или специальные символы в его имени</span><span class="sxs-lookup"><span data-stu-id="db253-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="db253-146">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="db253-146">Next steps</span></span>

<span data-ttu-id="db253-147">Заранее в следующей статье, чтобы просмотреть некоторые **часто задаваемые вопросы (часто задаваемые вопросы)**</span><span class="sxs-lookup"><span data-stu-id="db253-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="db253-148">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="db253-148">Next step</span></span>](faq.md)
