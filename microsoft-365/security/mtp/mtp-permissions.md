---
title: Управление доступом к данным Microsoft 365 Defender в центре безопасности Microsoft 365
description: Узнайте, как управлять разрешениями на данные в Microsoft 365 Defender
keywords: доступ, разрешения, MTP, Защита от угроз (Майкрософт), Microsoft 365, безопасность, MCAS, MDATP, Cloud App Security, Advanced Threat Protection в Microsoft Defender, область, определение области, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3acec7b3edd60dca1befa5347cd39afa884a3c03
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222814"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="edffa-104">Управление доступом к Microsoft 365 Defender с глобальными ролями Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="edffa-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="edffa-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="edffa-105">**Applies to:**</span></span>
- <span data-ttu-id="edffa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="edffa-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="edffa-107">Существует два способа управления доступом к Защитнику Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="edffa-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="edffa-108">**Роли Глобального Azure Active Directory (Azure AD)**</span><span class="sxs-lookup"><span data-stu-id="edffa-108">**Global Azure Active Directory (Azure AD) roles**</span></span>
- <span data-ttu-id="edffa-109">**Пользовательский доступ к роли**</span><span class="sxs-lookup"><span data-stu-id="edffa-109">**Custom role access**</span></span>

<span data-ttu-id="edffa-110">Учетные записи, на которые назначены следующие **роли Global Azure AD,** могут получать доступ к функциям и данным Защитника Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="edffa-110">Accounts assigned the following **Global Azure AD roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="edffa-111">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="edffa-111">Global administrator</span></span>
- <span data-ttu-id="edffa-112">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="edffa-112">Security administrator</span></span>
- <span data-ttu-id="edffa-113">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="edffa-113">Security Operator</span></span>
- <span data-ttu-id="edffa-114">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="edffa-114">Global Reader</span></span>
- <span data-ttu-id="edffa-115">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="edffa-115">Security Reader</span></span>

<span data-ttu-id="edffa-116">Чтобы просмотреть учетные записи с этими ролями, см. раздел [Разрешения в Центре безопасности Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="edffa-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="edffa-117">**Пользовательский доступ** к роли — это новая возможность в Microsoft 365 Defender и позволяет управлять доступом к определенным данным, задачам и возможностям в Microsoft Defender 365.</span><span class="sxs-lookup"><span data-stu-id="edffa-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="edffa-118">Настраиваемые роли предоставляют больше управления, чем глобальные роли Azure AD, предоставляя пользователям только необходимый доступ с наименьшими допустимыми ролями.</span><span class="sxs-lookup"><span data-stu-id="edffa-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="edffa-119">Кроме глобальных ролей Azure AD можно создавать настраиваемые роли.</span><span class="sxs-lookup"><span data-stu-id="edffa-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="edffa-120">[Дополнительные информацию о настраиваемой роли](custom-roles.md).</span><span class="sxs-lookup"><span data-stu-id="edffa-120">[Learn more about custom roles](custom-roles.md).</span></span>

><span data-ttu-id="edffa-121">! [ПРИМЕЧАНИЕ] Эта статья применяется только к управлению глобальными ролями Azure AD.</span><span class="sxs-lookup"><span data-stu-id="edffa-121">![NOTE] This article applies only to managing global Azure AD roles.</span></span> <span data-ttu-id="edffa-122">Дополнительные сведения об использовании настраиваемого управления доступом на основе ролей см. в пользовательских ролях для управления доступом на основе [ролей.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="edffa-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="edffa-123">Доступ к функциям</span><span class="sxs-lookup"><span data-stu-id="edffa-123">Access to functionality</span></span>
<span data-ttu-id="edffa-124">Доступ к определенным функциям зависит от [роли Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="edffa-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="edffa-125">Обратитесь к глобальному администратору, если вам нужен доступ к определенным функциям, для которых вам или вашей группе пользователей требуется назначить новую роль.</span><span class="sxs-lookup"><span data-stu-id="edffa-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="edffa-126">Утверждение ожидающих автоматизированных задач</span><span class="sxs-lookup"><span data-stu-id="edffa-126">Approve pending automated tasks</span></span>
<span data-ttu-id="edffa-127">[Автоматический анализ угроз и защита от атак](mtp-autoir-actions.md) может выполнять действия с сообщениями электронной почты, пересылая правила, файлы, механизмы сохраняемости и другие артефакты, обнаруженные во время анализа.</span><span class="sxs-lookup"><span data-stu-id="edffa-127">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="edffa-128">Чтобы утвердить или отклонить ожидающие действия, требующие явного утверждения, вам необходимы определенные роли, назначенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="edffa-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="edffa-129">Дополнительные сведения см. в статье [Разрешения центра уведомлений](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="edffa-129">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="edffa-130">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="edffa-130">Access to data</span></span>
<span data-ttu-id="edffa-131">Доступ к данным Microsoft 365 Defender можно контролировать с помощью области, назначенной группам пользователей в Microsoft Defender для управления доступом на основе ролей конечных точек (RBAC).</span><span class="sxs-lookup"><span data-stu-id="edffa-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="edffa-132">Если доступ к определенному набору устройств в конечной точке Defender для конечной точки не установлен, вы будете иметь полный доступ к данным в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="edffa-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="edffa-133">Однако если область учетной записи задана, вам будут доступны только данные об устройствах в этой области.</span><span class="sxs-lookup"><span data-stu-id="edffa-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="edffa-134">Например, если вы принадлежите только к одной группе пользователей с ролью Microsoft Defender для конечной точки, и эта группа пользователей имеет доступ только к устройствам продаж, вы увидите только данные о устройствах продаж в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="edffa-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="edffa-135">Дополнительные новости о параметрах RBAC в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="edffa-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="edffa-136">Элементы управления доступом в Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="edffa-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="edffa-137">Во время предварительного просмотра Microsoft 365 Defender не применяет элементы управления доступом на основе параметров безопасности облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="edffa-137">During the preview, Microsoft 365 Defender does not enforce access controls based on Cloud App Security settings.</span></span> <span data-ttu-id="edffa-138">На доступ к данным Microsoft 365 Defender эти параметры не влияют.</span><span class="sxs-lookup"><span data-stu-id="edffa-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="edffa-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="edffa-139">Related topics</span></span>
- [<span data-ttu-id="edffa-140">Настраиваемые роли в области управления доступом на основе ролей для Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="edffa-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="edffa-141">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="edffa-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="edffa-142">Microsoft Defender для endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="edffa-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="edffa-143">Роли Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="edffa-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)