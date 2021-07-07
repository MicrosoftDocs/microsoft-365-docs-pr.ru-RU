---
title: Функциональное тестирование на тестовой базе
description: Сведения о проверке приложения с помощью существующих автоматизированных функциональных тестов
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
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323227"
---
# <a name="functional-testing"></a><span data-ttu-id="d3bcb-103">Функциональное тестирование</span><span class="sxs-lookup"><span data-stu-id="d3bcb-103">Functional testing</span></span>

<span data-ttu-id="d3bcb-104">В качестве поставщика программного обеспечения теперь можно выполнять настраиваемые функциональные тесты с помощью тестовой базы по вашему выбору - через самообслуживаемую тестовую базу для портала M365.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-104">As a software vendor, you can now perform custom functional tests, using the test framework of your choice - via the self-serve Test Base for M365 portal.</span></span> 

<span data-ttu-id="d3bcb-105">Когда мы первоначально запустили службу, мы предложили тесты out-of-box, который является заранее определенным набором тестов, управляемых стандартным скриптом.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-105">When we initially launched the service, we offered the Out-of-box tests, which is a pre-defined set of tests driven through standardized scripting.</span></span> <span data-ttu-id="d3bcb-106">Это, однако, не удалось добиться полного тестирования для многих независимых поставщиков программного обеспечения (ISVs).</span><span class="sxs-lookup"><span data-stu-id="d3bcb-106">This, however, could not achieve full test coverage for many Independent Software Vendors (ISVs).</span></span> 

<span data-ttu-id="d3bcb-107">Таким образом, в ответ на ваши отзывы мы предоставляем нашим isV-системам возможность загружать автоматизированные функциональные тесты.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-107">Hence, in response to your feedback, we are providing our ISVs with the ability to upload automated functional tests.</span></span>

<span data-ttu-id="d3bcb-108">Чтобы использовать эту функцию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d3bcb-108">To use this feature, follow the steps below:</span></span>

1. <span data-ttu-id="d3bcb-109">Upload файлы (файлы, зависимости и сценарии) в качестве единого .zip пакета.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-109">Upload your files (binaries, dependencies and scripts) as a single .zip package.</span></span>
2. <span data-ttu-id="d3bcb-110">Выберите, чтобы перезагрузка тестовых виртуальных машин (виртуальных машин) в различных точках выполнения.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-110">Choose if you want to reboot the test Virtual Machines (VMs) at various points of execution.</span></span>
3. <span data-ttu-id="d3bcb-111">Управление доступными вариантами сценариев.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-111">Manage available options for your scripts.</span></span>
4. <span data-ttu-id="d3bcb-112">Выберите, когда применить Windows обновления на VM во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-112">Choose when to apply the Windows update on the VM during execution.</span></span>

<span data-ttu-id="d3bcb-113">Подробные описания вышеуказанных действий приведены ниже:</span><span class="sxs-lookup"><span data-stu-id="d3bcb-113">Detailed descriptions of the above steps are highlighted below:</span></span>

<span data-ttu-id="d3bcb-114">**Upload функциональный тестовый пакет**</span><span class="sxs-lookup"><span data-stu-id="d3bcb-114">**Upload a functional test package**</span></span>

<span data-ttu-id="d3bcb-115">Чтобы начать работу, перейдите на страницу Upload, выберите Upload приложение в каталоге приложений в левом меню навигации портала Test Base для M365 в Azure.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-115">To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span></span> <span data-ttu-id="d3bcb-116">Оттуда:</span><span class="sxs-lookup"><span data-stu-id="d3bcb-116">From there:</span></span>

<span data-ttu-id="d3bcb-117">Вкладка 1 . Ввод базовых сведений.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-117">Tab 1 - Enter basic information.</span></span> <span data-ttu-id="d3bcb-118">Укайте имя и версию приложения.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-118">Provide the name and version of your application.</span></span> <span data-ttu-id="d3bcb-119">В параметре Type of test выберите ```Functional tests``` .</span><span class="sxs-lookup"><span data-stu-id="d3bcb-119">In the Type of test option, select ```Functional tests```.</span></span> 

<span data-ttu-id="d3bcb-120">*Обратите внимание, что параметр Out-of-Box (OOB) требуется по умолчанию.*</span><span class="sxs-lookup"><span data-stu-id="d3bcb-120">*Note that the Out-of-Box (OOB) option is required by default.*</span></span>


![Выберите вкладку функционального тестирования](Media/functional_testing_tab1.png)

<span data-ttu-id="d3bcb-122">Вкладка 2 — Upload компонентов пакета, загрузив почтовый файл со всем тестом (файлы, зависимости, скрипты и т.д.).</span><span class="sxs-lookup"><span data-stu-id="d3bcb-122">Tab 2 - Upload the components of your package by uploading a zip file with your entire test (binaries, dependencies, scripts etc).</span></span> 

<span data-ttu-id="d3bcb-123">Подробные aka.ms/usl-package-outline см. в aka.ms/usl-package-outline.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-123">See aka.ms/usl-package-outline for details.</span></span> <span data-ttu-id="d3bcb-124">(Примечание. Оба тестовых скрипта out-of-Box и функциональное содержимое теста должны быть помещены в один и тот же почтовый файл).</span><span class="sxs-lookup"><span data-stu-id="d3bcb-124">(Note: Both the Out-of-Box test scripts and the Functional test contents should be placed into the same zip file).</span></span> <span data-ttu-id="d3bcb-125">В настоящее время размер файла ограничен 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-125">Currently, the file size is limited to 2GB.</span></span>

<span data-ttu-id="d3bcb-126">Вкладка 3 . Настройка задач тестирования вне окна и функциональных функций.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-126">Tab 3 - Configure the Out-of-Box and Functional test tasks.</span></span> <span data-ttu-id="d3bcb-127">Здесь выберите путь (ы) к скриптам PowerShell, которые будут устанавливать, запускать, закрывать и удалить приложение (для out-of-Box), а также путь (s) для всех настраиваемого скрипта для выполнения функционального теста.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-127">Here, choose the path(s) to the PowerShell scripts that will install, launch, close, and uninstall your application (for Out-of-Box) as well as the path(s) to all your custom scripts to perform your functional test.</span></span> <span data-ttu-id="d3bcb-128">**(Примечание. Сценарий для списания приложения необязателен).**</span><span class="sxs-lookup"><span data-stu-id="d3bcb-128">**(Note: A script to uninstall your application is optional).**</span></span>

<span data-ttu-id="d3bcb-129">В настоящее время для функциональных тестов можно загрузить от 1 до 8 скриптов.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-129">Currently, you can upload between 1 and 8 scripts for your functional tests.</span></span> <span data-ttu-id="d3bcb-130">(Любезно комментарий на этот пост, если вам нужно больше сценариев!)</span><span class="sxs-lookup"><span data-stu-id="d3bcb-130">(Kindly comment on this post if you need more scripts!)</span></span>

![Upload до 8 скриптов с функциональными тестами](Media/functional_testing_tab3.png)

<span data-ttu-id="d3bcb-132">(Необязательный) Настройка перезапуска после установки.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-132">(Optional) Configure a restart after installation.</span></span> <span data-ttu-id="d3bcb-133">Некоторые приложения требуют перезапуска после установки.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-133">Some applications require a restart after installation.</span></span> 

<span data-ttu-id="d3bcb-134">Выберите ```Reboot After Execution``` для конкретного скрипта на вкладке Задачи, если вы хотите, чтобы перезапуск был проведен после выполнения этого сценария.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-134">Select ```Reboot After Execution``` for the specific Script in the Tasks tab if you would like a restart to be conducted after the execution of that script.</span></span>

<span data-ttu-id="d3bcb-135">Вкладка 4 . Выберите Windows установки обновления: приложение патча Windows обновления будет сделано до любого сценария по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-135">Tab 4 - Choose when the Windows update gets installed: The application of the Windows Update patch is done before any script of your choice.</span></span> <span data-ttu-id="d3bcb-136">Рекомендуется установить обновление Windows после установки приложения, чтобы точно имитировать сценарии использования приложений в реальном мире.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-136">It is recommended that you install a Windows update after the application's installation to closely mimic your real-world application use scenarios.</span></span>

![Обновление Windows может быть установлено после определенного сценария](Media/functional_testing_tab4.png)

<span data-ttu-id="d3bcb-138">Вкладка 5 . Обзор и создание пакета.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-138">Tab 5 - Review and create the package.</span></span> <span data-ttu-id="d3bcb-139">После завершения перечисленных выше действий выберите, ```Create``` чтобы завершить процесс загрузки.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-139">Once you have completed the steps listed above, select ```Create``` to finish the uploading process.</span></span>

<span data-ttu-id="d3bcb-140">После создания пакета можно проверить состояние проверки пакета.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-140">Once your package has been created, you can check the verification status of your package.</span></span>

<span data-ttu-id="d3bcb-141">Мы запускаем начальный тест, чтобы установить, запустить, закрыть и удалить ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-141">We run an initial test to install, launch, close, and uninstall your application.</span></span> <span data-ttu-id="d3bcb-142">Это позволяет нам убедиться, что ваш пакет можно установить на нашей службе без ошибок.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-142">This allows us to verify that your package can install on our service error-free.</span></span>

<span data-ttu-id="d3bcb-143">Процесс проверки может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-143">The verification process could take up to 24 hours.</span></span> <span data-ttu-id="d3bcb-144">После завершения проверки можно увидеть состояние в меню, которое будет одним ```Manage packages``` из двух записей:</span><span class="sxs-lookup"><span data-stu-id="d3bcb-144">Once verification is complete, you can see the status in the ```Manage packages``` menu, which would be one of two entries:</span></span>

1. <span data-ttu-id="d3bcb-145">Проверка успешно: пакет будет автоматически протестирован на Windows обновления для выбранных сборки ОС.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-145">Verification succeeds: The package will be automatically tested against pre-release Windows updates for the OS builds you selected.</span></span>
<span data-ttu-id="d3bcb-146">или</span><span class="sxs-lookup"><span data-stu-id="d3bcb-146">or</span></span>
2. <span data-ttu-id="d3bcb-147">Проверка не удается. Вам потребуется изучить причины сбоя, устранить проблему и повторно загрузить пакет.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-147">Verification fails: You will need to investigate the reasons for the failure, fix the issue, and re-upload your package.</span></span>

<span data-ttu-id="d3bcb-148">Вы также будете уведомлены о любом исходе с помощью значка уведомлений на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="d3bcb-148">You will also be notified of either outcome via the notification icon in the Azure portal.</span></span>
