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
ms.openlocfilehash: 177f60f1fccc764d74ec0374249a62c602cb84aa
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036516"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="2cc86-103">Поиск и разблокирование сообщений, находящихся на карантине, для пользователя</span><span class="sxs-lookup"><span data-stu-id="2cc86-103">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="2cc86-104">На карантине хранятся потенциально опасные или нежелательные сообщения в организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2cc86-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="2cc86-105">Дополнительные сведения см. [В разделе Карантин в Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="2cc86-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="2cc86-106">Как пользователь, вы можете просматривать, выпускать и удалять сообщения, помещенные на карантин, если вы являетесь получателем, а сообщение было помещено на карантин как спам, электронная почта или (по состоянию на апрель 2020 года) фишинг.</span><span class="sxs-lookup"><span data-stu-id="2cc86-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="2cc86-107">Можно просматривать сообщения, помещенные на карантин, в центре безопасности и соблюдения требований (если администратор настроил этот вариант) в разделе [уведомления о спаме для пользователей](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="2cc86-107">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2cc86-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="2cc86-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2cc86-109">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="2cc86-109">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="2cc86-110">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="2cc86-110">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="2cc86-111">Администраторы могут настроить продолжительность хранения сообщений в карантине до их окончательного удаления (политики защиты от спама).</span><span class="sxs-lookup"><span data-stu-id="2cc86-111">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="2cc86-112">Сообщения, срок действия которых истек из карантина, невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="2cc86-112">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="2cc86-113">Дополнительные сведения см. в разделе [Настройка политик защиты от спама в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2cc86-113">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="2cc86-114">Администраторы также могут [включить уведомления о спаме для конечных пользователей](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) в политиках защиты от спама.</span><span class="sxs-lookup"><span data-stu-id="2cc86-114">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="2cc86-115">Пользователи могут освобождать прямо из этих уведомлений помещенные на карантин сообщения, но не сообщения, помещенные на карантин из-за фишинга.</span><span class="sxs-lookup"><span data-stu-id="2cc86-115">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="2cc86-116">Дополнительные сведения см. в разделе [Уведомления о спаме для конечных пользователей в Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="2cc86-116">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="2cc86-117">Сообщения, которые были помещены в карантин для фишинга с высокой степенью достоверности, вредоносного ПО или по правилам потока почты (также называемым правилами транспорта), доступны только администраторам.</span><span class="sxs-lookup"><span data-stu-id="2cc86-117">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="2cc86-118">Фишинговые сообщения могут просматриваться пользователями, но освобождаются только администраторами.</span><span class="sxs-lookup"><span data-stu-id="2cc86-118">Phish messages can be reviewed by users but only released by admins.</span></span> <span data-ttu-id="2cc86-119">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="2cc86-119">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="2cc86-120">Освободить сообщение и сообщить о ложном срабатывании (о том, что сообщение не является нежелательным) можно только один раз.</span><span class="sxs-lookup"><span data-stu-id="2cc86-120">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="2cc86-121">Просмотр сообщений на карантине</span><span class="sxs-lookup"><span data-stu-id="2cc86-121">View your quarantined messages</span></span>

1. <span data-ttu-id="2cc86-122">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-122">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="2cc86-123">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="2cc86-123">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="2cc86-124">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="2cc86-124">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="2cc86-125">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="2cc86-125">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="2cc86-126">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cc86-126">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="2cc86-127">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cc86-127">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="2cc86-128">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cc86-128">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="2cc86-129">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cc86-129">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="2cc86-130">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cc86-130">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="2cc86-131">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cc86-131">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="2cc86-132">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cc86-132">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="2cc86-133">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="2cc86-133">**Recipient**</span></span>

   - <span data-ttu-id="2cc86-134">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="2cc86-134">**Message ID**</span></span>

   - <span data-ttu-id="2cc86-135">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="2cc86-135">**Policy name**</span></span>

   - <span data-ttu-id="2cc86-136">**Размер**</span><span class="sxs-lookup"><span data-stu-id="2cc86-136">**Size**</span></span>

   - <span data-ttu-id="2cc86-137">**Направление**</span><span class="sxs-lookup"><span data-stu-id="2cc86-137">**Direction**</span></span>

   <span data-ttu-id="2cc86-138">Когда все будет готово, нажмите кнопку **сохранить**или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-138">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="2cc86-139">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-139">To filter the results, click **Filter**.</span></span> <span data-ttu-id="2cc86-140">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="2cc86-140">The available filters are:</span></span>

   - <span data-ttu-id="2cc86-141">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="2cc86-141">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="2cc86-142">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="2cc86-142">**Today**</span></span>

     - <span data-ttu-id="2cc86-143">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="2cc86-143">**Next 2 days**</span></span>

     - <span data-ttu-id="2cc86-144">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="2cc86-144">**Next 7 days**</span></span>

     - <span data-ttu-id="2cc86-145">**Настраиваемые**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-145">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="2cc86-146">**Время получения**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-146">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="2cc86-147">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="2cc86-147">**Quarantine reason**:</span></span>

     - <span data-ttu-id="2cc86-148">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="2cc86-148">**Bulk**</span></span>

     - <span data-ttu-id="2cc86-149">**Спам**</span><span class="sxs-lookup"><span data-stu-id="2cc86-149">**Spam**</span></span>

     - <span data-ttu-id="2cc86-150">**Фиш** (по состоянию на апрель 2020 г.)</span><span class="sxs-lookup"><span data-stu-id="2cc86-150">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="2cc86-151">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-151">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="2cc86-152">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-152">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="2cc86-153">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="2cc86-153">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="2cc86-154">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="2cc86-154">Wildcards aren't supported.</span></span> <span data-ttu-id="2cc86-155">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="2cc86-155">You can search by the following values:</span></span>

   - <span data-ttu-id="2cc86-156">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="2cc86-156">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="2cc86-157">Если вы выберете сообщение в списке, значение всплывающего **Идентификатора сообщения** появится в появившейся всплывающей панели **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-157">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="2cc86-158">Администраторы могут использовать [трассировку сообщений](message-trace-scc.md) для поиска сообщений и соответствующих им значений идентификатора сообщения.</span><span class="sxs-lookup"><span data-stu-id="2cc86-158">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="2cc86-159">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="2cc86-159">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="2cc86-160">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="2cc86-160">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="2cc86-161">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="2cc86-161">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="2cc86-162">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="2cc86-162">The search is not case-sensitive.</span></span>

   <span data-ttu-id="2cc86-163">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="2cc86-163">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="2cc86-164">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="2cc86-164">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="2cc86-165">Экспортировать результаты сообщения</span><span class="sxs-lookup"><span data-stu-id="2cc86-165">Export message results</span></span>

1. <span data-ttu-id="2cc86-166">Выберите интересующие вас сообщения и нажмите **Экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-166">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="2cc86-167">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="2cc86-167">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="2cc86-168">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="2cc86-168">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="2cc86-169">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="2cc86-169">View quarantined message details</span></span>

<span data-ttu-id="2cc86-170">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="2cc86-170">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="2cc86-171">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="2cc86-171">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="2cc86-172">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="2cc86-172">**Sender address**</span></span>

- <span data-ttu-id="2cc86-173">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="2cc86-173">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="2cc86-174">**Тема**</span><span class="sxs-lookup"><span data-stu-id="2cc86-174">**Subject**</span></span>

- <span data-ttu-id="2cc86-175">**Причина карантина**: показывает, было ли сообщение определено как **спам**,**массовой** или (в апреле, 2020) **фишинг**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-175">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="2cc86-176">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="2cc86-176">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="2cc86-177">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="2cc86-177">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="2cc86-178">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="2cc86-178">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="2cc86-179">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="2cc86-179">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="2cc86-180">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="2cc86-180">Take action on quarantined email</span></span>

<span data-ttu-id="2cc86-181">После того как вы выберете сообщение, у вас есть варианты действий с сообщениями в разделе **сведения** раскрывающейся области.</span><span class="sxs-lookup"><span data-stu-id="2cc86-181">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="2cc86-182">**Выпуск сообщений**: в открывшейся всплывающей области Укажите, нужно ли **сообщения отчетов в корпорацию Майкрософт для анализа**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-182">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="2cc86-183">Это выбрано по умолчанию и сообщает ошибочно помещенное в карантин сообщение Microsoft как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="2cc86-183">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="2cc86-184">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-184">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="2cc86-185">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="2cc86-185">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="2cc86-186">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="2cc86-186">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="2cc86-187">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="2cc86-187">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="2cc86-188">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="2cc86-188">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="2cc86-189">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="2cc86-189">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="2cc86-190">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="2cc86-190">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="2cc86-191">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="2cc86-191">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="2cc86-192">**Удалить из карантина**: После нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется.</span><span class="sxs-lookup"><span data-stu-id="2cc86-192">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="2cc86-193">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-193">When you're finished, click **Close**.</span></span>

<span data-ttu-id="2cc86-194">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2cc86-194">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="2cc86-195">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="2cc86-195">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="2cc86-196">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2cc86-196">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="2cc86-197">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-197">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="2cc86-198">**Удалить сообщения**: После нажатия кнопки **Да** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="2cc86-198">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="2cc86-199">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2cc86-199">When you're finished, click **Close**.</span></span>
