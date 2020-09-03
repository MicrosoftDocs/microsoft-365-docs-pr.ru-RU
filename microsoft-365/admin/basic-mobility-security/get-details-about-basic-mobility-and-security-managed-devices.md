---
title: Получение сведений об основных управляемых устройствах для мобильных устройств и безопасности
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
description: Используйте Windows PowerShell для получения сведений об основных устройствах для мобильных устройств и безопасности в Организации.
ms.openlocfilehash: 7b041e54d512291163616d3b61973cef989cec5c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337041"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="900e7-103">Получение сведений об основных управляемых устройствах для мобильных устройств и безопасности</span><span class="sxs-lookup"><span data-stu-id="900e7-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="900e7-104">В этой статье показано, как использовать Windows PowerShell для получения сведений об устройствах в Организации, которые вы настроили для обеспечения базовой мобильной работы и безопасности.</span><span class="sxs-lookup"><span data-stu-id="900e7-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="900e7-105">Ниже приведена подразделение сведений об устройствах, доступных вам.</span><span class="sxs-lookup"><span data-stu-id="900e7-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="900e7-106">**Detail**</span><span class="sxs-lookup"><span data-stu-id="900e7-106">**Detail**</span></span>|<span data-ttu-id="900e7-107">**Что искать в PowerShell**</span><span class="sxs-lookup"><span data-stu-id="900e7-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="900e7-108">Устройство регистрируется в базовой мобильной связи и безопасности.</span><span class="sxs-lookup"><span data-stu-id="900e7-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="900e7-109">Дополнительные сведения см. в статье [Регистрация мобильного устройства с помощью базовой мобильной работы и безопасности](enroll-your-mobile-device-using-basic-mobility-and-security.md)</span><span class="sxs-lookup"><span data-stu-id="900e7-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md)</span></span>|<span data-ttu-id="900e7-110">Параметр "для *управления*"   имеет следующий тип:</span><span class="sxs-lookup"><span data-stu-id="900e7-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="900e7-111">**True**= устройство зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="900e7-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="900e7-112">**False**= устройство не зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="900e7-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="900e7-113">Устройство соответствует политикам безопасности устройств.</span><span class="sxs-lookup"><span data-stu-id="900e7-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="900e7-114">Дополнительные сведения см в разделе [Создание политик безопасности устройств](create-device-security-policies-in-basic-mmobility-and-security.md)</span><span class="sxs-lookup"><span data-stu-id="900e7-114">For more info, see [Create device security policies](create-device-security-policies-in-basic-mmobility-and-security.md)</span></span>|<span data-ttu-id="900e7-115">Значение параметра "параметром" *соответствует*   :</span><span class="sxs-lookup"><span data-stu-id="900e7-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="900e7-116">**Значение true**   = устройство соответствует политикам.</span><span class="sxs-lookup"><span data-stu-id="900e7-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="900e7-117">**False (ложь**   ) = устройство несовместимо с политиками.</span><span class="sxs-lookup"><span data-stu-id="900e7-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Основные параметры PowerShell для обеспечения мобильности и безопасности":::

>[!NOTE]
><span data-ttu-id="900e7-119">Команды и сценарии также возвращают сведения обо всех устройствах под управлением [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="900e7-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="900e7-120">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="900e7-120">Before you begin</span></span>

<span data-ttu-id="900e7-121">Для выполнения команд и сценариев, описанных в этой статье, необходимо настроить несколько моментов.</span><span class="sxs-lookup"><span data-stu-id="900e7-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="900e7-122">Шаг 1: Скачайте и установите модуль Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="900e7-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="900e7-123">Для получения дополнительных сведений об этих действиях обратитесь к разделу [Подключение к Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="900e7-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="900e7-124">Перейдите на страницу [Помощник по входу в Microsoft Online Services для ИТ-специалистов ртвл](https://www.microsoft.com/download/details.aspx?id=41950)   и выберите пункт  **Загрузка для помощника по входу в Microsoft Online Services**.</span><span class="sxs-lookup"><span data-stu-id="900e7-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="900e7-125">Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="900e7-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>   

    1. <span data-ttu-id="900e7-126">Откройте командную строку для уровня администратора PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900e7-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="900e7-127">Выполните команду Install-Module MSOnline.</span><span class="sxs-lookup"><span data-stu-id="900e7-127">Run the Install-Module MSOnline command.</span></span>
    
    3. <span data-ttu-id="900e7-128">Если отобразится запрос на установку поставщика NuGet, введите Y и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="900e7-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>   

    4. <span data-ttu-id="900e7-129">Если отобразится запрос на установку модуля из репозитория PSGallery, введите Y и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="900e7-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>   

    5. <span data-ttu-id="900e7-130">После установки закройте командное окно PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900e7-130">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="900e7-131">Шаг 2: подключение к вашей подписке на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="900e7-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="900e7-132">В модуле Windows Azure Active Directory для Windows PowerShell выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="900e7-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="900e7-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="900e7-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="900e7-134">В диалоговом окне Запрос учетных данных Windows PowerShell введите имя пользователя и пароль для учетной записи глобального администратора Microsoft 365, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="900e7-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>
    
3. <span data-ttu-id="900e7-135">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="900e7-135">Run the following command.</span></span>
    
    <span data-ttu-id="900e7-136">Connect — MsolService — $UserCredential учетных данных</span><span class="sxs-lookup"><span data-stu-id="900e7-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="900e7-137">Шаг 3: Убедитесь, что вы можете запускать сценарии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900e7-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="900e7-138">Вы можете пропустить этот шаг, если вы уже настроили выполнение сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900e7-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="900e7-139">Чтобы запустить скрипт Get-MsolUserDeviceComplianceStatus.ps1, необходимо включить выполнение сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900e7-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="900e7-140">На рабочем столе Windows нажмите кнопку **Пуск**и введите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900e7-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="900e7-141">Щелкните правой кнопкой мыши Windows PowerShell, а затем выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="900e7-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="900e7-142">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="900e7-142">Run the following command.</span></span>
    
    <span data-ttu-id="900e7-143">Set — ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="900e7-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="900e7-144">При появлении соответствующего запроса введите Y и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="900e7-144">When prompted, type Y and then press Enter.</span></span>
    
<span data-ttu-id="900e7-145">**Выполните командлет Get – Мсолдевице, чтобы отобразить сведения для всех устройств в Организации.**</span><span class="sxs-lookup"><span data-stu-id="900e7-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="900e7-146">Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900e7-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="900e7-147">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="900e7-147">Run the following command.</span></span>
    
    <span data-ttu-id="900e7-148">Get – Мсолдевице — ALL – Ретурнрегистередовнерс | Where – Object {$ _. RegisteredOwners. Count — gt 0}</span><span class="sxs-lookup"><span data-stu-id="900e7-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="900e7-149">Дополнительные примеры приведены в статье  [Get – мсолдевице](https://go.microsoft.com/fwlink/?linkid=841721).</span><span class="sxs-lookup"><span data-stu-id="900e7-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="900e7-150">Запуск скрипта для получения сведений об устройстве</span><span class="sxs-lookup"><span data-stu-id="900e7-150">Run a script to get device details</span></span>

<span data-ttu-id="900e7-151">Сначала сохраните сценарий на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="900e7-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="900e7-152">Скопируйте и вставьте приведенный ниже текст в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="900e7-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="900e7-153">Param</span><span class="sxs-lookup"><span data-stu-id="900e7-153">param (</span></span>
    

3.  <span data-ttu-id="900e7-154">[PSObject []] $users = @ (),</span><span class="sxs-lookup"><span data-stu-id="900e7-154">[PSObject[]]$users = @(),</span></span>
    

4.  <span data-ttu-id="900e7-155">[Переключатель] $export,</span><span class="sxs-lookup"><span data-stu-id="900e7-155">[Switch]$export,</span></span>
    

5.  <span data-ttu-id="900e7-156">[Строка] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-format "yyMMdd_HHMMss") + ". csv",</span><span class="sxs-lookup"><span data-stu-id="900e7-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>
    

6.  <span data-ttu-id="900e7-157">[Строка] $exportPath = [среда]:: Жетфолдерпас ("Рабочий стол")</span><span class="sxs-lookup"><span data-stu-id="900e7-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>
    

7.  <span data-ttu-id="900e7-158">)</span><span class="sxs-lookup"><span data-stu-id="900e7-158">)</span></span>
    

9.  <span data-ttu-id="900e7-159">[System. Collections. IDictionary] $script: schema = @ {</span><span class="sxs-lookup"><span data-stu-id="900e7-159">[System.Collections.IDictionary]$script:schema = @{</span></span>
    

11.  <span data-ttu-id="900e7-160">DeviceId = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-160">DeviceId = ''</span></span>
    

12.  <span data-ttu-id="900e7-161">Девицеостипе = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-161">DeviceOSType = ''</span></span>
    

13.  <span data-ttu-id="900e7-162">Девицеосверсион = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-162">DeviceOSVersion = ''</span></span>
    

14.  <span data-ttu-id="900e7-163">Девицетрустлевел = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-163">DeviceTrustLevel = ''</span></span>
    

15.  <span data-ttu-id="900e7-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-164">DisplayName = ''</span></span>
    

16.  <span data-ttu-id="900e7-165">Является совместимым = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-165">IsCompliant = ''</span></span>
    

17.  <span data-ttu-id="900e7-166">Managed = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-166">IsManaged = ''</span></span>
    

18.  <span data-ttu-id="900e7-167">Аппроксимателастлогонтиместамп = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-167">ApproximateLastLogonTimestamp = ''</span></span>
    

19.  <span data-ttu-id="900e7-168">Девицеобжектид = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-168">DeviceObjectId = ''</span></span>
    

20.  <span data-ttu-id="900e7-169">Регистередовнерупн = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-169">RegisteredOwnerUpn = ''</span></span>
    

21.  <span data-ttu-id="900e7-170">Регистередовнеробжектид = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="900e7-171">Регистередовнердисплайнаме = ' '</span><span class="sxs-lookup"><span data-stu-id="900e7-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="900e7-172">}</span><span class="sxs-lookup"><span data-stu-id="900e7-172">}</span></span>
    

25.  <span data-ttu-id="900e7-173">Функция Креатересултобжект</span><span class="sxs-lookup"><span data-stu-id="900e7-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="900e7-174">{</span><span class="sxs-lookup"><span data-stu-id="900e7-174">{</span></span>
    

28.  <span data-ttu-id="900e7-175">[PSObject] $resultObject = New – Object: TypeName PSObject — Property $script: schema</span><span class="sxs-lookup"><span data-stu-id="900e7-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="900e7-176">Возврат $resultObject</span><span class="sxs-lookup"><span data-stu-id="900e7-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="900e7-177">}</span><span class="sxs-lookup"><span data-stu-id="900e7-177">}</span></span>
    

33.  <span data-ttu-id="900e7-178">Если ($users. Count-EQ 0)</span><span class="sxs-lookup"><span data-stu-id="900e7-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="900e7-179">{</span><span class="sxs-lookup"><span data-stu-id="900e7-179">{</span></span>
    

35.  <span data-ttu-id="900e7-180">$users = Get MsolUser</span><span class="sxs-lookup"><span data-stu-id="900e7-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="900e7-181">}</span><span class="sxs-lookup"><span data-stu-id="900e7-181">}</span></span>
    

38.  <span data-ttu-id="900e7-182">[PSObject []] $result = foreach ($u в $users)</span><span class="sxs-lookup"><span data-stu-id="900e7-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="900e7-183">{</span><span class="sxs-lookup"><span data-stu-id="900e7-183">{</span></span>
    

41.  <span data-ttu-id="900e7-184">[PSObject] $devices = Get – мсолдевице — Регистередовнерупн $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="900e7-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="900e7-185">foreach ($d в $devices)</span><span class="sxs-lookup"><span data-stu-id="900e7-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="900e7-186">{</span><span class="sxs-lookup"><span data-stu-id="900e7-186">{</span></span>
    

44.  <span data-ttu-id="900e7-187">[PSObject] $deviceResult = Креатересултобжект</span><span class="sxs-lookup"><span data-stu-id="900e7-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="900e7-188">$deviceResult. DeviceId = $d. DeviceId</span><span class="sxs-lookup"><span data-stu-id="900e7-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="900e7-189">$deviceResult. Девицеостипе = $d. Девицеостипе</span><span class="sxs-lookup"><span data-stu-id="900e7-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="900e7-190">$deviceResult. Девицеосверсион = $d. Девицеосверсион</span><span class="sxs-lookup"><span data-stu-id="900e7-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="900e7-191">$deviceResult. Девицетрустлевел = $d. Девицетрустлевел</span><span class="sxs-lookup"><span data-stu-id="900e7-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="900e7-192">$deviceResult. DisplayName = $d. DisplayName</span><span class="sxs-lookup"><span data-stu-id="900e7-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="900e7-193">$deviceResult. с соответствующим = $d. Графдевицеобжект. ALL</span><span class="sxs-lookup"><span data-stu-id="900e7-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="900e7-194">$deviceResult. Графдевицеобжект. Managed = $d...</span><span class="sxs-lookup"><span data-stu-id="900e7-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="900e7-195">$deviceResult. Девицеобжектид = $d. ObjectId</span><span class="sxs-lookup"><span data-stu-id="900e7-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="900e7-196">$deviceResult. Регистередовнерупн = $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="900e7-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="900e7-197">$deviceResult. Регистередовнеробжектид = $u. ObjectId</span><span class="sxs-lookup"><span data-stu-id="900e7-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="900e7-198">$deviceResult. Регистередовнердисплайнаме = $u. DisplayName</span><span class="sxs-lookup"><span data-stu-id="900e7-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="900e7-199">$deviceResult. Аппроксимателастлогонтиместамп = $d. Аппроксимателастлогонтиместамп</span><span class="sxs-lookup"><span data-stu-id="900e7-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="900e7-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="900e7-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="900e7-201">}</span><span class="sxs-lookup"><span data-stu-id="900e7-201">}</span></span>
    

61.  <span data-ttu-id="900e7-202">}</span><span class="sxs-lookup"><span data-stu-id="900e7-202">}</span></span>
    

63.  <span data-ttu-id="900e7-203">Если ($export)</span><span class="sxs-lookup"><span data-stu-id="900e7-203">If ($export)</span></span>
    

64.  <span data-ttu-id="900e7-204">{</span><span class="sxs-lookup"><span data-stu-id="900e7-204">{</span></span>
    

65.  <span data-ttu-id="900e7-205">$result | Export-CSV-Path ($exportPath + " \" + $exportFileName) — нотипеинформатион</span><span class="sxs-lookup"><span data-stu-id="900e7-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="900e7-206">}</span><span class="sxs-lookup"><span data-stu-id="900e7-206">}</span></span>
    

67.  <span data-ttu-id="900e7-207">Else</span><span class="sxs-lookup"><span data-stu-id="900e7-207">Else</span></span>
    

68.  <span data-ttu-id="900e7-208">{</span><span class="sxs-lookup"><span data-stu-id="900e7-208">{</span></span>
    

69.  <span data-ttu-id="900e7-209">$result</span><span class="sxs-lookup"><span data-stu-id="900e7-209">$result</span></span>
    

70.  <span data-ttu-id="900e7-210">}</span><span class="sxs-lookup"><span data-stu-id="900e7-210">}</span></span>
    

71.  <span data-ttu-id="900e7-211">Сохраните его как файл сценария Windows PowerShell, используя расширение File. ps1; Например, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="900e7-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="900e7-212">Запуск сценария для получения сведений об устройстве для одной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="900e7-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="900e7-213">Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900e7-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="900e7-214">Перейдите к папке, в которой был сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="900e7-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="900e7-215">Например, если вы сохранили его в К:\пс-скриптс, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="900e7-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="900e7-216">CD К:\пс-скриптс</span><span class="sxs-lookup"><span data-stu-id="900e7-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="900e7-217">Выполните следующую команду, чтобы определить пользователя, для которого необходимо получить сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="900e7-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="900e7-218">В этом примере показано получение сведений для bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="900e7-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="900e7-219">$u = Get MsolUser — UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="900e7-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="900e7-220">Выполните следующую команду, чтобы запустить скрипт.</span><span class="sxs-lookup"><span data-stu-id="900e7-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="900e7-221">.\Get-MsolUserDeviceComplianceStatus.ps1 $u экспорта</span><span class="sxs-lookup"><span data-stu-id="900e7-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="900e7-222">Информация экспортируется на Рабочий стол Windows в виде CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="900e7-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="900e7-223">Вы можете использовать дополнительные параметры, чтобы указать имя файла и путь для CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="900e7-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="900e7-224">Запуск скрипта для получения сведений об устройстве для группы пользователей</span><span class="sxs-lookup"><span data-stu-id="900e7-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="900e7-225">Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="900e7-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="900e7-226">Перейдите к папке, в которой был сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="900e7-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="900e7-227">Например, если вы сохранили его в К:\пс-скриптс, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="900e7-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="900e7-228">CD К:\пс-скриптс</span><span class="sxs-lookup"><span data-stu-id="900e7-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="900e7-229">Выполните следующую команду, чтобы определить группу, для которой требуется получить сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="900e7-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="900e7-230">В этом примере показано получение сведений для пользователей в группе Финанцестафф.</span><span class="sxs-lookup"><span data-stu-id="900e7-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="900e7-231">$u = Get – Мсолграупмембер — Сеарчстринг "Финанцестафф" | % {Get – MsolUser – ObjectId $ _. ИД</span><span class="sxs-lookup"><span data-stu-id="900e7-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="900e7-232">Выполните следующую команду, чтобы запустить скрипт.</span><span class="sxs-lookup"><span data-stu-id="900e7-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="900e7-233">.\Get-MsolUserDeviceComplianceStatus.ps1 $u экспорта</span><span class="sxs-lookup"><span data-stu-id="900e7-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="900e7-234">Информация экспортируется на Рабочий стол Windows в виде CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="900e7-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="900e7-235">Вы можете использовать дополнительные параметры, чтобы указать имя файла и путь для CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="900e7-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="900e7-236">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="900e7-236">Related topics</span></span>

[<span data-ttu-id="900e7-237">Microsoft Connect снят</span><span class="sxs-lookup"><span data-stu-id="900e7-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="900e7-238">Общие сведения о базовом мобильном и системном обеспечении безопасности</span><span class="sxs-lookup"><span data-stu-id="900e7-238">Overview of Basic Mobility and Security</span></span>](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[<span data-ttu-id="900e7-239">Get — Мсолдевице</span><span class="sxs-lookup"><span data-stu-id="900e7-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)