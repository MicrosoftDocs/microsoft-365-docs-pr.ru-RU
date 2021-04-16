---
title: Создание и управление группами устройств в Microsoft Defender для конечной точки
description: Создайте группы устройств и установите на них уровни автоматического устранения, настроив правила, применимые к группе.
keywords: группы устройств, группы, исправление, уровень, правила, группа aad, роль, назначение, ранж
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: acd24e5c87a74bbb32835ec170a121c5c0b6bb33
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860307"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="b3b87-104">Создание групп устройств и управление ими</span><span class="sxs-lookup"><span data-stu-id="b3b87-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b3b87-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b3b87-105">**Applies to:**</span></span>
- <span data-ttu-id="b3b87-106">Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b3b87-106">Azure Active Directory</span></span>
- <span data-ttu-id="b3b87-107">Office 365:</span><span class="sxs-lookup"><span data-stu-id="b3b87-107">Office 365</span></span>

> <span data-ttu-id="b3b87-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b3b87-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b3b87-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b3b87-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="b3b87-110">В корпоративном сценарии группам операций безопасности обычно назначен набор устройств.</span><span class="sxs-lookup"><span data-stu-id="b3b87-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="b3b87-111">Эти устройства сгруппируются на основе набора атрибутов, таких как домены, имена компьютеров или назначенные теги.</span><span class="sxs-lookup"><span data-stu-id="b3b87-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="b3b87-112">В Microsoft Defender для конечной точки можно создавать группы устройств и использовать их для:</span><span class="sxs-lookup"><span data-stu-id="b3b87-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="b3b87-113">Ограничение доступа к связанным оповещениям и данным определенным группам пользователей Azure AD с [назначенными ролями RBAC](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="b3b87-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="b3b87-114">Настройка различных параметров автоматической исправлений для различных наборов устройств</span><span class="sxs-lookup"><span data-stu-id="b3b87-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="b3b87-115">Назначение определенных уровней исправлений для применения во время автоматизированных расследований</span><span class="sxs-lookup"><span data-stu-id="b3b87-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="b3b87-116">В ходе исследования фильтруем список **Устройств** только для определенных групп устройств с помощью **группового фильтра.**</span><span class="sxs-lookup"><span data-stu-id="b3b87-116">In an investigation, filter the **Devices list** to just specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="b3b87-117">Группы устройств можно создавать в контексте ролевого доступа (RBAC), чтобы контролировать, кто может принимать конкретные действия или видеть сведения, назначая группу устройств (ы) группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="b3b87-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="b3b87-118">Дополнительные сведения см. в [ссылке Управление доступом к порталу с помощью управления доступом на основе ролей.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="b3b87-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="b3b87-119">Подробнее о приложении RBAC читайте в публикации "Ъ" "SoC работает с [RBAC".](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)</span><span class="sxs-lookup"><span data-stu-id="b3b87-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="b3b87-120">В процессе создания группы устройств вы будете:</span><span class="sxs-lookup"><span data-stu-id="b3b87-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="b3b87-121">Установите уровень автоматического восстановления для этой группы.</span><span class="sxs-lookup"><span data-stu-id="b3b87-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="b3b87-122">Дополнительные сведения об уровнях исправлений см. в этой ссылке Использование автоматического расследования для расследования и устранения [угроз.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="b3b87-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="b3b87-123">Укажите правило совпадения, определяющее, какая группа устройств относится к группе на основе имени устройства, домена, тегов и платформы ОС.</span><span class="sxs-lookup"><span data-stu-id="b3b87-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="b3b87-124">Если устройство также совпадает с другими группами, оно добавляется только в группу устройств с самым высоким уровнем.</span><span class="sxs-lookup"><span data-stu-id="b3b87-124">If a device is also matched to other groups, it is added only to the highest ranked device group.</span></span>
- <span data-ttu-id="b3b87-125">Выберите группу пользователей Azure AD, которая должна иметь доступ к группе устройств.</span><span class="sxs-lookup"><span data-stu-id="b3b87-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="b3b87-126">Ранжив группу устройств по сравнению с другими группами после ее создания.</span><span class="sxs-lookup"><span data-stu-id="b3b87-126">Rank the device group relative to other groups after it is created.</span></span>

>[!NOTE]
><span data-ttu-id="b3b87-127">Группа устройств доступна всем пользователям, если вы не назначите группе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b3b87-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="b3b87-128">Создание группы устройств</span><span class="sxs-lookup"><span data-stu-id="b3b87-128">Create a device group</span></span>

1. <span data-ttu-id="b3b87-129">В области навигации выберите **группы Устройств параметров.**  >  </span><span class="sxs-lookup"><span data-stu-id="b3b87-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="b3b87-130">Нажмите **кнопку Добавить группу устройств**.</span><span class="sxs-lookup"><span data-stu-id="b3b87-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="b3b87-131">Введите параметры имени группы и параметры автоматизации и укажите правило совпадения, определяющие, какие устройства относятся к группе.</span><span class="sxs-lookup"><span data-stu-id="b3b87-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="b3b87-132">Узнайте, [как начинается автоматическое расследование.](automated-investigations.md#how-the-automated-investigation-starts)</span><span class="sxs-lookup"><span data-stu-id="b3b87-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="b3b87-133">Если вы хотите группировать устройства по организационному подразделению, можно настроить ключ реестра для групповой принадлежности.</span><span class="sxs-lookup"><span data-stu-id="b3b87-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="b3b87-134">Дополнительные сведения о тегах устройств см. в дополнительных сведениях [о создании и управлении тегами устройств.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="b3b87-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="b3b87-135">Просмотр нескольких устройств, которые будут соответствовать этому правилу.</span><span class="sxs-lookup"><span data-stu-id="b3b87-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="b3b87-136">Если вы удовлетворены правилом, щелкните **вкладку Доступ пользователя.**</span><span class="sxs-lookup"><span data-stu-id="b3b87-136">If you are satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="b3b87-137">Назначьте группы пользователей, которые могут получить доступ к созданной группе устройств.</span><span class="sxs-lookup"><span data-stu-id="b3b87-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="b3b87-138">Вы можете предоставить доступ только к группам пользователей Azure AD, которые были назначены ролям RBAC.</span><span class="sxs-lookup"><span data-stu-id="b3b87-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="b3b87-139">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="b3b87-139">Click **Close**.</span></span> <span data-ttu-id="b3b87-140">Применяются изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b3b87-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="b3b87-141">Управление группами устройств</span><span class="sxs-lookup"><span data-stu-id="b3b87-141">Manage device groups</span></span>

<span data-ttu-id="b3b87-142">Вы можете повысить или понизить ранг группы устройств, чтобы во время совпадения ему было отдано более высокое или более низкое значение.</span><span class="sxs-lookup"><span data-stu-id="b3b87-142">You can promote or demote the rank of a device group so that it is given higher or lower priority during matching.</span></span> <span data-ttu-id="b3b87-143">Если устройство совпадает с более чем одной группой, оно добавляется только в группу с самым высоким уровнем.</span><span class="sxs-lookup"><span data-stu-id="b3b87-143">When a device is matched to more than one group, it is added only to the highest ranked group.</span></span> <span data-ttu-id="b3b87-144">Кроме того, можно изменить и удалить группы.</span><span class="sxs-lookup"><span data-stu-id="b3b87-144">You can also edit and delete groups.</span></span>

>[!WARNING]
><span data-ttu-id="b3b87-145">Удаление группы устройств может повлиять на правила уведомления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b3b87-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="b3b87-146">Если группа устройств настроена в соответствии с правилом уведомления по электронной почте, она будет удалена из этого правила.</span><span class="sxs-lookup"><span data-stu-id="b3b87-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="b3b87-147">Если группа устройств является единственной группой, настроенной для уведомления электронной почты, это правило уведомления электронной почты будет удалено вместе с группой устройств.</span><span class="sxs-lookup"><span data-stu-id="b3b87-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="b3b87-148">По умолчанию группы устройств доступны всем пользователям с доступом на портал.</span><span class="sxs-lookup"><span data-stu-id="b3b87-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="b3b87-149">Вы можете изменить поведение по умолчанию, назначив группы пользователей Azure AD группе устройств.</span><span class="sxs-lookup"><span data-stu-id="b3b87-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="b3b87-150">Устройства, не совпадают с группами, добавляются в группу Ungrouped devices (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b3b87-150">Devices that are not matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="b3b87-151">Вы не можете изменить ранг этой группы или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="b3b87-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="b3b87-152">Однако можно изменить уровень исправлений этой группы и определить группы пользователей Azure AD, которые могут получить доступ к этой группе.</span><span class="sxs-lookup"><span data-stu-id="b3b87-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="b3b87-153">Применение изменений в конфигурации группы устройств может занять до нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="b3b87-153">Applying changes to device group configuration may take up to several minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3b87-154">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="b3b87-154">Related topics</span></span>

- [<span data-ttu-id="b3b87-155">Управление доступом к порталу с помощью управления доступом на основе ролей</span><span class="sxs-lookup"><span data-stu-id="b3b87-155">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="b3b87-156">Создание тегов устройств и управление ими</span><span class="sxs-lookup"><span data-stu-id="b3b87-156">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="b3b87-157">Получите список групп устройств клиента с помощью API Graph</span><span class="sxs-lookup"><span data-stu-id="b3b87-157">Get list of tenant device groups using Graph API</span></span>](https://docs.microsoft.com/graph/api/device-list-memberof)
