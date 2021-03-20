---
title: Восстановление удаленной группы Microsoft 365
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
description: Узнайте, как восстановить удаленную группу Microsoft 365.
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910550"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="9d5c8-103">Восстановление удаленной группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d5c8-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="9d5c8-104">Если вы удалили группу, она будет храниться в течение 30 дней по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="9d5c8-105">Этот 30-дневный период считается "мягким удалением", так как можно восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="9d5c8-106">Через 30 дней группа и связанное с ней содержимое удаляются навсегда и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="9d5c8-107">Вместе с группой восстанавливается следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="9d5c8-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="9d5c8-108">Объект, свойства и участники Azure Active Directory (AD) Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="9d5c8-109">Адреса электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="9d5c8-110">Exchange Online поделился почтовым ящиком и календарем.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="9d5c8-111">Сайт и файлы группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="9d5c8-112">записная книжка OneNote;</span><span class="sxs-lookup"><span data-stu-id="9d5c8-112">OneNote notebook</span></span>
    
- <span data-ttu-id="9d5c8-113">Planner.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-113">Planner</span></span>
    
- <span data-ttu-id="9d5c8-114">Teams</span><span class="sxs-lookup"><span data-stu-id="9d5c8-114">Teams</span></span>

- <span data-ttu-id="9d5c8-115">Групповой и групповой контент Yammer (если группа Microsoft 365 была создана из Yammer)</span><span class="sxs-lookup"><span data-stu-id="9d5c8-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="9d5c8-116">В этой статье описывается восстановление только групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="9d5c8-117">Все остальные группы не могут быть восстановлены после удаления.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="9d5c8-118">Восстановление группы</span><span class="sxs-lookup"><span data-stu-id="9d5c8-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="9d5c8-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="9d5c8-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="9d5c8-120">Если вы владелец группы Microsoft 365, вы можете самостоятельно восстановить группу в Outlook в Интернете, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="9d5c8-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="9d5c8-121">На странице [удаленные группы](https://outlook.office.com/people/group/deleted)выберите параметр **Управление** группами в узле **Группы,** а затем выберите **Удаленный**.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="9d5c8-122">Щелкните **вкладку Восстановление** рядом с группой, необходимой для восстановления.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="9d5c8-123">Если удаленная группа не появится здесь, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="9d5c8-124">Центр администрирования</span><span class="sxs-lookup"><span data-stu-id="9d5c8-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="9d5c8-125">Если вы глобальный администратор или администратор групп, вы можете восстановить удаленную группу в центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="9d5c8-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="9d5c8-126">Перейдите в [Центр администрирования](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9d5c8-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="9d5c8-127">**Расширь** группы и нажмите **кнопку Удаленные группы.**</span><span class="sxs-lookup"><span data-stu-id="9d5c8-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="9d5c8-128">Выберите группу, которую необходимо восстановить, и нажмите кнопку **Восстановить группу**.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="9d5c8-129">В некоторых случаях для восстановления группы и всех ее данных может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="9d5c8-130">Есть вопросы о Группах Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="9d5c8-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="9d5c8-131">Посетите [техническое сообщество Майкрософт,](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) чтобы опубликовать вопросы и принять участие в беседах о группах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d5c8-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="9d5c8-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9d5c8-132">Related articles</span></span>

[<span data-ttu-id="9d5c8-133">Управление группами Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d5c8-133">Manage Microsoft 365 Groups with PowerShell</span></span>](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[<span data-ttu-id="9d5c8-134">Удаление групп с помощью командлета Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="9d5c8-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](/powershell/module/exchange/remove-unifiedgroup)
  
[<span data-ttu-id="9d5c8-135">Управление параметрами сайта группы, подключенного к группе</span><span class="sxs-lookup"><span data-stu-id="9d5c8-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="9d5c8-136">Удаление группы в Outlook</span><span class="sxs-lookup"><span data-stu-id="9d5c8-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)