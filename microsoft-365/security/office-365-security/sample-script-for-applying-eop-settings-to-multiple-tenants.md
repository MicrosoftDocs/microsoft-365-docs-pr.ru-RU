---
title: Пример скрипта для параметров EOP — несколько клиентов
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: Из этой статьи вы узнаете, как использовать PowerShell, чтобы применить параметры конфигурации к клиентам в службе Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 46b7c756171da7687568e5135974841d828f45bd
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827461"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Пример скрипта для применения параметров EOP к нескольким клиентам

Следующий пример скрипта позволяет администраторам Microsoft Exchange Online Protection (EOP), которые управляют несколькими клиентами (компаниями), использовать Windows PowerShell для применения параметров конфигурации к своим клиентам.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Запуск скрипта или командлета для нескольких клиентов

1. С помощью приложения, например Excel, создайте CSV-файл (например, c:\scripts\inputfile.csv):

2. В CSV-файле укажите два столбца: UserName и Cmdlet.

3. Для каждой строки в CSV-файле добавьте имя администратора клиента в столбец UserName и командлет, который необходимо выполнить для этого клиента, в столбец Cmdlet. Например, введите admin@contoso.com и Get-AcceptedDomain.

4. Скопируйте [RunCmdletOnMultipleTenants.ps1в ](#runcmdletonmultipletenantsps1) Блокнот, а затем сохраните файл в легко найти расположение (например, c:\scripts).

5. Выполните скрипт, используя следующий синтаксис:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Пример:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Вход в каждый клиент будет выполнен, а также будет запущен сценарий.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
