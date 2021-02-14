---
title: Управление пользователями и группами SharePoint Online с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
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
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: В этой статье вы узнаете, как использовать PowerShell для Microsoft 365 для управления пользователями, группами и сайтами SharePoint Online.
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693413"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a><span data-ttu-id="a65a7-103">Управление пользователями и группами SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a65a7-103">Manage SharePoint Online users and groups with PowerShell</span></span>

<span data-ttu-id="a65a7-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="a65a7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a65a7-105">Если вы администратор SharePoint Online, который работает с большими списками учетных записей пользователей или групп и хочет упростить управление ими, вы можете использовать PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a65a7-105">If you are a SharePoint Online administrator who works with large lists of user accounts or groups and wants an easier way to manage them, you can use PowerShell for Microsoft 365.</span></span> 

<span data-ttu-id="a65a7-106">Перед началом работы с процедурами в этом разделе необходимо подключиться к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a65a7-106">Before you begin, the procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="a65a7-107">Инструкции см. в [подключении к SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="a65a7-107">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="get-a-list-of-sites-groups-and-users"></a><span data-ttu-id="a65a7-108">Получение списков сайтов, групп и пользователей</span><span class="sxs-lookup"><span data-stu-id="a65a7-108">Get a list of sites, groups, and users</span></span>

<span data-ttu-id="a65a7-p102">Прежде чем мы начнем управлять пользователями и группами, вам необходимо получить список сайтов, групп и пользователей. Эту информацию можно использовать для работы с примером в данной статье.</span><span class="sxs-lookup"><span data-stu-id="a65a7-p102">Before we start to manage users and groups, you need to get lists of your sites, groups, and users. You can then use this information to work through the example in this article.</span></span>

<span data-ttu-id="a65a7-111">Чтобы получить список сайтов в своем клиенте, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a65a7-111">Get a list of the sites in your tenant with this command:</span></span>

```powershell
Get-SPOSite
```

<span data-ttu-id="a65a7-112">Чтобы получить список групп в своем клиенте, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a65a7-112">Get a list of the groups in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

<span data-ttu-id="a65a7-113">Чтобы получить список пользователей в своем клиенте, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a65a7-113">Get a list of the users in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a><span data-ttu-id="a65a7-114">Добавление пользователя в группу администраторов семейства веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="a65a7-114">Add a user to the Site Collection Administrators group</span></span>

<span data-ttu-id="a65a7-115">Он используется для добавления пользователя в список администраторов в `Set-SPOUser` коллекции веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="a65a7-115">You use the `Set-SPOUser` cmdlet to add a user to the list of Site Collection Administrators on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

<span data-ttu-id="a65a7-116">Чтобы использовать эти команды, замените все символы в кавычках, включая символы < и >, правильными именами.</span><span class="sxs-lookup"><span data-stu-id="a65a7-116">To use these commands, replace everything within the quotes, including the < and > characters, with the correct names.</span></span>

<span data-ttu-id="a65a7-117">Например, этот набор команд добавляет Opal Cast веб-часть (opalc имени пользователя) в список администраторов в коллекции сайтов ContosoTest в области аренды Contoso:</span><span class="sxs-lookup"><span data-stu-id="a65a7-117">For example, this set of commands adds Opal Castillo (user name opalc) to the list of Site Collection Administrators on the ContosoTest site collection in the Contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

<span data-ttu-id="a65a7-118">Вы можете скопировать и вкопировать эти команды в Блокнот, изменить значения переменных для $tenant, $site и $user на фактические значения из вашей среды, а затем в paste this into your SharePoint Online Management Shell window to run them.</span><span class="sxs-lookup"><span data-stu-id="a65a7-118">You can copy and paste these commands into Notepad, change the variable values for $tenant, $site, and $user to actual values from your environment, and then paste this into your SharePoint Online Management Shell window to run them.</span></span>

## <a name="add-a-user-to-other-site-collection-groups"></a><span data-ttu-id="a65a7-119">Добавление пользователя в другие группы в коллекции веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="a65a7-119">Add a user to other site collection groups</span></span>

<span data-ttu-id="a65a7-120">В этой задаче мы будем использовать этот cmdlet для добавления пользователя в группу `Add-SPOUser` SharePoint в коллекции веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="a65a7-120">In this task, we'll use the `Add-SPOUser` cmdlet to add a user to a SharePoint group on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

<span data-ttu-id="a65a7-121">Например, давайте добавим Пользователя Рия Рифа (пользователь с именем ольги) в группу аудиторов в коллекции веб-сайтов ContosoTest в области аренды contoso:</span><span class="sxs-lookup"><span data-stu-id="a65a7-121">For example, let's add Glen Rife (user name glenr) to the Auditors group on the ContosoTest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a><span data-ttu-id="a65a7-122">Создание группы семейства веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="a65a7-122">Create a site collection group</span></span>

<span data-ttu-id="a65a7-123">Он используется для создания новой группы SharePoint и ее добавления `New-SPOSiteGroup` в коллекцию веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="a65a7-123">You use the `New-SPOSiteGroup` cmdlet to create a new SharePoint group and add it to a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
<span data-ttu-id="a65a7-124">Свойства группы, например уровни разрешений, можно обновить позже с помощью `Set-SPOSiteGroup` этого cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a65a7-124">Group properties, such as permission levels, can be updated later by using the `Set-SPOSiteGroup` cmdlet.</span></span>

<span data-ttu-id="a65a7-125">Например, добавим группу аудиторов с разрешениями только на просмотр в коллекцию веб-сайтов contosotest в области contoso:</span><span class="sxs-lookup"><span data-stu-id="a65a7-125">For example, let's add the Auditors group with View Only permissions to the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a><span data-ttu-id="a65a7-126">Удаление пользователей из группы</span><span class="sxs-lookup"><span data-stu-id="a65a7-126">Remove users from a group</span></span>

<span data-ttu-id="a65a7-p103">Иногда необходимо удалить пользователя с сайта или даже со всех сайтов. Возможно, сотрудник переводится из одного подразделения в другое или увольняется из компании. Одного сотрудника можно легко удалить в пользовательском интерфейсе, однако не так-то просто перенести целое подразделение с одного сайта на другой.</span><span class="sxs-lookup"><span data-stu-id="a65a7-p103">Sometimes you have to remove a user from a site or even all sites. Perhaps the employee moves from one division to another or leaves the company. You can do this for one employee easily in the UI, but this is not easily done when you have to move a complete division from one site to another.</span></span>

<span data-ttu-id="a65a7-130">Однако с помощью оболочки управления SharePoint Online и CSV-файлов это быстро и просто.</span><span class="sxs-lookup"><span data-stu-id="a65a7-130">However by using the SharePoint Online Management Shell and CSV files, this is fast and easy.</span></span> <span data-ttu-id="a65a7-131">Для этой задачи вы используете Windows PowerShell, чтобы удалить пользователя из группы безопасности семейства сайтов.</span><span class="sxs-lookup"><span data-stu-id="a65a7-131">In this task, you'll use Windows PowerShell to remove a user from a site collection security group.</span></span> <span data-ttu-id="a65a7-132">Затем вы используете CSV-файл и удалите множество пользователей с разных сайтов.</span><span class="sxs-lookup"><span data-stu-id="a65a7-132">Then you'll use a CSV file and remove lots of users from different sites.</span></span> 

<span data-ttu-id="a65a7-133">С помощью командлета Remove-SPOUser мы удалим одного пользователя Microsoft 365 из группы, чтобы мы могли видеть синтаксис команды.</span><span class="sxs-lookup"><span data-stu-id="a65a7-133">We'll be using the 'Remove-SPOUser' cmdlet to remove a single Microsoft 365 user from a site collection group just so we can see the command syntax.</span></span> <span data-ttu-id="a65a7-134">Вот как выглядит синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a65a7-134">Here is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
<span data-ttu-id="a65a7-135">Например, удалим Сергея Перебоя из группы аудиторов в коллекции contosotest в области аренды contoso:</span><span class="sxs-lookup"><span data-stu-id="a65a7-135">For example, let's remove Bobby Overby from the site collection Auditors group in the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="a65a7-136">Предположим, что мы хотим удалить Bobby из всех групп, в которых он состоит.</span><span class="sxs-lookup"><span data-stu-id="a65a7-136">Suppose we wanted to remove Bobby from all the groups he is currently in.</span></span> <span data-ttu-id="a65a7-137">Вот как это сделать:</span><span class="sxs-lookup"><span data-stu-id="a65a7-137">Here is how we would do that:</span></span>

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> <span data-ttu-id="a65a7-138">Это всего лишь пример.</span><span class="sxs-lookup"><span data-stu-id="a65a7-138">This is just an example.</span></span> <span data-ttu-id="a65a7-139">Не следует выполнять эту команду, если вам действительно не требуется удалить пользователя из каждой группы, например если пользователь уволится из компании.</span><span class="sxs-lookup"><span data-stu-id="a65a7-139">You should not run this command unless you really have to remove a user from every group, for example if the user leaves the company.</span></span>

## <a name="automate-management-of-large-lists-of-users-and-groups"></a><span data-ttu-id="a65a7-140">Автоматизация управления большими списками пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="a65a7-140">Automate management of large lists of users and groups</span></span>

<span data-ttu-id="a65a7-141">Чтобы добавить большое количество учетных записей на сайты SharePoint и предоставить им разрешения, можно использовать Центр администрирования Microsoft 365, отдельные команды PowerShell или PowerShell в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="a65a7-141">To add a large number of accounts to SharePoint sites and give them permissions, you can use the Microsoft 365 admin center, individual PowerShell commands, or PowerShell an a CSV file.</span></span> <span data-ttu-id="a65a7-142">Быстрее всего эту задачу можно автоматизировать с помощью CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="a65a7-142">Of these choices, the CSV file is the fastest way to automate this task.</span></span>

<span data-ttu-id="a65a7-143">Создайте CSV-файл с заголовками (столбцами), соответствующими параметрам скрипта Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a65a7-143">The basic process is to create a CSV file that has headers (columns) that correspond to the parameters that the Windows PowerShell script needs.</span></span> <span data-ttu-id="a65a7-144">Вы можете легко создать такой список в Excel, а затем экспортировать его в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="a65a7-144">You can easily create such a list in Excel and then export it as a CSV file.</span></span> <span data-ttu-id="a65a7-145">Затем с помощью скрипта Windows PowerShell вы пройдете по всем записям (строкам) в CSV-файле, добавляя пользователей в группы и группы в сайты.</span><span class="sxs-lookup"><span data-stu-id="a65a7-145">Then, you use a Windows PowerShell script to iterate through records (rows) in the CSV file, adding the users to groups and the groups to sites.</span></span> 

<span data-ttu-id="a65a7-146">Например, создадим CSV-файл для определения группы сайтов, групп и разрешений.</span><span class="sxs-lookup"><span data-stu-id="a65a7-146">For example, let's create a CSV file to define a group of site collections, groups, and permissions.</span></span> <span data-ttu-id="a65a7-147">Затем мы создадим CSV-файл, чтобы заполнить группы пользователями.</span><span class="sxs-lookup"><span data-stu-id="a65a7-147">Next, we will create a CSV file to populate the groups with users.</span></span> <span data-ttu-id="a65a7-148">Наконец, мы создадим и выполним простой скрипт Windows PowerShell, который создает и заполняет группы.</span><span class="sxs-lookup"><span data-stu-id="a65a7-148">Finally, we will create and run a simple Windows PowerShell script that creates and populates the groups.</span></span>

<span data-ttu-id="a65a7-149">Первый CSV-файл добавляет одну или несколько групп в одно или несколько семейств сайтов. Он использует следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="a65a7-149">The first CSV file will add one or more groups to one or more site collections and will have this structure:</span></span>

<span data-ttu-id="a65a7-150">Заглавная:</span><span class="sxs-lookup"><span data-stu-id="a65a7-150">Header:</span></span>

```powershell
Site,Group,PermissionLevels
```

<span data-ttu-id="a65a7-151">Элемент:</span><span class="sxs-lookup"><span data-stu-id="a65a7-151">Item:</span></span>

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

<span data-ttu-id="a65a7-152">Ниже приведен пример файла:</span><span class="sxs-lookup"><span data-stu-id="a65a7-152">Here is an example file:</span></span>

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

<span data-ttu-id="a65a7-153">Второй CSV-файл добавляет одного или нескольких пользователей в одну или несколько групп. Он использует следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="a65a7-153">The second CSV file will add one or more users to one or more groups and will have this structure:</span></span>

<span data-ttu-id="a65a7-154">Заглавная:</span><span class="sxs-lookup"><span data-stu-id="a65a7-154">Header:</span></span>

```powershell
Group,LoginName,Site
```

<span data-ttu-id="a65a7-155">Элемент:</span><span class="sxs-lookup"><span data-stu-id="a65a7-155">Item:</span></span>

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

<span data-ttu-id="a65a7-156">Ниже приведен пример файла:</span><span class="sxs-lookup"><span data-stu-id="a65a7-156">Here is an example file:</span></span>

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

<span data-ttu-id="a65a7-157">Затем необходимо сохранить на диск два CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="a65a7-157">For the next step, you must have the two CSV files saved to your drive.</span></span> <span data-ttu-id="a65a7-158">Вот примеры команд, которые используют оба CSV-файла, а также добавляют разрешения и членство в группах:</span><span class="sxs-lookup"><span data-stu-id="a65a7-158">Here are example commands that use both CSV files and to add permissions and group membership:</span></span>

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

<span data-ttu-id="a65a7-159">Скрипт импортирует содержимое CSV-файла и использует значения в столбцах для заполнения параметров команд **New-SPOSiteGroup** и **Add-SPOUser.**</span><span class="sxs-lookup"><span data-stu-id="a65a7-159">The script imports the CSV file contents and uses the values in the columns to populate the parameters of the **New-SPOSiteGroup** and **Add-SPOUser** commands.</span></span> <span data-ttu-id="a65a7-160">В нашем примере мы сэкономим его в папкеO365Admin на диске C, но вы можете сохранить ее там, где хотите.</span><span class="sxs-lookup"><span data-stu-id="a65a7-160">In our example, we are saving this to theO365Admin folder on drive C, but you can save it wherever you want.</span></span>

<span data-ttu-id="a65a7-161">Теперь удалим группу людей для нескольких групп на разных сайтах с помощью одного CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="a65a7-161">Now, let's remove a bunch of people for several groups in different sites using the same CSV file.</span></span> <span data-ttu-id="a65a7-162">Вот пример необходимой команды:</span><span class="sxs-lookup"><span data-stu-id="a65a7-162">Here is an example command:</span></span>

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a><span data-ttu-id="a65a7-163">Создание отчетов о пользователях</span><span class="sxs-lookup"><span data-stu-id="a65a7-163">Generate user reports</span></span>

<span data-ttu-id="a65a7-p114">Возможно, вам потребуется простой отчет о пользователях нескольких сайтов, их уровне разрешений и других свойствах. Вот как выглядит синтаксис команды:</span><span class="sxs-lookup"><span data-stu-id="a65a7-p114">You might want to get a simple report for a few sites and display the users for those sites, their permission level, and other properties. This is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="a65a7-166">Команда получает данные для этих трех сайтов и записывает их в текстовый файл на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="a65a7-166">This will grab the data for these three sites and write them to a text file on your local drive.</span></span> <span data-ttu-id="a65a7-167">Обратите внимание, что параметр –Append добавляет новый контент в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="a65a7-167">Note that the parameter –Append will add new content to an existing file.</span></span>

<span data-ttu-id="a65a7-168">Например, запустим отчет на сайтах ContosoTest, TeamSite01 и Project01 клиентской организации Contoso1.</span><span class="sxs-lookup"><span data-stu-id="a65a7-168">For example, let's run a report on the ContosoTest, TeamSite01, and Project01 sites for the Contoso1 tenant:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="a65a7-169">Обратите внимание, что нам пришлось изменить только **$site** переменную.</span><span class="sxs-lookup"><span data-stu-id="a65a7-169">Note that we had to change only the **$site** variable.</span></span> <span data-ttu-id="a65a7-170">Переменная **$tenant** сохраняет свое значение во всех трех прогонах команды.</span><span class="sxs-lookup"><span data-stu-id="a65a7-170">The **$tenant** variable keeps its value through all three runs of the command.</span></span>

<span data-ttu-id="a65a7-p117">Но что делать, если вы хотите сделать это для каждого сайта? Используйте эту команду, чтобы не вводить все нужные веб-сайты:</span><span class="sxs-lookup"><span data-stu-id="a65a7-p117">However, what if you wanted to do this for every site? You can do this without having to type all those websites by using this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="a65a7-173">Это довольно простой отчет, и вы можете добавить код, чтобы создать более сложные отчеты или отчеты с более подробной информацией.</span><span class="sxs-lookup"><span data-stu-id="a65a7-173">This report is fairly simple, and you can add more code to create more specific reports or reports that include more detailed information.</span></span> <span data-ttu-id="a65a7-174">Но это должно дать вам представление о том, как использовать оболочку управления SharePoint Online для управления пользователями в среде SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a65a7-174">But this should give you an idea of how to use the SharePoint Online Management Shell to manage users in the SharePoint Online environment.</span></span>
   
## <a name="see-also"></a><span data-ttu-id="a65a7-175">См. также</span><span class="sxs-lookup"><span data-stu-id="a65a7-175">See also</span></span>

[<span data-ttu-id="a65a7-176">Подключение к PowerShell в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a65a7-176">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="a65a7-177">Управление SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a65a7-177">Manage SharePoint Online with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="a65a7-178">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a65a7-178">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a65a7-179">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a65a7-179">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
