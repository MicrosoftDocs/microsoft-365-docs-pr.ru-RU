---
title: Шаблоны уведомлений об управлении внутренними рисками
description: Узнайте о шаблонах уведомлений об управлении рисками изнутри в Microsoft 365
keywords: Microsoft 365, управление внутренними рисками, управление рисками, соответствие требованиям
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416483"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="42f55-104">Шаблоны уведомлений об управлении внутренними рисками</span><span class="sxs-lookup"><span data-stu-id="42f55-104">Insider risk management notice templates</span></span>

<span data-ttu-id="42f55-105">Шаблоны уведомлений об управлении рисками изнутри позволяют отправлять сообщения электронной почты пользователям, когда их действия создают соответствие политике и оповещение.</span><span class="sxs-lookup"><span data-stu-id="42f55-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="42f55-106">В большинстве случаев действия пользователей, которые создают оповещения, являются результатом ошибок или непреднамеренных действий без злого умысла.</span><span class="sxs-lookup"><span data-stu-id="42f55-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="42f55-107">Уведомления служат простым напоминанием пользователям о том, что нужно быть более осторожными, предоставлять ссылки на информацию для подготовки кадров или на ресурсы корпоративной политики.</span><span class="sxs-lookup"><span data-stu-id="42f55-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="42f55-108">Уведомления могут быть важной частью вашей внутренней программы подготовки по соблюдению требований и могут помочь создать документированный след аудита для пользователей с повторяющимися действиями риска.</span><span class="sxs-lookup"><span data-stu-id="42f55-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="42f55-109">Создайте шаблоны уведомлений, если вы хотите отправить пользователям уведомление о напоминаниях электронной почты для совпадений политик в рамках процесса разрешения проблем.</span><span class="sxs-lookup"><span data-stu-id="42f55-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="42f55-110">Уведомления можно отправлять только на адрес электронной почты пользователя, связанный с определенным оповещением, которое будет рассмотрено.</span><span class="sxs-lookup"><span data-stu-id="42f55-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="42f55-111">При выборе шаблона уведомлений для применения к матчу политики можно принять значения поля, определенные в шаблоне, или переписать поля по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="42f55-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="42f55-112">Панель мониторинга шаблонов уведомлений</span><span class="sxs-lookup"><span data-stu-id="42f55-112">Notice templates dashboard</span></span>

<span data-ttu-id="42f55-113">**Панель инструментов шаблонов уведомлений** отображает список настроенных шаблонов уведомлений и позволяет создавать новые шаблоны уведомлений.</span><span class="sxs-lookup"><span data-stu-id="42f55-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="42f55-114">Шаблоны уведомлений перечислены в обратном порядке дат, причем самый последний шаблон уведомления указан первым.</span><span class="sxs-lookup"><span data-stu-id="42f55-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Панель шаблонов уведомлений об управлении рисками изнутри](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="42f55-116">HTML для уведомлений</span><span class="sxs-lookup"><span data-stu-id="42f55-116">HTML for notices</span></span>

<span data-ttu-id="42f55-117">Если вы хотите создать не просто текстовое сообщение электронной почты для уведомлений, вы можете создать более подробное сообщение с помощью HTML в поле тела сообщений шаблона уведомлений.</span><span class="sxs-lookup"><span data-stu-id="42f55-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="42f55-118">В следующем примере содержится формат тела сообщения для базового шаблона уведомлений электронной почты на основе HTML:</span><span class="sxs-lookup"><span data-stu-id="42f55-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="42f55-119">Реализация атрибута HTML href в шаблонах уведомлений об управлении рисками в настоящее время поддерживает только отдельные кавычка, а не двойные кавычка для ссылок на URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="42f55-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="42f55-120">Создание нового шаблона уведомлений</span><span class="sxs-lookup"><span data-stu-id="42f55-120">Create a new notice template</span></span>

<span data-ttu-id="42f55-121">Чтобы создать новый шаблон уведомлений об управлении рисками изнутри, вы будете использовать мастер уведомлений в решении по управлению рисками **insider** в центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="42f55-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="42f55-122">Выполните следующие действия, чтобы создать новый шаблон уведомления об управлении рисками для инсайдеров:</span><span class="sxs-lookup"><span data-stu-id="42f55-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="42f55-123">В центре [Microsoft 365 соответствия](https://compliance.microsoft.com)требованиям перейдите к управлению рисками **insider** и выберите вкладку **Шаблоны** Уведомлений.</span><span class="sxs-lookup"><span data-stu-id="42f55-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="42f55-124">Выберите **шаблон Create notice для** открытия мастера уведомлений.</span><span class="sxs-lookup"><span data-stu-id="42f55-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="42f55-125">На странице **Создание нового шаблона уведомлений** выполните следующие поля:</span><span class="sxs-lookup"><span data-stu-id="42f55-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="42f55-126">**Имя шаблона.** Введите удобное имя для уведомления.</span><span class="sxs-lookup"><span data-stu-id="42f55-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="42f55-127">Это имя отображается в списке уведомлений на панели мониторинга уведомлений и в списке выбора уведомлений при отправке уведомлений из дела.</span><span class="sxs-lookup"><span data-stu-id="42f55-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="42f55-128">**Отправка:** Введите адрес электронной почты отправитель для уведомления.</span><span class="sxs-lookup"><span data-stu-id="42f55-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="42f55-129">Этот адрес будет отображаться в **поле From:** во всех уведомлениях, отправленных пользователям, если они не изменены при отправке уведомления из дела.</span><span class="sxs-lookup"><span data-stu-id="42f55-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="42f55-130">**Поля Cc и Bcc:** необязательные пользователи или группы, которые будут уведомлены о совпадении политик, выбранных из Active Directory для подписки.</span><span class="sxs-lookup"><span data-stu-id="42f55-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="42f55-131">**Тема.** Сведения, которые появляются в строке темы сообщения, поддерживают текстовые символы.</span><span class="sxs-lookup"><span data-stu-id="42f55-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="42f55-132">**Текст сообщения.** Сведения, которые появляются в теле сообщения, поддерживают текстовые или HTML-значения.</span><span class="sxs-lookup"><span data-stu-id="42f55-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="42f55-133">Выберите **Создать** для создания и сохранения шаблона уведомлений или выберите **Отмена** закрытия без сохранения шаблона уведомлений.</span><span class="sxs-lookup"><span data-stu-id="42f55-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="42f55-134">Обновление шаблона уведомлений</span><span class="sxs-lookup"><span data-stu-id="42f55-134">Update a notice template</span></span>

<span data-ttu-id="42f55-135">Чтобы обновить существующий шаблон уведомления об управлении рисками, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="42f55-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="42f55-136">В центре [Microsoft 365 соответствия](https://compliance.microsoft.com)требованиям перейдите к управлению рисками **insider** и выберите вкладку **Шаблоны** Уведомлений.</span><span class="sxs-lookup"><span data-stu-id="42f55-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="42f55-137">На панели мониторинга уведомлений выберите шаблон уведомлений, который необходимо управлять.</span><span class="sxs-lookup"><span data-stu-id="42f55-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="42f55-138">На странице сведения об уведомлении выберите **Изменить**</span><span class="sxs-lookup"><span data-stu-id="42f55-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="42f55-139">На странице **Редактирование** можно изменить следующие поля:</span><span class="sxs-lookup"><span data-stu-id="42f55-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="42f55-140">**Имя шаблона.** Введите новое удобное имя для уведомления.</span><span class="sxs-lookup"><span data-stu-id="42f55-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="42f55-141">Это имя отображается в списке уведомлений на панели мониторинга уведомлений и в списке выбора уведомлений при отправке уведомлений из дела.</span><span class="sxs-lookup"><span data-stu-id="42f55-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="42f55-142">**Отправка** из: Обновление адреса электронной почты отправитель для уведомления.</span><span class="sxs-lookup"><span data-stu-id="42f55-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="42f55-143">Этот адрес будет отображаться в **поле From:** во всех уведомлениях, отправленных пользователям, если они не изменены при отправке уведомления из дела.</span><span class="sxs-lookup"><span data-stu-id="42f55-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="42f55-144">**Поля Cc и Bcc.** Обновление необязательных пользователей или групп, которые будут уведомлены о совпадении политик, выбранных из Active Directory для подписки.</span><span class="sxs-lookup"><span data-stu-id="42f55-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="42f55-145">**Subject.** Обновление сведений, которые появляются в строке темы сообщения, поддерживает текстовые символы.</span><span class="sxs-lookup"><span data-stu-id="42f55-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="42f55-146">**Текст сообщения.** Обновление сведений, которые появляются в текстовом тексте, поддерживает текстовые или HTML-значения.</span><span class="sxs-lookup"><span data-stu-id="42f55-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="42f55-147">Выберите **Сохранить** для обновления и сохранения уведомления или выберите **Отмена** закрытия без сохранения шаблона уведомления.</span><span class="sxs-lookup"><span data-stu-id="42f55-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="42f55-148">Удаление шаблона уведомлений</span><span class="sxs-lookup"><span data-stu-id="42f55-148">Delete a notice template</span></span>

<span data-ttu-id="42f55-149">Чтобы удалить существующий шаблон уведомления об управлении рисками, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="42f55-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="42f55-150">В центре [Microsoft 365 соответствия](https://compliance.microsoft.com)требованиям перейдите к управлению рисками **insider** и выберите вкладку **Шаблоны** Уведомлений.</span><span class="sxs-lookup"><span data-stu-id="42f55-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="42f55-151">На панели мониторинга уведомлений выберите шаблон уведомлений, который необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="42f55-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="42f55-152">Выберите **значок Delete** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="42f55-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="42f55-153">Чтобы удалить шаблон уведомления, выберите **Да** в диалоговом окте удалить.</span><span class="sxs-lookup"><span data-stu-id="42f55-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="42f55-154">Чтобы отменить удаление, выберите **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="42f55-154">To cancel the deletion, select **Cancel**.</span></span>
