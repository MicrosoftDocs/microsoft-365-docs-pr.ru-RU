---
title: Управление доступом к данным Защиты от угроз (Майкрософт) в Центре безопасности Microsoft 365
description: Сведения об управлении разрешениями для данных Защиты от угроз (Майкрософт)
keywords: доступ, разрешения, MTP, Защита от угроз (Майкрософт), Microsoft 365, безопасность, MCAS, MDATP, Cloud App Security, Advanced Threat Protection в Microsoft Defender, область, определение области, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f747737fc94241ca5f65ad9881715f517d5fbe3c
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773843"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="cad1d-104">Управление доступом к службе Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="cad1d-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="cad1d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cad1d-105">**Applies to:**</span></span>
- <span data-ttu-id="cad1d-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="cad1d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cad1d-107">Доступ к данным и функциям Защиты от угроз (Майкрософт) имеют учетные записи, которым назначены следующие роли Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="cad1d-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="cad1d-108">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="cad1d-108">Global administrator</span></span>
- <span data-ttu-id="cad1d-109">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="cad1d-109">Security administrator</span></span>
- <span data-ttu-id="cad1d-110">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="cad1d-110">Security Operator</span></span>
- <span data-ttu-id="cad1d-111">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="cad1d-111">Global Reader</span></span>
- <span data-ttu-id="cad1d-112">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="cad1d-112">Security Reader</span></span>

<span data-ttu-id="cad1d-113">Чтобы просмотреть учетные записи с этими ролями, см. раздел [Разрешения в Центре безопасности Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="cad1d-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="cad1d-114">Доступ к функциям</span><span class="sxs-lookup"><span data-stu-id="cad1d-114">Access to functionality</span></span>
<span data-ttu-id="cad1d-115">Доступ к определенным функциям зависит от [роли Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="cad1d-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="cad1d-116">Обратитесь к глобальному администратору, если вам нужен доступ к определенным функциям, для которых вам или вашей группе пользователей требуется назначить новую роль.</span><span class="sxs-lookup"><span data-stu-id="cad1d-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="cad1d-117">Утверждение ожидающих автоматизированных задач</span><span class="sxs-lookup"><span data-stu-id="cad1d-117">Approve pending automated tasks</span></span>
<span data-ttu-id="cad1d-118">[Автоматический анализ угроз и защита от атак](mtp-autoir-actions.md) может выполнять действия с сообщениями электронной почты, пересылая правила, файлы, механизмы сохраняемости и другие артефакты, обнаруженные во время анализа.</span><span class="sxs-lookup"><span data-stu-id="cad1d-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="cad1d-119">Чтобы утвердить или отклонить ожидающие действия, требующие явного утверждения, вам необходимы определенные роли, назначенные в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cad1d-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="cad1d-120">Дополнительные сведения см. в статье [Разрешения центра уведомлений](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="cad1d-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="cad1d-121">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="cad1d-121">Access to data</span></span>
<span data-ttu-id="cad1d-122">Управлять доступом к данным Защиты от угроз (Майкрософт) можно с помощью области, назначаемой группам пользователей в средстве управления доступом на основе ролей (RBAC) ATP в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="cad1d-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="cad1d-123">Если область доступа не была задана как определенный набор устройств в службе ATP в Microsoft Defender, вы получите полный доступ к данным Защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="cad1d-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="cad1d-124">Однако если область учетной записи задана, вам будут доступны только данные об устройствах в этой области.</span><span class="sxs-lookup"><span data-stu-id="cad1d-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="cad1d-125">Например, если вы принадлежите только к одной группе пользователей с ролью ATP в Microsoft Defender и эта группа пользователей имеет доступ только к торговым устройствам, вы увидите только данные о торговых устройствах в службе Защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="cad1d-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="cad1d-126">Подробнее о параметрах RBAC в службе ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cad1d-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="cad1d-127">Элементы управления доступом в Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cad1d-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="cad1d-128">В режиме предварительного просмотра Защита от угроз (Майкрософт) не применяет элементы управления доступом на основе параметров Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="cad1d-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="cad1d-129">Эти параметры не влияют на доступ к данным Защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="cad1d-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cad1d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="cad1d-130">Related topics</span></span>

- [<span data-ttu-id="cad1d-131">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="cad1d-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="cad1d-132">RBAC ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cad1d-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="cad1d-133">Роли Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cad1d-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
