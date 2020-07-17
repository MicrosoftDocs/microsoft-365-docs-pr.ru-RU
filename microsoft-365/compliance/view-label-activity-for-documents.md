---
title: Просмотр действий с метками для документов
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Узнайте, как использовать Обозреватель действий с метками в Центре безопасности и соответствия требованиям Microsoft 365 для поиска и просмотра действий с метками.
ms.openlocfilehash: e21bb867044b2a6644b125aad9983ce3518f70ee
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127276"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="1f754-103">Просмотр действий с метками для документов</span><span class="sxs-lookup"><span data-stu-id="1f754-103">View label activity for documents</span></span>

<span data-ttu-id="1f754-p101">После создания меток вам нужно убедиться, что они надлежащим образом применяются к контенту. При помощи обозревателя действий с метками в Центре безопасности и соответствия требованиям вы можете быстро искать и просматривать весь контент в SharePoint и OneDrive для бизнеса за последние 30 дней. Эти данные обновляются в реальном времени, давая вам хорошее представление о том, что происходит в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="1f754-p101">After you create your labels, you'll want to verify that they're being applied to content as you intended. With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="1f754-107">Например, при помощи обозревателя действий с метками вы можете:</span><span class="sxs-lookup"><span data-stu-id="1f754-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="1f754-108">Просматривать, сколько раз каждая метка применялась в тот или иной день (до 30 дней).</span><span class="sxs-lookup"><span data-stu-id="1f754-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="1f754-109">Узнавать, кто и когда помечал какие файлы, и получать ссылки на сайты, где они хранятся.</span><span class="sxs-lookup"><span data-stu-id="1f754-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="1f754-110">Определять, метки каких файлов были изменены или удалены, просматривать старые и новые метки, а также узнавать, кто внес изменение.</span><span class="sxs-lookup"><span data-stu-id="1f754-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="1f754-p102">Фильтровать данные, чтобы просматривать действия с метками для определенных меток, файлов или пользователей. Вы также можете фильтровать действия с метками по расположению (SharePoint или OneDrive для бизнеса) и способу применения метки (вручную или автоматически).</span><span class="sxs-lookup"><span data-stu-id="1f754-p102">Filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="1f754-p103">Просматривать действия с метками для папок, а также отдельных документов. В скором времени появится возможность просматривать количество файлов в той или иной папке, помеченных в результате применения метки к этой папке.</span><span class="sxs-lookup"><span data-stu-id="1f754-p103">View label activity for folders as well as individual documents. Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="1f754-115">Обозреватель действий с метками можно открыть из Центра безопасности &amp; соответствия требованиям, выбрав пункты **Управление информацией** > **Обозреватель действий с метками**.</span><span class="sxs-lookup"><span data-stu-id="1f754-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="1f754-116">Обратите внимание, что для использования обозревателя действий с метками необходима подписка на Office 365 корпоративный E5.</span><span class="sxs-lookup"><span data-stu-id="1f754-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![Обозреватель действий с метками](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="1f754-118">Просмотр действий с метками для файлов и папок</span><span class="sxs-lookup"><span data-stu-id="1f754-118">View label activities for files or folders</span></span>

<span data-ttu-id="1f754-p104">В верхней части обозревателя действий с метками можно выбрать просмотр действий для файлов или папок. Обратите внимание, что под действиями с папкой подразумеваются операции только с самой папкой, а не с хранящимися в ней файлами.</span><span class="sxs-lookup"><span data-stu-id="1f754-p104">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders. Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="1f754-p105">Вам может потребоваться просматривать действия для папок, потому что когда вы помечаете папку, всем файлам в этой папке также назначается эта метка (кроме тех файлов, к которым была явно применена метка). Следовательно, пометка папок может повлиять на значительное количество файлов. Дополнительные сведения см. в разделе [Применение метки хранения по умолчанию ко всему контенту в библиотеке SharePoint, папке или набору документов](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="1f754-p105">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them). Therefore, labeling folders might affect a significant number of files. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![Раскрывающееся меню с пунктами для просмотра действий с файлами и папками](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="1f754-125">Действия с метками</span><span class="sxs-lookup"><span data-stu-id="1f754-125">Label activities</span></span>

 <span data-ttu-id="1f754-p106">**Действия с метками** включают все операции: **добавление**, **удаление** и **изменение** метки. С помощью этого представления вы можете узнать, к скольким файлам в день применяется та или иная метка.</span><span class="sxs-lookup"><span data-stu-id="1f754-p106">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label. You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="1f754-128">Изменения меток</span><span class="sxs-lookup"><span data-stu-id="1f754-128">Label changes</span></span>

 <span data-ttu-id="1f754-p107">Представление **Изменения меток** включает потенциально рискованные действия — **удаление** и **изменение** меток. С помощью этого представления вы можете быстро ознакомиться с рискованными действиями и узнать, какие пользователи их выполняли. Вы можете выбрать файл в списке действий под диаграммой, а затем перейти по ссылке на этот файл в области сведений справа.</span><span class="sxs-lookup"><span data-stu-id="1f754-p107">**Label changes** includes the potentially risky actions of **removing** or **changing** a label. You can use this view to quickly see such risky actions and the user who performed them. In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![Область сведений о действиях с метками](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="1f754-133">Фильтрация действий с метками</span><span class="sxs-lookup"><span data-stu-id="1f754-133">Filter label activity</span></span>

<span data-ttu-id="1f754-p108">Вы можете быстро отфильтровать данные, чтобы просмотреть действия с метками для определенных метки, файла или пользователя. Вы также можете фильтровать действия с метками по расположению (SharePoint или OneDrive для бизнеса) и способу применения метки (вручную или автоматически).</span><span class="sxs-lookup"><span data-stu-id="1f754-p108">You can quickly filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![Фильтры для действий с метками](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

