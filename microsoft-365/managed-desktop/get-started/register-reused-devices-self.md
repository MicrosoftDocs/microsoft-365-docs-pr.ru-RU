---
title: Самостоятельная регистрация существующих устройств
description: Зарегистрируйте повторноиспользованые устройства, которые у вас уже есть, чтобы управлять ими с помощью компьютеры, управляемые Майкрософт
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 21b0062a337dbeb3c7dec8b715971dbbc4917db1
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893279"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="5d2fc-103">Самостоятельная регистрация существующих устройств</span><span class="sxs-lookup"><span data-stu-id="5d2fc-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="5d2fc-104">В этом разделе описываются действия, которые необходимо предпринять для повторного использования уже у вас устройств и их регистрации в компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="5d2fc-105">Если вы работаете с совершенно новыми устройствами, выполните действия в Зарегистрировать новые устройства [в компьютеры, управляемые Майкрософт самостоятельно.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="5d2fc-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="5d2fc-106">Процесс регистрации устройств для партнеров задокументирован в ["Шаги для партнеров".](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="5d2fc-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="5d2fc-107">компьютеры, управляемые Майкрософт можно работать с совершенно новыми устройствами или повторно использовать устройства, которые у вас уже есть (для чего потребуется повторное их повторное использование).</span><span class="sxs-lookup"><span data-stu-id="5d2fc-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="5d2fc-108">Вы можете зарегистрировать устройства с компьютеры, управляемые Майкрософт на Microsoft Endpoint Manager портале.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="5d2fc-109">Подготовка к регистрации существующих устройств</span><span class="sxs-lookup"><span data-stu-id="5d2fc-109">Prepare to register existing devices</span></span>


<span data-ttu-id="5d2fc-110">Чтобы зарегистрировать существующие устройства, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5d2fc-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="5d2fc-111">Получение аппаратного хаш для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="5d2fc-112">Объединение данных с hash</span><span class="sxs-lookup"><span data-stu-id="5d2fc-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="5d2fc-113">[Регистрация устройств в компьютеры, управляемые Майкрософт](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="5d2fc-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="5d2fc-114">Дважды проверьте правильность изображения.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="5d2fc-115">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="5d2fc-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="5d2fc-116">Получение аппаратного хаш</span><span class="sxs-lookup"><span data-stu-id="5d2fc-116">Obtain the hardware hash</span></span>

<span data-ttu-id="5d2fc-117">компьютеры, управляемые Майкрософт определяет каждое устройство уникальным образом, ссылаясь на его аппаратный хаш.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="5d2fc-118">У вас есть четыре варианта получения этих сведений с устройств, которые вы уже используете:</span><span class="sxs-lookup"><span data-stu-id="5d2fc-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="5d2fc-119">Попросите поставщика OEM для файла регистрации АвтоПилота, который будет включать в себя хеши оборудования.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="5d2fc-120">Сбор сведений [в Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="5d2fc-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="5d2fc-121">Запустите Windows PowerShell - с помощью [Active Directory](#active-directory-powershell-script-method) или вручную на каждом устройстве - и соберите результаты в файле. [](#manual-powershell-script-method)</span><span class="sxs-lookup"><span data-stu-id="5d2fc-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="5d2fc-122">Запустите каждое устройство, но не выполните Windows настройки и соберите хеши на съемных [флэш-накопителях.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="5d2fc-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="5d2fc-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5d2fc-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="5d2fc-124">С помощью Microsoft Endpoint Configuration Manager можно собирать электронные хеши с существующих устройств, которые необходимо зарегистрировать компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d2fc-125">Любые устройства, для получения данных для Windows 10 версии 1703 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="5d2fc-126">Если вы выполнили все эти условия, вы готовы собрать информацию, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="5d2fc-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="5d2fc-127">В консоли Configuration Manager выберите **Мониторинг.**</span><span class="sxs-lookup"><span data-stu-id="5d2fc-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="5d2fc-128">В рабочей области Мониторинга разо расширении узла **Отчеты,** расширении **отчетов** и выборе **узла Hardware — General.**</span><span class="sxs-lookup"><span data-stu-id="5d2fc-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="5d2fc-129">Запустите отчет, **Windows сведения об** устройстве автопилота и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="5d2fc-130">В представлении отчета выберите значок **Экспорт** и выберите **параметр CSV (запятой).**</span><span class="sxs-lookup"><span data-stu-id="5d2fc-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="5d2fc-131">После сохранения файла необходимо отфильтровать результаты только для тех устройств, которые вы планируете зарегистрировать с помощью компьютеры, управляемые Майкрософт и загрузить данные в компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="5d2fc-132">Откройте Microsoft Endpoint Manager и перейдите в меню **Devices,** затем найдите раздел компьютеры, управляемые Майкрософт и выберите **Устройства.**</span><span class="sxs-lookup"><span data-stu-id="5d2fc-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="5d2fc-133">Выберите **+ Регистрируйте устройства,** которые открывают флайер для регистрации новых устройств.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="5d2fc-134">Дополнительные сведения можно получить на устройствах Register с помощью [портала администрирования.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="5d2fc-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="5d2fc-135">Метод сценария Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d2fc-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="5d2fc-136">В среде Active Directory можно использовать комлет PowerShell для удаленного сбора информации с устройств в Active Directory Groups с помощью `Get-WindowsAutoPilotInfo` WinRM.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="5d2fc-137">Вы также можете использовать cmdlet и получать отфильтрованные результаты для определенного имени модели `Get-AD Computer` оборудования, включенного в каталог.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="5d2fc-138">Прежде чем приступить, сначала подтвердим эти условия, а затем приступить к шагам:</span><span class="sxs-lookup"><span data-stu-id="5d2fc-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="5d2fc-139">WinRM включен.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-139">WinRM is enabled.</span></span>
- <span data-ttu-id="5d2fc-140">Устройства, которые необходимо зарегистрировать, активны в сети (то есть они не отключены или отключены).</span><span class="sxs-lookup"><span data-stu-id="5d2fc-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="5d2fc-141">Убедитесь, что у вас есть параметр учетных данных домена, который имеет разрешение на удаленное выполнение на устройствах.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="5d2fc-142">Убедитесь, что Windows брандмауэр позволяет получить доступ к WMI.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="5d2fc-143">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5d2fc-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="5d2fc-144">Откройте панель **брандмауэр Защитника Windows** и выберите Разрешить приложение или функцию **через брандмауэр Защитника Windows.**</span><span class="sxs-lookup"><span data-stu-id="5d2fc-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="5d2fc-145">Найдите **Windows инструментов управления (WMI)** в списке, встройку как для частных, так и для общедоступных, а затем выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="5d2fc-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="5d2fc-146">Откройте запрос PowerShell с административными правами.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="5d2fc-147">Запустите *один* из этих скриптов:</span><span class="sxs-lookup"><span data-stu-id="5d2fc-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="5d2fc-148">Доступ к любым каталогам, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="5d2fc-149">Удалите записи для  каждого устройства из всех каталогов, в том числе Windows Службы домена Active Directory и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="5d2fc-150">Следует помнить, что для полного процесса удаления может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="5d2fc-151">Доступ к службам управления, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="5d2fc-152">Удалите записи для  каждого устройства из всех служб управления, включая Microsoft Endpoint Configuration Manager, Microsoft Intune и Windows автопилот.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="5d2fc-153">Следует помнить, что для полного процесса удаления может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="5d2fc-154">Теперь вы можете перейти к [регистрации устройств.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="5d2fc-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="5d2fc-155">Метод скрипта Manual PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d2fc-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="5d2fc-156">Откройте запрос PowerShell с административными правами.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="5d2fc-157">Запуск `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="5d2fc-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="5d2fc-158">Запуск `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="5d2fc-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="5d2fc-159">Объединение данных с hash.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="5d2fc-160">Метод флэш-накопителя</span><span class="sxs-lookup"><span data-stu-id="5d2fc-160">Flash drive method</span></span>

1. <span data-ttu-id="5d2fc-161">На устройстве, помимо регистра, вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="5d2fc-162">Откройте запрос PowerShell с административными правами.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="5d2fc-163">Запуск `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="5d2fc-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="5d2fc-164">Включи устройство, которое вы регистрируете, но *не запустите настройку.*</span><span class="sxs-lookup"><span data-stu-id="5d2fc-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="5d2fc-165">Если вы случайно запустите установку, вам придется сбросить или перезагрузить устройство.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="5d2fc-166">Вставьте USB-накопитель, а затем нажмите SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="5d2fc-167">Откройте запрос PowerShell с административными правами и запустите `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="5d2fc-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="5d2fc-168">Запуск `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="5d2fc-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="5d2fc-169">Запуск `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="5d2fc-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="5d2fc-170">Удалите USB-накопитель, а затем отключите устройство при запуске `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="5d2fc-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="5d2fc-171">Объединение данных с hash.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="5d2fc-172">Не делайте питания на устройстве, которое вы регистрируете снова, пока не завершите регистрацию для него.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="5d2fc-173">Объединение данных с hash</span><span class="sxs-lookup"><span data-stu-id="5d2fc-173">Merge hash data</span></span>

<span data-ttu-id="5d2fc-174">Если вы собирали данные о аппаратном хаше с помощью методов ручного PowerShell или флэш-накопителя, для завершения регистрации необходимо объединить данные в CSV-файлах.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="5d2fc-175">Вот пример сценария PowerShell, чтобы у вас было легко:</span><span class="sxs-lookup"><span data-stu-id="5d2fc-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="5d2fc-176">С помощью слитых в один CSV-файл данных можно зарегистрировать [устройства.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="5d2fc-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


## <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="5d2fc-177">Регистрация устройств с помощью портала администрирования</span><span class="sxs-lookup"><span data-stu-id="5d2fc-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="5d2fc-178">В [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)выберите **Устройства** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="5d2fc-179">Посмотрите раздел компьютеры, управляемые Майкрософт меню и выберите **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="5d2fc-180">В рабочей компьютеры, управляемые Майкрософт Устройства выберите **+ Регистрация** устройств, что открывает флайер для регистрации новых устройств.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="5d2fc-181">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-181">Follow these steps:</span></span>

1. <span data-ttu-id="5d2fc-182">В **файле отправки** у вас есть путь к созданному ранее CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="5d2fc-183">Выберите профиль [устройства в](../service-description/profiles.md) выпадающее меню.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-183">Select a [device profile](../service-description/profiles.md) in the drop-down menu.</span></span>
3. <span data-ttu-id="5d2fc-184">Выберите **устройства Register.**</span><span class="sxs-lookup"><span data-stu-id="5d2fc-184">Select **Register devices**.</span></span> <span data-ttu-id="5d2fc-185">Система добавит устройства в список устройств на лезвии **Devices,** помеченное как **Регистрация в ожидании.**</span><span class="sxs-lookup"><span data-stu-id="5d2fc-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="5d2fc-186">Регистрация обычно занимает менее 10 минут, и при успешном запуске устройство будет показываться как **Готовое** для пользователя, что означает, что оно готово и ожидает, когда пользователь начнет использовать.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>

> [!NOTE]
> <span data-ttu-id="5d2fc-187">Если вы вручную измените Azure Active Directory (AAD) для устройства, оно будет автоматически назначено группе для профиля устройства и удалено из конфликтующих групп.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-187">If you manually change the Azure Active Directory (AAD) group membership of a device, it will be automatically reassigned to the group for its device profile and removed from any conflicting groups.</span></span>

<span data-ttu-id="5d2fc-188">Вы можете отслеживать ход регистрации устройств на главной странице.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-188">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="5d2fc-189">Возможные состояния, которые там сообщаются, включают:</span><span class="sxs-lookup"><span data-stu-id="5d2fc-189">Possible states reported there include:</span></span>

| <span data-ttu-id="5d2fc-190">Состояние</span><span class="sxs-lookup"><span data-stu-id="5d2fc-190">State</span></span> | <span data-ttu-id="5d2fc-191">Описание</span><span class="sxs-lookup"><span data-stu-id="5d2fc-191">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="5d2fc-192">Регистрация в ожидании</span><span class="sxs-lookup"><span data-stu-id="5d2fc-192">Registration Pending</span></span> | <span data-ttu-id="5d2fc-193">Регистрация еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-193">Registration is not done yet.</span></span> <span data-ttu-id="5d2fc-194">Проверьте позже.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-194">Check back later.</span></span> |
| <span data-ttu-id="5d2fc-195">Регистрация не удалась</span><span class="sxs-lookup"><span data-stu-id="5d2fc-195">Registration failed</span></span> | <span data-ttu-id="5d2fc-196">Регистрация не может быть завершена.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-196">Registration could not be completed.</span></span> <span data-ttu-id="5d2fc-197">Дополнительные [сведения обратитесь к регистрации](#troubleshooting-device-registration) устройств для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-197">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="5d2fc-198">Готово для пользователя</span><span class="sxs-lookup"><span data-stu-id="5d2fc-198">Ready for user</span></span> | <span data-ttu-id="5d2fc-199">Регистрация была успешной, и теперь устройство готово к доставке пользователю.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-199">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="5d2fc-200">компьютеры, управляемые Майкрософт будет направлять их по первой подготовке, поэтому вам не нужно делать какие-либо дополнительные подготовительные работы.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-200">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="5d2fc-201">Активация</span><span class="sxs-lookup"><span data-stu-id="5d2fc-201">Active</span></span> | <span data-ttu-id="5d2fc-202">Устройство доставлено пользователю и зарегистрировано у клиента.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-202">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="5d2fc-203">Это также указывает на то, что они регулярно используют устройство.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-203">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="5d2fc-204">Неактивный</span><span class="sxs-lookup"><span data-stu-id="5d2fc-204">Inactive</span></span> | <span data-ttu-id="5d2fc-205">Устройство доставлено пользователю и зарегистрировано у клиента.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-205">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="5d2fc-206">Однако они не использовали устройство в последнее время (за последние 7 дней).</span><span class="sxs-lookup"><span data-stu-id="5d2fc-206">However, they have not used the device recently (in the last 7 days).</span></span>  | 

### <a name="troubleshooting-device-registration"></a><span data-ttu-id="5d2fc-207">Устранение неполадок при регистрации устройств</span><span class="sxs-lookup"><span data-stu-id="5d2fc-207">Troubleshooting device registration</span></span>

| <span data-ttu-id="5d2fc-208">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="5d2fc-208">Error message</span></span> | <span data-ttu-id="5d2fc-209">Сведения</span><span class="sxs-lookup"><span data-stu-id="5d2fc-209">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="5d2fc-210">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="5d2fc-210">Device not found</span></span> | <span data-ttu-id="5d2fc-211">Мы не смогли зарегистрировать это устройство, так как не смогли найти совпадение для предоставленного производителя, модели или серийного номера.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-211">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="5d2fc-212">Подтвердите эти значения у поставщика устройств.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-212">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="5d2fc-213">Не допустимый хаш оборудования</span><span class="sxs-lookup"><span data-stu-id="5d2fc-213">Hardware hash not valid</span></span> | <span data-ttu-id="5d2fc-214">Предоставленный для этого устройства аппаратный хаш был неправильно отформатирован.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-214">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="5d2fc-215">Дважды проверьте хаш оборудования, а затем повторно.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-215">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="5d2fc-216">Уже зарегистрированное устройство</span><span class="sxs-lookup"><span data-stu-id="5d2fc-216">Device already registered</span></span> | <span data-ttu-id="5d2fc-217">Это устройство уже зарегистрировано в организации.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-217">This device is already registered to your organization.</span></span> <span data-ttu-id="5d2fc-218">Дополнительных действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-218">No further action required.</span></span> |
| <span data-ttu-id="5d2fc-219">Устройство, заявленное другой организацией</span><span class="sxs-lookup"><span data-stu-id="5d2fc-219">Device claimed by another organization</span></span> | <span data-ttu-id="5d2fc-220">Это устройство уже было заявлено другой организацией.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-220">This device has already been claimed by another organization.</span></span> <span data-ttu-id="5d2fc-221">Обратитесь к поставщику устройств.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-221">Check with your device supplier.</span></span> |
| <span data-ttu-id="5d2fc-222">Непредвиденная ошибка</span><span class="sxs-lookup"><span data-stu-id="5d2fc-222">Unexpected error</span></span> | <span data-ttu-id="5d2fc-223">Ваш запрос не может быть автоматически обработан.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-223">Your request could not be automatically processed.</span></span> <span data-ttu-id="5d2fc-224">Поддержка контактов и предоставление ID запроса: <requestId></span><span class="sxs-lookup"><span data-stu-id="5d2fc-224">Contact Support and provide the Request ID: <requestId></span></span> |

## <a name="check-the-image"></a><span data-ttu-id="5d2fc-225">Проверка изображения</span><span class="sxs-lookup"><span data-stu-id="5d2fc-225">Check the image</span></span>

<span data-ttu-id="5d2fc-226">Если устройство пришло от поставщика компьютеры, управляемые Майкрософт партнера, изображение должно быть правильным.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-226">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="5d2fc-227">Вы также можете применить изображение самостоятельно, если хотите.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-227">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="5d2fc-228">Чтобы начать работу, обратитесь к представителю Майкрософт, с который вы работаете, и они предупредят вам расположение и действия для применения изображения.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-228">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

## <a name="deliver-the-device"></a><span data-ttu-id="5d2fc-229">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="5d2fc-229">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d2fc-230">Перед тем как передать устройство пользователю, убедитесь, что вы получили и применили [соответствующие лицензии](../get-ready/prerequisites.md) для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-230">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="5d2fc-231">Если все лицензии применяются, вы можете получить пользователей готовыми к использованию [устройств,](get-started-devices.md)а затем пользователь может запустить устройство и перейти через Windows настройки.</span><span class="sxs-lookup"><span data-stu-id="5d2fc-231">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









