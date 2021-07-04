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
description: Сводка. Использование PowerShell для создания SharePoint сайтов в Интернете, а затем добавления пользователей и групп на эти сайты.
ms.openlocfilehash: 0c363df3edd40d810a0d8ca63090c0fec4c1c155
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288663"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Создание сайтов и добавление пользователей в SharePoint Online с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

При использовании PowerShell для Microsoft 365 для создания веб-сайтов SharePoint Online и добавления пользователей можно быстро и многократно выполнять задачи гораздо быстрее, чем в Центр администрирования Microsoft 365. Вы также можете выполнять задачи, которые невозможно выполнить в Центр администрирования Microsoft 365.

## <a name="connect-to-sharepoint-online"></a>Подключение к SharePoint Online

Процедуры в этом разделе требуют подключения к SharePoint Online. Инструкции см. [в Подключение SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="step-1-create-new-site-collections-using-powershell"></a>Шаг 1. Создание новых коллекций сайтов с помощью PowerShell

Создайте несколько сайтов с помощью PowerShell и .csv файл, который создается с помощью предоставленного кода примера и Блокнот. Для этой процедуры вы замените сведения о замещающих объектах, показанных в скобках, на собственные сведения о сайте и клиентах. Этот процесс позволяет создать один файл и запустить одну команду PowerShell, которая использует этот файл. Это делает действия, принятые как повторяемыми, так и переносными, и устраняет многие, если не все, ошибки, которые могут быть допущены при вводе длинных команд в SharePoint Online Management Shell. Эта процедура имеет две части. Сначала вы создайте файл .csv, а затем вы будете ссылаться на .csv файл с помощью PowerShell, который будет использовать его содержимое для создания сайтов.

Комлет PowerShell импортирует файл .csv и передает его в цикл внутри фигурных скобок, который читает первую строку файла в качестве столбцов. Затем комлет PowerShell итерирует оставшиеся записи, создает новую коллекцию сайтов для каждой записи и назначает свойства коллекции сайтов в соответствии с заглавными колонками.

### <a name="create-a-csv-file"></a>Создание CSV-файла

> [!NOTE]
> Параметр квоты ресурсов работает только на классических сайтах. Если вы используете этот параметр на современном сайте, вы можете получить предупреждение о том, что он был обесценив.

1. Откройте Блокнот и вставьте в него следующий блок текста:

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   Если *клиент* — это имя  клиента, а владелец — имя пользователя в клиенте, которому необходимо предоставить роль основного администратора коллекции сайтов.

   (Вы можете нажать Ctrl+H при использовании Блокнот для массовой замены быстрее.)

2. Сохраните файл на рабочем столе как **SiteCollections.csv.**

> [!TIP]
> Прежде чем использовать этот или .csv или Windows PowerShell файл скрипта, необходимо убедиться в том, что не существует неопечатаемых или непечатных символов. Откройте файл в Word и щелкните значок абзаца на ленте, чтобы показать непечатаемые символы. Файлы не должны содержать лишние непечатаемые символы. Например, в конце файла не должно быть знаков абзаца.

### <a name="run-the-windows-powershell-command"></a>Выполнение команды Windows PowerShell

1. В Windows PowerShell введите или скопируйте и введите следующую команду и нажмите кнопку Ввод:

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   Где *MyAlias* равняется псевдониму пользователя.

2. Дождитесь появления окна командной строки Windows PowerShell. Для этого может потребоваться одна или две минуты.

3. В командной строке Windows PowerShell введите или скопируйте и вставьте следующий командлет, а затем нажмите клавишу ВВОД:

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. Обратите внимание на новые семейства веб-сайтов в списке. С помощью нашего примера CSV-файла вы увидите следующие коллекции сайтов: **TeamSite01,** **Blog01,** **Project01** и **Community01.**

Вот и все. Вы создали несколько коллекций сайтов с .csv созданным файлом и одной Windows PowerShell командой. Теперь вы можете создать пользователей и назначить их сайтам.

## <a name="step-2-add-users-and-groups"></a>Действие 2. Добавление пользователей или групп

Теперь мы создадим пользователей и добавим их в группу семейства сайтов. Мы используем CSV-файл для массовой загрузки новых групп и пользователей.

Следующие процедуры по-прежнему используют примеры сайтов TeamSite01, Blog01, Project01 и Community01.

### <a name="create-csv-and-ps1-files"></a>Создание CSV- и PS1-файлов

1. Откройте Блокнот и вставьте в него следующий блок текста:

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

   Если *имя клиента* равно имени клиента.

2. Сохраните файл на рабочем столе в **GroupsAndPermissions.csv**.

3. Откройте новый экземпляр Блокнота и вставьте в него следующий блок текста:

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

   Если *клиент* равен имени клиента, а имя пользователя равно имени пользователя существующего пользователя. 

4. Сохраните файл на рабочем столе в **Users.csv**.

5. Откройте новый экземпляр Блокнота и вставьте в него следующий блок текста:

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   Где MyAlias равняется имени пользователя, который в настоящее время вошел в систему.

6. Сохраните файл на рабочем столе в **UsersAndGroups.ps1**. Это простой сценарий Windows PowerShell.

Теперь вы можете выполнить скрипт UsersAndGroup.ps1, чтобы добавить пользователей и группы в несколько семейств сайтов.

### <a name="run-usersandgroupsps1-script"></a>Выполнение скрипта UsersAndGroups.ps1

1. Вернитесь в командную консоль SharePoint Online.

2. В командной строке Windows PowerShell введите или скопируйте и вставьте следующую строку, а затем нажмите клавишу ВВОД:

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. На запрос подтверждения нажмите **кнопку Y**.

4. В командной строке Windows PowerShell введите и или скопируйте и вставьте следующую строку, а затем нажмите клавишу ВВОД:

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   Где *MyAlias* равняется вашему имени пользователя.

5. Дождитесь появления окна командной строки. Сначала вы увидите группы по мере их создания. Затем вы увидите список групп, который повторяется при добавлении пользователей.

## <a name="see-also"></a>См. также

[Подключение к PowerShell в SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[Управление группами сайтов SharePoint Online с помощью PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
