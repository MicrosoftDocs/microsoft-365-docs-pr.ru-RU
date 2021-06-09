---
title: Создание Microsoft 365 учетных записей пользователей с помощью PowerShell
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
description: Использование PowerShell для создания отдельных или нескольких Microsoft 365 учетных записей пользователей.
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907568"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Создание Microsoft 365 учетных записей пользователей с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете использовать PowerShell для Microsoft 365 для эффективного создания учетных записей пользователей, в том числе нескольких учетных записей.

При создании учетных записей пользователей в PowerShell всегда требуются определенные свойства учетных записей. Другие свойства не требуются, но важны. См. следующую таблицу.
  
|**Имя свойства**|**Обязательный?**|**Описание**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |Да  <br/> |Это имя отображения, которое используется в Microsoft 365 службах. Например, *Caleb Sills*. <br/> |
|**UserPrincipalName** <br/> |Да  <br/> |Это имя учетной записи, используемой для регистрации Microsoft 365 служб. Например, *CalebS \@ contoso.onmicrosoft.com*.  <br/> |
|**FirstName** <br/> |Нет  <br/> ||
|**LastName** <br/> |Нет  <br/> ||
|**LicenseAssignment** <br/> |Нет  <br/> |Это план лицензирования (также известный как план лицензии или SKU), из которого доступная лицензия назначена учетной записи пользователя. Лицензия определяет Microsoft 365 службы, доступные для учетной записи. При создании учетной записи пользователю не нужно назначать лицензию, но у учетной записи должна быть лицензия на доступ к Microsoft 365 службам. Лицензию требуется добавить в течение 30 дней после создания учетной записи пользователя. |
|**Password** <br/> |Нет  <br/> | Если пароль не указан, случайный пароль назначен учетной записи пользователя, и пароль отображается в результатах команды. Если указать пароль, он должен быть от 8 до 16 текстовых символов ASCII следующих типов: буквы нижнего регистра, верхние буквы, цифры и символы.<br/> |
|**UsageLocation** <br/> |Нет  <br/> |Это допустимый код страны согласно ISO 3166-1 alpha-2 (например, US для США и FR для Франции). Например, *США* для США и *FR* для Франции. Важно предоставить это значение, так как некоторые Microsoft 365 службы недоступны в некоторых странах. Вы не можете назначить лицензию учетной записи пользователя, если эта учетная запись не настроена. Дополнительные сведения см. [в дополнительных сведениях об ограничениях лицензии.](https://go.microsoft.com/fwlink/p/?LinkId=691730)<br/> |

>[!Note]
>[Узнайте, как создавать учетные записи пользователей](../admin/add-users/add-users.md) с помощью Microsoft 365 центра администрирования.
> 
> Список дополнительных ресурсов см. в списке [Управление пользователями и группами.](../admin/add-users/index.yml)
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

После подключения используйте следующий синтаксис для создания отдельной учетной записи:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

В этом примере создается учетная запись для американского пользователя *Caleb Sills:*
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="create-an-individual-user-account"></a>Создание одной учетной записи пользователя

Чтобы создать одну учетную запись, используйте следующий синтаксис:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для Windows PowerShell и командлетов с *Msol* в их имени. Эти командлеты требуется запускать из Windows PowerShell.
>

Чтобы предоставить список доступных имен плана лицензирования, используйте следующую команду:

````powershell
Get-MsolAccountSku
````

В этом примере создается учетная запись для американского пользователя *Caleb Sills* и назначается лицензия из плана лицензирования `contoso:ENTERPRISEPACK` (Office 365 корпоративный E3).
  
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
   >Имена столбцов и их порядок в первом ряду CSV-файла являются произвольными. Но убедитесь, что порядок данных в остальном файле соответствует порядку имен столбцов. И используйте имена столбцов для значений параметров в PowerShell для Microsoft 365 команды.
    
2. Используйте следующий синтаксис:
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   В этом примере создаются учетные записи пользователей из файла *C:\My Documents\NewAccounts.csv* и журналы результатов в файле *C:\My Documents\NewAccountResults.csv.*
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. Результаты можно просмотреть в выходном файле. Мы не указали пароли, поэтому случайные пароли, Microsoft 365 созданные, видны в файле вывода.
    
## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)