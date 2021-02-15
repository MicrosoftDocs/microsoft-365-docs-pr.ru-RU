---
title: Управление гостевим доступом в группах Microsoft 365
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
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753281"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="33033-103">Управление гостевим доступом в группах Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33033-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="33033-104">По умолчанию гостевой доступ для групп Microsoft 365 включен для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="33033-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="33033-105">Администраторы могут разрешить гостевой доступ к группам для всей организации или отдельных групп.</span><span class="sxs-lookup"><span data-stu-id="33033-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="33033-106">Если он включен, участники группы могут приглашать гостевых пользователей в группу Microsoft 365 через Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="33033-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="33033-107">Владельцу группы на утверждение отправляются приглашения.</span><span class="sxs-lookup"><span data-stu-id="33033-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="33033-108">После утверждения гостевой пользователь добавляется в каталог и группу.</span><span class="sxs-lookup"><span data-stu-id="33033-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="33033-109">Сети Yammer Корпоративный, которые находятся в режиме native или в географическом режиме [ЕС,](https://go.microsoft.com/fwlink/?linkid=2107357) не поддерживают гостей сети.</span><span class="sxs-lookup"><span data-stu-id="33033-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="33033-110">Подключенные к Microsoft 365 группы Yammer в настоящее время не поддерживают гостевой доступ, но вы можете создавать не подключенные внешние группы в сети Yammer.</span><span class="sxs-lookup"><span data-stu-id="33033-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="33033-111">Инструкции см. в инструкциях по созданию и управлению внешними группами [в Yammer.](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups)</span><span class="sxs-lookup"><span data-stu-id="33033-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="33033-112">Гостевой доступ в группах часто используется в рамках более широкого сценария, включаемого в SharePoint или Teams.</span><span class="sxs-lookup"><span data-stu-id="33033-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="33033-113">Эти службы имеют собственные параметры гостевого общего доступа.</span><span class="sxs-lookup"><span data-stu-id="33033-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="33033-114">Полные инструкции по настройке гостевого общего доступа в группах, SharePoint и Teams см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="33033-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="33033-115">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="33033-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="33033-116">Совместная работа с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="33033-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="33033-117">Управление гостевим доступом групп</span><span class="sxs-lookup"><span data-stu-id="33033-117">Manage groups guest access</span></span>

<span data-ttu-id="33033-118">Если вы хотите включить или отключить гостевой доступ в группах, это можно сделать в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33033-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="33033-119">В Центре администрирования выберите **"Показать** все параметры организации" и на вкладке "Службы" выберите группы \>  \>  **Microsoft 365.** </span><span class="sxs-lookup"><span data-stu-id="33033-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="33033-120">На странице **"Группы Microsoft 365"** выберите, хотите ли вы позволить людям за пределами вашей организации получать доступ к ресурсам группы или позволить владельцам групп добавлять в группы людей за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="33033-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="33033-121">Добавление гостей в группу Microsoft 365 из Центра администрирования</span><span class="sxs-lookup"><span data-stu-id="33033-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="33033-122">Если гость уже существует в вашем каталоге, вы можете добавить его в свои группы из Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33033-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="33033-123">В Центре администрирования перейдите на страницу   >  **"Группы групп".**</span><span class="sxs-lookup"><span data-stu-id="33033-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="33033-124">Щелкните группу, в которая нужно добавить гостя, и выберите **"Просмотреть всех** участников и управлять ими" на вкладке **"Участники".**</span><span class="sxs-lookup"><span data-stu-id="33033-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="33033-125">Выберите **"Добавить участников"** и выберите имя гостя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="33033-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="33033-126">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="33033-126">Select **Save**.</span></span>

<span data-ttu-id="33033-127">Если вы хотите добавить гостя непосредственно в каталог, вы можете добавить пользователей совместной работы [Azure Active Directory B2B на портале Azure.](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)</span><span class="sxs-lookup"><span data-stu-id="33033-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="33033-128">Если вы хотите изменить какие-либо сведения гостя, вы можете добавить или обновить данные профиля пользователя с помощью [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="33033-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="33033-129">См. также</span><span class="sxs-lookup"><span data-stu-id="33033-129">See also</span></span>

[<span data-ttu-id="33033-130">Блокировка гостевых пользователей из определенной группы</span><span class="sxs-lookup"><span data-stu-id="33033-130">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="33033-131">Управление членством в группах в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33033-131">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="33033-132">Проверки доступа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="33033-132">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="33033-133">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="33033-133">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
