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
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="fda22-103">Использование командлетов PowerShell для централизованного развертывания для управления надстройками</span><span class="sxs-lookup"><span data-stu-id="fda22-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="fda22-104">Как глобальный администратор Microsoft 365 вы можете развертывать надстройки Office для пользователей с помощью функции централизованного развертывания (см. раздел [Развертывание надстроек Office в центре администрирования](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span><span class="sxs-lookup"><span data-stu-id="fda22-104">As a Microsoft 365 global admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Deploy Office Add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span></span> <span data-ttu-id="fda22-105">Кроме развертывания надстроек Office с помощью центра администрирования Microsoft 365, вы также можете использовать Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fda22-105">In addition to deploying Office add-ins via the Microsoft 365 admin center, you can also use Microsoft PowerShell.</span></span> <span data-ttu-id="fda22-106">Установите [модуль развертывания Office 365 с централизованной надстройкой для Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span><span class="sxs-lookup"><span data-stu-id="fda22-106">Install the [O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span></span> 

<span data-ttu-id="fda22-107">После загрузки модуля откройте обычное окно Windows PowerShell и запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="fda22-107">After you download the module, open a regular Windows PowerShell window and run the following cmdlet:</span></span>

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="fda22-108">Подключение с использованием учетных данных администратора</span><span class="sxs-lookup"><span data-stu-id="fda22-108">Connect using your admin credentials</span></span>

<span data-ttu-id="fda22-109">Прежде чем использовать командлеты централизованного развертывания, необходимо войти в систему.</span><span class="sxs-lookup"><span data-stu-id="fda22-109">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="fda22-110">Запустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fda22-110">Start PowerShell.</span></span>
    
2. <span data-ttu-id="fda22-111">Подключитесь к PowerShell с помощью учетных данных администратора компании.</span><span class="sxs-lookup"><span data-stu-id="fda22-111">Connect to PowerShell by using your company admin credentials.</span></span> <span data-ttu-id="fda22-112">Выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="fda22-112">Run the following cmdlet.</span></span>
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="fda22-113">На странице **введите учетные данные** введите учетные данные глобального администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fda22-113">In the **Enter Credentials** page, enter your Microsoft 365 global admin credentials.</span></span> <span data-ttu-id="fda22-114">Кроме того, вы можете ввести свои учетные данные непосредственно в командлет.</span><span class="sxs-lookup"><span data-stu-id="fda22-114">Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="fda22-115">Выполните следующий командлет, указав учетные данные администратора компании в качестве объекта PSCredential.</span><span class="sxs-lookup"><span data-stu-id="fda22-115">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="fda22-116">Для получения дополнительных сведений об использовании PowerShell обратитесь [к разделу Подключение к Microsoft 365 с помощью PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span><span class="sxs-lookup"><span data-stu-id="fda22-116">For more information about using PowerShell, see [Connect to Microsoft 365 with PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="fda22-117">Отправка манифеста надстройки</span><span class="sxs-lookup"><span data-stu-id="fda22-117">Upload an add-in manifest</span></span>

<span data-ttu-id="fda22-118">Выполните командлет **New-организациянадстройки-in** , чтобы отправить манифест надстройки по пути, который может представлять собой расположение файла или URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="fda22-118">Run the **New-OrganizationAdd-In** cmdlet to upload an add-in manifest from a path, which can be either a file location or URL.</span></span> <span data-ttu-id="fda22-119">В следующем примере показано расположение файла для значения параметра  _манифестпас_ .</span><span class="sxs-lookup"><span data-stu-id="fda22-119">The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="fda22-120">Кроме того, можно выполнить командлет **New – организациянадстройки – in** , чтобы отправить надстройку и назначить ее пользователям или группам напрямую с помощью параметра  _Members_ , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fda22-120">You can also run the **New-OrganizationAdd-In** cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example.</span></span> <span data-ttu-id="fda22-121">Разделяйте адреса электронной почты членов запятыми.</span><span class="sxs-lookup"><span data-stu-id="fda22-121">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="fda22-122">Отправка надстройки из магазина Office</span><span class="sxs-lookup"><span data-stu-id="fda22-122">Upload an add-in from the Office Store</span></span>

<span data-ttu-id="fda22-123">Выполните командлет **New – организатионаддин** , чтобы отправить манифест из магазина Office.</span><span class="sxs-lookup"><span data-stu-id="fda22-123">Run the **New-OrganizationAddIn** cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="fda22-124">В следующем примере командлет **New – организатионаддин** указывает ассетид для надстройки для местонахождения США и рынка контента.</span><span class="sxs-lookup"><span data-stu-id="fda22-124">In the following example, the **New-OrganizationAddIn** cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="fda22-125">Чтобы определить значение параметра  _ассетид_ , можно скопировать его из URL-адреса веб-страницы магазина Office для надстройки.</span><span class="sxs-lookup"><span data-stu-id="fda22-125">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in.</span></span> <span data-ttu-id="fda22-126">Ассетидс всегда начинается с "WA", за которым следует число.</span><span class="sxs-lookup"><span data-stu-id="fda22-126">AssetIds always begin with "WA" followed by a number.</span></span> <span data-ttu-id="fda22-127">Например, в предыдущем примере источник для значения Ассетид для WA104099688 — это URL-адрес веб-страницы магазина Office для надстройки: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .</span><span class="sxs-lookup"><span data-stu-id="fda22-127">For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="fda22-128">Значения параметра  _locale_ и параметра  _контентмаркет_ идентичны и указывают страну или регион, из которого вы пытаетесь установить надстройку.</span><span class="sxs-lookup"><span data-stu-id="fda22-128">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from.</span></span> <span data-ttu-id="fda22-129">Формат — en-US, fr-FR.</span><span class="sxs-lookup"><span data-stu-id="fda22-129">The format is en-US, fr-FR.</span></span> <span data-ttu-id="fda22-130">и т. д.</span><span class="sxs-lookup"><span data-stu-id="fda22-130">and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fda22-131">Надстройки, отправленные из магазина Office, автоматически обновляются в течение нескольких дней с последнего обновления, доступного в магазине Office.</span><span class="sxs-lookup"><span data-stu-id="fda22-131">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="fda22-132">Получение сведений о надстройке</span><span class="sxs-lookup"><span data-stu-id="fda22-132">Get details of an add-in</span></span>

<span data-ttu-id="fda22-133">Выполните командлет **Get – организатионаддин** , как показано ниже, чтобы получить сведения обо всех надстройках, отправленных в клиент, включающих идентификатор продукта надстройки.</span><span class="sxs-lookup"><span data-stu-id="fda22-133">Run the **Get-OrganizationAddIn** cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```powershell
Get-OrganizationAddIn
```

<span data-ttu-id="fda22-134">Выполните командлет **Get – организатионаддин** со значением параметра  _ProductID_ , чтобы указать, для какой надстройки необходимо получить сведения.</span><span class="sxs-lookup"><span data-stu-id="fda22-134">Run the **Get-OrganizationAddIn** cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="fda22-135">Чтобы получить полные сведения обо всех надстройках, а также о назначенных пользователях и группах, перечислите выходные данные командлета **Get – организатионаддин** в командлет Format – List, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fda22-135">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the **Get-OrganizationAddIn** cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="fda22-136">Включение и отключение надстройки</span><span class="sxs-lookup"><span data-stu-id="fda22-136">Turn on or turn off an add-in</span></span>

<span data-ttu-id="fda22-137">Чтобы отключить надстройку, чтобы пользователи и группы, которым назначена эта надстройка, больше не были доступны, выполните командлет **Set – организатионаддин** с параметром  _ProductID_ и параметром  _Enabled_ , равным  `$false` , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fda22-137">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="fda22-138">Чтобы снова включить надстройку, выполните тот же командлет, для параметра  _Enabled_ которого задано значение  `$true` .</span><span class="sxs-lookup"><span data-stu-id="fda22-138">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="fda22-139">Добавление и удаление пользователей из надстройки</span><span class="sxs-lookup"><span data-stu-id="fda22-139">Add or remove users from an add-in</span></span>

<span data-ttu-id="fda22-140">Чтобы добавить пользователей и группы в определенную надстройку, выполните командлет **Set – организатионаддинассигнментс** с параметрами  _ProductID_,  _Add_и  _Members_ .</span><span class="sxs-lookup"><span data-stu-id="fda22-140">To add users and groups to a specific add-in, run the **Set-OrganizationAddInAssignments** cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters.</span></span> <span data-ttu-id="fda22-141">Разделяйте адреса электронной почты членов запятыми.</span><span class="sxs-lookup"><span data-stu-id="fda22-141">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="fda22-142">Чтобы удалить пользователей и группы, выполните один командлет с параметром  _Remove_ .</span><span class="sxs-lookup"><span data-stu-id="fda22-142">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="fda22-143">Чтобы назначить надстройку всем пользователям в клиенте, выполните тот же командлет с параметром  _ассигнтоеверйоне_ , для которого задано значение  `$true` .</span><span class="sxs-lookup"><span data-stu-id="fda22-143">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="fda22-144">Чтобы не присваивать надстройке всем пользователям и вернуться к ранее назначенным пользователям и группам, можно выполнить один и тот же командлет и отключить параметр  _ассигнтоеверйоне_ , присвоив ему значение  `$false` .</span><span class="sxs-lookup"><span data-stu-id="fda22-144">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="fda22-145">Обновление надстройки</span><span class="sxs-lookup"><span data-stu-id="fda22-145">Update an add-in</span></span>

<span data-ttu-id="fda22-146">Чтобы обновить надстройку с помощью манифеста, выполните командлет **Set – организатионаддин** с параметрами  _ProductID_,  _манифестпас_и  _locale_ , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fda22-146">To update an add-in from a manifest, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="fda22-147">Надстройки, отправленные из магазина Office, автоматически обновляются в течение нескольких дней с последнего обновления, доступного в магазине Office.</span><span class="sxs-lookup"><span data-stu-id="fda22-147">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="fda22-148">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="fda22-148">Delete an add-in</span></span>

<span data-ttu-id="fda22-149">Чтобы удалить надстройку, запустите командлет **Remove – организатионаддин** с параметром  _ProductID_ , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fda22-149">To delete an add-in, run the **Remove-OrganizationAddIn** cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="fda22-150">Получение подробной справки для каждого командлета</span><span class="sxs-lookup"><span data-stu-id="fda22-150">Get detailed help for each cmdlet</span></span>

<span data-ttu-id="fda22-151">С помощью командлета Get – Help можно просмотреть подробную справку для каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="fda22-151">You can look at detailed help for each cmdlet by using the Get-help cmdlet.</span></span> <span data-ttu-id="fda22-152">Например, следующий командлет предоставляет подробные сведения о командлете Remove – Организатионаддин.</span><span class="sxs-lookup"><span data-stu-id="fda22-152">For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```


