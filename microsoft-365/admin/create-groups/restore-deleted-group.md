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
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="475c1-103">Восстановление удаленной группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="475c1-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="475c1-104">Если вы удалили группу, она будет храниться по умолчанию в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="475c1-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="475c1-105">Этот 30-дневный период считается "мягким удалением", так как вы по-прежнему можете восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="475c1-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="475c1-106">Через 30 дней группа и связанное с ней содержимое окончательно удаляются и не могут быть восстановлены.</span><span class="sxs-lookup"><span data-stu-id="475c1-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="475c1-107">Вместе с группой восстанавливается следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="475c1-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="475c1-108">Объект, свойства и члены групп Microsoft 365 Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="475c1-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="475c1-109">Адреса электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="475c1-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="475c1-110">Общие почтовые ящики и календарь Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="475c1-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="475c1-111">Сайт и файлы группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="475c1-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="475c1-112">записная книжка OneNote;</span><span class="sxs-lookup"><span data-stu-id="475c1-112">OneNote notebook</span></span>
    
- <span data-ttu-id="475c1-113">Planner.</span><span class="sxs-lookup"><span data-stu-id="475c1-113">Planner</span></span>
    
- <span data-ttu-id="475c1-114">Teams</span><span class="sxs-lookup"><span data-stu-id="475c1-114">Teams</span></span>

- <span data-ttu-id="475c1-115">Содержимое групп и групп Yammer (если группа Microsoft 365 была создана из Yammer)</span><span class="sxs-lookup"><span data-stu-id="475c1-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="475c1-116">В этой статье описывается восстановление только групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="475c1-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="475c1-117">Все остальные группы невозможно восстановить после удаления.</span><span class="sxs-lookup"><span data-stu-id="475c1-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="475c1-118">Восстановление группы</span><span class="sxs-lookup"><span data-stu-id="475c1-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="475c1-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="475c1-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="475c1-120">Если вы владелец группы Microsoft 365, вы можете самостоятельно восстановить группу в Outlook в Интернете, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="475c1-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="475c1-121">На странице ["Удаленные группы"](https://outlook.office.com/people/group/deleted)выберите **параметр** "Управление группами" в узле "Группы" и выберите **"Удалено".** </span><span class="sxs-lookup"><span data-stu-id="475c1-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="475c1-122">Щелкните **вкладку "Восстановление"** рядом с группой, которая вы хотите восстановить.</span><span class="sxs-lookup"><span data-stu-id="475c1-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="475c1-123">Если удаленная группа не появляется здесь, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="475c1-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="475c1-124">Центр администрирования</span><span class="sxs-lookup"><span data-stu-id="475c1-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="475c1-125">Если вы глобальный администратор или администратор групп, вы можете восстановить удаленную группу в Центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="475c1-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="475c1-126">Перейдите в [Центр администрирования](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="475c1-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="475c1-127">Раз **развернуть группы** и щелкнуть **"Удаленные группы".**</span><span class="sxs-lookup"><span data-stu-id="475c1-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="475c1-128">Выберите группу, которую нужно восстановить, и нажмите кнопку **"Восстановить группу".**</span><span class="sxs-lookup"><span data-stu-id="475c1-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="475c1-129">В некоторых случаях восстановление группы и всех ее данных может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="475c1-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="475c1-130">Возникли вопросы о группах Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="475c1-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="475c1-131">Посетите сообщество [Microsoft Tech Community,](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) чтобы задавать вопросы и участвовать в беседах о группах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="475c1-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="475c1-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="475c1-132">Related articles</span></span>

[<span data-ttu-id="475c1-133">Управление группами Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="475c1-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="475c1-134">Удаление групп с помощью командлета Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="475c1-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="475c1-135">Управление параметрами сайта группы, подключенного к группе</span><span class="sxs-lookup"><span data-stu-id="475c1-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="475c1-136">Удаление группы в Outlook</span><span class="sxs-lookup"><span data-stu-id="475c1-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
