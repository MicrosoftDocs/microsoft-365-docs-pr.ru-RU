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
description: В этой статье узнайте, как использовать PowerShell для Microsoft 365 для управления пользователями, группами и сайтами SharePoint Online.
ms.openlocfilehash: cc977355f1182b18d2f2e90b573683ed69299c1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916730"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Управление пользователями и группами SharePoint Online с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Если вы администратор SharePoint Online, который работает с большими списками учетных записей пользователей или групп и хочет упростить управление ими, вы можете использовать PowerShell для Microsoft 365. 

Прежде чем приступить к этой теме, необходимо подключиться к SharePoint Online. Инструкции см. в [раздел Подключение к SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

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

Этот список используется для добавления пользователя в список администраторов коллекций сайтов в `Set-SPOUser` коллекции веб-сайтов.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Чтобы использовать эти команды, замените все в кавычках, включая < и >, правильными именами.

Например, этот набор команд добавляет Opal Castillo (имя пользователя opalc) в список администраторов коллекции сайтов в коллекции сайтов ContosoTest в аренде Contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

Можно скопировать и вклеить эти команды в блокнот, изменить переменные значения для $tenant, $site и $user фактических значений из среды, а затем вклеить их в окно sharePoint Online Management Shell для их запуска.

## <a name="add-a-user-to-other-site-collection-groups"></a>Добавление пользователя в другие группы коллекций сайтов

В этой задаче мы будем использовать этот комлет, чтобы добавить пользователя в группу `Add-SPOUser` SharePoint в коллекцию сайтов.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Например, давайте добавим Глена Рифа (гленра имени пользователя) в группу аудиторов в коллекции сайтов ContosoTest в аренде contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Создание группы семейства веб-сайтов

Этот комлет используется для создания новой группы SharePoint и добавления `New-SPOSiteGroup` его в коллекцию сайтов.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
Свойства группы, например уровни разрешений, могут обновляться позже с помощью `Set-SPOSiteGroup` cmdlet.

Например, давайте добавим группу аудиторов с разрешениями View Only в коллекцию сайтов contosotest в аренде contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Удаление пользователей из группы

Иногда необходимо удалить пользователя с сайта или даже со всех сайтов. Возможно, сотрудник переводится из одного подразделения в другое или увольняется из компании. Одного сотрудника можно легко удалить в пользовательском интерфейсе, однако не так-то просто перенести целое подразделение с одного сайта на другой.

Однако с помощью файлов управления SharePoint Online и CSV это быстро и просто. Для этой задачи вы используете Windows PowerShell, чтобы удалить пользователя из группы безопасности семейства сайтов. Затем вы используете CSV-файл и удалите множество пользователей с разных сайтов. 

Мы будем использовать командлет "Remove-SPOUser", чтобы удалить одного пользователя Microsoft 365 из группы коллекций сайтов только для того, чтобы мы могли увидеть синтаксис команды. Вот как выглядит синтаксис:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
Например, давайте удалим Бобби Оберби из группы аудиторов коллекции веб-сайтов в коллекции сайтов contosotest в аренде contoso:

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
> Это только пример. Не следует выполнять эту команду, если вам действительно не требуется удалить пользователя из каждой группы, например если пользователь уволится из компании.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Автоматизация управления большими списками пользователей и групп

Чтобы добавить большое количество учетных записей на сайты SharePoint и дать им разрешения, можно использовать центр администрирования Microsoft 365, отдельные команды PowerShell или файл CSV PowerShell. Быстрее всего эту задачу можно автоматизировать с помощью CSV-файла.

Создайте CSV-файл с заголовками (столбцами), соответствующими параметрам скрипта Windows PowerShell. Вы можете легко создать такой список в Excel и экспортировать его в качестве CSV-файла. Затем с помощью скрипта Windows PowerShell вы пройдете по всем записям (строкам) в CSV-файле, добавляя пользователей в группы и группы в сайты. 

Например, создадим CSV-файл, чтобы определить группу коллекций сайтов, групп и разрешений. Затем мы создадим CSV-файл, чтобы заполнить группы пользователями. Наконец, мы создадим и выполним простой скрипт Windows PowerShell, который создает и заполняет группы.

Первый CSV-файл добавляет одну или несколько групп в одно или несколько семейств сайтов. Он использует следующую структуру:

Заглавная:

```powershell
Site,Group,PermissionLevels
```

Элемент:

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

Заглавная:

```powershell
Group,LoginName,Site
```

Элемент:

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

Затем необходимо сохранить на диск два CSV-файла. Вот примеры команд, которые используют как CSV-файлы, так и для добавления разрешений и членства в группе:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Скрипт импортирует содержимое файла CSV и использует значения в столбцах для заполнения параметров команд **New-SPOSiteGroup** и **Add-SPOUser.** В нашем примере мы сэкономим это в папкеO365Admin на диске C, но вы можете сохранить ее там, где хотите.

Теперь давайте удалим группу людей для нескольких групп на разных сайтах с помощью одного и того же CSV-файла. Вот пример необходимой команды:

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

Обратите внимание, что нам пришлось изменить только **$site** переменную. Переменная **$tenant** сохраняет свое значение во всех трех забегах команды.

Но что делать, если вы хотите сделать это для каждого сайта? Используйте эту команду, чтобы не вводить все нужные веб-сайты:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Это довольно простой отчет, и вы можете добавить код, чтобы создать более сложные отчеты или отчеты с более подробной информацией. Но это должно дать представление о том, как использовать оболочку управления SharePoint Online для управления пользователями в среде SharePoint Online.
   
## <a name="see-also"></a>См. также

[Подключение к PowerShell в SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Управление SharePoint Online с помощью PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)