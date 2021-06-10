---
title: Сведения об управляемых устройствах Basic Mobility и Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Используйте Windows PowerShell, чтобы получить сведения о устройствах basic Mobility и Security в организации.
ms.openlocfilehash: 7cb2369c9a31210f26db12b0453e7a4228e1cccc
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782445"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="3f44e-103">Сведения об управляемых устройствах Basic Mobility и Security</span><span class="sxs-lookup"><span data-stu-id="3f44e-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="3f44e-104">В этой статье показано, как использовать Windows PowerShell для получения сведений о устройствах в организации, которые настроены для базовой мобильности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="3f44e-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="3f44e-105">Вот разбивка сведений о устройстве, доступных для вас.</span><span class="sxs-lookup"><span data-stu-id="3f44e-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="3f44e-106">**Detail**</span><span class="sxs-lookup"><span data-stu-id="3f44e-106">**Detail**</span></span>|<span data-ttu-id="3f44e-107">**Что нужно искать в PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3f44e-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="3f44e-108">Устройство зачислилось в Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="3f44e-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="3f44e-109">Дополнительные сведения см. в [записи мобильного устройства с помощью Basic Mobility and Security](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="3f44e-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="3f44e-110">Значение *параметра isManaged:*  </span><span class="sxs-lookup"><span data-stu-id="3f44e-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="3f44e-111">**True**= устройство зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="3f44e-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="3f44e-112">**False**= устройство не зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="3f44e-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="3f44e-113">Устройство соответствует политикам безопасности устройств.</span><span class="sxs-lookup"><span data-stu-id="3f44e-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="3f44e-114">Дополнительные сведения см. в [дополнительных сведениях о создании политик безопасности устройств](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3f44e-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="3f44e-115">Значение *параметра isCompliant:*  </span><span class="sxs-lookup"><span data-stu-id="3f44e-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="3f44e-116">**True**   = устройство соответствует политикам.</span><span class="sxs-lookup"><span data-stu-id="3f44e-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="3f44e-117">**False**   = устройство не соответствует политикам.</span><span class="sxs-lookup"><span data-stu-id="3f44e-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Параметры Basic Mobility и Security PowerShell":::

>[!NOTE]
><span data-ttu-id="3f44e-119">Команды и скрипты в этой статье также возвращают сведения о любых устройствах, управляемых [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="3f44e-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3f44e-120">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="3f44e-120">Before you begin</span></span>

<span data-ttu-id="3f44e-121">Для запуска команд и сценариев, описанных в этой статье, необходимо настроить несколько вещей.</span><span class="sxs-lookup"><span data-stu-id="3f44e-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3f44e-122">Шаг 1. Скачайте и установите модуль Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f44e-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="3f44e-123">Дополнительные сведения об этих действиях см. в [Подключение Microsoft 365 PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="3f44e-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="3f44e-124">Перейдите Microsoft Online Services Sign-In помощника для [ИТ-специалистов RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)и выберите Скачать для Microsoft Online Services помощника по    **входу**.</span><span class="sxs-lookup"><span data-stu-id="3f44e-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="3f44e-125">Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3f44e-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="3f44e-126">Откройте командную строку для уровня администратора PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f44e-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="3f44e-127">Выполните команду Install-Module MSOnline.</span><span class="sxs-lookup"><span data-stu-id="3f44e-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="3f44e-128">Если отобразится запрос на установку поставщика NuGet, введите Y и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="3f44e-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="3f44e-129">Если отобразится запрос на установку модуля из репозитория PSGallery, введите Y и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="3f44e-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="3f44e-130">После установки закройте командное окно PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f44e-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="3f44e-131">Шаг 2. Подключение подписку на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f44e-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="3f44e-132">В модуле Windows Azure Active Directory для Windows PowerShell запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3f44e-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="3f44e-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="3f44e-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="3f44e-134">В диалоговом окне Windows PowerShell запроса учетных данных введите имя пользователя и пароль для глобальной Microsoft 365 учетной записи администратора, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3f44e-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="3f44e-135">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3f44e-135">Run the following command.</span></span>

    <span data-ttu-id="3f44e-136">Connect-MsolService -Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="3f44e-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="3f44e-137">Шаг 3. Убедитесь, что вы можете запускать скрипты PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f44e-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="3f44e-138">Этот шаг можно пропустить, если вы уже настроены для запуска сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f44e-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="3f44e-139">Чтобы запустить Get-MsolUserDeviceComplianceStatus.ps1, необходимо включить запуск скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f44e-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="3f44e-140">Из рабочего Windows выберите **Начните,** а затем введите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f44e-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="3f44e-141">Щелкните правой кнопкой мыши Windows PowerShell, а затем выберите **Выполнить в качестве администратора.**</span><span class="sxs-lookup"><span data-stu-id="3f44e-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="3f44e-142">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3f44e-142">Run the following command.</span></span>

    <span data-ttu-id="3f44e-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="3f44e-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="3f44e-144">При запросе введите Y и нажмите кнопку Ввод.</span><span class="sxs-lookup"><span data-stu-id="3f44e-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="3f44e-145">**Запустите Get-MsolDevice для отображения сведений для всех устройств в организации**</span><span class="sxs-lookup"><span data-stu-id="3f44e-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="3f44e-146">Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f44e-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="3f44e-147">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3f44e-147">Run the following command.</span></span>

    <span data-ttu-id="3f44e-148">Get-MsolDevice -All-ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}</span><span class="sxs-lookup"><span data-stu-id="3f44e-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="3f44e-149">Дополнительные примеры см.  [в примере Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span><span class="sxs-lookup"><span data-stu-id="3f44e-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="3f44e-150">Запустите скрипт, чтобы получить сведения об устройстве</span><span class="sxs-lookup"><span data-stu-id="3f44e-150">Run a script to get device details</span></span>

<span data-ttu-id="3f44e-151">Сначала сохраните скрипт на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3f44e-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="3f44e-152">Скопируйте и вклеите следующий текст в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="3f44e-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="3f44e-153">param (</span><span class="sxs-lookup"><span data-stu-id="3f44e-153">param (</span></span>

3.  <span data-ttu-id="3f44e-154">[PSObject[]$users = @(),</span><span class="sxs-lookup"><span data-stu-id="3f44e-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="3f44e-155">[Switch]$export,</span><span class="sxs-lookup"><span data-stu-id="3f44e-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="3f44e-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span><span class="sxs-lookup"><span data-stu-id="3f44e-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="3f44e-157">[String]$exportPath = [Окружающая среда]::GetFolderPath ("Настольный компьютер")</span><span class="sxs-lookup"><span data-stu-id="3f44e-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="3f44e-158">)</span><span class="sxs-lookup"><span data-stu-id="3f44e-158">)</span></span>

9.  <span data-ttu-id="3f44e-159">[System.Collections.IDictionary]$script:схемы = @{</span><span class="sxs-lookup"><span data-stu-id="3f44e-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="3f44e-160">DeviceId = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="3f44e-161">DeviceOSType = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="3f44e-162">DeviceOSVersion = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="3f44e-163">DeviceTrustLevel = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="3f44e-164">DisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="3f44e-165">IsCompliant = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="3f44e-166">IsManaged = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="3f44e-167">ApproximateLastLogonTimestamp = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="3f44e-168">DeviceObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="3f44e-169">RegisteredOwnerUpn = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="3f44e-170">RegisteredOwnerObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="3f44e-171">RegisteredOwnerDisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="3f44e-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="3f44e-172">}</span><span class="sxs-lookup"><span data-stu-id="3f44e-172">}</span></span>
    

25.  <span data-ttu-id="3f44e-173">функция createResultObject</span><span class="sxs-lookup"><span data-stu-id="3f44e-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="3f44e-174">{</span><span class="sxs-lookup"><span data-stu-id="3f44e-174">{</span></span>
    

28.  <span data-ttu-id="3f44e-175">[PSObject]$resultObject = New-Object-TypeName PSObject-Property $script:schema</span><span class="sxs-lookup"><span data-stu-id="3f44e-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="3f44e-176">возвращение $resultObject</span><span class="sxs-lookup"><span data-stu-id="3f44e-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="3f44e-177">}</span><span class="sxs-lookup"><span data-stu-id="3f44e-177">}</span></span>
    

33.  <span data-ttu-id="3f44e-178">Если ($users. Count -eq 0)</span><span class="sxs-lookup"><span data-stu-id="3f44e-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="3f44e-179">{</span><span class="sxs-lookup"><span data-stu-id="3f44e-179">{</span></span>
    

35.  <span data-ttu-id="3f44e-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="3f44e-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="3f44e-181">}</span><span class="sxs-lookup"><span data-stu-id="3f44e-181">}</span></span>
    

38.  <span data-ttu-id="3f44e-182">[PSObject[]] $result = foreach ($u в $users)</span><span class="sxs-lookup"><span data-stu-id="3f44e-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="3f44e-183">{</span><span class="sxs-lookup"><span data-stu-id="3f44e-183">{</span></span>
    

41.  <span data-ttu-id="3f44e-184">[PSObject]$devices = get-msoldevice-RegisteredOwnerUpn $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="3f44e-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="3f44e-185">foreach ($d в $devices)</span><span class="sxs-lookup"><span data-stu-id="3f44e-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="3f44e-186">{</span><span class="sxs-lookup"><span data-stu-id="3f44e-186">{</span></span>
    

44.  <span data-ttu-id="3f44e-187">[PSObject]$deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="3f44e-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="3f44e-188">$deviceResult.DeviceId = $d.DeviceId</span><span class="sxs-lookup"><span data-stu-id="3f44e-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="3f44e-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="3f44e-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="3f44e-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="3f44e-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="3f44e-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="3f44e-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="3f44e-192">$deviceResult.DisplayName = $d.DisplayName</span><span class="sxs-lookup"><span data-stu-id="3f44e-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="3f44e-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span><span class="sxs-lookup"><span data-stu-id="3f44e-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="3f44e-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span><span class="sxs-lookup"><span data-stu-id="3f44e-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="3f44e-195">$deviceResult.DeviceObjectId = $d.ObjectId</span><span class="sxs-lookup"><span data-stu-id="3f44e-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="3f44e-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="3f44e-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="3f44e-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span><span class="sxs-lookup"><span data-stu-id="3f44e-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="3f44e-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span><span class="sxs-lookup"><span data-stu-id="3f44e-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="3f44e-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="3f44e-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="3f44e-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="3f44e-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="3f44e-201">}</span><span class="sxs-lookup"><span data-stu-id="3f44e-201">}</span></span>
    

61.  <span data-ttu-id="3f44e-202">}</span><span class="sxs-lookup"><span data-stu-id="3f44e-202">}</span></span>
    

63.  <span data-ttu-id="3f44e-203">Если ($export)</span><span class="sxs-lookup"><span data-stu-id="3f44e-203">If ($export)</span></span>
    

64.  <span data-ttu-id="3f44e-204">{</span><span class="sxs-lookup"><span data-stu-id="3f44e-204">{</span></span>
    

65.  <span data-ttu-id="3f44e-205">$result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="3f44e-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="3f44e-206">}</span><span class="sxs-lookup"><span data-stu-id="3f44e-206">}</span></span>
    

67.  <span data-ttu-id="3f44e-207">Else</span><span class="sxs-lookup"><span data-stu-id="3f44e-207">Else</span></span>
    

68.  <span data-ttu-id="3f44e-208">{</span><span class="sxs-lookup"><span data-stu-id="3f44e-208">{</span></span>
    

69.  <span data-ttu-id="3f44e-209">$result</span><span class="sxs-lookup"><span data-stu-id="3f44e-209">$result</span></span>
    

70.  <span data-ttu-id="3f44e-210">}</span><span class="sxs-lookup"><span data-stu-id="3f44e-210">}</span></span>
    

71.  <span data-ttu-id="3f44e-211">Сохраните его как файл Windows PowerShell с помощью расширения файла .ps1; например, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="3f44e-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="3f44e-212">Запустите скрипт, чтобы получить сведения об устройстве для одной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="3f44e-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="3f44e-213">Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f44e-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="3f44e-214">Перейдите к папке, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="3f44e-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="3f44e-215">Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3f44e-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="3f44e-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="3f44e-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="3f44e-217">Запустите следующую команду, чтобы определить пользователя, для получения сведений о устройстве.</span><span class="sxs-lookup"><span data-stu-id="3f44e-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="3f44e-218">В этом примере вы также bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="3f44e-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="3f44e-219">$u = Get-MsolUser-UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="3f44e-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="3f44e-220">Запустите следующую команду, чтобы инициировать сценарий.</span><span class="sxs-lookup"><span data-stu-id="3f44e-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="3f44e-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="3f44e-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="3f44e-222">Эти сведения экспортируются на Windows desktop в качестве CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="3f44e-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="3f44e-223">Для указания имени файла и пути CSV можно использовать дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="3f44e-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="3f44e-224">Запустите скрипт, чтобы получить сведения об устройстве для группы пользователей</span><span class="sxs-lookup"><span data-stu-id="3f44e-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="3f44e-225">Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f44e-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="3f44e-226">Перейдите к папке, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="3f44e-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="3f44e-227">Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3f44e-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="3f44e-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="3f44e-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="3f44e-229">Запустите следующую команду, чтобы определить группу, для получения сведений о устройстве.</span><span class="sxs-lookup"><span data-stu-id="3f44e-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="3f44e-230">В этом примере получаются сведения для пользователей из группы FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="3f44e-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="3f44e-231">$u = Get-MsolGroupMember-SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }</span><span class="sxs-lookup"><span data-stu-id="3f44e-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="3f44e-232">Запустите следующую команду, чтобы инициировать сценарий.</span><span class="sxs-lookup"><span data-stu-id="3f44e-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="3f44e-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="3f44e-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="3f44e-234">Эти сведения экспортируются на Windows desktop в качестве CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="3f44e-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="3f44e-235">Для указания имени файла и пути CSV можно использовать дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="3f44e-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3f44e-236">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3f44e-236">Related topics</span></span>

[<span data-ttu-id="3f44e-237">Microsoft Подключение была снята с службы</span><span class="sxs-lookup"><span data-stu-id="3f44e-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="3f44e-238">Обзор Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="3f44e-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="3f44e-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="3f44e-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)