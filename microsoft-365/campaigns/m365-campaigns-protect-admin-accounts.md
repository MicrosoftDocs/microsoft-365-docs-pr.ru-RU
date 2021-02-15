---
title: Защита учетных записей администраторов
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Узнайте, как настроить и защитить учетные записи администраторов.
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044492"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="8c855-103">Защита учетных записей администраторов</span><span class="sxs-lookup"><span data-stu-id="8c855-103">Protect your administrator accounts</span></span>

<span data-ttu-id="8c855-104">Поскольку учетные записи администраторов имеют повышенные привилегии, они являются ценными целями для злоумышленников и киберпреступных.</span><span class="sxs-lookup"><span data-stu-id="8c855-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="8c855-105">В этой статье описываются:</span><span class="sxs-lookup"><span data-stu-id="8c855-105">This article describes:</span></span>

- <span data-ttu-id="8c855-106">Настройка дополнительной учетной записи администратора для экстренных ситуаций.</span><span class="sxs-lookup"><span data-stu-id="8c855-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="8c855-107">Как защитить эти учетные записи.</span><span class="sxs-lookup"><span data-stu-id="8c855-107">How to protect these accounts.</span></span>

<span data-ttu-id="8c855-108">Когда вы зарегистрируетсяе в Microsoft 365 и введите свою информацию, вы автоматически станете глобальным администратором. Глобальный администратор полностью контролирует учетные записи пользователей и все остальные параметры в Центре администрирования Майкрософт, но существует множество различных типов учетных записей администраторов с различной степенью доступа.</span><span class="sxs-lookup"><span data-stu-id="8c855-108">When you sign up for Microsoft 365 and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="8c855-109">Сведения [о различных уровнях](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) доступа для каждой роли администратора см. в сведениях о ролях администраторов.</span><span class="sxs-lookup"><span data-stu-id="8c855-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="8c855-110">Создание дополнительных учетных записей администраторов</span><span class="sxs-lookup"><span data-stu-id="8c855-110">Create additional admin accounts</span></span>

<span data-ttu-id="8c855-111">Используйте учетные записи администратора только для администрирования.</span><span class="sxs-lookup"><span data-stu-id="8c855-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="8c855-112">Администраторы должны иметь отдельную учетную запись пользователя для регулярного использования приложений Office и использовать административную учетную запись только при необходимости для управления учетными записями и устройствами, а также при работе с другими функциями администратора.</span><span class="sxs-lookup"><span data-stu-id="8c855-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="8c855-113">Кроме того, имеется хорошая идея удалить лицензию Microsoft 365 из учетных записей администраторов, чтобы вам не нужно было платить за них.</span><span class="sxs-lookup"><span data-stu-id="8c855-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="8c855-114">Вам необходимо настроить по крайней мере одну дополнительную учетную запись глобального администратора, чтобы предоставить администратору доступ другому надежному сотруднику.</span><span class="sxs-lookup"><span data-stu-id="8c855-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="8c855-115">Вы также можете создать отдельные учетные записи администраторов для управления пользователями (эта роль называется **администратором управления пользователями).**</span><span class="sxs-lookup"><span data-stu-id="8c855-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="8c855-116">Дополнительные сведения см. [в сведениях о ролях администраторов.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="8c855-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="8c855-117">Создание дополнительных учетных записей администраторов:</span><span class="sxs-lookup"><span data-stu-id="8c855-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="8c855-118">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Центр администрирования и</a> выберите **"Активные** \> **пользователи" в** левой области.</span><span class="sxs-lookup"><span data-stu-id="8c855-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Choose Users and then Active users in the left nav](../media/Activeusers.png)

 2. <span data-ttu-id="8c855-120">На странице **"Активные пользователи"** выберите "Добавить пользователя" в  верхней части страницы, а на панели "Новый пользователь" введите имя и другие сведения. </span><span class="sxs-lookup"><span data-stu-id="8c855-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="8c855-121">Раз развернуть раздел **"Роли"** и выбрать **глобального администратора,** чтобы предоставить этому пользователю доступ глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8c855-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="8c855-122">Можно также выбрать **настраиваемого администратора** и выбрать любую из отображаемых ролей.</span><span class="sxs-lookup"><span data-stu-id="8c855-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="8c855-123">Введите альтернативное сообщение электронной почты в текстовое поле **"Альтернативный адрес электронной** почты".</span><span class="sxs-lookup"><span data-stu-id="8c855-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="8c855-124">Этот адрес можно использовать для восстановления данных пароля в случае блокировки. Для глобальных администраторов на этот адрес также будет отправлена выписка по счету.</span><span class="sxs-lookup"><span data-stu-id="8c855-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![Выбор роли администратора](../media/adminroles.png)

 4. <span data-ttu-id="8c855-126">В разделе **"Лицензии** на продукты" переместим селектор  **для Microsoft 365 бизнес** в выключенный и "Создать пользователя **без** лицензии на продукт" в **"Включите"**.</span><span class="sxs-lookup"><span data-stu-id="8c855-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Выбор лицензии на продукт](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="8c855-128">Создание учетной записи администратора экстренных служб</span><span class="sxs-lookup"><span data-stu-id="8c855-128">Create an emergency admin account</span></span>

<span data-ttu-id="8c855-129">Кроме того, следует создать резервную учетную запись, которая не настроена для многофакторной проверки подлинности (MFA), чтобы случайно не заблокировать себя (например, если вы теряете телефон, который используется в качестве второй формы проверки).</span><span class="sxs-lookup"><span data-stu-id="8c855-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="8c855-130">Убедитесь, что пароль для этой учетной записи является фразой или длиной не менее 16 символов.</span><span class="sxs-lookup"><span data-stu-id="8c855-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="8c855-131">Это часто называется "учетной записью для взлома".</span><span class="sxs-lookup"><span data-stu-id="8c855-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="8c855-132">Создание учетной записи пользователя для себя</span><span class="sxs-lookup"><span data-stu-id="8c855-132">Create a user account for yourself</span></span>

<span data-ttu-id="8c855-133">Используйте свою учетную запись пользователя для участия в совместной работе с организацией, включая проверку почты.</span><span class="sxs-lookup"><span data-stu-id="8c855-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="8c855-134">Это означает, что ваши учетные данные администратора могут быть похожи на *Alice.Chavez <span></span> @Contoso.org,* а обычная учетная запись пользователя может быть похожа на *Алису <span></span> @Contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="8c855-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="8c855-135">Чтобы создать новую учетную запись пользователя:</span><span class="sxs-lookup"><span data-stu-id="8c855-135">To create a new user account:</span></span>

1. <span data-ttu-id="8c855-136">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Центр администрирования и</a> выберите **"Активные** \> **пользователи" в** левой области.</span><span class="sxs-lookup"><span data-stu-id="8c855-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="8c855-137">На странице **"Активные пользователи"** выберите "Добавить пользователя" в  верхней части страницы, а на панели "Новый пользователь" введите имя и другие сведения. </span><span class="sxs-lookup"><span data-stu-id="8c855-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="8c855-138">Раз expand the **Roles** section, and choose **User (no administrative access)**.</span><span class="sxs-lookup"><span data-stu-id="8c855-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="8c855-139">В разделе **"Лицензии на** продукты" переместим селектор **для Microsoft 365 бизнес** в **"Ветвь".**</span><span class="sxs-lookup"><span data-stu-id="8c855-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="8c855-140">Регистрация каждой из этих учетных записей для многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="8c855-140">Register each of these accounts for multi-factor authentication</span></span>

<span data-ttu-id="8c855-141">Убедитесь, что эти учетные записи используют [многофакторную проверку подлинности.](m365-campaigns-multifactor-authenication.md)</span><span class="sxs-lookup"><span data-stu-id="8c855-141">Make sure these accounts are using [multifactor authentication](m365-campaigns-multifactor-authenication.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="8c855-142">Дополнительные рекомендации</span><span class="sxs-lookup"><span data-stu-id="8c855-142">Additional recommendations</span></span>

- <span data-ttu-id="8c855-143">Убедитесь, что учетные записи администраторов также настроены для многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8c855-143">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="8c855-144">Мы покажем, как это сделать в настройках политик [условного доступа.](m365-campaigns-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="8c855-144">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="8c855-145">Перед использованием учетных записей администратора закроем все несвязанные сеансы браузера и приложения, включая личные учетные записи электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8c855-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="8c855-146">Также можно использовать в частных окнах браузера или окнах браузера инкогнито.</span><span class="sxs-lookup"><span data-stu-id="8c855-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="8c855-147">После выполнения задач администрирования не забудьте выйти из сеанса браузера.</span><span class="sxs-lookup"><span data-stu-id="8c855-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
