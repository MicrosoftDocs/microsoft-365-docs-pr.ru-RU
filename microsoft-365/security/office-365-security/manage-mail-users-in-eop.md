---
title: Управление пользователями почты в автономной службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Узнайте, как управлять почтовыми пользователями в Exchange Online Protection (EOP), включая использование синхронизации каталогов, EAC и PowerShell для управления пользователями.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 34edafea7567da04094ea386d469d3d27937eee5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166397"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="0664d-103">Управление пользователями почты в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="0664d-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0664d-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="0664d-104">**Applies to**</span></span>
-  [<span data-ttu-id="0664d-105">Автономный режим Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0664d-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="0664d-106">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online почтовые пользователи являются основным типом учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="0664d-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="0664d-107">Пользователь почты имеет учетные данные учетной записи в вашей автономных организациях EOP и может получать доступ к ресурсам (им назначены разрешения).</span><span class="sxs-lookup"><span data-stu-id="0664d-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="0664d-108">Адрес электронной почты пользователя почты является внешним (например, в локальной среде электронной почты).</span><span class="sxs-lookup"><span data-stu-id="0664d-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="0664d-109">При создании почтового пользователя соответствующая учетная запись пользователя доступна в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0664d-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0664d-110">При создании учетной записи пользователя в Центре администрирования Microsoft 365 ее нельзя использовать для создания почтового пользователя.</span><span class="sxs-lookup"><span data-stu-id="0664d-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="0664d-111">Для создания пользователей почты и управления ими в автономных EOP рекомендуется использовать синхронизацию каталогов, как описано в разделе "Использование синхронизации каталогов для управления почтовыми пользователями" далее в этой статье. [](#use-directory-synchronization-to-manage-mail-users)</span><span class="sxs-lookup"><span data-stu-id="0664d-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="0664d-112">Для автономных организаций EOP с небольшим количеством пользователей можно добавлять почтовых пользователей и управлять ими в Центре администрирования Exchange (EAC) или в режиме автономных EOP PowerShell, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0664d-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0664d-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="0664d-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0664d-114">Чтобы открыть Центр администрирования Exchange (EAC), см. центр [администрирования Exchange в режиме автономных EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="0664d-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="0664d-115">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="0664d-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0664d-116">При создании почтовых пользователей в EOP PowerShell может возникнуть регулирование.</span><span class="sxs-lookup"><span data-stu-id="0664d-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="0664d-117">Кроме того, командлеты EOP PowerShell используют метод пакетной обработки, который приводит к задержке распространения за несколько минут до того, как будут видны результаты команд.</span><span class="sxs-lookup"><span data-stu-id="0664d-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="0664d-118">Для работы с процедурами, которые данная статья, вам должны быть назначены разрешения в Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="0664d-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="0664d-119">В частности, необходимы роли **создания** (создания) и **получателей** почты (изменения), которые по умолчанию назначены  группам ролей "Управление организацией" **(глобальные** администраторы) и "Управление получателями".</span><span class="sxs-lookup"><span data-stu-id="0664d-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="0664d-120">Дополнительные сведения см. в сведениях о разрешениях в автономных [EOP](feature-permissions-in-eop.md) и использовании EAC для изменения списка участников [в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="0664d-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="0664d-121">Сведения о сочетаниях клавиш, которые могут применяться к процедурам в этой статье, см. в статье "Сочетания клавиш" в Центре администрирования [Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="0664d-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="0664d-122">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="0664d-122">Having problems?</span></span> <span data-ttu-id="0664d-123">Обратитесь за помощью к участникам форумов Exchange.</span><span class="sxs-lookup"><span data-stu-id="0664d-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="0664d-124">Посетите форум [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="0664d-124">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="0664d-125">Управление почтовыми пользователями с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="0664d-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="0664d-126">Создание почтовых пользователей с помощью EAC</span><span class="sxs-lookup"><span data-stu-id="0664d-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="0664d-127">В EAC перейдите к **контакту** \> **получателей**</span><span class="sxs-lookup"><span data-stu-id="0664d-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="0664d-128">Щелкните **значок "Новый** ![ новый" ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="0664d-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="0664d-129">На **открываемой странице "Создать** пользователя почты" настройте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="0664d-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="0664d-130">Параметры, помеченные <sup>\*</sup> как необходимые.</span><span class="sxs-lookup"><span data-stu-id="0664d-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="0664d-131">**Имя**</span><span class="sxs-lookup"><span data-stu-id="0664d-131">**First name**</span></span>

   - <span data-ttu-id="0664d-132">**Инициалы:** инициалы человека в середине.</span><span class="sxs-lookup"><span data-stu-id="0664d-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="0664d-133">**Фамилия**</span><span class="sxs-lookup"><span data-stu-id="0664d-133">**Last name**</span></span>

   - <span data-ttu-id="0664d-134"><sup>\*</sup>**Отображаемая** имя: по умолчанию в этом поле отображаются значения из полей **"Имя",**"Инициалы" и "Фамилия".  </span><span class="sxs-lookup"><span data-stu-id="0664d-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="0664d-135">Вы можете принять это значение или изменить его.</span><span class="sxs-lookup"><span data-stu-id="0664d-135">You can accept this value or change it.</span></span> <span data-ttu-id="0664d-136">Значение должно быть уникальным и иметь максимальную длину 64 символа.</span><span class="sxs-lookup"><span data-stu-id="0664d-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="0664d-137"><sup>\*</sup>**Псевдоним:** введите уникальный псевдоним (не более 64 символов) для пользователя</span><span class="sxs-lookup"><span data-stu-id="0664d-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="0664d-138">**Внешний адрес электронной** почты: введите адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="0664d-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="0664d-139">Домен должен быть внешним по внешнему расположению для облачной организации.</span><span class="sxs-lookup"><span data-stu-id="0664d-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="0664d-140"><sup>\*</sup>**ИД пользователя:** введите учетную запись, которую пользователь будет использовать для входа в службу.</span><span class="sxs-lookup"><span data-stu-id="0664d-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="0664d-141">ИД пользователя состоит из имени пользователя в левой части символа @(@) и домена справа.</span><span class="sxs-lookup"><span data-stu-id="0664d-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="0664d-142"><sup>\*</sup>**Новый пароль и** <sup>\*</sup> **подтверждение пароля:** введите и повторно введите пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="0664d-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="0664d-143">Убедитесь, что пароль соответствует требованиям организации к длине, сложности и истории пароля.</span><span class="sxs-lookup"><span data-stu-id="0664d-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="0664d-144">Когда вы закончили, нажмите кнопку **Сохранить**, чтобы создать пользователя почты.</span><span class="sxs-lookup"><span data-stu-id="0664d-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="0664d-145">Использование EAC для изменения почтовых пользователей</span><span class="sxs-lookup"><span data-stu-id="0664d-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="0664d-146">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="0664d-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="0664d-147">Выберите пользователя почты, который нужно изменить, и нажмите значок  ![ ](../../media/ITPro-EAC-AddIcon.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="0664d-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="0664d-148">На открываемой странице свойств пользователя почты щелкните одну из следующих вкладок, чтобы просмотреть или изменить свойства.</span><span class="sxs-lookup"><span data-stu-id="0664d-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="0664d-149">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0664d-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="0664d-150">Общие</span><span class="sxs-lookup"><span data-stu-id="0664d-150">General</span></span>

<span data-ttu-id="0664d-151">Вкладка **"Общие"** используется для просмотра или изменения основных сведений о пользователе почты.</span><span class="sxs-lookup"><span data-stu-id="0664d-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="0664d-152">**Имя**</span><span class="sxs-lookup"><span data-stu-id="0664d-152">**First name**</span></span>

- <span data-ttu-id="0664d-153">**Инициалы**</span><span class="sxs-lookup"><span data-stu-id="0664d-153">**Initials**</span></span>

- <span data-ttu-id="0664d-154">**Фамилия**</span><span class="sxs-lookup"><span data-stu-id="0664d-154">**Last name**</span></span>

- <span data-ttu-id="0664d-155">**Отображаемого** имени : это имя отображается в адресной книге организации, в строках "To: and From" в электронной почте и в списке контактов в EAC.</span><span class="sxs-lookup"><span data-stu-id="0664d-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="0664d-156">Это имя не может содержать пробелы до или после отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="0664d-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="0664d-157">**ИД пользователя:** это учетная запись пользователя в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0664d-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="0664d-158">Здесь нельзя изменить это значение.</span><span class="sxs-lookup"><span data-stu-id="0664d-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="0664d-159">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="0664d-159">Contact information</span></span>

<span data-ttu-id="0664d-160">Используйте **вкладку "Контактные** данные" для просмотра или изменения контактных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="0664d-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="0664d-161">Информация на этой странице отображается в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="0664d-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="0664d-162">**Street**</span><span class="sxs-lookup"><span data-stu-id="0664d-162">**Street**</span></span>
- <span data-ttu-id="0664d-163">**City**</span><span class="sxs-lookup"><span data-stu-id="0664d-163">**City**</span></span>
- <span data-ttu-id="0664d-164">**Область, республика, край, округ**</span><span class="sxs-lookup"><span data-stu-id="0664d-164">**State/Province**</span></span>
- <span data-ttu-id="0664d-165">**Почтовый индекс**</span><span class="sxs-lookup"><span data-stu-id="0664d-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="0664d-166">**Страна или регион**</span><span class="sxs-lookup"><span data-stu-id="0664d-166">**Country/Region**</span></span>
- <span data-ttu-id="0664d-167">**Рабочий телефон**</span><span class="sxs-lookup"><span data-stu-id="0664d-167">**Work phone**</span></span>
- <span data-ttu-id="0664d-168">**Мобильный телефон**</span><span class="sxs-lookup"><span data-stu-id="0664d-168">**Mobile phone**</span></span>
- <span data-ttu-id="0664d-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="0664d-169">**Fax**</span></span>
- <span data-ttu-id="0664d-170">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="0664d-170">**More options**</span></span>

  - <span data-ttu-id="0664d-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="0664d-171">**Office**</span></span>
  - <span data-ttu-id="0664d-172">**Домашний телефон**</span><span class="sxs-lookup"><span data-stu-id="0664d-172">**Home phone**</span></span>
  - <span data-ttu-id="0664d-173">**Веб-страница**.</span><span class="sxs-lookup"><span data-stu-id="0664d-173">**Web page**</span></span>
  - <span data-ttu-id="0664d-174">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="0664d-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="0664d-175">Организация</span><span class="sxs-lookup"><span data-stu-id="0664d-175">Organization</span></span>

<span data-ttu-id="0664d-176">Вкладка **"Организация"** используется для записи подробных сведений о роли пользователя в организации.</span><span class="sxs-lookup"><span data-stu-id="0664d-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="0664d-177">**Title**</span><span class="sxs-lookup"><span data-stu-id="0664d-177">**Title**</span></span>
- <span data-ttu-id="0664d-178">**Department**</span><span class="sxs-lookup"><span data-stu-id="0664d-178">**Department**</span></span>
- <span data-ttu-id="0664d-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="0664d-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="0664d-180">Использование EAC для удаления почтовых пользователей</span><span class="sxs-lookup"><span data-stu-id="0664d-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="0664d-181">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="0664d-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="0664d-182">Выберите пользователя почты, который нужно удалить, и нажмите значок **"Удалить** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) удалить".</span><span class="sxs-lookup"><span data-stu-id="0664d-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="0664d-183">Использование PowerShell для управления почтовыми пользователями</span><span class="sxs-lookup"><span data-stu-id="0664d-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="0664d-184">Просмотр пользователей почты с помощью автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="0664d-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="0664d-185">Чтобы получить сводный список всех почтовых пользователей в автономных EOP PowerShell, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0664d-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="0664d-186">Чтобы просмотреть подробные сведения об определенном почтовом пользователе, замените имя, псевдоним или имя учетной записи пользователя почты и запустите следующие \<MailUserIdentity\> команды:</span><span class="sxs-lookup"><span data-stu-id="0664d-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="0664d-187">Подробные сведения о синтаксисах и параметрах см. в описании [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) и [Get-User.](https://docs.microsoft.com/powershell/module/exchange/get-user)</span><span class="sxs-lookup"><span data-stu-id="0664d-187">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="0664d-188">Создание пользователей почты с помощью автономных EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="0664d-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="0664d-189">Чтобы создать почтовых пользователей в автономных EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0664d-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="0664d-190">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="0664d-190">**Notes**:</span></span>

- <span data-ttu-id="0664d-191">Параметр _Name_ является обязательным, имеет максимальную длину 64 символа и должен быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="0664d-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="0664d-192">Если вы не используете параметр _DisplayName_, для отображаемого имени указывается значение параметра _Name_.</span><span class="sxs-lookup"><span data-stu-id="0664d-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="0664d-193">Если параметр _Alias_ не используется, для псевдонима используется левая сторона параметра _MicrosoftOnlineServicesID._</span><span class="sxs-lookup"><span data-stu-id="0664d-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="0664d-194">Если параметр _ExternalEmailAddress_ не используется, для внешнего адреса электронной почты используется значение _MicrosoftOnlineServicesID._</span><span class="sxs-lookup"><span data-stu-id="0664d-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="0664d-195">В этом примере создается почтовый пользователь со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="0664d-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="0664d-196">Имя — JeffreyZeng, а отображаемая — "Jeffrey Zeng".</span><span class="sxs-lookup"><span data-stu-id="0664d-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="0664d-197">Имя  Григорий, фамилия  Иванов.</span><span class="sxs-lookup"><span data-stu-id="0664d-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="0664d-198">Псевдоним  gregoryiv.</span><span class="sxs-lookup"><span data-stu-id="0664d-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="0664d-199">Внешний адрес электронной почты  givanov@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="0664d-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="0664d-200">Имя учетной записи jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0664d-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="0664d-201">Пароль  Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="0664d-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="0664d-202">Подробные сведения о синтаксисе и параметрах см. в описании [New-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="0664d-202">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="0664d-203">Использование автономных EOP PowerShell для изменения почтовых пользователей</span><span class="sxs-lookup"><span data-stu-id="0664d-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="0664d-204">Чтобы изменить существующих почтовых пользователей в автономных EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0664d-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="0664d-205">В этом примере настраивается внешний адрес электронной почты для пользователя Марты Артемьевой.</span><span class="sxs-lookup"><span data-stu-id="0664d-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="0664d-206">В этом примере значение "Компания" задано как Contoso для всех почтовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="0664d-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="0664d-207">Подробные сведения о синтаксисе и параметрах см. в описании [set-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="0664d-207">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="0664d-208">Использование автономных EOP PowerShell для удаления почтовых пользователей</span><span class="sxs-lookup"><span data-stu-id="0664d-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="0664d-209">Чтобы удалить почтовых пользователей в автономных EOP PowerShell, замените имя, псевдоним или имя учетной записи почтового пользователя и запустите \<MailUserIdentity\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0664d-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="0664d-210">В этом примере удаляется пользователь почты пользователя Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="0664d-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="0664d-211">Подробные сведения о синтаксисе и параметрах см. в [описании remove-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="0664d-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0664d-212">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="0664d-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="0664d-213">Чтобы убедиться, что вы успешно создали, изменили или удалили почтовых пользователей в автономных EOP, используйте любую из следующих процедур:</span><span class="sxs-lookup"><span data-stu-id="0664d-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="0664d-214">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="0664d-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="0664d-215">Убедитесь, что почтовый пользователь указан (или не указан).</span><span class="sxs-lookup"><span data-stu-id="0664d-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="0664d-216">Выберите пользователя почты и просмотреть сведения в  области сведений или нажмите значок редактирования, ![ чтобы ](../../media/ITPro-EAC-AddIcon.png) просмотреть параметры.</span><span class="sxs-lookup"><span data-stu-id="0664d-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="0664d-217">В автономных EOP PowerShell запустите следующую команду, чтобы убедиться, что почтовый пользователь указан (или не указан):</span><span class="sxs-lookup"><span data-stu-id="0664d-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="0664d-218">Замените имя, псевдоним или имя учетной записи почтового пользователя и запустите следующие команды для проверки \<MailUserIdentity\> параметров:</span><span class="sxs-lookup"><span data-stu-id="0664d-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="0664d-219">Управление почтовыми пользователями с помощью синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="0664d-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="0664d-220">В автономных EOP синхронизация службы каталогов доступна пользователям с локальной службой Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0664d-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="0664d-221">Вы можете синхронизировать эти учетные записи с Azure Active Directory (Azure AD), где копии учетных записей хранятся в облаке.</span><span class="sxs-lookup"><span data-stu-id="0664d-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="0664d-222">При синхронизации существующих учетных записей пользователей с Azure Active Directory их можно просмотреть в области получателей в Центре администрирования Exchange (EAC) или в автономных службах EOP PowerShell. </span><span class="sxs-lookup"><span data-stu-id="0664d-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="0664d-223">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="0664d-223">**Notes**:</span></span>

- <span data-ttu-id="0664d-224">Если вы используете синхронизацию службы каталогов для управления получателями, вы по-прежнему можете добавлять пользователей и управлять ими в Центре администрирования Microsoft 365, но они не будут синхронизированы с локальной службой Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0664d-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="0664d-225">Это объясняется тем, что получатели синхронизируются только в одном направлении: из локальной службы каталогов Active Directory в облако.</span><span class="sxs-lookup"><span data-stu-id="0664d-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="0664d-226">Синхронизацию службы каталогов рекомендуется использовать с такими функциями:</span><span class="sxs-lookup"><span data-stu-id="0664d-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="0664d-227">**Списки** надежных и заблокированных отправитель Outlook: при синхронизации со службой эти списки будут иметь приоритет над фильтрацией нежелательной почты в службе.</span><span class="sxs-lookup"><span data-stu-id="0664d-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="0664d-228">Это позволяет пользователям управлять собственным списком надежных и заблокированных отправитель с помощью отдельных записей отправитель и домен.</span><span class="sxs-lookup"><span data-stu-id="0664d-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="0664d-229">Дополнительные сведения см. в разделе [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="0664d-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="0664d-230">Пограмная блокировка на основе каталогов **(DBEB).** Дополнительные сведения о DBEB см. в этой теме, чтобы отклонить сообщения, отправленные недопустимым [получателям.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)</span><span class="sxs-lookup"><span data-stu-id="0664d-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="0664d-231">**Доступ конечных пользователей** к карантину: чтобы получить доступ к своим сообщениям на карантине, получатели должны иметь действительный ИД пользователя и пароль в службе.</span><span class="sxs-lookup"><span data-stu-id="0664d-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="0664d-232">Дополнительные сведения о карантине см. в записи поиска и освобождения сообщений из карантина от [пользователя.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="0664d-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="0664d-233">Правила потока обработки почты (также известные как правила **транспорта).** При использовании синхронизации службы каталогов существующие пользователи и группы Active Directory автоматически загружаются в облако, и вы можете создать правила потока обработки почты, которые будут ориентированы на определенных пользователей и/или группы, не добавляя их в службу вручную.</span><span class="sxs-lookup"><span data-stu-id="0664d-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="0664d-234">Обратите [внимание, что динамические](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) группы рассылки нельзя синхронизировать с помощью синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="0664d-234">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="0664d-235">Получите необходимые разрешения и подготовьтесь к синхронизации службы каталогов, как описано в описании гибридного удостоверения [с Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)</span><span class="sxs-lookup"><span data-stu-id="0664d-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="0664d-236">Синхронизация каталогов с помощью Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="0664d-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="0664d-237">Активация синхронизации службы каталогов, как описано в синхронизации [Azure AD Connect: понимание и настройка синхронизации.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)</span><span class="sxs-lookup"><span data-stu-id="0664d-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="0664d-238">Установка и настройка локального компьютера для запуска AAD Connect, как описано в предварительных условия [для Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="0664d-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="0664d-239">[Выберите тип установки, который будет применяться для Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="0664d-239">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="0664d-240">Express</span><span class="sxs-lookup"><span data-stu-id="0664d-240">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="0664d-241">Custom</span><span class="sxs-lookup"><span data-stu-id="0664d-241">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="0664d-242">Сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="0664d-242">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="0664d-p121">Когда Мастер настройки средства синхронизации Azure Active Directory завершит работу, учетная запись **MSOL_AD_SYNC** будет создана в вашем лесу Active Directory. Она используется для чтения и синхронизации локальных данных Active Directory. Чтобы каталоги синхронизировались правильно, убедитесь, что порт TCP 443 на локальном сервере синхронизации службы каталогов открыт.</span><span class="sxs-lookup"><span data-stu-id="0664d-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="0664d-246">После настройки синхронизации убедитесь, что AAD Connect синхронизируется правильно.</span><span class="sxs-lookup"><span data-stu-id="0664d-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="0664d-247">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты** и убедитесь, что список пользователей с локальной среды должным образом синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="0664d-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
