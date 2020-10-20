---
title: Поиск и разблокирование сообщений, находящихся на карантине, для пользователя
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
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
description: Пользователи могут узнать о том, как просматривать сообщения, помещенные на карантин в Exchange Online Protection (EOP), и управлять ими.
ms.openlocfilehash: 2a8e37dc430af5b3d3c47179c721d83832f01184
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600349"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="a2ada-103">Поиск и разблокирование сообщений, находящихся на карантине, для пользователя в EOP</span><span class="sxs-lookup"><span data-stu-id="a2ada-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a2ada-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="a2ada-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="a2ada-105">Дополнительные сведения см. в статье [Карантин в EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a2ada-105">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="a2ada-106">Как пользователь вы можете просмотреть, разблокировать и удалить сообщения, помещенные на карантин, если вы являетесь получателем, а сообщение было помещено на карантин как спам или массовая рассылка.</span><span class="sxs-lookup"><span data-stu-id="a2ada-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="a2ada-107">С апреля 2020 г. вы можете просматривать и удалять фишинговые сообщения (не относящиеся к фишингу с высокой вероятностью), помещенные на карантин, если вы являетесь получателем.</span><span class="sxs-lookup"><span data-stu-id="a2ada-107">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="a2ada-108">Можно просматривать сообщения, помещенные на карантин, в центре безопасности и соблюдения требований (если администратор настроил этот вариант) в разделе [уведомления о спаме для пользователей](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a2ada-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a2ada-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="a2ada-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a2ada-110">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="a2ada-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="a2ada-111">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="a2ada-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="a2ada-112">Администраторы могут настроить продолжительность хранения сообщений в карантине до их окончательного удаления (политики защиты от спама).</span><span class="sxs-lookup"><span data-stu-id="a2ada-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="a2ada-113">Сообщения, срок действия которых истек из карантина, невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="a2ada-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="a2ada-114">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a2ada-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="a2ada-115">Администраторы также могут [включить уведомления о спаме для конечных пользователей](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) в политиках защиты от спама.</span><span class="sxs-lookup"><span data-stu-id="a2ada-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="a2ada-116">Пользователи могут освобождать помещенные на карантин нежелательные сообщения прямо из этих уведомлений.</span><span class="sxs-lookup"><span data-stu-id="a2ada-116">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="a2ada-117">Пользователи могут просматривать помещенные на карантин фишинговые сообщения (не фишинговые сообщения с высокой степенью уверенности) прямо из этих уведомлений.</span><span class="sxs-lookup"><span data-stu-id="a2ada-117">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="a2ada-118">Дополнительные сведения см. в статье [Уведомления пользователей о спаме в EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a2ada-118">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="a2ada-119">Сообщения, которые были помещены в карантин по причине фишинга с высокой степенью уверенности, вредоносного ПО или по правилам потока почты (также называемым правилами транспорта), доступны только администраторам и не видны пользователям.</span><span class="sxs-lookup"><span data-stu-id="a2ada-119">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="a2ada-120">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="a2ada-120">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="a2ada-121">Освободить сообщение и сообщить о ложном срабатывании (о том, что сообщение не является нежелательным) можно только один раз.</span><span class="sxs-lookup"><span data-stu-id="a2ada-121">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="a2ada-122">Просмотр сообщений на карантине</span><span class="sxs-lookup"><span data-stu-id="a2ada-122">View your quarantined messages</span></span>

1. <span data-ttu-id="a2ada-123">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-123">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="a2ada-124">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="a2ada-124">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="a2ada-125">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="a2ada-125">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a2ada-126">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="a2ada-126">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="a2ada-127">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a2ada-127">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="a2ada-128">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a2ada-128">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="a2ada-129">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a2ada-129">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="a2ada-130">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a2ada-130">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="a2ada-131">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a2ada-131">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="a2ada-132">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a2ada-132">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="a2ada-133">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a2ada-133">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="a2ada-134">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="a2ada-134">**Recipient**</span></span>

   - <span data-ttu-id="a2ada-135">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="a2ada-135">**Message ID**</span></span>

   - <span data-ttu-id="a2ada-136">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="a2ada-136">**Policy name**</span></span>

   - <span data-ttu-id="a2ada-137">**Размер**</span><span class="sxs-lookup"><span data-stu-id="a2ada-137">**Size**</span></span>

   - <span data-ttu-id="a2ada-138">**Направление**</span><span class="sxs-lookup"><span data-stu-id="a2ada-138">**Direction**</span></span>

   <span data-ttu-id="a2ada-139">Когда все будет готово, нажмите кнопку **сохранить**или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="a2ada-140">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a2ada-141">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="a2ada-141">The available filters are:</span></span>

   - <span data-ttu-id="a2ada-142">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="a2ada-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="a2ada-143">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="a2ada-143">**Today**</span></span>

     - <span data-ttu-id="a2ada-144">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="a2ada-144">**Next 2 days**</span></span>

     - <span data-ttu-id="a2ada-145">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="a2ada-145">**Next 7 days**</span></span>

     - <span data-ttu-id="a2ada-146">**Настраиваемые**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a2ada-147">**Время получения**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a2ada-148">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="a2ada-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="a2ada-149">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="a2ada-149">**Bulk**</span></span>

     - <span data-ttu-id="a2ada-150">**Спам**</span><span class="sxs-lookup"><span data-stu-id="a2ada-150">**Spam**</span></span>

     - <span data-ttu-id="a2ada-151">**Фишинг**</span><span class="sxs-lookup"><span data-stu-id="a2ada-151">**Phish**</span></span>
     
   - <span data-ttu-id="a2ada-152">**Тип политики**: фильтрация сообщений по типу политики:</span><span class="sxs-lookup"><span data-stu-id="a2ada-152">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="a2ada-153">**Политика защиты от фишинга**</span><span class="sxs-lookup"><span data-stu-id="a2ada-153">**Anti-phish policy**</span></span>
     - <span data-ttu-id="a2ada-154">**Политика фильтрации размещенного содержимого**</span><span class="sxs-lookup"><span data-stu-id="a2ada-154">**Hosted content filter policy**</span></span>
     

   <span data-ttu-id="a2ada-155">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-155">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="a2ada-156">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-156">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="a2ada-157">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="a2ada-157">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="a2ada-158">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a2ada-158">Wildcards aren't supported.</span></span> <span data-ttu-id="a2ada-159">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="a2ada-159">You can search by the following values:</span></span>

   - <span data-ttu-id="a2ada-160">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="a2ada-160">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="a2ada-161">Если вы выберете сообщение в списке, значение всплывающего **Идентификатора сообщения** появится в появившейся всплывающей панели **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-161">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="a2ada-162">Администраторы могут использовать [трассировку сообщений](message-trace-scc.md) для поиска сообщений и соответствующих им значений идентификатора сообщения.</span><span class="sxs-lookup"><span data-stu-id="a2ada-162">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="a2ada-163">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="a2ada-163">**Sender email address**: A single sender's email address.</span></span>
   
   - <span data-ttu-id="a2ada-164">**Имя политики**: используйте полное имя политики сообщения.</span><span class="sxs-lookup"><span data-stu-id="a2ada-164">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="a2ada-165">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="a2ada-165">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="a2ada-166">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="a2ada-166">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="a2ada-167">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="a2ada-167">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="a2ada-168">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="a2ada-168">The search is not case-sensitive.</span></span>

   <span data-ttu-id="a2ada-169">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="a2ada-169">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="a2ada-170">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="a2ada-170">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="a2ada-171">Экспортировать результаты сообщения</span><span class="sxs-lookup"><span data-stu-id="a2ada-171">Export message results</span></span>

1. <span data-ttu-id="a2ada-172">Выберите интересующие вас сообщения и нажмите **Экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-172">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="a2ada-173">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="a2ada-173">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="a2ada-174">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="a2ada-174">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="a2ada-175">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="a2ada-175">View quarantined message details</span></span>

<span data-ttu-id="a2ada-176">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a2ada-176">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a2ada-177">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="a2ada-177">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="a2ada-178">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="a2ada-178">**Sender address**</span></span>

- <span data-ttu-id="a2ada-179">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="a2ada-179">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="a2ada-180">**Тема**</span><span class="sxs-lookup"><span data-stu-id="a2ada-180">**Subject**</span></span>

- <span data-ttu-id="a2ada-181">**Причина помещения на карантин**: Указывает, как было отмечено сообщение (**Спам**, **Массовая рассылка** или **Фишинг**).</span><span class="sxs-lookup"><span data-stu-id="a2ada-181">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="a2ada-182">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="a2ada-182">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="a2ada-183">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="a2ada-183">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="a2ada-184">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="a2ada-184">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="a2ada-185">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="a2ada-185">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="a2ada-186">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="a2ada-186">Take action on quarantined email</span></span>

<span data-ttu-id="a2ada-187">После того как вы выберете сообщение, у вас есть варианты действий с сообщениями в разделе **сведения** раскрывающейся области.</span><span class="sxs-lookup"><span data-stu-id="a2ada-187">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a2ada-188">**Выпуск сообщений**: в открывшейся всплывающей области Укажите, нужно ли **сообщения отчетов в корпорацию Майкрософт для анализа**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-188">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="a2ada-189">Это выбрано по умолчанию и сообщает ошибочно помещенное в карантин сообщение Microsoft как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="a2ada-189">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="a2ada-190">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-190">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="a2ada-191">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="a2ada-191">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="a2ada-192">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="a2ada-192">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="a2ada-193">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="a2ada-193">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="a2ada-194">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="a2ada-194">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="a2ada-195">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="a2ada-195">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="a2ada-196">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="a2ada-196">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="a2ada-197">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="a2ada-197">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="a2ada-198">**Удалить из карантина**: После нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется.</span><span class="sxs-lookup"><span data-stu-id="a2ada-198">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="a2ada-199">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-199">When you're finished, click **Close**.</span></span>

<span data-ttu-id="a2ada-200">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a2ada-200">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="a2ada-201">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="a2ada-201">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="a2ada-202">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a2ada-202">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="a2ada-203">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-203">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="a2ada-204">**Удалить сообщения**: После нажатия кнопки **Да** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="a2ada-204">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="a2ada-205">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a2ada-205">When you're finished, click **Close**.</span></span>
