---
title: Защита учетных записей администратора
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
description: Узнайте, как настроить и защитить учетные записи администратора.
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398245"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="f1bbb-103">Защита учетных записей администратора</span><span class="sxs-lookup"><span data-stu-id="f1bbb-103">Protect your administrator accounts</span></span>

<span data-ttu-id="f1bbb-104">Поскольку учетные записи администратора имеют повышенные привилегии, они являются ценными целями для хакеров и киберпреступлений.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="f1bbb-105">В этой статье описываются:</span><span class="sxs-lookup"><span data-stu-id="f1bbb-105">This article describes:</span></span>

- <span data-ttu-id="f1bbb-106">Настройка дополнительной учетной записи администратора для чрезвычайных ситуаций.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="f1bbb-107">Защита этих учетных записей.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-107">How to protect these accounts.</span></span>

<span data-ttu-id="f1bbb-108">Когда вы зарегистрируетсяе в Microsoft 365 и введите свои сведения, вы автоматически станете глобальным администратором. Глобальный администратор имеет полный контроль над учетными записями пользователей и всеми другими настройками в центре администрирования Майкрософт, но существует множество различных типов учетных записей администратора с различной степенью доступа.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-108">When you sign up for Microsoft 365 and enter your information, you automatically become the Global admin. A Global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="f1bbb-109">Сведения [о роли администратора](/office365/admin/add-users/about-admin-roles) см. в сведениях о различных уровнях доступа для каждого вида роли администратора.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-109">See [about admin roles](/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="f1bbb-110">Создание дополнительных учетных записей администратора</span><span class="sxs-lookup"><span data-stu-id="f1bbb-110">Create additional admin accounts</span></span>

<span data-ttu-id="f1bbb-111">Используйте учетные записи администратора только для администрирования.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="f1bbb-112">Администраторы должны иметь отдельную учетную запись пользователя для регулярного использования приложений Office и использовать их административную учетную запись только при необходимости для управления учетными записями и устройствами, а также при работе с другими функциями администратора.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="f1bbb-113">Также неплохо удалить лицензию Microsoft 365 из учетных записей администратора, чтобы не платить за них.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="f1bbb-114">Чтобы предоставить администратору доступ к другому доверенного сотрудника, необходимо настроить по крайней мере одну дополнительную учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-114">You'll want to set up at least one additional Global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="f1bbb-115">Можно также создать отдельные учетные записи администратора для управления пользователями (эта роль называется **администратором управления пользователями).**</span><span class="sxs-lookup"><span data-stu-id="f1bbb-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="f1bbb-116">Дополнительные сведения см. в [дополнительных сведениях о ролях администратора.](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="f1bbb-116">For more information, see [about admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="f1bbb-117">Создание дополнительных учетных записей администратора:</span><span class="sxs-lookup"><span data-stu-id="f1bbb-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="f1bbb-118">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">центр администрирования и</a> выберите **пользователей Users** Active \> **в** левом nav.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Выберите пользователей, а затем активных пользователей в левом nav](../media/Activeusers.png)

 2. <span data-ttu-id="f1bbb-120">На странице **Активные пользователи** выберите **Добавить** пользователя в верхней части страницы, а на панели **Новых** пользователей введите имя и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="f1bbb-121">**Расширь раздел Роли** и выберите **глобального** администратора, чтобы предоставить этому пользователю глобальный доступ администратора.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="f1bbb-122">Вы также можете выбрать **настраиваемого администратора** и выбрать любую из отображаемых ролей.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="f1bbb-123">Введите альтернативное сообщение электронной почты в **текстовом** окне Альтернативный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="f1bbb-124">Этот адрес можно использовать для восстановления сведений о паролях, если вас заблокировали. Для глобальных администраторов на этот адрес также будет отправлено заявление о выставлении счета.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-124">You can use this address to recover your password information if you get locked out. For Global admins, a billing statement will also be sent to this address.</span></span>

    ![Выбор роли администратора](../media/adminroles.png)

 4. <span data-ttu-id="f1bbb-126">В разделе **Лицензии** на продукт переключите селектор для  Microsoft  **365 Бизнес** на отключение и создайте пользователя без лицензии на продукт **в On**.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Выбор лицензии на продукт](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="f1bbb-128">Создание учетной записи администратора при чрезвычайных ситуациях</span><span class="sxs-lookup"><span data-stu-id="f1bbb-128">Create an emergency admin account</span></span>

<span data-ttu-id="f1bbb-129">Необходимо также создать учетную запись резервного копирования, которая не настроена с помощью многофакторной проверки подлинности (MFA), чтобы не случайно заблокировать себя (например, если вы потеряете телефон, который используется в качестве второй формы проверки).</span><span class="sxs-lookup"><span data-stu-id="f1bbb-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="f1bbb-130">Убедитесь, что пароль для этой учетной записи является фразой или длиной не менее 16 символов.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="f1bbb-131">Это часто называют "учетной записью с брейк-стеклом".</span><span class="sxs-lookup"><span data-stu-id="f1bbb-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="f1bbb-132">Создание учетной записи пользователя для себя</span><span class="sxs-lookup"><span data-stu-id="f1bbb-132">Create a user account for yourself</span></span>

<span data-ttu-id="f1bbb-133">Используйте учетную запись пользователя для участия в сотрудничестве с организацией, включая проверку почты.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="f1bbb-134">Это означает, что учетные данные администратора могут быть похожи на *Alice.Chavez <span></span> @Contoso.org,* а обычная учетная запись пользователя может быть похожа *на Alice <span></span> @Contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="f1bbb-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="f1bbb-135">Создание новой учетной записи пользователя:</span><span class="sxs-lookup"><span data-stu-id="f1bbb-135">To create a new user account:</span></span>

1. <span data-ttu-id="f1bbb-136">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">центр администрирования и</a> выберите **пользователей Users** Active \> **в** левом nav.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="f1bbb-137">На странице **Активные пользователи** выберите **Добавить** пользователя в верхней части страницы, а на панели **Новых** пользователей введите имя и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="f1bbb-138">**Расширь раздел Роли** и выберите User **(без административного доступа).**</span><span class="sxs-lookup"><span data-stu-id="f1bbb-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="f1bbb-139">В разделе **Лицензии на продукт** переместим селектор **для Microsoft 365 Бизнес** в **on**.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="turn-on-security-defaults"></a><span data-ttu-id="f1bbb-140">Включим по умолчанию безопасность</span><span class="sxs-lookup"><span data-stu-id="f1bbb-140">Turn on security defaults</span></span>

<span data-ttu-id="f1bbb-141">По умолчанию по умолчанию безопасность помогает защитить организацию от атак, связанных с удостоверениями, предоставляя заранее задатки безопасности, управляемые Корпорацией Майкрософт от имени вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-141">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="f1bbb-142">Эти параметры включают включение многофакторной проверки подлинности (MFA) для всех администраторов и учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-142">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="f1bbb-143">Дополнительные сведения о дефолтах безопасности и о том, как включить их, см. в руб. [Включим по умолчанию безопасность.](m365-campaigns-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="f1bbb-143">For more information about security defaults and to learn how to enable them on, see [Turn on security defaults](m365-campaigns-conditional-access.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="f1bbb-144">Дополнительные рекомендации</span><span class="sxs-lookup"><span data-stu-id="f1bbb-144">Additional recommendations</span></span>

- <span data-ttu-id="f1bbb-145">Перед использованием учетных записей администратора закрой все несвязанные сеансы браузера и приложения, включая личные учетные записи электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="f1bbb-146">Вы также можете использовать в частных окнах браузера или инкогнито.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="f1bbb-147">После выполнения задач администрирования не забудьте выйти из сеанса браузера.</span><span class="sxs-lookup"><span data-stu-id="f1bbb-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
