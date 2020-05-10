---
title: Поиск и разблокирование сообщений, находящихся на карантине, для пользователя
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.custom:
- seo-marvel-apr2020
description: В этой статье рассказывается о том, как просматривать сообщения, помещенные в карантин, и управлять ими в Центре безопасности и соответствия требованиям Microsoft 365.
ms.openlocfilehash: ff6cb3dbf9a0a2010bf792115c53265689873090
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173384"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="76784-103">Поиск и разблокирование сообщений, находящихся на карантине, для пользователя</span><span class="sxs-lookup"><span data-stu-id="76784-103">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="76784-104">На карантине хранятся потенциально опасные или нежелательные сообщения в организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="76784-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="76784-105">Дополнительные сведения см. [В разделе Карантин в Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="76784-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="76784-106">Как пользователь вы можете просмотреть, разблокировать и удалить сообщения, помещенные на карантин, если вы являетесь получателем, а сообщение было помещено на карантин как спам или массовая рассылка.</span><span class="sxs-lookup"><span data-stu-id="76784-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="76784-107">С апреля 2020 г. вы можете просматривать и удалять фишинговые сообщения (не относящиеся к фишингу с высокой вероятностью), помещенные на карантин, если вы являетесь получателем.</span><span class="sxs-lookup"><span data-stu-id="76784-107">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="76784-108">Можно просматривать сообщения, помещенные на карантин, в центре безопасности и соблюдения требований (если администратор настроил этот вариант) в разделе [уведомления о спаме для пользователей](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="76784-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="76784-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="76784-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="76784-110">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="76784-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="76784-111">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="76784-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="76784-112">Администраторы могут настроить продолжительность хранения сообщений в карантине до их окончательного удаления (политики защиты от спама).</span><span class="sxs-lookup"><span data-stu-id="76784-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="76784-113">Сообщения, срок действия которых истек из карантина, невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="76784-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="76784-114">Дополнительные сведения см. в разделе [Настройка политик защиты от спама в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="76784-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="76784-115">Администраторы также могут [включить уведомления о спаме для конечных пользователей](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) в политиках защиты от спама.</span><span class="sxs-lookup"><span data-stu-id="76784-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="76784-116">Пользователи могут освобождать прямо из этих уведомлений помещенные на карантин сообщения, но не сообщения, помещенные на карантин из-за фишинга.</span><span class="sxs-lookup"><span data-stu-id="76784-116">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="76784-117">Дополнительные сведения см. в разделе [Уведомления о спаме для конечных пользователей в Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="76784-117">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="76784-118">Сообщения, которые были помещены в карантин для фишинга с высокой степенью достоверности, вредоносного ПО или по правилам потока почты (также называемым правилами транспорта), доступны только администраторам.</span><span class="sxs-lookup"><span data-stu-id="76784-118">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="76784-119">Фишинговые сообщения могут просматриваться пользователями, но освобождаются только администраторами.</span><span class="sxs-lookup"><span data-stu-id="76784-119">Phish messages can be reviewed by users but only released by admins.</span></span> <span data-ttu-id="76784-120">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="76784-120">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="76784-121">Освободить сообщение и сообщить о ложном срабатывании (о том, что сообщение не является нежелательным) можно только один раз.</span><span class="sxs-lookup"><span data-stu-id="76784-121">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="76784-122">Просмотр сообщений на карантине</span><span class="sxs-lookup"><span data-stu-id="76784-122">View your quarantined messages</span></span>

1. <span data-ttu-id="76784-123">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="76784-123">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="76784-124">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="76784-124">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="76784-125">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="76784-125">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="76784-126">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="76784-126">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="76784-127">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="76784-127">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="76784-128">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="76784-128">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="76784-129">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="76784-129">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="76784-130">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="76784-130">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="76784-131">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="76784-131">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="76784-132">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="76784-132">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="76784-133">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="76784-133">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="76784-134">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="76784-134">**Recipient**</span></span>

   - <span data-ttu-id="76784-135">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="76784-135">**Message ID**</span></span>

   - <span data-ttu-id="76784-136">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="76784-136">**Policy name**</span></span>

   - <span data-ttu-id="76784-137">**Размер**</span><span class="sxs-lookup"><span data-stu-id="76784-137">**Size**</span></span>

   - <span data-ttu-id="76784-138">**Направление**</span><span class="sxs-lookup"><span data-stu-id="76784-138">**Direction**</span></span>

   <span data-ttu-id="76784-139">Когда все будет готово, нажмите кнопку **сохранить**или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="76784-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="76784-140">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="76784-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="76784-141">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="76784-141">The available filters are:</span></span>

   - <span data-ttu-id="76784-142">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="76784-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="76784-143">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="76784-143">**Today**</span></span>

     - <span data-ttu-id="76784-144">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="76784-144">**Next 2 days**</span></span>

     - <span data-ttu-id="76784-145">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="76784-145">**Next 7 days**</span></span>

     - <span data-ttu-id="76784-146">**Настраиваемые**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="76784-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="76784-147">**Время получения**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="76784-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="76784-148">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="76784-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="76784-149">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="76784-149">**Bulk**</span></span>

     - <span data-ttu-id="76784-150">**Спам**</span><span class="sxs-lookup"><span data-stu-id="76784-150">**Spam**</span></span>

     - <span data-ttu-id="76784-151">**Фиш** (по состоянию на апрель 2020 г.)</span><span class="sxs-lookup"><span data-stu-id="76784-151">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="76784-152">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="76784-152">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="76784-153">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="76784-153">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="76784-154">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="76784-154">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="76784-155">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="76784-155">Wildcards aren't supported.</span></span> <span data-ttu-id="76784-156">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="76784-156">You can search by the following values:</span></span>

   - <span data-ttu-id="76784-157">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="76784-157">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="76784-158">Если вы выберете сообщение в списке, значение всплывающего **Идентификатора сообщения** появится в появившейся всплывающей панели **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="76784-158">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="76784-159">Администраторы могут использовать [трассировку сообщений](message-trace-scc.md) для поиска сообщений и соответствующих им значений идентификатора сообщения.</span><span class="sxs-lookup"><span data-stu-id="76784-159">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="76784-160">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="76784-160">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="76784-161">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="76784-161">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="76784-162">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="76784-162">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="76784-163">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="76784-163">The search is not case-sensitive.</span></span>

   <span data-ttu-id="76784-164">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="76784-164">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="76784-165">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="76784-165">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="76784-166">Экспортировать результаты сообщения</span><span class="sxs-lookup"><span data-stu-id="76784-166">Export message results</span></span>

1. <span data-ttu-id="76784-167">Выберите интересующие вас сообщения и нажмите **Экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="76784-167">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="76784-168">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="76784-168">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="76784-169">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="76784-169">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="76784-170">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="76784-170">View quarantined message details</span></span>

<span data-ttu-id="76784-171">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="76784-171">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="76784-172">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="76784-172">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="76784-173">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="76784-173">**Sender address**</span></span>

- <span data-ttu-id="76784-174">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="76784-174">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="76784-175">**Тема**</span><span class="sxs-lookup"><span data-stu-id="76784-175">**Subject**</span></span>

- <span data-ttu-id="76784-176">**Причина карантина**: показывает, было ли сообщение определено как **спам**,**массовой** или (в апреле, 2020) **фишинг**.</span><span class="sxs-lookup"><span data-stu-id="76784-176">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="76784-177">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="76784-177">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="76784-178">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="76784-178">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="76784-179">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="76784-179">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="76784-180">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="76784-180">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="76784-181">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="76784-181">Take action on quarantined email</span></span>

<span data-ttu-id="76784-182">После того как вы выберете сообщение, у вас есть варианты действий с сообщениями в разделе **сведения** раскрывающейся области.</span><span class="sxs-lookup"><span data-stu-id="76784-182">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="76784-183">**Выпуск сообщений**: в открывшейся всплывающей области Укажите, нужно ли **сообщения отчетов в корпорацию Майкрософт для анализа**.</span><span class="sxs-lookup"><span data-stu-id="76784-183">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="76784-184">Это выбрано по умолчанию и сообщает ошибочно помещенное в карантин сообщение Microsoft как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="76784-184">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="76784-185">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="76784-185">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="76784-186">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="76784-186">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="76784-187">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="76784-187">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="76784-188">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="76784-188">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="76784-189">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="76784-189">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="76784-190">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="76784-190">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="76784-191">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="76784-191">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="76784-192">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="76784-192">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="76784-193">**Удалить из карантина**: После нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется.</span><span class="sxs-lookup"><span data-stu-id="76784-193">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="76784-194">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="76784-194">When you're finished, click **Close**.</span></span>

<span data-ttu-id="76784-195">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76784-195">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="76784-196">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="76784-196">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="76784-197">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="76784-197">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="76784-198">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="76784-198">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="76784-199">**Удалить сообщения**: После нажатия кнопки **Да** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="76784-199">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="76784-200">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="76784-200">When you're finished, click **Close**.</span></span>
