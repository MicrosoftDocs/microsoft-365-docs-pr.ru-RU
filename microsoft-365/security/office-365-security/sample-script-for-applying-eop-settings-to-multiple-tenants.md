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
ms.openlocfilehash: b7d856a7cec3bddc32455ba3afadf0323ddce935
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166595"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Пример сценария для применения параметров EOP к нескольким клиентам

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный режим Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

Следующий пример сценария позволяет администраторам Microsoft Exchange Online Protection (EOP), которые управляют несколькими клиентами (компаниями), использовать Exchange Online PowerShell для просмотра и/или применения параметров конфигурации к своим арендаторам.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Запуск скрипта или командлета для нескольких клиентов

1. Если вы еще не сделали этого, [установите модуль Exchange Online V2.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

2. С помощью приложения для электронных таблиц (например, Excel) создайте CSV-файл со следующими сведениями:

   - Столбец UserName: учетная запись, которую вы будете использовать для подключения `admin@contoso.onmicrosoft.com` (например).
   - Столбец командлета: командлет или команда для запуска (например, `Get-AcceptedDomain` или `Get-AcceptedDomain | FT Name` ).

   Файл будет выглядеть так:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Сохраните CSV-файл в расположении, которое легко найти (например, c:\scripts\inputfile.csv).

4. [СкопируйтеRunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) в Блокнот, а затем сохраните файл в расположении, которое легко найти (например, c:\scripts).

5. Выполните скрипт, используя следующий синтаксис:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Пример:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Каждый клиент будет вошел в систему, и будет запускаться сценарий.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> Вам может потребоваться изменить `Connect-IPPSSession` строку в сценарии в соответствии со своей средой. Например, для Office 365 Germany требуется другое значение _ConnectionUri,_ чем текущее значение в сценарии. Подробные сведения см. в подключении к [Exchange Online Powershell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

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
