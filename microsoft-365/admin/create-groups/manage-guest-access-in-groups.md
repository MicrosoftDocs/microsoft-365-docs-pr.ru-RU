---
title: Управление гостевым доступом в группах Microsoft 365
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
description: Узнайте, как добавлять гостей в группу Microsoft 365, просматривать гостевых пользователей и использовать PowerShell для управления гостевым доступом.
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753281"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="be81f-103">Управление гостевым доступом в группах Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="be81f-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="be81f-104">По умолчанию для вашей организации включен гостевой доступ для групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="be81f-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="be81f-105">Администраторы могут контролировать, разрешено ли гостевой доступ к группам для всей организации или для отдельных групп.</span><span class="sxs-lookup"><span data-stu-id="be81f-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="be81f-106">Когда она включена, участники группы могут приглашать гостевых пользователей в группу Microsoft 365 с помощью Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="be81f-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="be81f-107">Приглашения отправляются владельцу группы для утверждения.</span><span class="sxs-lookup"><span data-stu-id="be81f-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="be81f-108">После утверждения пользователь-гость добавляется в каталог и группу.</span><span class="sxs-lookup"><span data-stu-id="be81f-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="be81f-109">Сети Yammer Enterprise, которые находятся в собственном режиме или в [географическом формате ЕС](https://go.microsoft.com/fwlink/?linkid=2107357) , не поддерживают гостевые сети.</span><span class="sxs-lookup"><span data-stu-id="be81f-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="be81f-110">Microsoft 365 подключенные группы Yammer в настоящее время не поддерживают гостевой доступ, но вы можете создавать неподключенные внешние группы в сети Yammer.</span><span class="sxs-lookup"><span data-stu-id="be81f-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="be81f-111">Инструкции по [созданию и управлению внешними группами в Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) .</span><span class="sxs-lookup"><span data-stu-id="be81f-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="be81f-112">Гостевой доступ в группах часто используется в составе более широкого сценария, включающего SharePoint или Teams.</span><span class="sxs-lookup"><span data-stu-id="be81f-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="be81f-113">Эти службы имеют собственные параметры общего доступа к гостям.</span><span class="sxs-lookup"><span data-stu-id="be81f-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="be81f-114">Для получения полных инструкций по настройке общего доступа к гостевым компьютерам в группах, SharePoint и Teams, ознакомьтесь со статьей:</span><span class="sxs-lookup"><span data-stu-id="be81f-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="be81f-115">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="be81f-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="be81f-116">Совместная работа с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="be81f-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="be81f-117">Управление группами гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="be81f-117">Manage groups guest access</span></span>

<span data-ttu-id="be81f-118">Если вы хотите включить или отключить гостевой доступ в группах, это можно сделать в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="be81f-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="be81f-119">В центре администрирования перейдите в раздел **Показать все** \> **Параметры** \> **организационных параметров** и на вкладке **службы** выберите пункт **Microsoft 365 группы**.</span><span class="sxs-lookup"><span data-stu-id="be81f-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="be81f-120">На странице " **группы Microsoft 365** " выберите, следует ли разрешить пользователям, не входящим в организацию, получать доступ к ресурсам группы или разрешить владельцам групп добавлять людей вне Организации в группы.</span><span class="sxs-lookup"><span data-stu-id="be81f-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="be81f-121">Добавление гостей в группу Microsoft 365 из центра администрирования</span><span class="sxs-lookup"><span data-stu-id="be81f-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="be81f-122">Если гость уже существует в вашем каталоге, вы можете добавить их в свои группы из центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="be81f-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="be81f-123">В центре администрирования перейдите на **Groups**  >  страницу**группы** группы.</span><span class="sxs-lookup"><span data-stu-id="be81f-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="be81f-124">Щелкните группу, в которую требуется добавить гостя, и выберите **Просмотреть все и управлять участниками** на вкладке **Участники** .</span><span class="sxs-lookup"><span data-stu-id="be81f-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="be81f-125">Нажмите кнопку **Добавить участников**и выберите имя гостя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="be81f-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="be81f-126">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="be81f-126">Select **Save**.</span></span>

<span data-ttu-id="be81f-127">Если вы хотите добавить гостя в каталог напрямую, вы можете [Добавить пользователей службы совместной работы Azure Active Directory на портале Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="be81f-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="be81f-128">Если вы хотите изменить любую информацию гостя, вы можете [Добавить или обновить сведения о профиле пользователя с помощью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="be81f-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="be81f-129">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="be81f-129">See also</span></span>

[<span data-ttu-id="be81f-130">Блокировка гостевых пользователей из определенной группы</span><span class="sxs-lookup"><span data-stu-id="be81f-130">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="be81f-131">Управление членством в группах в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="be81f-131">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="be81f-132">Проверка доступа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="be81f-132">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="be81f-133">Set — AzureADUser</span><span class="sxs-lookup"><span data-stu-id="be81f-133">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
