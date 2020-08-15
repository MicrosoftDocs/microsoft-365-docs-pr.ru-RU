---
title: Управление группами сайтов SharePoint Online с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
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
description: В этой статье описаны процедуры использования PowerShell для Microsoft 365 для управления группами сайтов SharePoint Online.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693416"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Управление группами сайтов SharePoint Online с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Несмотря на то что вы можете использовать центр администрирования Microsoft 365, вы также можете использовать PowerShell для Microsoft 365, чтобы управлять своими группами сайтов SharePoint Online.

## <a name="before-you-begin"></a>Перед началом работы

Процедуры, описанные в этой статье, требуют подключения к SharePoint Online. Инструкции см. в статье [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Просмотр SharePoint Online с помощью PowerShell для Microsoft 365

В центре администрирования SharePoint Online есть несколько простых в использовании способов управления группами сайтов. Например, предположим, что вы хотите просмотреть группы и членов группы для `https://litwareinc.sharepoint.com/sites/finance` сайта. Вот что нужно сделать:

1. В центре администрирования SharePoint щелкните **активные сайты**, а затем щелкните URL-адрес сайта.
2. На странице сайт щелкните значок **Параметры** (в верхнем правом углу страницы), а затем выберите **разрешения для сайта**.

И затем повторить процесс для следующего сайта, который необходимо просмотреть.

Чтобы получить список групп с помощью PowerShell для Microsoft 365, можно использовать следующие команды:

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

Существует два способа выполнения этого набора команд в командной строке командной консоли SharePoint Online:

- Скопируйте команды в Блокнот (или другой текстовый редактор), измените значение переменной **$siteURL** , выберите команды, а затем вставьте их в командную строку консоли управления SharePoint Online. После этого PowerShell остановится в **>>** командной консоли. Нажмите клавишу ВВОД, чтобы выполнить `foreach` команду.<br/>
- Скопируйте команды в блокнот (или другой текстовый редактор), измените значение переменной **$siteURL**, а затем сохраните этот текстовый файл с именем и расширением .ps1 в подходящей папке. После этого запустите сценарий из командной строки командной консоли SharePoint Online, указав путь и имя файла. Вот пример необходимой команды:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

В обоих случаях должно отобразиться что-то вроде этого:

![Группы сайтов SharePoint Online](../media/SPO-site-groups.png)

Это все группы, созданные для сайта `https://litwareinc.sharepoint.com/sites/finance` , и все пользователи, назначенные этим группам. Имена групп обозначены желтым цветом, чтобы вы могли отличить имена групп от их участников.

Другой пример: набор команд, в котором перечислены группы и все сведения о членстве в группах для всех сайтов SharePoint Online.

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a>См. также

[Подключение к PowerShell в SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Создание сайтов и добавление пользователей в SharePoint Online с помощью PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Управление пользователями и группами SharePoint Online с помощью PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)

