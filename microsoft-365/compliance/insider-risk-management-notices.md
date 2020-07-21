---
title: Шаблоны уведомлений об управлении рисками для участников
description: Сведения о шаблонах уведомлений об управлении рисками в Microsoft 365
keywords: Microsoft 365, управление рисками для оценки, управление рисками, соответствие требованиям
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 0211eefe3c4a946bbaa4ad4c8c66e5df7b37091e
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199496"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="02a50-104">Шаблоны уведомлений об управлении рисками для участников</span><span class="sxs-lookup"><span data-stu-id="02a50-104">Insider risk management notice templates</span></span>

<span data-ttu-id="02a50-105">Шаблоны уведомления об управлении рисками для участников программы предварительной оценки позволяют отправлять сообщения электронной почты пользователям, когда их действия создают соответствующие политики и оповещения.</span><span class="sxs-lookup"><span data-stu-id="02a50-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="02a50-106">В большинстве случаев действия пользователя, создающие оповещения, являются результатом ошибок или случайных действий без некорректного намерения.</span><span class="sxs-lookup"><span data-stu-id="02a50-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="02a50-107">Уведомления являются простыми напоминаниями для пользователей, которые могут быть более осторожными, чтобы предоставить ссылки на сведения о процессе обновления или в корпоративные ресурсы политики.</span><span class="sxs-lookup"><span data-stu-id="02a50-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="02a50-108">Уведомления могут быть важной частью программы обучения по внутренней совместимости и могут помочь создать документированный журнал аудита для пользователей с повторяющимися действиями по рискам.</span><span class="sxs-lookup"><span data-stu-id="02a50-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="02a50-109">Создайте шаблоны примечаний, если вы хотите отправить пользователям уведомление о соответствии политики по электронной почте в рамках процесса разрешения проблем.</span><span class="sxs-lookup"><span data-stu-id="02a50-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="02a50-110">Уведомления можно отправлять только на адрес электронной почты пользователя, связанный с конкретным проверяемым предупреждением.</span><span class="sxs-lookup"><span data-stu-id="02a50-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="02a50-111">При выборе шаблона уведомления, применяемого к соответствию политики, можно выбрать, принимать ли значения полей, определенные в шаблоне, или заменять поля нужным образом.</span><span class="sxs-lookup"><span data-stu-id="02a50-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="02a50-112">Панель мониторинга шаблонов уведомлений</span><span class="sxs-lookup"><span data-stu-id="02a50-112">Notice templates dashboard</span></span>

<span data-ttu-id="02a50-113">**Панель мониторинга шаблонов уведомлений** отображает список настроенных шаблонов уведомлений и позволяет создавать новые шаблоны оповещений.</span><span class="sxs-lookup"><span data-stu-id="02a50-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="02a50-114">Шаблоны примечаний указаны в обратном порядке по дате с последним шаблоном уведомлений, указанным в списке первым.</span><span class="sxs-lookup"><span data-stu-id="02a50-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Панель мониторинга шаблона уведомления об управлении рисками для участников](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="02a50-116">HTML-код уведомлений</span><span class="sxs-lookup"><span data-stu-id="02a50-116">HTML for notices</span></span>

<span data-ttu-id="02a50-117">Если вы хотите создать больше простого текстового сообщения электронной почты для уведомлений, можно создать более подробное сообщение с помощью HTML в поле текст сообщения шаблона уведомления.</span><span class="sxs-lookup"><span data-stu-id="02a50-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="02a50-118">В следующем примере представлен формат текста сообщения для базового шаблона уведомления электронной почты на основе HTML:</span><span class="sxs-lookup"><span data-stu-id="02a50-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

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
> <span data-ttu-id="02a50-119">Реализация атрибута href в HTML в шаблонах уведомлений "Управление рисками" в настоящее время поддерживаются только одиночные кавычки вместо двойных кавычек для ссылок URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="02a50-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="02a50-120">Создание нового шаблона уведомления</span><span class="sxs-lookup"><span data-stu-id="02a50-120">Create a new notice template</span></span>

<span data-ttu-id="02a50-121">Чтобы создать новый шаблон уведомления об управлении рисками для оценки, вы будете использовать мастер уведомлений в решении по **управлению рисками** в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02a50-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="02a50-122">Выполните указанные ниже действия, чтобы создать новый шаблон уведомления об управлении рисками для оценки.</span><span class="sxs-lookup"><span data-stu-id="02a50-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="02a50-123">В [центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com)перейдите к разделу **Управление рисками для оценки** и перейдите на вкладку **шаблоны зауведомлений** .</span><span class="sxs-lookup"><span data-stu-id="02a50-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="02a50-124">Выберите **создать шаблон уведомления** , чтобы открыть мастер оповещений.</span><span class="sxs-lookup"><span data-stu-id="02a50-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="02a50-125">На странице **Создание нового шаблона уведомления** заполните следующие поля:</span><span class="sxs-lookup"><span data-stu-id="02a50-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="02a50-126">**Имя шаблона**: введите понятное имя для уведомления.</span><span class="sxs-lookup"><span data-stu-id="02a50-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="02a50-127">Это имя отображается в списке уведомлений на панели мониторинга уведомлений и в списке выбора уведомлений при отправке уведомлений из случая.</span><span class="sxs-lookup"><span data-stu-id="02a50-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="02a50-128">**Отправить от**: введите адрес электронной почты отправителя для уведомления.</span><span class="sxs-lookup"><span data-stu-id="02a50-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="02a50-129">Этот адрес будет отображаться в поле " **от"** во всех уведомлениях, отправляемых пользователям, если оно не будет изменено при отправке уведомления из случая.</span><span class="sxs-lookup"><span data-stu-id="02a50-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="02a50-130">Поля **CC и BCC** : необязательные пользователи или группы, которые будут уведомлены о соотношении с политикой, выбранном из Active Directory для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="02a50-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="02a50-131">**Тема**: сведения, отображаемые в строке темы сообщения, поддерживают текстовые символы.</span><span class="sxs-lookup"><span data-stu-id="02a50-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="02a50-132">**Текст сообщения**: сведения, отображаемые в тексте сообщения, поддерживает текст или HTML-значения.</span><span class="sxs-lookup"><span data-stu-id="02a50-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="02a50-133">Выберите **создать** , чтобы создать и сохранить шаблон уведомления, или нажмите **кнопку Отмена** , чтобы закрыть окно без сохранения шаблона уведомления.</span><span class="sxs-lookup"><span data-stu-id="02a50-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="02a50-134">Обновление шаблона уведомления</span><span class="sxs-lookup"><span data-stu-id="02a50-134">Update a notice template</span></span>

<span data-ttu-id="02a50-135">Чтобы обновить существующий шаблон уведомления об управлении рисками для оценки безопасности, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="02a50-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="02a50-136">В [центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com)перейдите к разделу **Управление рисками для оценки** и перейдите на вкладку **шаблоны зауведомлений** .</span><span class="sxs-lookup"><span data-stu-id="02a50-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="02a50-137">На панели мониторинга оповещений выберите шаблон уведомления, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="02a50-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="02a50-138">На странице сведения об уведомлении нажмите кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="02a50-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="02a50-139">На странице **редактирования** можно изменить следующие поля:</span><span class="sxs-lookup"><span data-stu-id="02a50-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="02a50-140">**Имя шаблона**: введите новое понятное имя для уведомления.</span><span class="sxs-lookup"><span data-stu-id="02a50-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="02a50-141">Это имя отображается в списке уведомлений на панели мониторинга уведомлений и в списке выбора уведомлений при отправке уведомлений из случая.</span><span class="sxs-lookup"><span data-stu-id="02a50-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="02a50-142">**Отправить от**: обновите адрес электронной почты отправителя для уведомления.</span><span class="sxs-lookup"><span data-stu-id="02a50-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="02a50-143">Этот адрес будет отображаться в поле " **от"** во всех уведомлениях, отправляемых пользователям, если оно не будет изменено при отправке уведомления из случая.</span><span class="sxs-lookup"><span data-stu-id="02a50-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="02a50-144">Поля **"копия" и "СК"** : обновление необязательных пользователей или групп для получения уведомления о политике, выбранной в службе каталогов Active Directory для вашей подписки.</span><span class="sxs-lookup"><span data-stu-id="02a50-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="02a50-145">**Тема**: сведения об обновлении, которые отображаются в строке темы сообщения, поддерживают текстовые символы.</span><span class="sxs-lookup"><span data-stu-id="02a50-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="02a50-146">**Текст сообщения**: сведения об обновлении, которые отображаются в тексте сообщения, поддерживают текстовые или HTML-значения.</span><span class="sxs-lookup"><span data-stu-id="02a50-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="02a50-147">Нажмите кнопку **сохранить** , чтобы обновить и сохранить уведомление, или кнопку **Отмена** , чтобы закрыть окно без сохранения шаблона уведомления.</span><span class="sxs-lookup"><span data-stu-id="02a50-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="02a50-148">Удаление шаблона уведомления</span><span class="sxs-lookup"><span data-stu-id="02a50-148">Delete a notice template</span></span>

<span data-ttu-id="02a50-149">Чтобы удалить существующий шаблон уведомления об управлении рисками, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="02a50-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="02a50-150">В [центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com)перейдите к разделу **Управление рисками для оценки** и перейдите на вкладку **шаблоны зауведомлений** .</span><span class="sxs-lookup"><span data-stu-id="02a50-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="02a50-151">На панели мониторинга уведомлений выберите шаблон уведомления, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="02a50-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="02a50-152">Нажмите значок **Удалить** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="02a50-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="02a50-153">Чтобы удалить шаблон уведомления, выберите **Да** в диалоговом окне удаления.</span><span class="sxs-lookup"><span data-stu-id="02a50-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="02a50-154">Чтобы отменить удаление, нажмите **кнопку Отмена**.</span><span class="sxs-lookup"><span data-stu-id="02a50-154">To cancel the deletion, select **Cancel**.</span></span>
