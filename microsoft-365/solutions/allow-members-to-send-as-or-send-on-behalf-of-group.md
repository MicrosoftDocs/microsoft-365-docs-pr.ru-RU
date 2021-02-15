---
title: Разрешить участникам отправлять сообщение от имени группы
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
description: Узнайте, как разрешить членам группы Microsoft 365 отправлять электронную почту от имени группы Microsoft 365.
ms.openlocfilehash: 6dff559eceec1b719f31d577d7fff8f604636a47
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663587"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="c47b2-103">Разрешить участникам отправлять сообщение от имени группы</span><span class="sxs-lookup"><span data-stu-id="c47b2-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="c47b2-104">Участник группы Microsoft 365, которому предоставлены разрешения  "Отправить как" или "Отправить от имени", может отправлять электронную почту от имени группы или от ее имени. </span><span class="sxs-lookup"><span data-stu-id="c47b2-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="c47b2-105">В этой статье объясняется, как глобальный администратор или администратор Exchange может установить эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="c47b2-105">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="c47b2-106">Например, если Марта Боуен входит в группу **Training** Microsoft  365 и имеет разрешения "Отправить как" для группы, если  она отправляет сообщение электронной почты в качестве группы, оно будет выглядеть так, как будто группа обучения отправила сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c47b2-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="c47b2-107">Разрешение **"Отправить от имени"** позволяет пользователю отправлять электронную почту от имени группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c47b2-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="c47b2-108">Например, если Алекс Уайлбер входит в группу **Marketing**  Microsoft 365 и имеет разрешения "Отправить от имени" и отправляет сообщение электронной почты в качестве группы, сообщение электронной почты выглядит так, будто оно было отправлено **Алексом Wilber** от имени отдела маркетинга.</span><span class="sxs-lookup"><span data-stu-id="c47b2-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c47b2-109">Вы можете настроить отправку **как** или отправить **от** имени для данного пользователя, но не оба одновременно.</span><span class="sxs-lookup"><span data-stu-id="c47b2-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="c47b2-110">Если вы настроите оба этих значения, по умолчанию будет установлено значение **"Отправить как".**</span><span class="sxs-lookup"><span data-stu-id="c47b2-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="c47b2-111">См. статью "Отправка электронной почты от или от имени группы [Microsoft 365",](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) чтобы узнать, как использовать Outlook и Outlook в Интернете для отправки электронной почты из группы.</span><span class="sxs-lookup"><span data-stu-id="c47b2-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="c47b2-112">Разрешить участникам отправлять электронную почту как группу</span><span class="sxs-lookup"><span data-stu-id="c47b2-112">Allow members to send email as a group</span></span>

<span data-ttu-id="c47b2-113">В этом разделе объясняется, как разрешить пользователям отправлять электронную почту как группу в Центре администрирования [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c47b2-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="c47b2-114">В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">администрирования Exchange</a>перейдите в **группу** \> **получателей.**</span><span class="sxs-lookup"><span data-stu-id="c47b2-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="c47b2-115">Выберите **значок** ![ "Изменить группу редактирования" в группе, отправляемой ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) пользователями.  </span><span class="sxs-lookup"><span data-stu-id="c47b2-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="c47b2-116">Выберите пункт **Делегирование группы**.</span><span class="sxs-lookup"><span data-stu-id="c47b2-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="c47b2-117">В разделе **"Отправить как"** выберите знак, чтобы добавить пользователей, которые **+** вы хотите отправить в качестве группы.</span><span class="sxs-lookup"><span data-stu-id="c47b2-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Снимок экрана: диалоговое окно "Отправить как"](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="c47b2-119">Введите имя, чтобы найти пользователя, или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="c47b2-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="c47b2-120">Выберите **"ОК"** и **сохраните**.</span><span class="sxs-lookup"><span data-stu-id="c47b2-120">Select **OK** and **Save**.</span></span>
    
    ![Введите для поиска или выберите пользователя из списка](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="c47b2-122">Разрешение участникам отправлять сообщения электронной почты от имени группы</span><span class="sxs-lookup"><span data-stu-id="c47b2-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="c47b2-123">В этом разделе объясняется, как разрешить пользователям отправлять электронную почту от имени группы в Центре администрирования Exchange (EAC) в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c47b2-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="c47b2-124">В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">администрирования Exchange</a>перейдите в **группу** \> **получателей.**</span><span class="sxs-lookup"><span data-stu-id="c47b2-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="c47b2-125">Выберите **значок** ![ "Изменить группу редактирования" в группе, отправляемой ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) пользователями.</span><span class="sxs-lookup"><span data-stu-id="c47b2-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="c47b2-126">Выберите пункт **Делегирование группы**.</span><span class="sxs-lookup"><span data-stu-id="c47b2-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="c47b2-127">В разделе "Отправить от имени" выберите знак, чтобы добавить пользователей, которые вы хотите **+** отправить в качестве группы.</span><span class="sxs-lookup"><span data-stu-id="c47b2-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Снимок экрана: отправка от имени диалоговое окно](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="c47b2-129">Введите имя, чтобы найти пользователя, или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="c47b2-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="c47b2-130">Выберите **"ОК"** и **сохраните**.</span><span class="sxs-lookup"><span data-stu-id="c47b2-130">Select **OK** and **Save**.</span></span>
    
    ![Введите для поиска или выберите пользователя из списка](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="c47b2-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c47b2-132">Related articles</span></span>

[<span data-ttu-id="c47b2-133">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="c47b2-133">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="c47b2-134">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="c47b2-134">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="c47b2-135">Узнайте больше о группах Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c47b2-135">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="c47b2-136">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="c47b2-136">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="c47b2-137">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="c47b2-137">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
