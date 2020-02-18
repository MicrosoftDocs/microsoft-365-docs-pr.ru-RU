---
title: Поиск и освобождение сообщений из карантина от имени пользователя в Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: 'Пользователи Office 365 могут управлять сообщениями в карантине двумя способами: реагируя на уведомления о спаме (если ваш администратор настроил эту возможность) или с помощью функции карантина спама в Центре безопасности и соответствия требованиям.'
ms.openlocfilehash: 277af18d2061e8bd13386ab96e37d982d68e0b52
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599296"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="892fb-103">Поиск и освобождение сообщений из карантина от имени пользователя в Office 365</span><span class="sxs-lookup"><span data-stu-id="892fb-103">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="892fb-104">Пользователи Office 365 могут управлять сообщениями, отправленными в карантин, двумя способами: [реагируя на уведомления о спаме напрямую](use-spam-notifications-to-release-and-report-quarantined-messages.md) (если администратор настроил эту возможность) или с помощью Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="892fb-104">As an Office 365 user, you can manage messages that were sent to quarantine instead of sent to you in one of two ways: by [responding to spam notifications sent to you directly](use-spam-notifications-to-release-and-report-quarantined-messages.md) (if your admin has set this up), or by using the Security &amp; Compliance Center.</span></span>

> [!NOTE]
> <span data-ttu-id="892fb-105">Администраторы могут [управлять сообщениями в карантине](manage-quarantined-messages-and-files.md) от имени других пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="892fb-105">If you're an admin, you can [manage quarantined messages](manage-quarantined-messages-and-files.md) for other people in your organization.</span></span>

## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a><span data-ttu-id="892fb-106">Просмотр сообщений, отправленных в карантин, а не вам</span><span class="sxs-lookup"><span data-stu-id="892fb-106">View messages that were sent to quarantine instead of to you</span></span>

1. <span data-ttu-id="892fb-107">Войдите в Office 365 и [откройте Центр безопасности и соответствия требованиям](../../compliance/go-to-the-securitycompliance-center.md), используя рабочую или учебную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="892fb-107">Sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) using your work or school account.</span></span>

2. <span data-ttu-id="892fb-108">В левой части экрана разверните список **Управление угрозами**, выберите **Проверка**, а затем нажмите плитку **Карантин**.</span><span class="sxs-lookup"><span data-stu-id="892fb-108">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

    > [!TIP]
    > <span data-ttu-id="892fb-109">Чтобы перейти напрямую к странице **Карантин** в Центре безопасности и соответствия требованиям, используйте следующий URL-адрес: [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="892fb-109">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

<span data-ttu-id="892fb-110">По умолчанию в Центре безопасности и соответствия требованиям отображаются все сообщения, которые были помещены в карантин как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="892fb-110">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam.</span></span> <span data-ttu-id="892fb-111">Они отсортированы по **дате** получения от новых к старым.</span><span class="sxs-lookup"><span data-stu-id="892fb-111">The messages are sorted from newest to oldest based on the **Date** the message was received.</span></span> <span data-ttu-id="892fb-112">Для каждого сообщения также указываются **отправитель**, **тема** и **срок действия**.</span><span class="sxs-lookup"><span data-stu-id="892fb-112">**Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message.</span></span> <span data-ttu-id="892fb-113">Вы можете отсортировать сообщения по полю, щелкнув его заголовок. Чтобы изменить порядок сортировки, щелкните заголовок столбца еще раз.</span><span class="sxs-lookup"><span data-stu-id="892fb-113">You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span>

<span data-ttu-id="892fb-114">Можно просмотреть список всех сообщений в карантине или найти определенные сообщения с помощью фильтра.</span><span class="sxs-lookup"><span data-stu-id="892fb-114">You can view a list of all quarantined messages, or you can search for specific messages by filtering.</span></span> <span data-ttu-id="892fb-115">Массовые операции можно выполнять не более чем со 100 элементами, поэтому если результатов больше, сократите их число с помощью фильтрации.</span><span class="sxs-lookup"><span data-stu-id="892fb-115">You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that.</span></span> <span data-ttu-id="892fb-116">Вы можете быстро отфильтровать сообщения по одной причине помещения в карантин, выбрав вариант из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="892fb-116">You can quickly filter messages for a single quarantine reason by choosing an option from the drop-down list.</span></span> <span data-ttu-id="892fb-117">Варианты:</span><span class="sxs-lookup"><span data-stu-id="892fb-117">Options include:</span></span>

- <span data-ttu-id="892fb-118">сообщения, которые считаются спамом</span><span class="sxs-lookup"><span data-stu-id="892fb-118">Mail identified as spam.</span></span> <span data-ttu-id="892fb-119">(эти сообщения отображаются по умолчанию);</span><span class="sxs-lookup"><span data-stu-id="892fb-119">These quarantined messages are shown by default.</span></span>

- <span data-ttu-id="892fb-120">сообщения, которые считаются массовыми рассылками.</span><span class="sxs-lookup"><span data-stu-id="892fb-120">Mail identified as bulk mail.</span></span>

<span data-ttu-id="892fb-121">Когда вы найдете нужное сообщение в карантине, дважды щелкните его, чтобы просмотреть сведения о нем и выполнить те или иные действия.</span><span class="sxs-lookup"><span data-stu-id="892fb-121">After you find a specific quarantined message, click the message to view details about it, and take actions.</span></span> <span data-ttu-id="892fb-122">Вы можете освободить сообщение в свой почтовый ящик, просмотреть или скачать сообщение либо сразу удалить его из карантина.</span><span class="sxs-lookup"><span data-stu-id="892fb-122">You can release the message to your mailbox, preview the message, download the message, or delete the message from quarantine immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="892fb-123">Для работы с сообщениями других пользователей, помещенными в карантин, требуются разрешения администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="892fb-123">You must have admin permissions in Office 365 to work with quarantined messages that were sent to other users.</span></span>

## <a name="to-filter-and-find-quarantined-messages"></a><span data-ttu-id="892fb-124">Фильтрация и поиск сообщений в карантине</span><span class="sxs-lookup"><span data-stu-id="892fb-124">To filter and find quarantined messages</span></span>

<span data-ttu-id="892fb-125">Если у вас в карантине много элементов, вы можете сократить их количество до удобного набора, отфильтровав их.</span><span class="sxs-lookup"><span data-stu-id="892fb-125">If you have a lot of quarantined items, you can reduce the number to a manageable set by filtering them.</span></span>

1. <span data-ttu-id="892fb-126">На странице **Карантин** выберите, какие сообщения в карантине вы хотите просмотреть: **спам** или **массовые рассылки**.</span><span class="sxs-lookup"><span data-stu-id="892fb-126">On the **Quarantine** page, choose whether you want to view **spam** or **bulk** quarantined messages.</span></span>

2. <span data-ttu-id="892fb-127">В поле **Сортировать результаты по** выберите сочетание условий, задав соответствующие фильтры (при этом не допускается использование подстановочных знаков).</span><span class="sxs-lookup"><span data-stu-id="892fb-127">Under **Sort results by**, choose any combination of conditions by setting the appropriate filter or filters (you can't use wildcards at this time).</span></span> <span data-ttu-id="892fb-128">Вы можете выбрать указанные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="892fb-128">There are several conditions you can choose, including the following:</span></span>

   - <span data-ttu-id="892fb-129">**ИД сообщения**. Вы можете найти определенное сообщение, если вам известен его идентификатор.</span><span class="sxs-lookup"><span data-stu-id="892fb-129">**Message ID**: Use this to select a specific message when you know the message ID.</span></span>

     <span data-ttu-id="892fb-130">Например, если определенное сообщение было адресовано пользователю в вашей организации или отправлено им, но не достигло адресата, вы можете найти его с помощью трассировки сообщений (см. статью [Трассировка сообщений в Центре безопасности и соответствия требованиям](message-trace-scc.md)).</span><span class="sxs-lookup"><span data-stu-id="892fb-130">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Message trace in the Security & Compliance Center](message-trace-scc.md)).</span></span> <span data-ttu-id="892fb-131">Если вы обнаружили, что сообщение было отправлено в карантин, потому что сработало правило потока обработки почты или оно было определено как нежелательное, вы можете легко найти это сообщение в карантине, указав его идентификатор.</span><span class="sxs-lookup"><span data-stu-id="892fb-131">If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its Message ID.</span></span> <span data-ttu-id="892fb-132">Не забудьте включить полную строку идентификатора сообщения.</span><span class="sxs-lookup"><span data-stu-id="892fb-132">Be sure to include the full Message ID string.</span></span> <span data-ttu-id="892fb-133">В ней могут быть угловые скобки (\<\>), например:</span><span class="sxs-lookup"><span data-stu-id="892fb-133">This might include angle brackets (\<\>), for example:</span></span>

     `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`

   - <span data-ttu-id="892fb-134">**Адрес электронной почты отправителя**. Позволяет отфильтровать сообщения по адресу отправителя.</span><span class="sxs-lookup"><span data-stu-id="892fb-134">**Sender email address**: Choose to filter by a single sender email address.</span></span>

   - <span data-ttu-id="892fb-135">**Адрес электронной почты получателя**. Позволяет отфильтровать сообщения по адресу получателя.</span><span class="sxs-lookup"><span data-stu-id="892fb-135">**Recipient email address**: Choose to filter by a single recipient email address.</span></span>

   - <span data-ttu-id="892fb-136">**Тема**. Укажите тему нужного сообщения.</span><span class="sxs-lookup"><span data-stu-id="892fb-136">**Subject**: Enter the subject of an email address you want to find.</span></span>

   - <span data-ttu-id="892fb-137">**Диапазон дат**. Вы можете выбрать фильтрацию по дате отправки сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="892fb-137">**Date range**: You can choose to filter by the date the message was sent to quarantine.</span></span> <span data-ttu-id="892fb-138">Можно указать как точную дату, так и диапазон, включая время.</span><span class="sxs-lookup"><span data-stu-id="892fb-138">You can specify the date or a date range, including the time.</span></span>

   - <span data-ttu-id="892fb-139">**Дата окончания срока действия**. Чтобы отфильтровать сообщения по сроку действия, выберите **Расширенный фильтр**.</span><span class="sxs-lookup"><span data-stu-id="892fb-139">**Expiration date**: To filter by expiration date, choose **Advanced filter**.</span></span> <span data-ttu-id="892fb-140">Вы можете выбрать сообщения, которые будут удалены из карантина в течение 24 часов (**Сегодня**), 48 часов (**Следующие 2 дня**), недели (**Следующие 7 дней**) или другого интервала времени.</span><span class="sxs-lookup"><span data-stu-id="892fb-140">You can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="892fb-141">По умолчанию спам и массовые рассылки хранятся в карантине в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="892fb-141">By default, spam and bulk messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="892fb-142">Однако этот период времени можно настраивать, а администратор может задать другой период хранения в карантине.</span><span class="sxs-lookup"><span data-stu-id="892fb-142">However, this time period is configurable and your admin might have set a different quarantine retention period.</span></span> <span data-ttu-id="892fb-143">Сообщения, удаленные службой Office 365 из карантина, невозможно вернуть.</span><span class="sxs-lookup"><span data-stu-id="892fb-143">When Office 365 deletes a message from quarantine, you can't get it back.</span></span>

## <a name="view-details-for-a-specific-message"></a><span data-ttu-id="892fb-144">Просмотр сведений о сообщении</span><span class="sxs-lookup"><span data-stu-id="892fb-144">View details for a specific message</span></span>

<span data-ttu-id="892fb-145">После выбора сообщения в правой части страницы выводится сводка его свойств.</span><span class="sxs-lookup"><span data-stu-id="892fb-145">After you select a message, you'll see a summary of the message properties in a pane on the right side of the page.</span></span>

- <span data-ttu-id="892fb-146">**Идентификатор сообщения**. Уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="892fb-146">**Message ID**: The unique identifier for the message.</span></span>

- <span data-ttu-id="892fb-147">**Адрес отправителя**. Отправитель сообщения.</span><span class="sxs-lookup"><span data-stu-id="892fb-147">**Sender Address**: Who sent the message.</span></span>

- <span data-ttu-id="892fb-148">**Получено**. Дата получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="892fb-148">**Received**: The date the message was received.</span></span>

- <span data-ttu-id="892fb-149">**Тема**. Строка темы сообщения.</span><span class="sxs-lookup"><span data-stu-id="892fb-149">**Subject**: The text of the Subject line in the message.</span></span>

- <span data-ttu-id="892fb-150">**Причина помещения на карантин**. Указывает, как было отмечено сообщение (**Спам** или **Массовая рассылка**).</span><span class="sxs-lookup"><span data-stu-id="892fb-150">**Quarantine reason**: Shows if a message has been identified as **Spam** or **Bulk**.</span></span>

- <span data-ttu-id="892fb-151">**Срок действия истекает**. Дата удаления сообщения из карантина.</span><span class="sxs-lookup"><span data-stu-id="892fb-151">**Expires**: The date when the message will be deleted from quarantine.</span></span>

- <span data-ttu-id="892fb-152">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="892fb-152">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="892fb-153">**Еще не разблокировано для пользователя**. Все электронные адреса (если таковые имеются), для которых сообщение еще не было освобождено.</span><span class="sxs-lookup"><span data-stu-id="892fb-153">**Not yet released to**: All email addresses (if any) to which the message has not been released.</span></span> <span data-ttu-id="892fb-154">Вы можете нажать кнопку **Разблокировать**, чтобы освободить сообщение в свой почтовый ящик (дополнительные сведения см. в следующем разделе).</span><span class="sxs-lookup"><span data-stu-id="892fb-154">You can choose **Release** if you want to release the message to your mailbox (more about releasing messages in the next section).</span></span>

<span data-ttu-id="892fb-155">Вы также можете просмотреть дополнительные сведения о сообщении, выбрав один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="892fb-155">You can get even more details about the message by choosing one of the following options:</span></span>

- <span data-ttu-id="892fb-156">**Просмотр заголовка сообщения**. Позволяет просмотреть текст заголовка.</span><span class="sxs-lookup"><span data-stu-id="892fb-156">**View message header**: Choose this to see the message header text.</span></span> <span data-ttu-id="892fb-157">Для подробного анализа заголовка скопируйте его текст в буфер обмена и выберите **Microsoft Message Header Analyzer**, чтобы открыть анализатор удаленного подключения (если вы не хотите покидать Office 365 для выполнения этой задачи, щелкните эту команду правой кнопкой мыши и выберите пункт "Открыть на новой вкладке").</span><span class="sxs-lookup"><span data-stu-id="892fb-157">To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose Open in a new tab if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="892fb-158">Вставьте заголовок сообщения на страницу в разделе Message Header Analyzer, а затем нажмите "Проанализировать заголовки".</span><span class="sxs-lookup"><span data-stu-id="892fb-158">Paste the message header onto the page in the Message Header Analyzer section, and choose Analyze headers.</span></span>

- <span data-ttu-id="892fb-159">**Предварительный просмотр сообщения**. Позволяет просмотреть неотформатированную или HTML-версию текста сообщения.</span><span class="sxs-lookup"><span data-stu-id="892fb-159">**Preview message**: Lets you see raw or HTML versions of the message body text.</span></span> <span data-ttu-id="892fb-160">В режиме HTML ссылки будут отключены.</span><span class="sxs-lookup"><span data-stu-id="892fb-160">In the HTML view, links are disabled.</span></span>

## <a name="manage-your-quarantined-messages"></a><span data-ttu-id="892fb-161">Управление сообщениями, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="892fb-161">Manage your quarantined messages</span></span>

<span data-ttu-id="892fb-162">После выбора сообщений в карантине с ними можно выполнить несколько действий.</span><span class="sxs-lookup"><span data-stu-id="892fb-162">After you select a message or group of messages, you have several options for managing messages in quarantine.</span></span>

- <span data-ttu-id="892fb-163">Ничего не предпринимать.</span><span class="sxs-lookup"><span data-stu-id="892fb-163">Do nothing.</span></span> <span data-ttu-id="892fb-164">Если ничего не делать, Office 365 автоматически удалит сообщения по истечении срока хранения.</span><span class="sxs-lookup"><span data-stu-id="892fb-164">If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration.</span></span> <span data-ttu-id="892fb-165">Помните, что сообщения, удаленные службой Office 365 из карантина, невозможно вернуть.</span><span class="sxs-lookup"><span data-stu-id="892fb-165">Remember, when Office 365 deletes a message from quarantine, you can't get it back.</span></span>

- <span data-ttu-id="892fb-166">**Разблокировка сообщения**. Освобождение сообщения (или набора сообщений) из карантина, чтобы это сообщение было отправлено в ваш почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="892fb-166">**Release message**: Release a quarantined message (or set of messages) so that the message is sent to your mailbox.</span></span> <span data-ttu-id="892fb-167">Освобождая сообщение, вы можете отправить его в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="892fb-167">When you release a message, you have the option to report the message to Microsoft for analysis.</span></span>

    <span data-ttu-id="892fb-168">Если вы сообщите о письме, ошибочно помещенном в карантин (ложном срабатывании), оно будет отправлено команде анализа спама Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="892fb-168">When you choose to report a message, also called reporting a message as a false positive, the message is reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="892fb-169">Эта команда оценивает и анализирует ложные срабатывания. В зависимости от результатов анализа можно изменить правила фильтрации контента для всей службы, чтобы пропускать такие сообщения.</span><span class="sxs-lookup"><span data-stu-id="892fb-169">The team evaluates and analyzes false positive messages, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow these messages through.</span></span>

- <span data-ttu-id="892fb-170">**Удаление из карантина**. Сообщение сразу удаляется из карантина и не освобождается в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="892fb-170">**Remove from quarantine**: Deletes the message immediately from quarantine without releasing the message to your mailbox.</span></span>
