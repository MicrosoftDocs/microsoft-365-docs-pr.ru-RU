---
title: Управление доступом гостей в Microsoft 365 группах
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
description: Узнайте, как добавить гостей в группу Microsoft 365, просматривать гостевых пользователей и использовать PowerShell для управления доступом гостей.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571941"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="de2cf-103">Управление доступом гостей в Microsoft 365 группах</span><span class="sxs-lookup"><span data-stu-id="de2cf-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="de2cf-104">По умолчанию для вашей организации Microsoft 365 доступ для групп гостей.</span><span class="sxs-lookup"><span data-stu-id="de2cf-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="de2cf-105">Администраторы могут контролировать, разрешать ли гостевой доступ к группам для всей организации или для отдельных групп.</span><span class="sxs-lookup"><span data-stu-id="de2cf-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="de2cf-106">Когда он включен, участники группы могут пригласить приглашенных пользователей в группу Microsoft 365 через Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="de2cf-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="de2cf-107">Приглашения отправляются владельцу группы для утверждения.</span><span class="sxs-lookup"><span data-stu-id="de2cf-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="de2cf-108">После утверждения гостевой пользователь добавляется в каталог и группу.</span><span class="sxs-lookup"><span data-stu-id="de2cf-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="de2cf-109">Yammer корпоративный сети, на которые находятся в родном режиме [или EU Geo,](/yammer/manage-security-and-compliance/manage-data-compliance) не поддерживают гостей сети.</span><span class="sxs-lookup"><span data-stu-id="de2cf-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="de2cf-110">Microsoft 365 Подключенные Yammer группы в настоящее время не поддерживают гостевой доступ, но вы можете создавать не связанные внешние группы в вашей Yammer сети.</span><span class="sxs-lookup"><span data-stu-id="de2cf-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="de2cf-111">Для [получения инструкций можно просмотреть создание и управление Yammer группами](/yammer/work-with-external-users/create-and-manage-external-groups) в других местах.</span><span class="sxs-lookup"><span data-stu-id="de2cf-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="de2cf-112">Доступ гостей в группы часто используется как часть более широкого сценария, который включает в себя SharePoint или Teams.</span><span class="sxs-lookup"><span data-stu-id="de2cf-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="de2cf-113">Эти службы имеют свои собственные настройки совместного использования гостей.</span><span class="sxs-lookup"><span data-stu-id="de2cf-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="de2cf-114">Для получения полных инструкций по настройке совместного использования гостей между группами, SharePoint и Teams см.:</span><span class="sxs-lookup"><span data-stu-id="de2cf-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="de2cf-115">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="de2cf-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="de2cf-116">Совместная работа с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="de2cf-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="de2cf-117">Управление гостевым доступом групп</span><span class="sxs-lookup"><span data-stu-id="de2cf-117">Manage groups guest access</span></span>

<span data-ttu-id="de2cf-118">Если вы хотите включить или отключить доступ гостей в группах, вы можете сделать это в Microsoft 365-центра.</span><span class="sxs-lookup"><span data-stu-id="de2cf-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="de2cf-119">В центре администратора перейдите на показ **всех настроек** org Параметры org и \>  \>  на **вкладке Услуги,** **выберите Microsoft 365 группы.**</span><span class="sxs-lookup"><span data-stu-id="de2cf-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="de2cf-120">На странице **Microsoft 365 групп выберите,** хотите ли вы, чтобы люди за пределами вашей организации доступ к групповым ресурсам или позволить владельцам групп добавлять людей за пределами вашей организации в группы.</span><span class="sxs-lookup"><span data-stu-id="de2cf-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="de2cf-121">Добавление гостей в Microsoft 365 группу из админ-центра</span><span class="sxs-lookup"><span data-stu-id="de2cf-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="de2cf-122">Если гость уже существует в вашем каталоге, вы можете добавить их в свои группы из Microsoft 365 центра.</span><span class="sxs-lookup"><span data-stu-id="de2cf-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="de2cf-123">(Группы с динамичным членством [должны управляться в Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span><span class="sxs-lookup"><span data-stu-id="de2cf-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="de2cf-124">В центре администратора перейдите на страницу **групп.**  >  </span><span class="sxs-lookup"><span data-stu-id="de2cf-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="de2cf-125">Нажмите на группу, в которую вы хотите добавить гостя, и **выберите Просмотр всех участников и управление ими** во **вкладке «Члены».**</span><span class="sxs-lookup"><span data-stu-id="de2cf-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="de2cf-126">Выберите **Add членов** и выберите имя гостя, который вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="de2cf-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="de2cf-127">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="de2cf-127">Select **Save**.</span></span>

<span data-ttu-id="de2cf-128">Если вы хотите добавить гостя в каталог напрямую, [вы можете добавить Azure Active Directory пользователей совместной работы B2B на портале Azure.](/azure/active-directory/b2b/add-users-administrator)</span><span class="sxs-lookup"><span data-stu-id="de2cf-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="de2cf-129">Если вы хотите отредактировать какую-либо информацию о госте, вы можете добавить [или обновить информацию о профиле пользователя, используя Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="de2cf-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="de2cf-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="de2cf-130">Related content</span></span>

<span data-ttu-id="de2cf-131">[Блокировка гостевых пользователей из определенной группы](../../solutions/per-group-guest-access.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="de2cf-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="de2cf-132">[Управление членством в группе Microsoft 365 центре (статья)](add-or-remove-members-from-groups.md)</span><span class="sxs-lookup"><span data-stu-id="de2cf-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="de2cf-133">[Azure Active Directory обзоры доступа](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (статья)</span><span class="sxs-lookup"><span data-stu-id="de2cf-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="de2cf-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (статья)</span><span class="sxs-lookup"><span data-stu-id="de2cf-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>