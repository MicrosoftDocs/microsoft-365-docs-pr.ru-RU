---
title: Встроенные устройства неустойчивой инфраструктуры виртуальных рабочих столов (VDI)
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
description: Разверните пакет конфигурации на устройстве инфраструктуры виртуальных рабочих столов (VDI), чтобы они были подключены к службе защиты от потери данных в Microsoft 365 Endpoint.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769450"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="900f5-103">Встроенные устройства неустойчивой инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="900f5-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="900f5-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="900f5-104">**Applies to:**</span></span>
- [<span data-ttu-id="900f5-105">Защита от потери данных (DLP) Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="900f5-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="900f5-106">Устройства в инфраструктуре виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="900f5-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="900f5-107">Поддержка защиты от потери данных в конечной точке Microsoft 365 для виртуальных рабочих столов Windows поддерживаются сценарии с одним сеансом.</span><span class="sxs-lookup"><span data-stu-id="900f5-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="900f5-108">Сценарии с несколькими сеансами на виртуальном рабочем столе Windows в настоящее время не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="900f5-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="900f5-109">Встроенные устройства VDI</span><span class="sxs-lookup"><span data-stu-id="900f5-109">Onboard VDI devices</span></span>

<span data-ttu-id="900f5-110">Защита от потери данных в конечных точках Microsoft 365 поддерживает непостоянную входящую миграцию сеансов VDI.</span><span class="sxs-lookup"><span data-stu-id="900f5-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="900f5-111">Для встроенных непостоянных сеансов VDI устройства VDI должны находиться в Windows 10 1809 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="900f5-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="900f5-112">При подключении Вдис могут возникнуть проблемы, связанные с подключением.</span><span class="sxs-lookup"><span data-stu-id="900f5-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="900f5-113">Ниже перечислены типичные проблемы, возникающие в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="900f5-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="900f5-114">Мгновенная миграция кратковременных сеансов кратковременной миграции, которая должна быть поставлена в корпорацию Майкрософт 365 защита от потери данных в конечной точке до реальной подготовки.</span><span class="sxs-lookup"><span data-stu-id="900f5-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="900f5-115">Имя устройства обычно используется повторно для новых сеансов.</span><span class="sxs-lookup"><span data-stu-id="900f5-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="900f5-116">Устройства VDI могут отображаться в центре соответствия требованиям Microsoft 365 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="900f5-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="900f5-117">Один элемент для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="900f5-117">Single entry for each device.</span></span>  
<span data-ttu-id="900f5-118">Обратите внимание, *что в этом случае имя устройства должно* быть настроено при создании сеанса, например с помощью файла ответов автоматической установки.</span><span class="sxs-lookup"><span data-stu-id="900f5-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="900f5-119">Несколько записей для каждого устройства — одно для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="900f5-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="900f5-120">Ниже приведены инструкции по переносу устройств VDI и выделяются действия для одной и нескольких записей.</span><span class="sxs-lookup"><span data-stu-id="900f5-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="900f5-121">В средах, где существуют недорогие конфигурации ресурсов, процедура загрузки VDI может замедлить приподключение защиты от потери данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="900f5-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="900f5-122">Откройте ZIP-файл пакета конфигурации VDI ( *DeviceCompliancePackage.zip* ), скачанный с помощью мастера входящей миграции служб.</span><span class="sxs-lookup"><span data-stu-id="900f5-122">Open the VDI configuration package .zip file ( *DeviceCompliancePackage.zip* ) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="900f5-123">В области навигации выберите **Параметры** входящей миграции  >  **устройств**  >  **Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="900f5-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="900f5-124">В поле **метод развертывания** выберите **сценарии входящей миграции VDI для непостоянных конечных точек** .</span><span class="sxs-lookup"><span data-stu-id="900f5-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints** .</span></span>

5. <span data-ttu-id="900f5-125">Нажмите кнопку **загрузить пакет** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="900f5-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="900f5-126">Скопируйте файлы из папки Девицекомплианцепаккаже, извлеченной из ZIP-файла, в `golden/master` образ по пути `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="900f5-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="900f5-127">Если вы не реализуете одну запись для каждого устройства, скопируйте Девицекомплианцеонбоардингскрипт. cmd.</span><span class="sxs-lookup"><span data-stu-id="900f5-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="900f5-128">Если вы реализуете одну запись для каждого устройства, скопируйте как Onboard-NonPersistentMachine.ps1, так и Девицекомплианцеонбоардингскрипт. cmd.</span><span class="sxs-lookup"><span data-stu-id="900f5-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="900f5-129">Если папка не отображается `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` , она может быть скрыта.</span><span class="sxs-lookup"><span data-stu-id="900f5-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="900f5-130">Необходимо выбрать параметр **Показать скрытые файлы и папки** в проводнике.</span><span class="sxs-lookup"><span data-stu-id="900f5-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="900f5-131">Откройте окно редактора локальной групповой политики и перейдите к разделу **Конфигурация компьютера** "  >  **Параметры Windows** "  >  **сценарии**  >  **запуска** сценариев.</span><span class="sxs-lookup"><span data-stu-id="900f5-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup** .</span></span>

   > [!NOTE]
   > <span data-ttu-id="900f5-132">Для входящей миграции непостоянных устройств VDI также может использоваться групповая политика домена.</span><span class="sxs-lookup"><span data-stu-id="900f5-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="900f5-133">В зависимости от метода, который вы хотите реализовать, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="900f5-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="900f5-134">**Для одной записи для каждого устройства**</span><span class="sxs-lookup"><span data-stu-id="900f5-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="900f5-135">Перейдите на вкладку **сценарии PowerShell** и нажмите кнопку **Добавить** (проводник Windows откроется непосредственно в папке, в которую ранее был скопирован сценарий входящей миграции).</span><span class="sxs-lookup"><span data-stu-id="900f5-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="900f5-136">Перейдите к встроенному скрипту PowerShell `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="900f5-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="900f5-137">**Для нескольких записей каждого устройства** :</span><span class="sxs-lookup"><span data-stu-id="900f5-137">**For multiple entries for each device** :</span></span>
   
   <span data-ttu-id="900f5-138">Перейдите на вкладку **сценарии** и нажмите кнопку **Добавить** (проводник Windows откроется непосредственно в папке, в которую ранее был скопирован сценарий входящей миграции).</span><span class="sxs-lookup"><span data-stu-id="900f5-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="900f5-139">Перейдите в сценарий bash входящей миграции `DeviceComplianceOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="900f5-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="900f5-140">Протестируйте решение:</span><span class="sxs-lookup"><span data-stu-id="900f5-140">Test your solution:</span></span>

   1. <span data-ttu-id="900f5-141">Создайте пул с одним устройством.</span><span class="sxs-lookup"><span data-stu-id="900f5-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="900f5-142">Вход на устройство.</span><span class="sxs-lookup"><span data-stu-id="900f5-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="900f5-143">Выход с устройства.</span><span class="sxs-lookup"><span data-stu-id="900f5-143">Logoff from device.</span></span>

   1. <span data-ttu-id="900f5-144">Вход на устройство с другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="900f5-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="900f5-145">**Для одной записи каждого устройства** : Проверьте только одну запись в центре безопасности защитника Microsoft.</span><span class="sxs-lookup"><span data-stu-id="900f5-145">**For single entry for each device** : Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="900f5-146">**Для нескольких записей каждого устройства** : Проверьте несколько записей в центре безопасности защитника Microsoft.</span><span class="sxs-lookup"><span data-stu-id="900f5-146">**For multiple entries for each device** : Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="900f5-147">В области навигации выберите пункт **список устройств** .</span><span class="sxs-lookup"><span data-stu-id="900f5-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="900f5-148">Используйте функцию поиска, введя имя устройства и выбрав **устройство** в качестве типа поиска.</span><span class="sxs-lookup"><span data-stu-id="900f5-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="900f5-149">Обновление образов инфраструктуры неустойчивых виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="900f5-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="900f5-150">Рекомендуется использовать автономные средства обслуживания для исправления эталонных и основных образов.</span><span class="sxs-lookup"><span data-stu-id="900f5-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="900f5-151">Например, вы можете использовать приведенные ниже команды для установки обновления, когда изображение остается в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="900f5-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="900f5-152">Для получения дополнительных сведений о командах DISM и автономном обслуживании обратитесь к следующим статьям:</span><span class="sxs-lookup"><span data-stu-id="900f5-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="900f5-153">Изменение образа Windows с помощью DISM</span><span class="sxs-lookup"><span data-stu-id="900f5-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="900f5-154">Параметры Command-Line управления изображениями DISM</span><span class="sxs-lookup"><span data-stu-id="900f5-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="900f5-155">Уменьшение размера хранилища компонентов в автономном образе Windows</span><span class="sxs-lookup"><span data-stu-id="900f5-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="900f5-156">Если автономное обслуживание не является допустимым вариантом для непостоянной среды VDI, необходимо выполнить следующие действия для обеспечения согласованности и работоспособности датчика.</span><span class="sxs-lookup"><span data-stu-id="900f5-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="900f5-157">После загрузки основного образа для интерактивного обслуживания или исправления запустите сценарий отключения, чтобы отключить датчик защиты от потери данных в Microsoft 365 Endpoint.</span><span class="sxs-lookup"><span data-stu-id="900f5-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="900f5-158">Для получения дополнительных сведений посетите [переносе устройства с помощью локального сценария](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="900f5-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="900f5-159">Убедитесь, что датчик остановлен, выполнив указанную ниже команду в окне CMD:</span><span class="sxs-lookup"><span data-stu-id="900f5-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="900f5-160">Обслуживание изображения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="900f5-160">Service the image as needed.</span></span>

4. <span data-ttu-id="900f5-161">Выполните приведенные ниже команды с помощью PsExec.exe (которые можно скачать, https://download.sysinternals.com/files/PSTools.zip) чтобы очистить содержимое папки кибератак, которое может накапливаться датчиком с момента загрузки:</span><span class="sxs-lookup"><span data-stu-id="900f5-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="900f5-162">Запечатайте Золотой и основной образ, как обычно.</span><span class="sxs-lookup"><span data-stu-id="900f5-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="900f5-163">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="900f5-163">Related topics</span></span>
- [<span data-ttu-id="900f5-164">Встроенные устройства с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="900f5-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="900f5-165">Встроенные устройства с Windows 10 с помощью диспетчера конфигураций конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="900f5-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="900f5-166">Встроенные устройства с Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="900f5-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="900f5-167">Встроенные устройства с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="900f5-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="900f5-168">Устранение неполадок, связанных с Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="900f5-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
