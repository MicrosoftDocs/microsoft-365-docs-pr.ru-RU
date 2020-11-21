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
description: В этой статье рассказывается, как использовать PowerShell для применения параметров конфигурации к клиентам в Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: dbb4135c89ac8d351c40bd7d9ce5301500a9b81b
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376571"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="cd6fb-103">Пример сценария для применения параметров EOP к нескольким клиентам</span><span class="sxs-lookup"><span data-stu-id="cd6fb-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cd6fb-104">Следующий пример скрипта позволяет администраторам Microsoft Exchange Online Protection (EOP), которые управляют несколькими клиентами (компаниями), использовать Exchange Online PowerShell для просмотра и/или применения параметров конфигурации к своим клиентам.</span><span class="sxs-lookup"><span data-stu-id="cd6fb-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="cd6fb-105">Запуск скрипта или командлета для нескольких клиентов</span><span class="sxs-lookup"><span data-stu-id="cd6fb-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="cd6fb-106">Если вы еще не сделали это, [установите модуль Exchange Online v2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="cd6fb-106">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="cd6fb-107">С помощью приложения для работы с электронными таблицами (например, Excel) создайте CSV-файл со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="cd6fb-107">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="cd6fb-108">Столбец UserName: учетная запись, которую вы будете использовать для подключения (например, `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="cd6fb-108">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="cd6fb-109">Столбец командлета: выполняемый командлет или команда (например, `Get-AcceptedDomain` или `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="cd6fb-109">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="cd6fb-110">Файл будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cd6fb-110">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="cd6fb-111">Сохраните CSV-файл в расположении, которое легко найти (например, c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="cd6fb-111">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="cd6fb-112">Скопируйте [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) скрипт в блокнот, а затем сохраните файл в месте, которое легко найти (например, c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="cd6fb-112">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="cd6fb-113">Выполните скрипт, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6fb-113">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="cd6fb-114">Пример:</span><span class="sxs-lookup"><span data-stu-id="cd6fb-114">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="cd6fb-115">Каждый клиент будет входить в систему, и сценарий будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="cd6fb-115">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="cd6fb-116">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="cd6fb-116">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="cd6fb-117">Возможно, вам потребуется изменить `Connect-IPPSSession` строку в сценарии, чтобы она была согласована с вашей средой.</span><span class="sxs-lookup"><span data-stu-id="cd6fb-117">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="cd6fb-118">Например, для Office 365 Германия необходимо указать значение _ConnectionURI_ , отличное от текущего значения в скрипте.</span><span class="sxs-lookup"><span data-stu-id="cd6fb-118">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="cd6fb-119">Дополнительные сведения см. в статье подключение к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="cd6fb-119">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
  
# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
