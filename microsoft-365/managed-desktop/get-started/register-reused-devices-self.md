---
title: Самостоятельная регистрация существующих устройств
description: Зарегистрируйте повторноиспользованые устройства, которыми вы, возможно, уже управляете, чтобы ими могли управлять компьютеры, управляемые Майкрософт
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840519"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="bcd16-103">Самостоятельная регистрация существующих устройств</span><span class="sxs-lookup"><span data-stu-id="bcd16-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="bcd16-104">В этом разделе описаны действия, которые необходимо предпринять для повторного использования уже у вас устройств и их регистрации на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bcd16-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="bcd16-105">Если вы работаете с совершенно новыми устройствами, самостоятельно выполните действия, которые необходимо предпринять при регистрации новых устройств на компьютерах, управляемых [Майкрософт.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="bcd16-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="bcd16-106">Процесс регистрации устройств для партнеров описан в шагах для [партнеров.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="bcd16-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="bcd16-107">Компьютеры, управляемые Майкрософт, могут работать с совершенно новыми устройствами или вы можете повторно использовать устройства, которые у вас уже есть (для этого потребуется их повторное использование).</span><span class="sxs-lookup"><span data-stu-id="bcd16-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="bcd16-108">Устройства можно зарегистрировать на портале Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="bcd16-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="bcd16-109">Подготовка к регистрации существующих устройств</span><span class="sxs-lookup"><span data-stu-id="bcd16-109">Prepare to register existing devices</span></span>


<span data-ttu-id="bcd16-110">Чтобы зарегистрировать существующие устройства, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bcd16-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="bcd16-111">Получите аппаратный hash для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="bcd16-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="bcd16-112">Объединение данных с hash</span><span class="sxs-lookup"><span data-stu-id="bcd16-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="bcd16-113">[Зарегистрируйте устройства на компьютере, управляемом Майкрософт.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="bcd16-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="bcd16-114">Убедитесь, что изображение правильное.</span><span class="sxs-lookup"><span data-stu-id="bcd16-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="bcd16-115">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="bcd16-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="bcd16-116">Получение аппаратного hash</span><span class="sxs-lookup"><span data-stu-id="bcd16-116">Obtain the hardware hash</span></span>

<span data-ttu-id="bcd16-117">Компьютер, управляемый Майкрософт, идентифицирует каждое устройство уникальным образом, ссылаясь на его аппаратный hash.</span><span class="sxs-lookup"><span data-stu-id="bcd16-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="bcd16-118">У вас есть четыре варианта получения этих сведений с уже использующихся устройств:</span><span class="sxs-lookup"><span data-stu-id="bcd16-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="bcd16-119">Задайте поставщику оборудования файл регистрации AutoPilot, который будет включать в себя аппаратные хеши.</span><span class="sxs-lookup"><span data-stu-id="bcd16-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="bcd16-120">Сбор сведений в [Microsoft Endpoint Configuration Manager.](#microsoft-endpoint-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="bcd16-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="bcd16-121">Запустите Windows PowerShell с помощью [Active Directory](#active-directory-powershell-script-method) [](#manual-powershell-script-method) или вручную на каждом устройстве и соберите результаты в файле.</span><span class="sxs-lookup"><span data-stu-id="bcd16-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="bcd16-122">Запустите каждое устройство, но не завершите настройку Windows, и соберите хеши на [съемный флэш-накопитель.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="bcd16-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="bcd16-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bcd16-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="bcd16-124">С помощью Microsoft Endpoint Configuration Manager вы можете собирать хеши оборудования с существующих устройств, которые необходимо зарегистрировать на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bcd16-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcd16-125">Все устройства, для которые вы хотите получить эти сведения, должны работать под управлением Windows 10 версии 1703 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="bcd16-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="bcd16-126">Если вы выполнили все эти условия, вы можете собрать информацию, вы выполнили следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bcd16-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="bcd16-127">В консоли Configuration Manager выберите **"Мониторинг".**</span><span class="sxs-lookup"><span data-stu-id="bcd16-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="bcd16-128">В рабочей области мониторинга разорвем узел **"Отчеты",** **"Отчеты"** и выберите узел **"Оборудование — общие".**</span><span class="sxs-lookup"><span data-stu-id="bcd16-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="bcd16-129">Запустите отчет, **сведения об устройстве Windows Autopilot** и просмотрете результаты.</span><span class="sxs-lookup"><span data-stu-id="bcd16-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="bcd16-130">В представлении отчета выберите **значок** "Экспорт" и выберите параметр **CSV (через запятую).**</span><span class="sxs-lookup"><span data-stu-id="bcd16-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="bcd16-131">После сохранения файла вам потребуется отфильтровать результаты только на тех устройствах, которые вы планируете зарегистрировать на компьютере, управляемом Майкрософт, и отправить данные на компьютер, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bcd16-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="bcd16-132">Откройте Microsoft Endpoint Manager  и перейдите в меню "Устройства", найдите раздел "Управляемые Майкрософт компьютеры" и выберите **"Устройства".**</span><span class="sxs-lookup"><span data-stu-id="bcd16-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="bcd16-133">Выберите **+Регистрация устройств,** что открывает окно регистрации новых устройств.</span><span class="sxs-lookup"><span data-stu-id="bcd16-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="bcd16-134">Дополнительные [сведения о регистрации устройств](#register-devices-by-using-the-admin-portal) можно найти на портале администрирования.</span><span class="sxs-lookup"><span data-stu-id="bcd16-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="bcd16-135">Метод скрипта Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcd16-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="bcd16-136">В среде Active Directory с помощью powerShell можно удаленно собирать информацию с устройств в группах Active Directory с `Get-WindowsAutoPilotInfo` помощью WinRM.</span><span class="sxs-lookup"><span data-stu-id="bcd16-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="bcd16-137">Вы также можете использовать этотлет и получить отфильтрованные результаты для определенного имени аппаратной модели, `Get-AD Computer` включенного в каталог.</span><span class="sxs-lookup"><span data-stu-id="bcd16-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="bcd16-138">Прежде чем продолжить, сначала подтвердим эти предварительные условия, а затем вы сможете перейти к указанным далее шагам.</span><span class="sxs-lookup"><span data-stu-id="bcd16-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="bcd16-139">WinRM включен.</span><span class="sxs-lookup"><span data-stu-id="bcd16-139">WinRM is enabled.</span></span>
- <span data-ttu-id="bcd16-140">Устройства, которые вы хотите зарегистрировать, активны в сети (то есть они не отключены или отключены).</span><span class="sxs-lookup"><span data-stu-id="bcd16-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="bcd16-141">Убедитесь, что у вас есть параметр учетных данных домена, который имеет разрешение на удаленное выполнение на устройствах.</span><span class="sxs-lookup"><span data-stu-id="bcd16-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="bcd16-142">Убедитесь, что брандмауэр Windows разрешает доступ к WMI.</span><span class="sxs-lookup"><span data-stu-id="bcd16-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="bcd16-143">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bcd16-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="bcd16-144">Откройте панель **Защитник Windows брандмауэра** и выберите "Разрешить приложение или функцию **через брандмауэр Защитник Windows брандмауэра".**</span><span class="sxs-lookup"><span data-stu-id="bcd16-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="bcd16-145">Найдите **инструментарий управления Windows (WMI)** в списке, в качестве частного и открытого, а затем выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="bcd16-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="bcd16-146">Откройте запрос PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="bcd16-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="bcd16-147">Запустите *один из* этих сценариев:</span><span class="sxs-lookup"><span data-stu-id="bcd16-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="bcd16-148">Доступ к каталогам, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="bcd16-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="bcd16-149">Удалите записи для каждого устройства из *всех* каталогов, включая доменные службы Windows Server Active Directory и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bcd16-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="bcd16-150">Следует помнить, что процесс полного удаления может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="bcd16-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="bcd16-151">Службы управления доступом, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="bcd16-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="bcd16-152">Удалите записи для  каждого устройства из всех служб управления, включая Microsoft Endpoint Configuration Manager, Microsoft Intune и Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="bcd16-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="bcd16-153">Следует помнить, что процесс полного удаления может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="bcd16-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="bcd16-154">Теперь вы можете зарегистрировать [устройства.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="bcd16-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="bcd16-155">Метод скрипта PowerShell вручную</span><span class="sxs-lookup"><span data-stu-id="bcd16-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="bcd16-156">Откройте запрос PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="bcd16-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="bcd16-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="bcd16-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="bcd16-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="bcd16-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="bcd16-159">Объединение данных с hash.</span><span class="sxs-lookup"><span data-stu-id="bcd16-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="bcd16-160">Метод Флэш-накопителя</span><span class="sxs-lookup"><span data-stu-id="bcd16-160">Flash drive method</span></span>

1. <span data-ttu-id="bcd16-161">Вставьте USB-накопитель на устройство, которое не регистрируется.</span><span class="sxs-lookup"><span data-stu-id="bcd16-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="bcd16-162">Откройте запрос PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="bcd16-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="bcd16-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="bcd16-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="bcd16-164">Включите устройство, которое вы регистрируете, *но не запускайте настройку.*</span><span class="sxs-lookup"><span data-stu-id="bcd16-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="bcd16-165">Если вы случайно запустите установку, вам придется сбросить устройство или сделать его повторно.</span><span class="sxs-lookup"><span data-stu-id="bcd16-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="bcd16-166">Вставьте USB-накопитель и нажмите shift + F10.</span><span class="sxs-lookup"><span data-stu-id="bcd16-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="bcd16-167">Откройте запрос PowerShell с правами администратора и запустите `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="bcd16-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="bcd16-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="bcd16-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="bcd16-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="bcd16-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="bcd16-170">Удалите USB-накопитель, а затем выключите устройство, загонив `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="bcd16-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="bcd16-171">Объединение данных с hash.</span><span class="sxs-lookup"><span data-stu-id="bcd16-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="bcd16-172">Не велись на устройстве, которое вы регистрируете снова, пока не завершите регистрацию для него.</span><span class="sxs-lookup"><span data-stu-id="bcd16-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="bcd16-173">Объединение данных с hash</span><span class="sxs-lookup"><span data-stu-id="bcd16-173">Merge hash data</span></span>

<span data-ttu-id="bcd16-174">Если данные об оборудовании были собраны с помощью ручного метода PowerShell или флэш-накопителя, для завершения регистрации необходимо объединить данные в CSV-файлы в один файл.</span><span class="sxs-lookup"><span data-stu-id="bcd16-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="bcd16-175">Вот пример сценария PowerShell, чтобы у вас было простое решение:</span><span class="sxs-lookup"><span data-stu-id="bcd16-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="bcd16-176">После слияния данных с помощью hash в один CSV-файл вы можете зарегистрировать [устройства.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="bcd16-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="bcd16-177">Регистрация устройств с помощью портала администрирования</span><span class="sxs-lookup"><span data-stu-id="bcd16-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="bcd16-178">В [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)выберите **"Устройства"** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="bcd16-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="bcd16-179">Наберем раздел меню "Управляемые Майкрософт компьютеры" и выберите **"Устройства".**</span><span class="sxs-lookup"><span data-stu-id="bcd16-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="bcd16-180">В рабочей области "Управляемые настольными устройствами Майкрософт" выберите **+зарегистрируйте** устройства, после чего откроется окно регистрации новых устройств.</span><span class="sxs-lookup"><span data-stu-id="bcd16-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="bcd16-181">Выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bcd16-181">Follow these steps:</span></span>

1. <span data-ttu-id="bcd16-182">При **отправке** файла ука между файлами у вас есть путь к ранее созданному CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="bcd16-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="bcd16-183">Выберите **"Регистрация устройств".**</span><span class="sxs-lookup"><span data-stu-id="bcd16-183">Select **Register devices**.</span></span> <span data-ttu-id="bcd16-184">Система добавит устройства в список устройств в blade **"Устройства"** с пометкой "Ожидание **регистрации".**</span><span class="sxs-lookup"><span data-stu-id="bcd16-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="bcd16-185">Регистрация обычно занимает менее 10 минут, и при  успешном запуске устройство будет показываться как готовое для пользователя. Это означает, что оно готово к использованию.</span><span class="sxs-lookup"><span data-stu-id="bcd16-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="bcd16-186">Вы можете отслеживать ход регистрации устройств на главной странице.</span><span class="sxs-lookup"><span data-stu-id="bcd16-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="bcd16-187">Возможные состояния, о них сообщается:</span><span class="sxs-lookup"><span data-stu-id="bcd16-187">Possible states reported there include:</span></span>

| <span data-ttu-id="bcd16-188">Состояние</span><span class="sxs-lookup"><span data-stu-id="bcd16-188">State</span></span> | <span data-ttu-id="bcd16-189">Описание</span><span class="sxs-lookup"><span data-stu-id="bcd16-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="bcd16-190">Ожидающих регистрации</span><span class="sxs-lookup"><span data-stu-id="bcd16-190">Registration Pending</span></span> | <span data-ttu-id="bcd16-191">Регистрация еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="bcd16-191">Registration is not done yet.</span></span> <span data-ttu-id="bcd16-192">Проверьте позже.</span><span class="sxs-lookup"><span data-stu-id="bcd16-192">Check back later.</span></span> |
| <span data-ttu-id="bcd16-193">Сбой регистрации</span><span class="sxs-lookup"><span data-stu-id="bcd16-193">Registration failed</span></span> | <span data-ttu-id="bcd16-194">Не удалось завершить регистрацию.</span><span class="sxs-lookup"><span data-stu-id="bcd16-194">Registration could not be completed.</span></span> <span data-ttu-id="bcd16-195">Дополнительные [сведения об устранении неполадок регистрации](#troubleshooting-device-registration) устройств.</span><span class="sxs-lookup"><span data-stu-id="bcd16-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="bcd16-196">Готово для пользователя</span><span class="sxs-lookup"><span data-stu-id="bcd16-196">Ready for user</span></span> | <span data-ttu-id="bcd16-197">Регистрация была успешной, и теперь устройство готово к доставке пользователю.</span><span class="sxs-lookup"><span data-stu-id="bcd16-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="bcd16-198">Компьютеры, управляемые Майкрософт, будут проходить их первую подготовку, поэтому нет необходимости в дальнейших подготовительные процессы.</span><span class="sxs-lookup"><span data-stu-id="bcd16-198">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="bcd16-199">Активное</span><span class="sxs-lookup"><span data-stu-id="bcd16-199">Active</span></span> | <span data-ttu-id="bcd16-200">Устройство было доставлено пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="bcd16-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="bcd16-201">Это также означает, что они регулярно используют устройство.</span><span class="sxs-lookup"><span data-stu-id="bcd16-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="bcd16-202">Неактивный</span><span class="sxs-lookup"><span data-stu-id="bcd16-202">Inactive</span></span> | <span data-ttu-id="bcd16-203">Устройство было доставлено пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="bcd16-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="bcd16-204">Однако они не использовали устройство в последнее время (за последние 7 дней).</span><span class="sxs-lookup"><span data-stu-id="bcd16-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="bcd16-205">Устранение неполадок регистрации устройств</span><span class="sxs-lookup"><span data-stu-id="bcd16-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="bcd16-206">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="bcd16-206">Error message</span></span> | <span data-ttu-id="bcd16-207">Сведения</span><span class="sxs-lookup"><span data-stu-id="bcd16-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="bcd16-208">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="bcd16-208">Device not found</span></span> | <span data-ttu-id="bcd16-209">Нам не удалось зарегистрировать это устройство, так как нам не удалось найти соответствие для предоставленного производителя, модели или серийного номера.</span><span class="sxs-lookup"><span data-stu-id="bcd16-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="bcd16-210">Подтвердите эти значения у поставщика устройства.</span><span class="sxs-lookup"><span data-stu-id="bcd16-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="bcd16-211">Не является допустимым аппаратный hash</span><span class="sxs-lookup"><span data-stu-id="bcd16-211">Hardware hash not valid</span></span> | <span data-ttu-id="bcd16-212">Аппаратный hash, предоставленный для этого устройства, был отформатирован неправильно.</span><span class="sxs-lookup"><span data-stu-id="bcd16-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="bcd16-213">Дважды проверьте аппаратный hash и затем повторно откройте его.</span><span class="sxs-lookup"><span data-stu-id="bcd16-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="bcd16-214">Устройство уже зарегистрировано</span><span class="sxs-lookup"><span data-stu-id="bcd16-214">Device already registered</span></span> | <span data-ttu-id="bcd16-215">Это устройство уже зарегистрировано в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bcd16-215">This device is already registered to your organization.</span></span> <span data-ttu-id="bcd16-216">Дальнейшие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="bcd16-216">No further action required.</span></span> |
| <span data-ttu-id="bcd16-217">Устройство, заявленное другой организацией</span><span class="sxs-lookup"><span data-stu-id="bcd16-217">Device claimed by another organization</span></span> | <span data-ttu-id="bcd16-218">Это устройство уже было заявлено другой организацией.</span><span class="sxs-lookup"><span data-stu-id="bcd16-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="bcd16-219">Обратитесь к поставщику устройства.</span><span class="sxs-lookup"><span data-stu-id="bcd16-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="bcd16-220">Непредвиденная ошибка</span><span class="sxs-lookup"><span data-stu-id="bcd16-220">Unexpected error</span></span> | <span data-ttu-id="bcd16-221">Не удалось автоматически обработать запрос.</span><span class="sxs-lookup"><span data-stu-id="bcd16-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="bcd16-222">Обратитесь в службу поддержки ИД запроса: <requestId></span><span class="sxs-lookup"><span data-stu-id="bcd16-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="bcd16-223">Проверка изображения</span><span class="sxs-lookup"><span data-stu-id="bcd16-223">Check the image</span></span>

<span data-ttu-id="bcd16-224">Если ваше устройство пришло от партнера microsoft Managed Desktop, образ должен быть правильным.</span><span class="sxs-lookup"><span data-stu-id="bcd16-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="bcd16-225">При желании вы также можете применить образ самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="bcd16-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="bcd16-226">Для начала обратитесь к представителю Майкрософт, с помощью который вы работаете, и он предоставит вам расположение и действия для применения образа.</span><span class="sxs-lookup"><span data-stu-id="bcd16-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="bcd16-227">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="bcd16-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcd16-228">Перед тем как передать устройство пользователю, убедитесь, что вы получили и применили соответствующие лицензии [для](../get-ready/prerequisites.md) этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="bcd16-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="bcd16-229">Если применяются все лицензии, вы можете подготовить пользователей к использованию [устройств,](get-started-devices.md)а затем пользователь сможет запустить устройство и перейти к настройке Windows.</span><span class="sxs-lookup"><span data-stu-id="bcd16-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









