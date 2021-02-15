---
title: Планирование управления организацией и жизненным циклом для групп Microsoft 365 и Microsoft Teams
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
description: Не подумайте о вариантах управления жизненным циклом для средств совместной работы в Microsoft 365
ms.openlocfilehash: 4d779701d241fc7178ab759063be1b8cdf2e960c
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613024"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="da961-103">Планирование управления организацией и жизненным циклом для групп Microsoft 365 и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da961-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="da961-104">В группах Microsoft 365 имеется богатый набор средств для реализации возможностей управления, необходимых для организации.</span><span class="sxs-lookup"><span data-stu-id="da961-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="da961-105">В следующем разделе описываются возможности, рекомендации и рекомендоваться ответы на правильные вопросы для определения требований к управлению и их удовлетворения.</span><span class="sxs-lookup"><span data-stu-id="da961-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="da961-106">Управление тем, кто может создавать группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da961-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="da961-107">Пользователи могут создавать группы из нескольких конечных точек, включая Outlook, SharePoint, Teams и другие среды.</span><span class="sxs-lookup"><span data-stu-id="da961-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![image desc](../media/04.png)

<span data-ttu-id="da961-109">Мы настоятельно рекомендуем использовать самообслуживляцию, чтобы помочь владельцам групп и упростят пользователям работу.</span><span class="sxs-lookup"><span data-stu-id="da961-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="da961-110">Ограничение создания групп и групп может замедлить производительность пользователей, так как многие службы Microsoft 365 требуют создания групп для работы службы.</span><span class="sxs-lookup"><span data-stu-id="da961-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="da961-111">Рассмотрите следующие варианты управления созданием групп:</span><span class="sxs-lookup"><span data-stu-id="da961-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="da961-112">Чтобы ограничить спрайт групп, используйте политики истечения срока действия групп, чтобы автоматически удалять группы, которые не используются. [](microsoft-365-groups-expiration-policy.md)</span><span class="sxs-lookup"><span data-stu-id="da961-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="da961-113">Ограничить создание группы участниками групп безопасности с [динамическим](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) членством, содержащим, например, всех сотрудников, работающих в режиме полного времени.</span><span class="sxs-lookup"><span data-stu-id="da961-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="da961-114">Ограничьте создание группы группой безопасности и требуйте от пользователей пройти обучение в политиках использования групп в организации, чтобы стать членами группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="da961-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="da961-115">Если вы хотите ограничить пользователей, которые могут создавать группы, см. статью "Управление тем, кто может создавать группы [Microsoft 365".](manage-creation-of-groups.md)</span><span class="sxs-lookup"><span data-stu-id="da961-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="da961-116">Group delete, restore, and archiving</span><span class="sxs-lookup"><span data-stu-id="da961-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="da961-117">При удалении группы Microsoft 365 она по умолчанию сохраняется в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="da961-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="da961-118">Этот период называется обратимым удалением, так как вы по-прежнему можете восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="da961-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="da961-119">Через 30 дней группа и ее контент окончательно удаляются, и их невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="da961-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="da961-120">Если у вас есть политики хранения для хранения чата, файлов или почты, эти элементы будут сохранены после удаления группы.</span><span class="sxs-lookup"><span data-stu-id="da961-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="da961-121">Подробные [сведения см. в](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) сведениях о политиках хранения.</span><span class="sxs-lookup"><span data-stu-id="da961-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="da961-122">Если вы хотите удалить группу, но сохранить контент из одной или более служб, подключенных к группе, см. сведения о группах архивов, командах и [Yammer.](end-life-cycle-groups-teams-sites-yammer.md)</span><span class="sxs-lookup"><span data-stu-id="da961-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="da961-123">Политика именования групп</span><span class="sxs-lookup"><span data-stu-id="da961-123">Group naming policy</span></span>

<span data-ttu-id="da961-124">Политика именования групп может помочь вам управлять группами двумя способами:</span><span class="sxs-lookup"><span data-stu-id="da961-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="da961-125">Политику именования префиксов и суффиксов можно использовать для принудительного применения фиксированных строк или атрибутов Azure AD в начале или конце имени группы и связанного с ней адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="da961-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="da961-126">Таким образом можно обеспечить включение, например, названий отделов или областей в имена групп.</span><span class="sxs-lookup"><span data-stu-id="da961-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="da961-127">Политика заблокированных слов позволяет гарантировать, что определенные слова, например имена руководителей, не будут использоваться в именах групп.</span><span class="sxs-lookup"><span data-stu-id="da961-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="da961-128">Политики именования применяются, когда группы создаются из любой службы, подключенной к группе.</span><span class="sxs-lookup"><span data-stu-id="da961-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="da961-129">Если вы решили использовать политики именования для групп, см. политику именования [групп Microsoft 365.](groups-naming-policy.md)</span><span class="sxs-lookup"><span data-stu-id="da961-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="da961-130">Политика срока действия группы</span><span class="sxs-lookup"><span data-stu-id="da961-130">Group expiration policy</span></span>

<span data-ttu-id="da961-131">Вы можете указать срок действия, и любая группа, которая достигнет конца этого периода и не будет продлена, будет удалена.</span><span class="sxs-lookup"><span data-stu-id="da961-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="da961-132">Срок действия начинается с создания группы или с даты последнего продления.</span><span class="sxs-lookup"><span data-stu-id="da961-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="da961-133">После того как вы настроим срок действия групп:</span><span class="sxs-lookup"><span data-stu-id="da961-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="da961-134">Владельцы группы будут уведомлены о продлении группы по окончании срока действия.</span><span class="sxs-lookup"><span data-stu-id="da961-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="da961-135">Активные группы обновляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="da961-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="da961-136">Любая группа, которая не продлевается, удаляется.</span><span class="sxs-lookup"><span data-stu-id="da961-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="da961-137">Все удаленные группы могут быть восстановлены владельцами или администраторами группы в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="da961-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="da961-138">Политики истечения срока действия — это хороший способ ограничить спрайт групп, обеспечив удаление групп, которые больше не используются.</span><span class="sxs-lookup"><span data-stu-id="da961-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="da961-139">Если вы хотите создать политику срока действия группы, см. политику срока действия группы [Microsoft 365.](microsoft-365-groups-expiration-policy.md)</span><span class="sxs-lookup"><span data-stu-id="da961-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="da961-140">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="da961-140">Related topics</span></span>

[<span data-ttu-id="da961-141">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="da961-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="da961-142">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="da961-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)
