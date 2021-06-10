---
title: Чтобы управлять надстройкими, используйте централизованные комлеты Deployment PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: Чтобы помочь развертыванию и управлению надстройки Office для вашей Microsoft 365 организации, используйте Office powerShell.
ms.openlocfilehash: 7872deedfcfe058f0a4ac63c489bbed139699d18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924676"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Чтобы управлять надстройкими, используйте централизованные комлеты Deployment PowerShell

В качестве Microsoft 365 глобального администратора можно развернуть Office пользователям с помощью функции централизованного развертывания (см. статью [Развертывание](../admin/manage/manage-deployment-of-add-ins.md)Office надстройки в центре администрирования). Помимо развертывания надстройок Office через центр администрирования Microsoft 365, вы также можете использовать Microsoft PowerShell. Установите [централизованный модуль развертывания O365 Add-In для Windows PowerShell.](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment) 

После загрузки модуля откройте обычное окно Windows PowerShell и запустите следующий командлет:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Подключение учетных данных администратора

Прежде чем использовать централизованные кодлеты развертывания, необходимо войти.
  
1. Запуск PowerShell.
    
2. Подключение PowerShell с помощью учетных данных администратора вашей компании. Запустите следующий cmdlet.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. На странице **Ввод учетных данных** введите свои Microsoft 365 учетные данные администратора. Поочередно можно ввести учетные данные непосредственно в cmdlet. 
    
    Запустите следующий комдлет с указанием учетных данных администратора компании в качестве объекта PSCredential.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Дополнительные сведения об использовании PowerShell см. в Подключение [Microsoft 365 с PowerShell.](./connect-to-microsoft-365-powershell.md) 
  
## <a name="upload-an-add-in-manifest"></a>Upload манифест надстройки

Запустите **комлет New-OrganizationAdd-In,** чтобы загрузить манифест надстройки с пути, который может быть расположением файла или URL-адресом. В следующем примере показано расположение файла для значения _параметра ManifestPath._ 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

Кроме того, можно запустить команды **New-OrganizationAdd-In,** чтобы загрузить надстройку и назначить ее пользователям или группам непосредственно с помощью параметра  _Members,_ как показано в следующем примере. Разделим адреса электронной почты участников с запятой. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Upload надстройку из Office Store

Запустите **кодлет New-OrganizationAddIn,** чтобы загрузить манифест из Office Store.
  
В следующем примере в **кодлете New-OrganizationAddIn** указывается AssetId для надстройки для рынка расположения и контента в США.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Чтобы определить значение _параметра AssetId,_ можно скопировать его с URL Office страницы магазина для надстройки. AssetIds всегда начинаются с "WA", за которым следует номер. Например, в предыдущем примере источником значения AssetId WA104099688 является URL-адрес веб-страницы Office Store для надстройки: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
Значения для параметра  _Locale_ и  _параметра ContentMarket_ идентичны и указывают страну или регион, в который вы пытаетесь установить надстройку. Формат en-US, fr-FR. и так далее. 
  
> [!NOTE]
> Надстройки, загруженные из Office Store, будут автоматически обновляться в течение нескольких дней после последнего обновления, доступного в Office Store. 
  
## <a name="get-details-of-an-add-in"></a>Сведения о надстройки

Запустите **cmdlet Get-OrganizationAddIn,** как показано ниже, чтобы получить сведения о всех надстройки, загруженных на клиента, включая код продукта надстройки.
  
```powershell
Get-OrganizationAddIn
```

Запустите **комлет Get-OrganizationAddIn** со значением для параметра  _ProductId,_ чтобы указать, для какой надстройки необходимо получить сведения. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Чтобы получить полные сведения о всех надстройках, а также о задавляемом пользователе и группах, перенаправляйте вывод комлета **Get-OrganizationAddIn** в Format-List, как показано в следующем примере.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Включите или отключите надстройки

Чтобы отключить надстройку, чтобы у пользователей и групп, которые ей назначены, больше не было доступа, запустите комлет **Set-OrganizationAddIn** с параметром  _ProductId_ и  _параметром Enabled,_ как показано в следующем  `$false` примере.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Чтобы включить надстройку, запустите тот же самый комдлет с параметром _Включен._ `$true`
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Добавление или удаление пользователей из надстройки

Чтобы добавить пользователей и группы в определенную надстройку, запустите команды **Set-OrganizationAddInAssignments** с параметрами _ProductId,_ _Add_ и _Members._ Разделим адреса электронной почты участников с запятой. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Чтобы удалить пользователей и группы, запустите один и тот же кодлет с помощью _параметра Remove._ 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Чтобы назначить надстройку всем пользователям клиента, запустите один и тот же кодлет с помощью  _параметра AssignToEveryone_ с заданным значением  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Чтобы не назначить надстройку всем и вернуться к ранее назначенным пользователям и группам, можно запустить один и тот же кодлет и отключить параметр  _AssignToEveryone,_ задав его значение  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Обновление надстройки

Чтобы обновить надстройку из манифеста, запустите кодлет **Set-OrganizationAddIn** с параметрами  _ProductId,_  _ManifestPath_ и  _Locale,_ как показано в следующем примере. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Надстройки, загруженные из Office Store, будут автоматически обновляться в течение нескольких дней после последнего обновления, доступного в Office Store. 
  
## <a name="delete-an-add-in"></a>Удаление надстройки

Чтобы удалить надстройку, запустите комлет **Remove-OrganizationAddIn** с параметром  _ProductId,_ как показано в следующем примере. 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a>Получить подробную справку для каждого cmdlet

Подробные сведения о каждом комлете можно найти с помощью cmdlet Get-help. Например, в следующем cmdlet содержится подробная информация о Remove-OrganizationAddIn.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```