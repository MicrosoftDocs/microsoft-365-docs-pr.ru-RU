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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 02119130df847da48f0c25ba13cbb321c83f59dd
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028395"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="94649-103">Поиск и разблокирование сообщений, находящихся на карантине, для пользователя в EOP</span><span class="sxs-lookup"><span data-stu-id="94649-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="94649-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="94649-104">**Applies to**</span></span>
- [<span data-ttu-id="94649-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="94649-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="94649-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="94649-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="94649-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94649-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="94649-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="94649-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="94649-109">Дополнительные сведения см. в статье [Карантин в EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="94649-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>


<span data-ttu-id="94649-110">Вы можете просматривать помещенные на карантин сообщения, а также управлять ими на портале Microsoft 365 Defender или (если администратор настроил этот вариант) в разделе [уведомлений о спаме для пользователей](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="94649-110">You view and manage your quarantined messages in the Microsoft 365 Defender portal or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="94649-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="94649-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="94649-112">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="94649-112">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="94649-113">Чтобы открыть страницу Карантина напрямую, перейдите на <https://security.microsoft.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="94649-113">To open the Quarantine page directly, go to <https://security.microsoft.com/quarantine>.</span></span>

- <span data-ttu-id="94649-114">Администраторы могут настроить продолжительность хранения сообщений в карантине до их окончательного удаления в политиках защиты от спама.</span><span class="sxs-lookup"><span data-stu-id="94649-114">Admins can configure how long messages are kept in quarantine before they're permanently deleted in anti-spam policies.</span></span> <span data-ttu-id="94649-115">Сообщения, срок действия которых истек из карантина, невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="94649-115">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="94649-116">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="94649-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="94649-117">Администраторы также могут [включить уведомления о спаме для конечных пользователей](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) в политиках защиты от спама.</span><span class="sxs-lookup"><span data-stu-id="94649-117">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="94649-118">Пользователи могут освобождать помещенные на карантин нежелательные сообщения прямо из этих уведомлений.</span><span class="sxs-lookup"><span data-stu-id="94649-118">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="94649-119">Пользователи могут просматривать помещенные на карантин фишинговые сообщения (не фишинговые сообщения с высокой степенью уверенности) прямо из этих уведомлений.</span><span class="sxs-lookup"><span data-stu-id="94649-119">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="94649-120">Дополнительные сведения см. в статье [Уведомления пользователей о спаме в EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="94649-120">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="94649-121">Сообщения, которые были помещены в карантин по причине фишинга с высокой степенью уверенности, вредоносного ПО или по правилам потока почты (также называемым правилами транспорта), доступны только администраторам и не видны пользователям.</span><span class="sxs-lookup"><span data-stu-id="94649-121">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="94649-122">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="94649-122">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="94649-123">Освободить сообщение и сообщить о ложном срабатывании (о том, что сообщение не является нежелательным) можно только один раз.</span><span class="sxs-lookup"><span data-stu-id="94649-123">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="94649-124">Просмотр сообщений на карантине</span><span class="sxs-lookup"><span data-stu-id="94649-124">View your quarantined messages</span></span>

1. <span data-ttu-id="94649-125">На портале Microsoft 365 Defender перейдите в раздел **Сообщения электронной почты и совместная работа** \> **Просмотр** \> **Карантин**.</span><span class="sxs-lookup"><span data-stu-id="94649-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="94649-126">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="94649-126">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="94649-127">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="94649-127">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="94649-128">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="94649-128">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="94649-129">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94649-129">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="94649-130">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94649-130">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="94649-131">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94649-131">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="94649-132">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94649-132">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="94649-133">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94649-133">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="94649-134">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94649-134">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="94649-135">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94649-135">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="94649-136">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="94649-136">**Recipient**</span></span>
   - <span data-ttu-id="94649-137">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="94649-137">**Message ID**</span></span>
   - <span data-ttu-id="94649-138">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="94649-138">**Policy name**</span></span>
   - <span data-ttu-id="94649-139">**Размер**</span><span class="sxs-lookup"><span data-stu-id="94649-139">**Size**</span></span>
   - <span data-ttu-id="94649-140">**Направление**</span><span class="sxs-lookup"><span data-stu-id="94649-140">**Direction**</span></span>

   <span data-ttu-id="94649-141">Когда все будет готово, нажмите кнопку **сохранить** или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="94649-141">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="94649-142">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="94649-142">To filter the results, click **Filter**.</span></span> <span data-ttu-id="94649-143">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="94649-143">The available filters are:</span></span>

   - <span data-ttu-id="94649-144">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="94649-144">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="94649-145">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="94649-145">**Today**</span></span>
     - <span data-ttu-id="94649-146">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="94649-146">**Next 2 days**</span></span>
     - <span data-ttu-id="94649-147">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="94649-147">**Next 7 days**</span></span>
     - <span data-ttu-id="94649-148">**Настраиваемые**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="94649-148">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="94649-149">**Время получения**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="94649-149">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="94649-150">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="94649-150">**Quarantine reason**:</span></span>
     - <span data-ttu-id="94649-151">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="94649-151">**Bulk**</span></span>
     - <span data-ttu-id="94649-152">**Спам**</span><span class="sxs-lookup"><span data-stu-id="94649-152">**Spam**</span></span>
     - <span data-ttu-id="94649-153">**Фишинг**</span><span class="sxs-lookup"><span data-stu-id="94649-153">**Phish**</span></span>

   - <span data-ttu-id="94649-154">**Тип политики**: фильтрация сообщений по типу политики:</span><span class="sxs-lookup"><span data-stu-id="94649-154">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="94649-155">**Политика защиты от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="94649-155">**Anti-malware policy**</span></span>
     - <span data-ttu-id="94649-156">**Политика безопасных вложений** (Defender для Office 365)</span><span class="sxs-lookup"><span data-stu-id="94649-156">**Safe Attachments policy** (Defender for Office 365)</span></span>
     - <span data-ttu-id="94649-157">**Политика защиты от фишинга**</span><span class="sxs-lookup"><span data-stu-id="94649-157">**Anti-phish policy**</span></span>
     - <span data-ttu-id="94649-158">**Политика фильтрации размещенного содержимого** (политика защиты от нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="94649-158">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="94649-159">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="94649-159">**Transport rule**</span></span>

     <sup>\*</sup>

   <span data-ttu-id="94649-160">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="94649-160">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="94649-161">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="94649-161">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="94649-162">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="94649-162">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="94649-163">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="94649-163">Wildcards aren't supported.</span></span> <span data-ttu-id="94649-164">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="94649-164">You can search by the following values:</span></span>

   - <span data-ttu-id="94649-165">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="94649-165">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="94649-166">Если вы выберете сообщение в списке, значение всплывающего **Идентификатора сообщения** появится в появившейся всплывающей панели **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="94649-166">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="94649-167">Администраторы могут использовать [трассировку сообщений](message-trace-scc.md) для поиска сообщений и соответствующих им значений идентификатора сообщения.</span><span class="sxs-lookup"><span data-stu-id="94649-167">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>
   - <span data-ttu-id="94649-168">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="94649-168">**Sender email address**: A single sender's email address.</span></span>
   - <span data-ttu-id="94649-169">**Имя политики**: используйте полное имя политики сообщения.</span><span class="sxs-lookup"><span data-stu-id="94649-169">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="94649-170">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="94649-170">The search is not case-sensitive.</span></span>
   - <span data-ttu-id="94649-171">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="94649-171">**Recipient email address**: A single recipient's email address.</span></span>
   - <span data-ttu-id="94649-172">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="94649-172">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="94649-173">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="94649-173">The search is not case-sensitive.</span></span>

   <span data-ttu-id="94649-174">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="94649-174">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="94649-175">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="94649-175">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="94649-176">Экспортировать результаты сообщения</span><span class="sxs-lookup"><span data-stu-id="94649-176">Export message results</span></span>

1. <span data-ttu-id="94649-177">Выберите интересующие вас сообщения и нажмите **Экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="94649-177">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="94649-178">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="94649-178">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="94649-179">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="94649-179">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="94649-180">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="94649-180">View quarantined message details</span></span>

<span data-ttu-id="94649-181">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="94649-181">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="94649-182">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="94649-182">**Message ID**: The globally unique identifier for the message.</span></span>
- <span data-ttu-id="94649-183">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="94649-183">**Sender address**</span></span>
- <span data-ttu-id="94649-184">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="94649-184">**Received**: The date/time when the message was received.</span></span>
- <span data-ttu-id="94649-185">**Тема**</span><span class="sxs-lookup"><span data-stu-id="94649-185">**Subject**</span></span>
- <span data-ttu-id="94649-186">**Причина помещения на карантин**: Указывает, как было отмечено сообщение (**Спам**, **Массовая рассылка** или **Фишинг**).</span><span class="sxs-lookup"><span data-stu-id="94649-186">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>
- <span data-ttu-id="94649-187">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="94649-187">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>
- <span data-ttu-id="94649-188">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="94649-188">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>
- <span data-ttu-id="94649-189">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="94649-189">**Released to**: All email addresses (if any) to which the message has been released.</span></span>
- <span data-ttu-id="94649-190">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="94649-190">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="94649-191">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="94649-191">Take action on quarantined email</span></span>

<span data-ttu-id="94649-192">После того как вы выберете сообщение, у вас есть варианты действий с сообщениями в разделе **сведения** раскрывающейся области.</span><span class="sxs-lookup"><span data-stu-id="94649-192">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="94649-193">**Выпуск сообщений**: в открывшейся всплывающей области Укажите, нужно ли **сообщения отчетов в корпорацию Майкрософт для анализа**.</span><span class="sxs-lookup"><span data-stu-id="94649-193">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="94649-194">Это выбрано по умолчанию и сообщает ошибочно помещенное в карантин сообщение Microsoft как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="94649-194">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="94649-195">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="94649-195">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="94649-196">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="94649-196">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="94649-197">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="94649-197">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="94649-198">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="94649-198">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="94649-199">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="94649-199">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="94649-200">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="94649-200">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="94649-201">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="94649-201">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="94649-202">**Удалить из карантина**: После нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется.</span><span class="sxs-lookup"><span data-stu-id="94649-202">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="94649-203">**Блокировка отправителя**: добавление отправителей в список заблокированных отправителей в вашем почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="94649-203">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="94649-204">Подробнее см. в разделе [Блокировка отправителя почтового сообщения](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="94649-204">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="94649-205">Отправитель будет добавлен в список заблокированных отправителей в вашем почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="94649-205">Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="94649-206">Подробнее см. в разделе [Блокировка отправителя почтового сообщения](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="94649-206">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="94649-207">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="94649-207">When you're finished, click **Close**.</span></span>

<span data-ttu-id="94649-208">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94649-208">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="94649-209">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="94649-209">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="94649-210">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="94649-210">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="94649-211">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="94649-211">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>
- <span data-ttu-id="94649-212">**Удалить сообщения**: После нажатия кнопки **Да** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="94649-212">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="94649-213">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="94649-213">When you're finished, click **Close**.</span></span>
