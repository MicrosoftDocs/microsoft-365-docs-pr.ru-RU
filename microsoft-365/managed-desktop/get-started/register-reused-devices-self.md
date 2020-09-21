---
title: Самостоятельная регистрация существующих устройств
description: Регистрация повторно используемых устройств. возможно, у вас уже есть права для управления на настольном компьютере, управляемом Майкрософт
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 6c241894ab50b6b1341b06f47c107c8945fb6e8c
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104574"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="be813-103">Самостоятельная регистрация существующих устройств</span><span class="sxs-lookup"><span data-stu-id="be813-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="be813-104">В этом разделе описываются действия, которые необходимо выполнить, чтобы повторно использовать уже имеющиеся устройства и зарегистрировать их в системе, управляемой корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="be813-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="be813-105">Если вы работаете с новыми устройствами, выполните действия, описанные в статье [Регистрация новых устройств на компьютере, управляемом Майкрософт](register-devices-self.md) , вместо этого.</span><span class="sxs-lookup"><span data-stu-id="be813-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="be813-106">Процесс для партнеров описан в [статье действия для партнеров по регистрации устройств](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="be813-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="be813-107">Рабочий стол, управляемый Майкрософт, может работать с новыми устройствами или можно повторно использовать уже имеющиеся устройства (которые потребуют их повторного создания образа).</span><span class="sxs-lookup"><span data-stu-id="be813-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="be813-108">Вы можете зарегистрировать устройства с помощью управляемого рабочего стола Майкрософт на портале Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="be813-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="be813-109">Подготовка к регистрации существующих устройств</span><span class="sxs-lookup"><span data-stu-id="be813-109">Prepare to register existing devices</span></span>


<span data-ttu-id="be813-110">Чтобы зарегистрировать существующие устройства, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="be813-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="be813-111">Получите хеш оборудования для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="be813-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="be813-112">Объединение хэш-данных</span><span class="sxs-lookup"><span data-stu-id="be813-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="be813-113">[Зарегистрируйте устройства на настольном компьютере, управляемом Майкрософт](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="be813-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="be813-114">Дважды проверьте правильность изображения.</span><span class="sxs-lookup"><span data-stu-id="be813-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="be813-115">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="be813-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="be813-116">Получение хэш-кода оборудования</span><span class="sxs-lookup"><span data-stu-id="be813-116">Obtain the hardware hash</span></span>

<span data-ttu-id="be813-117">Рабочий стол, управляемый Майкрософт, определяет каждое устройство уникальным образом, ссылаясь на хэш оборудования.</span><span class="sxs-lookup"><span data-stu-id="be813-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="be813-118">Существует четыре способа получения этой информации с устройств, которые вы уже используете:</span><span class="sxs-lookup"><span data-stu-id="be813-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="be813-119">Обратитесь к поставщику поставщика вычислительной техники для файла регистрации для автопилота, в котором будут содержаться хэши оборудования.</span><span class="sxs-lookup"><span data-stu-id="be813-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="be813-120">Сбор сведений в [диспетчере конфигураций конечных точек Майкрософт](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="be813-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="be813-121">Запустите сценарий Windows PowerShell, используя [Active Directory](#active-directory-powershell-script-method) или [вручную](#manual-powershell-script-method) на каждом устройстве, и соберите результаты в файл.</span><span class="sxs-lookup"><span data-stu-id="be813-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="be813-122">Запустите каждое устройство, но не завершите работу с программой установки Windows, и [Соберите хэши на съемном носителе флэш-памяти](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="be813-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="be813-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="be813-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="be813-124">С помощью диспетчера конфигураций конечных точек Майкрософт можно собирать аппаратные хэши с существующих устройств, которые вы хотите зарегистрировать с помощью управляемого рабочего стола Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="be813-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be813-125">Все устройства, для которых вы хотите получить эту информацию, должны работать под управлением Windows 10 версии 1703 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="be813-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="be813-126">Если вы удовлетворены всеми необходимыми компонентами, вы готовы собрать эти сведения, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="be813-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="be813-127">В консоли диспетчера конфигураций выберите пункт **мониторинг**.</span><span class="sxs-lookup"><span data-stu-id="be813-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="be813-128">В рабочей области мониторинга разверните узел **отчеты** , разверните элемент **отчеты**и выберите узел **Общий аппаратный** узел.</span><span class="sxs-lookup"><span data-stu-id="be813-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="be813-129">Запустите отчет, **сведения об устройствах Windows для автопилота**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="be813-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="be813-130">В средстве просмотра отчетов выберите значок **Экспорт** и выберите параметр **CSV (с разделителями-запятыми)** .</span><span class="sxs-lookup"><span data-stu-id="be813-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="be813-131">После сохранения файла необходимо отфильтровать результаты только на тех устройствах, которые планируется зарегистрировать с помощью управляемого рабочего стола Майкрософт, и загрузить данные на компьютер, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="be813-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="be813-132">Откройте диспетчер конечных точек Майкрософт и перейдите в меню **устройства** выберите раздел Рабочий стол с управляемым Майкрософт и выберите пункт **устройства**.</span><span class="sxs-lookup"><span data-stu-id="be813-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="be813-133">Выберите **+ Регистрация устройств** , которая открывает оперативную подпрограмму для регистрации новых устройств.</span><span class="sxs-lookup"><span data-stu-id="be813-133">Select **+ Register devices** which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="be813-134">Для получения дополнительных сведений обратитесь к разделу [Регистрация устройств с помощью портала администрирования](#register-devices-by-using-the-admin-portal) .</span><span class="sxs-lookup"><span data-stu-id="be813-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="be813-135">Метод сценария PowerShell Active Directory</span><span class="sxs-lookup"><span data-stu-id="be813-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="be813-136">В среде Active Directory вы можете использовать `Get-WindowsAutoPilotInfo` командлет PowerShell для удаленного сбора сведений от устройств в группах Active Directory с помощью WinRM.</span><span class="sxs-lookup"><span data-stu-id="be813-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="be813-137">Кроме того, можно использовать `Get-AD Computer` командлеты и получать отфильтрованные результаты для определенных аппаратных имен моделей, включенных в каталог.</span><span class="sxs-lookup"><span data-stu-id="be813-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="be813-138">Для этого сначала подтвердите необходимые условия, а затем выполните действия, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="be813-138">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="be813-139">Служба WinRM включена.</span><span class="sxs-lookup"><span data-stu-id="be813-139">WinRM is enabled.</span></span>
- <span data-ttu-id="be813-140">Устройства, которые вы хотите зарегистрировать, активны в сети (то есть они не отключены и не отключены).</span><span class="sxs-lookup"><span data-stu-id="be813-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="be813-141">Убедитесь, что у вас есть параметр учетных данных домена, у которого есть разрешение на удаленное выполнение на устройствах.</span><span class="sxs-lookup"><span data-stu-id="be813-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="be813-142">Убедитесь, что брандмауэр Windows предоставляет доступ к WMI.</span><span class="sxs-lookup"><span data-stu-id="be813-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="be813-143">Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="be813-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="be813-144">Откройте панель управления **брандмауэром защитника Windows** и выберите пункт **Разрешить приложение или компонент через брандмауэр защитника Windows**.</span><span class="sxs-lookup"><span data-stu-id="be813-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="be813-145">Найдите в списке **инструментарий управления Windows (WMI)** , включите как частный, так и **общедоступный**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="be813-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="be813-146">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="be813-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="be813-147">Выполните *один* из следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="be813-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="be813-148">Доступ к каталогам, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="be813-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="be813-149">Удалите записи для каждого устройства из *всех* каталогов, включая доменные службы Windows Server Active Directory и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="be813-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="be813-150">Обратите внимание, что для полного выполнения этого процесса может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="be813-150">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="be813-151">Доступ к службам управления, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="be813-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="be813-152">Удалите записи для каждого устройства из *всех* служб управления, включая диспетчер конфигураций конечных точек Майкрософт, Microsoft Intune и Windows автопилот.</span><span class="sxs-lookup"><span data-stu-id="be813-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="be813-153">Обратите внимание, что для полного выполнения этого процесса может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="be813-153">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="be813-154">Теперь вы можете перейти к разделу [Регистрация устройств](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="be813-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="be813-155">Метод сценария PowerShell вручную</span><span class="sxs-lookup"><span data-stu-id="be813-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="be813-156">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="be813-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="be813-157">Выполняем `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="be813-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="be813-158">Выполняем `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="be813-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="be813-159">Объединение хэш-данных.</span><span class="sxs-lookup"><span data-stu-id="be813-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="be813-160">Метод флэш-накопителя</span><span class="sxs-lookup"><span data-stu-id="be813-160">Flash drive method</span></span>

1. <span data-ttu-id="be813-161">На устройстве, отличном от регистрируемого, вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="be813-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="be813-162">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="be813-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="be813-163">Выполняем `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="be813-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="be813-164">Включите регистрируемое устройство, но не *запускайте процесс установки*.</span><span class="sxs-lookup"><span data-stu-id="be813-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="be813-165">Если вы случайно запустили программу установки, вам потребуется сбросить или переобразировать устройство.</span><span class="sxs-lookup"><span data-stu-id="be813-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="be813-166">Вставьте USB-накопитель, а затем нажмите клавиши SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="be813-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="be813-167">Откройте командную строку PowerShell с правами администратора и запустите `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="be813-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="be813-168">Выполняем `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="be813-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="be813-169">Выполняем `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="be813-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="be813-170">Удалите USB-накопитель, а затем завершите работу устройства, выполнив `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="be813-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="be813-171">Объединение хэш-данных.</span><span class="sxs-lookup"><span data-stu-id="be813-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="be813-172">Не выключайте устройство, которое вы регистрируете повторно, пока не завершите его регистрацию.</span><span class="sxs-lookup"><span data-stu-id="be813-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="be813-173">Слияние хэш-данных</span><span class="sxs-lookup"><span data-stu-id="be813-173">Merge hash data</span></span>

<span data-ttu-id="be813-174">Если вы собрали хэш-данные оборудования вручную с помощью методов PowerShell или устройства флэш-памяти, то теперь необходимо объединить данные CSV-файлов в один файл для завершения регистрации.</span><span class="sxs-lookup"><span data-stu-id="be813-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="be813-175">Вот пример сценария PowerShell для упрощения:</span><span class="sxs-lookup"><span data-stu-id="be813-175">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="be813-176">После объединения хэш-данных в один CSV-файл можно приступить к [регистрации устройств](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="be813-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="be813-177">Регистрация устройств с помощью портала администрирования</span><span class="sxs-lookup"><span data-stu-id="be813-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="be813-178">В [диспетчере конечных точек Майкрософт](https://endpoint.microsoft.com/)выберите **устройства** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="be813-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="be813-179">Найдите в меню раздел Рабочий стол, управляемый Майкрософт, а затем выберите пункт **устройства**.</span><span class="sxs-lookup"><span data-stu-id="be813-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="be813-180">В рабочей области "управляемые устройства Майкрософт" выберите **+ Регистрация устройств** , которая открывает оперативную подсистему для регистрации новых устройств.</span><span class="sxs-lookup"><span data-stu-id="be813-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices** which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="be813-181">Выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="be813-181">Follow these steps:</span></span>

1. <span data-ttu-id="be813-182">В поле **Отправка файла**укажите путь к созданному ранее CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="be813-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="be813-183">Выберите пункт **зарегистрировать устройства**.</span><span class="sxs-lookup"><span data-stu-id="be813-183">Select **Register devices**.</span></span> <span data-ttu-id="be813-184">Система добавит устройства в список устройств в **колонке устройства**, помеченной как **аутопилотрегистратионрекуестед**.</span><span class="sxs-lookup"><span data-stu-id="be813-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="be813-185">Регистрация обычно занимает менее 10 минут, и при успешном завершении работы устройство отображается как **готовое для пользователя** , что означает, что он готов к работе и ожидает, пока пользователь не запустится.</span><span class="sxs-lookup"><span data-stu-id="be813-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="be813-186">Вы можете отслеживать ход регистрации устройств на главной странице.</span><span class="sxs-lookup"><span data-stu-id="be813-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="be813-187">В отчет могут воздержаться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="be813-187">Possible states reported there include:</span></span>

| <span data-ttu-id="be813-188">Состояние</span><span class="sxs-lookup"><span data-stu-id="be813-188">State</span></span> | <span data-ttu-id="be813-189">Описание</span><span class="sxs-lookup"><span data-stu-id="be813-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="be813-190">аутопилотрегистратионрекуестед</span><span class="sxs-lookup"><span data-stu-id="be813-190">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="be813-191">Регистрация еще не выполняется.</span><span class="sxs-lookup"><span data-stu-id="be813-191">Registration is not done yet.</span></span> <span data-ttu-id="be813-192">Вернитесь позже.</span><span class="sxs-lookup"><span data-stu-id="be813-192">Check back later.</span></span> |
| <span data-ttu-id="be813-193">Сбой регистрации</span><span class="sxs-lookup"><span data-stu-id="be813-193">Registration failed</span></span> | <span data-ttu-id="be813-194">Не удалось выполнить регистрацию.</span><span class="sxs-lookup"><span data-stu-id="be813-194">Registration could not be completed.</span></span> <span data-ttu-id="be813-195">Для получения дополнительных сведений обратитесь к разделу [Устранение неполадок Device Registration](#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="be813-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="be813-196">Готово для пользователя</span><span class="sxs-lookup"><span data-stu-id="be813-196">Ready for user</span></span> | <span data-ttu-id="be813-197">Регистрация выполнена успешно, и теперь устройство готово к доставке пользователю.</span><span class="sxs-lookup"><span data-stu-id="be813-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="be813-198">Рабочий стол, управляемый Майкрософт, будет самостоятельно настраиваться, поэтому дальнейшие подготовительные действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="be813-198">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="be813-199">Активное</span><span class="sxs-lookup"><span data-stu-id="be813-199">Active</span></span> | <span data-ttu-id="be813-200">Устройство доставлено пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="be813-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="be813-201">Это также означает, что они регулярно используют устройство.</span><span class="sxs-lookup"><span data-stu-id="be813-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="be813-202">Отсутств</span><span class="sxs-lookup"><span data-stu-id="be813-202">Inactive</span></span> | <span data-ttu-id="be813-203">Устройство доставлено пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="be813-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="be813-204">Однако они не использовали устройство недавно (за последние 7 дней).</span><span class="sxs-lookup"><span data-stu-id="be813-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="be813-205">Устранение неполадок при регистрации устройств</span><span class="sxs-lookup"><span data-stu-id="be813-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="be813-206">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="be813-206">Error message</span></span> | <span data-ttu-id="be813-207">Сведения</span><span class="sxs-lookup"><span data-stu-id="be813-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="be813-208">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="be813-208">Device not found</span></span> | <span data-ttu-id="be813-209">Не удалось зарегистрировать это устройство, так как не удалось найти соответствующее значение для указанного производителя, модели или серийного номера.</span><span class="sxs-lookup"><span data-stu-id="be813-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="be813-210">Подтвердите эти значения с помощью поставщика устройств.</span><span class="sxs-lookup"><span data-stu-id="be813-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="be813-211">Недопустимый хеш оборудования</span><span class="sxs-lookup"><span data-stu-id="be813-211">Hardware hash not valid</span></span> | <span data-ttu-id="be813-212">Аппаратный хеш, указанный для этого устройства, отформатирован неправильно.</span><span class="sxs-lookup"><span data-stu-id="be813-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="be813-213">Дважды проверьте хэш оборудования, а затем повторите отправляются.</span><span class="sxs-lookup"><span data-stu-id="be813-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="be813-214">Устройство уже зарегистрировано</span><span class="sxs-lookup"><span data-stu-id="be813-214">Device already registered</span></span> | <span data-ttu-id="be813-215">Это устройство уже зарегистрировано в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="be813-215">This device is already registered to your organization.</span></span> <span data-ttu-id="be813-216">Дальнейшие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="be813-216">No further action required.</span></span> |
| <span data-ttu-id="be813-217">Устройство заявлено другой организацией</span><span class="sxs-lookup"><span data-stu-id="be813-217">Device claimed by another organization</span></span> | <span data-ttu-id="be813-218">Это устройство уже заявлено другой организацией.</span><span class="sxs-lookup"><span data-stu-id="be813-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="be813-219">Обратитесь к поставщику устройства.</span><span class="sxs-lookup"><span data-stu-id="be813-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="be813-220">Непредвиденная ошибка</span><span class="sxs-lookup"><span data-stu-id="be813-220">Unexpected error</span></span> | <span data-ttu-id="be813-221">Не удалось автоматически обработать запрос.</span><span class="sxs-lookup"><span data-stu-id="be813-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="be813-222">Обратитесь в службу поддержки и введите идентификатор запроса: <requestId></span><span class="sxs-lookup"><span data-stu-id="be813-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="be813-223">Проверка изображения</span><span class="sxs-lookup"><span data-stu-id="be813-223">Check the image</span></span>

<span data-ttu-id="be813-224">Если ваше устройство поступило от поставщика управляемого партнера Майкрософт для настольных ПК, изображение должно быть правильным.</span><span class="sxs-lookup"><span data-stu-id="be813-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="be813-225">Вы также можете применить образ самостоятельно, если хотите.</span><span class="sxs-lookup"><span data-stu-id="be813-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="be813-226">Чтобы приступить к работе, обратитесь к представителю Майкрософт, с которым вы работаете, и укажите расположение и действия по применению образа.</span><span class="sxs-lookup"><span data-stu-id="be813-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="be813-227">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="be813-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be813-228">Прежде чем вы перейдете на устройство для пользователя, убедитесь, что вы получили и применили [соответствующие лицензии](../get-ready/prerequisites.md) для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="be813-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="be813-229">Если все лицензии применяются, вы можете [приступить к работе с устройствами](get-started-devices.md), а затем, когда пользователь сможет запустить устройство и выполнить установку Windows.</span><span class="sxs-lookup"><span data-stu-id="be813-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









