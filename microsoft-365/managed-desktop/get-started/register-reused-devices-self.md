---
title: Самостоятельная регистрация существующих устройств
description: Регистрация повторно используемых устройств. возможно, у вас уже есть права для управления на настольном компьютере, управляемом Майкрософт
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 51c241c46a4c8745bcae169a1c1d89e5c4393f2f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289143"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="1e72d-103">Самостоятельная регистрация существующих устройств</span><span class="sxs-lookup"><span data-stu-id="1e72d-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="1e72d-104">В этом разделе описываются действия, которые необходимо выполнить, чтобы повторно использовать уже имеющиеся устройства и зарегистрировать их в системе, управляемой корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1e72d-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="1e72d-105">Если вы работаете с новыми устройствами, выполните действия, описанные в статье [Регистрация новых устройств на компьютере, управляемом Майкрософт](register-devices-self.md) , вместо этого.</span><span class="sxs-lookup"><span data-stu-id="1e72d-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="1e72d-106">Процесс для партнеров описан в [статье действия для партнеров по регистрации устройств](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="1e72d-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="1e72d-107">Рабочий стол, управляемый Майкрософт, может работать с новыми устройствами или можно повторно использовать уже имеющиеся устройства (которые потребуют их повторного создания образа).</span><span class="sxs-lookup"><span data-stu-id="1e72d-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="1e72d-108">Вы можете зарегистрировать устройства с помощью портала администрирования настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1e72d-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="1e72d-109">Подготовка к регистрации существующих устройств</span><span class="sxs-lookup"><span data-stu-id="1e72d-109">Prepare to register existing devices</span></span>


<span data-ttu-id="1e72d-110">Чтобы зарегистрировать существующие устройства, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1e72d-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="1e72d-111">Получите хеш оборудования для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="1e72d-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="1e72d-112">Объединение хэш-данных</span><span class="sxs-lookup"><span data-stu-id="1e72d-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="1e72d-113">[Зарегистрируйте устройства на настольном компьютере, управляемом Майкрософт](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="1e72d-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="1e72d-114">Дважды проверьте правильность изображения.</span><span class="sxs-lookup"><span data-stu-id="1e72d-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="1e72d-115">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="1e72d-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="1e72d-116">Получение хэш-кода оборудования</span><span class="sxs-lookup"><span data-stu-id="1e72d-116">Obtain the hardware hash</span></span>

<span data-ttu-id="1e72d-117">Рабочий стол, управляемый Майкрософт, определяет каждое устройство уникальным образом, ссылаясь на хэш оборудования.</span><span class="sxs-lookup"><span data-stu-id="1e72d-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="1e72d-118">Существует четыре способа получения этой информации с устройств, которые вы уже используете:</span><span class="sxs-lookup"><span data-stu-id="1e72d-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="1e72d-119">Обратитесь к поставщику поставщика вычислительной техники для файла регистрации для автопилота, в котором будут содержаться хэши оборудования.</span><span class="sxs-lookup"><span data-stu-id="1e72d-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="1e72d-120">Сбор сведений в [диспетчере конфигураций конечных точек Майкрософт](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="1e72d-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="1e72d-121">Запустите сценарий Windows PowerShell, используя [Active Directory](#active-directory-powershell-script-method) или [вручную](#manual-powershell-script-method) на каждом устройстве, и соберите результаты в файл.</span><span class="sxs-lookup"><span data-stu-id="1e72d-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="1e72d-122">Запустите каждое устройство, но не завершите работу с программой установки Windows, и [Соберите хэши на съемном носителе флэш-памяти](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="1e72d-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="1e72d-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1e72d-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="1e72d-124">С помощью диспетчера конфигураций конечных точек Майкрософт можно собирать аппаратные хэши с существующих устройств, которые вы хотите зарегистрировать с помощью управляемого рабочего стола Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1e72d-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e72d-125">Все устройства, для которых вы хотите получить эту информацию, должны работать под управлением Windows 10 версии 1703 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="1e72d-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="1e72d-126">Если вы удовлетворены всеми необходимыми компонентами, вы готовы собрать эти сведения, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1e72d-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="1e72d-127">В консоли диспетчера конфигураций выберите пункт **мониторинг**.</span><span class="sxs-lookup"><span data-stu-id="1e72d-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="1e72d-128">В рабочей области мониторинга разверните узел **отчеты** , разверните элемент **отчеты**и выберите узел **Общий аппаратный** узел.</span><span class="sxs-lookup"><span data-stu-id="1e72d-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="1e72d-129">Запустите отчет, **сведения об устройствах Windows для автопилота**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="1e72d-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="1e72d-130">В средстве просмотра отчетов выберите значок **Экспорт** и выберите параметр **CSV (с разделителями-запятыми)** .</span><span class="sxs-lookup"><span data-stu-id="1e72d-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="1e72d-131">После сохранения файла необходимо отфильтровать результаты только на тех устройствах, которые планируется зарегистрировать с помощью управляемого рабочего стола Майкрософт, и загрузить данные на [портал администрирования](https://aka.ms/mmdportal)настольных компьютеров Майкрософт, выбрав пункт **устройства** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="1e72d-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="1e72d-132">Выберите **+ Регистрация устройств**; Откроется вспомогательная надстройка:</span><span class="sxs-lookup"><span data-stu-id="1e72d-132">Select **+ Register devices**; the fly-in opens:</span></span>


<span data-ttu-id="1e72d-133">Для получения дополнительных сведений обратитесь к разделу [Регистрация устройств с помощью портала администрирования](#register-devices-by-using-the-admin-portal) .</span><span class="sxs-lookup"><span data-stu-id="1e72d-133">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="1e72d-134">Метод сценария PowerShell Active Directory</span><span class="sxs-lookup"><span data-stu-id="1e72d-134">Active Directory PowerShell script method</span></span>

<span data-ttu-id="1e72d-135">В среде Active Directory вы можете использовать `Get-WindowsAutoPilotInfo` командлет PowerShell для удаленного сбора сведений от устройств в группах Active Directory с помощью WinRM.</span><span class="sxs-lookup"><span data-stu-id="1e72d-135">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="1e72d-136">Кроме того, можно использовать `Get-AD Computer` командлеты и получать отфильтрованные результаты для определенных аппаратных имен моделей, включенных в каталог.</span><span class="sxs-lookup"><span data-stu-id="1e72d-136">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="1e72d-137">Для этого сначала подтвердите необходимые условия, а затем выполните действия, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="1e72d-137">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="1e72d-138">Служба WinRM включена.</span><span class="sxs-lookup"><span data-stu-id="1e72d-138">WinRM is enabled.</span></span>
- <span data-ttu-id="1e72d-139">Устройства, которые вы хотите зарегистрировать, активны в сети (то есть они не отключены и не отключены).</span><span class="sxs-lookup"><span data-stu-id="1e72d-139">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="1e72d-140">Убедитесь, что у вас есть параметр учетных данных домена, у которого есть разрешение на удаленное выполнение на устройствах.</span><span class="sxs-lookup"><span data-stu-id="1e72d-140">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="1e72d-141">Убедитесь, что брандмауэр Windows предоставляет доступ к WMI.</span><span class="sxs-lookup"><span data-stu-id="1e72d-141">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="1e72d-142">Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1e72d-142">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="1e72d-143">Откройте панель управления **брандмауэром защитника Windows** и выберите пункт **Разрешить приложение или компонент через брандмауэр защитника Windows**.</span><span class="sxs-lookup"><span data-stu-id="1e72d-143">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="1e72d-144">Найдите в списке **инструментарий управления Windows (WMI)** , включите как частный, так и **общедоступный**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e72d-144">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="1e72d-145">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="1e72d-145">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="1e72d-146">Выполните *один* из следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="1e72d-146">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="1e72d-147">Доступ к каталогам, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="1e72d-147">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="1e72d-148">Удалите записи для каждого устройства из *всех* каталогов, включая доменные службы Windows Server Active Directory и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1e72d-148">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="1e72d-149">Обратите внимание, что для полного выполнения этого процесса может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="1e72d-149">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="1e72d-150">Доступ к службам управления, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="1e72d-150">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="1e72d-151">Удалите записи для каждого устройства из *всех* служб управления, включая диспетчер конфигураций конечных точек Майкрософт, Microsoft Intune и Windows автопилот.</span><span class="sxs-lookup"><span data-stu-id="1e72d-151">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="1e72d-152">Обратите внимание, что для полного выполнения этого процесса может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="1e72d-152">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="1e72d-153">Теперь вы можете перейти к разделу [Регистрация устройств](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="1e72d-153">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="1e72d-154">Метод сценария PowerShell вручную</span><span class="sxs-lookup"><span data-stu-id="1e72d-154">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="1e72d-155">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="1e72d-155">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="1e72d-156">Выполняем `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="1e72d-156">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="1e72d-157">Выполняем `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="1e72d-157">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="1e72d-158">Объединение хэш-данных.</span><span class="sxs-lookup"><span data-stu-id="1e72d-158">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="1e72d-159">Метод флэш-накопителя</span><span class="sxs-lookup"><span data-stu-id="1e72d-159">Flash drive method</span></span>

1. <span data-ttu-id="1e72d-160">На устройстве, отличном от регистрируемого, вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="1e72d-160">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="1e72d-161">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="1e72d-161">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="1e72d-162">Выполняем `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="1e72d-162">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="1e72d-163">Включите регистрируемое устройство, но не *запускайте процесс установки*.</span><span class="sxs-lookup"><span data-stu-id="1e72d-163">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="1e72d-164">Если вы случайно запустили программу установки, вам потребуется сбросить или переобразировать устройство.</span><span class="sxs-lookup"><span data-stu-id="1e72d-164">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="1e72d-165">Вставьте USB-накопитель, а затем нажмите клавиши SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="1e72d-165">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="1e72d-166">Откройте командную строку PowerShell с правами администратора и запустите `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="1e72d-166">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="1e72d-167">Выполняем `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="1e72d-167">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="1e72d-168">Выполняем `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="1e72d-168">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="1e72d-169">Удалите USB-накопитель, а затем завершите работу устройства, выполнив `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="1e72d-169">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="1e72d-170">Объединение хэш-данных.</span><span class="sxs-lookup"><span data-stu-id="1e72d-170">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="1e72d-171">Не выключайте устройство, которое вы регистрируете повторно, пока не завершите его регистрацию.</span><span class="sxs-lookup"><span data-stu-id="1e72d-171">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="1e72d-172">Слияние хэш-данных</span><span class="sxs-lookup"><span data-stu-id="1e72d-172">Merge hash data</span></span>

<span data-ttu-id="1e72d-173">Если вы собрали хэш-данные оборудования вручную с помощью методов PowerShell или устройства флэш-памяти, то теперь необходимо объединить данные CSV-файлов в один файл для завершения регистрации.</span><span class="sxs-lookup"><span data-stu-id="1e72d-173">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="1e72d-174">Вот пример сценария PowerShell для упрощения:</span><span class="sxs-lookup"><span data-stu-id="1e72d-174">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="1e72d-175">После объединения хэш-данных в один CSV-файл можно приступить к [регистрации устройств](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="1e72d-175">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="1e72d-176">Регистрация устройств с помощью портала администрирования</span><span class="sxs-lookup"><span data-stu-id="1e72d-176">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="1e72d-177">На [портале администрирования](https://aka.ms/mmdportal)рабочих столов, управляемом Майкрософт, выберите **устройства** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="1e72d-177">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="1e72d-178">Выберите **+ Регистрация устройств**; Откроется вспомогательная надстройка:</span><span class="sxs-lookup"><span data-stu-id="1e72d-178">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="1e72d-179">[![Вскрывающийся после выбора параметра Регистрация устройств, перечисление устройств со столбцами для назначенных пользователей, серийного номера, состояния, даты последнего рассмотрения и срока хранения](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span><span class="sxs-lookup"><span data-stu-id="1e72d-179">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span></span>


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="1e72d-180">Выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1e72d-180">Follow these steps:</span></span>

1. <span data-ttu-id="1e72d-181">В поле **Отправка файла**укажите путь к созданному ранее CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="1e72d-181">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="1e72d-182">Выберите пункт **зарегистрировать устройства**.</span><span class="sxs-lookup"><span data-stu-id="1e72d-182">Select **Register devices**.</span></span> <span data-ttu-id="1e72d-183">Система добавит устройства в список устройств в **колонке устройства**, помеченной как **аутопилотрегистратионрекуестед**.</span><span class="sxs-lookup"><span data-stu-id="1e72d-183">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="1e72d-184">Регистрация обычно занимает менее 10 минут, и при успешном завершении работы устройство отображается как **готовое для пользователя** , что означает, что он готов к работе и ожидает, пока пользователь не запустится.</span><span class="sxs-lookup"><span data-stu-id="1e72d-184">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="1e72d-185">Вы можете отслеживать ход регистрации устройств на главной странице " **управляемые настольные устройства Майкрософт** ".</span><span class="sxs-lookup"><span data-stu-id="1e72d-185">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="1e72d-186">В отчет могут воздержаться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1e72d-186">Possible states reported there include:</span></span>

| <span data-ttu-id="1e72d-187">Состояние</span><span class="sxs-lookup"><span data-stu-id="1e72d-187">State</span></span> | <span data-ttu-id="1e72d-188">Описание</span><span class="sxs-lookup"><span data-stu-id="1e72d-188">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="1e72d-189">аутопилотрегистратионрекуестед</span><span class="sxs-lookup"><span data-stu-id="1e72d-189">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="1e72d-190">Регистрация еще не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1e72d-190">Registration is not done yet.</span></span> <span data-ttu-id="1e72d-191">Вернитесь позже.</span><span class="sxs-lookup"><span data-stu-id="1e72d-191">Check back later.</span></span> |
| <span data-ttu-id="1e72d-192">Сбой регистрации</span><span class="sxs-lookup"><span data-stu-id="1e72d-192">Registration failed</span></span> | <span data-ttu-id="1e72d-193">Не удалось выполнить регистрацию.</span><span class="sxs-lookup"><span data-stu-id="1e72d-193">Registration could not be completed.</span></span> <span data-ttu-id="1e72d-194">Для получения дополнительных сведений обратитесь к разделу [Устранение неполадок Device Registration](#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="1e72d-194">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="1e72d-195">Готово для пользователя</span><span class="sxs-lookup"><span data-stu-id="1e72d-195">Ready for user</span></span> | <span data-ttu-id="1e72d-196">Регистрация выполнена успешно, и теперь устройство готово к доставке пользователю.</span><span class="sxs-lookup"><span data-stu-id="1e72d-196">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="1e72d-197">Рабочий стол, управляемый Майкрософт, будет самостоятельно настраиваться, поэтому дальнейшие подготовительные действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="1e72d-197">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="1e72d-198">Активное</span><span class="sxs-lookup"><span data-stu-id="1e72d-198">Active</span></span> | <span data-ttu-id="1e72d-199">Устройство доставлено пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="1e72d-199">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="1e72d-200">Это также означает, что они регулярно используют устройство.</span><span class="sxs-lookup"><span data-stu-id="1e72d-200">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="1e72d-201">Отсутств</span><span class="sxs-lookup"><span data-stu-id="1e72d-201">Inactive</span></span> | <span data-ttu-id="1e72d-202">Устройство доставлено пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="1e72d-202">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="1e72d-203">Однако они не использовали устройство недавно (за последние 7 дней).</span><span class="sxs-lookup"><span data-stu-id="1e72d-203">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="1e72d-204">Устранение неполадок при регистрации устройств</span><span class="sxs-lookup"><span data-stu-id="1e72d-204">Troubleshooting device registration</span></span>

| <span data-ttu-id="1e72d-205">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="1e72d-205">Error message</span></span> | <span data-ttu-id="1e72d-206">Сведения</span><span class="sxs-lookup"><span data-stu-id="1e72d-206">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="1e72d-207">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="1e72d-207">Device not found</span></span> | <span data-ttu-id="1e72d-208">Не удалось зарегистрировать это устройство, так как не удалось найти соответствующее значение для указанного производителя, модели или серийного номера.</span><span class="sxs-lookup"><span data-stu-id="1e72d-208">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="1e72d-209">Подтвердите эти значения с помощью поставщика устройств.</span><span class="sxs-lookup"><span data-stu-id="1e72d-209">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="1e72d-210">Недопустимый хеш оборудования</span><span class="sxs-lookup"><span data-stu-id="1e72d-210">Hardware hash not valid</span></span> | <span data-ttu-id="1e72d-211">Аппаратный хеш, указанный для этого устройства, отформатирован неправильно.</span><span class="sxs-lookup"><span data-stu-id="1e72d-211">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="1e72d-212">Дважды проверьте хэш оборудования, а затем повторите отправляются.</span><span class="sxs-lookup"><span data-stu-id="1e72d-212">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="1e72d-213">Устройство уже зарегистрировано</span><span class="sxs-lookup"><span data-stu-id="1e72d-213">Device already registered</span></span> | <span data-ttu-id="1e72d-214">Это устройство уже зарегистрировано в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1e72d-214">This device is already registered to your organization.</span></span> <span data-ttu-id="1e72d-215">Дальнейшие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="1e72d-215">No further action required.</span></span> |
| <span data-ttu-id="1e72d-216">Устройство заявлено другой организацией</span><span class="sxs-lookup"><span data-stu-id="1e72d-216">Device claimed by another organization</span></span> | <span data-ttu-id="1e72d-217">Это устройство уже заявлено другой организацией.</span><span class="sxs-lookup"><span data-stu-id="1e72d-217">This device has already been claimed by another organization.</span></span> <span data-ttu-id="1e72d-218">Обратитесь к поставщику устройства.</span><span class="sxs-lookup"><span data-stu-id="1e72d-218">Check with your device supplier.</span></span> |
| <span data-ttu-id="1e72d-219">Непредвиденная ошибка</span><span class="sxs-lookup"><span data-stu-id="1e72d-219">Unexpected error</span></span> | <span data-ttu-id="1e72d-220">Не удалось автоматически обработать запрос.</span><span class="sxs-lookup"><span data-stu-id="1e72d-220">Your request could not be automatically processed.</span></span> <span data-ttu-id="1e72d-221">Обратитесь в службу поддержки и введите идентификатор запроса: <requestId></span><span class="sxs-lookup"><span data-stu-id="1e72d-221">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="1e72d-222">Проверка изображения</span><span class="sxs-lookup"><span data-stu-id="1e72d-222">Check the image</span></span>

<span data-ttu-id="1e72d-223">Если ваше устройство поступило от поставщика управляемого партнера Майкрософт для настольных ПК, изображение должно быть правильным.</span><span class="sxs-lookup"><span data-stu-id="1e72d-223">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="1e72d-224">Вы также можете применить образ самостоятельно, если хотите.</span><span class="sxs-lookup"><span data-stu-id="1e72d-224">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="1e72d-225">Чтобы приступить к работе, обратитесь к представителю Майкрософт, с которым вы работаете, и укажите расположение и действия по применению образа.</span><span class="sxs-lookup"><span data-stu-id="1e72d-225">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="1e72d-226">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="1e72d-226">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e72d-227">Прежде чем вы перейдете на устройство для пользователя, убедитесь, что вы получили и применили [соответствующие лицензии](../get-ready/prerequisites.md) для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="1e72d-227">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="1e72d-228">Если все лицензии применяются, вы можете [приступить к работе с устройствами](get-started-devices.md), а затем, когда пользователь сможет запустить устройство и выполнить установку Windows.</span><span class="sxs-lookup"><span data-stu-id="1e72d-228">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









