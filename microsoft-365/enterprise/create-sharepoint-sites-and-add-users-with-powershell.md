---
title: Создание сайтов и добавление пользователей в SharePoint Online с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Сводка. Используйте PowerShell для создания сайтов SharePoint Online и добавления пользователей и групп на эти сайты.
ms.openlocfilehash: 4c4edbd68343f0eaf3a25a8c60a2af1e83b058b6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693111"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="3c25a-103">Создание сайтов и добавление пользователей в SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c25a-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="3c25a-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="3c25a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3c25a-105">При использовании PowerShell для Microsoft 365 для создания сайтов SharePoint Online и добавления пользователей можно быстро и многократно выполнять задачи в центре администрирования Майкрософт 365 быстрее и многократно.</span><span class="sxs-lookup"><span data-stu-id="3c25a-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3c25a-106">Вы также можете выполнять задачи, которые невозможно выполнить в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3c25a-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="3c25a-107">Подключение к SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3c25a-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="3c25a-108">Процедуры, описанные в этом разделе, требуют подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3c25a-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="3c25a-109">Инструкции см в разделе [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="3c25a-109">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="3c25a-110">Шаг 1: создание новых семейств веб-сайтов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c25a-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="3c25a-111">Создайте несколько сайтов с помощью PowerShell и CSV-файла, который создается с помощью предоставленного примера кода и блокнота.</span><span class="sxs-lookup"><span data-stu-id="3c25a-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="3c25a-112">В этой процедуре заменяются сведения о заполнителе, показанные в квадратных скобках, с собственными сведениями о сайтах и клиентах.</span><span class="sxs-lookup"><span data-stu-id="3c25a-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="3c25a-113">Этот процесс позволяет создать один файл и выполнить одну команду PowerShell, использующую этот файл.</span><span class="sxs-lookup"><span data-stu-id="3c25a-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="3c25a-114">Это делает действия, которые были как повторяющимися, так и переносимыми, и исключает многие, если не все, ошибки, которые могут возникнуть при вводе длинных команд в командную консоль SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3c25a-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="3c25a-115">Эта процедура состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="3c25a-115">There are two parts to this procedure.</span></span> <span data-ttu-id="3c25a-116">Сначала вы создадите CSV-файл, а затем сослаться на этот CSV-файл с помощью PowerShell, который будет использовать его содержимое для создания сайтов.</span><span class="sxs-lookup"><span data-stu-id="3c25a-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="3c25a-117">Командлет PowerShell импортирует CSV-файл и передает его в цикл в фигурных скобках, который считывает первую строку файла в виде заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="3c25a-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="3c25a-118">Затем командлет PowerShell выполняет итерацию по оставшимся записям, создает новое семейство сайтов для каждой записи и присваивает свойствам семейства веб-сайтов в соответствии с заголовками столбцов.</span><span class="sxs-lookup"><span data-stu-id="3c25a-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="3c25a-119">Создание CSV-файла</span><span class="sxs-lookup"><span data-stu-id="3c25a-119">Create a .csv file</span></span>

1. <span data-ttu-id="3c25a-120">Откройте Блокнот и вставьте в него следующий блок текста:</span><span class="sxs-lookup"><span data-stu-id="3c25a-120">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="3c25a-121">Где *клиент* — это имя вашего клиента, а *owner* — это имя пользователя в клиенте, которому требуется предоставить роль главного администратора семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="3c25a-121">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="3c25a-122">(Можно нажать клавиши CTRL + H при использовании блокнота для ускорения массового замещения.)</span><span class="sxs-lookup"><span data-stu-id="3c25a-122">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="3c25a-123">Сохраните файл на рабочем столе как **SiteCollections.csv**.</span><span class="sxs-lookup"><span data-stu-id="3c25a-123">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="3c25a-124">Перед использованием этого или другого файла сценария. CSV или Windows PowerShell рекомендуется убедиться в отсутствии лишних или непечатаемых символов.</span><span class="sxs-lookup"><span data-stu-id="3c25a-124">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="3c25a-125">Откройте файл в Word и щелкните значок абзаца на ленте, чтобы показать непечатаемые символы.</span><span class="sxs-lookup"><span data-stu-id="3c25a-125">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="3c25a-126">Файлы не должны содержать лишние непечатаемые символы.</span><span class="sxs-lookup"><span data-stu-id="3c25a-126">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="3c25a-127">Например, в конце файла не должно быть знаков абзаца.</span><span class="sxs-lookup"><span data-stu-id="3c25a-127">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="3c25a-128">Выполнение команды Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c25a-128">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="3c25a-129">В командной консоли Windows PowerShell введите (или скопируйте и вставьте) следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="3c25a-129">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="3c25a-130">Где *мялиас* соответствует псевдониму пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c25a-130">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="3c25a-p106">Дождитесь появления окна командной строки Windows PowerShell. Для этого может потребоваться одна или две минуты.</span><span class="sxs-lookup"><span data-stu-id="3c25a-p106">Wait for the Windows PowerShell prompt to reappear. It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="3c25a-133">В командной строке Windows PowerShell введите или скопируйте и вставьте следующий командлет, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="3c25a-133">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="3c25a-134">Обратите внимание на новые семейства веб-сайтов в списке.</span><span class="sxs-lookup"><span data-stu-id="3c25a-134">Note the new site collections in the list.</span></span> <span data-ttu-id="3c25a-135">Используя наш пример CSV-файла, вы увидите следующие семейства веб-сайтов: **TeamSite01**, **Blog01**, **Project01**и **Community01**</span><span class="sxs-lookup"><span data-stu-id="3c25a-135">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="3c25a-136">Вот и все.</span><span class="sxs-lookup"><span data-stu-id="3c25a-136">That’s it.</span></span> <span data-ttu-id="3c25a-137">Вы создали несколько семейств веб-сайтов с помощью созданного CSV-файла и одной команды Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c25a-137">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="3c25a-138">Теперь вы можете создать пользователей и назначить их сайтам.</span><span class="sxs-lookup"><span data-stu-id="3c25a-138">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="3c25a-139">Действие 2. Добавление пользователей или групп</span><span class="sxs-lookup"><span data-stu-id="3c25a-139">Step 2: Add users and groups</span></span>

<span data-ttu-id="3c25a-p109">Теперь мы создадим пользователей и добавим их в группу семейства сайтов. Мы используем CSV-файл для массовой загрузки новых групп и пользователей.</span><span class="sxs-lookup"><span data-stu-id="3c25a-p109">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="3c25a-142">Следующие процедуры продолжают использовать примеры сайтов TeamSite01, Blog01, Project01 и Community01.</span><span class="sxs-lookup"><span data-stu-id="3c25a-142">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="3c25a-143">Создание CSV- и PS1-файлов</span><span class="sxs-lookup"><span data-stu-id="3c25a-143">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="3c25a-144">Откройте Блокнот и вставьте в него следующий блок текста:</span><span class="sxs-lookup"><span data-stu-id="3c25a-144">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/><span data-ttu-id="3c25a-145">Где *клиент* равняется имени клиента.</span><span class="sxs-lookup"><span data-stu-id="3c25a-145">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="3c25a-146">Сохраните файл на рабочем столе как **GroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="3c25a-146">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="3c25a-147">Откройте новый экземпляр Блокнота и вставьте в него следующий блок текста:</span><span class="sxs-lookup"><span data-stu-id="3c25a-147">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/><span data-ttu-id="3c25a-148">Где *клиент* равняется имени клиента, а *username* — имя пользователя существующего пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c25a-148">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="3c25a-149">Сохраните файл на рабочем столе как **Users.csv**.</span><span class="sxs-lookup"><span data-stu-id="3c25a-149">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="3c25a-150">Откройте новый экземпляр Блокнота и вставьте в него следующий блок текста:</span><span class="sxs-lookup"><span data-stu-id="3c25a-150">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="3c25a-151">Где Мялиас = имя пользователя, выполнившего вход в систему.</span><span class="sxs-lookup"><span data-stu-id="3c25a-151">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="3c25a-152">Сохраните файл на рабочем столе как **UsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="3c25a-152">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="3c25a-153">Это простой сценарий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c25a-153">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="3c25a-154">Теперь вы можете выполнить скрипт UsersAndGroup.ps1, чтобы добавить пользователей и группы в несколько семейств сайтов.</span><span class="sxs-lookup"><span data-stu-id="3c25a-154">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="3c25a-155">Выполнение скрипта UsersAndGroups.ps1</span><span class="sxs-lookup"><span data-stu-id="3c25a-155">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="3c25a-156">Вернитесь в командную консоль SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3c25a-156">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="3c25a-157">В командной строке Windows PowerShell введите или скопируйте и вставьте следующую строку, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="3c25a-157">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="3c25a-158">В запросе подтверждения нажмите **Y**.</span><span class="sxs-lookup"><span data-stu-id="3c25a-158">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="3c25a-159">В командной строке Windows PowerShell введите и или скопируйте и вставьте следующую строку, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="3c25a-159">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="3c25a-160">Где *мялиас* = ваше имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c25a-160">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="3c25a-p111">Дождитесь появления окна командной строки. Сначала вы увидите группы по мере их создания. Затем вы увидите список групп, который повторяется при добавлении пользователей.</span><span class="sxs-lookup"><span data-stu-id="3c25a-p111">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c25a-164">См. также</span><span class="sxs-lookup"><span data-stu-id="3c25a-164">See also</span></span>

[<span data-ttu-id="3c25a-165">Подключение к PowerShell в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3c25a-165">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="3c25a-166">Управление группами сайтов SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c25a-166">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="3c25a-167">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c25a-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3c25a-168">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c25a-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

