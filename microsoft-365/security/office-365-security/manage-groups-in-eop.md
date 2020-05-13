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
ms.custom:
- seo-marvel-apr2020
description: Администраторы в отдельных организациях Exchange Online Protection (EOP) могут узнать, как создавать, изменять и удалять группы рассылки и группы безопасности с включенной поддержкой почты в центре администрирования Exchange, а также в автономной службе Exchange Online Protection (EOP) PowerShell.
ms.openlocfilehash: fc3f3807216b269a9868e87c5ec784d75385f878
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209023"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="c8f35-103">Управление группами в EOP</span><span class="sxs-lookup"><span data-stu-id="c8f35-103">Manage groups in EOP</span></span>

<span data-ttu-id="c8f35-104">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно создавать, изменять и удалять следующие типы групп:</span><span class="sxs-lookup"><span data-stu-id="c8f35-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="c8f35-105">**Группы рассылки**: коллекция почтовых пользователей или других групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="c8f35-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="c8f35-106">Например, Teams или другие нерегламентированные группы, которым требуется получать или отправлять электронную почту в общей области.</span><span class="sxs-lookup"><span data-stu-id="c8f35-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="c8f35-107">Группы рассылки предназначены исключительно для распространения сообщений электронной почты и не являются участниками безопасности (им не могут быть назначены разрешения).</span><span class="sxs-lookup"><span data-stu-id="c8f35-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="c8f35-108">**Группы безопасности с включенной поддержкой почты**: коллекция почтовых пользователей и других групп безопасности, которым требуются разрешения на доступ для ролей администратора.</span><span class="sxs-lookup"><span data-stu-id="c8f35-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="c8f35-109">Например, может потребоваться предоставить определенной группе пользователей разрешения администратора, чтобы они могли настраивать параметры защиты от нежелательной почты и вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="c8f35-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <ul><li><span data-ttu-id="c8f35-110">По умолчанию новые группы безопасности, поддерживающие почту, отклоняются сообщения от внешних отправителей (не прошедших проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="c8f35-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span></li><li><span data-ttu-id="c8f35-111">Не добавляйте группы рассылки в группы безопасности с поддержкой электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c8f35-111">Don't add distribution groups to mail-enabled security groups.</span></span></li></ul><span data-ttu-id="c8f35-112">.</span><span class="sxs-lookup"><span data-stu-id="c8f35-112">.</span></span>

<span data-ttu-id="c8f35-113">Вы можете управлять группами в центре администрирования Exchange и в изолированной EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8f35-113">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c8f35-114">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c8f35-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c8f35-115">Чтобы открыть центр администрирования Exchange, обратитесь к [центру администрирования Exchange в автономной EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="c8f35-115">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="c8f35-116">Чтобы подключиться к изолированной EOP PowerShell, ознакомьтесь со статьей [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8f35-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c8f35-117">При управлении группами в изолированной EOP PowerShell может возникать регулирование.</span><span class="sxs-lookup"><span data-stu-id="c8f35-117">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="c8f35-118">В процедурах PowerShell, приведенных в этом разделе, используется метод пакетной обработки, который приводит к задержке распространения в течение нескольких минут до того, как результаты команд будут видны.</span><span class="sxs-lookup"><span data-stu-id="c8f35-118">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="c8f35-119">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="c8f35-119">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="c8f35-120">В частности, необходима роль групп рассылки, которая назначается группам ролей Организатионманажемент (глобальные администраторы) и РеЦипиентманажемент по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c8f35-120">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="c8f35-121">Дополнительные сведения см. [в разделе разрешения в автономных EOP](feature-permissions-in-eop.md) и используйте центр администрирования Exchange для [изменения списка участников в группах ролей](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="c8f35-121">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="c8f35-122">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c8f35-122">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="c8f35-123">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="c8f35-123">Having problems?</span></span> <span data-ttu-id="c8f35-124">Обратитесь за помощью к форуму [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-124">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="c8f35-125">Использование центра администрирования Exchange для управления группами рассылки</span><span class="sxs-lookup"><span data-stu-id="c8f35-125">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="c8f35-126">Использование центра администрирования Exchange для создания групп</span><span class="sxs-lookup"><span data-stu-id="c8f35-126">Use the EAC to create groups</span></span>

1. <span data-ttu-id="c8f35-127">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-127">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="c8f35-128">Нажмите **создать** ![ новый значок ](../../media/ITPro-EAC-AddIcon.png) , а затем выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c8f35-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="c8f35-129">**Группа рассылки.**</span><span class="sxs-lookup"><span data-stu-id="c8f35-129">**Distribution group**</span></span>

   - <span data-ttu-id="c8f35-130">**Группа безопасности с поддержкой электронной почты**</span><span class="sxs-lookup"><span data-stu-id="c8f35-130">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="c8f35-131">На открывшейся странице Новая группа настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="c8f35-131">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="c8f35-132">Параметры, отмеченные атрибутом, <sup>\*</sup> являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="c8f35-132">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="c8f35-133"><sup>\*</sup>**Отображаемое имя**: это имя отображается в адресной книге организации, в строке "Кому" при отправке сообщения в эту группу и в списке " **группы** " в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="c8f35-133"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="c8f35-134">Отображаемое имя обязательно должно быть уникальным и должно быть понятным для пользователей, чтобы пользователи могли понять, что это такое.</span><span class="sxs-lookup"><span data-stu-id="c8f35-134">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="c8f35-135"><sup>\*</sup>**Alias**: это поле используется для ввода имени псевдонима для группы.</span><span class="sxs-lookup"><span data-stu-id="c8f35-135"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="c8f35-136">Длина псевдонима не может превышать 64 символов и должна быть уникальной.</span><span class="sxs-lookup"><span data-stu-id="c8f35-136">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="c8f35-137">Когда пользователь вводит псевдоним в строке "Кому" сообщения электронной почты, он разрешается в отображаемое имя группы.</span><span class="sxs-lookup"><span data-stu-id="c8f35-137">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="c8f35-138"><sup>\*</sup>**Адрес электронной почты**: адрес электронной почты состоит из псевдонима в левой части символа @ (@) и домена в правой части.</span><span class="sxs-lookup"><span data-stu-id="c8f35-138"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="c8f35-139">По умолчанию для значения псевдонима используется значение **Alias** , но вы можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="c8f35-139">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="c8f35-140">В качестве значения домена щелкните раскрывающийся список и выберите обслуживаемый домен в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c8f35-140">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="c8f35-141">**Описание**: это описание отображается в адресной книге и в области сведений в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="c8f35-141">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="c8f35-142"><sup>\*</sup>**Владельцы**: владелец группы может управлять членством в группе.</span><span class="sxs-lookup"><span data-stu-id="c8f35-142"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="c8f35-143">По умолчанию владельцем группы становится пользователь, создавший ее.</span><span class="sxs-lookup"><span data-stu-id="c8f35-143">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="c8f35-144">Для каждой группы должен существовать по крайней мере один владелец.</span><span class="sxs-lookup"><span data-stu-id="c8f35-144">All groups must have at least one owner.</span></span>

     <span data-ttu-id="c8f35-145">Чтобы добавить владельцев, нажмите **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-145">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c8f35-146">В появившемся диалоговом окне найдите и выберите получателя или группу, а затем щелкните **добавить >**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-146">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="c8f35-147">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="c8f35-147">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c8f35-148">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-148">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="c8f35-149">Чтобы удалить владельца, выберите его, а затем нажмите кнопку **Удалить** ![ значок удаления ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-149">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="c8f35-150">**Члены**: Добавление и удаление членов группы.</span><span class="sxs-lookup"><span data-stu-id="c8f35-150">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="c8f35-151">Чтобы добавить участников, нажмите кнопку **Добавить** ![ значок ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-151">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c8f35-152">В появившемся диалоговом окне найдите и выберите получателя или группу, а затем щелкните **добавить >**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-152">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="c8f35-153">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="c8f35-153">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c8f35-154">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-154">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="c8f35-155">Чтобы удалить члена, выберите его, а затем нажмите кнопку **Удалить** ![ значок удаления ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-155">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="c8f35-156">Когда все будет готово, нажмите кнопку **сохранить** , чтобы создать группу рассылки.</span><span class="sxs-lookup"><span data-stu-id="c8f35-156">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="c8f35-157">Использование центра администрирования Exchange для изменения групп рассылки</span><span class="sxs-lookup"><span data-stu-id="c8f35-157">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="c8f35-158">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-158">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="c8f35-159">В списке групп выберите группу рассылки или группу безопасности с включенной поддержкой почты, которую нужно изменить, и нажмите кнопку **изменить** ![ значок редактирования ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-159">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="c8f35-160">На открывшейся странице свойств группы рассылки щелкните одну из указанных ниже вкладок, чтобы просмотреть или изменить свойства.</span><span class="sxs-lookup"><span data-stu-id="c8f35-160">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="c8f35-161">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-161">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="c8f35-162">Общие</span><span class="sxs-lookup"><span data-stu-id="c8f35-162">General</span></span>

<span data-ttu-id="c8f35-163">Эта вкладка позволяет просмотреть или изменить основные сведения о группе.</span><span class="sxs-lookup"><span data-stu-id="c8f35-163">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="c8f35-164">**Отображаемое имя**: это имя отображается в адресной книге в строке "Кому" при отправке сообщения по электронной почте этой группе и в **списке "группы**".</span><span class="sxs-lookup"><span data-stu-id="c8f35-164">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="c8f35-165">Отображаемое имя обязательно и должно быть понятным, чтобы пользователи могли понять его назначение.</span><span class="sxs-lookup"><span data-stu-id="c8f35-165">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="c8f35-166">Кроме того, оно должно быть уникальным в пределах домена.</span><span class="sxs-lookup"><span data-stu-id="c8f35-166">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="c8f35-167">Если используется политика именования групп, отображаемое имя должно соответствовать заданному в ней формату именования.</span><span class="sxs-lookup"><span data-stu-id="c8f35-167">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="c8f35-168">**Псевдоним**: это часть адреса электронной почты, которая отображается слева от символа "@".</span><span class="sxs-lookup"><span data-stu-id="c8f35-168">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="c8f35-169">Если изменить псевдоним, основной адрес SMTP группы также изменится и будет содержать новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="c8f35-169">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="c8f35-170">Кроме того, адрес электронной почты с предыдущим псевдонимом сохранится в качестве прокси-адреса группы.</span><span class="sxs-lookup"><span data-stu-id="c8f35-170">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="c8f35-171">**Адрес электронной почты**: адрес электронной почты состоит из псевдонима в левой части символа @ (@) и домена в правой части.</span><span class="sxs-lookup"><span data-stu-id="c8f35-171">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="c8f35-172">По умолчанию для значения псевдонима используется значение **Alias** , но вы можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="c8f35-172">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="c8f35-173">В качестве значения домена щелкните раскрывающийся список и выберите обслуживаемый домен в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c8f35-173">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="c8f35-174">**Описание**: это описание отображается в адресной книге и в области сведений в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="c8f35-174">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="c8f35-175">Собственность</span><span class="sxs-lookup"><span data-stu-id="c8f35-175">Ownership</span></span>

<span data-ttu-id="c8f35-176">Эта вкладка используется для назначения владельцев групп.</span><span class="sxs-lookup"><span data-stu-id="c8f35-176">Use this tab to assign group owners.</span></span> <span data-ttu-id="c8f35-177">Владелец группы может управлять членством в группе.</span><span class="sxs-lookup"><span data-stu-id="c8f35-177">A group owner can manage group membership.</span></span> <span data-ttu-id="c8f35-178">По умолчанию владельцем группы становится пользователь, создавший ее.</span><span class="sxs-lookup"><span data-stu-id="c8f35-178">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="c8f35-179">Для каждой группы должен существовать по крайней мере один владелец.</span><span class="sxs-lookup"><span data-stu-id="c8f35-179">All groups must have at least one owner.</span></span>

<span data-ttu-id="c8f35-180">Чтобы добавить владельцев, нажмите **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-180">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c8f35-181">В появившемся диалоговом окне найдите и выберите получателя, а затем щелкните **добавить >**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-181">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="c8f35-182">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="c8f35-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c8f35-183">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-183">When you're finished, click **OK**.</span></span>

<span data-ttu-id="c8f35-184">Чтобы удалить владельца, выберите его, а затем нажмите кнопку **Удалить** ![ значок удаления ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-184">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="c8f35-185">Участие</span><span class="sxs-lookup"><span data-stu-id="c8f35-185">Membership</span></span>

<span data-ttu-id="c8f35-186">Эта вкладка используется для добавления или удаления членов группы.</span><span class="sxs-lookup"><span data-stu-id="c8f35-186">Use this tab to add or remove group members.</span></span> <span data-ttu-id="c8f35-187">Владельцы групп не должны быть членами группы.</span><span class="sxs-lookup"><span data-stu-id="c8f35-187">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="c8f35-188">Чтобы добавить участников, нажмите кнопку **Добавить** ![ значок ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-188">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c8f35-189">В появившемся диалоговом окне найдите и выберите получателя или группу, а затем щелкните **добавить >**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-189">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="c8f35-190">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="c8f35-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c8f35-191">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-191">When you're finished, click **OK**.</span></span>

<span data-ttu-id="c8f35-192">Чтобы удалить члена, выберите его, а затем нажмите кнопку **Удалить** ![ значок удаления ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-192">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="c8f35-193">Использование центра администрирования Exchange для удаления групп</span><span class="sxs-lookup"><span data-stu-id="c8f35-193">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="c8f35-194">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-194">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="c8f35-195">В списке групп выберите группу рассылки, которую нужно удалить, и нажмите кнопку **Удалить** ![ значок удаления ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="c8f35-195">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="c8f35-196">Управление группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8f35-196">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="c8f35-197">Просмотр групп с помощью изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8f35-197">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="c8f35-198">Чтобы получить сводный список всех групп рассылки и групп безопасности с включенной поддержкой почты в изолированной EOP PowerShell, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c8f35-198">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="c8f35-199">Чтобы получить список членов группы, замените \< граупидентити \> на имя, псевдоним или адрес электронной почты группы, а затем выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c8f35-199">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="c8f35-200">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) и [Get/DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="c8f35-200">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="c8f35-201">Создание групп с помощью изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8f35-201">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="c8f35-202">Чтобы создать группы рассылки или группы безопасности с включенной поддержкой почты в изолированной EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c8f35-202">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="c8f35-203">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="c8f35-203">**Notes**:</span></span>

- <span data-ttu-id="c8f35-204">Параметр _Name_ является обязательным, его длина не должна превышать 64 символов и должна быть уникальной.</span><span class="sxs-lookup"><span data-stu-id="c8f35-204">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="c8f35-205">Если вы не используете параметр _DisplayName_, для отображаемого имени указывается значение параметра _Name_.</span><span class="sxs-lookup"><span data-stu-id="c8f35-205">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="c8f35-206">Если параметр _Alias_ не используется, для значения Alias используется параметр _Name_ .</span><span class="sxs-lookup"><span data-stu-id="c8f35-206">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="c8f35-207">Пробелы удаляются, а неподдерживаемые символы преобразуются в вопросительные знаки (?).</span><span class="sxs-lookup"><span data-stu-id="c8f35-207">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="c8f35-208">Если параметр _PrimarySmtpAddress_ не используется, используется значение псевдонима в параметре _PrimarySmtpAddress_ .</span><span class="sxs-lookup"><span data-stu-id="c8f35-208">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="c8f35-209">Если параметр _Type_ не используется, по умолчанию используется значение Distribution.</span><span class="sxs-lookup"><span data-stu-id="c8f35-209">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="c8f35-210">В этом примере создается группа рассылки с именем IT Administrators с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="c8f35-210">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="c8f35-211">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – eopdistributiongroup используется](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="c8f35-211">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="c8f35-212">Изменение групп с помощью изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8f35-212">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="c8f35-213">Чтобы изменить группы в изолированной EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c8f35-213">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="c8f35-214">В этом примере используются изменения основного SMTP-адреса (также называемого адресом ответа) для группы Employees в Сиэтле до sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c8f35-214">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="c8f35-215">В этом примере показано, как заменить текущих участников группы безопасности на Регины Petersen и Тисон Покровской.</span><span class="sxs-lookup"><span data-stu-id="c8f35-215">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="c8f35-216">В этом примере добавляется новый пользователь с именем Тисон Покровской в группу группа безопасности с сохранением текущих участников группы.</span><span class="sxs-lookup"><span data-stu-id="c8f35-216">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="c8f35-217">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set/eopdistributiongroup используется](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) и [Update – еопдистрибутионграупмембер](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="c8f35-217">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="c8f35-218">Удаление группы с помощью удаленной оболочки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8f35-218">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="c8f35-219">В этом примере показано, как удалить группу рассылки с именем IT Administrators.</span><span class="sxs-lookup"><span data-stu-id="c8f35-219">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="c8f35-220">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – eopdistributiongroup используется](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="c8f35-220">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c8f35-221">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="c8f35-221">How do you know these procedures worked?</span></span>

<span data-ttu-id="c8f35-222">Чтобы убедиться, что вы успешно создали, изменили или удалили группу рассылки или группу безопасности с включенной поддержкой почты, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="c8f35-222">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="c8f35-223">В Центре администрирования Exchange выберите **Получатели** \> **Группы**.</span><span class="sxs-lookup"><span data-stu-id="c8f35-223">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="c8f35-224">Убедитесь, что Группа присутствует в списке (или не указана), и проверьте значение **типа группы** .</span><span class="sxs-lookup"><span data-stu-id="c8f35-224">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="c8f35-225">Выберите группу и просмотрите сведения в области сведений или нажмите **изменить** ![ значок редактирования, ](../../media/ITPro-EAC-AddIcon.png) чтобы просмотреть параметры.</span><span class="sxs-lookup"><span data-stu-id="c8f35-225">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="c8f35-226">В изолированной EOP PowerShell выполните следующую команду, чтобы убедиться, что Группа присутствует в списке (или не указана):</span><span class="sxs-lookup"><span data-stu-id="c8f35-226">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="c8f35-227">Замените \< граупидентити \> именем, псевдонимом или адресом электронной почты группы и выполните следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="c8f35-227">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="c8f35-228">Чтобы просмотреть членов группы, замените \< граупидентити \> на имя, псевдоним или адрес электронной почты группы и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c8f35-228">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
