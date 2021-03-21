---
title: Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Развертывание пакета конфигурации на устройстве виртуальной инфраструктуры настольных компьютеров (VDI) таким образом, чтобы они были размещены в службе предотвращения потери данных конечной точки Microsoft 365.
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917955"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="280e1-103">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="280e1-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="280e1-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="280e1-104">**Applies to:**</span></span>
- [<span data-ttu-id="280e1-105">Предотвращение потери данных конечной точки Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="280e1-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="280e1-106">Устройства виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="280e1-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="280e1-107">Поддержка защиты от потери данных конечной точки Microsoft 365 для Windows Virtual Desktop поддерживает сценарии одного сеанса.</span><span class="sxs-lookup"><span data-stu-id="280e1-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="280e1-108">В настоящее время сценарии нескольких сеансов на виртуальном рабочем столе Windows не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="280e1-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="280e1-109">На борту устройств VDI</span><span class="sxs-lookup"><span data-stu-id="280e1-109">Onboard VDI devices</span></span>

<span data-ttu-id="280e1-110">Предотвращение потери данных конечной точки Microsoft 365 поддерживает неустанную запись сеанса VDI.</span><span class="sxs-lookup"><span data-stu-id="280e1-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="280e1-111">Чтобы на борту нестойких сеансов VDI устройства VDI должны быть на Windows 10 1809 или выше.</span><span class="sxs-lookup"><span data-stu-id="280e1-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="280e1-112">При висячих VDIs могут возникнуть связанные проблемы.</span><span class="sxs-lookup"><span data-stu-id="280e1-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="280e1-113">Для этого сценария характерны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="280e1-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="280e1-114">Мгновенный ранний учет недолговечивых сеансов, которые необходимо использовать в microsoft 365 Endpoint data loss prevention before the actual provisioning.</span><span class="sxs-lookup"><span data-stu-id="280e1-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="280e1-115">Имя устройства обычно используется повторно для новых сеансов.</span><span class="sxs-lookup"><span data-stu-id="280e1-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="280e1-116">Устройства VDI могут отображаться в центре соответствия требованиям Microsoft 365 так же:</span><span class="sxs-lookup"><span data-stu-id="280e1-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="280e1-117">Одна запись для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="280e1-117">Single entry for each device.</span></span>  
<span data-ttu-id="280e1-118">Обратите внимание, что  в этом случае при создания сеанса необходимо настроить одно и то же имя устройства, например с помощью неавтоматного файла ответа.</span><span class="sxs-lookup"><span data-stu-id="280e1-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="280e1-119">Несколько записей для каждого устройства — по одной для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="280e1-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="280e1-120">В следующих действиях вы сможете пройти через входные устройства VDI и выделить действия для одиночных и нескольких записей.</span><span class="sxs-lookup"><span data-stu-id="280e1-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="280e1-121">В средах с низкой конфигурацией ресурсов процедура загрузки VDI может замедлить процесс предотвращения потери данных конечной точки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="280e1-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="280e1-122">Откройте пакет конфигурации VDI .zip file *(DeviceCompliancePackage.zip), загруженный* из мастера бортового обслуживания.</span><span class="sxs-lookup"><span data-stu-id="280e1-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="280e1-123">В области навигации выберите **бортовую** установку Устройства  >    >  **параметров.**</span><span class="sxs-lookup"><span data-stu-id="280e1-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="280e1-124">В поле **методов развертывания** выберите **скрипты ВДИ для неустанных конечных точек.**</span><span class="sxs-lookup"><span data-stu-id="280e1-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="280e1-125">Нажмите **кнопку Скачать пакет** и сохранить файл .zip.</span><span class="sxs-lookup"><span data-stu-id="280e1-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="280e1-126">Скопируйте файлы из папки DeviceCompliancePackage, извлеченной из файла .zip, в `golden/master` изображение в `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` пути.</span><span class="sxs-lookup"><span data-stu-id="280e1-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="280e1-127">Если вы не реализуете одну запись для каждого устройства, скопируйте DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="280e1-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="280e1-128">Если вы реализуете одну запись для каждого устройства, скопируйте как Onboard-NonPersistentMachine.ps1, так и deviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="280e1-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="280e1-129">Если папку не видно, она может `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` быть скрыта.</span><span class="sxs-lookup"><span data-stu-id="280e1-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="280e1-130">Вам потребуется выбрать параметр Показать скрытые файлы **и папки** из File Explorer.</span><span class="sxs-lookup"><span data-stu-id="280e1-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="280e1-131">Откройте окно редактора локальной групповой политики и перейдите **к** запуску сценариев настройки  >    >    >  Windows.</span><span class="sxs-lookup"><span data-stu-id="280e1-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="280e1-132">Политика группы домена также может использоваться для использования на бортовых устройствах СДВ.</span><span class="sxs-lookup"><span data-stu-id="280e1-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="280e1-133">В зависимости от метода, который вы хотите реализовать, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="280e1-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="280e1-134">**Для одной записи для каждого устройства**</span><span class="sxs-lookup"><span data-stu-id="280e1-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="280e1-135">Выберите **вкладку PowerShell Scripts,** а затем нажмите **кнопку Добавить** (Обозреватель Windows откроется непосредственно в пути, на котором вы скопировали сценарий на борту ранее).</span><span class="sxs-lookup"><span data-stu-id="280e1-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="280e1-136">Перейдите к сценарию onboarding `Onboard-NonPersistentMachine.ps1` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="280e1-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="280e1-137">**Для нескольких записей для каждого устройства:**</span><span class="sxs-lookup"><span data-stu-id="280e1-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="280e1-138">Выберите **вкладку Scripts,** а затем нажмите **кнопку Добавить** (Обозреватель Windows откроется непосредственно в пути, где вы скопировали сценарий для вкладки ранее).</span><span class="sxs-lookup"><span data-stu-id="280e1-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="280e1-139">Перейдите к сценарию висят `DeviceComplianceOnboardingScript.cmd` баш.</span><span class="sxs-lookup"><span data-stu-id="280e1-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="280e1-140">Проверьте свое решение:</span><span class="sxs-lookup"><span data-stu-id="280e1-140">Test your solution:</span></span>

   1. <span data-ttu-id="280e1-141">Создайте пул с одним устройством.</span><span class="sxs-lookup"><span data-stu-id="280e1-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="280e1-142">Logon to device.</span><span class="sxs-lookup"><span data-stu-id="280e1-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="280e1-143">Вход с устройства.</span><span class="sxs-lookup"><span data-stu-id="280e1-143">Logoff from device.</span></span>

   1. <span data-ttu-id="280e1-144">Logon для устройства с другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="280e1-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="280e1-145">**Для одной записи для каждого устройства:** Проверьте только одну запись в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="280e1-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="280e1-146">**Для нескольких записей для каждого устройства:** Проверьте несколько записей в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="280e1-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="280e1-147">Щелкните **список Устройств** на области навигации.</span><span class="sxs-lookup"><span data-stu-id="280e1-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="280e1-148">Используйте функцию поиска, введите имя устройства и выберите **Устройство** в качестве типа поиска.</span><span class="sxs-lookup"><span data-stu-id="280e1-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="280e1-149">Обновление нестандартных изображений виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="280e1-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="280e1-150">В качестве наилучшей практики рекомендуется использовать средства автономного обслуживания для исправления золотых и мастер-изображений.</span><span class="sxs-lookup"><span data-stu-id="280e1-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="280e1-151">Например, вы можете использовать ниже команд для установки обновления, пока изображение остается в автономном режиме:</span><span class="sxs-lookup"><span data-stu-id="280e1-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="280e1-152">Дополнительные сведения о командах DISM и автономном обслуживании см. в статьях ниже:</span><span class="sxs-lookup"><span data-stu-id="280e1-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="280e1-153">Изменение образа Windows с помощью DISM</span><span class="sxs-lookup"><span data-stu-id="280e1-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="280e1-154">Параметры управления изображениями DISM Command-Line</span><span class="sxs-lookup"><span data-stu-id="280e1-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="280e1-155">Уменьшение размера магазина компонентов в автономном изображении Windows</span><span class="sxs-lookup"><span data-stu-id="280e1-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="280e1-156">Если автономное обслуживание не является жизнеспособным вариантом для среды нестойких VDI, необходимо предпринять следующие действия для обеспечения согласованности и безопасности датчиков:</span><span class="sxs-lookup"><span data-stu-id="280e1-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="280e1-157">После загрузки мастер-изображения для онлайн-обслуживания или исправления запустите сценарий offboarding, чтобы отключить датчик предотвращения потери конечных данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="280e1-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="280e1-158">Дополнительные сведения см. в [таблице Offboard devices с помощью локального скрипта.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="280e1-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="280e1-159">Убедитесь, что датчик остановлен, запуская команду ниже в окне CMD:</span><span class="sxs-lookup"><span data-stu-id="280e1-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="280e1-160">Обслуживание изображения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="280e1-160">Service the image as needed.</span></span>

4. <span data-ttu-id="280e1-161">Запустите ниже команд с помощью PsExec.exe (которые можно скачать для очистки содержимого кибер-папки, которые датчик, возможно, https://download.sysinternals.com/files/PSTools.zip) накопил после загрузки:</span><span class="sxs-lookup"><span data-stu-id="280e1-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="280e1-162">Повторно запечатыть золотое/мастер-изображение, как обычно.</span><span class="sxs-lookup"><span data-stu-id="280e1-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="280e1-163">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="280e1-163">Related topics</span></span>
- [<span data-ttu-id="280e1-164">На борту устройств Windows 10 с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="280e1-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="280e1-165">На борту устройств Windows 10 с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="280e1-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="280e1-166">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="280e1-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="280e1-167">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="280e1-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="280e1-168">Устранение неполадок с бортовой защитой расширенных угроз Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="280e1-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)