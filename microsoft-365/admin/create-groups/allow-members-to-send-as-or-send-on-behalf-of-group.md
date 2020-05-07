---
title: Разрешение пользователям отправлять сообщения от имени группы или отправлять от него
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Сведения о том, как разрешить участникам отправлять электронную почту как группу Microsoft 365 или отправлять электронную почту от имени группы Майкрософт 365.
ms.openlocfilehash: ce4527321468ee01864177fc1a607fab6a474481
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049391"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="ece01-103">Разрешение пользователям отправлять сообщения от имени группы или отправлять от него</span><span class="sxs-lookup"><span data-stu-id="ece01-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="ece01-104">Член группы Microsoft 365, которому предоставлены разрешения " **Отправить как** " или " **Отправить от имени** ", может отправлять сообщения электронной почты в виде группы или от имени группы.</span><span class="sxs-lookup"><span data-stu-id="ece01-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="ece01-105">В этом разделе объясняется, как администратор может настроить эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="ece01-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="ece01-106">Например, если Меган Бовен входит в **учебную** группу Microsoft 365 и имеет разрешения " **Отправить как** " для группы, то, если она отправляет сообщение электронной почты в качестве группы, она будет выглядеть так, как **учебная** группа отправила сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ece01-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="ece01-107">Разрешение " **Отправить от имени** " позволяет пользователю отправлять электронную почту от имени группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ece01-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="ece01-108">Например, если Алекс Вилбер является частью группы **маркетинга** Microsoft 365 и имеет разрешения **на отправку от имени** и отправляет сообщение электронной почты в качестве группы, сообщение будет выглядеть так, как было отправлено **Вилбер от имени маркетингового отдела**.</span><span class="sxs-lookup"><span data-stu-id="ece01-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ece01-109">Вы можете настроить " **Отправить как** " или " **Отправить от имени** " для определенного пользователя, но не для обоих.</span><span class="sxs-lookup"><span data-stu-id="ece01-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="ece01-110">Если вы настроили оба значения, то по умолчанию будет **отправляться как**.</span><span class="sxs-lookup"><span data-stu-id="ece01-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="ece01-111">Чтобы узнать, как использовать Outlook и Outlook в Интернете для отправки электронной почты из группы, обратитесь к разделу [Отправка сообщений от имени или от имени группы майкрософт 365](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ece01-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="ece01-112">Разрешение участникам отправлять электронную почту как группу</span><span class="sxs-lookup"><span data-stu-id="ece01-112">Allow members to send email as a group</span></span>

<span data-ttu-id="ece01-113">В этом разделе объясняется, как разрешить пользователям отправлять электронную почту как группу в [центре администрирования Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ece01-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="ece01-114">В <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">центре администрирования Exchange</a>перейдите в раздел группы **получателей** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="ece01-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="ece01-115">Выберите команду **изменить**![значок](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) редактирования группы для группы, которую нужно разрешить пользователям отправлять.  </span><span class="sxs-lookup"><span data-stu-id="ece01-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="ece01-116">Выберите пункт **Делегирование группы**.</span><span class="sxs-lookup"><span data-stu-id="ece01-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="ece01-117">В разделе **Отправить как** выберите **+** знак, чтобы добавить пользователей, которых нужно отправить в качестве группы.</span><span class="sxs-lookup"><span data-stu-id="ece01-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Нажмите значок "плюс", чтобы добавить пользователей, которых нужно отправить в качестве группы Microsoft 365.](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="ece01-119">Введите имя, чтобы найти пользователя, или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="ece01-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="ece01-120">Нажмите кнопку **ОК** и **Сохраните**.</span><span class="sxs-lookup"><span data-stu-id="ece01-120">Select **OK** and **Save**.</span></span>
    
    ![Введите текст для поиска или выберите пользователя из списка.](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="ece01-122">Разрешение участникам отправлять электронную почту от имени группы</span><span class="sxs-lookup"><span data-stu-id="ece01-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="ece01-123">В этом разделе объясняется, как разрешить пользователям отправлять электронную почту от имени группы в центре администрирования Exchange в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ece01-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="ece01-124">В <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">центре администрирования Exchange</a>перейдите в раздел группы **получателей** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="ece01-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="ece01-125">Выберите команду **изменить** ![значок](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) редактирования группы для группы, которую нужно разрешить пользователям отправлять.</span><span class="sxs-lookup"><span data-stu-id="ece01-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="ece01-126">Выберите пункт **Делегирование группы**.</span><span class="sxs-lookup"><span data-stu-id="ece01-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="ece01-127">В разделе Отправить от имени выберите **+** знак, чтобы добавить пользователей, которых нужно отправить в качестве группы.</span><span class="sxs-lookup"><span data-stu-id="ece01-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Нажмите значок "плюс", чтобы добавить пользователей, которых нужно отправить в качестве группы Microsoft 365.](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="ece01-129">Введите имя, чтобы найти пользователя, или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="ece01-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="ece01-130">Нажмите кнопку **ОК** и **Сохраните**.</span><span class="sxs-lookup"><span data-stu-id="ece01-130">Select **OK** and **Save**.</span></span>
    
    ![Введите текст для поиска или выберите пользователя из списка.](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="ece01-132">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="ece01-132">Related articles</span></span>

[<span data-ttu-id="ece01-133">Дополнительные сведения о группах Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ece01-133">Learn more about Microsoft 365 groups</span></span>](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="ece01-134">Add — RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="ece01-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="ece01-135">Set — UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="ece01-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
