---
title: Управление пользователями почты в автономном EOP
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
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Узнайте об управлении почтовыми пользователями в Exchange Online Protection (EOP), в том числе с использованием синхронизации службы каталогов, EAC и PowerShell для управления пользователями.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64b7effadd96b6dc025677139c4303acd538dadb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827079"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="e2897-103">Управление пользователями почты в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="e2897-103">Manage mail users in standalone EOP</span></span>

<span data-ttu-id="e2897-104">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online почтовые ящики пользователей почты являются основным типом учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2897-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="e2897-105">У пользователя почты есть учетные данные в вашей автономной организации EOP, и он может обращаться к ресурсам (иметь назначенные разрешения).</span><span class="sxs-lookup"><span data-stu-id="e2897-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="e2897-106">Электронный адрес пользователя почты является внешним (например, в локальной почтовой среде).</span><span class="sxs-lookup"><span data-stu-id="e2897-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="e2897-107">При создании почтового пользователя соответствующая учетная запись пользователя будет доступна в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2897-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e2897-108">При создании учетной записи пользователя в Центре администрирования Microsoft 365 невозможно использовать эту учетную запись для создания пользователя почты.</span><span class="sxs-lookup"><span data-stu-id="e2897-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="e2897-109">Рекомендуемый метод создания почтовых пользователей в автономной службе EOP [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) и управления ими — использование синхронизации службы каталогов, описанное далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e2897-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="e2897-110">Для отдельных организаций EOP с небольшим количеством пользователей можно добавлять почтовых пользователей и управлять ими в Центре администрирования Exchange (EAC) или автономной среде PowerShell EOP, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e2897-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e2897-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e2897-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e2897-112">Чтобы открыть Центр администрирования Exchange ,см. раздел [Центра администрирования Exchange в автономной службе EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="e2897-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="e2897-113">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e2897-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e2897-114">При создании почтовых пользователей в PowerShell в службе EOP вы можете столкнуться с регулированием.</span><span class="sxs-lookup"><span data-stu-id="e2897-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="e2897-115">Кроме того, командлеты PowerShell в EOP используют метод пакетной обработки, из-за чего результаты команд будут видны через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="e2897-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="e2897-116">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="e2897-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="e2897-117">В частности, требуются роли создания (создания) и получателей почты (изменение), которые по умолчанию назначаются группам ролей OrganizationManagement (глобальные администраторы) и RecipientManagement.</span><span class="sxs-lookup"><span data-stu-id="e2897-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="e2897-118">Дополнительные сведения см. в разделе ["Разрешения в автономной службе EOP"](feature-permissions-in-eop.md) и использовании Центра администрирования [Exchange для изменения списка членов в группах ролей.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="e2897-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="e2897-119">Сочетания клавиш для процедур, описанных в этой статье, приведены в разделе сочетания клавиш для [Центра администрирования Exchange в Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="e2897-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="e2897-120">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="e2897-120">Having problems?</span></span> <span data-ttu-id="e2897-121">Обратитесь за помощью к участникам форумов Exchange.</span><span class="sxs-lookup"><span data-stu-id="e2897-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="e2897-122">Посетите [форум по Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="e2897-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="e2897-123">Управление почтовыми пользователями с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="e2897-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="e2897-124">Создание почтовых пользователей с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="e2897-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="e2897-125">В Центре администрирования Exchange перейдите к **разделу "Получатели"** \> **Contacts**</span><span class="sxs-lookup"><span data-stu-id="e2897-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="e2897-126">Щелкните **значок** ![ ](../../media/ITPro-EAC-AddIcon.png) "Создать".</span><span class="sxs-lookup"><span data-stu-id="e2897-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="e2897-127">На **открывшейся странице "Новый** пользователь почты" настройте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e2897-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="e2897-128">Обязательными являются <sup>\*</sup> параметры.</span><span class="sxs-lookup"><span data-stu-id="e2897-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="e2897-129">**Имя**</span><span class="sxs-lookup"><span data-stu-id="e2897-129">**First name**</span></span>

   - <span data-ttu-id="e2897-130">**Инициалы:** отчество человека.</span><span class="sxs-lookup"><span data-stu-id="e2897-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="e2897-131">**Фамилия**</span><span class="sxs-lookup"><span data-stu-id="e2897-131">**Last name**</span></span>

   - <span data-ttu-id="e2897-132"><sup>\*</sup>**Отображаемое имя:** по умолчанию в этом поле отображаются значения из полей **"Имя",** **"Инициализация"** и **"Фамилия".**</span><span class="sxs-lookup"><span data-stu-id="e2897-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="e2897-133">Можно принять это или изменить его.</span><span class="sxs-lookup"><span data-stu-id="e2897-133">You can accept this value or change it.</span></span> <span data-ttu-id="e2897-134">Значение должно быть уникальным и иметь длину не более 64 символов.</span><span class="sxs-lookup"><span data-stu-id="e2897-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="e2897-135"><sup>\*</sup>**Псевдоним:** введите уникальный псевдоним пользователя, используя до 64 символов.</span><span class="sxs-lookup"><span data-stu-id="e2897-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="e2897-136">**Внешний адрес электронной**почты: введите электронный адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2897-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="e2897-137">Домен должен быть внешним по облачной организации.</span><span class="sxs-lookup"><span data-stu-id="e2897-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="e2897-138"><sup>\*</sup>**Идентификатор пользователя:** введите учетную запись, которую пользователь будет использовать для входа в службу.</span><span class="sxs-lookup"><span data-stu-id="e2897-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="e2897-139">Идентификатор состоит из имени пользователя слева от знака @и домена справа от нее.</span><span class="sxs-lookup"><span data-stu-id="e2897-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="e2897-140"><sup>\*</sup>**Новый пароль и** <sup>\*</sup> **подтверждение пароля:** введите пароль и снова введите пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e2897-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="e2897-141">Убедитесь, что пароль удовлетворяет требованиям вашей организации к длине, сложности и истории паролей.</span><span class="sxs-lookup"><span data-stu-id="e2897-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="e2897-142">Когда вы закончили, нажмите кнопку **Сохранить**, чтобы создать пользователя почты.</span><span class="sxs-lookup"><span data-stu-id="e2897-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="e2897-143">Изменение почтовых пользователей с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="e2897-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="e2897-144">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="e2897-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="e2897-145">Выберите пользователя почты, которого необходимо изменить, и нажмите значок **Edit** ![ "Изменить" и значок ](../../media/ITPro-EAC-AddIcon.png) "Изменить".</span><span class="sxs-lookup"><span data-stu-id="e2897-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="e2897-146">На открывшейся странице свойств пользователя почты щелкните одну из следующих вкладок, чтобы просмотреть или изменить свойства.</span><span class="sxs-lookup"><span data-stu-id="e2897-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="e2897-147">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e2897-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="e2897-148">Общие</span><span class="sxs-lookup"><span data-stu-id="e2897-148">General</span></span>

<span data-ttu-id="e2897-149">Вкладка **"Общие"** позволяет просматривать или изменять основные сведения о пользователе почты.</span><span class="sxs-lookup"><span data-stu-id="e2897-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="e2897-150">**Имя**</span><span class="sxs-lookup"><span data-stu-id="e2897-150">**First name**</span></span>

- <span data-ttu-id="e2897-151">**Инициалы**</span><span class="sxs-lookup"><span data-stu-id="e2897-151">**Initials**</span></span>

- <span data-ttu-id="e2897-152">**Фамилия**</span><span class="sxs-lookup"><span data-stu-id="e2897-152">**Last name**</span></span>

- <span data-ttu-id="e2897-153">**Отображаемое имя:** это имя будет отображаться в адресной книге, в поле "Кому" "От" в электронной почте и в списке контактов в Центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="e2897-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="e2897-154">Это имя не может содержать пробелы до или после отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="e2897-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="e2897-155">**Идентификатор пользователя:** это учетная запись пользователя в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2897-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="e2897-156">Это значение здесь невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="e2897-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="e2897-157">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="e2897-157">Contact information</span></span>

<span data-ttu-id="e2897-158">Используйте **вкладку "Контактные** данные" для просмотра или изменения контактных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2897-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="e2897-159">Информация на этой странице отображается в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="e2897-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="e2897-160">**Street**</span><span class="sxs-lookup"><span data-stu-id="e2897-160">**Street**</span></span>
- <span data-ttu-id="e2897-161">**City**</span><span class="sxs-lookup"><span data-stu-id="e2897-161">**City**</span></span>
- <span data-ttu-id="e2897-162">**Область, республика, край, округ**</span><span class="sxs-lookup"><span data-stu-id="e2897-162">**State/Province**</span></span>
- <span data-ttu-id="e2897-163">**Почтовый индекс**</span><span class="sxs-lookup"><span data-stu-id="e2897-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="e2897-164">**Страна или регион**</span><span class="sxs-lookup"><span data-stu-id="e2897-164">**Country/Region**</span></span>
- <span data-ttu-id="e2897-165">**Рабочий телефон**</span><span class="sxs-lookup"><span data-stu-id="e2897-165">**Work phone**</span></span>
- <span data-ttu-id="e2897-166">**Мобильный телефон**</span><span class="sxs-lookup"><span data-stu-id="e2897-166">**Mobile phone**</span></span>
- <span data-ttu-id="e2897-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="e2897-167">**Fax**</span></span>
- <span data-ttu-id="e2897-168">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="e2897-168">**More options**</span></span>

  - <span data-ttu-id="e2897-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="e2897-169">**Office**</span></span>
  - <span data-ttu-id="e2897-170">**Домашний телефон**</span><span class="sxs-lookup"><span data-stu-id="e2897-170">**Home phone**</span></span>
  - <span data-ttu-id="e2897-171">**Веб-страница**.</span><span class="sxs-lookup"><span data-stu-id="e2897-171">**Web page**</span></span>
  - <span data-ttu-id="e2897-172">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="e2897-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="e2897-173">Организация</span><span class="sxs-lookup"><span data-stu-id="e2897-173">Organization</span></span>

<span data-ttu-id="e2897-174">На **вкладке "Организация"** можно указывать подробные сведения о роли пользователя в организации.</span><span class="sxs-lookup"><span data-stu-id="e2897-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="e2897-175">**Название**</span><span class="sxs-lookup"><span data-stu-id="e2897-175">**Title**</span></span>
- <span data-ttu-id="e2897-176">**Department**</span><span class="sxs-lookup"><span data-stu-id="e2897-176">**Department**</span></span>
- <span data-ttu-id="e2897-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="e2897-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="e2897-178">Использование Центра администрирования Exchange для удаления почтовых пользователей</span><span class="sxs-lookup"><span data-stu-id="e2897-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="e2897-179">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="e2897-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="e2897-180">Выберите пользователя почты, которого необходимо удалить, и нажмите значок **Remove** ![ "Удалить". ](../../media/ITPro-EAC-RemoveIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="e2897-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="e2897-181">Управление почтовыми пользователями с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2897-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="e2897-182">Просмотр почтовых пользователей с помощью автономной оболочки EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2897-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="e2897-183">Чтобы получить сводный список всех пользователей почты в изолированной службе EOP PowerShell, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e2897-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="e2897-184">Чтобы просмотреть подробные сведения об определенном пользователе почты, замените именем, псевдонимом или \<MailUserIdentity\> учетной записью пользователя почты и выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e2897-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="e2897-185">Дополнительные сведения о синтаксисе и параметрах см. в [разделах Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) [и Get-User.](https://docs.microsoft.com/powershell/module/exchange/get-user)</span><span class="sxs-lookup"><span data-stu-id="e2897-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="e2897-186">Создание почтовых пользователей с помощью автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2897-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="e2897-187">Чтобы создать почтовых пользователей в изолированной службе EOP PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e2897-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="e2897-188">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="e2897-188">**Notes**:</span></span>

- <span data-ttu-id="e2897-189">Параметр _Name_ является обязательным, его длина не должна превышать 64 символа и быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="e2897-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="e2897-190">Если вы не используете параметр _DisplayName_, для отображаемого имени указывается значение параметра _Name_.</span><span class="sxs-lookup"><span data-stu-id="e2897-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="e2897-191">Если параметр Alias не указан, _то_ в качестве псевдонима используется левая часть параметра _MicrosoftOnlineServicesID._</span><span class="sxs-lookup"><span data-stu-id="e2897-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="e2897-192">Если параметр _ExternalEmailAddress_ не используется, значение _MicrosoftOnlineServicesID_ используется в качестве внешнего адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e2897-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="e2897-193">В этом примере создается пользователь почты со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="e2897-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="e2897-194">Имя Григорий Иван.</span><span class="sxs-lookup"><span data-stu-id="e2897-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="e2897-195">Имя  Григорий, фамилия  Иванов.</span><span class="sxs-lookup"><span data-stu-id="e2897-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="e2897-196">Псевдоним  gregoryiv.</span><span class="sxs-lookup"><span data-stu-id="e2897-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="e2897-197">Внешний адрес электронной почты  givanov@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="e2897-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="e2897-198">Имя учетной записи jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e2897-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="e2897-199">Пароль  Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="e2897-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="e2897-200">Дополнительные сведения о синтаксисе и параметрах см. в [разделе New-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="e2897-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="e2897-201">Использование автономной оболочки PowerShell для изменения почтовых пользователей</span><span class="sxs-lookup"><span data-stu-id="e2897-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="e2897-202">Для изменения существующих почтовых пользователей в автономной службе EOP PowerShell используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e2897-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="e2897-203">В этом примере настраивается внешний адрес электронной почты для пользователя Марты Артемьевой.</span><span class="sxs-lookup"><span data-stu-id="e2897-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="e2897-204">В этом примере значение "Компания" задано как Contoso для всех почтовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2897-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="e2897-205">Дополнительные сведения о синтаксисе и параметрах см. в [статье О Set-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="e2897-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="e2897-206">Удаление почтовых пользователей с помощью автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2897-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="e2897-207">Чтобы удалить пользователей почты в автономной службе EOP PowerShell, \<MailUserIdentity\> замените именем, псевдонимом или учетной записью почтового пользователя и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e2897-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="e2897-208">В этом примере удаляется пользователь почты для пользователя Григория Ивана.</span><span class="sxs-lookup"><span data-stu-id="e2897-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="e2897-209">Дополнительные сведения о синтаксисе и параметрах [см. в статье Remove-EOPMailUser.](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="e2897-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e2897-210">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="e2897-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="e2897-211">Чтобы убедиться в том, что в автономной службе EOP успешно создано, изменено или удалено пользователей почты, выполните одну из приведенных ниже процедур.</span><span class="sxs-lookup"><span data-stu-id="e2897-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="e2897-212">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты**.</span><span class="sxs-lookup"><span data-stu-id="e2897-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="e2897-213">Убедитесь, что почтовый пользователь входит в список (или нет в списке).</span><span class="sxs-lookup"><span data-stu-id="e2897-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="e2897-214">Выберите пользователя почты и просмотрите сведения в области сведений или **нажмите** значок ![ редактирования, ](../../media/ITPro-EAC-AddIcon.png) чтобы просмотреть параметры.</span><span class="sxs-lookup"><span data-stu-id="e2897-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="e2897-215">В автономной службе EOP PowerShell выполните следующую команду, чтобы убедиться, что почтовый пользователь добавлен в список (или нет в списке):</span><span class="sxs-lookup"><span data-stu-id="e2897-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="e2897-216">Замените \<MailUserIdentity\> именем, псевдонимом или учетной записью пользователя почты и выполните следующие команды для проверки параметров:</span><span class="sxs-lookup"><span data-stu-id="e2897-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="e2897-217">Управление почтовыми пользователями с помощью синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="e2897-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="e2897-218">В автономной службе EOP синхронизация каталогов доступна пользователям, использующих локальную службу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e2897-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="e2897-219">Вы можете синхронизировать эти учетные записи с Azure Active Directory (Azure AD), где копии учетных записей хранятся в облаке.</span><span class="sxs-lookup"><span data-stu-id="e2897-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="e2897-220">При синхронизации существующих учетных записей с Azure Active Directory **Recipients** вы можете просматривать соответствующих пользователей в области получателей Центра администрирования Exchange (EAC) или автономной службе EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2897-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="e2897-221">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="e2897-221">**Notes**:</span></span>

- <span data-ttu-id="e2897-222">Если для управления получателями используется синхронизация службы каталогов, пользователей можно добавлять и управлять ими в Центр администрирования Microsoft 365, однако они не будут синхронизироваться с локальной службой Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e2897-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="e2897-223">Это объясняется тем, что получатели синхронизируются только в одном направлении: из локальной службы каталогов Active Directory в облако.</span><span class="sxs-lookup"><span data-stu-id="e2897-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="e2897-224">Синхронизацию службы каталогов рекомендуется использовать с такими функциями:</span><span class="sxs-lookup"><span data-stu-id="e2897-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="e2897-225">**Списки надежных отправителей и заблокированных отправителей Outlook:** при синхронизации со службой эти списки имеют приоритет над фильтрацией нежелательной почты в службе.</span><span class="sxs-lookup"><span data-stu-id="e2897-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="e2897-226">Это позволяет пользователям управлять своими собственными списками надежных отправителей и заблокированных отправителей с отдельными записями отправителя и домена.</span><span class="sxs-lookup"><span data-stu-id="e2897-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="e2897-227">Дополнительные сведения см. в разделе [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="e2897-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="e2897-228">**Пограничная блокировка на основе каталогов (DBEB):** дополнительные сведения о пограничной блокировке на основе каталогов см. в разделе "Использование пограничной блокировки на основе каталогов" для отклонения [сообщений, отправленных недопустимым получателям.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)</span><span class="sxs-lookup"><span data-stu-id="e2897-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="e2897-229">**Доступ пользователей к карантине:** чтобы получить доступ к сообщениям, помещенным в карантин, у получателей должен быть действительный идентификатор пользователя и пароль в службе.</span><span class="sxs-lookup"><span data-stu-id="e2897-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="e2897-230">Дополнительные сведения о карантине см. в разделе ["Поиск и освобождение сообщений на карантине для пользователя".](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)</span><span class="sxs-lookup"><span data-stu-id="e2897-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="e2897-231">**Правила потока обработки почты (правила транспорта).** При использовании синхронизации службы каталогов существующие пользователи и группы Active Directory автоматически загружаются в облако и затем можно создать правила потока обработки почты для определенных пользователей и/или групп без необходимости добавлять их в службу вручную.</span><span class="sxs-lookup"><span data-stu-id="e2897-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="e2897-232">Обратите внимание, что [динамические группы рассылки](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) нельзя синхронизировать с синхронизацией службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="e2897-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="e2897-233">Получите необходимые разрешения и подготовьтесь к синхронизации службы каталогов, как описано в [статье что такое гибридное удостоверение в Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)</span><span class="sxs-lookup"><span data-stu-id="e2897-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="e2897-234">Синхронизация каталогов с Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="e2897-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="e2897-235">Активация синхронизации службы каталогов, как описано [в синхронизации Azure AD Connect: анализ синхронизации и настройка их](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)параметров.</span><span class="sxs-lookup"><span data-stu-id="e2897-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="e2897-236">Установка и настройка локального компьютера для запуска AAD Connect согласно предварительным [требованиям для Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="e2897-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="e2897-237">[Выберите тип установки для Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="e2897-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="e2897-238">Express</span><span class="sxs-lookup"><span data-stu-id="e2897-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="e2897-239">Custom</span><span class="sxs-lookup"><span data-stu-id="e2897-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="e2897-240">Сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="e2897-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="e2897-p121">Когда Мастер настройки средства синхронизации Azure Active Directory завершит работу, учетная запись **MSOL_AD_SYNC** будет создана в вашем лесу Active Directory. Она используется для чтения и синхронизации локальных данных Active Directory. Чтобы каталоги синхронизировались правильно, убедитесь, что порт TCP 443 на локальном сервере синхронизации службы каталогов открыт.</span><span class="sxs-lookup"><span data-stu-id="e2897-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="e2897-244">После настройки синхронизации убедитесь, что синхронизация в AAD Connect выполняется правильно.</span><span class="sxs-lookup"><span data-stu-id="e2897-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="e2897-245">В Центре администрирования Exchange перейдите в раздел **Получатели** \> **Контакты** и убедитесь, что список пользователей с локальной среды должным образом синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="e2897-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
