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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Администраторы в автономных организациях Exchange Online Protection (EOP) могут научиться создавать, изменять и удалять группы рассылки и группы безопасности с включенной поддержкой почты в Центре администрирования Exchange (EAC) и в автономных службах Exchange Online Protection (EOP) PowerShell.
ms.openlocfilehash: 5ff7c61d51ded039b06d1faa98ba6390939b3413
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658849"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="eb4e2-103">Управление группами в EOP</span><span class="sxs-lookup"><span data-stu-id="eb4e2-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="eb4e2-104">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно создавать, изменять и удалять группы следующих типов:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="eb4e2-105">**Группы рассылки:** коллекция почтовых пользователей или других групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="eb4e2-106">Например, команды или другие группы, которым нужно получать или отправлять электронную почту в интересущую общую зону.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="eb4e2-107">Группы рассылки распространяются исключительно для рассылки сообщений электронной почты и не являются основными безопасностью (им не могут быть назначены разрешения).</span><span class="sxs-lookup"><span data-stu-id="eb4e2-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="eb4e2-108">**Группы безопасности с включенной** поддержкой почты: коллекция почтовых пользователей и других групп безопасности, которым требуются разрешения на доступ для ролей администраторов.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="eb4e2-109">Например, может потребоваться предоставить определенной группе пользователей разрешения администратора, чтобы они могли настраивать параметры для борьбы со спамом и вредоносными программами.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="eb4e2-110">По умолчанию новые группы безопасности с включенной поддержкой почты отклоняет сообщения от внешних (неавтоматированных) отправителей.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="eb4e2-111">Не добавляйте группы рассылки в группы безопасности с включенной поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-111">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="eb4e2-112">Вы можете управлять группами в Центре администрирования Exchange (EAC) и в автономных EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-112">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eb4e2-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="eb4e2-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eb4e2-114">Чтобы открыть Центр администрирования Exchange, см. центр [администрирования Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="eb4e2-115">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="eb4e2-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="eb4e2-116">При управлении группами в автономных EOP PowerShell может возникнуть регулирование.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-116">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="eb4e2-117">В процедурах PowerShell в этой статье используется метод пакетной обработки, который приводит к задержке распространения за несколько минут до того, как будут видны результаты команд.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-117">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="eb4e2-118">Для работы с процедурами, которые данная статья, вам должны быть назначены разрешения в Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="eb4e2-119">В частности, необходима роль **групп** рассылки, которая  по  умолчанию назначена группам ролей "Управление организацией" и "Управление получателями".</span><span class="sxs-lookup"><span data-stu-id="eb4e2-119">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="eb4e2-120">Дополнительные сведения см. в сведениях о разрешениях в автономных [EOP](feature-permissions-in-eop.md) и использовании EAC для изменения списка участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="eb4e2-121">Сведения о сочетаниях клавиш, которые могут применяться к процедурам в этой статье, см. в статье "Сочетания клавиш" в Центре администрирования [Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="eb4e2-122">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="eb4e2-122">Having problems?</span></span> <span data-ttu-id="eb4e2-123">Обратитесь за помощью на форум по [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="eb4e2-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="eb4e2-124">Управление группами рассылки с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="eb4e2-124">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="eb4e2-125">Создание групп с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="eb4e2-125">Use the EAC to create groups</span></span>

1. <span data-ttu-id="eb4e2-126">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-126">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="eb4e2-127">Щелкните **значок** ![ "Новый новый" и выберите один из ](../../media/ITPro-EAC-AddIcon.png) следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-127">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="eb4e2-128">**Группа рассылки.**</span><span class="sxs-lookup"><span data-stu-id="eb4e2-128">**Distribution group**</span></span>

   - <span data-ttu-id="eb4e2-129">**Группа безопасности с поддержкой электронной почты**</span><span class="sxs-lookup"><span data-stu-id="eb4e2-129">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="eb4e2-130">На новой открываемой странице группы настройте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-130">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="eb4e2-131">Параметры, помеченные <sup>\*</sup> как необходимые.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-131">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="eb4e2-132"><sup>\*</sup>**Отображаемая** фамилия: это имя отображается в адресной книге организации, в строке  "К:" при отправке электронной почты в эту группу и в списке "Группы" в EAC.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-132"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="eb4e2-133">Отображаемое имя является обязательным, должно быть уникальным и должно быть удобным для пользователя, чтобы пользователи распознали его.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-133">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="eb4e2-134"><sup>\*</sup>**Псевдоним:** в этом поле можно ввести имя псевдонима для группы.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-134"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="eb4e2-135">Псевдоним не может превышать 64 символа и должен быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-135">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="eb4e2-136">Когда пользователь внося псевдоним в строку "К" сообщения электронной почты, он сообразуется с отображаемой именем группы.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-136">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="eb4e2-137"><sup>\*</sup>**Адрес электронной** почты: адрес электронной почты состоит из псевдонима слева от символа @и домена справа.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-137"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="eb4e2-138">По умолчанию значение **псевдонима** используется в качестве значения псевдонима, но его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-138">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="eb4e2-139">Для значения домена щелкните в выпадаемом и выберите и примите домен в организации.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-139">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="eb4e2-140">**Описание:** это описание отображается в адресной книге и в области сведений в EAC.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-140">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="eb4e2-141"><sup>\*</sup>**Владельцы:** владелец группы может управлять членством в группах.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-141"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="eb4e2-142">По умолчанию владельцем группы становится пользователь, создавший ее.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-142">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="eb4e2-143">Для каждой группы должен существовать по крайней мере один владелец.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-143">All groups must have at least one owner.</span></span>

     <span data-ttu-id="eb4e2-144">Чтобы добавить владельцев, нажмите **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) "Добавить".</span><span class="sxs-lookup"><span data-stu-id="eb4e2-144">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="eb4e2-145">В отображаемом диалоговом окте найдите и выберите получателя или группу, а затем нажмите кнопку **add ->**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-145">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="eb4e2-146">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-146">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="eb4e2-147">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-147">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="eb4e2-148">Чтобы удалить владельца, выберите его и нажмите значок **"Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) удалить".</span><span class="sxs-lookup"><span data-stu-id="eb4e2-148">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="eb4e2-149">**Участники:** добавление и удаление участников группы.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-149">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="eb4e2-150">Чтобы добавить участников, нажмите **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) "Добавить".</span><span class="sxs-lookup"><span data-stu-id="eb4e2-150">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="eb4e2-151">В отображаемом диалоговом окте найдите и выберите получателя или группу, а затем нажмите кнопку **add ->**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-151">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="eb4e2-152">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-152">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="eb4e2-153">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-153">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="eb4e2-154">Чтобы удалить участника, выберите его и нажмите кнопку **"Удалить** ![ значок "Удалить". ](../../media/ITPro-EAC-RemoveIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-154">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="eb4e2-155">После завершения нажмите кнопку  "Сохранить", чтобы создать группу рассылки.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-155">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="eb4e2-156">Использование EAC для изменения групп рассылки</span><span class="sxs-lookup"><span data-stu-id="eb4e2-156">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="eb4e2-157">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-157">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="eb4e2-158">В списке групп выберите группу рассылки или группу безопасности с включенной поддержкой почты, которую необходимо изменить, и нажмите значок  ![ редактирования. ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-158">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="eb4e2-159">На открываемой странице свойств группы рассылки щелкните одну из следующих вкладок, чтобы просмотреть или изменить свойства.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-159">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="eb4e2-160">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-160">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="eb4e2-161">Общие</span><span class="sxs-lookup"><span data-stu-id="eb4e2-161">General</span></span>

<span data-ttu-id="eb4e2-162">Эта вкладка позволяет просмотреть или изменить основные сведения о группе.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-162">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="eb4e2-163">**Отображаемая** имя: это имя отображается в адресной книге, в строке "К" при отправке электронной почты в эту группу и в **списке "Группы".**</span><span class="sxs-lookup"><span data-stu-id="eb4e2-163">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="eb4e2-164">Отображаемое имя обязательно и должно быть понятным, чтобы пользователи могли понять его назначение.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-164">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="eb4e2-165">Кроме того, оно должно быть уникальным в пределах домена.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-165">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="eb4e2-166">Если используется политика именования групп, отображаемое имя должно соответствовать заданному в ней формату именования.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-166">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="eb4e2-167">**Псевдоним:** это часть адреса электронной почты, которая отображается слева от символа @.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-167">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="eb4e2-168">Если изменить псевдоним, основной адрес SMTP группы также изменится и будет содержать новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-168">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="eb4e2-169">Кроме того, адрес электронной почты с предыдущим псевдонимом сохранится в качестве прокси-адреса группы.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-169">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="eb4e2-170">**Адрес электронной** почты: адрес электронной почты состоит из псевдонима слева от символа @и домена справа.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-170">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="eb4e2-171">По умолчанию значение **псевдонима** используется в качестве значения псевдонима, но его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-171">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="eb4e2-172">Для значения домена щелкните в выпадаемом и выберите и примите домен в организации.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-172">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="eb4e2-173">**Описание:** это описание отображается в адресной книге и в области сведений в EAC.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-173">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="eb4e2-174">Собственность</span><span class="sxs-lookup"><span data-stu-id="eb4e2-174">Ownership</span></span>

<span data-ttu-id="eb4e2-175">Эта вкладка используется для назначения владельцев группы.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-175">Use this tab to assign group owners.</span></span> <span data-ttu-id="eb4e2-176">Владелец группы может управлять членством в группах.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-176">A group owner can manage group membership.</span></span> <span data-ttu-id="eb4e2-177">По умолчанию владельцем группы становится пользователь, создавший ее.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-177">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="eb4e2-178">Для каждой группы должен существовать по крайней мере один владелец.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-178">All groups must have at least one owner.</span></span>

<span data-ttu-id="eb4e2-179">Чтобы добавить владельцев, нажмите **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) "Добавить".</span><span class="sxs-lookup"><span data-stu-id="eb4e2-179">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="eb4e2-180">В отображаемом диалоговом окте найдите и выберите получателя, а затем нажмите кнопку **add ->.**</span><span class="sxs-lookup"><span data-stu-id="eb4e2-180">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="eb4e2-181">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="eb4e2-182">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-182">When you're finished, click **OK**.</span></span>

<span data-ttu-id="eb4e2-183">Чтобы удалить владельца, выберите его и нажмите значок **"Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) удалить".</span><span class="sxs-lookup"><span data-stu-id="eb4e2-183">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="eb4e2-184">Участие</span><span class="sxs-lookup"><span data-stu-id="eb4e2-184">Membership</span></span>

<span data-ttu-id="eb4e2-185">Эта вкладка используется для добавления или удаления членов группы.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-185">Use this tab to add or remove group members.</span></span> <span data-ttu-id="eb4e2-186">Владельцы группы не должны быть ее членами.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-186">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="eb4e2-187">Чтобы добавить участников, нажмите **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) "Добавить".</span><span class="sxs-lookup"><span data-stu-id="eb4e2-187">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="eb4e2-188">В отображаемом диалоговом окте найдите и выберите получателя или группу, а затем нажмите кнопку **add ->**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-188">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="eb4e2-189">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-189">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="eb4e2-190">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-190">When you're finished, click **OK**.</span></span>

<span data-ttu-id="eb4e2-191">Чтобы удалить участника, выберите его и нажмите кнопку **"Удалить** ![ значок "Удалить". ](../../media/ITPro-EAC-RemoveIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-191">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="eb4e2-192">Использование EAC для удаления групп</span><span class="sxs-lookup"><span data-stu-id="eb4e2-192">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="eb4e2-193">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-193">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="eb4e2-194">В списке групп выберите группу рассылки, которую нужно удалить, и нажмите значок **"Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) удалить".</span><span class="sxs-lookup"><span data-stu-id="eb4e2-194">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="eb4e2-195">Использование PowerShell для управления группами</span><span class="sxs-lookup"><span data-stu-id="eb4e2-195">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="eb4e2-196">Просмотр групп с помощью автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb4e2-196">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="eb4e2-197">Чтобы получить сводный список всех групп рассылки и групп безопасности с включенной поддержкой почты в автономных EOP PowerShell, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-197">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="eb4e2-198">Чтобы получить список членов группы, замените имя, псевдоним или адрес электронной почты группы и запустите \<GroupIdentity\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-198">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="eb4e2-199">Подробные сведения о синтаксисах и параметрах см. в описании [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) и [Get-DistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-199">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="eb4e2-200">Создание групп с помощью автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb4e2-200">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="eb4e2-201">Чтобы создать группы рассылки или группы безопасности с включенной поддержкой почты в автономных EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-201">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="eb4e2-202">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-202">**Notes**:</span></span>

- <span data-ttu-id="eb4e2-203">Параметр _Name_ является обязательным, имеет максимальную длину 64 символа и должен быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-203">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="eb4e2-204">Если вы не используете параметр _DisplayName_, для отображаемого имени указывается значение параметра _Name_.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-204">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="eb4e2-205">Если параметр _Alias_ не используется, в качестве значения псевдонима используется параметр _Name._</span><span class="sxs-lookup"><span data-stu-id="eb4e2-205">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="eb4e2-206">Пробелы удаляются, а неподтвержденные символы преобразуются в вопросии (?).</span><span class="sxs-lookup"><span data-stu-id="eb4e2-206">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="eb4e2-207">Если параметр _PrimarySmtpAddress_ не используется, значение псевдонима используется в _параметре PrimarySmtpAddress._</span><span class="sxs-lookup"><span data-stu-id="eb4e2-207">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="eb4e2-208">Если параметр Type не используется, _по_ умолчанию используется значение Distribution.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-208">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="eb4e2-209">В этом примере создается группа рассылки с именем "ИТ-администраторы" с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-209">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="eb4e2-210">Подробные сведения о синтаксисах и параметрах см. в описании [New-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-210">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="eb4e2-211">Использование автономных EOP PowerShell для изменения групп</span><span class="sxs-lookup"><span data-stu-id="eb4e2-211">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="eb4e2-212">Чтобы изменить группы в автономных EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-212">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="eb4e2-213">В этом примере используется изменение основного SMTP-адреса (также называемого адресом ответа) группы Seattle Employees для sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-213">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="eb4e2-214">В этом примере заменяется текущий член группы "Группа безопасности" на Юдий Петрсен и Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-214">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="eb4e2-215">В этом примере новый пользователь с именем Tyson Fawcett добавляется в группу "Группа безопасности" при сохранении текущих членов группы.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-215">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="eb4e2-216">Подробные сведения о синтаксисах и параметрах см. в описании [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) и [Update-EOPDistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-216">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="eb4e2-217">Удаление группы с помощью удаленного Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb4e2-217">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="eb4e2-218">В этом примере удаляется группа рассылки с именем "ИТ-администраторы".</span><span class="sxs-lookup"><span data-stu-id="eb4e2-218">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="eb4e2-219">Подробные сведения о синтаксисах и параметрах см. в описании [Remove-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)</span><span class="sxs-lookup"><span data-stu-id="eb4e2-219">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="eb4e2-220">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="eb4e2-220">How do you know these procedures worked?</span></span>

<span data-ttu-id="eb4e2-221">Чтобы убедиться, что вы успешно создали, изменили или удалили группу рассылки или группу безопасности с включенной поддержкой почты, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-221">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="eb4e2-222">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-222">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="eb4e2-223">Убедитесь, что группа указана (или не указана) и проверьте значение **типа** группы.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-223">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="eb4e2-224">Выберите группу и просмотреть сведения в области  сведений или нажмите значок редактирования, ![ чтобы ](../../media/ITPro-EAC-AddIcon.png) просмотреть параметры.</span><span class="sxs-lookup"><span data-stu-id="eb4e2-224">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="eb4e2-225">В автономных EOP PowerShell запустите следующую команду, чтобы убедиться, что группа указана в списке (или не указана):</span><span class="sxs-lookup"><span data-stu-id="eb4e2-225">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="eb4e2-226">Замените имя, псевдоним или адрес электронной почты группы и запустите следующую команду, чтобы проверить \<GroupIdentity\> параметры:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-226">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="eb4e2-227">Чтобы просмотреть участников группы, замените имя, псевдоним или адрес электронной почты группы и запустите \<GroupIdentity\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="eb4e2-227">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
