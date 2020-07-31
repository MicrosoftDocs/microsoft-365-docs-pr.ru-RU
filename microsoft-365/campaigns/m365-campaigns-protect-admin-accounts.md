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
description: Узнайте, как настроить и защитить учетные записи администратора.
ms.openlocfilehash: dc5f72cda0255641d7d2407d266a6ae584560733
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527190"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="00a93-103">Защита учетных записей администраторов</span><span class="sxs-lookup"><span data-stu-id="00a93-103">Protect your administrator accounts</span></span>

<span data-ttu-id="00a93-104">Так как учетные записи администраторов поставляются с повышенными привилегиями, они являются ценными целями для хакеров и кибератакных злоумышленников.</span><span class="sxs-lookup"><span data-stu-id="00a93-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="00a93-105">В этой статье описываются:</span><span class="sxs-lookup"><span data-stu-id="00a93-105">This article describes:</span></span>

- <span data-ttu-id="00a93-106">Настройка дополнительной учетной записи администратора для экстренных ситуаций.</span><span class="sxs-lookup"><span data-stu-id="00a93-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="00a93-107">Способы защиты учетных записей.</span><span class="sxs-lookup"><span data-stu-id="00a93-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="00a93-108">При регистрации в Microsoft 365 и вводе информации автоматически становится глобальным администратором. Глобальный администратор имеет полный контроль над учетными записями пользователей и всеми другими параметрами в центре администрирования Майкрософт, но существует множество различных типов учетных записей администраторов с различной степенью доступа.</span><span class="sxs-lookup"><span data-stu-id="00a93-108">When you sign up for Microsoft 365 and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="00a93-109">Для получения сведений о различных уровнях доступа для каждого типа роли администратора, ознакомьтесь с развернутыми [ролями](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .</span><span class="sxs-lookup"><span data-stu-id="00a93-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="00a93-110">Создание дополнительных учетных записей администраторов</span><span class="sxs-lookup"><span data-stu-id="00a93-110">Create additional admin accounts</span></span>

<span data-ttu-id="00a93-111">Используйте учетные записи администраторов только для администрирования.</span><span class="sxs-lookup"><span data-stu-id="00a93-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="00a93-112">Администраторы должны иметь отдельную учетную запись для обычного использования приложений Office и использовать их административную учетную запись только при необходимости управления учетными записями и устройствами, а также при работе над другими функциями администрирования.</span><span class="sxs-lookup"><span data-stu-id="00a93-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="00a93-113">Кроме того, рекомендуется удалить лицензию на Microsoft 365 из учетных записей администраторов, чтобы их не нужно было платить.</span><span class="sxs-lookup"><span data-stu-id="00a93-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="00a93-114">Вы хотите настроить по крайней мере одну дополнительную учетную запись глобального администратора, чтобы предоставить администратору доступ к другому доверенному сотруднику.</span><span class="sxs-lookup"><span data-stu-id="00a93-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="00a93-115">Вы также можете создавать отдельные учетные записи администраторов для управления пользователями (эта роль называется **администратором управления пользователями**).</span><span class="sxs-lookup"><span data-stu-id="00a93-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="00a93-116">Более подробную информацию можно узнать в статье [сведения о ролях администратора](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="00a93-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="00a93-117">Чтобы создать дополнительные учетные записи администратора:</span><span class="sxs-lookup"><span data-stu-id="00a93-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="00a93-118">Откройте <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">центр администрирования</a> и выберите **Пользователи** \> **Активные пользователи** в левой панели навигации.</span><span class="sxs-lookup"><span data-stu-id="00a93-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Выбор пользователей и активных пользователей в левой панели навигации](../media/Activeusers.png)

2. <span data-ttu-id="00a93-120">На странице **Активные пользователи** выберите **Добавить пользователя** в верхней части страницы, а затем на панели **Новый пользователь** введите имя и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="00a93-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="00a93-121">Разверните раздел **роли** и выберите Глобальный администратор, чтобы предоставить этому пользователю доступ к глобальному **администратору** .</span><span class="sxs-lookup"><span data-stu-id="00a93-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="00a93-122">Вы также можете выбрать **настраиваемого администратора** и выбрать любую из отображаемых ролей.</span><span class="sxs-lookup"><span data-stu-id="00a93-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="00a93-123">Введите альтернативную электронную почту в текстовом поле **альтернативный адрес электронной почты** .</span><span class="sxs-lookup"><span data-stu-id="00a93-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="00a93-124">Вы можете использовать этот адрес для восстановления сведений о пароле в случае блокировки. Для глобальных администраторов на этот адрес также будет отправлена инструкция выставления счетов.</span><span class="sxs-lookup"><span data-stu-id="00a93-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![Выбор роли администратора](../media/adminroles.png)
    
4. <span data-ttu-id="00a93-126">В разделе **лицензии на продукты** переместите селектор для **Microsoft 365 Business** в **автономный режим** , **а для параметра** **создать пользователя без лицензии продукта** .</span><span class="sxs-lookup"><span data-stu-id="00a93-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Выбор лицензии на продукт](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="00a93-128">Создание учетной записи администратора аварийного администратора</span><span class="sxs-lookup"><span data-stu-id="00a93-128">Create an emergency admin account</span></span>

<span data-ttu-id="00a93-129">Кроме того, необходимо создать учетную запись резервного копирования, которая не настроена с использованием многофакторной проверки подлинности (MFA), чтобы не заблокировать себя (например, если вы потеряли свой номер телефона, который вы используете в качестве второй формы проверки).</span><span class="sxs-lookup"><span data-stu-id="00a93-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="00a93-130">Убедитесь, что пароль для этой учетной записи является фразой или длиной не менее 16 символов.</span><span class="sxs-lookup"><span data-stu-id="00a93-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="00a93-131">Это часто называется "учетной записью с разделением текста".</span><span class="sxs-lookup"><span data-stu-id="00a93-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="00a93-132">Самостоятельное создание учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="00a93-132">Create a user account for yourself</span></span>

<span data-ttu-id="00a93-133">Используйте учетную запись пользователя для участия в совместной работе с вашей организацией, включая проверку почты.</span><span class="sxs-lookup"><span data-stu-id="00a93-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="00a93-134">Это означает, что учетные данные администратора могут быть похожи на *Алиса. чавез <span></span> @Contoso. org* и обычная учетная запись пользователя могут быть похожи на *Алиса <span></span> @Contoso. com*.</span><span class="sxs-lookup"><span data-stu-id="00a93-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="00a93-135">Чтобы создать новую учетную запись пользователя, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="00a93-135">To create a new user account:</span></span>
1. <span data-ttu-id="00a93-136">Откройте <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">центр администрирования</a> и выберите **Пользователи** \> **Активные пользователи** в левой панели навигации.</span><span class="sxs-lookup"><span data-stu-id="00a93-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="00a93-137">На странице **Активные пользователи** выберите **Добавить пользователя** в верхней части страницы, а затем на панели **Новый пользователь** введите имя и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="00a93-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="00a93-138">Разверните раздел **роли** и выберите пункт **пользователь (нет административного доступа)**.</span><span class="sxs-lookup"><span data-stu-id="00a93-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="00a93-139">В разделе **лицензии на продукты** переместите селектор для **Microsoft 365 Business** в положение **включено**.</span><span class="sxs-lookup"><span data-stu-id="00a93-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="00a93-140">Зарегистрируйте каждый из этих учетных записей для многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="00a93-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="00a93-141">Дополнительные рекомендации</span><span class="sxs-lookup"><span data-stu-id="00a93-141">Additional recommendations</span></span>

- <span data-ttu-id="00a93-142">Убедитесь, что учетные записи администратора также настроены для многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="00a93-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="00a93-143">Мы покажем, как это сделать: [Настройка политик условного доступа](m365-campaigns-conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="00a93-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="00a93-144">Перед использованием учетных записей администраторов закройте все несвязанные сеансы и приложения браузера, в том числе личные учетные записи электронной почты.</span><span class="sxs-lookup"><span data-stu-id="00a93-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="00a93-145">Вы также можете использовать в частных или инкогнито окнах браузера.</span><span class="sxs-lookup"><span data-stu-id="00a93-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="00a93-146">После выполнения задач администратора не забудьте выйти из сеанса браузера.</span><span class="sxs-lookup"><span data-stu-id="00a93-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>
