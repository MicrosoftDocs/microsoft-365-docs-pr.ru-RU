---
title: Управление пользователями почты в автономном EOP
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
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Узнайте, как управлять почтовыми пользователями в Exchange Online Protection (EOP), в том числе с помощью синхронизации каталогов, центра администрирования Exchange и PowerShell для управления пользователями.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d82170499bcfa6465164ca2644eea43c2558ad18
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616838"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="1eb53-103">Управление пользователями почты в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="1eb53-103">Manage mail users in standalone EOP</span></span>

<span data-ttu-id="1eb53-104">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователям почты является основной тип учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="1eb53-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="1eb53-105">Почтовые пользователи имеют учетные данные в автономной организации EOP и могут получать доступ к ресурсам (назначены разрешения).</span><span class="sxs-lookup"><span data-stu-id="1eb53-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="1eb53-106">Адрес электронной почты пользователя является внешним (например, в локальной почтовой среде).</span><span class="sxs-lookup"><span data-stu-id="1eb53-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="1eb53-107">Когда вы создаете почтового пользователя, соответствующая учетная запись пользователя доступна в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1eb53-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1eb53-108">При создании учетной записи пользователя в центре администрирования Microsoft 365 эту учетную запись невозможно использовать для создания почтового пользователя.</span><span class="sxs-lookup"><span data-stu-id="1eb53-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="1eb53-109">Для создания и управления почтовыми пользователями в автономной EOP рекомендуется использовать синхронизацию службы каталогов, как описано в разделе Использование синхронизации каталогов [для управления почтовыми пользователями](#use-directory-synchronization-to-manage-mail-users) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1eb53-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="1eb53-110">Для автономных организаций EOP с небольшим количеством пользователей можно добавлять почтовых пользователей и управлять ими в центре администрирования Exchange или в автономной EOP PowerShell, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1eb53-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1eb53-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="1eb53-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1eb53-112">Чтобы открыть центр администрирования Exchange, обратитесь к [центру администрирования Exchange в автономной EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="1eb53-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="1eb53-113">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1eb53-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1eb53-114">При создании почтовых пользователей в EOP PowerShell может возникнуть возможность регулирования.</span><span class="sxs-lookup"><span data-stu-id="1eb53-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="1eb53-115">Кроме того, командлеты PowerShell EOP используют метод пакетной обработки, который приводит к задержке распространения в течение нескольких минут до того, как результаты команд будут видны.</span><span class="sxs-lookup"><span data-stu-id="1eb53-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="1eb53-116">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="1eb53-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1eb53-117">В частности, необходимы роли создания получателей почты и получателей почты (изменения), которые назначаются группам ролей Организатионманажемент (глобальные администраторы) и РеЦипиентманажемент по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1eb53-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="1eb53-118">Дополнительные сведения см. [в разделе разрешения в автономных EOP](feature-permissions-in-eop.md) и используйте центр администрирования Exchange для [изменения списка участников в группах ролей](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="1eb53-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="1eb53-119">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="1eb53-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="1eb53-120">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="1eb53-120">Having problems?</span></span> <span data-ttu-id="1eb53-121">Обратитесь за помощью к участникам форумов Exchange.</span><span class="sxs-lookup"><span data-stu-id="1eb53-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="1eb53-122">Посетите форум [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="1eb53-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="1eb53-123">Управление почтовыми пользователями с помощью центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="1eb53-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="1eb53-124">Использование центра администрирования Exchange для создания почтовых пользователей</span><span class="sxs-lookup"><span data-stu-id="1eb53-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="1eb53-125">В центре администрирования Exchange выберите **Recipients** \> **Контакты** получателей</span><span class="sxs-lookup"><span data-stu-id="1eb53-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="1eb53-126">Нажмите кнопку **создать** ![ новый значок ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="1eb53-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1eb53-127">На открывшейся странице **Создание почтового пользователя** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="1eb53-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="1eb53-128">Параметры, отмеченные атрибутом, <sup>\*</sup> являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="1eb53-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="1eb53-129">**Имя**</span><span class="sxs-lookup"><span data-stu-id="1eb53-129">**First name**</span></span>

   - <span data-ttu-id="1eb53-130">**Инициалы**: инициал отчества пользователя.</span><span class="sxs-lookup"><span data-stu-id="1eb53-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="1eb53-131">**Фамилия**</span><span class="sxs-lookup"><span data-stu-id="1eb53-131">**Last name**</span></span>

   - <span data-ttu-id="1eb53-132"><sup>\*</sup>**Отображаемое имя**: по умолчанию в этом поле отображаются значения из полей **имя**, **инициалы**и **Фамилия** .</span><span class="sxs-lookup"><span data-stu-id="1eb53-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="1eb53-133">Вы можете принять это значение или изменить его.</span><span class="sxs-lookup"><span data-stu-id="1eb53-133">You can accept this value or change it.</span></span> <span data-ttu-id="1eb53-134">Значение должно быть уникальным и не может быть длиннее 64 символов.</span><span class="sxs-lookup"><span data-stu-id="1eb53-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="1eb53-135"><sup>\*</sup>**Alias**: введите уникальный псевдоним для пользователя с длиной до 64 символов.</span><span class="sxs-lookup"><span data-stu-id="1eb53-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="1eb53-136">**Внешний адрес электронной почты**: введите адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="1eb53-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="1eb53-137">Домен должен быть внешним по отношению к облачной организации.</span><span class="sxs-lookup"><span data-stu-id="1eb53-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="1eb53-138"><sup>\*</sup>**Идентификатор пользователя**: введите учетную запись, которую пользователь будет использовать для входа в службу.</span><span class="sxs-lookup"><span data-stu-id="1eb53-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="1eb53-139">Идентификатор пользователя состоит из имени пользователя в левой части символа "@" (@) и домена в правой части.</span><span class="sxs-lookup"><span data-stu-id="1eb53-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="1eb53-140"><sup>\*</sup>**Новый пароль** и <sup>\*</sup> **Подтверждение пароля**: введите и повторно введите пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="1eb53-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="1eb53-141">Убедитесь, что пароль соответствует требованиям к длине, сложности и истории паролей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1eb53-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="1eb53-142">Когда вы закончили, нажмите кнопку **Сохранить**, чтобы создать пользователя почты.</span><span class="sxs-lookup"><span data-stu-id="1eb53-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="1eb53-143">Использование центра администрирования Exchange для изменения почтовых пользователей</span><span class="sxs-lookup"><span data-stu-id="1eb53-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="1eb53-144">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="1eb53-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="1eb53-145">Выберите пользователя почты, которого нужно изменить, а затем щелкните **изменить** ![ значок редактирования ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="1eb53-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="1eb53-146">На открывшейся странице "Свойства пользователя почты" щелкните одну из следующих вкладок, чтобы просмотреть или изменить свойства.</span><span class="sxs-lookup"><span data-stu-id="1eb53-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="1eb53-147">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1eb53-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="1eb53-148">Общие</span><span class="sxs-lookup"><span data-stu-id="1eb53-148">General</span></span>

<span data-ttu-id="1eb53-149">Используйте вкладку **Общие** , чтобы просмотреть или изменить основные сведения о почтовом пользователе.</span><span class="sxs-lookup"><span data-stu-id="1eb53-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="1eb53-150">**Имя**</span><span class="sxs-lookup"><span data-stu-id="1eb53-150">**First name**</span></span>

- <span data-ttu-id="1eb53-151">**Инициалы**</span><span class="sxs-lookup"><span data-stu-id="1eb53-151">**Initials**</span></span>

- <span data-ttu-id="1eb53-152">**Фамилия**</span><span class="sxs-lookup"><span data-stu-id="1eb53-152">**Last name**</span></span>

- <span data-ttu-id="1eb53-153">**Отображаемое имя**: это имя отображается в адресной книге организации, в строках "Кому:" и "от" в сообщении электронной почты, а также в списке контактов в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="1eb53-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="1eb53-154">Это имя не может содержать пробелы до или после отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="1eb53-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="1eb53-155">**Идентификатор пользователя**: учетная запись пользователя в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1eb53-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="1eb53-156">Здесь невозможно изменить это значение.</span><span class="sxs-lookup"><span data-stu-id="1eb53-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="1eb53-157">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="1eb53-157">Contact information</span></span>

<span data-ttu-id="1eb53-158">Используйте вкладку **контактные сведения** , чтобы просмотреть или изменить контактные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="1eb53-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="1eb53-159">Информация на этой странице отображается в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="1eb53-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="1eb53-160">**Street**</span><span class="sxs-lookup"><span data-stu-id="1eb53-160">**Street**</span></span>
- <span data-ttu-id="1eb53-161">**City**</span><span class="sxs-lookup"><span data-stu-id="1eb53-161">**City**</span></span>
- <span data-ttu-id="1eb53-162">**Область, республика, край, округ**</span><span class="sxs-lookup"><span data-stu-id="1eb53-162">**State/Province**</span></span>
- <span data-ttu-id="1eb53-163">**Почтовый индекс**</span><span class="sxs-lookup"><span data-stu-id="1eb53-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="1eb53-164">**Страна или регион**</span><span class="sxs-lookup"><span data-stu-id="1eb53-164">**Country/Region**</span></span>
- <span data-ttu-id="1eb53-165">**Рабочий телефон**</span><span class="sxs-lookup"><span data-stu-id="1eb53-165">**Work phone**</span></span>
- <span data-ttu-id="1eb53-166">**Мобильный телефон**</span><span class="sxs-lookup"><span data-stu-id="1eb53-166">**Mobile phone**</span></span>
- <span data-ttu-id="1eb53-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="1eb53-167">**Fax**</span></span>
- <span data-ttu-id="1eb53-168">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="1eb53-168">**More options**</span></span>

  - <span data-ttu-id="1eb53-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="1eb53-169">**Office**</span></span>
  - <span data-ttu-id="1eb53-170">**Домашний телефон**</span><span class="sxs-lookup"><span data-stu-id="1eb53-170">**Home phone**</span></span>
  - <span data-ttu-id="1eb53-171">**Веб-страница**.</span><span class="sxs-lookup"><span data-stu-id="1eb53-171">**Web page**</span></span>
  - <span data-ttu-id="1eb53-172">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="1eb53-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="1eb53-173">Организация</span><span class="sxs-lookup"><span data-stu-id="1eb53-173">Organization</span></span>

<span data-ttu-id="1eb53-174">Используйте вкладку **Организация** для записи подробных сведений о роли пользователя в Организации.</span><span class="sxs-lookup"><span data-stu-id="1eb53-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="1eb53-175">**Title**</span><span class="sxs-lookup"><span data-stu-id="1eb53-175">**Title**</span></span>
- <span data-ttu-id="1eb53-176">**Department**</span><span class="sxs-lookup"><span data-stu-id="1eb53-176">**Department**</span></span>
- <span data-ttu-id="1eb53-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="1eb53-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="1eb53-178">Использование центра администрирования Exchange для удаления почтовых пользователей</span><span class="sxs-lookup"><span data-stu-id="1eb53-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="1eb53-179">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="1eb53-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="1eb53-180">Выберите пользователя почты, которого нужно удалить, а затем нажмите кнопку **Удалить** ![ значок удаления ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="1eb53-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="1eb53-181">Управление почтовыми пользователями с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1eb53-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="1eb53-182">Просмотр почтовых пользователей с помощью изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="1eb53-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="1eb53-183">Чтобы получить сводный список всех пользователей почты в изолированной EOP PowerShell, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1eb53-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="1eb53-184">Чтобы просмотреть подробные сведения о конкретном почтовом пользователе, замените \<MailUserIdentity\> его на имя, псевдоним или имя учетной записи пользователя почты, а затем выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="1eb53-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="1eb53-185">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) и [Get – User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="1eb53-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="1eb53-186">Создание почтовых пользователей с помощью изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="1eb53-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="1eb53-187">Чтобы создавать почтовых пользователей в автономной EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1eb53-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="1eb53-188">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="1eb53-188">**Notes**:</span></span>

- <span data-ttu-id="1eb53-189">Параметр _Name_ является обязательным, его длина не должна превышать 64 символов и должна быть уникальной.</span><span class="sxs-lookup"><span data-stu-id="1eb53-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="1eb53-190">Если вы не используете параметр _DisplayName_, для отображаемого имени указывается значение параметра _Name_.</span><span class="sxs-lookup"><span data-stu-id="1eb53-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="1eb53-191">Если вы не используете параметр _Alias_ , для псевдонима используется левая сторона параметра _микрософтонлнесервицесид_ .</span><span class="sxs-lookup"><span data-stu-id="1eb53-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlneServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="1eb53-192">Если параметр _ExternalEmailAddress_ не используется, для внешнего адреса электронной почты используется значение _MicrosoftOnlineServicesID_ .</span><span class="sxs-lookup"><span data-stu-id="1eb53-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="1eb53-193">В этом примере создается пользователь почты со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="1eb53-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="1eb53-194">Имя — Жеффрэйзенг, а отображаемое имя — Джеффри Иванова.</span><span class="sxs-lookup"><span data-stu-id="1eb53-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="1eb53-195">Имя  Григорий, фамилия  Иванов.</span><span class="sxs-lookup"><span data-stu-id="1eb53-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="1eb53-196">Псевдоним  gregoryiv.</span><span class="sxs-lookup"><span data-stu-id="1eb53-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="1eb53-197">Внешний адрес электронной почты  givanov@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="1eb53-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="1eb53-198">Имя учетной записи — jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="1eb53-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="1eb53-199">Пароль  Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="1eb53-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="1eb53-200">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="1eb53-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="1eb53-201">Изменение почтовых пользователей с помощью изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="1eb53-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="1eb53-202">Чтобы изменить существующих почтовых пользователей в изолированной EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1eb53-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="1eb53-203">В этом примере настраивается внешний адрес электронной почты для пользователя Марты Артемьевой.</span><span class="sxs-lookup"><span data-stu-id="1eb53-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="1eb53-204">В этом примере значение "Компания" задано как Contoso для всех почтовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="1eb53-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="1eb53-205">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="1eb53-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="1eb53-206">Удаление почтовых пользователей с помощью изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="1eb53-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="1eb53-207">Чтобы удалить пользователей почты в изолированной EOP PowerShell, замените на \<MailUserIdentity\> имя, псевдоним или имя учетной записи пользователя почты и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1eb53-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="1eb53-208">В этом примере удаляется почтовый пользователь для Джеффри Иванова.</span><span class="sxs-lookup"><span data-stu-id="1eb53-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="1eb53-209">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="1eb53-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1eb53-210">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="1eb53-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="1eb53-211">Чтобы убедиться, что вы успешно создали, изменяли или удалили пользователей почты в автономной EOP, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1eb53-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="1eb53-212">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="1eb53-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="1eb53-213">Убедитесь, что пользователь почты указан (или не указан в списке).</span><span class="sxs-lookup"><span data-stu-id="1eb53-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="1eb53-214">Выберите пользователя почты и просмотрите сведения в области сведений или щелкните **изменить** ![ значок редактирования, ](../../media/ITPro-EAC-AddIcon.png) чтобы просмотреть параметры.</span><span class="sxs-lookup"><span data-stu-id="1eb53-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="1eb53-215">В изолированной EOP PowerShell выполните следующую команду, чтобы убедиться, что пользователь почты указан (или не указан в списке):</span><span class="sxs-lookup"><span data-stu-id="1eb53-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="1eb53-216">Замените \<MailUserIdentity\> именем, псевдонимом или именем учетной записи пользователя почты, а затем выполните следующие команды, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="1eb53-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="1eb53-217">Управление почтовыми пользователями с помощью синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="1eb53-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="1eb53-218">В автономном режиме EOP синхронизация каталогов доступна для клиентов с локальной службой Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1eb53-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="1eb53-219">Вы можете синхронизировать эти учетные записи в Azure Active Directory (Azure AD), где копии учетных записей хранятся в облаке.</span><span class="sxs-lookup"><span data-stu-id="1eb53-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="1eb53-220">При синхронизации существующих учетных записей пользователей с Azure Active Directory вы можете просмотреть этих пользователей в области **получателей** в центре администрирования Exchange или в автономной EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1eb53-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="1eb53-221">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="1eb53-221">**Notes**:</span></span>

- <span data-ttu-id="1eb53-222">Если вы используете синхронизацию службы каталогов для управления получателями, вы по-прежнему можете добавлять пользователей в центр администрирования Microsoft 365 и управлять ими, но они не будут синхронизированы с локальной службой Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1eb53-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="1eb53-223">Это объясняется тем, что получатели синхронизируются только в одном направлении: из локальной службы каталогов Active Directory в облако.</span><span class="sxs-lookup"><span data-stu-id="1eb53-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="1eb53-224">Синхронизацию службы каталогов рекомендуется использовать с такими функциями:</span><span class="sxs-lookup"><span data-stu-id="1eb53-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="1eb53-225">**Списки надежных отправителей Outlook и заблокированные списки отправителей**: при синхронизации со службой эти списки будут иметь приоритет над фильтрацией нежелательной почты в службе.</span><span class="sxs-lookup"><span data-stu-id="1eb53-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="1eb53-226">Это позволяет пользователям управлять собственным списком надежных отправителей и списком заблокированных отправителей с отдельными записями отправителя и домена.</span><span class="sxs-lookup"><span data-stu-id="1eb53-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="1eb53-227">Дополнительные сведения см. в разделе [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="1eb53-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="1eb53-228">**Пограничная блокировка на основе каталогов (DBEB)**: Дополнительные сведения о DBEB см. [в статье Использование пограничной блокировки на основе каталогов для отклонения сообщений, отправляемых недопустимым получателям](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="1eb53-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="1eb53-229">**Доступ конечного пользователя к карантину**: чтобы получить доступ к сообщениям, помещенным в карантин, получатели должны иметь действительный идентификатор пользователя и пароль в службе.</span><span class="sxs-lookup"><span data-stu-id="1eb53-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="1eb53-230">Для получения дополнительных сведений о карантине обратитесь к разделу [Поиск и освобождение сообщений, помещенных в карантин в качестве пользователя](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span><span class="sxs-lookup"><span data-stu-id="1eb53-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="1eb53-231">**Правила для поток обработки почты (также называемые правилами транспорта)**: при использовании синхронизации службы каталогов существующие пользователи и группы Active Directory автоматически отправляются в облако, а затем можно создавать правила для обработки почты, предназначенные для определенных пользователей и/или групп, без необходимости вручную добавлять их в службу.</span><span class="sxs-lookup"><span data-stu-id="1eb53-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="1eb53-232">Обратите внимание на то, что [динамические группы рассылки](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) невозможно синхронизировать через синхронизацию службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="1eb53-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="1eb53-233">Получите необходимые разрешения и подготовьтесь к синхронизации службы каталогов, как описано в разделе [что такое Гибридная идентификация с Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="1eb53-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="1eb53-234">Синхронизация каталогов с помощью Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="1eb53-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="1eb53-235">Активируйте синхронизацию службы каталогов, как описано в статье [Azure AD Connect Sync: сведения и Настройка синхронизации](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="1eb53-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="1eb53-236">Установите и настройте локальный компьютер для запуска подключения AAD, как описано в статье [необходимые условия для Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="1eb53-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="1eb53-237">[Выберите тип установки, который будет использоваться для Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span><span class="sxs-lookup"><span data-stu-id="1eb53-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="1eb53-238">Прямых</span><span class="sxs-lookup"><span data-stu-id="1eb53-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="1eb53-239">Custom</span><span class="sxs-lookup"><span data-stu-id="1eb53-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="1eb53-240">Сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="1eb53-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="1eb53-p121">Когда Мастер настройки средства синхронизации Azure Active Directory завершит работу, учетная запись **MSOL_AD_SYNC** будет создана в вашем лесу Active Directory. Она используется для чтения и синхронизации локальных данных Active Directory. Чтобы каталоги синхронизировались правильно, убедитесь, что порт TCP 443 на локальном сервере синхронизации службы каталогов открыт.</span><span class="sxs-lookup"><span data-stu-id="1eb53-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="1eb53-244">После настройки синхронизации обязательно убедитесь, что подключение AAD правильно синхронизируется.</span><span class="sxs-lookup"><span data-stu-id="1eb53-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="1eb53-245">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты** и убедитесь, что список пользователей с локальной среды должным образом синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="1eb53-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
