---
title: Управление удостоверениями Microsoft 365
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
description: Узнайте, как использовать функции управления удостоверениями Microsoft 365.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370350"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="04a8e-103">Управление удостоверениями Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="04a8e-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="04a8e-104">Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников.</span><span class="sxs-lookup"><span data-stu-id="04a8e-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="04a8e-105">Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.</span><span class="sxs-lookup"><span data-stu-id="04a8e-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="04a8e-106">Дополнительные сведения см. в статье [Обзор управления удостоверениями для Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="04a8e-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="04a8e-107">Настройка проверок доступа Azure AD</span><span class="sxs-lookup"><span data-stu-id="04a8e-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="04a8e-108">Проверка доступа Azure AD позволяет просматривать доступ пользователя, чтобы убедиться, что доступ к ним имеют только нужные пользователи.</span><span class="sxs-lookup"><span data-stu-id="04a8e-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="04a8e-109">Например:</span><span class="sxs-lookup"><span data-stu-id="04a8e-109">For example:</span></span>

- <span data-ttu-id="04a8e-110">При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.</span><span class="sxs-lookup"><span data-stu-id="04a8e-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="04a8e-111">Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.</span><span class="sxs-lookup"><span data-stu-id="04a8e-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="04a8e-112">Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.</span><span class="sxs-lookup"><span data-stu-id="04a8e-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="04a8e-113">Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.</span><span class="sxs-lookup"><span data-stu-id="04a8e-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="04a8e-114">Более подробную информацию можно узнать в статье [Обзор просмотров Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="04a8e-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="04a8e-115">Сведения о настройке различных типов проверок доступа см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="04a8e-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="04a8e-116">Группы и приложения</span><span class="sxs-lookup"><span data-stu-id="04a8e-116">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="04a8e-117">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="04a8e-117">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="04a8e-118">Роли ресурсов Azure</span><span class="sxs-lookup"><span data-stu-id="04a8e-118">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="04a8e-119">Настройка управления обслуживанием Azure AD</span><span class="sxs-lookup"><span data-stu-id="04a8e-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="04a8e-120">ВИХТ управления обслуживанием Azure AD можно управлять жизненным циклом удостоверений и доступом в масштабе, автоматизируя рабочие процессы запросов на доступ, назначения доступа, обзоры и срок действия.</span><span class="sxs-lookup"><span data-stu-id="04a8e-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="04a8e-121">Вашим сотрудникам требуется доступ к различным группам, приложениям и сайтам для выполнения их работы.</span><span class="sxs-lookup"><span data-stu-id="04a8e-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="04a8e-122">Управление этим доступом может быть проблематичным, так как изменяется требование, добавляются новые приложения или для пользователей требуются дополнительные права доступа.</span><span class="sxs-lookup"><span data-stu-id="04a8e-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="04a8e-123">При совместной работе с другими организациями может быть неясно, что в другой организации требуется доступ к ресурсам вашей организации, а за пределами пользователей неизвестно, какие приложения, группы или сайты используются в Организации.</span><span class="sxs-lookup"><span data-stu-id="04a8e-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="04a8e-124">Управление обслуживанием Azure AD поможет вам эффективнее управлять доступом к группам, приложениям и сайтам SharePoint для внутренних и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="04a8e-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="04a8e-125">Дополнительные сведения можно найти в статье [Обзор управления обслуживанием Azure AD](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="04a8e-125">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
