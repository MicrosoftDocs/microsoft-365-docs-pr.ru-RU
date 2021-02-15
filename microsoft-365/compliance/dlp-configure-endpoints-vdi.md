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
description: Развернете пакет конфигурации на устройстве инфраструктуры виртуальных рабочих стола (VDI), чтобы они были размещены в службе защиты от потери данных Конечной точки Microsoft 365.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769450"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="49d55-103">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="49d55-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="49d55-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="49d55-104">**Applies to:**</span></span>
- [<span data-ttu-id="49d55-105">Предотвращение потери данных конечной точки Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="49d55-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="49d55-106">Устройства инфраструктуры виртуальных рабочих стола (VDI)</span><span class="sxs-lookup"><span data-stu-id="49d55-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="49d55-107">Поддержка защиты от потери данных конечной точки Microsoft 365 для виртуального рабочего стола Windows поддерживает сценарии с одним сеансом.</span><span class="sxs-lookup"><span data-stu-id="49d55-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="49d55-108">Сценарии с несколькими сеансами на виртуальном рабочем столе Windows в настоящее время не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="49d55-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="49d55-109">Ветвь устройств VDI</span><span class="sxs-lookup"><span data-stu-id="49d55-109">Onboard VDI devices</span></span>

<span data-ttu-id="49d55-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span><span class="sxs-lookup"><span data-stu-id="49d55-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="49d55-111">Чтобы взламыть несохраняемые сеансы VDI, устройства VDI должны быть в Windows 10 1809 или выше.</span><span class="sxs-lookup"><span data-stu-id="49d55-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="49d55-112">При подборе VDIs могут возникнуть проблемы.</span><span class="sxs-lookup"><span data-stu-id="49d55-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="49d55-113">В этом сценарии типичные проблемы:</span><span class="sxs-lookup"><span data-stu-id="49d55-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="49d55-114">Мгновенное раннее подмавка кратковременных сеансов, которые должны быть переназначения в службу защиты от потери данных конечной точки Microsoft 365 перед фактической подготовкаю.</span><span class="sxs-lookup"><span data-stu-id="49d55-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="49d55-115">Имя устройства обычно используется повторно для новых сеансов.</span><span class="sxs-lookup"><span data-stu-id="49d55-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="49d55-116">Устройства VDI могут отображаться в Центре соответствия требованиям Microsoft 365 как:</span><span class="sxs-lookup"><span data-stu-id="49d55-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="49d55-117">Одна запись для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="49d55-117">Single entry for each device.</span></span>  
<span data-ttu-id="49d55-118">Обратите внимание, что  в этом случае при создания сеанса необходимо настроить одно и то же имя устройства, например с использованием файла ответов, не от имени которого установлено.</span><span class="sxs-lookup"><span data-stu-id="49d55-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="49d55-119">Несколько записей для каждого устройства — по одной для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="49d55-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="49d55-120">Далее приводится руководство по входоубору устройств VDI и выделены этапы для одной и нескольких записей.</span><span class="sxs-lookup"><span data-stu-id="49d55-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="49d55-121">В средах с низкой конфигурацией ресурсов процедура загрузки VDI может замедлить веху защиты от потери данных в Конечной точке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49d55-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="49d55-122">Откройте ZIP-файл пакета конфигурации \*\* VDI (DeviceCompliancePackage.zip), который вы скачали из мастера подбора службы.</span><span class="sxs-lookup"><span data-stu-id="49d55-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="49d55-123">В области навигации выберите **"Параметры** устройства для входящего  >  в  >  **нее".**</span><span class="sxs-lookup"><span data-stu-id="49d55-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="49d55-124">В поле **"Метод развертывания"** выберите сценарии взбора VDI для **постоянных конечных точек.**</span><span class="sxs-lookup"><span data-stu-id="49d55-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="49d55-125">Щелкните **"Скачать пакет"** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="49d55-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="49d55-126">Скопируйте файлы из папки DeviceCompliancePackage, извлеченной из ZIP-файла, в изображение `golden/master` по `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` пути.</span><span class="sxs-lookup"><span data-stu-id="49d55-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="49d55-127">Если вы не реализуете одну запись для каждого устройства, скопируйте DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="49d55-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="49d55-128">Если вы реализуете одну запись для каждого устройства, скопируйте и Onboard-NonPersistentMachine.ps1 DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="49d55-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="49d55-129">Если вы не видите папку, она может `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` быть скрыта.</span><span class="sxs-lookup"><span data-stu-id="49d55-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="49d55-130">Необходимо выбрать параметр "Показать скрытые **файлы и папки"** в проводнике.</span><span class="sxs-lookup"><span data-stu-id="49d55-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="49d55-131">Откройте окно редактора локальных групповых политик и перейдите к скриптам запуска параметров  >  **конфигурации**  >    >  компьютера.</span><span class="sxs-lookup"><span data-stu-id="49d55-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="49d55-132">Групповая политика домена также может использоваться для въехающих несохраняющихся устройств VDI.</span><span class="sxs-lookup"><span data-stu-id="49d55-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="49d55-133">В зависимости от метода, который вы хотите реализовать, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="49d55-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="49d55-134">**Для одной записи для каждого устройства**</span><span class="sxs-lookup"><span data-stu-id="49d55-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="49d55-135">Откройте **вкладку "Сценарии PowerShell",** а затем нажмите кнопку **"Добавить"** (проводник Windows откроется прямо по пути, в который ранее был скопирован сценарий вкладки).</span><span class="sxs-lookup"><span data-stu-id="49d55-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="49d55-136">Перейдите к сценарию входить в `Onboard-NonPersistentMachine.ps1` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49d55-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="49d55-137">**Для нескольких записей для каждого устройства:**</span><span class="sxs-lookup"><span data-stu-id="49d55-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="49d55-138">Перейдите **на вкладку** "Сценарии" и нажмите кнопку **"Добавить"** (проводник Windows откроется непосредственно по пути, куда ранее был скопирован сценарий вкладки).</span><span class="sxs-lookup"><span data-stu-id="49d55-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="49d55-139">Перейдите к сценарию onboarding `DeviceComplianceOnboardingScript.cmd` Bash.</span><span class="sxs-lookup"><span data-stu-id="49d55-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="49d55-140">Протестировать решение:</span><span class="sxs-lookup"><span data-stu-id="49d55-140">Test your solution:</span></span>

   1. <span data-ttu-id="49d55-141">Создайте пул с одним устройством.</span><span class="sxs-lookup"><span data-stu-id="49d55-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="49d55-142">Во время logon на устройстве.</span><span class="sxs-lookup"><span data-stu-id="49d55-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="49d55-143">Выйдите из устройства.</span><span class="sxs-lookup"><span data-stu-id="49d55-143">Logoff from device.</span></span>

   1. <span data-ttu-id="49d55-144">Во время этого действия во время устройства вы сможете работать с другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="49d55-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="49d55-145">**Для одной записи для каждого устройства:** проверьте только одну запись в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="49d55-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="49d55-146">**Для нескольких записей для каждого устройства:** проверьте несколько записей в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="49d55-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="49d55-147">Щелкните **список "Устройства"** в области навигации.</span><span class="sxs-lookup"><span data-stu-id="49d55-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="49d55-148">Используйте функцию поиска, введите имя устройства и выберите **"Устройство"** в качестве типа поиска.</span><span class="sxs-lookup"><span data-stu-id="49d55-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="49d55-149">Обновление образов инфраструктуры виртуальных рабочих стола (VDI) без сохраняемого сохраняемого рабочего стола</span><span class="sxs-lookup"><span data-stu-id="49d55-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="49d55-150">Рекомендуется использовать средства автономного обслуживания для исправления эталовых и эталовых образов.</span><span class="sxs-lookup"><span data-stu-id="49d55-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="49d55-151">Например, вы можете использовать команды ниже, чтобы установить обновление, пока образ остается в автономном режиме:</span><span class="sxs-lookup"><span data-stu-id="49d55-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="49d55-152">Дополнительные сведения о командах DISM и автономном обслуживании см. в статьях ниже:</span><span class="sxs-lookup"><span data-stu-id="49d55-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="49d55-153">Изменение образа Windows с помощью DISM</span><span class="sxs-lookup"><span data-stu-id="49d55-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="49d55-154">Параметры управления Command-Line DISM</span><span class="sxs-lookup"><span data-stu-id="49d55-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="49d55-155">Уменьшение размера хранения компонентов в автономном образе Windows</span><span class="sxs-lookup"><span data-stu-id="49d55-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="49d55-156">Если автономное обслуживание не является вариантом для несохраняемой среды VDI, необходимо предпринять следующие действия для обеспечения согласованности и безопасности датчиков:</span><span class="sxs-lookup"><span data-stu-id="49d55-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="49d55-157">После загрузки образа для онлайн-обслуживания или исправления запустите сценарий отключения, чтобы отключить датчик защиты от потери данных конечной точки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49d55-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="49d55-158">Дополнительные сведения см. в [подключеных устройствах с помощью локального сценария.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="49d55-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="49d55-159">Убедитесь, что датчик остановлен, выдав приведенную ниже команду в окне CMD:</span><span class="sxs-lookup"><span data-stu-id="49d55-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="49d55-160">Обслуживание изображения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="49d55-160">Service the image as needed.</span></span>

4. <span data-ttu-id="49d55-161">Запустите команды ниже с помощью PsExec.exe (которые можно скачать для очистки содержимого киберпамяти, которое может быть скоплено датчиком после https://download.sysinternals.com/files/PSTools.zip) загрузки:</span><span class="sxs-lookup"><span data-stu-id="49d55-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="49d55-162">Повторно запечатывка золотого/основному изображению, как обычно.</span><span class="sxs-lookup"><span data-stu-id="49d55-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="49d55-163">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="49d55-163">Related topics</span></span>
- [<span data-ttu-id="49d55-164">Ветвь устройств с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="49d55-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="49d55-165">Ветвь устройств с Windows 10 с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="49d55-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="49d55-166">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="49d55-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="49d55-167">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="49d55-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="49d55-168">Устранение неполадок с подсетями Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="49d55-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
