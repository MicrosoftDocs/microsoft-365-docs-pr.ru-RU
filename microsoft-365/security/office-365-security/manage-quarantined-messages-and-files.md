---
title: Управление сообщениями и файлами на карантине в качестве администратора
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Администраторы могут просматривать, освобождать и удалять все типы сообщений, помещенных в карантин, для всех пользователей. Только администраторы могут управлять сообщениями, помещенными на карантин, высокой достоверностью фишинга, или в результате правил для обработки почтового процесса (правила транспорта).
ms.openlocfilehash: 1ae64b71d29f9e2d973f5a73cc19790fe0736913
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635363"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator"></a><span data-ttu-id="777ab-104">Управление сообщениями и файлами на карантине от имени администратора</span><span class="sxs-lookup"><span data-stu-id="777ab-104">Manage quarantined messages and files as an administrator</span></span>

<span data-ttu-id="777ab-105">Карантин содержит потенциально опасные или нежелательные сообщения в организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или отдельной сети Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="777ab-105">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="777ab-106">Дополнительные сведения см. [В разделе Карантин в Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="777ab-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="777ab-107">Администраторы могут просматривать, освобождать и удалять все типы сообщений, помещенных в карантин, для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="777ab-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="777ab-108">Только администраторы могут управлять сообщениями, помещенными на карантин, высокой достоверностью фишинга, или в результате правил для процесса обработки почты (также называемых правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="777ab-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="777ab-109">Администраторы также могут сообщать ложные срабатывания корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="777ab-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="777ab-110">Администраторы в организациях с Office 365 Advanced Threat protection (ATP) также могут просматривать, загружать и удалять файлы, помещенные в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="777ab-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="777ab-111">Вы просматриваете и управляете сообщения, помещенные в карантин, в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 клиентов; Exchange Online Protection PowerShell для автономных клиентов EOP).</span><span class="sxs-lookup"><span data-stu-id="777ab-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="777ab-112">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="777ab-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="777ab-113">Чтобы открыть центр безопасности & соответствия требованиям, перейдите на <https://protection.office.com>страницу.</span><span class="sxs-lookup"><span data-stu-id="777ab-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="777ab-114">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="777ab-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="777ab-115">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="777ab-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="777ab-116">Чтобы подключиться к Exchange Online Protection PowerShell, ознакомьтесь [со статьей подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="777ab-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="777ab-117">Для управления карантином в качестве администратора необходимо назначить разрешения. Управление разрешениями осуществляется ролью **карантина** в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="777ab-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="777ab-118">По умолчанию эта роль назначается группам ролей " **Управление организацией** " (глобальными администраторами), " **Администратор карантина**" и " **Администраторы безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="777ab-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="777ab-119">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="777ab-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="777ab-120">Сообщения, помещенные в карантин, хранятся в течение определенного периода времени, по истечении которого они будут автоматически удалены:</span><span class="sxs-lookup"><span data-stu-id="777ab-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="777ab-121">Сообщения, помещенные в карантин политиками защиты от нежелательной почты (спама, фишинга и массовые сообщения электронной почты): 30 дней.</span><span class="sxs-lookup"><span data-stu-id="777ab-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="777ab-122">Это значение по умолчанию и максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="777ab-122">This is the default and maximum value.</span></span> <span data-ttu-id="777ab-123">Чтобы настроить это значение, ознакомьтесь со статьей [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="777ab-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="777ab-124">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора (или соответствующие роли центра безопасности & соответствия требованиям) в Организации, войдите в [Центр безопасности & соответствия требованиям](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="777ab-124">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

  - <span data-ttu-id="777ab-125">Сообщения, содержащие вредоносную программу: 15 дней.</span><span class="sxs-lookup"><span data-stu-id="777ab-125">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="777ab-126">При истечении срока действия сообщения из карантина его невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="777ab-126">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="777ab-127">Использование центра безопасности & соответствия требованиям для управления сообщениями электронной почты, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="777ab-127">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="777ab-128">Просмотр электронной почты, помещенной в карантин</span><span class="sxs-lookup"><span data-stu-id="777ab-128">View quarantined email</span></span>

1. <span data-ttu-id="777ab-129">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="777ab-129">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="777ab-130">Убедитесь, что для свойства **Просмотр в карантине** задано значение **электронной почты**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="777ab-130">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="777ab-131">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="777ab-131">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="777ab-132">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="777ab-132">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="777ab-133">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="777ab-133">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="777ab-134">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-134">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-135">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-135">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-136">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-136">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-137">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-137">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-138">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-138">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-139">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-139">**Policy type**<sup>\*</sup></span></span>

1. <span data-ttu-id="777ab-140">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора (или соответствующие роли центра безопасности & соответствия требованиям) в Организации, войдите в [Центр безопасности & соответствия требованиям](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="777ab-140">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

   - <span data-ttu-id="777ab-141">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="777ab-141">**Recipient**</span></span>

   - <span data-ttu-id="777ab-142">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="777ab-142">**Message ID**</span></span>

   - <span data-ttu-id="777ab-143">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="777ab-143">**Policy name**</span></span>

   - <span data-ttu-id="777ab-144">**Размер**</span><span class="sxs-lookup"><span data-stu-id="777ab-144">**Size**</span></span>

   - <span data-ttu-id="777ab-145">**Направление**</span><span class="sxs-lookup"><span data-stu-id="777ab-145">**Direction**</span></span>

   <span data-ttu-id="777ab-146">Когда все будет готово, нажмите кнопку **сохранить**или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="777ab-146">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="777ab-147">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="777ab-147">To filter the results, click **Filter**.</span></span> <span data-ttu-id="777ab-148">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="777ab-148">The available filters are:</span></span>

   - <span data-ttu-id="777ab-149">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="777ab-149">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="777ab-150">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="777ab-150">**Today**</span></span>

     - <span data-ttu-id="777ab-151">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="777ab-151">**Next 2 days**</span></span>

     - <span data-ttu-id="777ab-152">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="777ab-152">**Next 7 days**</span></span>

     - <span data-ttu-id="777ab-153">**Настраиваемые**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="777ab-153">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="777ab-154">**Время получения**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="777ab-154">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="777ab-155">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="777ab-155">**Quarantine reason**:</span></span>

     - <span data-ttu-id="777ab-156">**Политика**: сообщение, соответствующее условиям правила для обработки почтового ящика (которое также называется правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="777ab-156">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="777ab-157">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="777ab-157">**Bulk**</span></span>

     - <span data-ttu-id="777ab-158">**Фишинговых писем**</span><span class="sxs-lookup"><span data-stu-id="777ab-158">**Phish**</span></span>

     - <span data-ttu-id="777ab-159">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="777ab-159">**Malware**</span></span>

     - <span data-ttu-id="777ab-160">**Спам**</span><span class="sxs-lookup"><span data-stu-id="777ab-160">**Spam**</span></span>

     - <span data-ttu-id="777ab-161">**Фишинг с высокой степенью вероятности**</span><span class="sxs-lookup"><span data-stu-id="777ab-161">**High Confidence Phish**</span></span>

   - <span data-ttu-id="777ab-162">**Получатель электронной почты**: все пользователи или сообщения, отправленные вам.</span><span class="sxs-lookup"><span data-stu-id="777ab-162">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="777ab-163">Конечные пользователи могут управлять только отправленными ими сообщениями из карантина.</span><span class="sxs-lookup"><span data-stu-id="777ab-163">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="777ab-164">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="777ab-164">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="777ab-165">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="777ab-165">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="777ab-166">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="777ab-166">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="777ab-167">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="777ab-167">Wildcards aren't supported.</span></span> <span data-ttu-id="777ab-168">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="777ab-168">You can search by the following values:</span></span>

   - <span data-ttu-id="777ab-169">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="777ab-169">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="777ab-170">Например, [Трассировка сообщений](message-trace-scc.md) используется для поиска сообщения, отправленного пользователю в Организации, и определения того, что сообщение помещено в карантин, а не доставлено.</span><span class="sxs-lookup"><span data-stu-id="777ab-170">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="777ab-171">Обязательно укажите полное значение идентификатора сообщения, которое может включать угловые скобки (\<\>).</span><span class="sxs-lookup"><span data-stu-id="777ab-171">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="777ab-172">Пример: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="777ab-172">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="777ab-173">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="777ab-173">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="777ab-174">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="777ab-174">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="777ab-175">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="777ab-175">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="777ab-176">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="777ab-176">The search is not case-sensitive.</span></span>

   <span data-ttu-id="777ab-177">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="777ab-177">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="777ab-178">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="777ab-178">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="777ab-179">Экспортировать результаты сообщения</span><span class="sxs-lookup"><span data-stu-id="777ab-179">Export message results</span></span>

1. <span data-ttu-id="777ab-180">Выберите интересующие вас сообщения и нажмите **Экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="777ab-180">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="777ab-181">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="777ab-181">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="777ab-182">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="777ab-182">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="777ab-183">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="777ab-183">View quarantined message details</span></span>

<span data-ttu-id="777ab-184">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="777ab-184">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="777ab-185">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="777ab-185">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="777ab-186">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="777ab-186">**Sender address**</span></span>

- <span data-ttu-id="777ab-187">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="777ab-187">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="777ab-188">**Тема**</span><span class="sxs-lookup"><span data-stu-id="777ab-188">**Subject**</span></span>

- <span data-ttu-id="777ab-189">**Причина карантина**: показывает, что сообщение было определено как **Нежелательная**почта, **массовый**, **Фишинг**, сопоставляемое правило обработки почты (**правило транспорта**) или оно было определено как содержащее **вредоносную**программу.</span><span class="sxs-lookup"><span data-stu-id="777ab-189">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="777ab-190">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="777ab-190">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="777ab-191">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="777ab-191">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="777ab-192">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="777ab-192">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="777ab-193">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="777ab-193">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="777ab-194">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="777ab-194">Take action on quarantined email</span></span>

<span data-ttu-id="777ab-195">После выбора сообщения у вас есть несколько вариантов действий с сообщениями в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="777ab-195">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="777ab-196">**Сообщение об освобождении**: в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="777ab-196">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="777ab-197">**Сообщения отчетов в корпорацию Майкрософт для анализа**: этот параметр выбран по умолчанию и сообщает о том, что сообщение помещено в карантин в корпорацию Майкрософт как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="777ab-197">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="777ab-198">Если сообщение помещено в карантин, является пакетным, фишингом или содержит вредоносные программы, сообщение также передается группе анализа нежелательной почты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="777ab-198">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="777ab-199">В зависимости от их анализа можно настроить правила фильтрации нежелательной почты на уровне службы, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="777ab-199">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="777ab-200">Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="777ab-200">Choose one of the following options:</span></span>

    - <span data-ttu-id="777ab-201">**Освобождение сообщений всем получателям**</span><span class="sxs-lookup"><span data-stu-id="777ab-201">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="777ab-202">**Освобождение сообщений определенным получателям**</span><span class="sxs-lookup"><span data-stu-id="777ab-202">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="777ab-203">**Разблокирование сообщений для других пользователей**</span><span class="sxs-lookup"><span data-stu-id="777ab-203">**Release messages to other people**</span></span>

  <span data-ttu-id="777ab-204">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="777ab-204">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="777ab-205">Примечания по выпуску сообщений:</span><span class="sxs-lookup"><span data-stu-id="777ab-205">Notes about releasing messages:</span></span>

  - <span data-ttu-id="777ab-206">Вы не можете выпустить сообщение для одного и того же получателя несколько раз.</span><span class="sxs-lookup"><span data-stu-id="777ab-206">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="777ab-207">В списке потенциальных получателей будут отображаться только получатели, не получившие сообщение.</span><span class="sxs-lookup"><span data-stu-id="777ab-207">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="777ab-208">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="777ab-208">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="777ab-209">Чтобы проанализировать поля верхнего колонтитула и значения, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **анализатор заголовков сообщений Майкрософт** , чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите команду **Открыть на новой вкладке** , чтобы не оставлять Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="777ab-209">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="777ab-210">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="777ab-210">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="777ab-211">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="777ab-211">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="777ab-212">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="777ab-212">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="777ab-213">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="777ab-213">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="777ab-214">**Удалить из карантина**: после нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется без отправки первоначальным получателям.</span><span class="sxs-lookup"><span data-stu-id="777ab-214">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="777ab-215">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="777ab-215">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="777ab-216">**Сообщение о отсылке**: в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="777ab-216">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="777ab-217">**Тип объекта**: **адрес электронной почты** (по умолчанию), **URL-адрес**или **вложение**.</span><span class="sxs-lookup"><span data-stu-id="777ab-217">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="777ab-218">**Формат отправки**: **идентификатор сетевого сообщения** (по умолчанию с соответствующим ЗНАЧЕНИЕМ в поле " **идентификатор сетевого сообщения** ") или " **файл** " (перейдите в локальный файл. EML или. MSG).</span><span class="sxs-lookup"><span data-stu-id="777ab-218">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="777ab-219">Обратите внимание, что если выбрать пункт **файл** , а затем выбрать **идентификатор сетевого сообщения**, начальное значение исчезнет.</span><span class="sxs-lookup"><span data-stu-id="777ab-219">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="777ab-220">**Recipients**: введите в поле аренда одного исходного получателя сообщения или нажмите кнопку **выбрать все** , чтобы определить всех получателей.</span><span class="sxs-lookup"><span data-stu-id="777ab-220">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="777ab-221">Вы также можете выбрать команду **выделить все** , а затем удалить отдельных получателей.</span><span class="sxs-lookup"><span data-stu-id="777ab-221">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="777ab-222">**Причина отправки**: **не должен быть заблокирован** (по умолчанию) или **должен быть заблокирован**.</span><span class="sxs-lookup"><span data-stu-id="777ab-222">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="777ab-223">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="777ab-223">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="777ab-224">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="777ab-224">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="777ab-225">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="777ab-225">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="777ab-226">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="777ab-226">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="777ab-227">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="777ab-227">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="777ab-228">**Удалить сообщения**: После нажатия кнопки **Да** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="777ab-228">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="777ab-229">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="777ab-229">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="777ab-230">Только ATP: использование центра безопасности & соответствия требованиям для управления файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="777ab-230">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="777ab-231">Процедуры для файлов, помещенных в карантин в этом разделе, доступны только для подписчиков ATP Plan 1 и Plan 2.</span><span class="sxs-lookup"><span data-stu-id="777ab-231">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="777ab-232">В организациях с ATP администраторы могут управлять файлами, помещенными в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="777ab-232">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="777ab-233">Просмотр файлов, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="777ab-233">View quarantined files</span></span>

1. <span data-ttu-id="777ab-234">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="777ab-234">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="777ab-235">Изменение **представления, помещенного в карантин** , в **файлы**значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="777ab-235">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="777ab-236">Можно выполнить сортировку по полю, щелкнув доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="777ab-236">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="777ab-237">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="777ab-237">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="777ab-238">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="777ab-238">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="777ab-239">По умолчанию столбцы помечаются звездочкой<sup>\*</sup>().</span><span class="sxs-lookup"><span data-stu-id="777ab-239">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="777ab-240">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-240">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-241">**Расположение**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-241">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-242">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-242">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-243">**URL-адрес файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-243">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-244">**Размер файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-244">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-245">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-245">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-246">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="777ab-246">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="777ab-247">**Определяется**</span><span class="sxs-lookup"><span data-stu-id="777ab-247">**Detected by**</span></span>

   - <span data-ttu-id="777ab-248">**Изменено временем**</span><span class="sxs-lookup"><span data-stu-id="777ab-248">**Modified by time**</span></span>

4. <span data-ttu-id="777ab-249">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="777ab-249">To filter the results, click **Filter**.</span></span> <span data-ttu-id="777ab-250">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="777ab-250">The available filters are:</span></span>

   - <span data-ttu-id="777ab-251">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="777ab-251">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="777ab-252">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="777ab-252">**Today**</span></span>

     - <span data-ttu-id="777ab-253">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="777ab-253">**Next 2 days**</span></span>

     - <span data-ttu-id="777ab-254">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="777ab-254">**Next 7 days**</span></span>

     - <span data-ttu-id="777ab-255">Настраиваемый диапазон дат и времени.</span><span class="sxs-lookup"><span data-stu-id="777ab-255">A custom date/time range.</span></span>

   - <span data-ttu-id="777ab-256">**Время получения**</span><span class="sxs-lookup"><span data-stu-id="777ab-256">**Received time**</span></span>

   - <span data-ttu-id="777ab-257">**Причина карантина**: единственным доступным значением является **вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="777ab-257">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="777ab-258">Когда вы обнаружите определенный файл в карантине, выберите его, чтобы просмотреть сведения о нем, и выполните действия с ним (например, просмотр, освобождение, Загрузка или удаление сообщения).</span><span class="sxs-lookup"><span data-stu-id="777ab-258">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="777ab-259">Результаты экспорта файлов</span><span class="sxs-lookup"><span data-stu-id="777ab-259">Export file results</span></span>

1. <span data-ttu-id="777ab-260">Выберите нужные файлы и нажмите **экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="777ab-260">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="777ab-261">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="777ab-261">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="777ab-262">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="777ab-262">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="777ab-263">Просмотр сведений о файле, помещенном в карантин</span><span class="sxs-lookup"><span data-stu-id="777ab-263">View quarantined file details</span></span>

<span data-ttu-id="777ab-264">При выборе файла в списке в всплывающей области **сведений** отображаются следующие сведения о файлах:</span><span class="sxs-lookup"><span data-stu-id="777ab-264">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="777ab-265">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="777ab-265">**File Name**</span></span>

- <span data-ttu-id="777ab-266">**URL-адрес файла**: URL-адрес, определяющий расположение файла (например, в SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="777ab-266">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="777ab-267">**Обнаружено вредоносное содержимое в** Дата и время, когда файл помещен в карантин.</span><span class="sxs-lookup"><span data-stu-id="777ab-267">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="777ab-268">**Expires**: Дата, когда файл будет удален из карантина.</span><span class="sxs-lookup"><span data-stu-id="777ab-268">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="777ab-269">**Определяется: ATP**(Advanced Threat protection) или модуль защиты от вредоносных программ корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="777ab-269">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="777ab-270">**Выпущено?**</span><span class="sxs-lookup"><span data-stu-id="777ab-270">**Released?**</span></span>

- <span data-ttu-id="777ab-271">**Имя вредоносной программы**</span><span class="sxs-lookup"><span data-stu-id="777ab-271">**Malware Name**</span></span>

- <span data-ttu-id="777ab-272">**Идентификатор документа**: уникальный идентификатор документа.</span><span class="sxs-lookup"><span data-stu-id="777ab-272">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="777ab-273">**Размер файла**: в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="777ab-273">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="777ab-274">**Организация** Уникальный идентификатор организации.</span><span class="sxs-lookup"><span data-stu-id="777ab-274">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="777ab-275">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="777ab-275">**Last modified**</span></span>

- <span data-ttu-id="777ab-276">**Изменено**: пользователь, который последним изменил файл.</span><span class="sxs-lookup"><span data-stu-id="777ab-276">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="777ab-277">**Безопасное значение хэш-алгоритма 256-bit (SHA-256)**: вы можете использовать это значение хэша, чтобы определить файл в других хранилищах репутации или в других расположениях в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="777ab-277">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="777ab-278">Выполнение действий с файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="777ab-278">Take action on quarantined files</span></span>

<span data-ttu-id="777ab-279">При выборе файла в списке можно выполнить следующие действия с файлом в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="777ab-279">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="777ab-280">**Выпуски файлов**: выберите (по умолчанию) или отменить выбор **файлов отчета в корпорацию Майкрософт для анализа**, а затем нажмите кнопку **освободить файлы**.</span><span class="sxs-lookup"><span data-stu-id="777ab-280">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="777ab-281">**Скачивание файла**</span><span class="sxs-lookup"><span data-stu-id="777ab-281">**Download file**</span></span>

- <span data-ttu-id="777ab-282">**Удаление файла из карантина**</span><span class="sxs-lookup"><span data-stu-id="777ab-282">**Remove file from quarantine**</span></span>

<span data-ttu-id="777ab-283">Если вы не Освободите или не удалите эти файлы, они будут удалены по истечении периода хранения на карантине по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="777ab-283">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="777ab-284">Действия с несколькими файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="777ab-284">Actions on multiple quarantined files</span></span>

<span data-ttu-id="777ab-285">При выборе нескольких файлов, помещенных в карантин, в списке (до 100) отображается раскрывающаяся панель **массовых действий** , в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="777ab-285">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="777ab-286">**Выпустить файлы**</span><span class="sxs-lookup"><span data-stu-id="777ab-286">**Release files**</span></span>

- <span data-ttu-id="777ab-287">**Удалить файлы**: после нажатия кнопки **Да** в появившемся предупреждении файлы сразу же удаляются.</span><span class="sxs-lookup"><span data-stu-id="777ab-287">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="777ab-288">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора (или соответствующие роли центра безопасности & соответствия требованиям) в Организации, войдите в [Центр безопасности & соответствия требованиям](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="777ab-288">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="777ab-289">Просмотр сообщений и файлов, помещенных в карантин, и управление ими с помощью Exchange Online PowerShell или отдельной Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="777ab-289">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="777ab-290">Для просмотра и управления сообщениями и файлами в карантине используются следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="777ab-290">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="777ab-291">Delete — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="777ab-291">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="777ab-292">Export — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="777ab-292">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="777ab-293">Get — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="777ab-293">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="777ab-294">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Обратите внимание, что этот командлет предназначен только для сообщений, а не от вредоносных файлов из ATP для SharePoint Online, OneDrive для бизнеса или Teams.</span><span class="sxs-lookup"><span data-stu-id="777ab-294">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="777ab-295">Release — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="777ab-295">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
