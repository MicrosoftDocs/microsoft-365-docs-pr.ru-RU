---
title: Управление группами в EOP
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: С помощью Exchange Online Protection (EOP) для организации Exchange можно создавать группы с включенной поддержкой почты. EOP также позволяет определять или обновлять свойства групп, указывающие членство, адреса электронной почты и другие данные групп.
ms.openlocfilehash: ae4e0a8c39c97720cb51c0f5d7b69547258b11b7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598996"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="1878e-104">Управление группами в EOP</span><span class="sxs-lookup"><span data-stu-id="1878e-104">Manage groups in EOP</span></span>

 <span data-ttu-id="1878e-p102">С помощью Exchange Online Protection (EOP) для организации Exchange можно создавать группы с включенной поддержкой почты. EOP также позволяет определять или обновлять свойства групп, указывающие членство, адреса электронной почты и другие данные групп. В зависимости от своих требований вы можете создать группы рассылки или группы безопасности. Такие группы можно создать с помощью Центра администрирования Exchange или удаленной консоли Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1878e-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="1878e-109">Типы групп с включенной поддержкой почты</span><span class="sxs-lookup"><span data-stu-id="1878e-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="1878e-110">Для организации Exchange вы можете создать группы двух типов.</span><span class="sxs-lookup"><span data-stu-id="1878e-110">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="1878e-111">Группы рассылки — это коллекции пользователей электронной почты, таких как группа или другая группа "ad hoc", которая должна получать или отправлять электронную почту относительно общей области.</span><span class="sxs-lookup"><span data-stu-id="1878e-111">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="1878e-112">Группы рассылки создаются исключительно для распространения сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1878e-112">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="1878e-113">В EOP под группой рассылки подразумевается любая группа с включенной поддержкой почты вне зависимости от ее контекста безопасности.</span><span class="sxs-lookup"><span data-stu-id="1878e-113">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="1878e-114">Группы безопасности — это коллекции пользователей электронной почты, которым требуются разрешения на доступ для ролей администратора.</span><span class="sxs-lookup"><span data-stu-id="1878e-114">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="1878e-115">Например, вам может понадобиться предоставить определенной группе пользователей разрешения на уровне роли администратора, чтобы они могли настраивать параметры защиты от нежелательной почты и вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="1878e-115">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1878e-p105">По умолчанию все новые группы безопасности требуют проверки подлинности всех отправителей. Это запрещает внешним отправителям отправлять сообщения в группы безопасности с включенной поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="1878e-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1878e-118">Приступая к работе</span><span class="sxs-lookup"><span data-stu-id="1878e-118">Before you begin</span></span>

- <span data-ttu-id="1878e-p106">Для выполнения этих процедур необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в статье Запись "Группы рассылки и группы безопасности" в разделе [Разрешения на функции в службе EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="1878e-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="1878e-121">Чтобы открыть центр администрирования Exchange, ознакомьтесь со статьей [центр администрирования Exchange в Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="1878e-121">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="1878e-122">Имейте в виду, что при создании групп и управлении ими с помощью командлетов PowerShell для Exchange Online Protection вы можете столкнуться с регулированием.</span><span class="sxs-lookup"><span data-stu-id="1878e-122">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="1878e-123">В процедурах PowerShell, приведенных в этом разделе, используется метод пакетной обработки, который приводит к задержке распространения в течение нескольких минут до того, как результаты команд будут видны.</span><span class="sxs-lookup"><span data-stu-id="1878e-123">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="1878e-124">Сведения об использовании Windows PowerShell для подключения к службе Exchange Online Protection см. в статье [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1878e-124">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1878e-125">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="1878e-125">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="1878e-126">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="1878e-126">Having problems?</span></span> <span data-ttu-id="1878e-127">Обратитесь за помощью к форуму [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="1878e-127">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="1878e-128">Создание группы в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="1878e-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="1878e-129">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="1878e-129">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="1878e-130">Нажмите кнопку **создать** ![значок](../media/ITPro-EAC-AddIcon.gif)добавить, а затем выберите **группу рассылки** или **группу безопасности**, в зависимости от ваших потребностей.</span><span class="sxs-lookup"><span data-stu-id="1878e-130">Click **New** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="1878e-131">На странице **Новая группа рассылки** или **Новая группа безопасности** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="1878e-131">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="1878e-132">**Отображаемое имя**: введите понятное имя, которое является уникальным для Организации и имеет значение для пользователей EOP.</span><span class="sxs-lookup"><span data-stu-id="1878e-132">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="1878e-133">Отображаемое имя является обязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="1878e-133">The display name is required.</span></span>

   - <span data-ttu-id="1878e-134">**Псевдоним**: введите псевдоним группы длиной до 64 символов, уникальный для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1878e-134">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="1878e-135">Пользователи EOP вводят псевдоним в строке "Кому:" сообщения электронной почты, и он сопоставляется с отображаемым именем группы.</span><span class="sxs-lookup"><span data-stu-id="1878e-135">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="1878e-136">Если изменить псевдоним, основной SMTP-адрес группы также изменится и будет содержать новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="1878e-136">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="1878e-137">Псевдоним является обязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="1878e-137">The alias is required.</span></span>

   - <span data-ttu-id="1878e-138">**Описание**: введите описание группы, чтобы люди знали назначение этой группы.</span><span class="sxs-lookup"><span data-stu-id="1878e-138">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="1878e-139">**Владельцы**: по умолчанию владельцем является пользователь, который создает группу.</span><span class="sxs-lookup"><span data-stu-id="1878e-139">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="1878e-140">Чтобы добавить владельца, нажмите кнопку **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="1878e-140">You can add an owner by choosing **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="1878e-141">Для каждой группы должен существовать по крайней мере один владелец.</span><span class="sxs-lookup"><span data-stu-id="1878e-141">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1878e-142">Владельцы не обязательно должны быть членами группы.</span><span class="sxs-lookup"><span data-stu-id="1878e-142">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="1878e-143">**Members**: Используйте этот раздел, чтобы добавить участников группы и указать, требуется ли утверждение для пользователей присоединения к группе или выхода из нее.</span><span class="sxs-lookup"><span data-stu-id="1878e-143">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="1878e-144">Чтобы добавить участников в группу, нажмите кнопку **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="1878e-144">To add members to the group, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="1878e-145">Нажмите кнопку **ОК**, чтобы вернуться на исходную страницу.</span><span class="sxs-lookup"><span data-stu-id="1878e-145">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="1878e-p112">Закончив, нажмите кнопку **Сохранить**, чтобы создать группу. Новая группа должна отобразиться в списке групп.</span><span class="sxs-lookup"><span data-stu-id="1878e-p112">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="1878e-148">Изменение или удаление группы в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="1878e-148">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="1878e-149">В Центре администрирования Exchange последовательно выберите пункты **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="1878e-149">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="1878e-150">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1878e-150">Do one of the following steps:</span></span>

   - <span data-ttu-id="1878e-151">Чтобы изменить группу, выберите группу, которую нужно просмотреть или изменить, и нажмите кнопку **изменить** ![значок](../media/ITPro-EAC-EditIcon.gif)редактирования.</span><span class="sxs-lookup"><span data-stu-id="1878e-151">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="1878e-152">Вы можете обновлять Общие параметры, добавлять и удалять владельцев групп, а также добавлять и удалять участников групп по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="1878e-152">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="1878e-153">Чтобы удалить группу, выберите группу и нажмите кнопку **Удалить** ![значок](../media/ITPro-EAC-RemoveIcon.gif)"Удалить".</span><span class="sxs-lookup"><span data-stu-id="1878e-153">To remove a group: Select the group and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="1878e-154">После внесения изменений нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1878e-154">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="1878e-155">Создание, изменение или удаление группы с помощью удаленной консоли Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1878e-155">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="1878e-156">В этом разделе представлены сведения о создании групп и изменении их свойств в Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1878e-156">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="1878e-157">В нем также рассказывается об удалении существующей группы.</span><span class="sxs-lookup"><span data-stu-id="1878e-157">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="1878e-158">Создание группы с помощью удаленной оболочки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1878e-158">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="1878e-p115">В этом примере командлет [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) используется для создания группы рассылки с псевдонимом "itadmin" и именем "ИТ-администраторы". Кроме того, он добавляет пользователей как членов группы.</span><span class="sxs-lookup"><span data-stu-id="1878e-p115">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="1878e-161">**Note**: чтобы создать группу безопасности вместо группы рассылки, используйте значение `Security` параметра *Type* .</span><span class="sxs-lookup"><span data-stu-id="1878e-161">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="1878e-162">Чтобы убедиться, что группа "ИТ Administrators" успешно создана, выполните следующую команду, чтобы отобразить сведения о новой группе:</span><span class="sxs-lookup"><span data-stu-id="1878e-162">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="1878e-163">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span><span class="sxs-lookup"><span data-stu-id="1878e-163">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="1878e-164">Чтобы получить список членов группы, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1878e-164">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="1878e-165">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="1878e-165">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="1878e-166">Чтобы получить полный список всех групп, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1878e-166">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="1878e-167">Изменение свойств группы с помощью удаленной оболочки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1878e-167">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="1878e-168">Преимуществом использования PowerShell вместо центра администрирования Exchange является возможность изменения свойств нескольких групп.</span><span class="sxs-lookup"><span data-stu-id="1878e-168">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="1878e-169">Ниже приведено несколько примеров использования Exchange Online Protection PowerShell для изменения свойств групп.</span><span class="sxs-lookup"><span data-stu-id="1878e-169">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="1878e-170">В этом примере используются изменения основного SMTP-адреса (также называемого адресом ответа) для группы Employees в Сиэтле до sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1878e-170">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="1878e-171">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – eopdistributiongroup используется](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="1878e-171">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="1878e-172">Чтобы убедиться, что вы успешно изменили свойства группы, выполните следующую команду, чтобы проверить новое значение:</span><span class="sxs-lookup"><span data-stu-id="1878e-172">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="1878e-173">В этом примере обновляются все участники группы Employees в Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="1878e-173">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="1878e-174">Разделяйте всех членов запятой.</span><span class="sxs-lookup"><span data-stu-id="1878e-174">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="1878e-175">Подробные сведения о синтаксисе и параметрах можно найти в [статье Update – еопдистрибутионграупмембер](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="1878e-175">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="1878e-176">Чтобы получить список всех участников группы сотрудники в Сиэтле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1878e-176">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="1878e-177">Удаление группы с помощью удаленной оболочки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1878e-177">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="1878e-178">В этом примере показано, как удалить группу рассылки с именем IT Administrators.</span><span class="sxs-lookup"><span data-stu-id="1878e-178">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="1878e-179">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – eopdistributiongroup используется](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="1878e-179">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="1878e-180">Чтобы убедиться, что группа удалена, выполните следующую команду и убедитесь, что группа (в данном случае "ИТ-администраторы") удалена.</span><span class="sxs-lookup"><span data-stu-id="1878e-180">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
