---
title: Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)
description: Развертывание пакета конфигурации на устройстве виртуальной инфраструктуры настольных компьютеров (VDI), чтобы они были размещены в службе Microsoft Defender для конечных точек.
keywords: настройка устройства виртуальной инфраструктуры настольных компьютеров, vdi, управления устройствами, настройка конечных точек ATP Windows, настройка конечных точек Microsoft Defender для конечных точек endpoint
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
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 1e970be7967e221c29017be804a98770a778654f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892797"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="91a99-104">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="91a99-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="91a99-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="91a99-105">**Applies to:**</span></span>
- [<span data-ttu-id="91a99-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="91a99-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="91a99-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91a99-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="91a99-108">Устройства виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="91a99-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="91a99-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="91a99-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="91a99-110">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="91a99-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="91a99-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="91a99-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="91a99-112">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="91a99-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="91a99-113">Defender for Endpoint поддерживает непродержку сеанса VDI в бортовом окантовке.</span><span class="sxs-lookup"><span data-stu-id="91a99-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="91a99-114">При висячих VDIs могут возникнуть связанные проблемы.</span><span class="sxs-lookup"><span data-stu-id="91a99-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="91a99-115">Для этого сценария характерны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="91a99-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="91a99-116">Мгновенный ранний сеанс, который должен быть переназначелен в Defender для конечной точки до фактического обеспечения.</span><span class="sxs-lookup"><span data-stu-id="91a99-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="91a99-117">Имя устройства обычно используется повторно для новых сеансов.</span><span class="sxs-lookup"><span data-stu-id="91a99-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="91a99-118">Устройства VDI могут отображаться на портале Defender для конечных точек так же:</span><span class="sxs-lookup"><span data-stu-id="91a99-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="91a99-119">Одна запись для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="91a99-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="91a99-120">В этом случае одно и *то же* имя устройства необходимо настроить после создания сеанса, например с помощью неавтоматного файла ответа.</span><span class="sxs-lookup"><span data-stu-id="91a99-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="91a99-121">Несколько записей для каждого устройства — по одной для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="91a99-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="91a99-122">В следующих действиях вы сможете пройти через входные устройства VDI и выделить действия для одиночных и нескольких записей.</span><span class="sxs-lookup"><span data-stu-id="91a99-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="91a99-123">В средах с низкой конфигурацией ресурсов процедура загрузки VDI может замедлить загрузку датчика Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="91a99-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="91a99-124">Для Windows 10 или Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="91a99-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="91a99-125">Откройте пакет конфигурации VDI .zip file *(WindowsDefenderATPOnboardingPackage.zip), загруженный* из мастера бортового обслуживания.</span><span class="sxs-lookup"><span data-stu-id="91a99-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="91a99-126">Вы также можете получить пакет из [Центра безопасности Защитника Майкрософт:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="91a99-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="91a99-127">В области навигации выберите **параметры**  >  **onboarding**.</span><span class="sxs-lookup"><span data-stu-id="91a99-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="91a99-128">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="91a99-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="91a99-129">В поле **методов развертывания** выберите **скрипты ВДИ для неустанных конечных точек.**</span><span class="sxs-lookup"><span data-stu-id="91a99-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="91a99-130">Нажмите **кнопку Скачать пакет** и сохранить файл .zip.</span><span class="sxs-lookup"><span data-stu-id="91a99-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="91a99-131">Скопируйте файлы из папки WindowsDefenderATPOnboardingPackage, извлеченной из файла .zip, в изображение `golden/master` под `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` путем.</span><span class="sxs-lookup"><span data-stu-id="91a99-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="91a99-132">Если вы не реализуете одну запись для каждого устройства, скопируйте WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="91a99-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="91a99-133">Если вы реализуете одну запись для каждого устройства, скопируйте как Onboard-NonPersistentMachine.ps1, так и WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="91a99-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="91a99-134">Если папку не видно, она может `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` быть скрыта.</span><span class="sxs-lookup"><span data-stu-id="91a99-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="91a99-135">Вам потребуется выбрать параметр Показать скрытые файлы **и папки** из File Explorer.</span><span class="sxs-lookup"><span data-stu-id="91a99-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="91a99-136">Откройте окно редактора локальной групповой политики и перейдите **к** запуску сценариев настройки  >    >    >  Windows.</span><span class="sxs-lookup"><span data-stu-id="91a99-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="91a99-137">Политика группы домена также может использоваться для использования на бортовых устройствах СДВ.</span><span class="sxs-lookup"><span data-stu-id="91a99-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="91a99-138">В зависимости от метода, который вы хотите реализовать, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="91a99-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="91a99-139">Для одной записи для каждого устройства:</span><span class="sxs-lookup"><span data-stu-id="91a99-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="91a99-140">Выберите **вкладку PowerShell Scripts,** а затем нажмите **кнопку Добавить** (Обозреватель Windows откроется непосредственно в пути, на котором вы скопировали сценарий на борту ранее).</span><span class="sxs-lookup"><span data-stu-id="91a99-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="91a99-141">Перейдите к сценарию onboarding `Onboard-NonPersistentMachine.ps1` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91a99-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="91a99-142">Нет необходимости указывать другой файл, так как он будет активируется автоматически.</span><span class="sxs-lookup"><span data-stu-id="91a99-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="91a99-143">Для нескольких записей для каждого устройства:</span><span class="sxs-lookup"><span data-stu-id="91a99-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="91a99-144">Выберите **вкладку Scripts,** а затем нажмите **кнопку Добавить** (Обозреватель Windows откроется непосредственно в пути, где вы скопировали сценарий для вкладки ранее).</span><span class="sxs-lookup"><span data-stu-id="91a99-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="91a99-145">Перейдите к сценарию висят `WindowsDefenderATPOnboardingScript.cmd` баш.</span><span class="sxs-lookup"><span data-stu-id="91a99-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="91a99-146">Проверьте свое решение:</span><span class="sxs-lookup"><span data-stu-id="91a99-146">Test your solution:</span></span>

   1. <span data-ttu-id="91a99-147">Создайте пул с одним устройством.</span><span class="sxs-lookup"><span data-stu-id="91a99-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="91a99-148">Logon to device.</span><span class="sxs-lookup"><span data-stu-id="91a99-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="91a99-149">Вход с устройства.</span><span class="sxs-lookup"><span data-stu-id="91a99-149">Logoff from device.</span></span>

   1. <span data-ttu-id="91a99-150">Logon для устройства с другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="91a99-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="91a99-151">В зависимости от метода, который вы хотите реализовать, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="91a99-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="91a99-152">Для одной записи для каждого устройства:</span><span class="sxs-lookup"><span data-stu-id="91a99-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="91a99-153">Проверьте только одну запись в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="91a99-153">Check only one entry in Microsoft Defender Security Center.</span></span>

      - <span data-ttu-id="91a99-154">Для нескольких записей для каждого устройства:</span><span class="sxs-lookup"><span data-stu-id="91a99-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="91a99-155">Проверьте несколько записей в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="91a99-155">Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="91a99-156">Щелкните **список Устройств** на области навигации.</span><span class="sxs-lookup"><span data-stu-id="91a99-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="91a99-157">Используйте функцию поиска, введите имя устройства и выберите **Устройство** в качестве типа поиска.</span><span class="sxs-lookup"><span data-stu-id="91a99-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="91a99-158">Для downlevel SKUs</span><span class="sxs-lookup"><span data-stu-id="91a99-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="91a99-159">Следующий реестр актуален только в том случае, если цель состоит в достижении "Единой записи для каждого устройства".</span><span class="sxs-lookup"><span data-stu-id="91a99-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="91a99-160">Установите значение реестра:</span><span class="sxs-lookup"><span data-stu-id="91a99-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="91a99-161">или с помощью командной строки:</span><span class="sxs-lookup"><span data-stu-id="91a99-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="91a99-162">Следуйте [за процессом бортовой обработки сервера.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="91a99-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="91a99-163">Обновление нестандартных изображений виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="91a99-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="91a99-164">В качестве наилучшей практики рекомендуется использовать средства автономного обслуживания для исправления золотых и мастер-изображений.</span><span class="sxs-lookup"><span data-stu-id="91a99-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="91a99-165">Например, вы можете использовать ниже команд для установки обновления, пока изображение остается в автономном режиме:</span><span class="sxs-lookup"><span data-stu-id="91a99-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="91a99-166">Дополнительные сведения о командах DISM и автономном обслуживании см. в статьях ниже:</span><span class="sxs-lookup"><span data-stu-id="91a99-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="91a99-167">Изменение образа Windows с помощью DISM</span><span class="sxs-lookup"><span data-stu-id="91a99-167">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="91a99-168">Параметры управления изображениями DISM Command-Line</span><span class="sxs-lookup"><span data-stu-id="91a99-168">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="91a99-169">Уменьшение размера магазина компонентов в автономном изображении Windows</span><span class="sxs-lookup"><span data-stu-id="91a99-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="91a99-170">Если автономное обслуживание не является жизнеспособным вариантом для среды нестойких VDI, необходимо предпринять следующие действия для обеспечения согласованности и безопасности датчиков:</span><span class="sxs-lookup"><span data-stu-id="91a99-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="91a99-171">После загрузки мастер-изображения для онлайн-обслуживания или исправления запустите сценарий offboarding, чтобы отключить датчик Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="91a99-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="91a99-172">Дополнительные сведения см. в [таблице Offboard devices с помощью локального скрипта.](configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="91a99-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="91a99-173">Убедитесь, что датчик остановлен, запуская команду ниже в окне CMD:</span><span class="sxs-lookup"><span data-stu-id="91a99-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="91a99-174">Обслуживание изображения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="91a99-174">Service the image as needed.</span></span>

4. <span data-ttu-id="91a99-175">Запустите ниже команд с помощью PsExec.exe (которые можно скачать для очистки содержимого кибер-папки, которые датчик, возможно, https://download.sysinternals.com/files/PSTools.zip) накопил после загрузки:</span><span class="sxs-lookup"><span data-stu-id="91a99-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="91a99-176">Повторно запечатыть золотое/мастер-изображение, как обычно.</span><span class="sxs-lookup"><span data-stu-id="91a99-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="91a99-177">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="91a99-177">Related topics</span></span>
- [<span data-ttu-id="91a99-178">На борту устройств Windows 10 с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="91a99-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="91a99-179">На борту устройств Windows 10 с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="91a99-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="91a99-180">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="91a99-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="91a99-181">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="91a99-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="91a99-182">Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки</span><span class="sxs-lookup"><span data-stu-id="91a99-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
