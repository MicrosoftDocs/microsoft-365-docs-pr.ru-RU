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
description: Сводка. Используйте PowerShell для создания новых сайтов SharePoint Online, а затем добавления пользователей и групп на эти сайты.
ms.openlocfilehash: 28a51cc39fe838f6c7f9c50e9d750d28e5d830c4
ms.sourcegitcommit: 24ccb910ffac4d065c512a57c5decd9dd19ef4c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594922"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Создание сайтов и добавление пользователей в SharePoint Online с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

При использовании PowerShell для Microsoft 365 для создания сайтов SharePoint Online и добавления пользователей можно быстро и многократно выполнять задачи гораздо быстрее, чем в Центре администрирования Microsoft 365. Вы также можете выполнять задачи, которые невозможно выполнить в Центре администрирования Microsoft 365. 

## <a name="connect-to-sharepoint-online"></a>Подключение к SharePoint Online

Процедуры в этом разделе требуют подключения к SharePoint Online. Инструкции см. в [подключении к SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="step-1-create-new-site-collections-using-powershell"></a>Шаг 1. Создание новых коллекций веб-сайтов с помощью PowerShell

Создайте несколько сайтов с помощью PowerShell и CSV-файла, который вы создаете с помощью предоставленного примера кода и Блокнота. Для этой процедуры необходимо заменить информацию-замещатель, показанную в скобках, на собственные сведения о сайте и клиенте. Этот процесс позволяет создать один файл и выполнить одну команду PowerShell, которая использует этот файл. Это делает действия повторяемыми и переносимыми, а также устраняет многие (если не все) ошибки, которые могут привести к вводу длинных команд в командной оболочке SharePoint Online. Эта процедура имеет две части. Сначала создадим CSV-файл, а затем соберем ссылку на CSV-файл с помощью PowerShell, который будет использовать его содержимое для создания сайтов.

Этот CSV-файл импортируется и передается в цикл в фигурных скобках, который считывает первую строку файла в качестве колонок столбцов. После этого с помощью cmdlet PowerShell можно итерировать оставшиеся записи, создать новое коллекцию веб-сайтов для каждой записи и назначить свойства этого сайта в соответствии с заглавными колонами столбцов.

### <a name="create-a-csv-file"></a>Создание CSV-файла

> [!NOTE]
> Параметр квоты ресурсов работает только на классических сайтах. При использовании этого параметра на современном сайте может появиться предупреждение о том, что он является неподготовленным. 

1. Откройте Блокнот и вставьте в него следующий блок текста:<br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/>Где *клиент* — это имя  клиента, а владелец — это имя пользователя в клиенте, которому вы хотите предоставить роль основного администратора.<br/>(Вы можете нажать CTRL+H, если вы используете Блокнот для массовой замены быстрее.)<br/>

2. Сохраните файл на рабочем столе как **SiteCollections.csv.**<br/>

> [!TIP]
> Перед использованием этого или любого другого CSV-или Windows PowerShell-файла сценария лучше убедиться, что нет лишних или непечатающих символов. Откройте файл в Word и щелкните значок абзаца на ленте, чтобы показать непечатаемые символы. Файлы не должны содержать лишние непечатаемые символы. Например, в конце файла не должно быть знаков абзаца.

### <a name="run-the-windows-powershell-command"></a>Выполнение команды Windows PowerShell

1. В командной Windows PowerShell введите (или скопируйте и введите) следующую команду и нажмите ввод:<br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/>Где *MyAlias* равно псевдониму пользователя.<br/>

2. Дождитесь появления окна командной строки Windows PowerShell. Для этого может потребоваться одна или две минуты.<br/>

3. В командной строке Windows PowerShell введите или скопируйте и вставьте следующий командлет, а затем нажмите клавишу ВВОД:<br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. Обратите внимание на новые семейства веб-сайтов в списке. Используя наш пример CSV-файла, вы увидите следующие коллекции веб-сайтов: **TeamSite01,** **Blog01,** **Project01** и **Community01**

Вот и все. Вы создали несколько коллекций веб-сайтов с помощью созданного CSV-файла и одной Windows PowerShell команды. Теперь вы можете создать пользователей и назначить их сайтам.

## <a name="step-2-add-users-and-groups"></a>Действие 2. Добавление пользователей или групп

Теперь мы создадим пользователей и добавим их в группу семейства сайтов. Мы используем CSV-файл для массовой загрузки новых групп и пользователей.

В следующих процедурах по-прежнему используется пример сайтов TeamSite01, Blog01, Project01 и Community01.

### <a name="create-csv-and-ps1-files"></a>Создание CSV- и PS1-файлов

1. Откройте Блокнот и вставьте в него следующий блок текста:<br/>

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
<br/>Где *клиент* равно вашему имени клиента.<br/>

2. Сохраните файл на рабочем столе как **GroupsAndPermissions.csv.**<br/>

3. Откройте новый экземпляр Блокнота и вставьте в него следующий блок текста:<br/>

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
<br/>Если *клиент* равен вашему имени клиента, а *имя* пользователя равно имени пользователя существующего пользователя.<br/>

4. Сохраните файл на рабочем столе как **Users.csv.**<br/>

5. Откройте новый экземпляр Блокнота и вставьте в него следующий блок текста:<br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/>Где MyAlias равно имени пользователя, который в данный момент вошел в систему.<br/>

6. Сохраните файл на рабочем столе как **UsersAndGroups.ps1.** Это простой сценарий Windows PowerShell.

Теперь вы можете выполнить скрипт UsersAndGroup.ps1, чтобы добавить пользователей и группы в несколько семейств сайтов.

### <a name="run-usersandgroupsps1-script"></a>Выполнение скрипта UsersAndGroups.ps1

1. Вернитесь в командную консоль SharePoint Online.<br/>
2. В командной строке Windows PowerShell введите или скопируйте и вставьте следующую строку, а затем нажмите клавишу ВВОД:<br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. В запросе на подтверждение нажмите **Y.**<br/>

4. В командной строке Windows PowerShell введите и или скопируйте и вставьте следующую строку, а затем нажмите клавишу ВВОД:<br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/>Где *MyAlias* равно вашему имени пользователя.<br/>

5. Дождитесь появления окна командной строки. Сначала вы увидите группы по мере их создания. Затем вы увидите список групп, который повторяется при добавлении пользователей.

## <a name="see-also"></a>См. также

[Подключение к PowerShell в SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Управление группами сайтов SharePoint Online с помощью PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
