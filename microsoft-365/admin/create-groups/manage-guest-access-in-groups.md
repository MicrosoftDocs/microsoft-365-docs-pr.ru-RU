---
title: Управление гостевых доступом в группах Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Узнайте, как добавлять гостей в группу Microsoft 365, просматривать гостевых пользователей и управлять гостевим доступом с помощью PowerShell.
ms.openlocfilehash: 114fc1b5262f1632c7e7a8d1aa339c2470223288
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908610"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="a9913-103">Управление гостевых доступом в группах Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9913-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="a9913-104">По умолчанию для групп Microsoft 365 включен гостевой доступ для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a9913-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="a9913-105">Администраторы могут контролировать, разрешить ли гостевой доступ к группам для всей организации или для отдельных групп.</span><span class="sxs-lookup"><span data-stu-id="a9913-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="a9913-106">После его включив, участники группы могут приглашать гостевых пользователей в группу Microsoft 365 через Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a9913-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="a9913-107">Приглашения отправляются владельцу группы для утверждения.</span><span class="sxs-lookup"><span data-stu-id="a9913-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="a9913-108">После утверждения гостевой пользователь добавляется в каталог и группу.</span><span class="sxs-lookup"><span data-stu-id="a9913-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="a9913-109">Сети Yammer Enterprise, которые находятся в родном режиме или [в Eu Geo,](/yammer/manage-security-and-compliance/manage-data-compliance) не поддерживают гостей сети.</span><span class="sxs-lookup"><span data-stu-id="a9913-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="a9913-110">В настоящее время группы подключенных yammer Microsoft 365 не поддерживают гостевой доступ, но в сети Yammer можно создавать внешние группы, не связанные с подключением.</span><span class="sxs-lookup"><span data-stu-id="a9913-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="a9913-111">Дополнительные инструкции см. в инструкциях По созданию и управлению внешними группами [в Yammer.](/yammer/work-with-external-users/create-and-manage-external-groups)</span><span class="sxs-lookup"><span data-stu-id="a9913-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="a9913-112">Гостевой доступ в группах часто используется в рамках более широкого сценария, который включает SharePoint или Teams.</span><span class="sxs-lookup"><span data-stu-id="a9913-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="a9913-113">Эти службы имеют собственные параметры гостевых обменов.</span><span class="sxs-lookup"><span data-stu-id="a9913-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="a9913-114">Полные инструкции по настройке гостевых обменов между группами, SharePoint и Teams см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="a9913-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="a9913-115">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="a9913-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="a9913-116">Совместная работа с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="a9913-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="a9913-117">Управление гостевом доступом групп</span><span class="sxs-lookup"><span data-stu-id="a9913-117">Manage groups guest access</span></span>

<span data-ttu-id="a9913-118">Если вы хотите включить или отключить гостевой доступ в группах, вы можете сделать это в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9913-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="a9913-119">В центре администрирования  перейдите к демонстрации всех параметров параметров Org и на вкладке \>  \>  **Services** выберите **группы Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="a9913-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="a9913-120">На странице **Microsoft 365 Groups** выберите, хотите ли вы позволить людям, не входим в ресурсы группы организации, или позволить владельцам групп добавлять людей за пределами организации в группы.</span><span class="sxs-lookup"><span data-stu-id="a9913-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="a9913-121">Добавление гостей в группу Microsoft 365 из центра администрирования</span><span class="sxs-lookup"><span data-stu-id="a9913-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="a9913-122">Если гость уже существует в каталоге, его можно добавить в группы из центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9913-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="a9913-123">(Группы с динамическим членством должны управляться [в Azure Active Directory.)](/azure/active-directory/enterprise-users/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="a9913-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="a9913-124">В центре администрирования перейдите на страницу **Группы**  >  **групп.**</span><span class="sxs-lookup"><span data-stu-id="a9913-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="a9913-125">Щелкните группу, в которая нужно добавить гостя, и выберите **Просмотр** всех участников и управление ими на **вкладке Члены.**</span><span class="sxs-lookup"><span data-stu-id="a9913-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="a9913-126">Выберите **Добавить участников** и выбрать имя гостя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="a9913-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="a9913-127">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a9913-127">Select **Save**.</span></span>

<span data-ttu-id="a9913-128">Если вы хотите напрямую добавить гостя в каталог, вы можете добавить пользователей совместной работы [Azure Active Directory B2B на портале Azure.](/azure/active-directory/b2b/add-users-administrator)</span><span class="sxs-lookup"><span data-stu-id="a9913-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="a9913-129">Если вы хотите изменить любую информацию гостя, вы можете добавить или обновить сведения о профиле пользователя с [помощью Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="a9913-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="a9913-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a9913-130">See also</span></span>

[<span data-ttu-id="a9913-131">Блокировка гостевых пользователей из определенной группы</span><span class="sxs-lookup"><span data-stu-id="a9913-131">Block guest users from a specific group</span></span>](../../solutions/per-group-guest-access.md)

[<span data-ttu-id="a9913-132">Управление членством в группе в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9913-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="a9913-133">Обзоры доступа к Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a9913-133">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="a9913-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="a9913-134">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)