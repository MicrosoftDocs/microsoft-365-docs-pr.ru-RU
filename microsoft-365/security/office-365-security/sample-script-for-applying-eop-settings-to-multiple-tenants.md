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
description: В этой статье вы узнаете, как использовать PowerShell для применения параметров конфигурации для клиентов в Microsoft Exchange Online Защиты (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1dce25901845628f8148c44a0d0783088255e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928512"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="41351-103">Пример сценария для применения параметров EOP к нескольким клиентам</span><span class="sxs-lookup"><span data-stu-id="41351-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41351-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="41351-104">**Applies to**</span></span>
-  [<span data-ttu-id="41351-105">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="41351-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="41351-106">Следующий пример сценария позволяет администраторам Microsoft Exchange Online (EOP), которые управляют несколькими арендаторами (компаниями), использовать Exchange Online PowerShell для просмотра и/или применения параметров конфигурации для своих клиентов.</span><span class="sxs-lookup"><span data-stu-id="41351-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="41351-107">Запуск скрипта или командлета для нескольких клиентов</span><span class="sxs-lookup"><span data-stu-id="41351-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="41351-108">Если вы еще не сделали этого, [установите модуль Exchange Online V2.](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)</span><span class="sxs-lookup"><span data-stu-id="41351-108">If you haven't already, [install the Exchange Online V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="41351-109">С помощью приложения таблицы (например, Excel) создайте файл CSV со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="41351-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="41351-110">Столбец UserName. Учетная запись, которую вы будете использовать для подключения (например, `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="41351-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="41351-111">Столбец командлета: командлет или команда для запуска (например, `Get-AcceptedDomain` или `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="41351-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="41351-112">Файл будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="41351-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="41351-113">Сохраните файл .csv в удобном для поиска расположении (например, c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="41351-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="41351-114">[СкопируйтеRunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) в блокнот, а затем сохраните файл в удобном для поиска расположении (например, c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="41351-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="41351-115">Выполните скрипт, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="41351-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="41351-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="41351-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="41351-117">Каждый клиент будет вошел в систему, и сценарий будет запускаться.</span><span class="sxs-lookup"><span data-stu-id="41351-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="41351-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="41351-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="41351-119">Возможно, потребуется изменить `Connect-IPPSSession` строку в скрипте, чтобы соответствовать среде.</span><span class="sxs-lookup"><span data-stu-id="41351-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="41351-120">Например, Для Office 365 в Германии требуется другое значение _ConnectionUri,_ чем текущее значение в скрипте.</span><span class="sxs-lookup"><span data-stu-id="41351-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="41351-121">Подробные сведения см. в материале Connect to [Exchange Online Powershell.](/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="41351-121">For details, see Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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