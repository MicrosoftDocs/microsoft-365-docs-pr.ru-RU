---
title: Восстановление удаленной Microsoft 365 группы
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Удаленная группа сохраняется в течение 30 дней, и вы все еще можете восстановить группу. Через 30 дней группа и ее содержимое будут удалены навсегда.
ms.openlocfilehash: 285796ec45b1e6d77d46d7a0c39706f566bb8cf6
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582684"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="2e05c-104">Восстановление удаленной Microsoft 365 группы</span><span class="sxs-lookup"><span data-stu-id="2e05c-104">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="2e05c-105">Если вы удалили группу, она будет храниться в течение 30 дней по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2e05c-105">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="2e05c-106">Этот 30-дневный период считается "мягким удалением", так как можно восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="2e05c-106">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="2e05c-107">Через 30 дней группа и связанное с ней содержимое удаляются навсегда и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="2e05c-107">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="2e05c-108">Вместе с группой восстанавливается следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="2e05c-108">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="2e05c-109">Azure Active Directory (AD) Microsoft 365, свойств и членов групп.</span><span class="sxs-lookup"><span data-stu-id="2e05c-109">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="2e05c-110">Адреса электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="2e05c-110">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="2e05c-111">Exchange Online общий почтовый ящик и календарь.</span><span class="sxs-lookup"><span data-stu-id="2e05c-111">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="2e05c-112">SharePoint Веб-сайт и файлы команды в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2e05c-112">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="2e05c-113">записная книжка OneNote;</span><span class="sxs-lookup"><span data-stu-id="2e05c-113">OneNote notebook</span></span>
    
- <span data-ttu-id="2e05c-114">Planner.</span><span class="sxs-lookup"><span data-stu-id="2e05c-114">Planner</span></span>
    
- <span data-ttu-id="2e05c-115">Teams</span><span class="sxs-lookup"><span data-stu-id="2e05c-115">Teams</span></span>

- <span data-ttu-id="2e05c-116">Yammer группового и группового контента (если Microsoft 365 группа была создана из Yammer)</span><span class="sxs-lookup"><span data-stu-id="2e05c-116">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="2e05c-117">В этой статье описывается восстановление только Microsoft 365 групп.</span><span class="sxs-lookup"><span data-stu-id="2e05c-117">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="2e05c-118">Все остальные группы не могут быть восстановлены после удаления.</span><span class="sxs-lookup"><span data-stu-id="2e05c-118">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="2e05c-119">Восстановление группы</span><span class="sxs-lookup"><span data-stu-id="2e05c-119">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="2e05c-120">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e05c-120">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="2e05c-121">Если вы владелец группы Microsoft 365, вы можете восстановить группу самостоятельно Outlook интернете, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="2e05c-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="2e05c-122">На странице [удаленные группы](https://outlook.office.com/people/group/deleted)выберите параметр **Управление** группами в узле **Группы,** а затем выберите **Удаленный**.</span><span class="sxs-lookup"><span data-stu-id="2e05c-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="2e05c-123">Щелкните **вкладку Восстановление** рядом с группой, необходимой для восстановления.</span><span class="sxs-lookup"><span data-stu-id="2e05c-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="2e05c-124">Если удаленная группа не появится здесь, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="2e05c-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="2e05c-125">Центр администрирования</span><span class="sxs-lookup"><span data-stu-id="2e05c-125">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="2e05c-126">Если вы глобальный администратор или администратор групп, вы можете восстановить удаленную группу в центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="2e05c-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="2e05c-127">Перейдите в [Центр администрирования](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="2e05c-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="2e05c-128">**Расширь** группы и нажмите **кнопку Удаленные группы.**</span><span class="sxs-lookup"><span data-stu-id="2e05c-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="2e05c-129">Выберите группу, которую необходимо восстановить, и нажмите кнопку **Восстановить группу**.</span><span class="sxs-lookup"><span data-stu-id="2e05c-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="2e05c-130">В некоторых случаях для восстановления группы и всех ее данных может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="2e05c-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="2e05c-131">Есть вопросы о Microsoft 365 группах?</span><span class="sxs-lookup"><span data-stu-id="2e05c-131">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="2e05c-132">Посетите [веб-сайт Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) для публикации вопросов и участия в беседах о Microsoft 365 группах.</span><span class="sxs-lookup"><span data-stu-id="2e05c-132">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="2e05c-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e05c-133">Related content</span></span>

<span data-ttu-id="2e05c-134">[Управление Microsoft 365 группами с помощью PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="2e05c-134">[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article)</span></span>
  
<span data-ttu-id="2e05c-135">[Удаление групп с Remove-UnifiedGroup (статья)](/powershell/module/exchange/remove-unifiedgroup)</span><span class="sxs-lookup"><span data-stu-id="2e05c-135">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (article)</span></span>
  
<span data-ttu-id="2e05c-136">[Управление настройками веб-сайтов группы](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) с подключением к группе (статья)</span><span class="sxs-lookup"><span data-stu-id="2e05c-136">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (article)</span></span>
  
<span data-ttu-id="2e05c-137">[Удаление группы в Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (статья)</span><span class="sxs-lookup"><span data-stu-id="2e05c-137">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (article)</span></span>