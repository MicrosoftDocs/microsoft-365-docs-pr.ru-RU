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
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="5c2fb-103">Управление группами сайтов SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c2fb-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="5c2fb-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="5c2fb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5c2fb-105">Несмотря на то что вы можете использовать центр администрирования Microsoft 365, вы также можете использовать PowerShell для Microsoft 365, чтобы управлять своими группами сайтов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5c2fb-106">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="5c2fb-106">Before you begin</span></span>

<span data-ttu-id="5c2fb-107">Процедуры, описанные в этой статье, требуют подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="5c2fb-108">Инструкции см. в статье [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="5c2fb-108">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="5c2fb-109">Просмотр SharePoint Online с помощью PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5c2fb-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="5c2fb-110">В центре администрирования SharePoint Online есть несколько простых в использовании способов управления группами сайтов.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="5c2fb-111">Например, предположим, что вы хотите просмотреть группы и членов группы для `https://litwareinc.sharepoint.com/sites/finance` сайта.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="5c2fb-112">Вот что нужно сделать:</span><span class="sxs-lookup"><span data-stu-id="5c2fb-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="5c2fb-113">В центре администрирования SharePoint щелкните **активные сайты**, а затем щелкните URL-адрес сайта.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="5c2fb-114">На странице сайт щелкните значок **Параметры** (в верхнем правом углу страницы), а затем выберите **разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="5c2fb-115">И затем повторить процесс для следующего сайта, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="5c2fb-116">Чтобы получить список групп с помощью PowerShell для Microsoft 365, можно использовать следующие команды:</span><span class="sxs-lookup"><span data-stu-id="5c2fb-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

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

<span data-ttu-id="5c2fb-117">Существует два способа выполнения этого набора команд в командной строке командной консоли SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="5c2fb-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="5c2fb-118">Скопируйте команды в Блокнот (или другой текстовый редактор), измените значение переменной **$siteURL** , выберите команды, а затем вставьте их в командную строку консоли управления SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="5c2fb-119">После этого PowerShell остановится в **>>** командной консоли.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="5c2fb-120">Нажмите клавишу ВВОД, чтобы выполнить `foreach` команду.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="5c2fb-121">Скопируйте команды в блокнот (или другой текстовый редактор), измените значение переменной **$siteURL**, а затем сохраните этот текстовый файл с именем и расширением .ps1 в подходящей папке.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="5c2fb-122">После этого запустите сценарий из командной строки командной консоли SharePoint Online, указав путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="5c2fb-123">Вот пример необходимой команды:</span><span class="sxs-lookup"><span data-stu-id="5c2fb-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="5c2fb-124">В обоих случаях должно отобразиться что-то вроде этого:</span><span class="sxs-lookup"><span data-stu-id="5c2fb-124">In both cases, you should see something similar to this:</span></span>

![Группы сайтов SharePoint Online](../media/SPO-site-groups.png)

<span data-ttu-id="5c2fb-126">Это все группы, созданные для сайта `https://litwareinc.sharepoint.com/sites/finance` , и все пользователи, назначенные этим группам.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="5c2fb-127">Имена групп обозначены желтым цветом, чтобы вы могли отличить имена групп от их участников.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="5c2fb-128">Другой пример: набор команд, в котором перечислены группы и все сведения о членстве в группах для всех сайтов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

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
    
## <a name="see-also"></a><span data-ttu-id="5c2fb-129">См. также</span><span class="sxs-lookup"><span data-stu-id="5c2fb-129">See also</span></span>

[<span data-ttu-id="5c2fb-130">Подключение к PowerShell в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5c2fb-130">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="5c2fb-131">Создание сайтов и добавление пользователей в SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c2fb-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="5c2fb-132">Управление пользователями и группами SharePoint Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c2fb-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="5c2fb-133">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c2fb-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5c2fb-134">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5c2fb-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

