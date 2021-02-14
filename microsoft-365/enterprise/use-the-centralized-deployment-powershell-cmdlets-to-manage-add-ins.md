---
title: Использование централизованного развертывания powerShell для управления надстройки
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
description: Используйте централизованное развертывание powerShell для развертывания надстройок Office в организации Microsoft 365 и управления ими.
ms.openlocfilehash: 659f12d2533601c4b2165a95ddbf59ea521945b8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693445"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Использование централизованного развертывания powerShell для управления надстройки

Как глобальный администратор Microsoft 365 вы можете развертывать надстройки Office для пользователей с помощью функции централизованного развертывания (см. статью "Развертывание надстройки Office в Центре [администрирования").](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins) Помимо развертывания надстройки Office через Центр администрирования Microsoft 365, вы также можете использовать Microsoft PowerShell. Установите модуль централизованного развертывания [O365 Add-In для Windows PowerShell.](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment) 

После загрузки модуля откройте обычное окно Windows PowerShell и запустите следующий командлет:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Подключение с помощью учетных данных администратора

Прежде чем использовать централизованные развертывание, необходимо войти.
  
1. Запустите PowerShell.
    
2. Подключись к PowerShell, используя учетные данные администратора компании. Запустите следующий cmdlet.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. На странице **"Ввод учетных данных"** введите учетные данные глобального администратора Microsoft 365. Кроме того, вы можете ввести свои учетные данные непосредственно в cmdlet. 
    
    Запустите следующий cmdlet, указав учетные данные администратора компании в качестве объекта PSCredential.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Дополнительные сведения об использовании PowerShell см. в подключении к [Microsoft 365 с помощью PowerShell.](https://go.microsoft.com/fwlink/p/?linkid=848585) 
  
## <a name="upload-an-add-in-manifest"></a>Отправка манифеста надстройки

Запустите **cmdlet New-OrganizationAdd-In,** чтобы отправить манифест надстройки по пути, который может быть расположением файла или URL-адресом. В следующем примере показано расположение файла для значения _параметра ManifestPath._ 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

Кроме того, можно выполнить с помощью команды **New-OrganizationAdd-In,** чтобы отправить надстройку и назначить ее пользователям или группам напрямую с помощью параметра  _Members,_ как показано в следующем примере. Разделять адреса электронной почты участников запятой. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Отправка надстройки из Магазина Office

Запустите **cmdlet New-OrganizationAddIn,** чтобы отправить манифест из Магазина Office.
  
В следующем примере для надстройки для рынка расположения и контента в США указывается код AssetId для **new-OrganizationAddIn.**
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Чтобы определить значение параметра  _AssetId,_ можно скопировать его с URL-адреса веб-страницы Магазина Office для надстройки. AssetIds всегда начинаются с "WA", за которым следует число. Например, в предыдущем примере источником значения AssetId wa104099688 является URL-адрес веб-страницы Магазина Office для надстройки: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688)
  
Значения параметров  _Locale_ и  _ContentMarket_ идентичны и указывают страну или регион, из которые вы пытаетесь установить надстройку. Формат: en-US, fr-FR. и так далее. 
  
> [!NOTE]
> Надстройки, загруженные из Магазина Office, будут автоматически обновляться в течение нескольких дней после того, как в Магазине Office будет доступно последнее обновление. 
  
## <a name="get-details-of-an-add-in"></a>Получить сведения о надстройки

Запустите **cmdlet Get-OrganizationAddIn,** как показано ниже, чтобы получить сведения о всех надстройки, загруженных в клиент, включая код продукта надстройки.
  
```powershell
Get-OrganizationAddIn
```

Запустите **cmdlet Get-OrganizationAddIn** со значением параметра  _ProductId,_ чтобы указать, для какой надстройки требуется получить сведения. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Чтобы получить полные сведения о всех надстройки, а также о назначенных пользователях и группах, перенаправляйте выходные данные из **get-OrganizationAddIn** в Format-List, как показано в следующем примере.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Включите или отключите надстройки

Чтобы отключить надстройку, чтобы у пользователей и групп, которые ей были назначены, больше не было доступа, запустите **cmdlet Set-OrganizationAddIn** с параметром _ProductId_ и параметром _Enabled,_ как показано в следующем примере. `$false`
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Чтобы снова включить надстройку, запустите тот же самый cmdlet с параметром _Enabled._ `$true`
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Добавление или удаление пользователей из надстройки

Чтобы добавить пользователей и группы в определенную надстройку, запустите **cmdlet Set-OrganizationAddInAssignments** с параметрами _ProductId,_ _Add_ и _Members._ Разделять адреса электронной почты участников запятой. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Чтобы удалить пользователей и группы, запустите тот же самый cmdlet с помощью _параметра Remove._ 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Чтобы назначить надстройку всем пользователям в клиенте, запустите тот же самый cmdlet, используя параметр  _AssignToEveryone_ со значением , установленным на  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Чтобы не назначать надстройку всем и вернуться к ранее назначенной группе и пользователям, можно запустить тот же самый и тот же параметр и отключить параметр  _AssignToEveryone,_ задав для нее значение  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Обновление надстройки

Чтобы обновить надстройку из манифеста, запустите его с параметрами _ProductId,_ _ManifestPath_ и _Locale,_ как показано в следующем примере.  
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Надстройки, загруженные из Магазина Office, будут автоматически обновляться в течение нескольких дней после того, как в Магазине Office будет доступно последнее обновление. 
  
## <a name="delete-an-add-in"></a>Удаление надстройки

Чтобы удалить надстройку, запустите **cmdlet Remove-OrganizationAddIn** с параметром  _ProductId,_ как показано в следующем примере. 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a>Получите подробную справку по каждому из них

Подробные сведения о каждом из них см. в справке с помощью get-help. Например, следующий cmdlet предоставляет подробные сведения о Remove-OrganizationAddIn.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```


