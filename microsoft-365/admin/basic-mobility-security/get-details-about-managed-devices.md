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
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228175"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="a469f-103">Сведения об управляемых устройствах Basic Mobility и Security</span><span class="sxs-lookup"><span data-stu-id="a469f-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="a469f-104">В этой статье показано, как использовать Windows PowerShell для получения сведений о устройствах в организации, которые настроены для базовой мобильности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="a469f-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="a469f-105">Вот разбивка сведений о устройстве, доступных для вас.</span><span class="sxs-lookup"><span data-stu-id="a469f-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="a469f-106">**Detail**</span><span class="sxs-lookup"><span data-stu-id="a469f-106">**Detail**</span></span>|<span data-ttu-id="a469f-107">**Что нужно искать в PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a469f-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="a469f-108">Устройство зачислилось в Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="a469f-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="a469f-109">Дополнительные сведения см. в [записи мобильного устройства с помощью Basic Mobility and Security](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="a469f-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="a469f-110">Значение *параметра isManaged:*  </span><span class="sxs-lookup"><span data-stu-id="a469f-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="a469f-111">**True**= устройство зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="a469f-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="a469f-112">**False**= устройство не зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="a469f-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="a469f-113">Устройство соответствует политикам безопасности устройств.</span><span class="sxs-lookup"><span data-stu-id="a469f-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="a469f-114">Дополнительные сведения см. в [дополнительных сведениях о создании политик безопасности устройств](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a469f-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="a469f-115">Значение *параметра isCompliant:*  </span><span class="sxs-lookup"><span data-stu-id="a469f-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="a469f-116">**True**   = устройство соответствует политикам.</span><span class="sxs-lookup"><span data-stu-id="a469f-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="a469f-117">**False**   = устройство не соответствует политикам.</span><span class="sxs-lookup"><span data-stu-id="a469f-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Параметры Basic Mobility и Security PowerShell":::

> [!NOTE]
> <span data-ttu-id="a469f-119">Команды и скрипты в этой статье также возвращают сведения о любых устройствах, управляемых [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="a469f-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a469f-120">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="a469f-120">Before you begin</span></span>

<span data-ttu-id="a469f-121">Для запуска команд и сценариев, описанных в этой статье, необходимо настроить несколько вещей.</span><span class="sxs-lookup"><span data-stu-id="a469f-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a469f-122">Шаг 1. Скачайте и установите модуль Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a469f-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a469f-123">Дополнительные сведения об этих действиях см. в [Подключение Microsoft 365 PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="a469f-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="a469f-124">Перейдите Microsoft Online Services Sign-In помощника для [ИТ-специалистов RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)и выберите Скачать для Microsoft Online Services помощника по    **входу**.</span><span class="sxs-lookup"><span data-stu-id="a469f-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="a469f-125">Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="a469f-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="a469f-126">Откройте командную строку для уровня администратора PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a469f-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="a469f-127">Выполните команду `Install-Module MSOnline`.</span><span class="sxs-lookup"><span data-stu-id="a469f-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="a469f-128">Если отобразится запрос на установку поставщика NuGet, введите Y и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a469f-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="a469f-129">Если отобразится запрос на установку модуля из репозитория PSGallery, введите Y и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a469f-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="a469f-130">После установки закройте командное окно PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a469f-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="a469f-131">Шаг 2. Подключение подписку на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a469f-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="a469f-132">В модуле Windows Azure Active Directory для Windows PowerShell запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a469f-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="a469f-133">В диалоговом окне Windows PowerShell запроса учетных данных введите имя пользователя и пароль для глобальной Microsoft 365 учетной записи администратора, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a469f-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="a469f-134">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a469f-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="a469f-135">Шаг 3. Убедитесь, что вы можете запускать скрипты PowerShell</span><span class="sxs-lookup"><span data-stu-id="a469f-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="a469f-136">Этот шаг можно пропустить, если вы уже настроены для запуска сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a469f-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="a469f-137">Чтобы запустить Get-MsolUserDeviceComplianceStatus.ps1, необходимо включить запуск скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a469f-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="a469f-138">Из рабочего Windows выберите **Начните,** а затем введите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a469f-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="a469f-139">Щелкните правой кнопкой мыши Windows PowerShell, а затем выберите **Выполнить в качестве администратора.**</span><span class="sxs-lookup"><span data-stu-id="a469f-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="a469f-140">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a469f-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="a469f-141">При запросе введите Y и нажмите кнопку Ввод.</span><span class="sxs-lookup"><span data-stu-id="a469f-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="a469f-142">Запустите Get-MsolDevice для отображения сведений для всех устройств в организации</span><span class="sxs-lookup"><span data-stu-id="a469f-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="a469f-143">Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a469f-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="a469f-144">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a469f-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="a469f-145">Дополнительные примеры см.  [в примере Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span><span class="sxs-lookup"><span data-stu-id="a469f-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="a469f-146">Запустите скрипт, чтобы получить сведения об устройстве</span><span class="sxs-lookup"><span data-stu-id="a469f-146">Run a script to get device details</span></span>

<span data-ttu-id="a469f-147">Сначала сохраните скрипт на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a469f-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="a469f-148">Скопируйте и вклеите следующий текст в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="a469f-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="a469f-149">Сохраните его как файл Windows PowerShell с помощью расширения файла .ps1; например, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="a469f-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="a469f-150">Запустите скрипт, чтобы получить сведения об устройстве для одной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="a469f-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="a469f-151">Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a469f-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="a469f-152">Перейдите к папке, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="a469f-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="a469f-153">Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a469f-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="a469f-154">Запустите следующую команду, чтобы определить пользователя, для получения сведений о устройстве.</span><span class="sxs-lookup"><span data-stu-id="a469f-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="a469f-155">В этом примере вы также bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="a469f-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="a469f-156">Запустите следующую команду, чтобы инициировать сценарий.</span><span class="sxs-lookup"><span data-stu-id="a469f-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="a469f-157">Эти сведения экспортируются на Windows desktop в качестве CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="a469f-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="a469f-158">Для указания имени файла и пути CSV можно использовать дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="a469f-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="a469f-159">Запустите скрипт, чтобы получить сведения об устройстве для группы пользователей</span><span class="sxs-lookup"><span data-stu-id="a469f-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="a469f-160">Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a469f-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="a469f-161">Перейдите к папке, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="a469f-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="a469f-162">Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a469f-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="a469f-163">Запустите следующую команду, чтобы определить группу, для получения сведений о устройстве.</span><span class="sxs-lookup"><span data-stu-id="a469f-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="a469f-164">В этом примере получаются сведения для пользователей из группы FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="a469f-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="a469f-165">Запустите следующую команду, чтобы инициировать сценарий.</span><span class="sxs-lookup"><span data-stu-id="a469f-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="a469f-166">Эти сведения экспортируются на Windows desktop в качестве CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="a469f-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="a469f-167">Для указания имени файла и пути CSV можно использовать дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="a469f-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a469f-168">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="a469f-168">Related topics</span></span>

[<span data-ttu-id="a469f-169">Microsoft Подключение была снята с службы</span><span class="sxs-lookup"><span data-stu-id="a469f-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="a469f-170">Обзор Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="a469f-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="a469f-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="a469f-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
