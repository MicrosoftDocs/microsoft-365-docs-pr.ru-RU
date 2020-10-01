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
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328546"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="bbbb1-103">Управление удостоверениями Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bbbb1-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="bbbb1-104">Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="bbbb1-105">Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="bbbb1-106">Дополнительные сведения см. в статье [Обзор управления удостоверениями для Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="bbbb1-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="bbbb1-107">Настройка проверок доступа Azure AD</span><span class="sxs-lookup"><span data-stu-id="bbbb1-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="bbbb1-108">Проверка доступа Azure AD позволяет просматривать доступ пользователя, чтобы убедиться, что доступ к ним имеют только нужные пользователи.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="bbbb1-109">Например:</span><span class="sxs-lookup"><span data-stu-id="bbbb1-109">For example:</span></span>

- <span data-ttu-id="bbbb1-110">При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="bbbb1-111">Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="bbbb1-112">Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="bbbb1-113">Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="bbbb1-114">Более подробную информацию можно узнать в статье [Обзор просмотров Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="bbbb1-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="bbbb1-115">Azure AD Privileged Identity Management (PIM) предоставляет целый ряд средств управления, предназначенных для защиты прав доступа к ресурсам в AAD, Azure и других облачных службах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-115">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="bbbb1-116">Azure AD PIM предоставляет полный набор средств управления, помогающих защитить ресурсы компании, такие как каталог, Office 365 и роли ресурсов Azure.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-116">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="bbbb1-117">Как и для других видов доступа, с помощью проверок доступа можно настроить регулярные сертификации прав доступа для всех пользователей с ролями администратора.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-117">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="bbbb1-118">Служба Azure AD PIM доступна только в версии E5 Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-118">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="bbbb1-119">Сведения о настройке различных типов проверок доступа см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="bbbb1-119">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="bbbb1-120">Группы и приложения</span><span class="sxs-lookup"><span data-stu-id="bbbb1-120">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="bbbb1-121">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="bbbb1-121">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="bbbb1-122">Роли ресурсов Azure</span><span class="sxs-lookup"><span data-stu-id="bbbb1-122">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="bbbb1-123">Настройка управления обслуживанием Azure AD</span><span class="sxs-lookup"><span data-stu-id="bbbb1-123">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="bbbb1-124">ВИХТ управления обслуживанием Azure AD можно управлять жизненным циклом удостоверений и доступом в масштабе, автоматизируя рабочие процессы запросов на доступ, назначения доступа, обзоры и срок действия.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-124">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="bbbb1-125">Вашим сотрудникам требуется доступ к различным группам, приложениям и сайтам для выполнения их работы.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-125">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="bbbb1-126">Управление этим доступом может быть проблематичным, так как изменяется требование, добавляются новые приложения или для пользователей требуются дополнительные права доступа.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-126">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="bbbb1-127">При совместной работе с другими организациями может быть неясно, что в другой организации требуется доступ к ресурсам вашей организации, а за пределами пользователей неизвестно, какие приложения, группы или сайты используются в Организации.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-127">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="bbbb1-128">Управление обслуживанием Azure AD поможет вам эффективнее управлять доступом к группам, приложениям и сайтам SharePoint для внутренних и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-128">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="bbbb1-129">Дополнительные сведения можно найти в статье [Обзор управления обслуживанием Azure AD](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="bbbb1-129">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
