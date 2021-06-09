---
title: Microsoft 365 идентификатора только для облака
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Описывает, как создавать пользователей и группы, если Microsoft 365 подписка использует идентификатор только для облака.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327931"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="7e2f1-103">Microsoft 365 идентификатора только для облака</span><span class="sxs-lookup"><span data-stu-id="7e2f1-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="7e2f1-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="7e2f1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7e2f1-105">С идентификатором только для облака все пользователи, группы и контакты хранятся в клиенте Azure Active Directory Azure AD вашей Microsoft 365 подписки.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="7e2f1-106">Вот основные компоненты идентификатора только для облака.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-106">Here are the basic components of cloud-only identity.</span></span>
 
![Основные компоненты идентификатора только для облака](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="7e2f1-108">Пользователи и их учетные записи пользователей в организациях могут быть классифицированы по ряду способов.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="7e2f1-109">Например, некоторые из них имеют статус постоянных сотрудников.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="7e2f1-110">Некоторые являются поставщиками, подрядчиками или партнерами с временным статусом.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="7e2f1-111">Кроме того, существуют внешние пользователи, у которых нет учетных записей, но которым все равно необходимо предоставить доступ к определенным службам и ресурсам в целях взаимодействия и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="7e2f1-112">Например:</span><span class="sxs-lookup"><span data-stu-id="7e2f1-112">For example:</span></span>

- <span data-ttu-id="7e2f1-113">учетные записи клиента представляют пользователей в вашей организации, которым вы предоставляете лицензии на доступ к облачным службам;</span><span class="sxs-lookup"><span data-stu-id="7e2f1-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="7e2f1-114">учетные записи типа "бизнес-бизнес" (B2B) представляют пользователей за пределами вашей организации, которых вы приглашаете принять участие в совместной работе.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="7e2f1-115">Подбирайте итоги типов пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="7e2f1-116">Как они группируются?</span><span class="sxs-lookup"><span data-stu-id="7e2f1-116">What are the groupings?</span></span> <span data-ttu-id="7e2f1-117">Например, вы можете группировать пользователей по ролям высокого уровня или обязанностям в организации.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="7e2f1-118">Кроме того, доступ к некоторым облачным службам можно предоставлять пользователям за пределами организации, у которых нет учетных записей.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-118">Additionally, some cloud services can be shared with users outside your organization without any user accounts.</span></span> <span data-ttu-id="7e2f1-119">Вам потребуется определить и эти группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-119">You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="7e2f1-120">Группы в Azure AD можно использовать для нескольких целей, и это упрощает управление облачной средой.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="7e2f1-121">Например, в группах Azure AD можно:</span><span class="sxs-lookup"><span data-stu-id="7e2f1-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="7e2f1-122">Используйте групповое лицензирование для назначения лицензий для Microsoft 365 для учетных записей пользователей автоматически, как только они будут добавлены в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="7e2f1-123">Добавьте учетные записи пользователей в определенные группы динамически на основе атрибутов учетных записей пользователей, таких как имя отдела.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="7e2f1-124">Автоматические предоставление пользователям приложений Software as a Service (SaaS) и защита доступа к этим приложениям с помощью многофакторной проверки подлинности (MFA) и других политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="7e2f1-125">Подготавливать разрешения и уровни доступа для сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7e2f1-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

## <a name="next-steps-for-cloud-only-identity"></a><span data-ttu-id="7e2f1-126">Дальнейшие действия для удостоверения только для облака</span><span class="sxs-lookup"><span data-stu-id="7e2f1-126">Next steps for cloud-only identity</span></span>

- [<span data-ttu-id="7e2f1-127">Управление учетными записями пользователей</span><span class="sxs-lookup"><span data-stu-id="7e2f1-127">Manage user accounts</span></span>](manage-microsoft-365-accounts.md)
- [<span data-ttu-id="7e2f1-128">Назначение лицензий учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="7e2f1-128">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
- [<span data-ttu-id="7e2f1-129">Управление группами и членством в группах</span><span class="sxs-lookup"><span data-stu-id="7e2f1-129">Manage groups and group membership</span></span>](manage-microsoft-365-groups.md)
- [<span data-ttu-id="7e2f1-130">Управление паролями учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="7e2f1-130">Manage user account passwords</span></span>](manage-microsoft-365-passwords.md)
