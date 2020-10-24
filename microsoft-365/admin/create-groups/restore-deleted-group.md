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
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753247"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="976d6-103">Восстановление удаленной группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="976d6-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="976d6-104">Если вы удалили группу, по умолчанию она будет храниться в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="976d6-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="976d6-105">Этот 30-дневный период считается "обратимым удалением", так как вы по-прежнему можете восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="976d6-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="976d6-106">По истечении 30 дней группа и связанное с ней содержимое безвозвратно удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="976d6-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="976d6-107">Вместе с группой восстанавливается следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="976d6-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="976d6-108">Azure Active Directory (AD), Microsoft 365 группирует объект, свойства и элементы.</span><span class="sxs-lookup"><span data-stu-id="976d6-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="976d6-109">Адреса электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="976d6-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="976d6-110">Общие папки "Входящие" и "Календарь" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="976d6-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="976d6-111">Сайт группы SharePoint Online и файлы.</span><span class="sxs-lookup"><span data-stu-id="976d6-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="976d6-112">записная книжка OneNote;</span><span class="sxs-lookup"><span data-stu-id="976d6-112">OneNote notebook</span></span>
    
- <span data-ttu-id="976d6-113">Planner.</span><span class="sxs-lookup"><span data-stu-id="976d6-113">Planner</span></span>
    
- <span data-ttu-id="976d6-114">Teams</span><span class="sxs-lookup"><span data-stu-id="976d6-114">Teams</span></span>

- <span data-ttu-id="976d6-115">Группа Yammer и контент группы (если группа Microsoft 365 была создана из Yammer)</span><span class="sxs-lookup"><span data-stu-id="976d6-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="976d6-116">В этой статье описывается восстановление только групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="976d6-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="976d6-117">После удаления все другие группы не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="976d6-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="976d6-118">Восстановление группы</span><span class="sxs-lookup"><span data-stu-id="976d6-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="976d6-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="976d6-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="976d6-120">Если вы являетесь владельцем группы Microsoft 365, вы можете восстановить эту группу в Outlook в Интернете, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="976d6-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="976d6-121">На [странице удаленные группы](https://outlook.office.com/people/group/deleted)выберите пункт **Управление группами** в узле **группы** , а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="976d6-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="976d6-122">Щелкните вкладку **Восстановление** рядом с группой, которую требуется восстановить.</span><span class="sxs-lookup"><span data-stu-id="976d6-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="976d6-123">Если удаленная группа не отображается здесь, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="976d6-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="976d6-124">Центр администрирования</span><span class="sxs-lookup"><span data-stu-id="976d6-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="976d6-125">Если вы являетесь глобальным администратором или администратором групп, вы можете восстановить удаленную группу в центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="976d6-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="976d6-126">Перейдите в [Центр администрирования](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="976d6-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="976d6-127">Разверните узел **группы**, а затем щелкните **удаленные группы**.</span><span class="sxs-lookup"><span data-stu-id="976d6-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="976d6-128">Выберите группу, которую требуется восстановить, и нажмите кнопку **восстановить группу**.</span><span class="sxs-lookup"><span data-stu-id="976d6-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="976d6-129">В некоторых случаях восстановление группы и всех ее данных может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="976d6-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="976d6-130">У вас есть вопросы по группам Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="976d6-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="976d6-131">Посетите [сообщество Майкрософт](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) для отправки вопросов и участия в беседах, посвященных группам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="976d6-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="976d6-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="976d6-132">Related articles</span></span>

[<span data-ttu-id="976d6-133">Управление группами Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="976d6-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="976d6-134">Удаление групп с помощью командлета Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="976d6-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="976d6-135">Управление параметрами сайта группы, подключенного к группе</span><span class="sxs-lookup"><span data-stu-id="976d6-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="976d6-136">Удаление группы в Outlook</span><span class="sxs-lookup"><span data-stu-id="976d6-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
