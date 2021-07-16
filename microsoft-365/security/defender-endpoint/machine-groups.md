---
title: Создание и управление группами устройств в Microsoft Defender для конечной точки
description: Создайте группы устройств и установите на них уровни автоматического устранения, подтвердив правила, применимые к группе
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
ms.openlocfilehash: 49bd90d8a082f55622e54976cc8fc78229d8c646
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453541"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="23c34-104">Создание групп устройств и управление ими</span><span class="sxs-lookup"><span data-stu-id="23c34-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="23c34-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="23c34-105">**Applies to:**</span></span>
- <span data-ttu-id="23c34-106">Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="23c34-106">Azure Active Directory</span></span>
- <span data-ttu-id="23c34-107">Office 365:</span><span class="sxs-lookup"><span data-stu-id="23c34-107">Office 365</span></span>

> <span data-ttu-id="23c34-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="23c34-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="23c34-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="23c34-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="23c34-110">В корпоративном сценарии группам операций безопасности обычно назначен набор устройств.</span><span class="sxs-lookup"><span data-stu-id="23c34-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="23c34-111">Эти устройства сгруппируются на основе набора атрибутов, таких как домены, имена компьютеров или назначенные теги.</span><span class="sxs-lookup"><span data-stu-id="23c34-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="23c34-112">В Microsoft Defender для конечной точки можно создавать группы устройств и использовать их для:</span><span class="sxs-lookup"><span data-stu-id="23c34-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="23c34-113">Ограничение доступа к связанным оповещениям и данным определенным группам пользователей Azure AD с [назначенными ролями RBAC](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="23c34-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="23c34-114">Настройка различных параметров автоматической исправлений для различных наборов устройств</span><span class="sxs-lookup"><span data-stu-id="23c34-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="23c34-115">Назначение определенных уровней исправлений для применения во время автоматизированных расследований</span><span class="sxs-lookup"><span data-stu-id="23c34-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="23c34-116">В ходе исследования фильтруем список **Устройств для** определенных групп устройств с помощью **группового фильтра.**</span><span class="sxs-lookup"><span data-stu-id="23c34-116">In an investigation, filter the **Devices list** to specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="23c34-117">Группы устройств можно создавать в контексте ролевого доступа (RBAC), чтобы контролировать, кто может принимать конкретные действия или видеть сведения, назначая группу устройств (ы) группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="23c34-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="23c34-118">Дополнительные сведения см. в [ссылке Управление доступом к порталу с помощью управления доступом на основе ролей.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="23c34-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="23c34-119">Подробнее о приложении RBAC читайте в публикации "Ъ" "SoC работает с [RBAC".](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)</span><span class="sxs-lookup"><span data-stu-id="23c34-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="23c34-120">В процессе создания группы устройств вы будете:</span><span class="sxs-lookup"><span data-stu-id="23c34-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="23c34-121">Установите уровень автоматического восстановления для этой группы.</span><span class="sxs-lookup"><span data-stu-id="23c34-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="23c34-122">Дополнительные сведения об уровнях исправлений см. в этой ссылке Использование автоматического расследования для расследования и устранения [угроз.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="23c34-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="23c34-123">Укажите правило совпадения, определяющее, какая группа устройств относится к группе на основе имени устройства, домена, тегов и платформы ОС.</span><span class="sxs-lookup"><span data-stu-id="23c34-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="23c34-124">Если устройство также совпадает с другими группами, оно добавляется только в группу устройств с наивысшим ранжом.</span><span class="sxs-lookup"><span data-stu-id="23c34-124">If a device is also matched to other groups, it's added only to the highest ranked device group.</span></span>
- <span data-ttu-id="23c34-125">Выберите группу пользователей Azure AD, которая должна иметь доступ к группе устройств.</span><span class="sxs-lookup"><span data-stu-id="23c34-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="23c34-126">Ранжив группу устройств по сравнению с другими группами после ее создания.</span><span class="sxs-lookup"><span data-stu-id="23c34-126">Rank the device group relative to other groups after it's created.</span></span>

>[!NOTE]
><span data-ttu-id="23c34-127">Группа устройств доступна всем пользователям, если вы не назначите группе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="23c34-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="23c34-128">Создание группы устройств</span><span class="sxs-lookup"><span data-stu-id="23c34-128">Create a device group</span></span>

1. <span data-ttu-id="23c34-129">В области навигации выберите группы **Параметры**  >  конечных **точек.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="23c34-129">In the navigation pane, select **Settings** > **Endpoints** > **Permissions** > **Device groups**.</span></span>

2. <span data-ttu-id="23c34-130">Нажмите **кнопку Добавить группу устройств**.</span><span class="sxs-lookup"><span data-stu-id="23c34-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="23c34-131">Введите параметры имени группы и параметры автоматизации и укажите правило совпадения, определяющие, какие устройства относятся к группе.</span><span class="sxs-lookup"><span data-stu-id="23c34-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="23c34-132">Узнайте, [как начинается автоматическое расследование.](automated-investigations.md#how-the-automated-investigation-starts)</span><span class="sxs-lookup"><span data-stu-id="23c34-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="23c34-133">Если вы хотите группировать устройства по организационному подразделению, можно настроить ключ реестра для групповой принадлежности.</span><span class="sxs-lookup"><span data-stu-id="23c34-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="23c34-134">Дополнительные сведения о тегах устройств см. в дополнительных сведениях [о создании и управлении тегами устройств.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="23c34-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="23c34-135">Просмотр нескольких устройств, которые будут соответствовать этому правилу.</span><span class="sxs-lookup"><span data-stu-id="23c34-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="23c34-136">Если вы удовлетворены правилом, щелкните вкладку **Доступ пользователя.**</span><span class="sxs-lookup"><span data-stu-id="23c34-136">If you're satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="23c34-137">Назначьте группы пользователей, которые могут получить доступ к созданной группе устройств.</span><span class="sxs-lookup"><span data-stu-id="23c34-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="23c34-138">Вы можете предоставить доступ только к группам пользователей Azure AD, которые были назначены ролям RBAC.</span><span class="sxs-lookup"><span data-stu-id="23c34-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="23c34-139">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="23c34-139">Click **Close**.</span></span> <span data-ttu-id="23c34-140">Применяются изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="23c34-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="23c34-141">Управление группами устройств</span><span class="sxs-lookup"><span data-stu-id="23c34-141">Manage device groups</span></span>

<span data-ttu-id="23c34-142">Можно повысить или понизить ранг группы устройств, чтобы во время совпадения ему было отдано более высокое или более низкое значение.</span><span class="sxs-lookup"><span data-stu-id="23c34-142">You can promote or demote the rank of a device group so that it's given higher or lower priority during matching.</span></span> <span data-ttu-id="23c34-143">Если устройство совпадает с более чем одной группой, оно добавляется только в группу с самым высоким рейтингом.</span><span class="sxs-lookup"><span data-stu-id="23c34-143">When a device is matched to more than one group, it's added only to the highest ranked group.</span></span> <span data-ttu-id="23c34-144">Кроме того, можно изменить и удалить группы.</span><span class="sxs-lookup"><span data-stu-id="23c34-144">You can also edit and delete groups.</span></span>



>[!WARNING]
><span data-ttu-id="23c34-145">Удаление группы устройств может повлиять на правила уведомления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="23c34-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="23c34-146">Если группа устройств настроена в соответствии с правилом уведомления по электронной почте, она будет удалена из этого правила.</span><span class="sxs-lookup"><span data-stu-id="23c34-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="23c34-147">Если группа устройств является единственной группой, настроенной для уведомления электронной почты, это правило уведомления электронной почты будет удалено вместе с группой устройств.</span><span class="sxs-lookup"><span data-stu-id="23c34-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="23c34-148">По умолчанию группы устройств доступны всем пользователям с доступом на портал.</span><span class="sxs-lookup"><span data-stu-id="23c34-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="23c34-149">Вы можете изменить поведение по умолчанию, назначив группы пользователей Azure AD группе устройств.</span><span class="sxs-lookup"><span data-stu-id="23c34-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="23c34-150">Устройства, не совпадают с группами, добавляются в группу Ungrouped devices (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="23c34-150">Devices that aren't matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="23c34-151">Вы не можете изменить ранг этой группы или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="23c34-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="23c34-152">Однако можно изменить уровень исправлений этой группы и определить группы пользователей Azure AD, которые могут получить доступ к этой группе.</span><span class="sxs-lookup"><span data-stu-id="23c34-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="23c34-153">Применение изменений в конфигурации группы устройств может занять до нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="23c34-153">Applying changes to device group configuration may take up to several minutes.</span></span>


### <a name="add-device-group-definitions"></a><span data-ttu-id="23c34-154">Добавление определений группы устройств</span><span class="sxs-lookup"><span data-stu-id="23c34-154">Add device group definitions</span></span>
<span data-ttu-id="23c34-155">Определения группы устройств также могут включать несколько значений для каждого условия.</span><span class="sxs-lookup"><span data-stu-id="23c34-155">Device group definitions can also include multiple values for each condition.</span></span> <span data-ttu-id="23c34-156">Можно установить несколько тегов, имен устройств и доменов для определения одной группы устройств.</span><span class="sxs-lookup"><span data-stu-id="23c34-156">You can set multiple tags, device names, and domains to the definition of a single device group.</span></span>

1. <span data-ttu-id="23c34-157">Создайте новую группу устройств и выберите **вкладку Devices.**</span><span class="sxs-lookup"><span data-stu-id="23c34-157">Create a new device group, then select **Devices** tab.</span></span>
2. <span data-ttu-id="23c34-158">Добавьте первое значение для одного из условий.</span><span class="sxs-lookup"><span data-stu-id="23c34-158">Add the first value for one of the conditions.</span></span>
3. <span data-ttu-id="23c34-159">Выберите, `+` чтобы добавить больше строк того же типа свойства.</span><span class="sxs-lookup"><span data-stu-id="23c34-159">Select `+` to add more rows of the same property type.</span></span>

>[!TIP]
> <span data-ttu-id="23c34-160">Используйте оператор "OR" между строками одного типа условий, что позволяет использовать несколько значений для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="23c34-160">Use the 'OR' operator between rows of the same condition type, which allows multiple values per property.</span></span>
> <span data-ttu-id="23c34-161">Для каждого типа свойств можно добавить до 10 строк (значений) — тег, имя устройства, домен.</span><span class="sxs-lookup"><span data-stu-id="23c34-161">You can add up to 10 rows (values) for each property type - tag, device name, domain.</span></span>

<span data-ttu-id="23c34-162">Дополнительные сведения о привязке к определениям групп устройств см. в группе [Device groups - Microsoft 365 безопасности.](https://sip.security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="23c34-162">For more information on linking to device groups definitions, see [Device groups - Microsoft 365 security](https://sip.security.microsoft.com/homepage).</span></span>

## <a name="related-topics"></a><span data-ttu-id="23c34-163">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="23c34-163">Related topics</span></span>

- [<span data-ttu-id="23c34-164">Управление доступом к порталу с помощью управления доступом на основе ролей</span><span class="sxs-lookup"><span data-stu-id="23c34-164">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="23c34-165">Создание тегов устройств и управление ими</span><span class="sxs-lookup"><span data-stu-id="23c34-165">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="23c34-166">Получите список групп устройств клиента с Graph API</span><span class="sxs-lookup"><span data-stu-id="23c34-166">Get list of tenant device groups using Graph API</span></span>](/graph/api/device-list-memberof)
