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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Пример сценария для применения параметров EOP к нескольким клиентам

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

Следующий пример сценария позволяет администраторам Microsoft Exchange Online (EOP), которые управляют несколькими арендаторами (компаниями), использовать Exchange Online PowerShell для просмотра и/или применения параметров конфигурации для своих клиентов.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Запуск скрипта или командлета для нескольких клиентов

1. Если вы еще не сделали этого, [установите модуль Exchange Online V2.](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

2. С помощью приложения таблицы (например, Excel) создайте файл CSV со следующими сведениями:

   - Столбец UserName. Учетная запись, которую вы будете использовать для подключения (например, `admin@contoso.onmicrosoft.com` ).
   - Столбец командлета: командлет или команда для запуска (например, `Get-AcceptedDomain` или `Get-AcceptedDomain | FT Name` ).

   Файл будет выглядеть так:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Сохраните файл .csv в удобном для поиска расположении (например, c:\scripts\inputfile.csv).

4. [СкопируйтеRunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) в блокнот, а затем сохраните файл в удобном для поиска расположении (например, c:\scripts).

5. Выполните скрипт, используя следующий синтаксис:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Пример:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Каждый клиент будет вошел в систему, и сценарий будет запускаться.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> Возможно, потребуется изменить `Connect-IPPSSession` строку в скрипте, чтобы соответствовать среде. Например, Для Office 365 в Германии требуется другое значение _ConnectionUri,_ чем текущее значение в скрипте. Подробные сведения см. в материале Connect to [Exchange Online Powershell.](/powershell/exchange/connect-to-exchange-online-protection-powershell)

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