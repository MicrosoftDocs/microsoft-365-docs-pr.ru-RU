---
title: Управление удостоверением Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Узнайте, как использовать функции управления удостоверением Microsoft 365.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370350"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="83d1a-103">Управление удостоверением Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="83d1a-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="83d1a-104">Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников.</span><span class="sxs-lookup"><span data-stu-id="83d1a-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="83d1a-105">Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.</span><span class="sxs-lookup"><span data-stu-id="83d1a-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="83d1a-106">Дополнительные сведения см. в этом [обзоре управления удостоверением для Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)</span><span class="sxs-lookup"><span data-stu-id="83d1a-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="83d1a-107">Настройка проверок доступа Azure AD</span><span class="sxs-lookup"><span data-stu-id="83d1a-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="83d1a-108">Проверки доступа Azure AD позволяют вам просмотреть доступ пользователя, чтобы обеспечить постоянный доступ только нужным пользователям.</span><span class="sxs-lookup"><span data-stu-id="83d1a-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="83d1a-109">Например:</span><span class="sxs-lookup"><span data-stu-id="83d1a-109">For example:</span></span>

- <span data-ttu-id="83d1a-110">При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.</span><span class="sxs-lookup"><span data-stu-id="83d1a-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="83d1a-111">Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.</span><span class="sxs-lookup"><span data-stu-id="83d1a-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="83d1a-112">Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.</span><span class="sxs-lookup"><span data-stu-id="83d1a-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="83d1a-113">Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.</span><span class="sxs-lookup"><span data-stu-id="83d1a-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="83d1a-114">Дополнительные сведения [см. в обзоре проверок доступа.](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)</span><span class="sxs-lookup"><span data-stu-id="83d1a-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="83d1a-115">Сведения о настройке различных типов проверок доступа см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="83d1a-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="83d1a-116">Группы и приложения</span><span class="sxs-lookup"><span data-stu-id="83d1a-116">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="83d1a-117">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="83d1a-117">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="83d1a-118">Роли ресурсов Azure</span><span class="sxs-lookup"><span data-stu-id="83d1a-118">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="83d1a-119">Настройка управления правами Azure AD</span><span class="sxs-lookup"><span data-stu-id="83d1a-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="83d1a-120">Управление правами Wiht в Azure AD. Вы можете управлять жизненным циклом удостоверений и доступа в масштабе путем автоматизации рабочего процесса запроса доступа, назначений доступа, отзывов и истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="83d1a-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="83d1a-121">Сотрудникам нужен доступ к различным группам, приложениям и сайтам для выполнения своей работы.</span><span class="sxs-lookup"><span data-stu-id="83d1a-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="83d1a-122">Управление этим доступом может быть сложной задачей, так как требования меняются, добавляются новые приложения или пользователям требуются дополнительные права доступа.</span><span class="sxs-lookup"><span data-stu-id="83d1a-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="83d1a-123">При совместной работе с другими организациями вы можете не знать, кому из других организаций нужен доступ к ресурсам вашей организации, а внешние пользователи не будут знать, какие приложения, группы или сайты использует ваша организация.</span><span class="sxs-lookup"><span data-stu-id="83d1a-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="83d1a-124">Управление правами Azure AD позволяет более эффективно управлять доступом к группам, приложениям и сайтам SharePoint для внутренних и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="83d1a-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="83d1a-125">Дополнительные сведения см. в обзоре управления правами [Azure AD.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)</span><span class="sxs-lookup"><span data-stu-id="83d1a-125">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
