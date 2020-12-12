---
title: Управление группами ролей в EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Администраторы могут узнать, как назначать или удалять разрешения в Центре администрирования Exchange (EAC) в Exchange Online Protection.
ms.openlocfilehash: 4a1353963e5e3eadc1a07f8b4aa3a765b06c86ec
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659301"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="17973-103">Управление ролевыми группами в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="17973-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="17973-104">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online для добавления пользователей в группы ролей можно использовать Центр администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="17973-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="17973-105">Добавление пользователей в группу ролей дает им разрешения на выполнение определенных задач администрирования.</span><span class="sxs-lookup"><span data-stu-id="17973-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="17973-106">Вы также можете удалять пользователей из групп ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="17973-107">Дополнительные сведения о ролях и группах ролей см. в [сведениях о разрешениях в автономных EOP.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="17973-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="17973-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="17973-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="17973-109">Чтобы открыть Центр администрирования Exchange (EAC), см. центр [администрирования Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="17973-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="17973-110">Чтобы открыть автономный EOP PowerShell, см. веб-сайт [Connect to Exchange Online Protection PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="17973-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="17973-111">Для работы с процедурами, которые данная статья, вам должны быть назначены разрешения в Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="17973-111">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="17973-112">В частности, необходима роль **управления** ролем, которая по умолчанию назначена группе ролей **"Управление** организацией".</span><span class="sxs-lookup"><span data-stu-id="17973-112">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="17973-113">Дополнительные сведения см. в сведениях о разрешениях в автономных [EOP](feature-permissions-in-eop.md) и использовании EAC для изменения списка участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="17973-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="17973-114">Сведения о сочетаниях клавиш, которые могут применяться к процедурам в этой статье, см. в статье "Сочетания клавиш" для Центра администрирования [Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="17973-114">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="17973-115">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="17973-115">Having problems?</span></span> <span data-ttu-id="17973-116">Обратитесь за помощью на форум по [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="17973-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="17973-117">Использование EAC для управления группами ролей</span><span class="sxs-lookup"><span data-stu-id="17973-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="17973-118">Просмотр групп ролей с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="17973-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="17973-119">В EAC перейдите к **ролям** \> **администратора разрешений.**</span><span class="sxs-lookup"><span data-stu-id="17973-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="17973-120">Здесь перечислены все группы ролей в организации.</span><span class="sxs-lookup"><span data-stu-id="17973-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="17973-121">Выберите группу ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-121">Select a role group.</span></span> <span data-ttu-id="17973-122">В области сведений показаны **имена,** **описание,** назначенная **роль** и управление **группой** ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="17973-123">Вы также можете увидеть эти  сведения, щелкнув значок ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="17973-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="17973-124">Создание групп ролей с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="17973-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="17973-125">При создании новой группы ролей можно настроить все параметры самостоятельно (во время создания группы или после нее).</span><span class="sxs-lookup"><span data-stu-id="17973-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="17973-126">Кроме того, можно скопировать существующую группу ролей и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="17973-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="17973-127">В EAC перейдите к **ролям** администратора разрешений \> и сделайте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="17973-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="17973-128">**Вручную создайте новую группу ролей:** щелкните **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) "Добавить".</span><span class="sxs-lookup"><span data-stu-id="17973-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="17973-129">**Скопируйте существующую группу** ролей: выберите группу ролей, которую нужно скопировать, и щелкните значок  ![ ](../../media/ITPro-EAC-CopyIcon.png) копирования.</span><span class="sxs-lookup"><span data-stu-id="17973-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="17973-130">В новом **окне** группы ролей настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="17973-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="17973-131">**Name**: Enter a unique name for the role group.</span><span class="sxs-lookup"><span data-stu-id="17973-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="17973-132">**Описание:** введите необязательное описание группы ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="17973-133">**Roles**: Click **Add** ![ Add icon or Remove ](../../media/ITPro-EAC-AddIcon.png) **Remove** icon to select or modify the roles that ![ are ](../../media/ITPro-EAC-RemoveIcon.gif) assigned to the role group.</span><span class="sxs-lookup"><span data-stu-id="17973-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="17973-134">**Участники:** **щелкните значок "Добавить** добавить" или ![ ](../../media/ITPro-EAC-AddIcon.png) **"Удалить** ![ значок "Удалить", ](../../media/ITPro-EAC-RemoveIcon.gif) чтобы изменить членство в группе ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="17973-135">После завершения нажмите кнопку  "Сохранить", чтобы создать группу ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="17973-136">Использование EAC для изменения групп ролей</span><span class="sxs-lookup"><span data-stu-id="17973-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="17973-137">В EAC перейдите к **ролям** администратора разрешений, выберите группу ролей, которую необходимо изменить, и нажмите значок \>   ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="17973-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="17973-138">При изменении групп ролей доступны те же параметры, что и при создании групп ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="17973-139">Вы можете выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="17973-139">You can:</span></span>

- <span data-ttu-id="17973-140">Измените имя и описание.</span><span class="sxs-lookup"><span data-stu-id="17973-140">Change the name and description.</span></span>

- <span data-ttu-id="17973-141">Добавление и удаление ролей управления (создание или удаление назначений ролей).</span><span class="sxs-lookup"><span data-stu-id="17973-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="17973-142">Добавление и удаление участников.</span><span class="sxs-lookup"><span data-stu-id="17973-142">Add and remove members.</span></span>

<span data-ttu-id="17973-143">**Примечание.** Некоторые группы ролей (например, Управление организацией) ограничивают роли, которые можно удалить из группы.</span><span class="sxs-lookup"><span data-stu-id="17973-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="17973-144">Изменение списка участников в группах ролей с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="17973-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="17973-145">В EAC перейдите к **ролям** администратора разрешений, выберите группу ролей, которую нужно изменить, и нажмите значок \>   ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="17973-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="17973-146">На открываемой странице свойств группы ролей в разделе **"Участники"** сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="17973-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="17973-147">Нажмите **кнопку "Добавить** ![ значок добавления" ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="17973-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="17973-148">На этой странице найдите пользователя, который нужно добавить, и нажмите кнопку **add ->.**</span><span class="sxs-lookup"><span data-stu-id="17973-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="17973-149">Выберите пользователей и **нажмите кнопку add ->** многократно при необходимости.</span><span class="sxs-lookup"><span data-stu-id="17973-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="17973-150">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="17973-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="17973-151">Выберите пользователей, которые нужно удалить, и нажмите значок **"Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) удалить".</span><span class="sxs-lookup"><span data-stu-id="17973-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="17973-152">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="17973-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="17973-153">После добавления или удаления членов группы ролей данным пользователям необходимо выйти из системы, а затем снова войти в нее, чтобы изменить административные права.</span><span class="sxs-lookup"><span data-stu-id="17973-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="17973-154">Удаление групп ролей с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="17973-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="17973-155">Встроенные группы ролей удалить нельзя, но вы можете удалить созданные настраиваемые группы ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="17973-156">В EAC перейдите к **ролям** \> **администратора разрешений.**</span><span class="sxs-lookup"><span data-stu-id="17973-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="17973-157">Выберите группу ролей, которую нужно удалить, и нажмите **значок "Удалить** ![ удалить". ](../../media/ITPro-EAC-DeleteIcon.png)</span><span class="sxs-lookup"><span data-stu-id="17973-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="17973-158">Нажмите **кнопку "Да"** в от появится окно подтверждения.</span><span class="sxs-lookup"><span data-stu-id="17973-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="17973-159">Управление группами ролей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="17973-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="17973-160">Просмотр групп ролей с помощью автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="17973-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="17973-161">Чтобы просмотреть группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="17973-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="17973-162">В этом примере возвращается сводный список всех групп ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="17973-163">В этом примере возвращаются подробные сведения о группе ролей с именем Recipient Administrators.</span><span class="sxs-lookup"><span data-stu-id="17973-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="17973-164">В этом примере возвращаются все группы ролей, участником которых является пользователь Юлия.</span><span class="sxs-lookup"><span data-stu-id="17973-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="17973-165">Необходимо использовать значение DistinguishedName (DN) для Юлии, которое можно найти с помощью команды: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="17973-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="17973-166">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="17973-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="17973-167">Создание групп ролей с помощью автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="17973-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="17973-168">При создании новой группы ролей можно настроить все параметры вручную (во время создания группы или после нее).</span><span class="sxs-lookup"><span data-stu-id="17973-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="17973-169">Кроме того, можно скопировать существующую группу ролей и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="17973-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="17973-170">Чтобы вручную создать новую группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="17973-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="17973-171">Параметр _Roles_ указывает роли управления, назначаемые группе ролей, с помощью следующего синтаксиса. `"Role1","Role1",..."RoleN"`</span><span class="sxs-lookup"><span data-stu-id="17973-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="17973-172">Доступные роли можно увидеть с помощью команды **Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="17973-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="17973-173">Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="17973-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="17973-174">Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты или другие группы ролей (участников безопасности).</span><span class="sxs-lookup"><span data-stu-id="17973-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="17973-175">В этом примере создается группа ролей с именем "Limited Recipient Management" со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="17973-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="17973-176">Группе ролей назначена роль получателей почты.</span><span class="sxs-lookup"><span data-stu-id="17973-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="17973-177">Пользователи Kim и Martin добавляются в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="17973-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="17973-178">Чтобы скопировать существующую группу ролей, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="17973-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="17973-179">Сохраните группу ролей, которую необходимо копировать, в переменной с помощью следующей синтаксической конструкции:</span><span class="sxs-lookup"><span data-stu-id="17973-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="17973-180">Создайте новую группу ролей, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="17973-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="17973-181">Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="17973-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="17973-182">Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты или другие группы ролей (участников безопасности).</span><span class="sxs-lookup"><span data-stu-id="17973-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="17973-183">В этом примере группа ролей Управление организацией копируется в новую группу ролей с именем "Limited Organization Management".</span><span class="sxs-lookup"><span data-stu-id="17973-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="17973-184">Участниками группы ролей являются Isabelle, Carter и Lukas.</span><span class="sxs-lookup"><span data-stu-id="17973-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="17973-185">Подробные сведения о синтаксисах и параметрах: [New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="17973-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="17973-186">Использование автономных EOP PowerShell для изменения списка участников в группах ролей</span><span class="sxs-lookup"><span data-stu-id="17973-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="17973-187">С **их стороны можно**  добавлять или удалять отдельных участников по одному.</span><span class="sxs-lookup"><span data-stu-id="17973-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="17973-188">Для замены или изменения существующего списка членов можно использовать команды **Update-RoleGroupMember.**</span><span class="sxs-lookup"><span data-stu-id="17973-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="17973-189">Участниками группы ролей могут быть пользователи, универсальные группы безопасности с включенной поддержкой почты или другие группы ролей (участники безопасности).</span><span class="sxs-lookup"><span data-stu-id="17973-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="17973-190">Чтобы изменить членов группы ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="17973-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="17973-191">Чтобы _заменить_ существующий список членов на задамые вами значения, используйте следующий синтаксис: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="17973-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="17973-192">Чтобы _выборочно_ изменить существующий список членов, используйте следующий синтаксис: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="17973-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="17973-193">В этом примере все текущие члены группы ролей "Help Desk" заменяются указанными пользователями.</span><span class="sxs-lookup"><span data-stu-id="17973-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="17973-194">В этом примере daigoro Akai и Valeria Barrio удаляется из списка членов группы ролей "Help Desk".</span><span class="sxs-lookup"><span data-stu-id="17973-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="17973-195">Подробные сведения о синтаксисах и параметрах см. в описании [Update-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="17973-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="17973-196">Удаление групп ролей с помощью автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="17973-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="17973-197">Встроенные группы ролей удалить нельзя, но вы можете удалить созданные настраиваемые группы ролей.</span><span class="sxs-lookup"><span data-stu-id="17973-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="17973-198">Чтобы удалить настраиваемую группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="17973-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="17973-199">В этом примере удаляется группа ролей "Обучающие администраторы".</span><span class="sxs-lookup"><span data-stu-id="17973-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="17973-200">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="17973-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="17973-201">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="17973-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="17973-202">Чтобы убедиться, что вы успешно скопировали группу ролей, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="17973-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="17973-203">В EAC перейдите к **ролям** администратора разрешений и убедитесь, что группа ролей указана \> (или не указана).</span><span class="sxs-lookup"><span data-stu-id="17973-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="17973-204">Выберите группу ролей и проверьте параметры в области  сведений или нажмите значок редактирования, чтобы ![ проверить ](../../media/ITPro-EAC-EditIcon.png) параметры.</span><span class="sxs-lookup"><span data-stu-id="17973-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="17973-205">В Exchange Online PowerShell замените имя группы ролей и запустите следующую команду, чтобы убедиться, что группа ролей существует (или не существует) и \<Role Group Name\> проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="17973-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
