---
title: Использование командлетов PowerShell для централизованного развертывания для управления надстройками
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
description: Используйте командлеты PowerShell централизованного развертывания для развертывания надстроек Office для организации Microsoft 365 и управления ими.
ms.openlocfilehash: 659f12d2533601c4b2165a95ddbf59ea521945b8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693445"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Использование командлетов PowerShell для централизованного развертывания для управления надстройками

Как глобальный администратор Microsoft 365 вы можете развертывать надстройки Office для пользователей с помощью функции централизованного развертывания (см. раздел [Развертывание надстроек Office в центре администрирования](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)). Кроме развертывания надстроек Office с помощью центра администрирования Microsoft 365, вы также можете использовать Microsoft PowerShell. Установите [модуль развертывания Office 365 с централизованной надстройкой для Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment). 

После загрузки модуля откройте обычное окно Windows PowerShell и запустите следующий командлет:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Подключение с использованием учетных данных администратора

Прежде чем использовать командлеты централизованного развертывания, необходимо войти в систему.
  
1. Запустите PowerShell.
    
2. Подключитесь к PowerShell с помощью учетных данных администратора компании. Выполните следующий командлет.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. На странице **введите учетные данные** введите учетные данные глобального администратора Microsoft 365. Кроме того, вы можете ввести свои учетные данные непосредственно в командлет. 
    
    Выполните следующий командлет, указав учетные данные администратора компании в качестве объекта PSCredential.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Для получения дополнительных сведений об использовании PowerShell обратитесь [к разделу Подключение к Microsoft 365 с помощью PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585). 
  
## <a name="upload-an-add-in-manifest"></a>Отправка манифеста надстройки

Выполните командлет **New-организациянадстройки-in** , чтобы отправить манифест надстройки по пути, который может представлять собой расположение файла или URL-адрес. В следующем примере показано расположение файла для значения параметра  _манифестпас_ . 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

Кроме того, можно выполнить командлет **New – организациянадстройки – in** , чтобы отправить надстройку и назначить ее пользователям или группам напрямую с помощью параметра  _Members_ , как показано в следующем примере. Разделяйте адреса электронной почты членов запятыми. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Отправка надстройки из магазина Office

Выполните командлет **New – организатионаддин** , чтобы отправить манифест из магазина Office.
  
В следующем примере командлет **New – организатионаддин** указывает ассетид для надстройки для местонахождения США и рынка контента.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Чтобы определить значение параметра  _ассетид_ , можно скопировать его из URL-адреса веб-страницы магазина Office для надстройки. Ассетидс всегда начинается с "WA", за которым следует число. Например, в предыдущем примере источник для значения Ассетид для WA104099688 — это URL-адрес веб-страницы магазина Office для надстройки: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
Значения параметра  _locale_ и параметра  _контентмаркет_ идентичны и указывают страну или регион, из которого вы пытаетесь установить надстройку. Формат — en-US, fr-FR. и т. д. 
  
> [!NOTE]
> Надстройки, отправленные из магазина Office, автоматически обновляются в течение нескольких дней с последнего обновления, доступного в магазине Office. 
  
## <a name="get-details-of-an-add-in"></a>Получение сведений о надстройке

Выполните командлет **Get – организатионаддин** , как показано ниже, чтобы получить сведения обо всех надстройках, отправленных в клиент, включающих идентификатор продукта надстройки.
  
```powershell
Get-OrganizationAddIn
```

Выполните командлет **Get – организатионаддин** со значением параметра  _ProductID_ , чтобы указать, для какой надстройки необходимо получить сведения. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Чтобы получить полные сведения обо всех надстройках, а также о назначенных пользователях и группах, перечислите выходные данные командлета **Get – организатионаддин** в командлет Format – List, как показано в следующем примере.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Включение и отключение надстройки

Чтобы отключить надстройку, чтобы пользователи и группы, которым назначена эта надстройка, больше не были доступны, выполните командлет **Set – организатионаддин** с параметром  _ProductID_ и параметром  _Enabled_ , равным  `$false` , как показано в следующем примере.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Чтобы снова включить надстройку, выполните тот же командлет, для параметра  _Enabled_ которого задано значение  `$true` .
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Добавление и удаление пользователей из надстройки

Чтобы добавить пользователей и группы в определенную надстройку, выполните командлет **Set – организатионаддинассигнментс** с параметрами  _ProductID_,  _Add_и  _Members_ . Разделяйте адреса электронной почты членов запятыми. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Чтобы удалить пользователей и группы, выполните один командлет с параметром  _Remove_ . 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Чтобы назначить надстройку всем пользователям в клиенте, выполните тот же командлет с параметром  _ассигнтоеверйоне_ , для которого задано значение  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Чтобы не присваивать надстройке всем пользователям и вернуться к ранее назначенным пользователям и группам, можно выполнить один и тот же командлет и отключить параметр  _ассигнтоеверйоне_ , присвоив ему значение  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Обновление надстройки

Чтобы обновить надстройку с помощью манифеста, выполните командлет **Set – организатионаддин** с параметрами  _ProductID_,  _манифестпас_и  _locale_ , как показано в следующем примере. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Надстройки, отправленные из магазина Office, автоматически обновляются в течение нескольких дней с последнего обновления, доступного в магазине Office. 
  
## <a name="delete-an-add-in"></a>Удаление надстройки

Чтобы удалить надстройку, запустите командлет **Remove – организатионаддин** с параметром  _ProductID_ , как показано в следующем примере. 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a>Получение подробной справки для каждого командлета

С помощью командлета Get – Help можно просмотреть подробную справку для каждого командлета. Например, следующий командлет предоставляет подробные сведения о командлете Remove – Организатионаддин.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```


