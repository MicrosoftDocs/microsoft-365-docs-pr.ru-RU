---
title: Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)
description: Развертывание пакета конфигурации на устройстве виртуальной инфраструктуры настольных компьютеров (VDI), чтобы они были размещены в службе ATP Microsoft Defender.
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
ms.openlocfilehash: 167db9b5da841528e95f167b3af6a840b6c71eb4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165565"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="e5c8b-104">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="e5c8b-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e5c8b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-105">**Applies to:**</span></span>
- [<span data-ttu-id="e5c8b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e5c8b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e5c8b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5c8b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="e5c8b-108">Устройства виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="e5c8b-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="e5c8b-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="e5c8b-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="e5c8b-110">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e5c8b-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e5c8b-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="e5c8b-112">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="e5c8b-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="e5c8b-113">Defender for Endpoint поддерживает непродержку сеанса VDI в бортовом окантовке.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="e5c8b-114">При висячих VDIs могут возникнуть связанные проблемы.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="e5c8b-115">Для этого сценария характерны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="e5c8b-116">Мгновенный ранний сеанс, который должен быть переназначелен в Defender для конечной точки до фактического обеспечения.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="e5c8b-117">Имя устройства обычно используется повторно для новых сеансов.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="e5c8b-118">Устройства VDI могут отображаться на портале Defender для конечных точек так же:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="e5c8b-119">Одна запись для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-119">Single entry for each device.</span></span>  
<span data-ttu-id="e5c8b-120">Обратите внимание, что  в этом случае при создания сеанса необходимо настроить одно и то же имя устройства, например с помощью неавтоматного файла ответа.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-120">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="e5c8b-121">Несколько записей для каждого устройства — по одной для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="e5c8b-122">В следующих действиях вы сможете пройти через входные устройства VDI и выделить действия для одиночных и нескольких записей.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="e5c8b-123">В средах с низкой конфигурацией ресурсов процедура загрузки VDI может замедлить загрузку датчика Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="e5c8b-124">Для Windows 10 или Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e5c8b-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="e5c8b-125">Откройте пакет конфигурации VDI .zip file *(WindowsDefenderATPOnboardingPackage.zip), загруженный* из мастера бортового обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="e5c8b-126">Вы также можете получить пакет из [Центра безопасности Защитника Майкрософт:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="e5c8b-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="e5c8b-127">В области навигации выберите **параметры**  >  **onboarding**.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="e5c8b-128">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="e5c8b-129">В поле **методов развертывания** выберите **скрипты ВДИ для неустанных конечных точек.**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="e5c8b-130">Нажмите **кнопку Скачать пакет** и сохранить файл .zip.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="e5c8b-131">Скопируйте файлы из папки WindowsDefenderATPOnboardingPackage, извлеченной из файла .zip, в изображение `golden/master` под `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` путем.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="e5c8b-132">Если вы не реализуете одну запись для каждого устройства, скопируйте WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="e5c8b-133">Если вы реализуете одну запись для каждого устройства, скопируйте как Onboard-NonPersistentMachine.ps1, так и WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e5c8b-134">Если папку не видно, она может `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` быть скрыта.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="e5c8b-135">Вам потребуется выбрать параметр Показать скрытые файлы **и папки** из File Explorer.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="e5c8b-136">Откройте окно редактора локальной групповой политики и перейдите **к** запуску сценариев настройки  >    >    >  Windows.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e5c8b-137">Политика группы домена также может использоваться для использования на бортовых устройствах СДВ.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="e5c8b-138">В зависимости от метода, который вы хотите реализовать, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span> <br>
   <span data-ttu-id="e5c8b-139">**Для одной записи для каждого устройства:**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-139">**For single entry for each device**:</span></span><br>
   
   <span data-ttu-id="e5c8b-140">Выберите **вкладку PowerShell Scripts,** а затем нажмите **кнопку Добавить** (Обозреватель Windows откроется непосредственно в пути, на котором вы скопировали сценарий на борту ранее).</span><span class="sxs-lookup"><span data-stu-id="e5c8b-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e5c8b-141">Перейдите к сценарию onboarding `Onboard-NonPersistentMachine.ps1` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="e5c8b-142">**Для нескольких записей для каждого устройства:**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-142">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="e5c8b-143">Выберите **вкладку Scripts,** а затем нажмите **кнопку Добавить** (Обозреватель Windows откроется непосредственно в пути, где вы скопировали сценарий для вкладки ранее).</span><span class="sxs-lookup"><span data-stu-id="e5c8b-143">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e5c8b-144">Перейдите к сценарию висят `WindowsDefenderATPOnboardingScript.cmd` баш.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-144">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="e5c8b-145">Проверьте свое решение:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-145">Test your solution:</span></span>

   1. <span data-ttu-id="e5c8b-146">Создайте пул с одним устройством.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-146">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="e5c8b-147">Logon to device.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-147">Logon to device.</span></span>
      
   1. <span data-ttu-id="e5c8b-148">Вход с устройства.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-148">Logoff from device.</span></span>

   1. <span data-ttu-id="e5c8b-149">Logon для устройства с другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-149">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="e5c8b-150">**Для одной записи для каждого устройства:** Проверьте только одну запись в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-150">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="e5c8b-151">**Для нескольких записей для каждого устройства:** Проверьте несколько записей в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-151">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="e5c8b-152">Щелкните **список Устройств** на области навигации.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-152">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="e5c8b-153">Используйте функцию поиска, введите имя устройства и выберите **Устройство** в качестве типа поиска.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-153">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="e5c8b-154">Для downlevel SKUs</span><span class="sxs-lookup"><span data-stu-id="e5c8b-154">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="e5c8b-155">Следующий реестр актуален только в том случае, если цель состоит в достижении "Единой записи для каждого устройства".</span><span class="sxs-lookup"><span data-stu-id="e5c8b-155">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="e5c8b-156">Установите значение реестра:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-156">Set registry value to:</span></span>

    ```reg
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="e5c8b-157">или с помощью командной строки:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-157">or using command line:</span></span>

    ```
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="e5c8b-158">Следуйте [за процессом бортовой обработки сервера.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="e5c8b-158">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="e5c8b-159">Обновление нестандартных изображений виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="e5c8b-159">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="e5c8b-160">В качестве наилучшей практики рекомендуется использовать средства автономного обслуживания для исправления золотых и мастер-изображений.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-160">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="e5c8b-161">Например, вы можете использовать ниже команд для установки обновления, пока изображение остается в автономном режиме:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-161">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="e5c8b-162">Дополнительные сведения о командах DISM и автономном обслуживании см. в статьях ниже:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-162">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="e5c8b-163">Изменение образа Windows с помощью DISM</span><span class="sxs-lookup"><span data-stu-id="e5c8b-163">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="e5c8b-164">Параметры управления изображениями DISM Command-Line</span><span class="sxs-lookup"><span data-stu-id="e5c8b-164">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="e5c8b-165">Уменьшение размера магазина компонентов в автономном изображении Windows</span><span class="sxs-lookup"><span data-stu-id="e5c8b-165">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="e5c8b-166">Если автономное обслуживание не является жизнеспособным вариантом для среды нестойких VDI, необходимо предпринять следующие действия для обеспечения согласованности и безопасности датчиков:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-166">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="e5c8b-167">После загрузки мастер-изображения для онлайн-обслуживания или исправления запустите сценарий offboarding, чтобы отключить датчик Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-167">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="e5c8b-168">Дополнительные сведения см. в [таблице Offboard devices с помощью локального скрипта.](configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="e5c8b-168">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="e5c8b-169">Убедитесь, что датчик остановлен, запуская команду ниже в окне CMD:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-169">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="e5c8b-170">Обслуживание изображения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-170">Service the image as needed.</span></span>

4. <span data-ttu-id="e5c8b-171">Запустите ниже команд с помощью PsExec.exe (которые можно скачать для очистки содержимого кибер-папки, которые датчик, возможно, https://download.sysinternals.com/files/PSTools.zip) накопил после загрузки:</span><span class="sxs-lookup"><span data-stu-id="e5c8b-171">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="e5c8b-172">Повторно запечатыть золотое/мастер-изображение, как обычно.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-172">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5c8b-173">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e5c8b-173">Related topics</span></span>
- [<span data-ttu-id="e5c8b-174">На борту устройств Windows 10 с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="e5c8b-174">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="e5c8b-175">На борту устройств Windows 10 с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e5c8b-175">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="e5c8b-176">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="e5c8b-176">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="e5c8b-177">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="e5c8b-177">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="e5c8b-178">Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки</span><span class="sxs-lookup"><span data-stu-id="e5c8b-178">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
