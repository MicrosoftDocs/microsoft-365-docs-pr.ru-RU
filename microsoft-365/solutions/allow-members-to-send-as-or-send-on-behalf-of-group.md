---
title: Разрешить участникам отправлять как или отправлять от имени группы
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Узнайте, как разрешить участникам группы отправлять электронную почту в качестве группы Microsoft 365 или отправлять сообщения от имени группы Microsoft 365.
ms.openlocfilehash: 44a0a7a690c8faa9fe00732e8154f36aa5a6fe6f
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727083"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="b54b8-103">Разрешить участникам отправлять как или отправлять от имени группы</span><span class="sxs-lookup"><span data-stu-id="b54b8-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="b54b8-104">Член группы Microsoft 365, которому были  предоставлены  разрешения Отправить как или Отправить от имени, может отправлять электронную почту как группе, так и от имени группы.</span><span class="sxs-lookup"><span data-stu-id="b54b8-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="b54b8-105">(Гостям в группе не могут быть предоставлены эти разрешения.)</span><span class="sxs-lookup"><span data-stu-id="b54b8-105">(Guests in the group cannot be granted these permissions.)</span></span>

<span data-ttu-id="b54b8-106">В этой статье объясняется, как глобальный или администратор Exchange может устанавливать эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="b54b8-106">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="b54b8-107">Например, если Меган Боуэн входит в группу **Training** Microsoft  365 и имеет отправку в качестве разрешений в группе,  если она отправляет сообщение электронной почты в качестве группы, это будет выглядеть так, как будто группа training отправила сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b54b8-107">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="b54b8-108">Разрешение **Отправка от имени** позволяет пользователю отправлять электронную почту от имени группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b54b8-108">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="b54b8-109">Например, если Алекс Уилбер входит в группу **"Маркетинг** Microsoft  365" и имеет разрешения на отправку от имени и отправляет электронное письмо в качестве группы, сообщение электронной почты выглядит так, будто оно было отправлено Алексом Уилбером от имени **отдела маркетинга**.</span><span class="sxs-lookup"><span data-stu-id="b54b8-109">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b54b8-110">Вы можете настроить **отправку как** или **отправить** от имени данного пользователя, но не оба.</span><span class="sxs-lookup"><span data-stu-id="b54b8-110">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="b54b8-111">Если настроить оба, по умолчанию будет **отправляться как**.</span><span class="sxs-lookup"><span data-stu-id="b54b8-111">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="b54b8-112">См. статью Отправка электронной почты от или от имени группы [Microsoft 365,](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) чтобы узнать, как использовать Outlook и Outlook в Интернете для отправки электронной почты из группы.</span><span class="sxs-lookup"><span data-stu-id="b54b8-112">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="b54b8-113">Разрешить участникам отправлять электронную почту как группу</span><span class="sxs-lookup"><span data-stu-id="b54b8-113">Allow members to send email as a group</span></span>

<span data-ttu-id="b54b8-114">В этом разделе рассказывается, как разрешить пользователям отправлять электронную почту в качестве группы в центре администрирования [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b54b8-114">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="b54b8-115">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">администрирования Exchange</a>перейдите в **группы** \> **получателей**.</span><span class="sxs-lookup"><span data-stu-id="b54b8-115">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="b54b8-116">Выберите **значок** ![ Изменить группу редактирования в группе, которую необходимо разрешить пользователям отправлять ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) как.  </span><span class="sxs-lookup"><span data-stu-id="b54b8-116">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="b54b8-117">Выберите пункт **Делегирование группы**.</span><span class="sxs-lookup"><span data-stu-id="b54b8-117">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="b54b8-118">В разделе **Отправка как** выберите знак, чтобы добавить пользователей, которые вы **+** хотите отправить в группу.</span><span class="sxs-lookup"><span data-stu-id="b54b8-118">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Снимок экрана отправки в диалоговом окне](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="b54b8-120">Введите имя, чтобы найти пользователя, или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="b54b8-120">Type to search or pick a user from the list.</span></span> <span data-ttu-id="b54b8-121">Выберите **ОК** и **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b54b8-121">Select **OK** and **Save**.</span></span>
    
    ![Введите для поиска или выберите пользователя из списка](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="b54b8-123">Разрешить участникам отправлять электронную почту от имени группы</span><span class="sxs-lookup"><span data-stu-id="b54b8-123">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="b54b8-124">В этом разделе рассказывается, как разрешить пользователям отправлять электронную почту от имени группы в центре администрирования Exchange (EAC) в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b54b8-124">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="b54b8-125">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">администрирования Exchange</a>перейдите в **группы** \> **получателей**.</span><span class="sxs-lookup"><span data-stu-id="b54b8-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="b54b8-126">Выберите **значок** ![ Изменить группу редактирования в группе, которую необходимо разрешить пользователям отправлять ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) как.</span><span class="sxs-lookup"><span data-stu-id="b54b8-126">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="b54b8-127">Выберите пункт **Делегирование группы**.</span><span class="sxs-lookup"><span data-stu-id="b54b8-127">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="b54b8-128">В разделе Отправка от имени выберите знак, чтобы добавить пользователей, которые вы **+** хотите отправить в группу.</span><span class="sxs-lookup"><span data-stu-id="b54b8-128">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Снимок экрана отправки от имени диалоговое окно](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="b54b8-130">Введите имя, чтобы найти пользователя, или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="b54b8-130">Type to search or pick a user from the list.</span></span> <span data-ttu-id="b54b8-131">Выберите **ОК** и **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b54b8-131">Select **OK** and **Save**.</span></span>
    
    ![Введите для поиска или выберите пользователя из списка](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="b54b8-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b54b8-133">Related articles</span></span>

[<span data-ttu-id="b54b8-134">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="b54b8-134">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="b54b8-135">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="b54b8-135">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="b54b8-136">Дополнительные информацию о группах Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b54b8-136">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="b54b8-137">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="b54b8-137">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="b54b8-138">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="b54b8-138">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
