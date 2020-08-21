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
description: Администраторы могут научиться назначать и удалять разрешения в Центре администрирования Exchange в Exchange Online Protection.
ms.openlocfilehash: 8d452eb85d59bbe82cc6685d652617bc857c1ddf
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825693"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="f06a4-103">Управление ролевыми группами в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="f06a4-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="f06a4-104">Для добавления пользователей в группы ролей в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно использовать Центр администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="f06a4-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="f06a4-105">Добавление пользователей в группу ролей предоставляет пользователям разрешения на выполнения определенных задач администрирования.</span><span class="sxs-lookup"><span data-stu-id="f06a4-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="f06a4-106">Кроме того, можно удалять пользователей из группролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="f06a4-107">Дополнительные сведения о ролях и группах ролей см. в статье ["Разрешения в автономной службе EOP".](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f06a4-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f06a4-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f06a4-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f06a4-109">Чтобы открыть Центр администрирования Exchange ,см. раздел [Центра администрирования Exchange в автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f06a4-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="f06a4-110">Чтобы открыть автономную оболочку EOP PowerShell, см. [статью "Подключение к PowerShell для Exchange Online Protection".](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="f06a4-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f06a4-111">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="f06a4-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="f06a4-112">В частности, вам потребуется роль управления ролями, которая по умолчанию назначается группе ролей OrganizationManagement (глобальные администраторы).</span><span class="sxs-lookup"><span data-stu-id="f06a4-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="f06a4-113">Дополнительные сведения см. в разделе ["Разрешения в автономной службе EOP"](feature-permissions-in-eop.md) и использовании Центра администрирования [Exchange для изменения списка членов в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="f06a4-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="f06a4-114">Сочетания клавиш для процедур, описанных в этой статье, приведены в разделе сочетания клавиш для [Центра администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="f06a4-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="f06a4-115">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="f06a4-115">Having problems?</span></span> <span data-ttu-id="f06a4-116">Обратитесь за помощью на форум по [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="f06a4-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="f06a4-117">Использование Центра администрирования Exchange для управления группами ролей</span><span class="sxs-lookup"><span data-stu-id="f06a4-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="f06a4-118">Использование Центра администрирования Exchange для просмотра групп ролей</span><span class="sxs-lookup"><span data-stu-id="f06a4-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="f06a4-119">В Центре администрирования Exchange перейдите к **ролям** \> **администраторов.**</span><span class="sxs-lookup"><span data-stu-id="f06a4-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="f06a4-120">Здесь перечислены все группы ролей в организации.</span><span class="sxs-lookup"><span data-stu-id="f06a4-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="f06a4-121">Выберите группу ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-121">Select a role group.</span></span> <span data-ttu-id="f06a4-122">В области сведений **отображаются имя,** **описание,** **назначенные роли** **и управляется** группой ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="f06a4-123">Эти сведения также можно просмотреть, нажав **значок** ![ правки. ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="f06a4-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="f06a4-124">Использование Центра администрирования Exchange для создания групп ролей</span><span class="sxs-lookup"><span data-stu-id="f06a4-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="f06a4-125">При создании новой группы ролей можно настроить все параметры самостоятельно (во время создания группы или после нее).</span><span class="sxs-lookup"><span data-stu-id="f06a4-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="f06a4-126">Или можно скопировать существующую группу ролей и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="f06a4-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="f06a4-127">В Центре администрирования Exchange выберите **Permissions** \> **"Роли администраторов"** и выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f06a4-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="f06a4-128">**Создайте новую группу ролей вручную:** нажмите **кнопку Добавить** ![ значок "Добавить". ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="f06a4-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="f06a4-129">**Скопируйте существующую группу ролей:** выберите группу ролей, которую необходимо скопировать, и нажмите **значок копирования** ![ ](../../media/ITPro-EAC-CopyIcon.png) копии.</span><span class="sxs-lookup"><span data-stu-id="f06a4-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="f06a4-130">В **открывшемся окне** создания группы ролей настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f06a4-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="f06a4-131">**Имя:** введите уникальное имя группы ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="f06a4-132">**Описание:** введите необязательное описание для группы ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="f06a4-133">**Роли:** нажмите **кнопку** ![ "Добавить ](../../media/ITPro-EAC-AddIcon.png) значок **Remove** ![ ](../../media/ITPro-EAC-RemoveIcon.gif)ITPro-EAC-RemoveIcon.gif" для выбора или изменения ролей, назначенных для группы ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="f06a4-134">**Members:** Click **Add** ![ icon or ](../../media/ITPro-EAC-AddIcon.png) **Remove**ITPro-EAC-RemoveIcon.gifto modify the role ![ group ](../../media/ITPro-EAC-RemoveIcon.gif) membership.</span><span class="sxs-lookup"><span data-stu-id="f06a4-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="f06a4-135">По завершении нажмите кнопку **"Сохранить",** чтобы создать группу ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="f06a4-136">Использование Центра администрирования Exchange для изменения групп ролей</span><span class="sxs-lookup"><span data-stu-id="f06a4-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="f06a4-137">В Центре администрирования Exchange перейдите к **ролям** \> **администраторов,** выберите группу ролей, которую необходимо изменить, и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="f06a4-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="f06a4-138">При изменении групп ролей доступны те же параметры, что и при создании групп ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="f06a4-139">Вы можете выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f06a4-139">You can:</span></span>

- <span data-ttu-id="f06a4-140">Изменить имя и описание.</span><span class="sxs-lookup"><span data-stu-id="f06a4-140">Change the name and description.</span></span>

- <span data-ttu-id="f06a4-141">Добавление и удаление ролей управления (создания или удаления назначений ролей).</span><span class="sxs-lookup"><span data-stu-id="f06a4-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="f06a4-142">Добавить и удалить участников.</span><span class="sxs-lookup"><span data-stu-id="f06a4-142">Add and remove members.</span></span>

<span data-ttu-id="f06a4-143">**Примечание.** Некоторые группы ролей (например, Управление организацией) ограничивают роли, которые можно удалить из группы.</span><span class="sxs-lookup"><span data-stu-id="f06a4-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="f06a4-144">Использование Центра администрирования Exchange для изменения списка членов в группах ролей</span><span class="sxs-lookup"><span data-stu-id="f06a4-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="f06a4-145">В Центре администрирования Exchange перейдите к **ролям** администраторов, выберите группу \> **Admin roles**ролей, которую необходимо изменить, и нажмите **значок** ![ ](../../media/ITPro-EAC-EditIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="f06a4-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="f06a4-146">На открывшейся странице свойств группы ролей в разделе **"Участники"** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f06a4-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="f06a4-147">Нажмите **кнопку Add** ![ Icon (Добавить значок. ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="f06a4-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="f06a4-148">На появляющемся странице найдите нужного пользователя и нажмите \*\*кнопку ">. \*\*</span><span class="sxs-lookup"><span data-stu-id="f06a4-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="f06a4-149">Выберите пользователей и **нажмите кнопку ">** добавлять несколько раз при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f06a4-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="f06a4-150">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f06a4-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="f06a4-151">Выберите пользователей, которых нужно удалить, и нажмите значок **Remove** ![ "Удалить". ](../../media/ITPro-EAC-RemoveIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="f06a4-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="f06a4-152">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f06a4-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f06a4-153">После добавления или удаления членов группы ролей данным пользователям необходимо выйти из системы, а затем снова войти в нее, чтобы изменить административные права.</span><span class="sxs-lookup"><span data-stu-id="f06a4-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="f06a4-154">Использование Центра администрирования Exchange для удаления групп ролей</span><span class="sxs-lookup"><span data-stu-id="f06a4-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="f06a4-155">Встроенные группы ролей удалить невозможно, однако можно удалить созданные пользователем настраиваемые группы ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="f06a4-156">В Центре администрирования Exchange перейдите к **ролям** \> **администраторов.**</span><span class="sxs-lookup"><span data-stu-id="f06a4-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="f06a4-157">Выберите группу ролей, которую необходимо удалить, и нажмите **значок "Удалить** ![ удалить". ](../../media/ITPro-EAC-DeleteIcon.png)</span><span class="sxs-lookup"><span data-stu-id="f06a4-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="f06a4-158">Нажмите **кнопку "Да"** в открывшемся окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="f06a4-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="f06a4-159">Использование PowerShell для управления группами ролей</span><span class="sxs-lookup"><span data-stu-id="f06a4-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="f06a4-160">Просмотр групп ролей с помощью автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="f06a4-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="f06a4-161">Чтобы просмотреть группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f06a4-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="f06a4-162">В этом примере возвращается сводный список всех групп ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="f06a4-163">В этом примере возвращаются подробные сведения о группе ролей с именем Recipient Administrators.</span><span class="sxs-lookup"><span data-stu-id="f06a4-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="f06a4-164">В этом примере возвращаются все группы ролей, в которых является пользователь Julia.</span><span class="sxs-lookup"><span data-stu-id="f06a4-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="f06a4-165">Нужно использовать значение DistinguishedName (DN) для Юлиии, которое можно найти, выполнив следующую `Get-User -Identity Julia | Format-List DistinguishedName` команду: .</span><span class="sxs-lookup"><span data-stu-id="f06a4-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="f06a4-166">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="f06a4-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="f06a4-167">Создание групп ролей с помощью автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="f06a4-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="f06a4-168">При создании новой группы ролей можно настроить все параметры вручную (при создании группы или после нее).</span><span class="sxs-lookup"><span data-stu-id="f06a4-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="f06a4-169">Или можно скопировать существующую группу ролей и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="f06a4-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="f06a4-170">Чтобы создать новую группу ролей вручную, используйте следующую синтаксическую конпричину:</span><span class="sxs-lookup"><span data-stu-id="f06a4-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="f06a4-171">Параметр _Roles указывает роли_ управления, назначаемые группе ролей, используя следующую синтаксическую константу. `"Role1","Role1",..."RoleN"`</span><span class="sxs-lookup"><span data-stu-id="f06a4-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="f06a4-172">Доступные роли можно просмотреть с помощью **командлета Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="f06a4-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="f06a4-173">Параметр _Members_ указывает членов группы ролей, используя следующий `"Member1","Member2",..."MemberN"` синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f06a4-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="f06a4-174">Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты и другие группы ролей (участников безопасности).</span><span class="sxs-lookup"><span data-stu-id="f06a4-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="f06a4-175">В этом примере создается группа ролей с именем Limited Recipient Management со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="f06a4-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="f06a4-176">Роль получателей почты назначается группе ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="f06a4-177">Пользователи Kim и Мартина добавляются в качестве членов.</span><span class="sxs-lookup"><span data-stu-id="f06a4-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="f06a4-178">Чтобы скопировать существующую группу ролей, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f06a4-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="f06a4-179">Сохраните группу ролей, которую необходимо копировать, в переменной с помощью следующей синтаксической конструкции:</span><span class="sxs-lookup"><span data-stu-id="f06a4-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="f06a4-180">Создайте новую группу ролей с помощью следующей синтаксической кончестки:</span><span class="sxs-lookup"><span data-stu-id="f06a4-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="f06a4-181">Параметр _Members_ указывает членов группы ролей, используя следующий `"Member1","Member2",..."MemberN"` синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f06a4-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="f06a4-182">Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты и другие группы ролей (участников безопасности).</span><span class="sxs-lookup"><span data-stu-id="f06a4-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="f06a4-183">В этом примере группа ролей Organization Management копируется в новую группу ролей с именем "Limited Organization Management".</span><span class="sxs-lookup"><span data-stu-id="f06a4-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="f06a4-184">Участники группы ролей являются Еабелы, Карталом и Лукасом.</span><span class="sxs-lookup"><span data-stu-id="f06a4-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="f06a4-185">Дополнительные сведения о синтаксисе и [параметрах: New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="f06a4-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="f06a4-186">Использование автономного сервиса EOP PowerShell для изменения списка членов в группах ролей</span><span class="sxs-lookup"><span data-stu-id="f06a4-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="f06a4-187">Командлеты **Add-RoleGroupMember** и **Remove-RoleGroupMember** добавляют или удаляют отдельных членов по одному.</span><span class="sxs-lookup"><span data-stu-id="f06a4-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="f06a4-188">Командлет **Update-RoleGroupMember** может заменить или изменить существующий список членов.</span><span class="sxs-lookup"><span data-stu-id="f06a4-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="f06a4-189">Участниками группы ролей могут быть пользователи, универсальные группы безопасности с включенной поддержкой почты и другие группы ролей (участники безопасности).</span><span class="sxs-lookup"><span data-stu-id="f06a4-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="f06a4-190">Для изменения членов группы ролей используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f06a4-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="f06a4-191">Для _замены_ существующего списка членов указанными значениями используется следующий `"Member1","Member2",..."MemberN"` синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f06a4-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="f06a4-192">Для _выборочного_ изменения существующего списка элементов используется следующий `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f06a4-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="f06a4-193">В этом примере показано, как заменить всех текущих членов группы ролей службы поддержки указанными пользователями.</span><span class="sxs-lookup"><span data-stu-id="f06a4-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="f06a4-194">В этом примере показано, как добавить Daigoro Akai и удалить Мария Барио из списка членов в группе ролей службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="f06a4-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="f06a4-195">Дополнительные сведения о синтаксисе и параметрах см. [в разделе Update-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="f06a4-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="f06a4-196">Удаление групп ролей с помощью автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="f06a4-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="f06a4-197">Встроенные группы ролей удалить невозможно, однако можно удалить созданные пользователем настраиваемые группы ролей.</span><span class="sxs-lookup"><span data-stu-id="f06a4-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="f06a4-198">Для удаления настраиваемой группы ролей используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f06a4-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="f06a4-199">В этом примере удаляется группа ролей "Обучающие администраторы".</span><span class="sxs-lookup"><span data-stu-id="f06a4-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="f06a4-200">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="f06a4-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f06a4-201">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="f06a4-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="f06a4-202">Чтобы убедиться, что группа ролей скопирована успешно, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f06a4-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="f06a4-203">В Центре администрирования Exchange перейдите к **ролям** \> **администраторов**и убедитесь в наличии группы ролей (или нет в списке).</span><span class="sxs-lookup"><span data-stu-id="f06a4-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="f06a4-204">Выберите группу ролей и проверьте параметры в области "Сведения" или нажмите значок **Edit** ![ "Изменить" ](../../media/ITPro-EAC-EditIcon.png) для проверки параметров.</span><span class="sxs-lookup"><span data-stu-id="f06a4-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="f06a4-205">В Exchange Online PowerShell замените именем группы ролей, а затем выполните следующую команду, чтобы убедиться, что группа ролей \<Role Group Name\> существует (или не существует) и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="f06a4-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
