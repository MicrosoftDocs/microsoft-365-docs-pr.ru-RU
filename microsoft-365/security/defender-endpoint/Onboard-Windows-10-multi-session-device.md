---
title: Onboard Windows 10 multi-session devices in Windows Virtual Desktop
description: Дополнительные статьи о многосерийных устройствах Windows 10 в Windows Virtual Desktop
keywords: Windows Virtual Desktop, WVD, microsoft defender, endpoint, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.date: 09/10/2020
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 30e664aed74ed01944c67b139e6268fc3340ada4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069861"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="bbdc9-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="bbdc9-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="bbdc9-105">6 минут для чтения</span><span class="sxs-lookup"><span data-stu-id="bbdc9-105">6 minutes to read</span></span> 

<span data-ttu-id="bbdc9-106">Применимо к:</span><span class="sxs-lookup"><span data-stu-id="bbdc9-106">Applies to:</span></span> 
- <span data-ttu-id="bbdc9-107">Много сеансы Windows 10, работающие на виртуальном рабочем столе Windows (WVD)</span><span class="sxs-lookup"><span data-stu-id="bbdc9-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="bbdc9-108">Добро пожаловать в Microsoft Defender для конечной точки, новое имя для Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-108">Welcome to Microsoft Defender for Endpoint, the new name for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bbdc9-109">Дополнительные сведения об этом и других обновлениях см. здесь.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-109">Read more about this and other updates here.</span></span> <span data-ttu-id="bbdc9-110">В ближайшее время мы будем обновлять названия в продуктах и документах.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-110">We'll be updating names in products and in the docs in the near future.</span></span>

> [!WARNING]
> <span data-ttu-id="bbdc9-111">Поддержка Microsoft Defender для конечных точек для сценариев нескольких сеансов Windows Virtual Desktop в настоящее время находится в режиме предварительного просмотра и ограничена до 25 сеансов одновременно на один хост/VM.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-111">Microsoft Defender for Endpoint support for Windows Virtual Desktop multi-session scenarios is currently in Preview and limited up to 25 concurrent sessions per host/VM.</span></span> <span data-ttu-id="bbdc9-112">Однако сценарии одного сеанса на виртуальном рабочем столе Windows полностью поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-112">However, single session scenarios on Windows Virtual Desktop are fully supported.</span></span>

<span data-ttu-id="bbdc9-113">Microsoft Defender для конечной точки поддерживает мониторинг как сеансов виртуального компьютера, так и виртуальных настольных компьютеров Windows.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-113">Microsoft Defender for Endpoint supports monitoring both VDI as well as Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="bbdc9-114">В зависимости от потребностей организации вам может потребоваться реализовать сеансы виртуального компьютера vDI или Windows Virtual Desktop, чтобы помочь сотрудникам получать доступ к корпоративным данным и приложениям из неугодного устройства, удаленного расположения или аналогичного сценария.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-114">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="bbdc9-115">С помощью Microsoft Defender для конечной точки вы можете отслеживать эти виртуальные машины для аномальной активности.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-115">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="bbdc9-116">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="bbdc9-116">Before you begin</span></span>
<span data-ttu-id="bbdc9-117">Ознакомьтесь с [соображениями для нестандартных VDI](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span><span class="sxs-lookup"><span data-stu-id="bbdc9-117">Familiarize yourself with the [considerations for non-persistent VDI](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="bbdc9-118">Несмотря [на то,](https://docs.microsoft.com/azure/virtual-desktop/overview) что виртуальный рабочий стол Windows не предоставляет параметры сохраняемости, он предоставляет способы использования золотого изображения Windows, которое можно использовать для обеспечения новых хостов и передислокационных машин.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-118">While [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) does not provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="bbdc9-119">Это повышает волатильность в среде и таким образом влияет на то, какие записи создаются и поддерживаются на портале Microsoft Defender для конечных точек, что потенциально снижает видимость для аналитиков безопасности.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-119">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="bbdc9-120">В зависимости от выбора метода бортовой работы устройства могут отображаться на портале Microsoft Defender для конечных точек так же:</span><span class="sxs-lookup"><span data-stu-id="bbdc9-120">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="bbdc9-121">Одна запись для каждого виртуального рабочего стола</span><span class="sxs-lookup"><span data-stu-id="bbdc9-121">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="bbdc9-122">Несколько записей для каждого виртуального рабочего стола</span><span class="sxs-lookup"><span data-stu-id="bbdc9-122">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="bbdc9-123">Корпорация Майкрософт рекомендует использовать Виртуальный рабочий стол Windows в качестве единой записи на виртуальном рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-123">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="bbdc9-124">Это гарантирует, что опыт исследования на портале Конечной точки Защитника Майкрософт находится в контексте одного устройства на основе имени машины.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-124">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="bbdc9-125">Организации, которые часто удаляют и повторно развертывают хосты WVD, должны активно использовать этот метод, поскольку он не позволяет создавать несколько объектов для одной машины на портале Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-125">Organizations that frequently delete and re-deploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="bbdc9-126">Это может привести к путанице при расследовании инцидентов.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-126">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="bbdc9-127">Для тестовых или нестабиленных сред можно выбрать другой выбор.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-127">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="bbdc9-128">Корпорация Майкрософт рекомендует добавить сценарий onboarding Microsoft Defender для конечной точки в золотое изображение WVD.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-128">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="bbdc9-129">Таким образом, вы можете быть уверены, что этот сценарий для загрузки выполняется сразу же при первой загрузке.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-129">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="bbdc9-130">Он выполняется в качестве скрипта запуска при первой загрузке на всех машинах WVD, которые были оформлены из золотого изображения WVD.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-130">It is executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="bbdc9-131">Однако если вы используете одно из изображений галереи без изменений, поместите сценарий в общее расположение и позвоните ему из локальной или групповой политики домена.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-131">However, if you are using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="bbdc9-132">Размещение и конфигурация сценария запуска VDI на золотом изображении WVD настраивает его как сценарий запуска, который запускается при запуске WVD.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-132">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="bbdc9-133">Не рекомендуется использовать фактическое золотое изображение WVD.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-133">It is NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="bbdc9-134">Другим фактором является метод, используемый для запуска скрипта.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-134">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="bbdc9-135">Он должен запуститься как можно раньше в процессе запуска и подготовка, чтобы сократить время между машиной, доступной для получения сеансов, и устройством на борту службы.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-135">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="bbdc9-136">Ниже приведены сценарии 1 & 2 с учетом этого.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-136">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="bbdc9-137">Сценарии</span><span class="sxs-lookup"><span data-stu-id="bbdc9-137">Scenarios</span></span>
<span data-ttu-id="bbdc9-138">Существует несколько способов на борту хост-машины WVD:</span><span class="sxs-lookup"><span data-stu-id="bbdc9-138">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="bbdc9-139">Запустите сценарий в золотом изображении (или из общего расположения) во время запуска.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-139">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="bbdc9-140">Используйте средство управления для запуска скрипта.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-140">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="bbdc9-141">*Сценарий 1. Использование локальной групповой политики*</span><span class="sxs-lookup"><span data-stu-id="bbdc9-141">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="bbdc9-142">Этот сценарий требует размещения скрипта в золотом изображении и использования локальной групповой политики для запуска на ранних стадиях загрузки.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-142">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="bbdc9-143">Используйте инструкции на устройствах VDI инфраструктуры виртуальной инфраструктуры виртуальных [настольных компьютеров.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)</span><span class="sxs-lookup"><span data-stu-id="bbdc9-143">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="bbdc9-144">Следуйте инструкциям для одной записи для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-144">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="bbdc9-145">*Сценарий 2. Использование политики группы доменов*</span><span class="sxs-lookup"><span data-stu-id="bbdc9-145">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="bbdc9-146">Этот сценарий использует централизованный сценарий и запускает его с помощью групповой политики на основе домена.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-146">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="bbdc9-147">Вы также можете разместить сценарий в золотом изображении и запустить его таким же образом.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-147">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="bbdc9-148">**Скачайте WindowsDefenderATPOnboardingPackage.zip из центра Защитник Windows безопасности**</span><span class="sxs-lookup"><span data-stu-id="bbdc9-148">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>
1. <span data-ttu-id="bbdc9-149">Откройте пакет конфигурации VDI .zip-файл (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="bbdc9-149">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  
    - <span data-ttu-id="bbdc9-150">В области навигации Центра безопасности Microsoft Defender выберите **параметры**  >  **onboarding**.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-150">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    - <span data-ttu-id="bbdc9-151">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-151">Select Windows 10 as the operating system.</span></span> 
    - <span data-ttu-id="bbdc9-152">В поле **Метод развертывания** выберите скрипты бортового VDI для неохраняющих конечных точек.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-152">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    - <span data-ttu-id="bbdc9-153">Нажмите **кнопку Скачать пакет** и сохранить файл .zip.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-153">Click **Download package** and save the .zip file.</span></span> 
2. <span data-ttu-id="bbdc9-154">Извлечение содержимого файла .zip в общее, только для чтения расположение, которое можно получить на устройстве.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="bbdc9-155">У вас должна быть папка **OptionalParamsPolicy** и файлы **WindowsDefenderATPOnboardingScript.cmd** **иOnboard-NonPersistentMachine.ps1.**</span><span class="sxs-lookup"><span data-stu-id="bbdc9-155">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="bbdc9-156">**При запуске виртуальной машины используйте консоль управления групповой политикой для запуска сценария**</span><span class="sxs-lookup"><span data-stu-id="bbdc9-156">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>
1. <span data-ttu-id="bbdc9-157">Откройте консоль управления групповой политикой (GPMC), щелкните правой кнопкой мыши объект групповой политики (GPO), который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-157">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>
1. <span data-ttu-id="bbdc9-158">В редакторе управления групповой политикой перейдите **к** настройкам панели \> **управления настройками** конфигурации \> компьютера.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-158">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 
1. <span data-ttu-id="bbdc9-159">Щелкните правой кнопкой мыши **Запланированные задачи,** нажмите **кнопку New** и нажмите **кнопку** Немедленная задача (по крайней мере Windows 7).</span><span class="sxs-lookup"><span data-stu-id="bbdc9-159">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 
1. <span data-ttu-id="bbdc9-160">В открываемом окне Задача перейдите на **вкладку General.** В **статье Параметры безопасности** нажмите **кнопку Изменить пользователя или группу** и введите SYSTEM.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-160">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="bbdc9-161">Щелкните **Check Names** и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-161">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="bbdc9-162">NT AUTHORITY\SYSTEM отображается в качестве учетной записи пользователя, как будет работать задача.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-162">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 
1. <span data-ttu-id="bbdc9-163">Выберите **Выполнить, вошел** ли пользователь или нет, и проверьте поле Выполнить с **самыми** высокими привилегиями.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-163">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 
1. <span data-ttu-id="bbdc9-164">Перейдите на вкладку **Действия** и нажмите **кнопку New**.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-164">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="bbdc9-165">**Убедитесь, что программа Start** выбрана в поле Действия.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-165">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="bbdc9-166">Введите следующее:</span><span class="sxs-lookup"><span data-stu-id="bbdc9-166">Enter the following:</span></span> 

> <span data-ttu-id="bbdc9-167">Действие = "Запуск программы"</span><span class="sxs-lookup"><span data-stu-id="bbdc9-167">Action = "Start a program"</span></span> <br>
> <span data-ttu-id="bbdc9-168">Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span><span class="sxs-lookup"><span data-stu-id="bbdc9-168">Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span></span> <br>
> <span data-ttu-id="bbdc9-169">Добавление аргументов (необязательный) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"</span><span class="sxs-lookup"><span data-stu-id="bbdc9-169">Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"</span></span>

<span data-ttu-id="bbdc9-170">Нажмите **кнопку ОК** и закрой все открытые окна GPMC.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-170">Click **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="bbdc9-171">*Сценарий 3. Использование средств управления*</span><span class="sxs-lookup"><span data-stu-id="bbdc9-171">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="bbdc9-172">Если вы планируете управлять компьютерами с помощью средства управления, вы можете использовать бортовые устройства с помощью Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-172">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="bbdc9-173">Дополнительные сведения см. в дополнительных сведениях: [на борту устройств с Windows 10 с помощью Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span><span class="sxs-lookup"><span data-stu-id="bbdc9-173">For more information, see: [Onboard Windows 10 devices using Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span></span> 

> [!WARNING]
> <span data-ttu-id="bbdc9-174">Если вы планируете использовать правила уменьшения [поверхности](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)атаки, обратите внимание, что правило "Блокируйте создание процессов, происходящих из команд[PSExec](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)и WMI", не следует использовать, так как это несовместимо с управлением с помощью Microsoft Endpoint Configuration Manager, так как это правило блокирует WMI команды, используемые клиентом Configuration Manager для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-174">If you plan to use [Attack Surface reduction Rules](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction), please note that rule “[Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used as it is incompatible with management through Microsoft Endpoint Configuration Manager because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="bbdc9-175">После работы на устройстве можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вошел в службу.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-175">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="bbdc9-176">Дополнительные сведения см. в таблице Выполнить тест обнаружения на недавно созданном [устройстве Microsoft Defender для конечных точек.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)</span><span class="sxs-lookup"><span data-stu-id="bbdc9-176">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="bbdc9-177">Пометка машин при создании золотого изображения</span><span class="sxs-lookup"><span data-stu-id="bbdc9-177">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="bbdc9-178">В рамках вашей работы в центре безопасности Майкрософт может потребоваться установить тег машины для более легкой дифференцированности машин WVD.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-178">As part of your onboarding, you may want to consider setting a machine tag to be able to differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="bbdc9-179">Дополнительные сведения см. в [добавлении тегов устройств, установив ключевое значение реестра.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value)</span><span class="sxs-lookup"><span data-stu-id="bbdc9-179">For more information, see [Add device tags by setting a registry key value](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="bbdc9-180">Другие рекомендуемые параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="bbdc9-180">Other recommended configuration settings</span></span> 

<span data-ttu-id="bbdc9-181">При создании золотого изображения может потребоваться также настроить начальные параметры защиты.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-181">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="bbdc9-182">Дополнительные сведения см. [в других рекомендуемых параметрах конфигурации.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings)</span><span class="sxs-lookup"><span data-stu-id="bbdc9-182">For more information, see [Other recommended configuration settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="bbdc9-183">Кроме того, если вы используете профили пользователей FSlogix, рекомендуем исключить из всегдай защиты следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="bbdc9-183">In addition, if you are using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="bbdc9-184">**Исключение файлов:**</span><span class="sxs-lookup"><span data-stu-id="bbdc9-184">**Exclude Files:**</span></span> 

> <span data-ttu-id="bbdc9-185">%ProgramFiles%\FSLogix\Apps\frxdrv.sys</span><span class="sxs-lookup"><span data-stu-id="bbdc9-185">%ProgramFiles%\FSLogix\Apps\frxdrv.sys</span></span> <br>
> <span data-ttu-id="bbdc9-186">%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys</span><span class="sxs-lookup"><span data-stu-id="bbdc9-186">%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys</span></span> <br>
> <span data-ttu-id="bbdc9-187">%ProgramFiles%\FSLogix\Apps\frxccd.sys</span><span class="sxs-lookup"><span data-stu-id="bbdc9-187">%ProgramFiles%\FSLogix\Apps\frxccd.sys</span></span> <br>
> <span data-ttu-id="bbdc9-188">%TEMP%. \* VHD</span><span class="sxs-lookup"><span data-stu-id="bbdc9-188">%TEMP%\*.VHD</span></span> <br>
> <span data-ttu-id="bbdc9-189">%TEMP%. \* VHDX</span><span class="sxs-lookup"><span data-stu-id="bbdc9-189">%TEMP%\*.VHDX</span></span> <br>
> <span data-ttu-id="bbdc9-190">%Windir%\TEMP \* . VHD</span><span class="sxs-lookup"><span data-stu-id="bbdc9-190">%Windir%\TEMP\*.VHD</span></span> <br>
> <span data-ttu-id="bbdc9-191">%Windir%\TEMP \* . VHDX</span><span class="sxs-lookup"><span data-stu-id="bbdc9-191">%Windir%\TEMP\*.VHDX</span></span> <br>
> <span data-ttu-id="bbdc9-192">\\storageaccount.file.core.windows.net\share \* \* . VHD</span><span class="sxs-lookup"><span data-stu-id="bbdc9-192">\\storageaccount.file.core.windows.net\share\*\*.VHD</span></span> <br>
> <span data-ttu-id="bbdc9-193">\\storageaccount.file.core.windows.net\share \* \* . VHDX</span><span class="sxs-lookup"><span data-stu-id="bbdc9-193">\\storageaccount.file.core.windows.net\share\*\*.VHDX</span></span> <br>

<span data-ttu-id="bbdc9-194">**Исключить процессы:**</span><span class="sxs-lookup"><span data-stu-id="bbdc9-194">**Exclude Processes:**</span></span>

> <span data-ttu-id="bbdc9-195">%ProgramFiles%\FSLogix\Apps\frxccd.exe</span><span class="sxs-lookup"><span data-stu-id="bbdc9-195">%ProgramFiles%\FSLogix\Apps\frxccd.exe</span></span> <br>
> <span data-ttu-id="bbdc9-196">%ProgramFiles%\FSLogix\Apps\frxccds.exe</span><span class="sxs-lookup"><span data-stu-id="bbdc9-196">%ProgramFiles%\FSLogix\Apps\frxccds.exe</span></span> <br>
> <span data-ttu-id="bbdc9-197">%ProgramFiles%\FSLogix\Apps\frxsvc.exe</span><span class="sxs-lookup"><span data-stu-id="bbdc9-197">%ProgramFiles%\FSLogix\Apps\frxsvc.exe</span></span> <br>

#### <a name="licensing-requirements"></a><span data-ttu-id="bbdc9-198">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="bbdc9-198">Licensing requirements</span></span> 

<span data-ttu-id="bbdc9-199">Windows 10 Multi-session — это клиентская ОС.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-199">Windows 10 Multi-session is a client OS.</span></span> <span data-ttu-id="bbdc9-200">Требования к лицензированию для Microsoft Defender для конечной точки можно найти по: [Лицензионные требования.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="bbdc9-200">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>