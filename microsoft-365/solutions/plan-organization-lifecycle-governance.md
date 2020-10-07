---
title: Планирование управления Организацией и жизненным циклом для групп Microsoft 365 и Microsoft Teams
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
description: Экономичность параметров управления жизненным циклом средств для совместной работы в Microsoft 365
ms.openlocfilehash: 706f1aaecf22c4088d4539c208fef68320c5e710
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377191"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="f0556-103">Планирование управления Организацией и жизненным циклом для групп Microsoft 365 и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0556-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="f0556-104">Группы Microsoft 365 имеют богатый набор средств для реализации возможностей управления, необходимых вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f0556-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="f0556-105">В следующем разделе описываются возможности, рекомендации и приводятся инструкции по заданию нужных вопросов для определения требований к управлению и способов их выполнения.</span><span class="sxs-lookup"><span data-stu-id="f0556-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="f0556-106">Контроль пользователей, которые могут создавать группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0556-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="f0556-107">Группы могут создаваться конечными пользователями из нескольких конечных точек, в том числе Outlook, SharePoint, Teams и других сред.</span><span class="sxs-lookup"><span data-stu-id="f0556-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![изображение DESC](../media/04.png)

<span data-ttu-id="f0556-109">Мы настоятельно рекомендуем самообслуживания для поддержки владельцев групп и упрощения работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="f0556-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="f0556-110">Ограничение создания групп и групп может замедлить работу пользователей, так как многие службы Microsoft 365 требуют, чтобы группы создавались для нормальной работы службы.</span><span class="sxs-lookup"><span data-stu-id="f0556-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="f0556-111">Рассмотрите следующие возможности управления для создания групп:</span><span class="sxs-lookup"><span data-stu-id="f0556-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="f0556-112">Чтобы ограничить количество групп, используйте [политики истечения срока действия](microsoft-365-groups-expiration-policy.md) для автоматического удаления неиспользуемых групп.</span><span class="sxs-lookup"><span data-stu-id="f0556-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="f0556-113">Ограничьте создание групп членами групп безопасности, включающих [динамическое членство](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) , например всех сотрудников с полной занятостью.</span><span class="sxs-lookup"><span data-stu-id="f0556-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="f0556-114">Ограничьте создание группы группой безопасности и попросите пользователей завершить обучение в политиках использования группы в вашей организации, чтобы стать членами группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f0556-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="f0556-115">Если вы хотите ограничить круг пользователей, которые могут создавать группы, ознакомьтесь со статьей [Управление пользователями, которые могут создавать группы Microsoft 365,](manage-creation-of-groups.md) чтобы узнать, как настроить эту конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f0556-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="f0556-116">Удаление, восстановление и архивация групп</span><span class="sxs-lookup"><span data-stu-id="f0556-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="f0556-117">По умолчанию при удалении группы Microsoft 365 она сохраняется в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f0556-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="f0556-118">Этот период называется обратимым удалением, так как вы по-прежнему можете восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="f0556-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="f0556-119">Через 30 дней группа и ее контент окончательно удаляются, и их невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="f0556-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="f0556-120">Если у вас есть политики хранения для сохранения чата, файлов или почты, эти элементы будут сохранены после удаления группы.</span><span class="sxs-lookup"><span data-stu-id="f0556-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="f0556-121">Дополнительные сведения [о политиках хранения](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) см.</span><span class="sxs-lookup"><span data-stu-id="f0556-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="f0556-122">Если вы хотите удалить группу, но сохранить контент из одной или нескольких служб, подключенных к группе, обратитесь к разделу [Архивные группы, Teams и Yammer](end-life-cycle-groups-teams-sites-yammer.md) для получения сведений.</span><span class="sxs-lookup"><span data-stu-id="f0556-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="f0556-123">Политика именования групп</span><span class="sxs-lookup"><span data-stu-id="f0556-123">Group naming policy</span></span>

<span data-ttu-id="f0556-124">Политика именования групп помогает управлять группами двумя способами:</span><span class="sxs-lookup"><span data-stu-id="f0556-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="f0556-125">Политику именования префиксов и суффиксов можно использовать для принудительного применения фиксированных строк или атрибутов Azure AD в начале или конце имени группы и сопоставленного адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f0556-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="f0556-126">Таким образом вы можете гарантировать включение, например, названий отделов или регионов в именах групп.</span><span class="sxs-lookup"><span data-stu-id="f0556-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="f0556-127">Политика заблокированных слов позволяет гарантировать, что определенные слова, например имена руководителей, не будут использоваться в именах групп.</span><span class="sxs-lookup"><span data-stu-id="f0556-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="f0556-128">Политики именования применяются при создании групп из любой из служб, подключенных к группе.</span><span class="sxs-lookup"><span data-stu-id="f0556-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="f0556-129">Если вы решили использовать политики именования для групп, ознакомьтесь со статьей [Политика именования групп Microsoft 365](groups-naming-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f0556-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="f0556-130">Политика истечения срока действия групп</span><span class="sxs-lookup"><span data-stu-id="f0556-130">Group expiration policy</span></span>

<span data-ttu-id="f0556-131">Вы можете указать срок действия и группу, которые достигают конца этого периода и не будут обновляться.</span><span class="sxs-lookup"><span data-stu-id="f0556-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="f0556-132">Срок действия начинается с момента создания группы или даты ее последнего продления.</span><span class="sxs-lookup"><span data-stu-id="f0556-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="f0556-133">После того как вы настроили срок действия групп, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f0556-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="f0556-134">Владельцы группы уведомляются о необходимости продления срока действия группы в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="f0556-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="f0556-135">Активные группы обновляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="f0556-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="f0556-136">Все необновленные группы удаляются.</span><span class="sxs-lookup"><span data-stu-id="f0556-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="f0556-137">Любую удаленную группу можно восстановить в течение 30 дней с помощью владельца группы или администратора.</span><span class="sxs-lookup"><span data-stu-id="f0556-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="f0556-138">Политики истечения срока действия являются хорошим способом ограничения числа групп, что позволяет удалять группы, которые больше не используются.</span><span class="sxs-lookup"><span data-stu-id="f0556-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="f0556-139">Если вы хотите создать политику истечения срока действия групп, ознакомьтесь со статьей " [политика истечения срока действия групп Microsoft 365](microsoft-365-groups-expiration-policy.md)".</span><span class="sxs-lookup"><span data-stu-id="f0556-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>
