---
title: Создание и использование шаблона для добавления пользователей
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- MET150
- MOE150
description: Вы можете создать и использовать шаблон для экономии времени и параметров стандартизации при добавлении нескольких пользователей.
ms.openlocfilehash: a39ad3df7928e45f7cb93a13c6ffc40111f2ee48
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140656"
---
# <a name="create-and-use-a-template-to-add-users"></a><span data-ttu-id="a69c0-103">Создание и использование шаблона для добавления пользователей</span><span class="sxs-lookup"><span data-stu-id="a69c0-103">Create and use a template to add users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a69c0-104">Изменяется центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="a69c0-104">The admin center is changing.</span></span> <span data-ttu-id="a69c0-105">Если ваш интерфейс не отвечает указанным здесь сведениям, ознакомьтесь [со статьей о новом центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a69c0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="a69c0-106">Вы можете создать и использовать шаблон для экономии времени и параметров стандартизации при добавлении нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="a69c0-106">You can create and use a template to save time and standardize settings when you are adding multiple users.</span></span> <span data-ttu-id="a69c0-107">Шаблоны особенно удобны, если у вас есть пользователи, которые совместно используют многие общие свойства, например те, у кого есть одна и та же роль, и те, кому требуется одно и то же программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="a69c0-107">Templates are particularly useful if you have users who share many common properties, like those who have the same role and work at the same location and those who require the same software.</span></span> <span data-ttu-id="a69c0-108">Например, у вас может быть группа инженеров службы поддержки, работающих в одном офисе.</span><span class="sxs-lookup"><span data-stu-id="a69c0-108">For example, you might have a team of support engineers who work in the same office.</span></span>  

## <a name="create-a-template"></a><span data-ttu-id="a69c0-109">Создание шаблона</span><span class="sxs-lookup"><span data-stu-id="a69c0-109">Create a template</span></span>

<span data-ttu-id="a69c0-110">Шаблоны просты в создании&mdash;можно выбрать **Пользователи** > **Активные пользователи** > **шаблоны**пользователей, а затем выбрать команду **Добавить шаблон** из раскрывающегося списка или добавить нового пользователя, после чего вы сможете сохранить запись в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="a69c0-110">Templates are easy to create&mdash;you can select **Users** > **Active users** > **User templates**, and then select **Add a template** from the drop-down list, or you can add a new user and when you are finished, you will have the option of saving the entry as a template.</span></span>

<span data-ttu-id="a69c0-111">При создании шаблона после добавления пользователя значения, выбранные для следующих параметров, сохраняются в шаблоне:</span><span class="sxs-lookup"><span data-stu-id="a69c0-111">When you create a template after adding a user, the values you choose for the following settings are saved in the template:</span></span>

- <span data-ttu-id="a69c0-112">Доменное имя</span><span class="sxs-lookup"><span data-stu-id="a69c0-112">Domain name</span></span>
- <span data-ttu-id="a69c0-113">Выбор параметров паролей: вы можете создавать пароли или автоматически создавать их.</span><span class="sxs-lookup"><span data-stu-id="a69c0-113">Password settings choice: you can choose to create passwords or have them auto-generated</span></span>
- <span data-ttu-id="a69c0-114">Одноразовый пароль: вы можете потребовать от пользователя создания нового пароля после первого входа в систему.</span><span class="sxs-lookup"><span data-stu-id="a69c0-114">One-time password choice: you can require the user to create a new password after first sign in</span></span>
- <span data-ttu-id="a69c0-115">Место проведения лицензии</span><span class="sxs-lookup"><span data-stu-id="a69c0-115">License location</span></span>
- <span data-ttu-id="a69c0-116">Варианты лицензирования</span><span class="sxs-lookup"><span data-stu-id="a69c0-116">License choices</span></span>
- <span data-ttu-id="a69c0-117">Варианты выбора приложения</span><span class="sxs-lookup"><span data-stu-id="a69c0-117">Application choices</span></span>
- <span data-ttu-id="a69c0-118">Role</span><span class="sxs-lookup"><span data-stu-id="a69c0-118">Role</span></span>
- <span data-ttu-id="a69c0-119">Большая часть сведений о профиле, таких как **профиль задания**, **Отдел**, **офис**, **офис**и **почтовый адрес**</span><span class="sxs-lookup"><span data-stu-id="a69c0-119">Most profile information, such as **Job profile**, **Department**, **Office**, **Office phone**, and **Street address**</span></span> 

<span data-ttu-id="a69c0-120">Следующие сведения относятся к определенному пользователю и не сохраняются в шаблоне:</span><span class="sxs-lookup"><span data-stu-id="a69c0-120">The following information is user-specific and isn't saved in the template:</span></span>

- <span data-ttu-id="a69c0-121">Имя и фамилия</span><span class="sxs-lookup"><span data-stu-id="a69c0-121">First and last name</span></span>
- <span data-ttu-id="a69c0-122">Различающееся имя (DN)</span><span class="sxs-lookup"><span data-stu-id="a69c0-122">Display name</span></span>
- <span data-ttu-id="a69c0-123">Имя пользователя</span><span class="sxs-lookup"><span data-stu-id="a69c0-123">User name</span></span>
- <span data-ttu-id="a69c0-124">Выбор для отправки пароля в сообщении электронной почты и отправку по электронной почте пароля</span><span class="sxs-lookup"><span data-stu-id="a69c0-124">Choice to send the password in email and who the password email is sent to</span></span>
- <span data-ttu-id="a69c0-125">Номер мобильного телефона</span><span class="sxs-lookup"><span data-stu-id="a69c0-125">Mobile phone number</span></span>

<span data-ttu-id="a69c0-126">Если вы не вводите сведения о параметрах в разделе, это значение будет пустым, а параметр не будет отображаться в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="a69c0-126">If you choose not to enter information for a setting within a section, that value will be blank and that setting will not display in the template.</span></span> <span data-ttu-id="a69c0-127">Например, если оставить **название задания** пустым, то при просмотре шаблона и при использовании шаблона **должность** не будет отображаться вообще.</span><span class="sxs-lookup"><span data-stu-id="a69c0-127">For example, if you leave **Job title** blank, when you review your template and when you use your template, **Job title** will not appear at all.</span></span> <span data-ttu-id="a69c0-128">Если оставить все параметры раздела **профиля** пустыми, в разделе **профиль** будет отображаться **значение нет** в итоговом шаблоне.</span><span class="sxs-lookup"><span data-stu-id="a69c0-128">If you leave all the **Profile** section settings blank, the **Profile** section will display **None provided** in your final template.</span></span>

<span data-ttu-id="a69c0-129">Когда вы создаете шаблон, выбрав параметр **Добавить шаблон** , вы можете выбрать, какие значения следует выполнить.</span><span class="sxs-lookup"><span data-stu-id="a69c0-129">When you create a template by selecting the **Add a template** option, you can choose which values to complete.</span></span> <span data-ttu-id="a69c0-130">Все, что остается пустым, будет отображаться в шаблоне как **нет** .</span><span class="sxs-lookup"><span data-stu-id="a69c0-130">Anything that is left blank will appear as **None provided** in the template.</span></span>

## <a name="use-a-template-to-add-a-user"></a><span data-ttu-id="a69c0-131">Использование шаблона для добавления пользователя</span><span class="sxs-lookup"><span data-stu-id="a69c0-131">Use a template to add a user</span></span>

<span data-ttu-id="a69c0-132">Чтобы использовать существующий шаблон для добавления пользователя:</span><span class="sxs-lookup"><span data-stu-id="a69c0-132">To use an existing template to add a user:</span></span>

1. <span data-ttu-id="a69c0-133">В центре администрирования выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a69c0-133">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="a69c0-134">Выберите **шаблоны пользователя**, а затем выберите шаблон из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="a69c0-134">Select **User templates**, and then select a template from the drop-down list.</span></span> <span data-ttu-id="a69c0-135">(Список будет содержать только созданные вами шаблоны, а не созданные другими администраторами.)</span><span class="sxs-lookup"><span data-stu-id="a69c0-135">(The list will contain only the templates that you created, not those created by other admins.)</span></span>

 > [!NOTE]
 > <span data-ttu-id="a69c0-136">Вы также можете использовать шаблон, чтобы добавить пользователя, выбрав **шаблоны** > пользователя,**Управление шаблонами**, выбрав шаблон и выбрав **использовать шаблон**.</span><span class="sxs-lookup"><span data-stu-id="a69c0-136">You can also use a template to add a user by selecting **User templates** > **Manage templates**, selecting a template, and then selecting **Use template**.</span></span>

3. <span data-ttu-id="a69c0-137">Выполните действия, чтобы создать пользователя на основе выбранного шаблона.</span><span class="sxs-lookup"><span data-stu-id="a69c0-137">Follow the steps to create a user from the template you selected.</span></span>

> [!NOTE]
> <span data-ttu-id="a69c0-138">Если у вас не хватает лицензий для добавляемого пользователя, а сведения об оплате доступны, мы будем пытаться приобретать другую лицензию, используя ваши сведения об оплате.</span><span class="sxs-lookup"><span data-stu-id="a69c0-138">If you have insufficient licenses available for a user that you add, and your payment information is available, we will attempt to purchase another license using your existing payment information.</span></span> <span data-ttu-id="a69c0-139">Если сведения об оплате недоступны, пользователь будет создан в качестве нелицензированного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a69c0-139">If your payment information is unavailable, the user will be created as an unlicensed user.</span></span>

## <a name="manage-templates"></a><span data-ttu-id="a69c0-140">Управление шаблонами</span><span class="sxs-lookup"><span data-stu-id="a69c0-140">Manage templates</span></span>

<span data-ttu-id="a69c0-141">Вы можете легко удалить шаблоны, которые больше не нужны, и добавить новые.</span><span class="sxs-lookup"><span data-stu-id="a69c0-141">You can easily delete templates you no longer need and add new ones.</span></span> <span data-ttu-id="a69c0-142">Чтобы удалить шаблон, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a69c0-142">To delete a template:</span></span>

1. <span data-ttu-id="a69c0-143">В центре администрирования выберите пункт **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a69c0-143">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="a69c0-144">Выберите **шаблоны**, а затем в раскрывающемся списке выберите пункт **Управление шаблонами** .</span><span class="sxs-lookup"><span data-stu-id="a69c0-144">Select **Templates**, and then select **Manage templates** from the drop-down list.</span></span>

3. <span data-ttu-id="a69c0-145">Появится список шаблонов.</span><span class="sxs-lookup"><span data-stu-id="a69c0-145">A list of templates will appear.</span></span> <span data-ttu-id="a69c0-146">Вы можете удалить шаблон, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a69c0-146">You can delete a template by doing any of the following:</span></span>
    - <span data-ttu-id="a69c0-147">Выберите один или несколько шаблонов, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a69c0-147">Select one or more templates, and then select **Delete**.</span></span> 
    - <span data-ttu-id="a69c0-148">Выберите три точки справа от имени шаблона, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a69c0-148">Select the three dots to the right of the template name, and then select **Delete**.</span></span>
    - <span data-ttu-id="a69c0-149">Выберите имя шаблона.</span><span class="sxs-lookup"><span data-stu-id="a69c0-149">Select the template name.</span></span> <span data-ttu-id="a69c0-150">Когда в правой части экрана отобразятся сведения о шаблоне, выберите команду **удалить шаблон**.</span><span class="sxs-lookup"><span data-stu-id="a69c0-150">When the template details appear on the right side of your screen, select **Delete template**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a69c0-151">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a69c0-151">Related articles</span></span>

[<span data-ttu-id="a69c0-152">Добавление пользователей по отдельности или с пакетом в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a69c0-152">Add users individually or in bulk to Microsoft 365</span></span>](add-users.md)

[<span data-ttu-id="a69c0-153">Удаление бывшего сотрудника из Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a69c0-153">Remove a former employee from Microsoft 365</span></span>](remove-former-employee.md)
  
