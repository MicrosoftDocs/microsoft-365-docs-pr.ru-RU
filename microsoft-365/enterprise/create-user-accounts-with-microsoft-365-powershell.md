---
title: Создание учетных записей пользователей Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Использование PowerShell для создания отдельных или нескольких учетных записей пользователей Microsoft 365.
ms.openlocfilehash: d96de72ca3e7c4a439665c3ebf751a8fe25ce572
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754214"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Создание учетных записей пользователей Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

С помощью PowerShell для Microsoft 365 можно эффективно создавать учетные записи пользователей, включая несколько учетных записей.

При создании учетных записей пользователей в PowerShell всегда требуются определенные свойства учетной записи. Другие свойства не требуются, но важны. См. следующую таблицу.
  
|**Имя свойства**|**Обязательный?**|**Описание**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |Да  <br/> |Это отображаемая имя, используемая в службах Microsoft 365. Например, *Caleb Sills*. <br/> |
|**UserPrincipalName** <br/> |Да  <br/> |Это имя учетной записи, используемой для входов в службы Microsoft 365. Например, *CalebS \@ contoso.onmicrosoft.com*.  <br/> |
|**FirstName** <br/> |Нет  <br/> ||
|**LastName** <br/> |Нет  <br/> ||
|**LicenseAssignment** <br/> |Нет  <br/> |Это план лицензирования (также известный как план лицензирования или SKU), из которого учетной записи пользователя назначена доступная лицензия. Лицензия определяет службы Microsoft 365, доступные учетной записи. При создании учетной записи пользователю не нужно назначать лицензию, но у учетной записи должна быть лицензия на доступ к службам Microsoft 365. Лицензию требуется добавить в течение 30 дней после создания учетной записи пользователя. |
|**Password** <br/> |Нет  <br/> | Если пароль не указан, учетной записи пользователя назначен случайный пароль, который отображается в результатах команды. Если указать пароль, он должен быть от 8 до 16 текстовых символов ASCII следующих типов: буквы нижнего регистра, прописные буквы, цифры и символы.<br/> |
|**UsageLocation** <br/> |Нет  <br/> |Это допустимый код страны согласно ISO 3166-1 alpha-2 (например, US для США и FR для Франции). Например, *США* для США и *FR* для Франции. Важно предоставить это значение, так как некоторые службы Microsoft 365 недоступны в некоторых странах. Вы не можете назначить лицензию учетной записи пользователя, если в учетной записи не настроено это значение. Дополнительные сведения см. [в сведениях об ограничениях лицензий.](https://go.microsoft.com/fwlink/p/?LinkId=691730)<br/> |

>[!Note]
>[Узнайте, как создавать учетные записи пользователей](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) с помощью Центра администрирования Microsoft 365.
> 
> Список дополнительных ресурсов см. в [подсети "Управление пользователями и группами".](https://docs.microsoft.com/microsoft-365/admin/add-users/)
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

После подключения используйте следующий синтаксис для создания отдельной учетной записи:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

В этом примере создается учетная запись пользователя *Caleb Sills из США:*
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="create-an-individual-user-account"></a>Создание одной учетной записи пользователя

Чтобы создать одну учетную запись, используйте следующий синтаксис:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты *с Msol* в их имени. Эти командлеты требуется запускать из Windows PowerShell.
>

Чтобы предоставить список доступных имен плана лицензирования, используйте следующую команду:

````powershell
Get-MsolAccountSku
````

В этом примере создается учетная запись пользователя *Caleb Sills* в США и назначается лицензия из плана лицензирования `contoso:ENTERPRISEPACK` (Office 365 корпоративный E3).
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>Создание нескольких учетных записей пользователей

1. Создайте CSV-файл, который содержит обязательные сведения об учетных записях пользователей. Пример:

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   >Имена столбцов и их порядок в первой строке CSV-файла произвольны. Однако убедитесь, что порядок данных в остальной части файла соответствует порядку имен столбцов. Используйте имена столбцов для значений параметров в команде PowerShell для Microsoft 365.
    
2. Используйте указанный ниже синтаксис.
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   В этом примере создаются учетные записи пользователей из файла *C:\My Documents\NewAccounts.csv* и занося результаты в файл *C:\My Documents\NewAccountResults.csv.*
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. Результаты можно просмотреть в выходном файле. Мы не указали пароли, поэтому случайные пароли, созданные Microsoft 365, будут видны в выходной файле.
    
## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
