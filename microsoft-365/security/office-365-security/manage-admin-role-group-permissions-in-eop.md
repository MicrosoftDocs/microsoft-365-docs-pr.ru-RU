---
title: Управление группами ролей в EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Администраторы могут научиться назначать и удалять разрешения в центре администрирования Exchange в Exchange Online Protection.
ms.openlocfilehash: 3555d3bd7fa4c53802eb214747735223cccc21e5
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616518"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="4a246-103">Управление ролевыми группами в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="4a246-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="4a246-104">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно использовать центр администрирования Exchange для добавления пользователей в группы ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="4a246-105">Добавление пользователей в группу ролей дает пользователю разрешения на выполнение определенных задач администрирования.</span><span class="sxs-lookup"><span data-stu-id="4a246-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="4a246-106">Вы также можете удалять пользователей из групп ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="4a246-107">Дополнительные сведения о ролях и группах ролей содержатся в разделе [разрешения в автономной EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4a246-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4a246-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="4a246-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4a246-109">Чтобы открыть центр администрирования Exchange, обратитесь к [центру администрирования Exchange в автономной EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4a246-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="4a246-110">Чтобы открыть автономную среду EOP PowerShell, ознакомьтесь со статьей [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="4a246-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4a246-111">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="4a246-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="4a246-112">В частности, необходима роль управления ролями, которая по умолчанию назначена группе ролей Организатионманажемент (глобальные администраторы).</span><span class="sxs-lookup"><span data-stu-id="4a246-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="4a246-113">Дополнительные сведения см. [в разделе разрешения в автономных EOP](feature-permissions-in-eop.md) и используйте центр администрирования Exchange для [изменения списка участников в группах ролей](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="4a246-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="4a246-114">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4a246-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="4a246-115">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="4a246-115">Having problems?</span></span> <span data-ttu-id="4a246-116">Обратитесь за помощью к форуму [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="4a246-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="4a246-117">Использование центра администрирования Exchange для управления группами ролей</span><span class="sxs-lookup"><span data-stu-id="4a246-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="4a246-118">Использование центра администрирования Exchange для просмотра групп ролей</span><span class="sxs-lookup"><span data-stu-id="4a246-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="4a246-119">В центре администрирования Exchange перейдите к **Permissions** разделу \> **роли администратора**разрешений.</span><span class="sxs-lookup"><span data-stu-id="4a246-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="4a246-120">Здесь перечислены все группы ролей в организации.</span><span class="sxs-lookup"><span data-stu-id="4a246-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="4a246-121">Выберите группу ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-121">Select a role group.</span></span> <span data-ttu-id="4a246-122">Область сведений отображает **имя**, **Описание**, **назначенные роли**и **управляется** группой ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="4a246-123">Эти сведения также можно просмотреть, нажав кнопку **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4a246-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="4a246-124">Использование центра администрирования Exchange для создания групп ролей</span><span class="sxs-lookup"><span data-stu-id="4a246-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="4a246-125">При создании новой группы ролей можно настроить все параметры самостоятельно (во время создания группы или после нее).</span><span class="sxs-lookup"><span data-stu-id="4a246-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="4a246-126">Кроме того, вы можете скопировать существующую группу ролей и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="4a246-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="4a246-127">В центре администрирования Exchange откройте раздел **Permissions** \> **роли администратора**разрешения, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4a246-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="4a246-128">**Вручную создайте новую группу ролей**: щелкните **Добавить** ![ значок "Добавить" ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4a246-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="4a246-129">**Скопируйте существующую группу ролей**: выберите группу ролей, которую необходимо скопировать, и нажмите кнопку **Копировать** ![ копию ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4a246-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="4a246-130">В открывшемся окне **Новая роль группы** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4a246-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="4a246-131">**Name**: введите уникальное имя группы ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="4a246-132">**Описание**: введите необязательное описание группы ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="4a246-133">**Роли**: щелкните **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) или **Удалить** ![ итпро-ЕАК-ремовеикон. gif, ](../../media/ITPro-EAC-RemoveIcon.gif) чтобы выбрать или изменить роли, назначенные группе ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="4a246-134">**Члены**: щелкните **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) или **Удалить** ![ итпро-ЕАК-ремовеикон. gif ](../../media/ITPro-EAC-RemoveIcon.gif) , чтобы изменить членство в группе ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="4a246-135">Когда все будет готово, нажмите кнопку **сохранить** , чтобы создать группу ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="4a246-136">Использование центра администрирования Exchange для изменения групп ролей</span><span class="sxs-lookup"><span data-stu-id="4a246-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="4a246-137">В центре администрирования Exchange перейдите в **Permissions** раздел \> **роли администратора**разрешений, выберите группу ролей, которую необходимо изменить, и нажмите кнопку **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4a246-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="4a246-138">Те же параметры доступны при изменении групп ролей в соответствии с созданием групп ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="4a246-139">Вы можете выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4a246-139">You can:</span></span>

- <span data-ttu-id="4a246-140">Измените имя и описание.</span><span class="sxs-lookup"><span data-stu-id="4a246-140">Change the name and description.</span></span>

- <span data-ttu-id="4a246-141">Добавление и удаление ролей управления (создание и удаление назначений ролей).</span><span class="sxs-lookup"><span data-stu-id="4a246-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="4a246-142">Добавление и удаление членов.</span><span class="sxs-lookup"><span data-stu-id="4a246-142">Add and remove members.</span></span>

<span data-ttu-id="4a246-143">**Note**: некоторые группы ролей (например, Управление организацией) ограничивают роли, которые можно удалить из группы.</span><span class="sxs-lookup"><span data-stu-id="4a246-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="4a246-144">Использование центра администрирования Exchange для изменения списка участников в группах ролей</span><span class="sxs-lookup"><span data-stu-id="4a246-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="4a246-145">В центре администрирования Exchange перейдите в **Permissions** раздел \> **роли администратора**разрешений, выберите группу ролей, которую необходимо изменить, а затем щелкните **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4a246-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="4a246-146">На открывшейся странице "Свойства группы ролей" в разделе **мемеберс** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="4a246-146">In the role group properties page that opens, in the **Memebers** section, do either of the following steps:</span></span>

   - <span data-ttu-id="4a246-147">Нажмите кнопку **Добавить** ![ значок "Добавить" ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4a246-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="4a246-148">На открывшейся странице найдите пользователя, которого нужно добавить в Вау, и нажмите кнопку **Add->**.</span><span class="sxs-lookup"><span data-stu-id="4a246-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="4a246-149">Выберите пункт Пользователи и нажмите кнопку **добавить >** много раз, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="4a246-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="4a246-150">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4a246-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="4a246-151">Выберите пользователей, которых нужно удалить, а затем нажмите кнопку **Удалить** ![ значок удаления ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="4a246-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="4a246-152">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4a246-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4a246-153">После добавления или удаления членов группы ролей данным пользователям необходимо выйти из системы, а затем снова войти в нее, чтобы изменить административные права.</span><span class="sxs-lookup"><span data-stu-id="4a246-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="4a246-154">Использование центра администрирования Exchange для удаления групп ролей</span><span class="sxs-lookup"><span data-stu-id="4a246-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="4a246-155">Невозможно удалить встроенные группы ролей, но вы можете удалить созданные пользовательские группы ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="4a246-156">В центре администрирования Exchange перейдите к **Permissions** разделу \> **роли администратора**разрешений.</span><span class="sxs-lookup"><span data-stu-id="4a246-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="4a246-157">Выберите группу ролей, которую необходимо удалить, и нажмите кнопку **Удалить** ![ значок удаления ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4a246-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="4a246-158">Нажмите кнопку **Да** в появившемся окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="4a246-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="4a246-159">Управление группами ролей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a246-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="4a246-160">Использование автономной EOP PowerShell для просмотра групп ролей</span><span class="sxs-lookup"><span data-stu-id="4a246-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="4a246-161">Чтобы просмотреть группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4a246-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="4a246-162">В этом примере возвращается сводный список всех групп ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="4a246-163">В этом примере возвращаются подробные сведения для группы ролей "Администраторы получателей".</span><span class="sxs-lookup"><span data-stu-id="4a246-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="4a246-164">В этом примере возвращаются все группы ролей, в которых пользователь Жулиа является участником.</span><span class="sxs-lookup"><span data-stu-id="4a246-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="4a246-165">Необходимо использовать значение DistinguishedName (DN) для Жулиа, которое можно найти, выполнив следующую команду: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="4a246-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="4a246-166">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="4a246-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="4a246-167">Создание групп ролей с помощью изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a246-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="4a246-168">При создании новой группы ролей можно настроить все параметры вручную (во время создания группы или после нее).</span><span class="sxs-lookup"><span data-stu-id="4a246-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="4a246-169">Кроме того, вы можете скопировать существующую группу ролей и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="4a246-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="4a246-170">Чтобы вручную создать новую группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4a246-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="4a246-171">Параметр _roles_ указывает роли управления, которые необходимо назначить группе ролей, используя следующий синтаксис `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="4a246-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="4a246-172">Доступные роли можно просмотреть с помощью командлета **Get – ManagementRole** .</span><span class="sxs-lookup"><span data-stu-id="4a246-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="4a246-173">Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="4a246-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="4a246-174">Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты (универсальные группы безопасности) или другие группы ролей (субъекты безопасности).</span><span class="sxs-lookup"><span data-stu-id="4a246-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="4a246-175">В этом примере создается новая группа ролей с именем "ограниченный Управление получателями" со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="4a246-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="4a246-176">Роль получателей почты назначается группе ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="4a246-177">Пользователи Kim и Мартен добавляются в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="4a246-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="4a246-178">Чтобы скопировать существующую группу ролей, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4a246-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="4a246-179">Сохраните группу ролей, которую необходимо копировать, в переменной с помощью следующей синтаксической конструкции:</span><span class="sxs-lookup"><span data-stu-id="4a246-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="4a246-180">Создайте новую группу ролей, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4a246-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="4a246-181">Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="4a246-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="4a246-182">Можно указать пользователей, универсальные группы безопасности с включенной поддержкой почты (универсальные группы безопасности) или другие группы ролей (субъекты безопасности).</span><span class="sxs-lookup"><span data-stu-id="4a246-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="4a246-183">В этом примере группа ролей Управление организацией копируется в новую группу ролей с именем "ограниченное управление организацией".</span><span class="sxs-lookup"><span data-stu-id="4a246-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="4a246-184">Членами группы ролей являются Исабелле, Carter и Лукас.</span><span class="sxs-lookup"><span data-stu-id="4a246-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="4a246-185">Для получения подробных сведений о синтаксисе и параметре [New – RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="4a246-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="4a246-186">Использование изолированной EOP PowerShell изменение списка участников в группах ролей</span><span class="sxs-lookup"><span data-stu-id="4a246-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="4a246-187">Командлеты **Add RoleGroupMember** и **Remove – RoleGroupMember** добавляют или удаляют отдельных участников по одному.</span><span class="sxs-lookup"><span data-stu-id="4a246-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="4a246-188">Командлет **Update – RoleGroupMember** может заменить или изменить существующий список элементов.</span><span class="sxs-lookup"><span data-stu-id="4a246-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="4a246-189">Членами группы ролей могут быть пользователи, универсальные группы безопасности с включенной поддержкой почты (универсальные группы безопасности) или другие группы ролей (субъекты безопасности).</span><span class="sxs-lookup"><span data-stu-id="4a246-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="4a246-190">Чтобы изменить членов группы ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4a246-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="4a246-191">Чтобы _заменить_ существующий список элементов указанными значениями, используйте следующий синтаксис: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="4a246-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="4a246-192">Чтобы _выборочно изменить_ существующий список элементов, используйте следующий синтаксис: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="4a246-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="4a246-193">В этом примере все текущие участники группы ролей службы поддержки заменяются указанными пользователями.</span><span class="sxs-lookup"><span data-stu-id="4a246-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="4a246-194">В этом примере показано, как добавить Даигоро Акаи и удалить Valeria Баррио из списка участников в группе ролей службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="4a246-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="4a246-195">Подробные сведения о синтаксисе и параметрах можно найти в [статье Update – RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="4a246-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="4a246-196">Удаление групп ролей с помощью изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a246-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="4a246-197">Невозможно удалить встроенные группы ролей, но вы можете удалить созданные пользовательские группы ролей.</span><span class="sxs-lookup"><span data-stu-id="4a246-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="4a246-198">Чтобы удалить настраиваемую группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4a246-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="4a246-199">В этом примере удаляется группа ролей "Обучающие администраторы".</span><span class="sxs-lookup"><span data-stu-id="4a246-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="4a246-200">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="4a246-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4a246-201">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="4a246-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="4a246-202">Чтобы убедиться, что вы успешно скопировали группу ролей, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4a246-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="4a246-203">В центре администрирования Exchange перейдите в **Permissions** раздел \> **роли администратора**разрешений и убедитесь, что группа ролей указана (или не указана в списке).</span><span class="sxs-lookup"><span data-stu-id="4a246-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="4a246-204">Выберите группу ролей и проверьте параметры в области сведений или нажмите **изменить** ![ значок редактирования ](../../media/ITPro-EAC-EditIcon.png) , чтобы проверить параметры.</span><span class="sxs-lookup"><span data-stu-id="4a246-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="4a246-205">В Exchange Online PowerShell замените \<Role Group Name\> именем группы ролей и выполните следующую команду, чтобы убедиться, что группа ролей существует (или не существует), и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="4a246-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
