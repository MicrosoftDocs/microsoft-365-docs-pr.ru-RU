---
title: Шаблоны уведомлений об управлении рисками внутри организации
description: Узнайте о шаблонах уведомлений об управлении рисками в Microsoft 365
keywords: Microsoft 365, управление рисками внутри организации, управление рисками, соответствие требованиям
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
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="fe7fd-104">Шаблоны уведомлений об управлении рисками внутри организации</span><span class="sxs-lookup"><span data-stu-id="fe7fd-104">Insider risk management notice templates</span></span>

<span data-ttu-id="fe7fd-105">Шаблоны уведомлений об управлении рисками внутри организации позволяют отправлять сообщения электронной почты пользователям, когда их действия создают соответствие политике и оповещение.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="fe7fd-106">В большинстве случаев действия пользователей, которые создают оповещения, являются результатом ошибок или непреднамеренных действий без злонамеренного действия.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="fe7fd-107">Уведомления служат простым напоминанием пользователям о том, что нужно быть более осторожными, предоставлять ссылки на информацию для обновления или ресурсов корпоративной политики.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="fe7fd-108">Уведомления могут быть важной частью внутренней программы обучения обеспечению соответствия требованиям и могут помочь создать задокументированный след аудита для пользователей с повторяющимися действиями по рискам.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="fe7fd-109">Создайте шаблоны уведомлений, если вы хотите отправить пользователям уведомление с напоминанием о совпадениях политик в процессе решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="fe7fd-110">Уведомления можно отправлять только на адрес электронной почты пользователя, связанный с проверяемой оповещением.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="fe7fd-111">При выборе шаблона уведомления для применения к совпадению с политикой можно принять значения полей, определенные в шаблоне, или переопределить поля по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="fe7fd-112">Панель мониторинга шаблонов уведомлений</span><span class="sxs-lookup"><span data-stu-id="fe7fd-112">Notice templates dashboard</span></span>

<span data-ttu-id="fe7fd-113">Панель **мониторинга шаблонов** уведомлений отображает список настроенных шаблонов уведомлений и позволяет создавать новые шаблоны уведомлений.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="fe7fd-114">Шаблоны уведомлений перечислены в обратном порядке, а самый последний шаблон уведомлений указан первым.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Панель мониторинга шаблонов уведомлений об управлении рисками для оценки рисков](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="fe7fd-116">HTML для уведомлений</span><span class="sxs-lookup"><span data-stu-id="fe7fd-116">HTML for notices</span></span>

<span data-ttu-id="fe7fd-117">Если вы хотите создать не просто текстовое сообщение электронной почты для уведомлений, вы можете создать более подробное сообщение с помощью HTML-кода в поле текста сообщения шаблона уведомления.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="fe7fd-118">В следующем примере предоставляется формат основного тела сообщения для базового шаблона уведомлений электронной почты на основе HTML:</span><span class="sxs-lookup"><span data-stu-id="fe7fd-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

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
> <span data-ttu-id="fe7fd-119">Реализация атрибута HTML href в шаблонах уведомлений об управлении рисками внутри организации в настоящее время поддерживает только одиночные кавычка вместо двойных кавычках для ссылок на URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="fe7fd-120">Создание шаблона уведомления</span><span class="sxs-lookup"><span data-stu-id="fe7fd-120">Create a new notice template</span></span>

<span data-ttu-id="fe7fd-121">Чтобы создать новый шаблон уведомлений об управлении рисками  внутри организации, используйте мастер уведомлений в решении для управления рисками для программы оценки в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="fe7fd-122">Выполните следующие действия, чтобы создать шаблон уведомления об управлении рисками внутри организации:</span><span class="sxs-lookup"><span data-stu-id="fe7fd-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="fe7fd-123">В Центре [соответствия требованиям Microsoft 365](https://compliance.microsoft.com)перейдите в центр управления рисками для программы **insider и** выберите вкладку "Шаблоны уведомлений". </span><span class="sxs-lookup"><span data-stu-id="fe7fd-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="fe7fd-124">Выберите **шаблон "Создать уведомление",** чтобы открыть мастер уведомлений.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="fe7fd-125">На странице **"Создание шаблона уведомления"** заполняйте следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fe7fd-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="fe7fd-126">**Имя шаблона:** введите имя уведомления.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="fe7fd-127">Это имя отображается в списке уведомлений на панели мониторинга уведомлений и в списке выбора уведомлений при отправке уведомлений из дела.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="fe7fd-128">**Send from**: Enter the sender email address for the notice.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="fe7fd-129">Этот адрес будет отображаться в поле **"От:"** во всех уведомлениях, отправляемых пользователям, если они не были изменены при отправке уведомления из дела.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="fe7fd-130">**Поля "Ск"** и "Ск": необязательные пользователи или группы, которые должны быть уведомлены о совпадении политики, выбранные в Active Directory для подписки.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="fe7fd-131">**Тема:** сведения, которые появляются в строке темы сообщения, поддерживают текстовые символы.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="fe7fd-132">**Текст сообщения:** сведения, которые появляются в тексте сообщения, поддерживают текстовые или HTML-значения.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="fe7fd-133">Выберите **"Создать",** чтобы создать  и сохранить шаблон уведомлений, или выберите "Отмена" для закрытия без сохранения шаблона уведомления.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="fe7fd-134">Обновление шаблона уведомления</span><span class="sxs-lookup"><span data-stu-id="fe7fd-134">Update a notice template</span></span>

<span data-ttu-id="fe7fd-135">Чтобы обновить существующий шаблон уведомления об управлении рисками внутри организации, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="fe7fd-136">В Центре [соответствия требованиям Microsoft 365](https://compliance.microsoft.com)перейдите в центр управления рисками для программы **insider и** выберите вкладку "Шаблоны уведомлений". </span><span class="sxs-lookup"><span data-stu-id="fe7fd-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="fe7fd-137">На панели мониторинга уведомлений выберите шаблон уведомлений, который необходимо управлять.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="fe7fd-138">На странице сведений об уведомлении выберите **"Изменить"**</span><span class="sxs-lookup"><span data-stu-id="fe7fd-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="fe7fd-139">На странице **"Изменение"** можно изменить следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fe7fd-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="fe7fd-140">**Имя шаблона:** введите новое имя уведомления.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="fe7fd-141">Это имя отображается в списке уведомлений на панели мониторинга уведомлений и в списке выбора уведомлений при отправке уведомлений из дела.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="fe7fd-142">**Send from**: Update the sender email address for the notice.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="fe7fd-143">Этот адрес будет отображаться в поле **"От:"** во всех уведомлениях, отправляемых пользователям, если они не были изменены при отправке уведомления из дела.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="fe7fd-144">**Поля "Ск"** и "Ск": обновите необязательных пользователей или группы, чтобы они были уведомлены о совпадении с политикой, выбранной в Active Directory для подписки.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="fe7fd-145">**Тема:** обновление сведений, которые появляются в строке темы сообщения, поддерживает текстовые символы.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="fe7fd-146">**Текст сообщения:** обновляются сведения, которые появляются в тексте сообщения, поддерживаются текстовые или HTML-значения.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="fe7fd-147">Выберите **"Сохранить",** чтобы обновить  и сохранить уведомление, или "Отмена" для закрытия без сохранения шаблона уведомления.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="fe7fd-148">Удаление шаблона уведомления</span><span class="sxs-lookup"><span data-stu-id="fe7fd-148">Delete a notice template</span></span>

<span data-ttu-id="fe7fd-149">Чтобы удалить существующий шаблон уведомления об управлении рисками внутри организации, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="fe7fd-150">В Центре [соответствия требованиям Microsoft 365](https://compliance.microsoft.com)перейдите в центр управления рисками для программы **insider и** выберите вкладку "Шаблоны уведомлений". </span><span class="sxs-lookup"><span data-stu-id="fe7fd-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="fe7fd-151">На панели мониторинга уведомлений выберите шаблон уведомлений, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="fe7fd-152">Выберите **значок "Удалить"** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="fe7fd-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="fe7fd-153">Чтобы удалить шаблон уведомления, выберите **"Да"** в диалоговом оке "Удалить".</span><span class="sxs-lookup"><span data-stu-id="fe7fd-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="fe7fd-154">Чтобы отменить удаление, выберите **"Отмена".**</span><span class="sxs-lookup"><span data-stu-id="fe7fd-154">To cancel the deletion, select **Cancel**.</span></span>
