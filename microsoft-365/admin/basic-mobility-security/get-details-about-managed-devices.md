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
description: Используйте Windows PowerShell для получения сведений об основных мобильных устройствах и устройствах безопасности в организации.
ms.openlocfilehash: 7c6a0365dfd573377c3675bbcee8ee8280e33816
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876892"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Сведения об управляемых устройствах Basic Mobility и Security

В этой статье показано, как использовать Windows PowerShell для получения сведений об устройствах в организации, которые вы настроили для Базовой мобильности и безопасности.

Ниже вы можете получить подробные сведения об устройстве.

|**Detail**|**Что нужно искать в PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Устройство зарегистрировать в Basic Mobility and Security. Дополнительные сведения [см.](enroll-your-mobile-device.md) в записи мобильного устройства с помощью Basic Mobility and Security|Значение параметра *isManaged:*  <br/>**True**= устройство зарегистрировать.<br/>**False**= устройство не зарегистрировать. |
|Устройство соответствует политикам безопасности устройства. Дополнительные сведения см. в [дополнительных сведениях о создании политик безопасности устройств](create-device-security-policies.md)|Значение параметра *isCompliant:*  <br/>**True**   = устройство соответствует политикам.<br/>**False**   = устройство не соответствует политикам.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Параметры Basic Mobility and Security PowerShell":::

>[!NOTE]
>Команды и сценарии в этой статье также возвращают сведения о любых устройствах, управляемых [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)

## <a name="before-you-begin"></a>Прежде чем начать

Существует несколько вещей, которые необходимо настроить для запуска команд и сценариев, описанных в этой статье.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Шаг 1. Скачайте и установите модуль Azure Active Directory для Windows PowerShell

Дополнительные сведения об этих действиях см. в [подключении к Microsoft 365 с помощью PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Перейдите Microsoft Online Services Sign-In помощника для ИТ-специалистов [по RTWl](https://www.microsoft.com/download/details.aspx?id=41950)и выберите "Загрузить для Microsoft Online Services помощника по    **входу".**   

2. Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, сделайте следующее:

    1. Откройте командную строку для уровня администратора PowerShell.  

    2. Выполните команду Install-Module MSOnline.

    3. Если отобразится запрос на установку поставщика NuGet, введите Y и нажмите клавишу ВВОД.

    4. Если отобразится запрос на установку модуля из репозитория PSGallery, введите Y и нажмите клавишу ВВОД.

    5. После установки закройте командное окно PowerShell.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Шаг 2. Подключение к подписке Microsoft 365

1. В модуле Windows Azure Active Directory для Windows PowerShell запустите следующую команду.  

    $UserCredential = Get-Credential

2. В диалоговом Windows PowerShell запроса учетных данных введите имя пользователя и пароль для учетной записи глобального администратора Microsoft 365, а затем выберите **"ОК".**

3. Выполните следующую команду.

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Шаг 3. Убедитесь, что вы можете запускать сценарии PowerShell

>[!NOTE]
>Этот шаг можно пропустить, если вы уже настроены на запуск сценариев PowerShell.

Чтобы запустить сценарий Get-MsolUserDeviceComplianceStatus.ps1, необходимо включить запуск сценариев PowerShell.

1. На рабочем столе Windows выберите **"Начните"** и введите Windows PowerShell. Щелкните правой кнопкой мыши Windows PowerShell выберите "Запуск **от администратора".**

2. Выполните следующую команду.

    Set-ExecutionPolicy RemoteSigned

3. При запросе введите Y и нажмите ввод.

**Запустите Get-MsolDevice для отображения сведений о всех устройствах в организации**

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.  

2. Выполните следующую команду.

    Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}

Дополнительные примеры см. в  [примере Get-MsolDevice.](https://go.microsoft.com/fwlink/?linkid=841721)

## <a name="run-a-script-to-get-device-details"></a>Запуск сценария для получения сведений об устройстве

Сначала сохраните сценарий на компьютере.

1. Скопируйте и в paste следующий текст в Блокноте.  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [Switch]$export,

5.  [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [Environment]::GetFolderPath("Desktop")

7.  )

9.  [System.Collections.IDictionary]$script:schema = @{

11.  DeviceId = ''

12.  DeviceOSType = ''

13.  DeviceOSVersion = ''

14.  DeviceTrustLevel = ''

15.  DisplayName = ''

16.  IsCompliant = ''

17.  IsManaged = ''

18.  ApproximateLastLogonTimestamp = ''

19.  DeviceObjectId = ''

20.  RegisteredOwnerUpn = ''

21.  RegisteredOwnerObjectId = ''
    

22.  RegisteredOwnerDisplayName = ''
    

23.  }
    

25.  function createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
    

30.  возвращаемая $resultObject
    

31.  }
    

33.  If ($users. Count -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]]$result = foreach ($u в $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach ($d в $devices)
    

43.  {
    

44.  [PSObject]$deviceResult = createResultObject
    

45.  $deviceResult.DeviceId = $d.DeviceId
    

46.  $deviceResult.DeviceOSType = $d.DeviceOSType
    

47.  $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
    

48.  $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
    

49.  $deviceResult.DisplayName = $d.DisplayName
    

50.  $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
    

51.  $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
    

52.  $deviceResult.DeviceObjectId = $d.ObjectId
    

53.  $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
    

54.  $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
    

55.  $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
    

56.  $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Сохраните его в Windows PowerShell с помощью расширения PS1; например, Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Запуск сценария для получения сведений об устройстве для одной учетной записи пользователя

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.
    
2. Перейдите в папку, в которой сохранен сценарий. Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.
    
    cd C:\PS-Scripts

3. Чтобы определить пользователя, для который вы хотите получить сведения об устройстве, запустите следующую команду. В этом примере по bar@example.com.
    
    $u = Get-MsolUser -UserPrincipalName bar@example.com

4. Чтобы запустить сценарий, запустите следующую команду.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

Эти сведения экспортируются на рабочий стол Windows в CSV-файле. Вы можете использовать дополнительные параметры, чтобы указать имя файла и путь CSV-файла.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Запуск сценария для получения сведений об устройстве для группы пользователей

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.
    
2. Перейдите в папку, в которой сохранен сценарий. Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.   

    cd C:\PS-Scripts

3. Чтобы определить группу, для получения сведений об устройстве, запустите следующую команду. В этом примере возвращается информация о пользователях в группе FinanceStaff. 

    $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }

4. Чтобы запустить сценарий, запустите следующую команду.   

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

Эти сведения экспортируются на рабочий стол Windows в CSV-файле. Вы можете использовать дополнительные параметры, чтобы указать имя файла и путь CSV-файла.

## <a name="related-topics"></a>Связанные статьи

[Microsoft Connect больше не установлен](https://docs.microsoft.com/collaborate/connect-redirect)

[Обзор Basic Mobility + Security](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)