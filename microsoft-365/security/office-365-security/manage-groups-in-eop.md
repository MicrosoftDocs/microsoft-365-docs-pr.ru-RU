---
title: Управление группами в EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Администраторы в автономных организациях Exchange Online Protection (EOP) могут научиться создавать, изменять и удалять группы рассылки и группы безопасности с поддержкой почты в центре администрирования Exchange (EAC) и в автономных powerShell Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b97e3fac0840753edada964252875a6e3a4fa04
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205058"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="7fbd3-103">Управление группами в EOP</span><span class="sxs-lookup"><span data-stu-id="7fbd3-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7fbd3-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="7fbd3-104">**Applies to**</span></span>
-  [<span data-ttu-id="7fbd3-105">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7fbd3-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="7fbd3-106">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно создавать, изменять и удалять следующие типы групп:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="7fbd3-107">**Группы рассылки:** коллекция пользователей почты или других групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="7fbd3-108">Например, группы или другие группы, которым необходимо получать или отправлять электронную почту в общей области, интересуемой.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="7fbd3-109">Группы рассылки исключительно для распространения сообщений электронной почты и не являются директорами безопасности (им не могут быть назначены разрешения).</span><span class="sxs-lookup"><span data-stu-id="7fbd3-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="7fbd3-110">**Группы безопасности с поддержкой почты:** коллекция пользователей почты и других групп безопасности, которым необходимы разрешения на доступ для ролей администратора.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="7fbd3-111">Например, может потребоваться предоставить определенной группе пользователей разрешения администратора, чтобы они могли настраивать параметры для борьбы со спамом и вредоносными программами.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="7fbd3-112">По умолчанию новые группы безопасности с поддержкой почты отклоняет сообщения от внешних (неавентированных) отправителей.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="7fbd3-113">Не добавляйте группы рассылки в группы безопасности с поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="7fbd3-114">Вы можете управлять группами в центре администрирования Exchange (EAC) и в автономных центрах EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7fbd3-115">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7fbd3-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7fbd3-116">Чтобы открыть центр администрирования Exchange, см. в [центре администрирования Exchange в режиме автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="7fbd3-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="7fbd3-117">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="7fbd3-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7fbd3-118">При управлении группами в автономных EOP PowerShell может возникнуть регулирование.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="7fbd3-119">Процедуры PowerShell в этой статье используют метод пакетной обработки, который приводит к задержке распространения за несколько минут до того, как будут видны результаты команд.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="7fbd3-120">Вам необходимо получить разрешения в Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="7fbd3-121">В частности, вам нужна роль **Группы** рассылки,  которая по умолчанию назначена группам ролей "Управление организацией" и "Управление  получателями".</span><span class="sxs-lookup"><span data-stu-id="7fbd3-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="7fbd3-122">Дополнительные сведения см. в рублях Разрешения в автономных [EOP](feature-permissions-in-eop.md) и Use the EAC изменить список участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="7fbd3-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="7fbd3-123">Сведения о ярлыках клавиатуры, которые могут применяться к процедурам в этой статье, см. в статье Клавишные ярлыки для центра администрирования Exchange в [Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="7fbd3-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="7fbd3-124">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="7fbd3-124">Having problems?</span></span> <span data-ttu-id="7fbd3-125">Обратитесь за помощью на форум по [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="7fbd3-125">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="7fbd3-126">Центр администрирования Exchange используется для управления группами рассылки</span><span class="sxs-lookup"><span data-stu-id="7fbd3-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="7fbd3-127">Использование EAC для создания групп</span><span class="sxs-lookup"><span data-stu-id="7fbd3-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="7fbd3-128">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="7fbd3-129">Щелкните **новый** ![ значок ](../../media/ITPro-EAC-AddIcon.png) New, а затем выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="7fbd3-130">**Группа рассылки.**</span><span class="sxs-lookup"><span data-stu-id="7fbd3-130">**Distribution group**</span></span>

   - <span data-ttu-id="7fbd3-131">**Группа безопасности с поддержкой электронной почты**</span><span class="sxs-lookup"><span data-stu-id="7fbd3-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="7fbd3-132">На открываемой странице группы настройте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="7fbd3-133">Необходимы параметры, <sup>\*</sup> отмеченные с помощью параметра.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="7fbd3-134"><sup>\*</sup>**Отображение имени.** Это имя отображается в адресной книге организации, на строке To:  при отправке электронной почты в эту группу и в списке Групп в EAC.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="7fbd3-135">Требуется имя отображения, оно должно быть уникальным и должно быть удобным для пользователя, чтобы люди узнали, что это такое.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="7fbd3-136"><sup>\*</sup>**Псевдоним:** Используйте этот поле для введите имя псевдонима для группы.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="7fbd3-137">Псевдоним не может превышать 64 символов и должен быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="7fbd3-138">При типе псевдонима в строке To сообщения электронной почты пользователь решает имя отображения группы.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="7fbd3-139"><sup>\*</sup>**Адрес электронной** почты: адрес электронной почты состоит из псевдонима на левой стороне символа at (@) и домена справа.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="7fbd3-140">По умолчанию значение **Alias** используется для значения псевдонима, но его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="7fbd3-141">Для значения домена щелкните падение вниз и выберите и принятый домен в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="7fbd3-142">**Описание.** Это описание отображается в адресной книге и в области Подробные сведения в EAC.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="7fbd3-143"><sup>\*</sup>**Владельцы.** Владелец группы может управлять членством в группе.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="7fbd3-144">По умолчанию владельцем группы становится пользователь, создавший ее.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="7fbd3-145">Для каждой группы должен существовать по крайней мере один владелец.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="7fbd3-146">Чтобы добавить владельцев, **нажмите кнопку Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="7fbd3-147">В диалоговом окте, который появится, найдите и выберите получателя или группу, а затем нажмите **кнопку добавить ->**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="7fbd3-148">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="7fbd3-149">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="7fbd3-150">Чтобы удалить владельца, выберите владельца и нажмите кнопку **Удалить значок Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="7fbd3-151">**Участники.** Добавляйте и удаляйте участников группы.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="7fbd3-152">Чтобы добавить участников, нажмите **кнопку Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="7fbd3-153">В диалоговом окте, который появится, найдите и выберите получателя или группу, а затем нажмите **кнопку добавить ->**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="7fbd3-154">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="7fbd3-155">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="7fbd3-156">Чтобы удалить члена, выберите члена, а затем нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="7fbd3-157">По завершению щелкните **Сохранить,** чтобы создать группу рассылки.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="7fbd3-158">Использование центра EAC для изменения групп рассылки</span><span class="sxs-lookup"><span data-stu-id="7fbd3-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="7fbd3-159">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="7fbd3-160">В списке групп выберите группу рассылки или группу безопасности с поддержкой почты, которую необходимо изменить, и нажмите кнопку **Изменить** ![ значок Изменить ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="7fbd3-161">На открываемой странице свойств групп рассылки щелкните одну из следующих вкладок, чтобы просмотреть или изменить свойства.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="7fbd3-162">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="7fbd3-163">Общие</span><span class="sxs-lookup"><span data-stu-id="7fbd3-163">General</span></span>

<span data-ttu-id="7fbd3-164">Эта вкладка позволяет просмотреть или изменить основные сведения о группе.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="7fbd3-165">**Отображение имени.** Это имя отображается в адресной книге, в строке To при отправке электронной почты в эту группу и в **списке Групп.**</span><span class="sxs-lookup"><span data-stu-id="7fbd3-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="7fbd3-166">Отображаемое имя обязательно и должно быть понятным, чтобы пользователи могли понять его назначение.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="7fbd3-167">Кроме того, оно должно быть уникальным в пределах домена.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="7fbd3-168">Если используется политика именования групп, отображаемое имя должно соответствовать заданному в ней формату именования.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="7fbd3-169">**Псевдоним.** Это часть адреса электронной почты, который отображается слева от символа at (@).</span><span class="sxs-lookup"><span data-stu-id="7fbd3-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="7fbd3-170">Если изменить псевдоним, основной адрес SMTP группы также изменится и будет содержать новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="7fbd3-171">Кроме того, адрес электронной почты с предыдущим псевдонимом сохранится в качестве прокси-адреса группы.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="7fbd3-172">**Адрес электронной** почты: адрес электронной почты состоит из псевдонима на левой стороне символа at (@) и домена справа.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="7fbd3-173">По умолчанию значение **Alias** используется для значения псевдонима, но его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="7fbd3-174">Для значения домена щелкните падение вниз и выберите и принятый домен в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="7fbd3-175">**Описание.** Это описание отображается в адресной книге и в области Подробные сведения в EAC.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="7fbd3-176">Собственность</span><span class="sxs-lookup"><span data-stu-id="7fbd3-176">Ownership</span></span>

<span data-ttu-id="7fbd3-177">Используйте эту вкладку для назначения владельцев групп.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="7fbd3-178">Владелец группы может управлять членством в группе.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-178">A group owner can manage group membership.</span></span> <span data-ttu-id="7fbd3-179">По умолчанию владельцем группы становится пользователь, создавший ее.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="7fbd3-180">Для каждой группы должен существовать по крайней мере один владелец.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="7fbd3-181">Чтобы добавить владельцев, **нажмите кнопку Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="7fbd3-182">В диалоговом окте, который появится, найдите и выберите получателя, а затем нажмите **добавить ->**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="7fbd3-183">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="7fbd3-184">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="7fbd3-185">Чтобы удалить владельца, выберите владельца и нажмите кнопку **Удалить значок Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="7fbd3-186">Участие</span><span class="sxs-lookup"><span data-stu-id="7fbd3-186">Membership</span></span>

<span data-ttu-id="7fbd3-187">Эта вкладка используется для добавления или удаления членов группы.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="7fbd3-188">Владельцам групп не нужно быть членами группы.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="7fbd3-189">Чтобы добавить участников, нажмите **кнопку Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="7fbd3-190">В диалоговом окте, который появится, найдите и выберите получателя или группу, а затем нажмите **кнопку добавить ->**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="7fbd3-191">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="7fbd3-192">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="7fbd3-193">Чтобы удалить члена, выберите члена, а затем нажмите **кнопку Удалить значок Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="7fbd3-194">Использование EAC для удаления групп</span><span class="sxs-lookup"><span data-stu-id="7fbd3-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="7fbd3-195">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="7fbd3-196">В списке групп выберите группу рассылки, которую необходимо удалить, а затем нажмите кнопку **Удалить значок Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7fbd3-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="7fbd3-197">Использование PowerShell для управления группами</span><span class="sxs-lookup"><span data-stu-id="7fbd3-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="7fbd3-198">Использование автономных EOP PowerShell для просмотра групп</span><span class="sxs-lookup"><span data-stu-id="7fbd3-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="7fbd3-199">Чтобы вернуть сводный список всех групп рассылки и групп безопасности с поддержкой почты в автономных EOP PowerShell, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="7fbd3-200">Чтобы вернуть список участников группы, замените имя, псевдоним или адрес электронной почты группы и запустите \<GroupIdentity\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="7fbd3-201">Подробные сведения о синтаксисах и параметрах см. в [сведениях Get-Recipient](/powershell/module/exchange/get-recipient) и [Get-DistributionGroupMember.](/powershell/module/exchange/get-distributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="7fbd3-201">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="7fbd3-202">Использование автономных EOP PowerShell для создания групп</span><span class="sxs-lookup"><span data-stu-id="7fbd3-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="7fbd3-203">Чтобы создать группы рассылки или группы безопасности с поддержкой почты в автономных EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="7fbd3-204">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-204">**Notes**:</span></span>

- <span data-ttu-id="7fbd3-205">Параметр _Name_ необходим, имеет максимальную длину 64 символа и должен быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="7fbd3-206">Если параметр _DisplayName_ не используется, для имени отображения используется значение _параметра Name._</span><span class="sxs-lookup"><span data-stu-id="7fbd3-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="7fbd3-207">Если параметр _Alias_ не используется, параметр _Name_ используется для значения псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="7fbd3-208">Пробелы будут удалены, а неподдерживаемые символы преобразованы в знаки вопроса (?).</span><span class="sxs-lookup"><span data-stu-id="7fbd3-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="7fbd3-209">Если параметр _PrimarySmtpAddress_ не используется, значение псевдонима используется в _параметре PrimarySmtpAddress._</span><span class="sxs-lookup"><span data-stu-id="7fbd3-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="7fbd3-210">Если параметр Type не  используется, по умолчанию используется значение Distribution.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="7fbd3-211">В этом примере создается группа рассылки с ИТ-администраторами с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="7fbd3-212">Подробные сведения о синтаксисах и параметрах см. в [обзоре New-EOPDistributionGroup.](/powershell/module/exchange/New-EOPDistributionGroup)</span><span class="sxs-lookup"><span data-stu-id="7fbd3-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="7fbd3-213">Использование автономных EOP PowerShell для изменения групп</span><span class="sxs-lookup"><span data-stu-id="7fbd3-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="7fbd3-214">Чтобы изменить группы в автономных EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="7fbd3-215">В этом примере используется изменение основного SMTP-адреса (также называемого адресом ответа) для группы сотрудников Сиэтла для sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="7fbd3-216">В этом примере вместо нынешних членов группы безопасности на Китти Петерсен и Тайсон Фосетт.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="7fbd3-217">В этом примере в группу с именем Security Team добавляется новый пользователь по имени Тайсон Фосетт, сохраняя при этом текущие члены группы.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="7fbd3-218">Подробные сведения о синтаксисах и параметрах см. в [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) и [Update-EOPDistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="7fbd3-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="7fbd3-219">Удалите группу с помощью удаленного Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fbd3-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="7fbd3-220">В этом примере используется удаление группы рассылки с именем ИТ-администраторов.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="7fbd3-221">Подробные сведения о синтаксисах и параметрах см. в [инструкции Remove-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)</span><span class="sxs-lookup"><span data-stu-id="7fbd3-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7fbd3-222">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="7fbd3-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="7fbd3-223">Чтобы убедиться, что вы успешно создали, изменили или удалили группу рассылки или группу безопасности с поддержкой почты, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="7fbd3-224">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="7fbd3-225">Убедитесь, что группа указана (или не указана), и проверьте значение **типа группы.**</span><span class="sxs-lookup"><span data-stu-id="7fbd3-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="7fbd3-226">Выберите группу и просмотреть сведения в области Details или щелкните **значок Edit** ![ Edit для просмотра ](../../media/ITPro-EAC-AddIcon.png) параметров.</span><span class="sxs-lookup"><span data-stu-id="7fbd3-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="7fbd3-227">В автономных EOP PowerShell запустите следующую команду, чтобы убедиться, что группа указана (или не указана):</span><span class="sxs-lookup"><span data-stu-id="7fbd3-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="7fbd3-228">Замените имя, псевдоним или адрес электронной почты группы и запустите следующую команду для проверки \<GroupIdentity\> параметров:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="7fbd3-229">Чтобы просмотреть участников группы, замените имя, псевдоним или адрес электронной почты группы и запустите \<GroupIdentity\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7fbd3-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```