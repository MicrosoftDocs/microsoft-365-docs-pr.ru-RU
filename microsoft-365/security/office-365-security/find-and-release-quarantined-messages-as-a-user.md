---
title: Поиск и освобождение сообщений из карантина от имени пользователя в Office 365
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
description: Будучи пользователем Office 365, вы можете просматривать, выпускать и удалять сообщения, помещенные на карантин (сообщения, для которых вы являетесь получателем, а фильтрация нежелательной почты изолировала сообщение как спам или массовую электронную почту). Вы просматриваете свои карантинные сообщения и управляете ими в Центре безопасности и соответствия требованиям.
ms.openlocfilehash: 04f04cfddb123bf176f3c71568789c77d225a601
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893674"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="51205-104">Поиск и освобождение сообщений из карантина от имени пользователя в Office 365</span><span class="sxs-lookup"><span data-stu-id="51205-104">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="51205-105">Карантин содержит потенциально опасные или нежелательные сообщения в организациях Office 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="51205-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="51205-106">Дополнительные сведения см. [В разделе Карантин в Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="51205-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="51205-107">Как пользователь, вы можете просматривать, выпускать и удалять сообщения, помещенные на карантин, если вы являетесь получателем, а сообщение было помещено на карантин как спам, электронная почта или (по состоянию на апрель 2020 года) фишинг.</span><span class="sxs-lookup"><span data-stu-id="51205-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="51205-108">Вы также можете сообщить о ложных срабатываниях в Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51205-108">You can also report false positives to Microsoft.</span></span>

<span data-ttu-id="51205-109">Вы просматриваете свои карантинные сообщения и управляете ими в Центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="51205-109">You view and manage your quarantined messages in the Security & Compliance Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51205-110">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="51205-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="51205-111">Чтобы открыть Центр безопасности и соответствия требованиям Office 365, перейдите на <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="51205-111">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="51205-112">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="51205-112">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="51205-113">Администраторы могут настроить продолжительность хранения сообщений в карантине до их окончательного удаления (политики защиты от спама).</span><span class="sxs-lookup"><span data-stu-id="51205-113">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="51205-114">Сообщения, срок действия которых истек из карантина, невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="51205-114">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="51205-115">Дополнительные сведения см. в разделе [Настройка политик защиты от спама в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="51205-115">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="51205-116">Администраторы также могут [включить уведомления о спаме для конечных пользователей](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) в политиках защиты от спама.</span><span class="sxs-lookup"><span data-stu-id="51205-116">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="51205-117">С октября 2019 года вы больше не можете выпускать сообщения из карантина непосредственно из этих уведомлений.</span><span class="sxs-lookup"><span data-stu-id="51205-117">As of October 2019, you can no longer release quarantined messages directly from these notifications.</span></span> <span data-ttu-id="51205-118">Вы можете нажать кнопку **Просмотр** в уведомлении, после чего вы попадете на карантин в Центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="51205-118">You can click **Review** in the notification, which will take you to Quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="51205-119">Дополнительные сведения об уведомлениях см. в статье [Уведомления пользователей о нежелательной почте в Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="51205-119">For more information about the notifications, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="51205-120">Сообщения, которые были помещены в карантин для фишинга с высокой степенью достоверности, вредоносного ПО или по правилам потока почты (также называемым правилами транспорта), доступны только администраторам.</span><span class="sxs-lookup"><span data-stu-id="51205-120">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="51205-121">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="51205-121">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="51205-122">Освободить сообщение и сообщить о ложном срабатывании (о том, что сообщение не является нежелательным) можно только один раз.</span><span class="sxs-lookup"><span data-stu-id="51205-122">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="51205-123">Просмотр сообщений на карантине</span><span class="sxs-lookup"><span data-stu-id="51205-123">View your quarantined messages</span></span>

1. <span data-ttu-id="51205-124">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="51205-124">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="51205-125">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="51205-125">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="51205-126">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="51205-126">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="51205-127">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="51205-127">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="51205-128">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51205-128">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="51205-129">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51205-129">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="51205-130">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51205-130">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="51205-131">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51205-131">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="51205-132">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51205-132">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="51205-133">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51205-133">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="51205-134">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51205-134">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="51205-135">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="51205-135">**Recipient**</span></span>

   - <span data-ttu-id="51205-136">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="51205-136">**Message ID**</span></span>

   - <span data-ttu-id="51205-137">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="51205-137">**Policy name**</span></span>

   - <span data-ttu-id="51205-138">**Размер**</span><span class="sxs-lookup"><span data-stu-id="51205-138">**Size**</span></span>

   - <span data-ttu-id="51205-139">**Направление**</span><span class="sxs-lookup"><span data-stu-id="51205-139">**Direction**</span></span>

   <span data-ttu-id="51205-140">Когда все будет готово, нажмите кнопку **сохранить**или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="51205-140">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="51205-141">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="51205-141">To filter the results, click **Filter**.</span></span> <span data-ttu-id="51205-142">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="51205-142">The available filters are:</span></span>

   - <span data-ttu-id="51205-143">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="51205-143">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="51205-144">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="51205-144">**Today**</span></span>

     - <span data-ttu-id="51205-145">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="51205-145">**Next 2 days**</span></span>

     - <span data-ttu-id="51205-146">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="51205-146">**Next 7 days**</span></span>

     - <span data-ttu-id="51205-147">**Настраиваемые**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="51205-147">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="51205-148">**Время получения**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="51205-148">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="51205-149">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="51205-149">**Quarantine reason**:</span></span>

     - <span data-ttu-id="51205-150">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="51205-150">**Bulk**</span></span>

     - <span data-ttu-id="51205-151">**Спам**</span><span class="sxs-lookup"><span data-stu-id="51205-151">**Spam**</span></span>

     - <span data-ttu-id="51205-152">**Фиш** (по состоянию на апрель 2020 г.)</span><span class="sxs-lookup"><span data-stu-id="51205-152">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="51205-153">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="51205-153">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="51205-154">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="51205-154">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="51205-155">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="51205-155">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="51205-156">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="51205-156">Wildcards aren't supported.</span></span> <span data-ttu-id="51205-157">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="51205-157">You can search by the following values:</span></span>

   - <span data-ttu-id="51205-158">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="51205-158">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="51205-159">Если вы выберете сообщение в списке, значение всплывающего **Идентификатора сообщения** появится в появившейся всплывающей панели **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="51205-159">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="51205-160">Администраторы могут использовать [трассировку сообщений](message-trace-scc.md) для поиска сообщений и соответствующих им значений идентификатора сообщения.</span><span class="sxs-lookup"><span data-stu-id="51205-160">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="51205-161">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="51205-161">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="51205-162">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="51205-162">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="51205-163">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="51205-163">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="51205-164">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="51205-164">The search is not case-sensitive.</span></span>

   <span data-ttu-id="51205-165">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="51205-165">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="51205-166">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="51205-166">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="51205-167">Экспортировать результаты сообщения</span><span class="sxs-lookup"><span data-stu-id="51205-167">Export message results</span></span>

1. <span data-ttu-id="51205-168">Выберите интересующие вас сообщения и нажмите **Экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="51205-168">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="51205-169">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="51205-169">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="51205-170">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="51205-170">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="51205-171">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="51205-171">View quarantined message details</span></span>

<span data-ttu-id="51205-172">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="51205-172">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="51205-173">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="51205-173">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="51205-174">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="51205-174">**Sender address**</span></span>

- <span data-ttu-id="51205-175">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="51205-175">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="51205-176">**Тема**</span><span class="sxs-lookup"><span data-stu-id="51205-176">**Subject**</span></span>

- <span data-ttu-id="51205-177">**Причина карантина**: показывает, было ли сообщение определено как **спам**,**массовой** или (в апреле, 2020) **фишинг**.</span><span class="sxs-lookup"><span data-stu-id="51205-177">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="51205-178">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="51205-178">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="51205-179">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="51205-179">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="51205-180">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="51205-180">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="51205-181">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="51205-181">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="51205-182">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="51205-182">Take action on quarantined email</span></span>

<span data-ttu-id="51205-183">После того как вы выберете сообщение, у вас есть варианты действий с сообщениями в разделе **сведения** раскрывающейся области.</span><span class="sxs-lookup"><span data-stu-id="51205-183">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="51205-184">**Выпуск сообщений**: в открывшейся всплывающей области Укажите, нужно ли **сообщения отчетов в корпорацию Майкрософт для анализа**.</span><span class="sxs-lookup"><span data-stu-id="51205-184">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="51205-185">Это выбрано по умолчанию и сообщает ошибочно помещенное в карантин сообщение Microsoft как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="51205-185">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="51205-186">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="51205-186">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="51205-187">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="51205-187">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="51205-188">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если не хотите покинуть Office 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="51205-188">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="51205-189">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="51205-189">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="51205-190">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="51205-190">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="51205-191">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="51205-191">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="51205-192">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="51205-192">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="51205-193">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="51205-193">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="51205-194">**Удалить из карантина**: После нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется.</span><span class="sxs-lookup"><span data-stu-id="51205-194">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="51205-195">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="51205-195">When you're finished, click **Close**.</span></span>

<span data-ttu-id="51205-196">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51205-196">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="51205-197">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="51205-197">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="51205-198">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="51205-198">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="51205-199">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="51205-199">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="51205-200">**Удалить сообщения**: После нажатия кнопки **Да** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="51205-200">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="51205-201">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="51205-201">When you're finished, click **Close**.</span></span>
