---
title: Управление доступом к Microsoft 365 Defender данным в центре Microsoft 365 безопасности
description: Узнайте, как управлять разрешениями на данные в Microsoft 365 Defender
keywords: доступ, разрешения, Microsoft 365 Defender, M365, безопасность, MCAS, Cloud App Security, Microsoft Defender для конечной точки, область, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 738315c446fd57d4cd027de92eb77b0029f84323
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177534"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="d937a-104">Управление доступом к Microsoft 365 Defender с Azure Active Directory глобальными ролями</span><span class="sxs-lookup"><span data-stu-id="d937a-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d937a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d937a-105">**Applies to:**</span></span>
- <span data-ttu-id="d937a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d937a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d937a-107">Существует два способа управления доступом к Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d937a-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="d937a-108">**Роли Azure Active Directory (AD)**</span><span class="sxs-lookup"><span data-stu-id="d937a-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="d937a-109">**Пользовательский доступ к роли**</span><span class="sxs-lookup"><span data-stu-id="d937a-109">**Custom role access**</span></span>

<span data-ttu-id="d937a-110">Учетные записи, задав следующие роли **глобальной Azure Active Directory (AD),** могут получать доступ к Microsoft 365 Defender и данным:</span><span class="sxs-lookup"><span data-stu-id="d937a-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="d937a-111">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="d937a-111">Global administrator</span></span>
- <span data-ttu-id="d937a-112">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="d937a-112">Security administrator</span></span>
- <span data-ttu-id="d937a-113">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="d937a-113">Security Operator</span></span>
- <span data-ttu-id="d937a-114">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="d937a-114">Global Reader</span></span>
- <span data-ttu-id="d937a-115">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="d937a-115">Security Reader</span></span>

<span data-ttu-id="d937a-116">Чтобы просмотреть учетные записи с этими ролями, см. раздел [Разрешения в Центре безопасности Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="d937a-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="d937a-117">**Пользовательский** доступ к роли — это новая возможность в Microsoft 365 Defender и позволяет управлять доступом к определенным данным, задачам и возможностям в Microsoft Defender 365.</span><span class="sxs-lookup"><span data-stu-id="d937a-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="d937a-118">Настраиваемые роли предоставляют больше управления, чем глобальные роли Azure AD, предоставляя пользователям только необходимый доступ с наименьшими допустимыми ролями.</span><span class="sxs-lookup"><span data-stu-id="d937a-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="d937a-119">Кроме глобальных ролей Azure AD можно создавать настраиваемые роли.</span><span class="sxs-lookup"><span data-stu-id="d937a-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="d937a-120">[Дополнительные информацию о настраиваемой роли](custom-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d937a-120">[Learn more about custom roles](custom-roles.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d937a-121">Эта статья применяется только к управлению глобальными Azure Active Directory ролей.</span><span class="sxs-lookup"><span data-stu-id="d937a-121">This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="d937a-122">Дополнительные сведения об использовании настраиваемого управления доступом на основе ролей см. в пользовательских ролях для управления доступом на основе [ролей.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d937a-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="d937a-123">Доступ к функциям</span><span class="sxs-lookup"><span data-stu-id="d937a-123">Access to functionality</span></span>
<span data-ttu-id="d937a-124">Доступ к определенным функциям зависит от [роли Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="d937a-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="d937a-125">Обратитесь к глобальному администратору, если вам нужен доступ к определенным функциям, для которых вам или вашей группе пользователей требуется назначить новую роль.</span><span class="sxs-lookup"><span data-stu-id="d937a-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="d937a-126">Утверждение ожидающих автоматизированных задач</span><span class="sxs-lookup"><span data-stu-id="d937a-126">Approve pending automated tasks</span></span>
<span data-ttu-id="d937a-127">[Автоматический анализ угроз и защита от атак](m365d-autoir-actions.md) может выполнять действия с сообщениями электронной почты, пересылая правила, файлы, механизмы сохраняемости и другие артефакты, обнаруженные во время анализа.</span><span class="sxs-lookup"><span data-stu-id="d937a-127">[Automated investigation and remediation](m365d-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="d937a-128">Чтобы утвердить или отклонить ожидающие действия, требующие явного утверждения, вам необходимы определенные роли, назначенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d937a-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="d937a-129">Дополнительные сведения см. в статье [Разрешения центра уведомлений](m365d-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="d937a-129">To learn more, see [Action center permissions](m365d-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="d937a-130">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="d937a-130">Access to data</span></span>
<span data-ttu-id="d937a-131">Доступ к Microsoft 365 Defender данным можно контролировать с помощью области, назначенной группам пользователей в Microsoft Defender для управления доступом на основе ролей конечных точек (RBAC).</span><span class="sxs-lookup"><span data-stu-id="d937a-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="d937a-132">Если доступ к определенному набору устройств в конечной точке Defender для конечной точки не был областью охвата, вы будете иметь полный доступ к данным в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d937a-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="d937a-133">Однако если область учетной записи задана, вам будут доступны только данные об устройствах в этой области.</span><span class="sxs-lookup"><span data-stu-id="d937a-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="d937a-134">Например, если вы принадлежите только к одной группе пользователей с ролью Microsoft Defender для конечной точки и эта группа пользователей имеет доступ только к устройствам продаж, в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d937a-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="d937a-135">Дополнительные новости о параметрах RBAC в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d937a-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="d937a-136">Элементы управления доступом в Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d937a-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="d937a-137">Во время предварительного просмотра Microsoft 365 Defender не применяет элементы управления доступом на основе Cloud App Security параметров.</span><span class="sxs-lookup"><span data-stu-id="d937a-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="d937a-138">Доступ к Microsoft 365 Defender данным не зависит от этих параметров.</span><span class="sxs-lookup"><span data-stu-id="d937a-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d937a-139">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="d937a-139">Related topics</span></span>
- [<span data-ttu-id="d937a-140">Настраиваемые роли в области управления доступом на основе ролей для Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d937a-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="d937a-141">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="d937a-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="d937a-142">Microsoft Defender для endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="d937a-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="d937a-143">Роли Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d937a-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)
