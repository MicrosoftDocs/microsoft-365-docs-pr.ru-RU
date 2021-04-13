---
title: Руководство по развертыванию виртуальной инфраструктуры инфраструктуры виртуальной настольной инфраструктуры Microsoft Defender
description: Узнайте, как развернуть антивирус Microsoft Defender в виртуальной среде рабочего стола для обеспечения наилучшего баланса между защитой и производительностью.
keywords: vdi, hyper-v, vm, виртуальная машина, защитник Windows, антивирус, av, виртуальный рабочий стол, rds, удаленный рабочий стол
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b81addbcaabb1c5ea0d344dbaab9d76a8b100c2b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691489"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="37f09-104">Руководство по развертыванию антивируса Microsoft Defender в среде виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="37f09-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="37f09-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="37f09-105">**Applies to:**</span></span>

- [<span data-ttu-id="37f09-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="37f09-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="37f09-107">Помимо стандартных локальной или аппаратной конфигураций можно также использовать антивирус Microsoft Defender в среде удаленного рабочего стола (RDS) или виртуальной инфраструктуры настольных компьютеров (VDI).</span><span class="sxs-lookup"><span data-stu-id="37f09-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="37f09-108">Дополнительные сведения о [службах](/azure/virtual-desktop) microsoft Remote Desktop Services и VDI см. в документации по виртуальным настольным компьютерам Windows.</span><span class="sxs-lookup"><span data-stu-id="37f09-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="37f09-109">Для виртуальных машин на основе Azure см. в [видеоролике Install Endpoint Protection in Azure Defender.](/azure/security-center/security-center-install-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="37f09-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="37f09-110">Благодаря возможности легкого развертывания обновлений для VMs, работающих в VDIs, мы сократили это руководство, чтобы сосредоточиться на том, как быстро и легко получать обновления на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="37f09-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="37f09-111">Вам больше не нужно создавать и запечатать золотые изображения на периодической основе, так как обновления расширяются в их части компонентов на сервере хост-сервера и загружаются непосредственно в VM, когда он включен.</span><span class="sxs-lookup"><span data-stu-id="37f09-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="37f09-112">В этом руководстве описывается настройка VM-компьютеров для оптимальной защиты и производительности, в том числе:</span><span class="sxs-lookup"><span data-stu-id="37f09-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="37f09-113">Настройка выделенного файла VDI для обновления сведении о безопасности</span><span class="sxs-lookup"><span data-stu-id="37f09-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="37f09-114">Рандомизация запланированных сканов</span><span class="sxs-lookup"><span data-stu-id="37f09-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="37f09-115">Использование быстрых сканов</span><span class="sxs-lookup"><span data-stu-id="37f09-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="37f09-116">Предотвращение уведомлений</span><span class="sxs-lookup"><span data-stu-id="37f09-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="37f09-117">Отключение сканирования после каждого обновления</span><span class="sxs-lookup"><span data-stu-id="37f09-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="37f09-118">Сканирование устарелых машин или компьютеров, которые некоторое время не были в автономном режиме</span><span class="sxs-lookup"><span data-stu-id="37f09-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="37f09-119">Применение исключений</span><span class="sxs-lookup"><span data-stu-id="37f09-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="37f09-120">Вы также можете скачать антивирус [Microsoft Defender](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)в виртуальной инфраструктуре настольных компьютеров, который рассматривает новую функцию общего обновления сведении безопасности, а также тестирование производительности и рекомендации по проверке производительности антивируса на собственном VDI.</span><span class="sxs-lookup"><span data-stu-id="37f09-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37f09-121">Несмотря на то, что VDI может быть организован на Windows Server 2012 или Windows Server 2016, виртуальные машины (виртуальные машины) должны работать как минимум под управлением Windows 10 1607 из-за более современных технологий защиты и функций, недоступных в более ранних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="37f09-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="37f09-122">Существуют улучшения производительности и функций в том, как Microsoft Defender AV работает на виртуальных машинах в Предварительной версии Windows 10 Insider, сборке 18323 (и более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="37f09-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="37f09-123">В этом руководстве мы определяем, нужно ли использовать сборку предварительного просмотра для предварительного просмотра. если она не указана, то минимальная требуемая версия для наилучшей защиты и производительности — Windows 10 1607.</span><span class="sxs-lookup"><span data-stu-id="37f09-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="37f09-124">Настройка выделенного файла VDI</span><span class="sxs-lookup"><span data-stu-id="37f09-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="37f09-125">В Windows 10 версии 1903 мы представили функцию общей разведки безопасности, которая разгружает распаковку скачаемых обновлений разведки безопасности на хост-машину, тем самым сэкономив предыдущие ресурсы ЦП, диска и памяти на отдельных машинах.</span><span class="sxs-lookup"><span data-stu-id="37f09-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="37f09-126">Эта функция была отопорна и теперь работает в Windows 10 версии 1703 и выше.</span><span class="sxs-lookup"><span data-stu-id="37f09-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="37f09-127">Эту функцию можно настроить с помощью групповой политики или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37f09-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="37f09-128">Используйте групповую политику, чтобы включить функцию общей разведки безопасности:</span><span class="sxs-lookup"><span data-stu-id="37f09-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="37f09-129">На компьютере управления групповой политикой откройте консоль управления групповой политикой, щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="37f09-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="37f09-130">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="37f09-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="37f09-131">Щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="37f09-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="37f09-132">Расширь дерево до **компонентов Microsoft**  >  **Defender Antivirus** Security Intelligence  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="37f09-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="37f09-133">Дважды **щелкните Определение расположения аналитики безопасности для клиентов VDI,** а затем установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="37f09-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="37f09-134">Поле автоматически отображается.</span><span class="sxs-lookup"><span data-stu-id="37f09-134">A field automatically appears.</span></span>

6. <span data-ttu-id="37f09-135">Введите `\\<sharedlocation\>\wdav-update` (для справки с этим значением см. [Скачать и распаковать).](#download-and-unpackage-the-latest-updates)</span><span class="sxs-lookup"><span data-stu-id="37f09-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="37f09-136">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="37f09-136">Click **OK**.</span></span>

8. <span data-ttu-id="37f09-137">Развертывание GPO для тестовых VMs.</span><span class="sxs-lookup"><span data-stu-id="37f09-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="37f09-138">Использование PowerShell для обеспечения общей функции разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="37f09-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="37f09-139">Чтобы включить эту функцию, используйте следующий cmdlet.</span><span class="sxs-lookup"><span data-stu-id="37f09-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="37f09-140">Затем необходимо нажать это, как правило, нажимая политики конфигурации на основе PowerShell на VMs:</span><span class="sxs-lookup"><span data-stu-id="37f09-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="37f09-141">Раздел [Загрузка и распаковка](#download-and-unpackage-the-latest-updates) см. в разделе Загрузка и \<shared location\> распаковка.</span><span class="sxs-lookup"><span data-stu-id="37f09-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="37f09-142">Скачивание и распаковка последних обновлений</span><span class="sxs-lookup"><span data-stu-id="37f09-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="37f09-143">Теперь вы можете начать загрузку и установку новых обновлений.</span><span class="sxs-lookup"><span data-stu-id="37f09-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="37f09-144">Ниже мы создали пример сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37f09-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="37f09-145">Этот скрипт — самый простой способ скачивания новых обновлений и их готовности к вашим VMs.</span><span class="sxs-lookup"><span data-stu-id="37f09-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="37f09-146">Затем следует настроить сценарий для запуска в определенное время на машине управления с помощью запланированной задачи (или, если вы знакомы с использованием скриптов PowerShell в Azure, Intune или SCCM, вы также можете использовать эти скрипты).</span><span class="sxs-lookup"><span data-stu-id="37f09-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="37f09-147">Вы можете установить запланированную задачу, которую нужно выполнить один раз в день, чтобы при загрузке и распаковке пакета видеомайки получали новое обновление.</span><span class="sxs-lookup"><span data-stu-id="37f09-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="37f09-148">Мы предлагаем начинать с одного раза в день, но для понимания воздействия следует экспериментировать с увеличением или уменьшением частоты.</span><span class="sxs-lookup"><span data-stu-id="37f09-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="37f09-149">Пакеты сведений безопасности обычно публикуются один раз в три-четыре часа.</span><span class="sxs-lookup"><span data-stu-id="37f09-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="37f09-150">Не рекомендуется устанавливать частоту меньше четырех часов, так как это увеличит накладные расходы на сеть на компьютере управления без каких-либо преимуществ.</span><span class="sxs-lookup"><span data-stu-id="37f09-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="37f09-151">Установите запланированную задачу для запуска сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="37f09-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="37f09-152">На компьютере управления откройте меню Пуск и введите **план-график задач.**</span><span class="sxs-lookup"><span data-stu-id="37f09-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="37f09-153">Откройте его и выберите **Создать задачу...**</span><span class="sxs-lookup"><span data-stu-id="37f09-153">Open it and select **Create task…**</span></span> <span data-ttu-id="37f09-154">на боковой панели.</span><span class="sxs-lookup"><span data-stu-id="37f09-154">on the side panel.</span></span>

2. <span data-ttu-id="37f09-155">Введите имя в **качестве распаковщика сведений** безопасности .</span><span class="sxs-lookup"><span data-stu-id="37f09-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="37f09-156">Перейдите на **вкладку Trigger.** Выберите **новое...**</span><span class="sxs-lookup"><span data-stu-id="37f09-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="37f09-157"> > **Ежедневно** и выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="37f09-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="37f09-158">Перейдите на **вкладку Действия.** Выберите **новое...**</span><span class="sxs-lookup"><span data-stu-id="37f09-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="37f09-159">Введите **PowerShell** в **поле Program/Script.**</span><span class="sxs-lookup"><span data-stu-id="37f09-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="37f09-160">Введите `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` в поле Добавление **аргументов.**</span><span class="sxs-lookup"><span data-stu-id="37f09-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="37f09-161">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="37f09-161">Select **OK**.</span></span>

4. <span data-ttu-id="37f09-162">При желании можно настроить дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="37f09-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="37f09-163">Выберите **ОК,** чтобы сохранить запланированную задачу.</span><span class="sxs-lookup"><span data-stu-id="37f09-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="37f09-164">Вы можете инициировать обновление вручную, щелкнув правой кнопкой мыши по задаче и нажав **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="37f09-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="37f09-165">Загрузка и распаковка вручную</span><span class="sxs-lookup"><span data-stu-id="37f09-165">Download and unpackage manually</span></span>

<span data-ttu-id="37f09-166">Если вы предпочитаете делать все вручную, вот что нужно сделать для репликации поведения скрипта:</span><span class="sxs-lookup"><span data-stu-id="37f09-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="37f09-167">Создайте новую папку в корневой системе, призванной хранить обновления `wdav_update` сведении, например, создайте папку. `c:\wdav_update`</span><span class="sxs-lookup"><span data-stu-id="37f09-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="37f09-168">Создание подмостков под *wdav_update* с именем GUID, например `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="37f09-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="37f09-169">Вот пример: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="37f09-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="37f09-170">В скрипте мы задаем его таким образом, что последние 12 цифр GUID — это год, месяц, день и время загрузки файла, чтобы каждый раз создавалась новая папка.</span><span class="sxs-lookup"><span data-stu-id="37f09-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="37f09-171">Это можно изменить, чтобы файл каждый раз загружался в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="37f09-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="37f09-172">Скачайте пакет сведений безопасности [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  из папки GUID.</span><span class="sxs-lookup"><span data-stu-id="37f09-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="37f09-173">Файл должен быть назван `mpam-fe.exe` .</span><span class="sxs-lookup"><span data-stu-id="37f09-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="37f09-174">Откройте окно подсказки cmd и перейдите в созданную папку GUID.</span><span class="sxs-lookup"><span data-stu-id="37f09-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="37f09-175">Для **извлечения** файлов, например, используйте команду извлечения `mpam-fe.exe /X` /X.</span><span class="sxs-lookup"><span data-stu-id="37f09-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="37f09-176">VMs будут выбирать обновленный пакет всякий раз, когда новая папка GUID создается с извлеченным пакетом обновления или когда существующая папка обновляется с помощью нового извлеченного пакета.</span><span class="sxs-lookup"><span data-stu-id="37f09-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="37f09-177">Рандомизация запланированных сканов</span><span class="sxs-lookup"><span data-stu-id="37f09-177">Randomize scheduled scans</span></span>

<span data-ttu-id="37f09-178">Запланированные проверки запускают в дополнение к защите [и сканированию в режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="37f09-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="37f09-179">Время начала самой проверки по-прежнему основано на политике планового сканирования **(ScheduleDay,** **ScheduleTime** и **ScheduleQuickScanTime).**</span><span class="sxs-lookup"><span data-stu-id="37f09-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="37f09-180">Рандомизация приведет к тому, что антивирус Microsoft Defender запустит сканирование на каждом компьютере в течение 4-часового окна со времени запланированного сканирования.</span><span class="sxs-lookup"><span data-stu-id="37f09-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="37f09-181">См. [список сканов](scheduled-catch-up-scans-microsoft-defender-antivirus.md) расписания для других параметров конфигурации, доступных для запланированных сканов.</span><span class="sxs-lookup"><span data-stu-id="37f09-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="37f09-182">Использование быстрых сканов</span><span class="sxs-lookup"><span data-stu-id="37f09-182">Use quick scans</span></span>

<span data-ttu-id="37f09-183">Можно указать тип сканирования, который должен выполняться во время запланированного сканирования.</span><span class="sxs-lookup"><span data-stu-id="37f09-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="37f09-184">Быстрые проверки являются предпочтительным подходом, так как они предназначены для того, чтобы выглядеть во всех местах, где вредоносные программы должны находиться для активного использования.</span><span class="sxs-lookup"><span data-stu-id="37f09-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="37f09-185">В следующей процедуре описывается настройка быстрого сканирования с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="37f09-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="37f09-186">В редакторе групповой политики перейдите к **административным шаблонам** компонентов Антивирусной проверки  >    >  **Microsoft Defender Microsoft Defender.**  >  </span><span class="sxs-lookup"><span data-stu-id="37f09-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="37f09-187">Выберите Тип сканирования, который **необходимо использовать для запланированного** сканирования, а затем изменить параметр политики.</span><span class="sxs-lookup"><span data-stu-id="37f09-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="37f09-188">Установите политику **включенной,** а затем в **статье Параметры** выберите **быстрое сканирование.**</span><span class="sxs-lookup"><span data-stu-id="37f09-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="37f09-189">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="37f09-189">Select **OK**.</span></span> 

5. <span data-ttu-id="37f09-190">Развертывание объекта групповой политики, как обычно.</span><span class="sxs-lookup"><span data-stu-id="37f09-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="37f09-191">Предотвращение уведомлений</span><span class="sxs-lookup"><span data-stu-id="37f09-191">Prevent notifications</span></span>

<span data-ttu-id="37f09-192">Иногда антивирусные уведомления Microsoft Defender могут быть отправлены или сохраняются на нескольких сеансах.</span><span class="sxs-lookup"><span data-stu-id="37f09-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="37f09-193">Чтобы свести к минимуму эту проблему, можно заблокировать пользовательский интерфейс антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="37f09-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="37f09-194">В следующей процедуре описывается, как пресекать уведомления с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="37f09-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="37f09-195">В редакторе групповой политики перейдите к **компонентам Windows** антивирусного клиентского  >  **интерфейса Microsoft**  >  Defender.</span><span class="sxs-lookup"><span data-stu-id="37f09-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="37f09-196">Выберите **Suppress all notifications** and then edit the policy settings.</span><span class="sxs-lookup"><span data-stu-id="37f09-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="37f09-197">Установите политику **включенной,** а затем выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="37f09-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="37f09-198">Развертывание объекта групповой политики, как обычно.</span><span class="sxs-lookup"><span data-stu-id="37f09-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="37f09-199">Подавление уведомлений предотвращает отображение уведомлений от антивируса Microsoft Defender в Центре действий на Windows 10 при сканировании или действиях по исправлению.</span><span class="sxs-lookup"><span data-stu-id="37f09-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="37f09-200">Тем не менее, группа операций безопасности будет видеть результаты проверки в Центре безопасности Защитника Майкрософт [https://securitycenter.windows.com](https://securitycenter.windows.com) ().</span><span class="sxs-lookup"><span data-stu-id="37f09-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="37f09-201">Чтобы открыть Центр действий в Windows 10, необходимо сделать один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="37f09-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="37f09-202">В правом конце панели задач выберите значок Центра действий.</span><span class="sxs-lookup"><span data-stu-id="37f09-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="37f09-203">Нажмите кнопку Клавиша логотипа Windows + A.</span><span class="sxs-lookup"><span data-stu-id="37f09-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="37f09-204">На сенсорном экране проведите пальцем по правому краю экрана.</span><span class="sxs-lookup"><span data-stu-id="37f09-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="37f09-205">Отключение сканов после обновления</span><span class="sxs-lookup"><span data-stu-id="37f09-205">Disable scans after an update</span></span>

<span data-ttu-id="37f09-206">Отключение сканирования после обновления не позволит сканировать после получения обновления.</span><span class="sxs-lookup"><span data-stu-id="37f09-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="37f09-207">Этот параметр можно применить при создании базового изображения, если вы также запустите быстрое сканирование.</span><span class="sxs-lookup"><span data-stu-id="37f09-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="37f09-208">Таким образом, можно запретить вновь обновленной VM выполнять сканирование (как вы уже отсканировали его при создания базового изображения).</span><span class="sxs-lookup"><span data-stu-id="37f09-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37f09-209">Запуск сканирования после обновления поможет убедиться, что ваши VMs защищены последними обновлениями разведки безопасности.</span><span class="sxs-lookup"><span data-stu-id="37f09-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="37f09-210">Отключение этого параметра снизит уровень защиты ваших VMs и должно использоваться только при первом создании или развертывании базового изображения.</span><span class="sxs-lookup"><span data-stu-id="37f09-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="37f09-211">В редакторе групповой политики перейдите к **компонентам Windows**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates**.</span><span class="sxs-lookup"><span data-stu-id="37f09-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="37f09-212">Выберите **включив сканирование после обновления сведении безопасности,** а затем изменить параметр политики.</span><span class="sxs-lookup"><span data-stu-id="37f09-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="37f09-213">Установите политику **отключенной.**</span><span class="sxs-lookup"><span data-stu-id="37f09-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="37f09-214">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="37f09-214">Select **OK**.</span></span>

5. <span data-ttu-id="37f09-215">Развертывание объекта групповой политики, как обычно.</span><span class="sxs-lookup"><span data-stu-id="37f09-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="37f09-216">Эта политика предотвращает запуск сканирования сразу после обновления.</span><span class="sxs-lookup"><span data-stu-id="37f09-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="37f09-217">Сканирование VMs, которые были отключены</span><span class="sxs-lookup"><span data-stu-id="37f09-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="37f09-218">В редакторе групповой политики перейдите к компонентам **Windows**  >  **антивирусного сканирования Microsoft Defender.**  >  </span><span class="sxs-lookup"><span data-stu-id="37f09-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="37f09-219">**Включите быстрое сканирование и** отредактируйте параметр политики.</span><span class="sxs-lookup"><span data-stu-id="37f09-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="37f09-220">Установите политику **включенной**.</span><span class="sxs-lookup"><span data-stu-id="37f09-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="37f09-221">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="37f09-221">Select **OK**.</span></span>

5. <span data-ttu-id="37f09-222">Развертывание объекта групповой политики, как обычно.</span><span class="sxs-lookup"><span data-stu-id="37f09-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="37f09-223">Эта политика заставляет проверку, если VM пропустил два или более последовательных запланированных сканов.</span><span class="sxs-lookup"><span data-stu-id="37f09-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="37f09-224">Включить безголовый режим пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="37f09-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="37f09-225">В редакторе групповой политики перейдите к **компонентам Windows** антивирусного клиентского  >  **интерфейса Microsoft**  >  Defender.</span><span class="sxs-lookup"><span data-stu-id="37f09-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="37f09-226">Выберите **режим включить безголовый пользовательский интерфейс** и изменить политику.</span><span class="sxs-lookup"><span data-stu-id="37f09-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="37f09-227">Установите политику **включенной**.</span><span class="sxs-lookup"><span data-stu-id="37f09-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="37f09-228">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="37f09-228">Click **OK**.</span></span>

5. <span data-ttu-id="37f09-229">Развертывание объекта групповой политики, как обычно.</span><span class="sxs-lookup"><span data-stu-id="37f09-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="37f09-230">Эта политика скрывает весь пользовательский интерфейс антивируса Microsoft Defender от конечных пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="37f09-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="37f09-231">Исключения</span><span class="sxs-lookup"><span data-stu-id="37f09-231">Exclusions</span></span>

<span data-ttu-id="37f09-232">Исключения можно добавлять, удалять или настраивать в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="37f09-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="37f09-233">Дополнительные сведения см. в дополнительных сведениях о настройке исключений [антивируса Microsoft Defender на Windows Server.](configure-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="37f09-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="37f09-234">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="37f09-234">Additional resources</span></span>

- [<span data-ttu-id="37f09-235">Блог сообщества технологий: настройка антивируса Microsoft Defender для нестандартных машин VDI</span><span class="sxs-lookup"><span data-stu-id="37f09-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="37f09-236">Форумы TechNet по службам удаленного рабочего стола и VDI</span><span class="sxs-lookup"><span data-stu-id="37f09-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="37f09-237">Сценарий SignatureDownloadCustomTask PowerShell</span><span class="sxs-lookup"><span data-stu-id="37f09-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)