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
description: Администраторы в автономных организациях Exchange Online Protection (EOP) могут узнать, как создавать, изменять и удалять группы рассылки и группы безопасности с включенной поддержкой почты, в PowerShell в Центре администрирования Exchange (EAC) и автономной службе Exchange Online Protection (EOP).
ms.openlocfilehash: e7b93b9d05fda7e4f5f8abea02fbe3f1c70a6c74
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826557"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="d9145-103">Управление группами в EOP</span><span class="sxs-lookup"><span data-stu-id="d9145-103">Manage groups in EOP</span></span>

<span data-ttu-id="d9145-104">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно создавать, изменять и удалять группы следующих типов.</span><span class="sxs-lookup"><span data-stu-id="d9145-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="d9145-105">**Группы рассылки:** коллекция почтовых пользователей или других групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="d9145-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="d9145-106">Например, команды или другие специализированные группы, которым необходимо получать или отправлять сообщения электронной почты в общем сфере интереса.</span><span class="sxs-lookup"><span data-stu-id="d9145-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="d9145-107">Группы рассылки предназначены исключительно для распространения сообщений электронной почты и не являются субъектами безопасности (у них нет прав.</span><span class="sxs-lookup"><span data-stu-id="d9145-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="d9145-108">**Группы безопасности, поддерживающие почту:** коллекция почтовых пользователей и другие группы безопасности, которым нужны разрешения на доступ для ролей администраторов.</span><span class="sxs-lookup"><span data-stu-id="d9145-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="d9145-109">Например, вам может понадобиться предоставить определенной группе пользователей разрешения администратора, чтобы они могли настраивать параметры защиты от нежелательной почты и вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="d9145-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="d9145-110">По умолчанию новые группы безопасности с включенной поддержкой почты отклоняют сообщения от внешних (не прошедших проверку подлинности) отправителей.</span><span class="sxs-lookup"><span data-stu-id="d9145-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="d9145-111">Не добавляйте группы рассылки в группы безопасности с включенной поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="d9145-111">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="d9145-112">Вы можете управлять группами с помощью Центра администрирования Exchange (EAC) и автономной службы EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9145-112">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d9145-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d9145-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d9145-114">Сведения о том, как открыть Центр администрирования [Exchange, см. в центре администрирования Exchange в автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="d9145-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="d9145-115">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d9145-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d9145-116">При управлении группами в автономной среде PowerShell EOP вы можете столкнуться с регулированием.</span><span class="sxs-lookup"><span data-stu-id="d9145-116">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="d9145-117">В процедурах, описанных в этой статье, используется метод пакетной обработки, из-за чего результаты команд будут отображены через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="d9145-117">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="d9145-118">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="d9145-118">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="d9145-119">В частности, вам потребуется роль групп рассылки, которая по умолчанию назначается группам ролей OrganizationManagement (глобальные администраторы) и RecipientManagement.</span><span class="sxs-lookup"><span data-stu-id="d9145-119">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="d9145-120">Дополнительные сведения см. в разделе ["Разрешения в автономной службе EOP"](feature-permissions-in-eop.md) и использовании Центра администрирования [Exchange для изменения списка членов в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="d9145-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="d9145-121">Сочетания клавиш для процедур, описанных в этой статье, приведены в разделе сочетания клавиш для [Центра администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="d9145-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="d9145-122">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="d9145-122">Having problems?</span></span> <span data-ttu-id="d9145-123">Обратитесь за помощью на форум по [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="d9145-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="d9145-124">Использование Центра администрирования Exchange для управления группами рассылки</span><span class="sxs-lookup"><span data-stu-id="d9145-124">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="d9145-125">Создание групп с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="d9145-125">Use the EAC to create groups</span></span>

1. <span data-ttu-id="d9145-126">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="d9145-126">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="d9145-127">Щелкните **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) "Создать" и выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d9145-127">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="d9145-128">**Группа рассылки.**</span><span class="sxs-lookup"><span data-stu-id="d9145-128">**Distribution group**</span></span>

   - <span data-ttu-id="d9145-129">**Группа безопасности с поддержкой электронной почты**</span><span class="sxs-lookup"><span data-stu-id="d9145-129">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="d9145-130">На открывшейся странице новой группы настройте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="d9145-130">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="d9145-131">Обязательными являются <sup>\*</sup> параметры.</span><span class="sxs-lookup"><span data-stu-id="d9145-131">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="d9145-132"><sup>\*</sup>**Отображаемое имя:** это имя будет отображаться в адресной книге, в поле "Кому" при отправке в эту группу электронного сообщения и в списке **"Группы"** в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="d9145-132"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="d9145-133">Отображаемое имя является обязательным, оно должно быть уникальным и должно быть понятным, чтобы пользователи могли по-разобраться на самом деле.</span><span class="sxs-lookup"><span data-stu-id="d9145-133">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="d9145-134"><sup>\*</sup>**Alias**(Псевдоним) — это поле используется для ввода псевдонима группы.</span><span class="sxs-lookup"><span data-stu-id="d9145-134"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="d9145-135">Длина псевдонима не должна превышать 64 символа и должен быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="d9145-135">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="d9145-136">Когда пользователь вводит псевдоним в строке "Кому" электронного сообщения, он сопоставляется с кратким именем группы.</span><span class="sxs-lookup"><span data-stu-id="d9145-136">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="d9145-137"><sup>\*</sup>**Адрес**электронной почты: электронный адрес состоит из псевдонима слева от символа @и домена справа от него.</span><span class="sxs-lookup"><span data-stu-id="d9145-137"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="d9145-138">По умолчанию псевдоним **используется** в качестве значения псевдонима, но его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="d9145-138">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="d9145-139">В качестве значения домена щелкните раскрывающийся список, а затем выберите обслуживаемый домен в организации.</span><span class="sxs-lookup"><span data-stu-id="d9145-139">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="d9145-140">**Описание:** это описание отображается в адресной книге на панели подробностей в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="d9145-140">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="d9145-141"><sup>\*</sup>**Владельцы:** владелец группы может управлять членством в группе.</span><span class="sxs-lookup"><span data-stu-id="d9145-141"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="d9145-142">По умолчанию владельцем группы становится пользователь, создавший ее.</span><span class="sxs-lookup"><span data-stu-id="d9145-142">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="d9145-143">Для каждой группы должен существовать по крайней мере один владелец.</span><span class="sxs-lookup"><span data-stu-id="d9145-143">All groups must have at least one owner.</span></span>

     <span data-ttu-id="d9145-144">Чтобы добавить владельцев, нажмите кнопку **Добавить** ![ значок "Добавить". ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="d9145-144">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="d9145-145">В отобразившемся диалоговом окне найдите и выберите получателя или группу, а затем \*\*нажмите кнопку добавить ->. \*\*</span><span class="sxs-lookup"><span data-stu-id="d9145-145">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="d9145-146">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="d9145-146">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="d9145-147">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d9145-147">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="d9145-148">Чтобы удалить владельца, выберите владельца и нажмите кнопку **"Удалить"** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="d9145-148">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="d9145-149">**Members:** Add and remove group members.</span><span class="sxs-lookup"><span data-stu-id="d9145-149">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="d9145-150">Чтобы добавить участников, нажмите кнопку **"Добавить"** ![ и значок "Добавить". ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="d9145-150">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="d9145-151">В отобразившемся диалоговом окне найдите и выберите получателя или группу, а затем \*\*нажмите кнопку добавить ->. \*\*</span><span class="sxs-lookup"><span data-stu-id="d9145-151">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="d9145-152">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="d9145-152">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="d9145-153">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d9145-153">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="d9145-154">Чтобы удалить члена, выберите его и нажмите кнопку **"Удалить" значок** ![ "Удалить". ](../../media/ITPro-EAC-RemoveIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="d9145-154">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="d9145-155">По завершении нажмите кнопку **"Сохранить",** чтобы создать группу рассылки.</span><span class="sxs-lookup"><span data-stu-id="d9145-155">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="d9145-156">Использование Центра администрирования Exchange для изменения групп рассылки</span><span class="sxs-lookup"><span data-stu-id="d9145-156">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="d9145-157">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="d9145-157">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="d9145-158">Выберите в списке группы рассылки или группу безопасности с включенной поддержкой почты, которую необходимо изменить, и нажмите **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="d9145-158">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="d9145-159">На открывшейся странице свойств группы рассылки выберите одну из следующих вкладок, чтобы просмотреть или изменить свойства.</span><span class="sxs-lookup"><span data-stu-id="d9145-159">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="d9145-160">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d9145-160">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="d9145-161">Общие</span><span class="sxs-lookup"><span data-stu-id="d9145-161">General</span></span>

<span data-ttu-id="d9145-162">Эта вкладка позволяет просмотреть или изменить основные сведения о группе.</span><span class="sxs-lookup"><span data-stu-id="d9145-162">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="d9145-163">**Отображаемое имя:** это имя будет отображаться в адресной книге, в строке "Кому" при отправке в эту группу электронного сообщения и в **списке "Группы".**</span><span class="sxs-lookup"><span data-stu-id="d9145-163">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="d9145-164">Отображаемое имя обязательно и должно быть понятным, чтобы пользователи могли понять его назначение.</span><span class="sxs-lookup"><span data-stu-id="d9145-164">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="d9145-165">Кроме того, оно должно быть уникальным в пределах домена.</span><span class="sxs-lookup"><span data-stu-id="d9145-165">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="d9145-166">Если используется политика именования групп, отображаемое имя должно соответствовать заданному в ней формату именования.</span><span class="sxs-lookup"><span data-stu-id="d9145-166">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="d9145-167">**Псевдоним**— это часть адреса электронной почты слева от знака @.</span><span class="sxs-lookup"><span data-stu-id="d9145-167">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="d9145-168">Если изменить псевдоним, основной адрес SMTP группы также изменится и будет содержать новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="d9145-168">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="d9145-169">Кроме того, адрес электронной почты с предыдущим псевдонимом сохранится в качестве прокси-адреса группы.</span><span class="sxs-lookup"><span data-stu-id="d9145-169">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="d9145-170">**Адрес**электронной почты: электронный адрес состоит из псевдонима слева от символа @и домена справа от него.</span><span class="sxs-lookup"><span data-stu-id="d9145-170">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="d9145-171">По умолчанию псевдоним **используется** в качестве значения псевдонима, но его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="d9145-171">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="d9145-172">В качестве значения домена щелкните раскрывающийся список, а затем выберите обслуживаемый домен в организации.</span><span class="sxs-lookup"><span data-stu-id="d9145-172">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="d9145-173">**Описание:** это описание отображается в адресной книге на панели подробностей в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="d9145-173">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="d9145-174">Собственность</span><span class="sxs-lookup"><span data-stu-id="d9145-174">Ownership</span></span>

<span data-ttu-id="d9145-175">Эта вкладка используется для назначения владельцев группы.</span><span class="sxs-lookup"><span data-stu-id="d9145-175">Use this tab to assign group owners.</span></span> <span data-ttu-id="d9145-176">Владелец группы может управлять членством в группе.</span><span class="sxs-lookup"><span data-stu-id="d9145-176">A group owner can manage group membership.</span></span> <span data-ttu-id="d9145-177">По умолчанию владельцем группы становится пользователь, создавший ее.</span><span class="sxs-lookup"><span data-stu-id="d9145-177">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="d9145-178">Для каждой группы должен существовать по крайней мере один владелец.</span><span class="sxs-lookup"><span data-stu-id="d9145-178">All groups must have at least one owner.</span></span>

<span data-ttu-id="d9145-179">Чтобы добавить владельцев, нажмите кнопку **Добавить** ![ значок "Добавить". ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="d9145-179">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="d9145-180">В появившемся диалоговом окне найдите и выберите получателя, а затем \*\*нажмите кнопку добавить ->. \*\*</span><span class="sxs-lookup"><span data-stu-id="d9145-180">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="d9145-181">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="d9145-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="d9145-182">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d9145-182">When you're finished, click **OK**.</span></span>

<span data-ttu-id="d9145-183">Чтобы удалить владельца, выберите владельца и нажмите кнопку **"Удалить"** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="d9145-183">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="d9145-184">Участие</span><span class="sxs-lookup"><span data-stu-id="d9145-184">Membership</span></span>

<span data-ttu-id="d9145-185">Эта вкладка используется для добавления или удаления членов группы.</span><span class="sxs-lookup"><span data-stu-id="d9145-185">Use this tab to add or remove group members.</span></span> <span data-ttu-id="d9145-186">Владельцы группы не обязательно должны быть ее членами.</span><span class="sxs-lookup"><span data-stu-id="d9145-186">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="d9145-187">Чтобы добавить участников, нажмите кнопку **"Добавить"** ![ и значок "Добавить". ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="d9145-187">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="d9145-188">В отобразившемся диалоговом окне найдите и выберите получателя или группу, а затем \*\*нажмите кнопку добавить ->. \*\*</span><span class="sxs-lookup"><span data-stu-id="d9145-188">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="d9145-189">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="d9145-189">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="d9145-190">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d9145-190">When you're finished, click **OK**.</span></span>

<span data-ttu-id="d9145-191">Чтобы удалить члена, выберите его и нажмите кнопку **"Удалить" значок** ![ "Удалить". ](../../media/ITPro-EAC-RemoveIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="d9145-191">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="d9145-192">Удаление групп с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="d9145-192">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="d9145-193">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="d9145-193">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="d9145-194">В списке групп выберите группу рассылки, которую **Remove** необходимо удалить, и нажмите значок ![ "Удалить". ](../../media/ITPro-EAC-RemoveIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="d9145-194">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="d9145-195">Управление группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9145-195">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="d9145-196">Просмотр групп с помощью автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9145-196">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="d9145-197">Чтобы получить сводный список всех групп рассылки и групп безопасности с включенной поддержкой почты в автономной службе EOP PowerShell, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d9145-197">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="d9145-198">Чтобы получить список членов группы, замените его именем, псевдонимом или электронным адресом \<GroupIdentity\> группы и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d9145-198">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="d9145-199">Дополнительные сведения о синтаксисе и параметрах см. в [разделах Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) [и Get-DistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="d9145-199">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="d9145-200">Создание групп с помощью автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9145-200">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="d9145-201">Чтобы создать группы рассылки или поддерживающие почту группы безопасности в автономной службе EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d9145-201">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="d9145-202">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="d9145-202">**Notes**:</span></span>

- <span data-ttu-id="d9145-203">Параметр _Name_ является обязательным, его длина не должна превышать 64 символа и быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="d9145-203">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="d9145-204">Если вы не используете параметр _DisplayName_, для отображаемого имени указывается значение параметра _Name_.</span><span class="sxs-lookup"><span data-stu-id="d9145-204">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="d9145-205">Если параметр _Alias_ не указан, в качестве _значения псевдонима_ будет использован параметр Name.</span><span class="sxs-lookup"><span data-stu-id="d9145-205">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="d9145-206">Пробелы удаляются, и неподдерживаемые символы преобразуются в вопросительные знаки (?).</span><span class="sxs-lookup"><span data-stu-id="d9145-206">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="d9145-207">Если параметр _PrimarySmtpAddress_ не используется, в параметре _PrimarySmtpAddress_ используется значение псевдонима.</span><span class="sxs-lookup"><span data-stu-id="d9145-207">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="d9145-208">Если вы не используете параметр _Type, значением_ по умолчанию будет "Распространение".</span><span class="sxs-lookup"><span data-stu-id="d9145-208">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="d9145-209">В этом примере создается группа рассылки "ИТ-администраторы" с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="d9145-209">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="d9145-210">Дополнительные сведения о синтаксисе и параметрах см. в [разделе New-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)</span><span class="sxs-lookup"><span data-stu-id="d9145-210">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="d9145-211">Изменение групп с помощью автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9145-211">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="d9145-212">Для изменения групп в автономной службе EOP PowerShell используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d9145-212">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="d9145-213">В этом примере показано, как изменить основной адрес SMTP (также называемый адресответа) для группы "Сотрудники Москвы" на sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d9145-213">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="d9145-214">В этом примере показано, как заменить текущих членов группы "Группа безопасности" на Kitty Petersen и Tyson Facet.</span><span class="sxs-lookup"><span data-stu-id="d9145-214">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="d9145-215">В этом примере показано добавление нового пользователя с именем Tyson Facet в группу безопасности с сохранением текущих членов.</span><span class="sxs-lookup"><span data-stu-id="d9145-215">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="d9145-216">Дополнительные сведения о синтаксисе и параметрах см. в [разделах Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) и [Update-EOPDistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)</span><span class="sxs-lookup"><span data-stu-id="d9145-216">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="d9145-217">Удаление группы с помощью удаленной консоли Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9145-217">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="d9145-218">В этом примере используется группа рассылки "ИТ-администраторы".</span><span class="sxs-lookup"><span data-stu-id="d9145-218">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="d9145-219">Дополнительные сведения о синтаксисе и параметрах см. в [статье Remove-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)</span><span class="sxs-lookup"><span data-stu-id="d9145-219">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d9145-220">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="d9145-220">How do you know these procedures worked?</span></span>

<span data-ttu-id="d9145-221">Чтобы убедиться в успешном создании, изменении или удалении группы рассылки или группы безопасности с поддержкой электронной почты, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="d9145-221">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="d9145-222">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="d9145-222">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="d9145-223">Убедитесь, что группа присутствует (или нет в списке) и проверьте **значение этого типа.**</span><span class="sxs-lookup"><span data-stu-id="d9145-223">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="d9145-224">Выберите группу и просмотрите сведения в области "Сведения" или **нажмите** значок ![ редактирования, ](../../media/ITPro-EAC-AddIcon.png) чтобы просмотреть параметры.</span><span class="sxs-lookup"><span data-stu-id="d9145-224">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="d9145-225">В автономной службе EOP PowerShell выполните следующую команду, чтобы убедиться, что группа присутствует в списке (или нет в списке):</span><span class="sxs-lookup"><span data-stu-id="d9145-225">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="d9145-226">Замените \<GroupIdentity\> на имя, псевдоним или адрес электронной почты группы и выполните следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="d9145-226">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="d9145-227">Чтобы просмотреть участников группы, замените его именем, псевдонимом или \<GroupIdentity\> электронным адресом группы и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d9145-227">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
