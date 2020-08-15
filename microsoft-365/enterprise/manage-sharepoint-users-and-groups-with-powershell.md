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
description: В этой статье рассказывается, как использовать PowerShell для Microsoft 365 для управления пользователями, группами и сайтами SharePoint Online.
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693413"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Управление пользователями и группами SharePoint Online с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Если вы являетесь администратором SharePoint Online, который работает с большими списками учетных записей пользователей или групп и хотите упростить управление ими, вы можете использовать PowerShell для Microsoft 365. 

Прежде чем приступать к работе, процедуры, описанные в этом разделе, требуют подключения к SharePoint Online. Инструкции см в разделе [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="get-a-list-of-sites-groups-and-users"></a>Получение списков сайтов, групп и пользователей

Прежде чем мы начнем управлять пользователями и группами, вам необходимо получить список сайтов, групп и пользователей. Эту информацию можно использовать для работы с примером в данной статье.

Чтобы получить список сайтов в своем клиенте, выполните следующую команду:

```powershell
Get-SPOSite
```

Чтобы получить список групп в своем клиенте, выполните следующую команду:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

Чтобы получить список пользователей в своем клиенте, выполните следующую команду:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Добавление пользователя в группу администраторов семейства веб-сайтов

Используйте командлет, `Set-SPOUser` чтобы добавить пользователя в список администраторов семейства веб-сайтов в семействе веб-сайтов.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Чтобы использовать эти команды, замените все в кавычках, включая < и > символы, указав правильные имена.

Например, этот набор команд добавляет Кастилло Opalis (имя пользователя opalc) в список администраторов семейства веб-сайтов в семействе веб-сайтов ContosoTest в клиенте Contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

Вы можете скопировать и вставить эти команды в блокнот, изменить значения переменных для $tenant, $site и $user на фактические значения из вашей среды, а затем вставить их в окно командной консоли SharePoint Online для их запуска.

## <a name="add-a-user-to-other-site-collection-groups"></a>Добавление пользователя в другие группы семейств веб-сайтов

В этой задаче мы будем использовать `Add-SPOUser` командлет, чтобы добавить пользователя в группу SharePoint в семействе веб-сайтов.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Например, добавим Glen Rife (имя пользователя "glenr") в группу аудиторий в семействе веб-сайтов ContosoTest в компании Contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Создание группы семейства веб-сайтов

`New-SPOSiteGroup`Командлет используется для создания новой группы SharePoint и ее добавления в семейство веб-сайтов.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
Свойства групп, такие как уровни разрешений, можно обновлять позже с помощью `Set-SPOSiteGroup` командлета.

Например, добавим группу аудиторий с разрешениями "Просмотр только для просмотра" в семействе веб-сайтов ContosoTest в клиенте Contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Удаление пользователей из группы

Иногда необходимо удалить пользователя с сайта или даже со всех сайтов. Возможно, сотрудник переводится из одного подразделения в другое или увольняется из компании. Одного сотрудника можно легко удалить в пользовательском интерфейсе, однако не так-то просто перенести целое подразделение с одного сайта на другой.

Однако с помощью командной консоли SharePoint Online и CSV-файлов это быстро и легко. Для этой задачи вы используете Windows PowerShell, чтобы удалить пользователя из группы безопасности семейства сайтов. Затем вы используете CSV-файл и удалите множество пользователей с разных сайтов. 

Мы будем использовать командлет "Remove-супруг" для удаления одного пользователя Microsoft 365 из группы семейств веб-сайтов, так как мы можем увидеть синтаксис команды. Вот как выглядит синтаксис:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
Например, давайте удалим Бобби Оверби из группы аудиторий семейства веб-сайтов в семействе веб-сайтов ContosoTest в клиенте Contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Предположим, что мы хотим удалить Bobby из всех групп, в которых он состоит. Вот как это сделать:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Это всего лишь пример. Не следует выполнять эту команду, если вам действительно не требуется удалить пользователя из каждой группы, например если пользователь уволится из компании.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Автоматизация управления большими списками пользователей и групп

Для добавления большого количества учетных записей на сайты SharePoint и предоставления им разрешений можно использовать центр администрирования Microsoft 365, отдельные команды PowerShell или файл CSV. Быстрее всего эту задачу можно автоматизировать с помощью CSV-файла.

Создайте CSV-файл с заголовками (столбцами), соответствующими параметрам скрипта Windows PowerShell. Такой список можно легко создать в Excel, а затем экспортировать в виде CSV-файла. Затем с помощью скрипта Windows PowerShell вы пройдете по всем записям (строкам) в CSV-файле, добавляя пользователей в группы и группы в сайты. 

Например, создадим CSV-файл, чтобы определить группу семейств веб-сайтов, групп и разрешений. Затем мы создадим CSV-файл, чтобы заполнить группы пользователями. Наконец, мы создадим и выполним простой скрипт Windows PowerShell, который создает и заполняет группы.

Первый CSV-файл добавляет одну или несколько групп в одно или несколько семейств сайтов. Он использует следующую структуру:

Верхний

```powershell
Site,Group,PermissionLevels
```

Элемента

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

Ниже приведен пример файла:

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

Второй CSV-файл добавляет одного или нескольких пользователей в одну или несколько групп. Он использует следующую структуру:

Верхний

```powershell
Group,LoginName,Site
```

Элемента

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

Ниже приведен пример файла:

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

Затем необходимо сохранить на диск два CSV-файла. Ниже приведены примеры команд, использующих как CSV-файлы, так и добавления разрешений и членства в группах.

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Сценарий импортирует содержимое CSV-файла и использует значения в столбцах для заполнения параметров команд **New-SPOSiteGroup** и **Add-супруг** . В нашем примере мы сохраняем это в папке theO365Admin на диске C, но вы можете сохранить ее там, где бы вы ни находились.

Теперь удалим группу людей для нескольких групп на разных сайтах, используя один и тот же CSV-файл. Вот пример необходимой команды:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Создание отчетов о пользователях

Возможно, вам потребуется простой отчет о пользователях нескольких сайтов, их уровне разрешений и других свойствах. Вот как выглядит синтаксис команды:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Команда получает данные для этих трех сайтов и записывает их в текстовый файл на локальном диске. Обратите внимание, что параметр –Append добавляет новый контент в существующий файл.

Например, запустим отчет на сайтах ContosoTest, TeamSite01 и Project01 клиентской организации Contoso1.

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Обратите внимание, что нам пришлось изменить только переменную **$site** . Переменная **$tenant** сохраняет свое значение по всем трем запускам команды.

Но что делать, если вы хотите сделать это для каждого сайта? Используйте эту команду, чтобы не вводить все нужные веб-сайты:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Это довольно простой отчет, и вы можете добавить код, чтобы создать более сложные отчеты или отчеты с более подробной информацией. Однако в этом случае необходимо понять, как использовать командную консоль SharePoint Online для управления пользователями в среде SharePoint Online.
   
## <a name="see-also"></a>См. также

[Подключение к PowerShell в SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Управление SharePoint Online с помощью PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
