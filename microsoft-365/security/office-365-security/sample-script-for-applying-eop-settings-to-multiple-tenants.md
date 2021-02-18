---
title: Пример сценария для параметров EOP — несколько клиентов
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: В этой статье вы узнаете, как использовать PowerShell для применения параметров конфигурации к своим арендаторам в Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4823ed09cd8a9d72aef21df3d51213cb4512b4f9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288541"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="f8c34-103">Пример сценария для применения параметров EOP к нескольким клиентам</span><span class="sxs-lookup"><span data-stu-id="f8c34-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f8c34-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f8c34-104">**Applies to**</span></span>
-  [<span data-ttu-id="f8c34-105">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f8c34-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="f8c34-106">Следующий пример сценария позволяет администраторам Microsoft Exchange Online Protection (EOP), которые управляют несколькими клиентами (компаниями), использовать Exchange Online PowerShell для просмотра и/или применения параметров конфигурации к своим арендаторам.</span><span class="sxs-lookup"><span data-stu-id="f8c34-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="f8c34-107">Запуск скрипта или командлета для нескольких клиентов</span><span class="sxs-lookup"><span data-stu-id="f8c34-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="f8c34-108">Если вы еще не сделали этого, [установите модуль Exchange Online V2.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)</span><span class="sxs-lookup"><span data-stu-id="f8c34-108">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="f8c34-109">С помощью приложения для электронных таблиц (например, Excel) создайте CSV-файл со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="f8c34-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="f8c34-110">Столбец UserName: учетная запись, которую вы будете использовать для подключения `admin@contoso.onmicrosoft.com` (например).</span><span class="sxs-lookup"><span data-stu-id="f8c34-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="f8c34-111">Столбец командлета: командлет или команда для запуска (например, `Get-AcceptedDomain` или `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="f8c34-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="f8c34-112">Файл будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="f8c34-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="f8c34-113">Сохраните CSV-файл в расположении, которое легко найти (например, c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="f8c34-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="f8c34-114">[СкопируйтеRunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) в Блокнот, а затем сохраните файл в расположении, которое легко найти (например, c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="f8c34-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="f8c34-115">Выполните скрипт, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f8c34-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="f8c34-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8c34-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="f8c34-117">Каждый клиент будет вошел в систему, и будет запускаться сценарий.</span><span class="sxs-lookup"><span data-stu-id="f8c34-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="f8c34-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="f8c34-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="f8c34-119">Возможно, потребуется изменить `Connect-IPPSSession` строку в сценарии в соответствии со своей средой.</span><span class="sxs-lookup"><span data-stu-id="f8c34-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="f8c34-120">Например, для Office 365 Germany требуется другое значение _ConnectionUri,_ чем текущее значение в сценарии.</span><span class="sxs-lookup"><span data-stu-id="f8c34-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="f8c34-121">Подробные сведения см. в подключении к [Exchange Online Powershell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="f8c34-121">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
