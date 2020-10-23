---
title: Восстановление удаленной группы
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Узнайте, как восстановить удаленную группу Microsoft 365.
ms.openlocfilehash: 30e267a149bc18c2425d4ea38423b887116794c6
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681650"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="f5974-103">Восстановление удаленной группы</span><span class="sxs-lookup"><span data-stu-id="f5974-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f5974-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="f5974-104">The admin center is changing.</span></span> <span data-ttu-id="f5974-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="f5974-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

> [!NOTE]
> <span data-ttu-id="f5974-106">В этой статье описывается восстановление только групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5974-106">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="f5974-107">После удаления все другие группы не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="f5974-107">All other groups cannot be restored once deleted.</span></span>

<span data-ttu-id="f5974-108">Если вы удалили группу, по умолчанию она будет храниться в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f5974-108">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="f5974-109">Этот 30-дневный период считается "обратимым удалением", так как вы по-прежнему можете восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="f5974-109">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="f5974-110">По истечении 30 дней группа и связанное с ней содержимое безвозвратно удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="f5974-110">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="f5974-111">Вместе с группой восстанавливается следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="f5974-111">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="f5974-112">Azure Active Directory (AD), Microsoft 365 группирует объект, свойства и элементы.</span><span class="sxs-lookup"><span data-stu-id="f5974-112">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="f5974-113">Адреса электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="f5974-113">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="f5974-114">Общие папки "Входящие" и "Календарь" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f5974-114">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="f5974-115">Сайт группы SharePoint Online и файлы.</span><span class="sxs-lookup"><span data-stu-id="f5974-115">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="f5974-116">записная книжка OneNote;</span><span class="sxs-lookup"><span data-stu-id="f5974-116">OneNote notebook</span></span>
    
- <span data-ttu-id="f5974-117">Planner.</span><span class="sxs-lookup"><span data-stu-id="f5974-117">Planner</span></span>
    
- <span data-ttu-id="f5974-118">Teams</span><span class="sxs-lookup"><span data-stu-id="f5974-118">Teams</span></span>

- <span data-ttu-id="f5974-119">Группа Yammer и контент группы (если группа Microsoft 365 была создана из Yammer)</span><span class="sxs-lookup"><span data-stu-id="f5974-119">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="f5974-120">Восстановление группы, которой владеет пользователь, с помощью Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="f5974-120">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="f5974-121">Если вы являетесь владельцем группы Microsoft 365, вы можете восстановить эту группу в Outlook в Интернете, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f5974-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="f5974-122">На [странице удаленные группы](https://outlook.office.com/people/group/deleted)выберите пункт **Управление группами** в узле **группы** , а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f5974-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="f5974-123">Щелкните вкладку **Восстановление** рядом с группой, которую требуется восстановить.</span><span class="sxs-lookup"><span data-stu-id="f5974-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="f5974-124">Если удаленная группа не отображается здесь, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="f5974-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f5974-125">Восстановление группы в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5974-125">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="f5974-126">Если вы являетесь глобальным администратором или администратором групп, вы можете восстановить удаленную группу в центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f5974-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="f5974-127">Перейдите в [Центр администрирования](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f5974-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="f5974-128">Разверните узел **группы**, а затем щелкните **удаленные группы**.</span><span class="sxs-lookup"><span data-stu-id="f5974-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="f5974-129">Выберите группу, которую требуется восстановить, и нажмите кнопку **восстановить группу**.</span><span class="sxs-lookup"><span data-stu-id="f5974-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="f5974-130">В некоторых случаях восстановление группы и всех ее данных может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="f5974-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="f5974-131">Окончательное удаление группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5974-131">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="f5974-132">Иногда может потребоваться окончательно очистить группу, не дожидаясь периода действия 30 дней для мягкого удаления.</span><span class="sxs-lookup"><span data-stu-id="f5974-132">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="f5974-133">Для этого запустите PowerShell и выполните эту команду, чтобы получить идентификатор объекта группы:</span><span class="sxs-lookup"><span data-stu-id="f5974-133">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="f5974-134">Запишите идентификатор объекта группы или групп, которые требуется окончательно удалить.</span><span class="sxs-lookup"><span data-stu-id="f5974-134">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f5974-135">При этом группа и все ее данные будут удалены навсегда.</span><span class="sxs-lookup"><span data-stu-id="f5974-135">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="f5974-136">Чтобы окончательно удалить группу, в PowerShell выполните эту команду:</span><span class="sxs-lookup"><span data-stu-id="f5974-136">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="f5974-p105">Чтобы проверить, удалилась ли группа, снова запустите командлет  *Get-AzureADMSDeletedGroup*  и убедитесь, что группа отсутствует в списке обратимо удаленных. В некоторых случаях процесс полного окончательного удаления группы и всех ее данных может длиться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="f5974-p105">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="f5974-139">У вас есть вопросы по группам Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="f5974-139">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="f5974-140">Посетите [сообщество Майкрософт](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) для отправки вопросов и участия в беседах, посвященных группам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5974-140">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="f5974-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f5974-141">Related articles</span></span>

[<span data-ttu-id="f5974-142">Управление группами Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5974-142">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="f5974-143">Удаление групп с помощью командлета Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="f5974-143">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="f5974-144">Управление параметрами сайта группы, подключенного к группе</span><span class="sxs-lookup"><span data-stu-id="f5974-144">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="f5974-145">Удаление группы в Outlook</span><span class="sxs-lookup"><span data-stu-id="f5974-145">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
