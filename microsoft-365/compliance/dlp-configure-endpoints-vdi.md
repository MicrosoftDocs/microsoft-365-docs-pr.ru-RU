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
description: Развертывание пакета конфигурации на устройстве виртуальной инфраструктуры настольных компьютеров (VDI), чтобы они были Microsoft 365 службу предотвращения потери данных конечной точки.
ms.openlocfilehash: 64d9bfed3d1d5600b5843c697e894577f83527fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226879"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="dca62-103">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="dca62-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="dca62-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="dca62-104">**Applies to:**</span></span>
- [<span data-ttu-id="dca62-105">Microsoft 365 Предотвращение потери конечных данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="dca62-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="dca62-106">Устройства виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="dca62-106">Virtual desktop infrastructure (VDI) devices</span></span>

> [!WARNING]
> <span data-ttu-id="dca62-107">Microsoft 365 Поддержка предотвращения потери данных конечной точки для Windows Virtual Desktop поддерживает сценарии одного сеанса.</span><span class="sxs-lookup"><span data-stu-id="dca62-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="dca62-108">Сценарии нескольких сеансов на Windows в настоящее время не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="dca62-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="dca62-109">На борту устройств VDI</span><span class="sxs-lookup"><span data-stu-id="dca62-109">Onboard VDI devices</span></span>

<span data-ttu-id="dca62-110">Microsoft 365 Предотвращение потери данных конечной точки поддерживает непродержку сеанса VDI на борту.</span><span class="sxs-lookup"><span data-stu-id="dca62-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span>

> [!NOTE]
> <span data-ttu-id="dca62-111">Чтобы на борту нестойких сеансов VDI устройства VDI должны быть Windows 10 1809 или выше.</span><span class="sxs-lookup"><span data-stu-id="dca62-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="dca62-112">При висячих VDIs могут возникнуть связанные проблемы.</span><span class="sxs-lookup"><span data-stu-id="dca62-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="dca62-113">Для этого сценария характерны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="dca62-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="dca62-114">Мгновенный ранний сеанс, который необходимо использовать для Microsoft 365 предотвращения потери данных конечной точки перед фактической подготовкаю.</span><span class="sxs-lookup"><span data-stu-id="dca62-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="dca62-115">Имя устройства обычно используется повторно для новых сеансов.</span><span class="sxs-lookup"><span data-stu-id="dca62-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="dca62-116">Устройства VDI могут отображаться в центре Microsoft 365 соответствия требованиям как таковые:</span><span class="sxs-lookup"><span data-stu-id="dca62-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="dca62-117">Одна запись для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="dca62-117">Single entry for each device.</span></span>
<span data-ttu-id="dca62-118">Обратите внимание, что  в этом случае при создания сеанса необходимо настроить одно и то же имя устройства, например с помощью неавтоматного файла ответа.</span><span class="sxs-lookup"><span data-stu-id="dca62-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="dca62-119">Несколько записей для каждого устройства — по одной для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="dca62-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="dca62-120">В следующих действиях вы сможете пройти через входные устройства VDI и выделить действия для одиночных и нескольких записей.</span><span class="sxs-lookup"><span data-stu-id="dca62-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

> [!WARNING]
> <span data-ttu-id="dca62-121">В средах с низкими конфигурациями ресурсов процедура загрузки VDI может замедлить Microsoft 365 предотвращения потери данных конечной точки.</span><span class="sxs-lookup"><span data-stu-id="dca62-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span>

1. <span data-ttu-id="dca62-122">Откройте пакет конфигурации VDI .zip *(DeviceCompliancePackage.zip), который* вы скачали из мастера бортового обслуживания.</span><span class="sxs-lookup"><span data-stu-id="dca62-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2. <span data-ttu-id="dca62-123">В области навигации выберите **Параметры**  >  **бортового**  >  устройства.</span><span class="sxs-lookup"><span data-stu-id="dca62-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="dca62-124">В поле **методов развертывания** выберите **скрипты ВДИ для неустанных конечных точек.**</span><span class="sxs-lookup"><span data-stu-id="dca62-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

4. <span data-ttu-id="dca62-125">Нажмите **кнопку Загрузка** пакета и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="dca62-125">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="dca62-126">Скопируйте файлы из папки DeviceCompliancePackage, извлеченной из файла .zip в образ `golden/master` под пути `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="dca62-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span>

6. <span data-ttu-id="dca62-127">Если вы не реализуете одну запись для каждого устройства, скопируйте DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="dca62-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

7. <span data-ttu-id="dca62-128">Если вы реализуете одну запись для каждого устройства, скопируйте как Onboard-NonPersistentMachine.ps1, так и deviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="dca62-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dca62-129">Если папку не видно, она может `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` быть скрыта.</span><span class="sxs-lookup"><span data-stu-id="dca62-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="dca62-130">Вам потребуется выбрать параметр Показать скрытые файлы **и папки** из File Explorer.</span><span class="sxs-lookup"><span data-stu-id="dca62-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

8. <span data-ttu-id="dca62-131">Откройте окно редактора локальной групповой политики и перейдите к запуску  >  **Windows Параметры**  >    >  **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="dca62-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dca62-132">Политика группы домена также может использоваться для использования на бортовых устройствах СДВ.</span><span class="sxs-lookup"><span data-stu-id="dca62-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

9. <span data-ttu-id="dca62-133">В зависимости от метода, который вы хотите реализовать, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="dca62-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="dca62-134">**Для одной записи для каждого устройства**</span><span class="sxs-lookup"><span data-stu-id="dca62-134">**For single entry for each device**</span></span>

   <span data-ttu-id="dca62-135">Выберите **вкладку PowerShell Scripts,** а затем нажмите кнопку **Добавить** (Windows Explorer откроется непосредственно в пути, на котором вы скопировали сценарий для вкладки ранее).</span><span class="sxs-lookup"><span data-stu-id="dca62-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="dca62-136">Перейдите к сценарию onboarding `Onboard-NonPersistentMachine.ps1` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dca62-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>

   <span data-ttu-id="dca62-137">**Для нескольких записей для каждого устройства:**</span><span class="sxs-lookup"><span data-stu-id="dca62-137">**For multiple entries for each device**:</span></span>

   <span data-ttu-id="dca62-138">Выберите **вкладку Scripts,** а затем нажмите кнопку **Добавить** (Windows Explorer откроется непосредственно в пути, где вы скопировали сценарий на борту ранее).</span><span class="sxs-lookup"><span data-stu-id="dca62-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="dca62-139">Перейдите к сценарию висят `DeviceComplianceOnboardingScript.cmd` баш.</span><span class="sxs-lookup"><span data-stu-id="dca62-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

10. <span data-ttu-id="dca62-140">Проверьте свое решение:</span><span class="sxs-lookup"><span data-stu-id="dca62-140">Test your solution:</span></span>
    1. <span data-ttu-id="dca62-141">Создайте пул с одним устройством.</span><span class="sxs-lookup"><span data-stu-id="dca62-141">Create a pool with one device.</span></span>
    1. <span data-ttu-id="dca62-142">Logon to device.</span><span class="sxs-lookup"><span data-stu-id="dca62-142">Logon to device.</span></span>
    1. <span data-ttu-id="dca62-143">Вход с устройства.</span><span class="sxs-lookup"><span data-stu-id="dca62-143">Logoff from device.</span></span>
    1. <span data-ttu-id="dca62-144">Logon для устройства с другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="dca62-144">Logon to device with another user.</span></span>
    1. <span data-ttu-id="dca62-145">**Для одной записи для каждого устройства:** проверьте только одну запись в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="dca62-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span>
       <span data-ttu-id="dca62-146">**Для нескольких записей для каждого устройства:** Проверьте несколько записей в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="dca62-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

11. <span data-ttu-id="dca62-147">Щелкните **список Устройств** на области навигации.</span><span class="sxs-lookup"><span data-stu-id="dca62-147">Click **Devices list** on the Navigation pane.</span></span>

12. <span data-ttu-id="dca62-148">Используйте функцию поиска, введите имя устройства и выберите **Устройство** в качестве типа поиска.</span><span class="sxs-lookup"><span data-stu-id="dca62-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="dca62-149">Обновление нестандартных изображений виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="dca62-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>

<span data-ttu-id="dca62-150">В качестве наилучшей практики рекомендуется использовать средства автономного обслуживания для исправления золотых и мастер-изображений.</span><span class="sxs-lookup"><span data-stu-id="dca62-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span>

<span data-ttu-id="dca62-151">Например, вы можете использовать ниже команд для установки обновления, пока изображение остается в автономном режиме:</span><span class="sxs-lookup"><span data-stu-id="dca62-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="dca62-152">Дополнительные сведения о командах DISM и автономном обслуживании см. в статьях ниже:</span><span class="sxs-lookup"><span data-stu-id="dca62-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>

- [<span data-ttu-id="dca62-153">Изменение Windows с помощью DISM</span><span class="sxs-lookup"><span data-stu-id="dca62-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="dca62-154">Параметры управления изображениями DISM Command-Line</span><span class="sxs-lookup"><span data-stu-id="dca62-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="dca62-155">Уменьшение размера магазина компонентов в автономном Windows изображении</span><span class="sxs-lookup"><span data-stu-id="dca62-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="dca62-156">Если автономное обслуживание не является жизнеспособным вариантом для среды нестойких VDI, необходимо предпринять следующие действия для обеспечения согласованности и безопасности датчиков:</span><span class="sxs-lookup"><span data-stu-id="dca62-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="dca62-157">После загрузки мастер-изображения для онлайн-обслуживания или исправления запустите сценарий offboarding, чтобы отключить датчик предотвращения потери Microsoft 365 конечных точек.</span><span class="sxs-lookup"><span data-stu-id="dca62-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="dca62-158">Дополнительные сведения см. в [таблице Offboard devices с помощью локального скрипта.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="dca62-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="dca62-159">Убедитесь, что датчик остановлен, запуская команду ниже в окне CMD:</span><span class="sxs-lookup"><span data-stu-id="dca62-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="dca62-160">Обслуживание изображения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="dca62-160">Service the image as needed.</span></span>

4. <span data-ttu-id="dca62-161">Запустите ниже команд с помощью PsExec.exe (которые можно скачать для очистки содержимого кибер-папки, которые датчик, возможно, https://download.sysinternals.com/files/PSTools.zip) накопил после загрузки:</span><span class="sxs-lookup"><span data-stu-id="dca62-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="dca62-162">Повторно запечатыть золотое/мастер-изображение, как обычно.</span><span class="sxs-lookup"><span data-stu-id="dca62-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dca62-163">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="dca62-163">Related topics</span></span>

- [<span data-ttu-id="dca62-164">Onboard Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="dca62-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="dca62-165">На борту Windows 10 устройства с Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dca62-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="dca62-166">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="dca62-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="dca62-167">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="dca62-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="dca62-168">Устранение неполадок с бортовой защитой расширенных угроз Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dca62-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
