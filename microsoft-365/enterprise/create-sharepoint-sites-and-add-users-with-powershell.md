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
description: Сводка. Использование PowerShell для создания новых сайтов SharePoint Online, а затем добавления пользователей и групп к этим сайтам.
ms.openlocfilehash: eb6c2817c8760ca222da8a7c2b14cbfcda4eb4b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907622"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="28c76-103">Создание сайтов и добавление пользователей в SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="28c76-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="28c76-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="28c76-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="28c76-105">При использовании PowerShell для Microsoft 365 для создания сайтов SharePoint Online и добавления пользователей можно быстро и многократно выполнять задачи гораздо быстрее, чем в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28c76-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="28c76-106">Вы также можете выполнять задачи, которые невозможно выполнить в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28c76-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="28c76-107">Подключение к SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="28c76-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="28c76-108">Процедуры в этом разделе требуют подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="28c76-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="28c76-109">Инструкции см. в [раздел Подключение к SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="28c76-109">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="28c76-110">Шаг 1. Создание новых коллекций сайтов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="28c76-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="28c76-111">Создайте несколько сайтов с помощью PowerShell и файла CSV, который создается с помощью предоставленного кода примера и блокнота.</span><span class="sxs-lookup"><span data-stu-id="28c76-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="28c76-112">Для этой процедуры вы замените сведения о замещающих объектах, показанных в скобках, на собственные сведения о сайте и клиентах.</span><span class="sxs-lookup"><span data-stu-id="28c76-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="28c76-113">Этот процесс позволяет создать один файл и запустить одну команду PowerShell, которая использует этот файл.</span><span class="sxs-lookup"><span data-stu-id="28c76-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="28c76-114">Это делает действия, принятые как повторяемыми, так и переносными, а также устраняет многие, если не все, ошибки, которые могут быть допущены при вводе длинных команд в командную оболочку SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="28c76-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="28c76-115">Эта процедура имеет две части.</span><span class="sxs-lookup"><span data-stu-id="28c76-115">There are two parts to this procedure.</span></span> <span data-ttu-id="28c76-116">Сначала создадим файл CSV, а затем со ссылкой на файл .csv с помощью PowerShell, который будет использовать его содержимое для создания сайтов.</span><span class="sxs-lookup"><span data-stu-id="28c76-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="28c76-117">Комлет PowerShell импортирует файл .csv и передает его в цикл внутри фигурных скобок, который читает первую строку файла в качестве столбцов.</span><span class="sxs-lookup"><span data-stu-id="28c76-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="28c76-118">Затем комлет PowerShell итерирует оставшиеся записи, создает новую коллекцию сайтов для каждой записи и назначает свойства коллекции сайтов в соответствии с заглавными колонками.</span><span class="sxs-lookup"><span data-stu-id="28c76-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="28c76-119">Создание CSV-файла</span><span class="sxs-lookup"><span data-stu-id="28c76-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="28c76-120">Параметр квоты ресурсов работает только на классических сайтах.</span><span class="sxs-lookup"><span data-stu-id="28c76-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="28c76-121">Если вы используете этот параметр на современном сайте, вы можете получить предупреждение о том, что он был обесценив.</span><span class="sxs-lookup"><span data-stu-id="28c76-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span> 

1. <span data-ttu-id="28c76-122">Откройте Блокнот и вставьте в него следующий блок текста:</span><span class="sxs-lookup"><span data-stu-id="28c76-122">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="28c76-123">Если *клиент* — это имя  клиента, а владелец — имя пользователя в клиенте, которому необходимо предоставить роль основного администратора коллекции сайтов.</span><span class="sxs-lookup"><span data-stu-id="28c76-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="28c76-124">(Вы можете нажать Ctrl+H, когда вы используете Блокнот для массовой замены быстрее.)</span><span class="sxs-lookup"><span data-stu-id="28c76-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="28c76-125">Сохраните файл на рабочем столе как **SiteCollections.csv.**</span><span class="sxs-lookup"><span data-stu-id="28c76-125">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="28c76-126">Перед использованием этого или любого другого файла скрипта csv или Windows PowerShell, это хорошая практика, чтобы убедиться, что нет никаких неопечатающих или непечатных символов.</span><span class="sxs-lookup"><span data-stu-id="28c76-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="28c76-127">Откройте файл в Word и щелкните значок абзаца на ленте, чтобы показать непечатаемые символы.</span><span class="sxs-lookup"><span data-stu-id="28c76-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="28c76-128">Файлы не должны содержать лишние непечатаемые символы.</span><span class="sxs-lookup"><span data-stu-id="28c76-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="28c76-129">Например, в конце файла не должно быть знаков абзаца.</span><span class="sxs-lookup"><span data-stu-id="28c76-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="28c76-130">Выполнение команды Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28c76-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="28c76-131">В Windows PowerShell введите или скопируйте и введите следующую команду и нажмите кнопку Ввод:</span><span class="sxs-lookup"><span data-stu-id="28c76-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="28c76-132">Где *MyAlias* равняется псевдониму пользователя.</span><span class="sxs-lookup"><span data-stu-id="28c76-132">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="28c76-p107">Дождитесь появления окна командной строки Windows PowerShell. Для этого может потребоваться одна или две минуты.</span><span class="sxs-lookup"><span data-stu-id="28c76-p107">Wait for the Windows PowerShell prompt to reappear. It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="28c76-135">В командной строке Windows PowerShell введите или скопируйте и вставьте следующий командлет, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="28c76-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="28c76-136">Обратите внимание на новые семейства веб-сайтов в списке.</span><span class="sxs-lookup"><span data-stu-id="28c76-136">Note the new site collections in the list.</span></span> <span data-ttu-id="28c76-137">С помощью нашего примера CSV-файла вы увидите следующие коллекции сайтов: **TeamSite01,** **Blog01,** **Project01** и **Community01.**</span><span class="sxs-lookup"><span data-stu-id="28c76-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="28c76-138">Вот и все.</span><span class="sxs-lookup"><span data-stu-id="28c76-138">That’s it.</span></span> <span data-ttu-id="28c76-139">Вы создали несколько коллекций сайтов с помощью созданного файла CSV и одной Windows PowerShell команды.</span><span class="sxs-lookup"><span data-stu-id="28c76-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="28c76-140">Теперь вы можете создать пользователей и назначить их сайтам.</span><span class="sxs-lookup"><span data-stu-id="28c76-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="28c76-141">Действие 2. Добавление пользователей или групп</span><span class="sxs-lookup"><span data-stu-id="28c76-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="28c76-p110">Теперь мы создадим пользователей и добавим их в группу семейства сайтов. Мы используем CSV-файл для массовой загрузки новых групп и пользователей.</span><span class="sxs-lookup"><span data-stu-id="28c76-p110">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="28c76-144">Следующие процедуры по-прежнему используют примеры сайтов TeamSite01, Blog01, Project01 и Community01.</span><span class="sxs-lookup"><span data-stu-id="28c76-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="28c76-145">Создание CSV- и PS1-файлов</span><span class="sxs-lookup"><span data-stu-id="28c76-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="28c76-146">Откройте Блокнот и вставьте в него следующий блок текста:</span><span class="sxs-lookup"><span data-stu-id="28c76-146">Open Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="28c76-147">Если *имя клиента* равно имени клиента.</span><span class="sxs-lookup"><span data-stu-id="28c76-147">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="28c76-148">Сохраните файл на рабочем столе в **GroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="28c76-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="28c76-149">Откройте новый экземпляр Блокнота и вставьте в него следующий блок текста:</span><span class="sxs-lookup"><span data-stu-id="28c76-149">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="28c76-150">Если *клиент* равен имени клиента, а имя пользователя равно имени пользователя существующего пользователя. </span><span class="sxs-lookup"><span data-stu-id="28c76-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="28c76-151">Сохраните файл на рабочем столе в **Users.csv**.</span><span class="sxs-lookup"><span data-stu-id="28c76-151">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="28c76-152">Откройте новый экземпляр Блокнота и вставьте в него следующий блок текста:</span><span class="sxs-lookup"><span data-stu-id="28c76-152">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="28c76-153">Где MyAlias равняется имени пользователя, который в настоящее время вошел в систему.</span><span class="sxs-lookup"><span data-stu-id="28c76-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="28c76-154">Сохраните файл на рабочем столе в **UsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="28c76-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="28c76-155">Это простой сценарий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28c76-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="28c76-156">Теперь вы можете выполнить скрипт UsersAndGroup.ps1, чтобы добавить пользователей и группы в несколько семейств сайтов.</span><span class="sxs-lookup"><span data-stu-id="28c76-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="28c76-157">Выполнение скрипта UsersAndGroups.ps1</span><span class="sxs-lookup"><span data-stu-id="28c76-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="28c76-158">Вернитесь в командную консоль SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="28c76-158">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="28c76-159">В командной строке Windows PowerShell введите или скопируйте и вставьте следующую строку, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="28c76-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="28c76-160">На запрос подтверждения нажмите **кнопку Y**.</span><span class="sxs-lookup"><span data-stu-id="28c76-160">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="28c76-161">В командной строке Windows PowerShell введите и или скопируйте и вставьте следующую строку, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="28c76-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="28c76-162">Где *MyAlias* равняется вашему имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="28c76-162">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="28c76-p112">Дождитесь появления окна командной строки. Сначала вы увидите группы по мере их создания. Затем вы увидите список групп, который повторяется при добавлении пользователей.</span><span class="sxs-lookup"><span data-stu-id="28c76-p112">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="28c76-166">См. также</span><span class="sxs-lookup"><span data-stu-id="28c76-166">See also</span></span>

[<span data-ttu-id="28c76-167">Подключение к PowerShell в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="28c76-167">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="28c76-168">Управление группами сайтов SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="28c76-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="28c76-169">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="28c76-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="28c76-170">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="28c76-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)