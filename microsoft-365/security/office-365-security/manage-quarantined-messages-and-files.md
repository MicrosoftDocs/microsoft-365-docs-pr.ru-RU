---
title: Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в Office 365
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
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857082"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="36e3d-104">Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в Office 365</span><span class="sxs-lookup"><span data-stu-id="36e3d-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="36e3d-105">Карантин содержит потенциально опасные или нежелательные сообщения в организациях Office 365 с почтовыми ящиками в организациях Exchange Online или в автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange</span><span class="sxs-lookup"><span data-stu-id="36e3d-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="36e3d-106">Дополнительные сведения см в разделе [Карантин в Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="36e3d-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="36e3d-107">Администраторы могут просматривать, освобождать и удалять все типы сообщений, помещенных в карантин, для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="36e3d-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="36e3d-108">Только администраторы могут управлять сообщениями, помещенными на карантин, высокой достоверностью фишинга, или в результате правил для процесса обработки почты (также называемых правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="36e3d-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="36e3d-109">Администраторы также могут сообщать ложные срабатывания корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="36e3d-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="36e3d-110">Администраторы в организациях с Office 365 Advanced Threat protection (ATP) также могут просматривать, загружать и удалять файлы, помещенные в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36e3d-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="36e3d-111">Вы просматриваете и управляете сообщения, помещенные в карантин, в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Office 365 клиентов; Exchange Online Protection PowerShell для автономных клиентов EOP).</span><span class="sxs-lookup"><span data-stu-id="36e3d-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="36e3d-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="36e3d-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="36e3d-113">Чтобы открыть центр соответствия требованиям & безопасности Office 365, перейдите на <https://protection.office.com>страницу.</span><span class="sxs-lookup"><span data-stu-id="36e3d-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="36e3d-114">Чтобы напрямую открыть страницу карантина, перейдите на <https://protection.office.com/quarantine>страницу.</span><span class="sxs-lookup"><span data-stu-id="36e3d-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="36e3d-115">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="36e3d-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="36e3d-116">Чтобы подключиться к Exchange Online Protection PowerShell, ознакомьтесь [со статьей подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="36e3d-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="36e3d-117">Для управления карантином в качестве администратора необходимо назначить разрешения. Управление разрешениями осуществляется ролью **карантина** в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="36e3d-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="36e3d-118">По умолчанию эта роль назначается группам ролей " **Управление организацией** " (глобальными администраторами), " **Администратор карантина**" и " **Администраторы безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="36e3d-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="36e3d-119">Дополнительные сведения см. [в разделе разрешения в центре безопасности & Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="36e3d-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="36e3d-120">Сообщения, помещенные в карантин, хранятся в течение определенного периода времени, по истечении которого они будут автоматически удалены:</span><span class="sxs-lookup"><span data-stu-id="36e3d-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="36e3d-121">Сообщения, помещенные в карантин политиками защиты от нежелательной почты (спама, фишинга и массовые сообщения электронной почты): 30 дней.</span><span class="sxs-lookup"><span data-stu-id="36e3d-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="36e3d-122">Это значение по умолчанию и максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="36e3d-122">This is the default and maximum value.</span></span> <span data-ttu-id="36e3d-123">Чтобы настроить это значение, ознакомьтесь со статьей [Настройка политик защиты от нежелательной почты в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="36e3d-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="36e3d-124">Сообщения, помещенные в карантин с помощью правил для обработки почтового процесса (действие правила **доставит сообщение в размещенный карантин**): 30 дней.</span><span class="sxs-lookup"><span data-stu-id="36e3d-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="36e3d-125">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="36e3d-125">You can't change this value.</span></span>

  - <span data-ttu-id="36e3d-126">Сообщения, содержащие вредоносную программу: 15 дней.</span><span class="sxs-lookup"><span data-stu-id="36e3d-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="36e3d-127">При истечении срока действия сообщения из карантина его невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="36e3d-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="36e3d-128">Использование центра безопасности & соответствия требованиям для управления сообщениями электронной почты, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="36e3d-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="36e3d-129">Просмотр электронной почты, помещенной в карантин</span><span class="sxs-lookup"><span data-stu-id="36e3d-129">View quarantined email</span></span>

1. <span data-ttu-id="36e3d-130">В центре безопасности и соответствия требованиям откройте **Карантин** \> **Обзор** \> **управления угрозами** .</span><span class="sxs-lookup"><span data-stu-id="36e3d-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="36e3d-131">Убедитесь, что для свойства **Просмотр в карантине** задано значение **электронной почты**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36e3d-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="36e3d-132">Вы можете отсортировать результаты, щелкнув заголовок доступного столбца.</span><span class="sxs-lookup"><span data-stu-id="36e3d-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="36e3d-133">Щелкните **изменить столбцы** , чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="36e3d-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="36e3d-134">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="36e3d-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="36e3d-135">**Доставлен**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-136">**Организатор**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-137">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-138">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-139">**Снят?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-140">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-141">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-142">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="36e3d-142">**Recipient**</span></span>

   - <span data-ttu-id="36e3d-143">**Код сообщения**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-143">**Message ID**</span></span>

   - <span data-ttu-id="36e3d-144">**Имя политики**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-144">**Policy name**</span></span>

   - <span data-ttu-id="36e3d-145">**Size**</span><span class="sxs-lookup"><span data-stu-id="36e3d-145">**Size**</span></span>

   - <span data-ttu-id="36e3d-146">**Direction**</span><span class="sxs-lookup"><span data-stu-id="36e3d-146">**Direction**</span></span>

   <span data-ttu-id="36e3d-147">Завершив настройку, нажмите кнопку **сохранить**или выберите пункт **по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="36e3d-148">Чтобы отфильтровать результаты, нажмите кнопку **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="36e3d-149">Доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="36e3d-149">The available filters are:</span></span>

   - <span data-ttu-id="36e3d-150">**Срок**действия: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="36e3d-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="36e3d-151">**Посещения**</span><span class="sxs-lookup"><span data-stu-id="36e3d-151">**Today**</span></span>

     - <span data-ttu-id="36e3d-152">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="36e3d-152">**Next 2 days**</span></span>

     - <span data-ttu-id="36e3d-153">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="36e3d-153">**Next 7 days**</span></span>

     - <span data-ttu-id="36e3d-154">**Custom**: **Введите начальную и** **конечную даты**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="36e3d-155">**Время получения**: введите **начальную** и **конечную даты**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="36e3d-156">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="36e3d-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="36e3d-157">**Политика**: сообщение, соответствующее условиям правила для обработки почтового ящика (которое также называется правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="36e3d-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="36e3d-158">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="36e3d-158">**Bulk**</span></span>

     - <span data-ttu-id="36e3d-159">**Фишинговых писем**</span><span class="sxs-lookup"><span data-stu-id="36e3d-159">**Phish**</span></span>

     - <span data-ttu-id="36e3d-160">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="36e3d-160">**Malware**</span></span>

     - <span data-ttu-id="36e3d-161">**Спам**</span><span class="sxs-lookup"><span data-stu-id="36e3d-161">**Spam**</span></span>

     - <span data-ttu-id="36e3d-162">**Фишинг с высокой степенью вероятности**</span><span class="sxs-lookup"><span data-stu-id="36e3d-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="36e3d-163">**Получатель электронной почты**: все пользователи или сообщения, отправленные вам.</span><span class="sxs-lookup"><span data-stu-id="36e3d-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="36e3d-164">Конечные пользователи могут управлять только отправленными ими сообщениями из карантина.</span><span class="sxs-lookup"><span data-stu-id="36e3d-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="36e3d-165">Чтобы очистить фильтр, нажмите кнопку **очистить**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="36e3d-166">Чтобы скрыть всплывающее окно фильтра, нажмите кнопку **Фильтр** еще раз.</span><span class="sxs-lookup"><span data-stu-id="36e3d-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="36e3d-167">Используйте **сортировку результатов по** умолчанию (кнопка **идентификатора сообщения** по умолчанию) и соответствующее значение для поиска определенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="36e3d-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="36e3d-168">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="36e3d-168">Wildcards aren't supported.</span></span> <span data-ttu-id="36e3d-169">Можно выполнить поиск по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="36e3d-169">You can search by the following values:</span></span>

   - <span data-ttu-id="36e3d-170">**Идентификатор сообщения**: глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="36e3d-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="36e3d-171">Например, [Трассировка сообщений](message-trace-scc.md) используется для поиска сообщения, отправленного пользователю в Организации, и определения того, что сообщение помещено в карантин, а не доставлено.</span><span class="sxs-lookup"><span data-stu-id="36e3d-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="36e3d-172">Обязательно укажите полное значение идентификатора сообщения, которое может включать угловые скобки (\<\>).</span><span class="sxs-lookup"><span data-stu-id="36e3d-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="36e3d-173">Пример: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="36e3d-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="36e3d-174">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="36e3d-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="36e3d-175">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="36e3d-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="36e3d-176">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="36e3d-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="36e3d-177">При поиске регистр символов не учитывается.</span><span class="sxs-lookup"><span data-stu-id="36e3d-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="36e3d-178">После ввода условий поиска нажмите кнопку ![обновить кнопку](../media/scc-quarantine-refresh.png) **Обновить, чтобы** отфильтровать результаты.</span><span class="sxs-lookup"><span data-stu-id="36e3d-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="36e3d-179">Когда вы обнаружите конкретное сообщение в карантине, выберите сообщение, чтобы просмотреть сведения о нем, и выполните действия с ним (например, просмотр, освобождение, Загрузка или удаление сообщения).</span><span class="sxs-lookup"><span data-stu-id="36e3d-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="36e3d-180">Экспорт результатов сообщений</span><span class="sxs-lookup"><span data-stu-id="36e3d-180">Export message results</span></span>

1. <span data-ttu-id="36e3d-181">Выберите интересующие вас сообщения и нажмите кнопку **Экспорт результатов**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="36e3d-182">Нажмите кнопку **Да** в окне подтверждения, в котором отобразится сообщение о том, что окно браузера открыто.</span><span class="sxs-lookup"><span data-stu-id="36e3d-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="36e3d-183">Когда экспорт будет готов, можно присвоить имя и выбрать расположение для скачивания CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="36e3d-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="36e3d-184">Просмотр сведений о сообщении в карантине</span><span class="sxs-lookup"><span data-stu-id="36e3d-184">View quarantined message details</span></span>

<span data-ttu-id="36e3d-185">При выборе сообщения электронной почты в списке в всплывающей панели **сведений** отображаются следующие сведения о сообщении:</span><span class="sxs-lookup"><span data-stu-id="36e3d-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="36e3d-186">**Идентификатор сообщения**: глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="36e3d-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="36e3d-187">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="36e3d-187">**Sender address**</span></span>

- <span data-ttu-id="36e3d-188">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="36e3d-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="36e3d-189">**Subject**</span><span class="sxs-lookup"><span data-stu-id="36e3d-189">**Subject**</span></span>

- <span data-ttu-id="36e3d-190">**Причина карантина**: показывает, что сообщение было определено как **Нежелательная**почта, **массовый**, **Фишинг**, сопоставляемое правило обработки почты (**правило транспорта**) или оно было определено как содержащее **вредоносную**программу.</span><span class="sxs-lookup"><span data-stu-id="36e3d-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="36e3d-191">**Получатели**: Если сообщение содержит несколько получателей, необходимо щелкнуть **Предварительный просмотр сообщения** или **Просмотр заголовка сообщения** , чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="36e3d-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="36e3d-192">**Срок действия**: Дата и время, когда сообщение будет автоматически удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="36e3d-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="36e3d-193">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="36e3d-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="36e3d-194">**Еще не выпущено**: все адреса электронной почты (при их наличии), для которых сообщение еще не было выпущено.</span><span class="sxs-lookup"><span data-stu-id="36e3d-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="36e3d-195">Выполнение действий на почтовом письме в карантине</span><span class="sxs-lookup"><span data-stu-id="36e3d-195">Take action on quarantined email</span></span>

<span data-ttu-id="36e3d-196">После выбора сообщения у вас есть несколько вариантов действий с сообщениями в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="36e3d-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="36e3d-197">**Сообщение об освобождении**: в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="36e3d-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="36e3d-198">**Сообщения отчетов в корпорацию Майкрософт для анализа**: этот параметр выбран по умолчанию и сообщает о том, что сообщение помещено в карантин в корпорацию Майкрософт как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="36e3d-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="36e3d-199">Если сообщение помещено в карантин, является пакетным, фишингом или содержит вредоносные программы, сообщение также передается группе анализа нежелательной почты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="36e3d-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="36e3d-200">В зависимости от их анализа можно настроить правила фильтрации нежелательной почты на уровне службы, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="36e3d-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="36e3d-201">Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="36e3d-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="36e3d-202">**Освобождение сообщений всем получателям**</span><span class="sxs-lookup"><span data-stu-id="36e3d-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="36e3d-203">**Освобождение сообщений определенным получателям**</span><span class="sxs-lookup"><span data-stu-id="36e3d-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="36e3d-204">**Разблокирование сообщений для других пользователей**</span><span class="sxs-lookup"><span data-stu-id="36e3d-204">**Release messages to other people**</span></span>

  <span data-ttu-id="36e3d-205">Когда все будет готово, нажмите кнопку **освободить сообщения**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="36e3d-206">Примечания по выпуску сообщений:</span><span class="sxs-lookup"><span data-stu-id="36e3d-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="36e3d-207">Вы не можете выпустить сообщение для одного и того же получателя несколько раз.</span><span class="sxs-lookup"><span data-stu-id="36e3d-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="36e3d-208">В списке потенциальных получателей будут отображаться только получатели, не получившие сообщение.</span><span class="sxs-lookup"><span data-stu-id="36e3d-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="36e3d-209">**Просмотр заголовка сообщения**: выберите эту ссылку, чтобы увидеть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="36e3d-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="36e3d-210">Чтобы проанализировать поля верхнего колонтитула и значения, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **анализатор заголовков сообщений Майкрософт** , чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите команду **Открыть на новой вкладке** , если не хотите покинуть Office 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="36e3d-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="36e3d-211">Вставьте заголовок сообщения на страницу в разделе анализатор заголовков сообщений и выберите **анализ заголовков**:</span><span class="sxs-lookup"><span data-stu-id="36e3d-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="36e3d-212">**Предварительная версия сообщения**: в открывшейся всплывающей области выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="36e3d-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="36e3d-213">**Представление исходного кода**: отображает HTML-версию текста сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="36e3d-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="36e3d-214">**Представление текста**: отображает текст сообщения в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="36e3d-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="36e3d-215">**Удалить из карантина**: после нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется без отправки первоначальным получателям.</span><span class="sxs-lookup"><span data-stu-id="36e3d-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="36e3d-216">**Сообщение о загрузке**: в открывшейся всплывающей области выберите **я понимаю риски, из которых можно скачать это сообщение** , чтобы сохранить локальную копию сообщения в формате EML.</span><span class="sxs-lookup"><span data-stu-id="36e3d-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="36e3d-217">**Сообщение о отсылке**: в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="36e3d-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="36e3d-218">**Тип объекта**: **адрес электронной почты** (по умолчанию), **URL-адрес**или **вложение**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="36e3d-219">**Формат отправки**: **идентификатор сетевого сообщения** (по умолчанию с соответствующим ЗНАЧЕНИЕМ в поле " **идентификатор сетевого сообщения** ") или " **файл** " (перейдите в локальный файл. EML или. MSG).</span><span class="sxs-lookup"><span data-stu-id="36e3d-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="36e3d-220">Обратите внимание, что если выбрать пункт **файл** , а затем выбрать **идентификатор сетевого сообщения**, начальное значение исчезнет.</span><span class="sxs-lookup"><span data-stu-id="36e3d-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="36e3d-221">**Recipients**: введите в поле аренда одного исходного получателя сообщения или нажмите кнопку **выбрать все** , чтобы определить всех получателей.</span><span class="sxs-lookup"><span data-stu-id="36e3d-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="36e3d-222">Вы также можете выбрать команду **выделить все** , а затем удалить отдельных получателей.</span><span class="sxs-lookup"><span data-stu-id="36e3d-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="36e3d-223">**Причина отправки**: **не должен быть заблокирован** (по умолчанию) или **должен быть заблокирован**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="36e3d-224">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="36e3d-225">Если сообщение не освобождено или удалено, оно будет удалено по истечении периода хранения на карантине по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36e3d-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="36e3d-226">Выполнение действий над несколькими помещенными в карантин сообщениями электронной почты</span><span class="sxs-lookup"><span data-stu-id="36e3d-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="36e3d-227">При выборе нескольких сообщений, помещенных в карантин, в списке (до 100) отображается раскрывающаяся панель **массовых действий** , в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="36e3d-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="36e3d-228">**Выпуски сообщений**: при выпуске одного сообщения параметры будут такими же, как и в случае, если вы не можете выбрать **отпустить сообщения для определенных получателей**; Вы можете выбрать только **сообщение Release для всех получателей** или **отпустить сообщения для других пользователей**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="36e3d-229">**Удалить сообщения**: после нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется без отправки первоначальным получателям.</span><span class="sxs-lookup"><span data-stu-id="36e3d-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="36e3d-230">Когда все будет готово, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="36e3d-231">Только ATP: использование центра безопасности & соответствия требованиям для управления файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="36e3d-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="36e3d-232">Процедуры для файлов, помещенных в карантин в этом разделе, доступны только для подписчиков ATP Plan 1 и Plan 2.</span><span class="sxs-lookup"><span data-stu-id="36e3d-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="36e3d-233">В организациях с ATP администраторы могут управлять файлами, помещенными в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36e3d-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="36e3d-234">Просмотр файлов, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="36e3d-234">View quarantined files</span></span>

1. <span data-ttu-id="36e3d-235">В центре безопасности и соответствия требованиям откройте **Карантин** \> **Обзор** \> **управления угрозами** .</span><span class="sxs-lookup"><span data-stu-id="36e3d-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="36e3d-236">Изменение **представления, помещенного в карантин** , в **файлы**значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36e3d-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="36e3d-237">Можно выполнить сортировку по полю, щелкнув доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="36e3d-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="36e3d-238">Вы можете отсортировать результаты, щелкнув заголовок доступного столбца.</span><span class="sxs-lookup"><span data-stu-id="36e3d-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="36e3d-239">Щелкните **изменить столбцы** , чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="36e3d-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="36e3d-240">По умолчанию столбцы помечаются звездочкой<sup>\*</sup>().</span><span class="sxs-lookup"><span data-stu-id="36e3d-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="36e3d-241">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-242">**Расположение**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-243">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-244">**URL-адрес файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-245">**Размер файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-246">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-247">**Снят?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36e3d-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="36e3d-248">**Определяется**</span><span class="sxs-lookup"><span data-stu-id="36e3d-248">**Detected by**</span></span>

   - <span data-ttu-id="36e3d-249">**Изменено временем**</span><span class="sxs-lookup"><span data-stu-id="36e3d-249">**Modified by time**</span></span>

4. <span data-ttu-id="36e3d-250">Чтобы отфильтровать результаты, нажмите кнопку **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="36e3d-251">Доступны следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="36e3d-251">The available filters are:</span></span>

   - <span data-ttu-id="36e3d-252">**Срок**действия: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="36e3d-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="36e3d-253">**Посещения**</span><span class="sxs-lookup"><span data-stu-id="36e3d-253">**Today**</span></span>

     - <span data-ttu-id="36e3d-254">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="36e3d-254">**Next 2 days**</span></span>

     - <span data-ttu-id="36e3d-255">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="36e3d-255">**Next 7 days**</span></span>

     - <span data-ttu-id="36e3d-256">Настраиваемый диапазон дат и времени.</span><span class="sxs-lookup"><span data-stu-id="36e3d-256">A custom date/time range.</span></span>

   - <span data-ttu-id="36e3d-257">**Время получения**</span><span class="sxs-lookup"><span data-stu-id="36e3d-257">**Received time**</span></span>

   - <span data-ttu-id="36e3d-258">**Причина карантина**: единственным доступным значением является **вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="36e3d-259">Когда вы обнаружите определенный файл в карантине, выберите его, чтобы просмотреть сведения о нем, и выполните действия с ним (например, просмотр, освобождение, Загрузка или удаление сообщения).</span><span class="sxs-lookup"><span data-stu-id="36e3d-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="36e3d-260">Результаты экспорта файлов</span><span class="sxs-lookup"><span data-stu-id="36e3d-260">Export file results</span></span>

1. <span data-ttu-id="36e3d-261">Выберите нужные файлы и нажмите **экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="36e3d-262">Нажмите кнопку **Да** в окне подтверждения, в котором отобразится сообщение о том, что окно браузера открыто.</span><span class="sxs-lookup"><span data-stu-id="36e3d-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="36e3d-263">Когда экспорт будет готов, можно присвоить имя и выбрать расположение для скачивания CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="36e3d-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="36e3d-264">Просмотр сведений о файле, помещенном в карантин</span><span class="sxs-lookup"><span data-stu-id="36e3d-264">View quarantined file details</span></span>

<span data-ttu-id="36e3d-265">При выборе файла в списке в всплывающей области **сведений** отображаются следующие сведения о файлах:</span><span class="sxs-lookup"><span data-stu-id="36e3d-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="36e3d-266">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="36e3d-266">**File Name**</span></span>

- <span data-ttu-id="36e3d-267">**URL-адрес файла**: URL-адрес, определяющий расположение файла (например, в SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="36e3d-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="36e3d-268">**Обнаружено вредоносное содержимое в** Дата и время, когда файл помещен в карантин.</span><span class="sxs-lookup"><span data-stu-id="36e3d-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="36e3d-269">**Expires**: Дата, когда файл будет удален из карантина.</span><span class="sxs-lookup"><span data-stu-id="36e3d-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="36e3d-270">**Определяется: ATP**(Advanced Threat protection) или модуль защиты от вредоносных программ корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="36e3d-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="36e3d-271">**Снят?**</span><span class="sxs-lookup"><span data-stu-id="36e3d-271">**Released?**</span></span>

- <span data-ttu-id="36e3d-272">**Имя вредоносной программы**</span><span class="sxs-lookup"><span data-stu-id="36e3d-272">**Malware Name**</span></span>

- <span data-ttu-id="36e3d-273">**Идентификатор документа**: уникальный идентификатор документа.</span><span class="sxs-lookup"><span data-stu-id="36e3d-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="36e3d-274">**Размер файла**: в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="36e3d-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="36e3d-275">**Организация** Уникальный идентификатор организации.</span><span class="sxs-lookup"><span data-stu-id="36e3d-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="36e3d-276">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="36e3d-276">**Last modified**</span></span>

- <span data-ttu-id="36e3d-277">**Изменено**: пользователь, который последним изменил файл.</span><span class="sxs-lookup"><span data-stu-id="36e3d-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="36e3d-278">**Безопасное значение хэш-алгоритма 256-bit (SHA-256)**: вы можете использовать это значение хэша, чтобы определить файл в других хранилищах репутации или в других расположениях в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="36e3d-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="36e3d-279">Выполнение действий с файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="36e3d-279">Take action on quarantined files</span></span>

<span data-ttu-id="36e3d-280">При выборе файла в списке можно выполнить следующие действия с файлом в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="36e3d-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="36e3d-281">**Выпуски файлов**: выберите (по умолчанию) или отменить выбор **файлов отчета в корпорацию Майкрософт для анализа**, а затем нажмите кнопку **освободить файлы**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="36e3d-282">**Скачивание файла**</span><span class="sxs-lookup"><span data-stu-id="36e3d-282">**Download file**</span></span>

- <span data-ttu-id="36e3d-283">**Удаление файла из карантина**</span><span class="sxs-lookup"><span data-stu-id="36e3d-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="36e3d-284">Если вы не Освободите или не удалите эти файлы, они будут удалены по истечении периода хранения на карантине по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36e3d-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="36e3d-285">Действия с несколькими файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="36e3d-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="36e3d-286">При выборе нескольких файлов, помещенных в карантин, в списке (до 100) отображается раскрывающаяся панель **массовых действий** , в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="36e3d-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="36e3d-287">**Выпустить файлы**</span><span class="sxs-lookup"><span data-stu-id="36e3d-287">**Release files**</span></span>

- <span data-ttu-id="36e3d-288">**Удалить файлы**: после нажатия кнопки **Да** в появившемся предупреждении файлы сразу же удаляются.</span><span class="sxs-lookup"><span data-stu-id="36e3d-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="36e3d-289">Когда все будет готово, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="36e3d-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="36e3d-290">Просмотр сообщений и файлов, помещенных в карантин, и управление ими с помощью Exchange Online PowerShell или отдельной Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="36e3d-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="36e3d-291">Для просмотра и управления сообщениями и файлами в карантине используются следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="36e3d-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="36e3d-292">Delete — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="36e3d-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="36e3d-293">Export — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="36e3d-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="36e3d-294">Get — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="36e3d-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="36e3d-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Обратите внимание, что этот командлет предназначен только для сообщений, а не от вредоносных файлов из ATP для SharePoint Online, OneDrive для бизнеса или Teams.</span><span class="sxs-lookup"><span data-stu-id="36e3d-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="36e3d-296">Release — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="36e3d-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
