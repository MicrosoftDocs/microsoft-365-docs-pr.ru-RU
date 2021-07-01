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
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Сведения об управляемых устройствах Basic Mobility и Security

В этой статье показано, как использовать Windows PowerShell для получения сведений о устройствах в организации, которые настроены для базовой мобильности и безопасности.

Вот разбивка сведений о устройстве, доступных для вас.

|**Detail**|**Что нужно искать в PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Устройство зачислилось в Basic Mobility and Security. Дополнительные сведения см. в [записи мобильного устройства с помощью Basic Mobility and Security](enroll-your-mobile-device.md)|Значение *параметра isManaged:*  <br/>**True**= устройство зарегистрировано.<br/>**False**= устройство не зарегистрировано. |
|Устройство соответствует политикам безопасности устройств. Дополнительные сведения см. в [дополнительных сведениях о создании политик безопасности устройств](create-device-security-policies.md)|Значение *параметра isCompliant:*  <br/>**True**   = устройство соответствует политикам.<br/>**False**   = устройство не соответствует политикам.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Параметры Basic Mobility и Security PowerShell":::

> [!NOTE]
> Команды и скрипты в этой статье также возвращают сведения о любых устройствах, управляемых [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Прежде чем начать

Для запуска команд и сценариев, описанных в этой статье, необходимо настроить несколько вещей.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Шаг 1. Скачайте и установите модуль Azure Active Directory для Windows PowerShell

Дополнительные сведения об этих действиях см. в [Подключение Microsoft 365 PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Перейдите Microsoft Online Services Sign-In помощника для [ИТ-специалистов RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)и выберите Скачать для Microsoft Online Services помощника по    **входу**.

2. Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, сделайте следующее:

    1. Откройте командную строку для уровня администратора PowerShell.

    2. Выполните команду `Install-Module MSOnline`.

    3. Если отобразится запрос на установку поставщика NuGet, введите Y и нажмите клавишу ВВОД.

    4. Если отобразится запрос на установку модуля из репозитория PSGallery, введите Y и нажмите клавишу ВВОД.

    5. После установки закройте командное окно PowerShell.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Шаг 2. Подключение подписку на Microsoft 365

1. В модуле Windows Azure Active Directory для Windows PowerShell запустите следующую команду.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. В диалоговом окне Windows PowerShell запроса учетных данных введите имя пользователя и пароль для глобальной Microsoft 365 учетной записи администратора, а затем выберите **ОК**.

3. Выполните следующую команду.

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Шаг 3. Убедитесь, что вы можете запускать скрипты PowerShell

> [!NOTE]
> Этот шаг можно пропустить, если вы уже настроены для запуска сценариев PowerShell.

Чтобы запустить Get-MsolUserDeviceComplianceStatus.ps1, необходимо включить запуск скриптов PowerShell.

1. Из рабочего Windows выберите **Начните,** а затем введите Windows PowerShell. Щелкните правой кнопкой мыши Windows PowerShell, а затем выберите **Выполнить в качестве администратора.**

2. Выполните следующую команду.

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. При запросе введите Y и нажмите кнопку Ввод.

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Запустите Get-MsolDevice для отображения сведений для всех устройств в организации

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.

2. Выполните следующую команду.

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

Дополнительные примеры см.  [в примере Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).

## <a name="run-a-script-to-get-device-details"></a>Запустите скрипт, чтобы получить сведения об устройстве

Сначала сохраните скрипт на компьютере.

1. Скопируйте и вклеите следующий текст в Блокнот.

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

2. Сохраните его как файл Windows PowerShell с помощью расширения файла .ps1; например, Get-MsolUserDeviceComplianceStatus.ps1.

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Запустите скрипт, чтобы получить сведения об устройстве для одной учетной записи пользователя

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.

2. Перейдите к папке, в которой сохранен сценарий. Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Запустите следующую команду, чтобы определить пользователя, для получения сведений о устройстве. В этом примере вы также bar@example.com.

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. Запустите следующую команду, чтобы инициировать сценарий.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

Эти сведения экспортируются на Windows desktop в качестве CSV-файла. Для указания имени файла и пути CSV можно использовать дополнительные параметры.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Запустите скрипт, чтобы получить сведения об устройстве для группы пользователей

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.

2. Перейдите к папке, в которой сохранен сценарий. Например, если вы сохранили его в C:\PS-Scripts, запустите следующую команду.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Запустите следующую команду, чтобы определить группу, для получения сведений о устройстве. В этом примере получаются сведения для пользователей из группы FinanceStaff.

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. Запустите следующую команду, чтобы инициировать сценарий.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

Эти сведения экспортируются на Windows desktop в качестве CSV-файла. Для указания имени файла и пути CSV можно использовать дополнительные параметры.

## <a name="related-topics"></a>Похожие темы

[Microsoft Подключение была снята с службы](/collaborate/connect-redirect)

[Обзор Basic Mobility + Security](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
