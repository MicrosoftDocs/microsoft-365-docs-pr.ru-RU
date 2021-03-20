---
title: Планирование организации и управления жизненным циклом для групп Microsoft 365 и Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Подробнее о вариантах управления жизненным циклом для средств совместной работы в Microsoft 365
ms.openlocfilehash: ff3a3a60ce49c423410b51dc6fee2137ebf8952a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907932"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="788f9-103">Планирование организации и управления жизненным циклом для групп Microsoft 365 и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="788f9-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="788f9-104">Группы Microsoft 365 обладает богатым набором средств для реализации необходимых для организации возможностей управления.</span><span class="sxs-lookup"><span data-stu-id="788f9-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="788f9-105">В следующем разделе описаны возможности, рекомендации по рекомендациям и рекомендации по задавать правильные вопросы для определения требований к управлению и их удовлетворения.</span><span class="sxs-lookup"><span data-stu-id="788f9-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="788f9-106">Управление созданием групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="788f9-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="788f9-107">Конечные пользователи могут создавать группы из нескольких конечных точек, включая Outlook, SharePoint, Teams и другие среды.</span><span class="sxs-lookup"><span data-stu-id="788f9-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![image desc](../media/04.png)

<span data-ttu-id="788f9-109">Мы настоятельно рекомендуем самообслужить, чтобы уполномочивать владельцев групп и помогать пользователям работать проще.</span><span class="sxs-lookup"><span data-stu-id="788f9-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="788f9-110">Ограничение создания групп и групп может замедлить производительность пользователей, так как многие службы Microsoft 365 требуют создания групп для функционирования службы.</span><span class="sxs-lookup"><span data-stu-id="788f9-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="788f9-111">Рассмотрим следующие параметры управления для создания групп:</span><span class="sxs-lookup"><span data-stu-id="788f9-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="788f9-112">Чтобы ограничить разрастаемую группу, используйте [политики](microsoft-365-groups-expiration-policy.md) истечения срока действия групп для автоматического удаления не используемых групп.</span><span class="sxs-lookup"><span data-stu-id="788f9-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="788f9-113">Ограничить создание группы членами групп безопасности с [динамическим](/azure/active-directory/users-groups-roles/groups-create-rule) членством, содержащими, например, всех сотрудников, работающих полный рабочий день.</span><span class="sxs-lookup"><span data-stu-id="788f9-113">Limit group creation to members of a [security groups with dynamic membership](/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="788f9-114">Ограничьте создание группы группой безопасности и обязывите пользователей пройти обучение политикам использования групп в вашей организации, чтобы стать членами группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="788f9-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="788f9-115">Если вы хотите ограничить возможности создания групп, см. в статью Управление созданием [групп Microsoft 365](manage-creation-of-groups.md) для получения сведений о настройке этих групп.</span><span class="sxs-lookup"><span data-stu-id="788f9-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="788f9-116">Удаление, восстановление и архивативная группа</span><span class="sxs-lookup"><span data-stu-id="788f9-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="788f9-117">При удалении группы Microsoft 365 по умолчанию она сохраняется в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="788f9-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="788f9-118">Этот период называется обратимым удалением, так как вы по-прежнему можете восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="788f9-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="788f9-119">Через 30 дней группа и ее контент окончательно удаляются, и их невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="788f9-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="788f9-120">Если у вас есть политики хранения для хранения чата, файлов или почты, эти элементы будут сохранены после удаления группы.</span><span class="sxs-lookup"><span data-stu-id="788f9-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="788f9-121">Подробные сведения см. в [материале "Сведения о политиках](../compliance/retention.md) хранения".</span><span class="sxs-lookup"><span data-stu-id="788f9-121">See [Learn about retention policies](../compliance/retention.md) for details.</span></span>

<span data-ttu-id="788f9-122">Если вы хотите удалить группу, но сохранить содержимое одной или более служб, связанных с группой, см. в публикации [Archive groups, teams и Yammer.](end-life-cycle-groups-teams-sites-yammer.md)</span><span class="sxs-lookup"><span data-stu-id="788f9-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="788f9-123">Политика именования групп</span><span class="sxs-lookup"><span data-stu-id="788f9-123">Group naming policy</span></span>

<span data-ttu-id="788f9-124">Политика именования групп может помочь управлять группами двумя способами:</span><span class="sxs-lookup"><span data-stu-id="788f9-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="788f9-125">Политика именования префикса и суффикса может использоваться для принудительного применения фиксированных строк или атрибутов Azure AD в начале или конце имени группы и связанного с ней адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="788f9-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="788f9-126">Таким образом можно обеспечить включение, например, имен отделов или областей в имена групп.</span><span class="sxs-lookup"><span data-stu-id="788f9-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="788f9-127">Политика заблокированных слов может гарантировать, что некоторые слова, например имена руководителей, не используются в именах групп.</span><span class="sxs-lookup"><span data-stu-id="788f9-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="788f9-128">Политики именования применяются, когда группы создаются из любой из служб, подключенных к группе.</span><span class="sxs-lookup"><span data-stu-id="788f9-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="788f9-129">Если вы решите использовать политики именования для групп, см. политику [именования групп Microsoft 365.](groups-naming-policy.md)</span><span class="sxs-lookup"><span data-stu-id="788f9-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="788f9-130">Политика истечения срока действия группы</span><span class="sxs-lookup"><span data-stu-id="788f9-130">Group expiration policy</span></span>

<span data-ttu-id="788f9-131">Вы можете указать срок действия, и любая группа, достигаемая в конце этого периода и не обновляемая, будет удалена.</span><span class="sxs-lookup"><span data-stu-id="788f9-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="788f9-132">Срок действия начинается с создания группы или с даты ее последнего возобновления.</span><span class="sxs-lookup"><span data-stu-id="788f9-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="788f9-133">После истечения срока действия набора групп:</span><span class="sxs-lookup"><span data-stu-id="788f9-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="788f9-134">Владельцы группы уведомлены о возобновлении группы по мере истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="788f9-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="788f9-135">Активные группы обновляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="788f9-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="788f9-136">Любая группа, которая не обновляется, удаляется.</span><span class="sxs-lookup"><span data-stu-id="788f9-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="788f9-137">Любая удаленная группа может быть восстановлена в течение 30 дней владельцами группы или администратором.</span><span class="sxs-lookup"><span data-stu-id="788f9-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="788f9-138">Политики истечения срока действия — это хороший способ ограничить разрастаемую группу, обеспечив удаление групп, которые больше не используются.</span><span class="sxs-lookup"><span data-stu-id="788f9-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="788f9-139">Если вы хотите создать политику группового истечения срока действия, см. в [веб-сайте Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="788f9-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="788f9-140">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="788f9-140">Related topics</span></span>

[<span data-ttu-id="788f9-141">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="788f9-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="788f9-142">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="788f9-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)