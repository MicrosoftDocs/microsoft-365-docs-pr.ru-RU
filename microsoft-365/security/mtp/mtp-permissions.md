---
title: Управление доступом к данным Защитника Microsoft 365 в Центре безопасности Microsoft 365
description: Узнайте, как управлять разрешениями на доступ к данным в Microsoft 365 Defender
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
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930142"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="43690-104">Управление доступом к Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43690-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="43690-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="43690-105">**Applies to:**</span></span>
- <span data-ttu-id="43690-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43690-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="43690-107">Учетные записи с следующими ролями Azure Active Directory (AD) могут получать доступ к функциям и данным Защитника Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="43690-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="43690-108">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="43690-108">Global administrator</span></span>
- <span data-ttu-id="43690-109">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="43690-109">Security administrator</span></span>
- <span data-ttu-id="43690-110">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="43690-110">Security Operator</span></span>
- <span data-ttu-id="43690-111">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="43690-111">Global Reader</span></span>
- <span data-ttu-id="43690-112">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="43690-112">Security Reader</span></span>

<span data-ttu-id="43690-113">Чтобы просмотреть учетные записи с этими ролями, см. раздел [Разрешения в Центре безопасности Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="43690-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="43690-114">Доступ к функциям</span><span class="sxs-lookup"><span data-stu-id="43690-114">Access to functionality</span></span>
<span data-ttu-id="43690-115">Доступ к определенным функциям зависит от [роли Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="43690-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="43690-116">Обратитесь к глобальному администратору, если вам нужен доступ к определенным функциям, для которых вам или вашей группе пользователей требуется назначить новую роль.</span><span class="sxs-lookup"><span data-stu-id="43690-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="43690-117">Утверждение ожидающих автоматизированных задач</span><span class="sxs-lookup"><span data-stu-id="43690-117">Approve pending automated tasks</span></span>
<span data-ttu-id="43690-118">[Автоматический анализ угроз и защита от атак](mtp-autoir-actions.md) может выполнять действия с сообщениями электронной почты, пересылая правила, файлы, механизмы сохраняемости и другие артефакты, обнаруженные во время анализа.</span><span class="sxs-lookup"><span data-stu-id="43690-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="43690-119">Чтобы утвердить или отклонить ожидающие действия, требующие явного утверждения, вам необходимы определенные роли, назначенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43690-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="43690-120">Дополнительные сведения см. в статье [Разрешения центра уведомлений](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="43690-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="43690-121">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="43690-121">Access to data</span></span>
<span data-ttu-id="43690-122">Доступ к данным Защитника Microsoft 365 можно контролировать с помощью области, назначенной группам пользователей в Microsoft Defender для управления доступом на основе ролей (RBAC) конечной точки.</span><span class="sxs-lookup"><span data-stu-id="43690-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="43690-123">Если область вашего доступа не была областью действия определенного набора устройств в Защитнике для конечной точки, вы будете иметь полный доступ к данным в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="43690-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="43690-124">Однако если область учетной записи задана, вам будут доступны только данные об устройствах в этой области.</span><span class="sxs-lookup"><span data-stu-id="43690-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="43690-125">Например, если вы принадлежите только к одной группе пользователей с ролью Microsoft Defender for Endpoint и этой группе пользователей предоставлен доступ только к устройствам продаж, вы увидите только данные об устройствах продаж в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="43690-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="43690-126">Узнайте больше о параметрах RBAC в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="43690-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="43690-127">Элементы управления доступом в Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="43690-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="43690-128">Во время предварительной версии Защитник Microsoft 365 не применяет элементы управления доступом на основе параметров Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="43690-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="43690-129">Эти параметры не влияют на доступ к данным Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43690-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43690-130">См. также</span><span class="sxs-lookup"><span data-stu-id="43690-130">Related topics</span></span>

- [<span data-ttu-id="43690-131">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="43690-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="43690-132">Microsoft Defender for Endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="43690-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="43690-133">Роли Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="43690-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
