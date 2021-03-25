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
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Администраторы могут узнать, как назначать или удалять разрешения в центре администрирования Exchange (EAC) в Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206277"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="25b5b-103">Управление ролевыми группами в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="25b5b-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="25b5b-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="25b5b-104">**Applies to**</span></span>
-  [<span data-ttu-id="25b5b-105">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="25b5b-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="25b5b-106">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно использовать центр администрирования Exchange (EAC) для добавления пользователей в группы ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="25b5b-107">Добавление пользователей в группу ролей дает пользователям разрешения на выполнение определенных задач администрирования.</span><span class="sxs-lookup"><span data-stu-id="25b5b-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="25b5b-108">Вы также можете удалить пользователей из групп ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="25b5b-109">Дополнительные сведения о ролях и группах ролей см. в рублях [Permissions in standalone EOP.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="25b5b-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="25b5b-110">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="25b5b-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="25b5b-111">Чтобы открыть центр администрирования Exchange (EAC), см. в центре администрирования Exchange в режиме [автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="25b5b-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="25b5b-112">Чтобы открыть автономный EOP PowerShell, см. в обзоре [Connect to Exchange Online Protection PowerShell.](/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="25b5b-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="25b5b-113">Вам необходимо получить разрешения в Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="25b5b-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="25b5b-114">В частности, вам нужна роль **"Управление** ролью", которая по умолчанию назначена группе ролей **"Управление** организацией".</span><span class="sxs-lookup"><span data-stu-id="25b5b-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="25b5b-115">Дополнительные сведения см. в рублях Разрешения в автономных [EOP](feature-permissions-in-eop.md) и Use the EAC изменить список участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="25b5b-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="25b5b-116">Сведения о ярлыках клавиатуры, которые могут применяться к процедурам в этой статье, см. в статье Клавишные ярлыки для центра администрирования Exchange в [Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="25b5b-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="25b5b-117">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="25b5b-117">Having problems?</span></span> <span data-ttu-id="25b5b-118">Обратитесь за помощью на форум по [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="25b5b-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="25b5b-119">Использование EAC для управления группами ролей</span><span class="sxs-lookup"><span data-stu-id="25b5b-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="25b5b-120">Использование EAC для просмотра групп ролей</span><span class="sxs-lookup"><span data-stu-id="25b5b-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="25b5b-121">В EAC перейдите к **роли Администратора** \> **разрешений**.</span><span class="sxs-lookup"><span data-stu-id="25b5b-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="25b5b-122">Здесь перечислены все группы ролей в организации.</span><span class="sxs-lookup"><span data-stu-id="25b5b-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="25b5b-123">Выберите группу ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-123">Select a role group.</span></span> <span data-ttu-id="25b5b-124">На области Details показаны **имя,** **описание,** **назначены роли** и **управляемые** группой ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="25b5b-125">Вы также можете увидеть эту информацию, щелкнув **значок Edit** ![ Edit ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="25b5b-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="25b5b-126">Использование EAC для создания групп ролей</span><span class="sxs-lookup"><span data-stu-id="25b5b-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="25b5b-127">При создании новой группы ролей можно настроить все параметры самостоятельно (при создании группы или после).</span><span class="sxs-lookup"><span data-stu-id="25b5b-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="25b5b-128">Или можно скопировать существующую группу ролей и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="25b5b-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="25b5b-129">В EAC перейдите к роли **администратора permissions** и сделайте \> один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="25b5b-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="25b5b-130">**Вручную создайте новую группу ролей:** нажмите **кнопку Добавить значок** ![ Добавить ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="25b5b-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="25b5b-131">**Скопируйте существующую группу** ролей: выберите группу ролей, которую необходимо скопировать, а затем нажмите **значок Copy** ![ Copy ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="25b5b-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="25b5b-132">В **окне "Новая группа** ролей", которое отображается, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="25b5b-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="25b5b-133">**Имя.** Введите уникальное имя для группы ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="25b5b-134">**Описание.** Введите необязательное описание группы ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="25b5b-135">**Роли.** **Нажмите кнопку Добавить** значок Добавить или Удалить значок Удалить, чтобы выбрать или изменить роли, которые назначены ![ группе ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="25b5b-136">**Участники.** **Нажмите кнопку Добавить** ![ значок Добавить или ](../../media/ITPro-EAC-AddIcon.png) **Удалить** ![ значок ](../../media/ITPro-EAC-RemoveIcon.gif) Удалить, чтобы изменить членство в группе ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="25b5b-137">По завершению щелкните **Сохранить,** чтобы создать группу ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="25b5b-138">Использование EAC для изменения групп ролей</span><span class="sxs-lookup"><span data-stu-id="25b5b-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="25b5b-139">В EAC перейдите к роли **Администратора разрешений,** выберите группу ролей, которую необходимо изменить, а затем нажмите \>  **кнопку Изменить** ![ изменить ](../../media/ITPro-EAC-EditIcon.png) значок .</span><span class="sxs-lookup"><span data-stu-id="25b5b-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="25b5b-140">При изменении групп ролей доступны те же параметры, что и при создании групп ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="25b5b-141">Вы можете выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="25b5b-141">You can:</span></span>

- <span data-ttu-id="25b5b-142">Измените имя и описание.</span><span class="sxs-lookup"><span data-stu-id="25b5b-142">Change the name and description.</span></span>

- <span data-ttu-id="25b5b-143">Добавление и удаление ролей управления (создание или удаление назначений ролей).</span><span class="sxs-lookup"><span data-stu-id="25b5b-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="25b5b-144">Добавление и удаление участников.</span><span class="sxs-lookup"><span data-stu-id="25b5b-144">Add and remove members.</span></span>

<span data-ttu-id="25b5b-145">**Примечание.** Некоторые группы ролей (например, Управление организацией) ограничивают роли, которые можно удалить из группы.</span><span class="sxs-lookup"><span data-stu-id="25b5b-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="25b5b-146">Использование EAC измените список участников в группах ролей</span><span class="sxs-lookup"><span data-stu-id="25b5b-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="25b5b-147">В EAC перейдите к роли **Администратора** разрешений, выберите группу ролей, которую необходимо изменить, а затем нажмите \>  **кнопку Изменить** ![ значок Редактирование ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="25b5b-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="25b5b-148">На странице свойства групп ролей, открываемой в разделе **Members,** сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="25b5b-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="25b5b-149">Нажмите **кнопку Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="25b5b-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="25b5b-150">На странице, которая появится, найдите пользователя, который wou хотите добавить, а затем нажмите **кнопку добавить ->**.</span><span class="sxs-lookup"><span data-stu-id="25b5b-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="25b5b-151">Выберите пользователей и **нажмите кнопку добавить ->** раз по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="25b5b-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="25b5b-152">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="25b5b-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="25b5b-153">Выберите пользователей, которые необходимо удалить, а затем нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="25b5b-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="25b5b-154">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="25b5b-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="25b5b-155">После добавления или удаления членов группы ролей данным пользователям необходимо выйти из системы, а затем снова войти в нее, чтобы изменить административные права.</span><span class="sxs-lookup"><span data-stu-id="25b5b-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="25b5b-156">Использование EAC для удаления групп ролей</span><span class="sxs-lookup"><span data-stu-id="25b5b-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="25b5b-157">Вы не можете удалить встроенные группы ролей, но вы можете удалить созданные настраиваемые группы ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="25b5b-158">В EAC перейдите к **роли Администратора** \> **разрешений**.</span><span class="sxs-lookup"><span data-stu-id="25b5b-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="25b5b-159">Выберите группу ролей, которую необходимо удалить, а затем нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="25b5b-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="25b5b-160">Нажмите **кнопку Да** в появится окно подтверждения.</span><span class="sxs-lookup"><span data-stu-id="25b5b-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="25b5b-161">Использование PowerShell для управления группами ролей</span><span class="sxs-lookup"><span data-stu-id="25b5b-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="25b5b-162">Использование автономных групп ролей EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="25b5b-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="25b5b-163">Чтобы просмотреть группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="25b5b-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="25b5b-164">В этом примере возвращается сводный список всех групп ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="25b5b-165">В этом примере возвращаются подробные сведения для группы ролей с именем Администраторы получателей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="25b5b-166">В этом примере возвращаются все группы ролей, в которых пользователь Юлия является участником.</span><span class="sxs-lookup"><span data-stu-id="25b5b-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="25b5b-167">Для Юлии необходимо использовать значение DistinguishedName (DN), которое можно найти при запуске команды: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="25b5b-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="25b5b-168">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="25b5b-168">For detailed syntax and parameter information, see [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="25b5b-169">Использование автономных групп EOP PowerShell для создания групп ролей</span><span class="sxs-lookup"><span data-stu-id="25b5b-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="25b5b-170">При создании новой группы ролей можно настроить все параметры вручную (при создании группы или после).</span><span class="sxs-lookup"><span data-stu-id="25b5b-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="25b5b-171">Или можно скопировать существующую группу ролей и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="25b5b-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="25b5b-172">Чтобы вручную создать новую группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="25b5b-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="25b5b-173">Параметр _Roles_ указывает роли управления для назначения группе ролей с помощью следующего синтаксиса. `"Role1","Role1",..."RoleN"`</span><span class="sxs-lookup"><span data-stu-id="25b5b-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="25b5b-174">Доступные роли можно увидеть с помощью команды **Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="25b5b-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="25b5b-175">Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="25b5b-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="25b5b-176">Можно указать пользователей, универсальные группы безопасности с поддержкой почты (USGs) или другие группы ролей (принципы безопасности).</span><span class="sxs-lookup"><span data-stu-id="25b5b-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="25b5b-177">В этом примере создается новая группа ролей с именем "Управление ограниченными получателями" со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="25b5b-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="25b5b-178">Роль получателей почты назначена группе ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="25b5b-179">Пользователи Ким и Мартин добавляются в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="25b5b-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="25b5b-180">Чтобы скопировать существующую группу ролей, сделайте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="25b5b-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="25b5b-181">Сохраните группу ролей, которую необходимо копировать, в переменной с помощью следующей синтаксической конструкции:</span><span class="sxs-lookup"><span data-stu-id="25b5b-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="25b5b-182">Создайте новую группу ролей с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="25b5b-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="25b5b-183">Параметр _Members_ указывает членов группы ролей с помощью следующего синтаксиса: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="25b5b-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="25b5b-184">Можно указать пользователей, универсальные группы безопасности с поддержкой почты (USGs) или другие группы ролей (принципы безопасности).</span><span class="sxs-lookup"><span data-stu-id="25b5b-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="25b5b-185">В этом примере группа ролей управления организацией копируется в новую группу ролей с именем "Управление ограниченной организацией".</span><span class="sxs-lookup"><span data-stu-id="25b5b-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="25b5b-186">Участниками группы ролей являются Изабель, Картер и Лукас.</span><span class="sxs-lookup"><span data-stu-id="25b5b-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="25b5b-187">Подробные сведения о синтаксисах и параметрах можно получить [в New-RoleGroup.](/powershell/module/exchange/New-RoleGroup)</span><span class="sxs-lookup"><span data-stu-id="25b5b-187">For detailed syntax and parameter information, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="25b5b-188">Использование автономных EOP PowerShell измените список участников в группах ролей</span><span class="sxs-lookup"><span data-stu-id="25b5b-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="25b5b-189">Команды **Add-RoleGroupMember** и **Remove-RoleGroupMember** добавляют или удаляют отдельных участников по одному.</span><span class="sxs-lookup"><span data-stu-id="25b5b-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="25b5b-190">Комлет **Update-RoleGroupMember** может заменить или изменить существующий список участников.</span><span class="sxs-lookup"><span data-stu-id="25b5b-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="25b5b-191">Членами группы ролей могут быть пользователи, универсальные группы безопасности с поддержкой почты (USGs) или другие группы ролей (принципы безопасности).</span><span class="sxs-lookup"><span data-stu-id="25b5b-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="25b5b-192">Чтобы изменить членов группы ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="25b5b-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="25b5b-193">Чтобы _заменить_ существующий список участников значениями, которые вы указываете, используйте следующий синтаксис: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="25b5b-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="25b5b-194">Чтобы _выборочно_ изменить существующий список участников, используйте следующий синтаксис: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="25b5b-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="25b5b-195">В этом примере все текущие члены группы ролей службы поддержки заменяются указанными пользователями.</span><span class="sxs-lookup"><span data-stu-id="25b5b-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="25b5b-196">В этом примере Daigoro Akai удаляет Валерию Баррио из списка участников группы ролей службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="25b5b-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="25b5b-197">Подробные сведения о синтаксисах и параметрах см. в [обзоре Update-RoleGroupMember.](/powershell/module/exchange/Update-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="25b5b-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="25b5b-198">Для удаления групп ролей используйте автономные группы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="25b5b-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="25b5b-199">Вы не можете удалить встроенные группы ролей, но вы можете удалить созданные настраиваемые группы ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="25b5b-200">Чтобы удалить настраиваемую группу ролей, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="25b5b-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="25b5b-201">В этом примере удаляется группа ролей "Обучающие администраторы".</span><span class="sxs-lookup"><span data-stu-id="25b5b-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="25b5b-202">Дополнительные сведения о синтаксисе и параметрах см. в разделе [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="25b5b-202">For detailed syntax and parameter information, see [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="25b5b-203">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="25b5b-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="25b5b-204">Чтобы убедиться, что вы успешно скопировали группу ролей, сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="25b5b-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="25b5b-205">В EAC перейдите к роли **Администратор разрешений** и убедитесь, что указана (или не указана) группа \> ролей.</span><span class="sxs-lookup"><span data-stu-id="25b5b-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="25b5b-206">Выберите группу ролей и проверьте параметры в области Details или щелкните **значок Edit** ![ Edit для ](../../media/ITPro-EAC-EditIcon.png) проверки параметров.</span><span class="sxs-lookup"><span data-stu-id="25b5b-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="25b5b-207">В Exchange Online PowerShell замените имя группы ролей и запустите следующую команду для проверки существования группы ролей (или ее не существует) и проверки \<Role Group Name\> параметров:</span><span class="sxs-lookup"><span data-stu-id="25b5b-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```