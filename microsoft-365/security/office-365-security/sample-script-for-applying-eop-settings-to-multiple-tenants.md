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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="3e47c-103">Пример скрипта для применения параметров EOP к нескольким клиентам</span><span class="sxs-lookup"><span data-stu-id="3e47c-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="3e47c-104">Следующий пример скрипта позволяет администраторам Microsoft Exchange Online Protection (EOP), которые управляют несколькими клиентами (компаниями), использовать Windows PowerShell для применения параметров конфигурации к своим клиентам.</span><span class="sxs-lookup"><span data-stu-id="3e47c-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="3e47c-105">Запуск скрипта или командлета для нескольких клиентов</span><span class="sxs-lookup"><span data-stu-id="3e47c-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="3e47c-106">С помощью приложения, например Excel, создайте CSV-файл (например, c:\scripts\inputfile.csv):</span><span class="sxs-lookup"><span data-stu-id="3e47c-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="3e47c-107">В CSV-файле укажите два столбца: UserName и Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3e47c-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="3e47c-p101">Для каждой строки в CSV-файле добавьте имя администратора клиента в столбец UserName и командлет, который необходимо выполнить для этого клиента, в столбец Cmdlet. Например, введите admin@contoso.com и Get-AcceptedDomain.</span><span class="sxs-lookup"><span data-stu-id="3e47c-p101">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column. For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="3e47c-110">Скопируйте [RunCmdletOnMultipleTenants.ps1в ](#runcmdletonmultipletenantsps1) Блокнот, а затем сохраните файл в легко найти расположение (например, c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="3e47c-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find  (for example, c:\scripts).</span></span>

5. <span data-ttu-id="3e47c-111">Выполните скрипт, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3e47c-111">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="3e47c-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="3e47c-112">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="3e47c-113">Вход в каждый клиент будет выполнен, а также будет запущен сценарий.</span><span class="sxs-lookup"><span data-stu-id="3e47c-113">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="3e47c-114">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="3e47c-114">RunCmdletOnMultipleTenants.ps1</span></span>

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
