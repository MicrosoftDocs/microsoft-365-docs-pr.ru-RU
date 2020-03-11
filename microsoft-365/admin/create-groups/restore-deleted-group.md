---
title: Восстановление удаленной группы Office 365
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Узнайте, как восстановить удаленную группу Office 365.
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583166"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="f670d-103">Восстановление удаленной группы Office 365</span><span class="sxs-lookup"><span data-stu-id="f670d-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="f670d-104">Если вы удалили группу, по умолчанию она будет храниться в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f670d-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="f670d-105">Этот 30-дневный период считается "обратимым удалением", так как вы по-прежнему можете восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="f670d-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="f670d-106">По истечении 30 дней группа и связанное с ней содержимое безвозвратно удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="f670d-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="f670d-107">Вместе с группой восстанавливается следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="f670d-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="f670d-108">Azure Active Directory (AD) Office 365 группирует объект, свойства и элементы.</span><span class="sxs-lookup"><span data-stu-id="f670d-108">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="f670d-109">Адреса электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="f670d-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="f670d-110">Общие папки "Входящие" и "Календарь" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f670d-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="f670d-111">Сайт группы SharePoint Online и файлы.</span><span class="sxs-lookup"><span data-stu-id="f670d-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="f670d-112">записная книжка OneNote;</span><span class="sxs-lookup"><span data-stu-id="f670d-112">OneNote notebook</span></span>
    
- <span data-ttu-id="f670d-113">Planner.</span><span class="sxs-lookup"><span data-stu-id="f670d-113">Planner</span></span>
    
- <span data-ttu-id="f670d-114">Teams</span><span class="sxs-lookup"><span data-stu-id="f670d-114">Teams</span></span>

- <span data-ttu-id="f670d-115">Группа Yammer и контент группы (если группа Office 365 была создана из Yammer)</span><span class="sxs-lookup"><span data-stu-id="f670d-115">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="f670d-116">Восстановление группы, которой владеет пользователь, с помощью Outlook</span><span class="sxs-lookup"><span data-stu-id="f670d-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="f670d-117">Если вы являетесь владельцем группы Office 365, вы можете восстановить ее самостоятельно в Outlook, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f670d-117">If you are the owner of an Office 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="f670d-118">На [странице удаленные группы](https://outlook.office.com/people/group/deleted)выберите пункт **Управление группами** в узле **группы** , а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f670d-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="f670d-119">Щелкните вкладку **Восстановление** рядом с группой, которую требуется восстановить.</span><span class="sxs-lookup"><span data-stu-id="f670d-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="f670d-120">Если удаленная группа не отображается здесь, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="f670d-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f670d-121">Восстановление группы в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f670d-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="f670d-122">Если вы являетесь глобальным администратором или администратором групп, вы можете восстановить удаленную группу в центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f670d-122">If you are a global administrator or a groups admin, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="f670d-123">Перейдите в Центр администрирования [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f670d-123">Go to the admin center at [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="f670d-124">Разверните узел **группы**, а затем щелкните **удаленные группы**.</span><span class="sxs-lookup"><span data-stu-id="f670d-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="f670d-125">Выберите группу, которую требуется восстановить, и нажмите кнопку **восстановить группу**.</span><span class="sxs-lookup"><span data-stu-id="f670d-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="f670d-126">Окончательное удаление группы Office 365</span><span class="sxs-lookup"><span data-stu-id="f670d-126">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="f670d-127">Иногда может потребоваться окончательно очистить группу, не дожидаясь периода действия 30 дней для мягкого удаления.</span><span class="sxs-lookup"><span data-stu-id="f670d-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="f670d-128">Для этого запустите PowerShell и выполните эту команду, чтобы получить идентификатор объекта группы:</span><span class="sxs-lookup"><span data-stu-id="f670d-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="f670d-129">Запишите идентификатор объекта группы или групп, которые требуется окончательно удалить.</span><span class="sxs-lookup"><span data-stu-id="f670d-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f670d-130">При этом группа и все ее данные будут удалены навсегда.</span><span class="sxs-lookup"><span data-stu-id="f670d-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="f670d-131">Чтобы окончательно удалить группу, в PowerShell выполните эту команду:</span><span class="sxs-lookup"><span data-stu-id="f670d-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="f670d-p103">Чтобы проверить, удалилась ли группа, снова запустите командлет  *Get-AzureADMSDeletedGroup*  и убедитесь, что группа отсутствует в списке обратимо удаленных. В некоторых случаях процесс полного окончательного удаления группы и всех ее данных может длиться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="f670d-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="f670d-134">У вас есть вопросы о группах Office 365?</span><span class="sxs-lookup"><span data-stu-id="f670d-134">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="f670d-135">Посетите [сообщество Майкрософт](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) для отправки вопросов и участия в беседах, посвященных группам Office 365.</span><span class="sxs-lookup"><span data-stu-id="f670d-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="f670d-136">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="f670d-136">Related articles</span></span>

[<span data-ttu-id="f670d-137">Управление группами Office 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f670d-137">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="f670d-138">Удаление групп с помощью командлета Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="f670d-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="f670d-139">Управление параметрами сайта группы, подключенного к группе</span><span class="sxs-lookup"><span data-stu-id="f670d-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="f670d-140">Удаление группы в Outlook</span><span class="sxs-lookup"><span data-stu-id="f670d-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
