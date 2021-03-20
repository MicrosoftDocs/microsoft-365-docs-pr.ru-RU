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
description: Используйте Windows PowerShell, чтобы получить сведения о устройствах Basic Mobility и Security в организации.
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904256"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Сведения об управляемых устройствах Basic Mobility и Security

В этой статье показано, как использовать Windows PowerShell для получения сведений о устройствах в организации, которые вы создали для Basic Mobility and Security.

Вот разбивка сведений о устройстве, доступных для вас.

|**Detail**|**Что нужно искать в PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Устройство зачислилось в Basic Mobility and Security. Дополнительные сведения см. в [записи мобильного устройства с помощью Basic Mobility and Security](enroll-your-mobile-device.md)|Значение *параметра isManaged:*  <br/>**True**= устройство зарегистрировано.<br/>**False**= устройство не зарегистрировано. |
|Устройство соответствует политикам безопасности устройств. Дополнительные сведения см. в [дополнительных сведениях о создании политик безопасности устройств](create-device-security-policies.md)|Значение *параметра isCompliant:*  <br/>**True**   = устройство соответствует политикам.<br/>**False**   = устройство не соответствует политикам.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Параметры Basic Mobility и Security PowerShell":::

>[!NOTE]
>Команды и скрипты в этой статье также возвращают сведения о любых устройствах, управляемых [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)

## <a name="before-you-begin"></a>Подготовка

Для запуска команд и сценариев, описанных в этой статье, необходимо настроить несколько вещей.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Шаг 1. Скачайте и установите модуль Azure Active Directory для Windows PowerShell

Дополнительные сведения об этих действиях см. в ссылке [Подключение к Microsoft 365 с помощью PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Перейдите Microsoft Online Services Sign-In помощника для [ИТ-специалистов RTWl](https://www.microsoft.com/download/details.aspx?id=41950)и выберите Скачать для Microsoft Online Services помощника по    **входу**.

2. Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, сделайте следующее:

    1. Откройте командную строку для уровня администратора PowerShell.  

    2. Выполните команду Install-Module MSOnline.

    3. Если отобразится запрос на установку поставщика NuGet, введите Y и нажмите клавишу ВВОД.

    4. Если отобразится запрос на установку модуля из репозитория PSGallery, введите Y и нажмите клавишу ВВОД.

    5. После установки закройте командное окно PowerShell.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Шаг 2. Подключение к подписке Microsoft 365

1. В модуле Windows Azure Active Directory для Windows PowerShell запустите следующую команду.  

    $UserCredential = Get-Credential

2. В диалоговом окне Windows PowerShell запроса учетных данных введите имя пользователя и пароль для глобальной учетной записи администратора Microsoft 365, а затем выберите **ОК.**

3. Выполните следующую команду.

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Шаг 3. Убедитесь, что вы можете запускать скрипты PowerShell

>[!NOTE]
>Этот шаг можно пропустить, если вы уже настроены для запуска сценариев PowerShell.

Чтобы запустить Get-MsolUserDeviceComplianceStatus.ps1, необходимо включить запуск скриптов PowerShell.

1. На рабочем столе Windows выберите **Начните** и введите Windows PowerShell. Щелкните правой кнопкой мыши Windows PowerShell, а затем выберите **Выполнить в качестве администратора**.

2. Выполните следующую команду.

    Set-ExecutionPolicy RemoteSigned

3. При запросе введите Y и нажмите кнопку Ввод.

**Запустите Get-MsolDevice для отображения сведений для всех устройств в организации**

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.  

2. Выполните следующую команду.

    Get-MsolDevice -All-ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}

Дополнительные примеры см.  [в примере Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).

## <a name="run-a-script-to-get-device-details"></a>Запустите скрипт, чтобы получить сведения об устройстве

Сначала сохраните скрипт на компьютере.

1. Скопируйте и вклейте следующий текст в блокнот.  

2.  param (

3.  [PSObject[]$users = @(),

4.  [Switch]$export,

5.  [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [Окружающая среда]::GetFolderPath ("Настольный компьютер")

7.  )

9.  [System.Collections.IDictionary]$script:схемы = @{

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
    

25.  функция createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object-TypeName PSObject-Property $script:schema
    

30.  возвращение $resultObject
    

31.  }
    

33.  Если ($users. Count -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]] $result = foreach ($u в $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice-RegisteredOwnerUpn $u.UserPrincipalName
    

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
    

63.  Если ($export)
    

64.  {
    

65.  $result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Сохраните его как Windows PowerShell скрипта с помощью расширения файла .ps1; например, Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Запустите скрипт, чтобы получить сведения об устройстве для одной учетной записи пользователя

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.
    
2. Перейдите к папке, в которой сохранен сценарий. Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.
    
    cd C:\PS-Scripts

3. Запустите следующую команду, чтобы определить пользователя, для получения сведений о устройстве. В этом примере вы также bar@example.com.
    
    $u = Get-MsolUser-UserPrincipalName bar@example.com

4. Запустите следующую команду, чтобы инициировать сценарий.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

Эти сведения экспортируются в windows Desktop в качестве CSV-файла. Для указания имени файла и пути CSV можно использовать дополнительные параметры.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Запустите скрипт, чтобы получить сведения об устройстве для группы пользователей

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.
    
2. Перейдите к папке, в которой сохранен сценарий. Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.   

    cd C:\PS-Scripts

3. Запустите следующую команду, чтобы определить группу, для получения сведений о устройстве. В этом примере получаются сведения для пользователей из группы FinanceStaff. 

    $u = Get-MsolGroupMember-SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }

4. Запустите следующую команду, чтобы инициировать сценарий.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

Эти сведения экспортируются в windows Desktop в качестве CSV-файла. Для указания имени файла и пути CSV можно использовать дополнительные параметры.

## <a name="related-topics"></a>Родственные темы

[Microsoft Connect была снята с службы](/collaborate/connect-redirect)

[Обзор Basic Mobility + Security](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)