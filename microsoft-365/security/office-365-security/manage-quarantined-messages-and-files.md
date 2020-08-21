---
title: Управление сообщениями и файлами на карантине в качестве администратора
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как просматривать сообщения в карантине и управлять ими для всех пользователей в Exchange Online Protection (EOP). Администраторы в организациях, использующих Office 365 Advanced Threat Protection (Office 365 ATP), также могут управлять файлами на карантине в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.openlocfilehash: 5da67f15a933694c1aef059ff18945122e3ee2e8
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827067"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="35b69-104">Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в EOP</span><span class="sxs-lookup"><span data-stu-id="35b69-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="35b69-105">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="35b69-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="35b69-106">Дополнительные сведения см. в статье "Сообщения [электронной почты, помещенные на карантин" в службе EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="35b69-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="35b69-107">Администраторы могут просматривать, выпускать и удалять все типы сообщений, помещенных в карантин, для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="35b69-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="35b69-108">Управлять сообщениями, помещенными в карантин как вредоносные программы, фишинговыми сообщениями с высоким уровнем вероятности или с помощью правил потока обработки почты (их также называют правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="35b69-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="35b69-109">Администраторы также могут сообщать о ложных срабатываниях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35b69-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="35b69-110">Администраторы в организациях, у которых используется защита от угроз на Office 365 ADR (Office 365 ATP), также могут просматривать, скачивать и удалять файлы на карантине в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="35b69-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="35b69-111">Вы просматривайте сообщения на карантине и управляете ими в Центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономную оболочку PowerShell EOP для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="35b69-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="35b69-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="35b69-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="35b69-113">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="35b69-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="35b69-114">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="35b69-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="35b69-115">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="35b69-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="35b69-116">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="35b69-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="35b69-117">Для управления карантием в качестве администратора вам должны быть назначены разрешения. Управлять ими управляет роль **"Карантин"** в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="35b69-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="35b69-118">По умолчанию эта роль назначается группам **ролей "Управление организацией** (глобальные администраторы"), **"Администратор карантина"** **и "Администратор** безопасности" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="35b69-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="35b69-119">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="35b69-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="35b69-120">Помещенные на карантин сообщения сохраняются в течение периода времени, по умолчанию перед их автоматическим удалением.</span><span class="sxs-lookup"><span data-stu-id="35b69-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="35b69-121">Сообщения, помещенные в карантин политиками защиты от нежелательной почты (спам, фишинговые и массовая рассылка): 30 дней.</span><span class="sxs-lookup"><span data-stu-id="35b69-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="35b69-122">Это значение по умолчанию и максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="35b69-122">This is the default and maximum value.</span></span> <span data-ttu-id="35b69-123">Чтобы настроить это значение, см. раздел ["Настройка политик защиты от нежелательной почты".](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="35b69-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="35b69-124">Сообщения, содержащие вредоносную программу: 15 дней.</span><span class="sxs-lookup"><span data-stu-id="35b69-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="35b69-125">По истечении срока действия сообщения в карантине его нельзя восстановить.</span><span class="sxs-lookup"><span data-stu-id="35b69-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="35b69-126">Использование Центра безопасности & для управления сообщениями электронной почты в карантине</span><span class="sxs-lookup"><span data-stu-id="35b69-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="35b69-127">Просмотр электронной почты в карантине</span><span class="sxs-lookup"><span data-stu-id="35b69-127">View quarantined email</span></span>

1. <span data-ttu-id="35b69-128">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="35b69-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="35b69-129">Убедитесь, что **для параметра view quarantined** задано значение электронной почты **по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="35b69-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="35b69-130">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="35b69-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="35b69-131">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="35b69-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="35b69-132">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="35b69-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="35b69-133">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-134">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-135">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-136">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-137">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-138">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-139">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="35b69-139">**Recipient**</span></span>

   - <span data-ttu-id="35b69-140">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="35b69-140">**Message ID**</span></span>

   - <span data-ttu-id="35b69-141">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="35b69-141">**Policy name**</span></span>

   - <span data-ttu-id="35b69-142">**Размер**</span><span class="sxs-lookup"><span data-stu-id="35b69-142">**Size**</span></span>

   - <span data-ttu-id="35b69-143">**Направление**</span><span class="sxs-lookup"><span data-stu-id="35b69-143">**Direction**</span></span>

   <span data-ttu-id="35b69-144">Когда все будет готово, нажмите кнопку **сохранить**или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="35b69-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="35b69-145">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="35b69-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="35b69-146">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="35b69-146">The available filters are:</span></span>

   - <span data-ttu-id="35b69-147">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="35b69-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="35b69-148">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="35b69-148">**Today**</span></span>

     - <span data-ttu-id="35b69-149">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="35b69-149">**Next 2 days**</span></span>

     - <span data-ttu-id="35b69-150">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="35b69-150">**Next 7 days**</span></span>

     - <span data-ttu-id="35b69-151">**Настраиваемые**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="35b69-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="35b69-152">**Время получения**: введите \*\*дату начала \*\* и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="35b69-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="35b69-153">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="35b69-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="35b69-154">**Политика:** сообщение соответствует условиям правила потока обработки почты (другое название — правило транспорта).</span><span class="sxs-lookup"><span data-stu-id="35b69-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="35b69-155">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="35b69-155">**Bulk**</span></span>

     - <span data-ttu-id="35b69-156">**Фишинг**</span><span class="sxs-lookup"><span data-stu-id="35b69-156">**Phish**</span></span>

     - <span data-ttu-id="35b69-157">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="35b69-157">**Malware**</span></span>

     - <span data-ttu-id="35b69-158">**Спам**</span><span class="sxs-lookup"><span data-stu-id="35b69-158">**Spam**</span></span>

     - <span data-ttu-id="35b69-159">**Фишинг с высокой достоверностью**</span><span class="sxs-lookup"><span data-stu-id="35b69-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="35b69-160">**Получатель электронной почты:** Все пользователи или только сообщения, отправленные вам.</span><span class="sxs-lookup"><span data-stu-id="35b69-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="35b69-161">Конечные пользователи могут управлять сообщениями, отправленными в карантин.</span><span class="sxs-lookup"><span data-stu-id="35b69-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="35b69-162">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="35b69-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="35b69-163">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="35b69-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="35b69-164">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="35b69-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="35b69-165">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="35b69-165">Wildcards aren't supported.</span></span> <span data-ttu-id="35b69-166">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="35b69-166">You can search by the following values:</span></span>

   - <span data-ttu-id="35b69-167">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="35b69-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="35b69-168">Например, трассировка [сообщений использовалась](message-trace-scc.md) для поиска сообщения, отправленного пользователю в организации, и определили, что сообщение помещено в карантин, а не доставлено.</span><span class="sxs-lookup"><span data-stu-id="35b69-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="35b69-169">Не забудьте включить полный идентификатор сообщения, который может содержать угловые скобки ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="35b69-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="35b69-170">Пример: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="35b69-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="35b69-171">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="35b69-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="35b69-172">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="35b69-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="35b69-173">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="35b69-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="35b69-174">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="35b69-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="35b69-175">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="35b69-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="35b69-176">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="35b69-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="35b69-177">Экспортировать результаты сообщения</span><span class="sxs-lookup"><span data-stu-id="35b69-177">Export message results</span></span>

1. <span data-ttu-id="35b69-178">Выберите интересующие вас сообщения и нажмите **Экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="35b69-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="35b69-179">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="35b69-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="35b69-180">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="35b69-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="35b69-181">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="35b69-181">View quarantined message details</span></span>

<span data-ttu-id="35b69-182">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="35b69-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="35b69-183">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="35b69-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="35b69-184">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="35b69-184">**Sender address**</span></span>

- <span data-ttu-id="35b69-185">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="35b69-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="35b69-186">**Тема**</span><span class="sxs-lookup"><span data-stu-id="35b69-186">**Subject**</span></span>

- <span data-ttu-id="35b69-187">**Причина карантина:** показывает, распознано ли сообщение как **спам,** массовая рассылка, **фишинг,** сопоставленное правилу потока обработки почты (**правило**транспорта) или было обнаружено как содержащее **вредоносную программу.** **Bulk**</span><span class="sxs-lookup"><span data-stu-id="35b69-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="35b69-188">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="35b69-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="35b69-189">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="35b69-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="35b69-190">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="35b69-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="35b69-191">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="35b69-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="35b69-192">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="35b69-192">Take action on quarantined email</span></span>

<span data-ttu-id="35b69-193">После выбора сообщения в области всплывающего **Details** окна "Сведения" можно использовать несколько вариантов действий.</span><span class="sxs-lookup"><span data-stu-id="35b69-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="35b69-194">**Отпущено**сообщение: в появившейся всплывающей панели выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="35b69-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="35b69-195">**Сообщайте о сообщениях в корпорацию Майкрософт**для анализа: этот параметр выбирается по умолчанию и сообщает корпорации Майкрософт о ложном срабатывании.</span><span class="sxs-lookup"><span data-stu-id="35b69-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="35b69-196">Если сообщение было помещено в карантин как спам, массовая рассылка или содержит вредоносную программу, сообщение также отправляется рабочей группе корпорации Майкрософт по анализу нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="35b69-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="35b69-197">В зависимости от результата анализа могут быть скорректированы правила фильтрации нежелательной почты на уровне службы, чтобы продолжить доставку сообщения.</span><span class="sxs-lookup"><span data-stu-id="35b69-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="35b69-198">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="35b69-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="35b69-199">**Разблокировка сообщений для всех получателей**</span><span class="sxs-lookup"><span data-stu-id="35b69-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="35b69-200">**Разблокировка сообщений для определенных получателей**</span><span class="sxs-lookup"><span data-stu-id="35b69-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="35b69-201">**Разблокировка сообщений другим людям**</span><span class="sxs-lookup"><span data-stu-id="35b69-201">**Release messages to other people**</span></span>

  <span data-ttu-id="35b69-202">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="35b69-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="35b69-203">Примечания об освобождение сообщений:</span><span class="sxs-lookup"><span data-stu-id="35b69-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="35b69-204">Освободить сообщение одному получателю невозможно более одного раза.</span><span class="sxs-lookup"><span data-stu-id="35b69-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="35b69-205">Только получатели, не получившие это сообщение, будут присутствовать в списке потенциальных получателей.</span><span class="sxs-lookup"><span data-stu-id="35b69-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="35b69-206">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="35b69-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="35b69-207">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="35b69-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="35b69-208">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="35b69-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="35b69-209">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="35b69-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="35b69-210">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="35b69-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="35b69-211">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="35b69-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="35b69-212">**Удалить из карантина:** после нажатия кнопки **"Да"** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="35b69-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="35b69-213">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="35b69-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="35b69-214">**"Отправить сообщение"** В появившейся всплывающей панели выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="35b69-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="35b69-215">**Тип объекта:** **Электронная почта** (по умолчанию), **URL-адрес**или **вложение.**</span><span class="sxs-lookup"><span data-stu-id="35b69-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="35b69-216">**Формат отправки:** **идентификатор сетевого сообщения** (по умолчанию с соответствующим значением в **поле "Идентификатор сетевого** сообщения") или **файлом** (перейдите к локальному EML- или MSG-файлу).</span><span class="sxs-lookup"><span data-stu-id="35b69-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="35b69-217">Обратите внимание, что если выбрать **"Файл"** и **выбрать идентификатор сетевого сообщения,** первоначальное значение исчезнет.</span><span class="sxs-lookup"><span data-stu-id="35b69-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="35b69-218">**Получатели:** укажите аренду одного исходного получателя сообщения или нажмите кнопку **"Выбрать** все", чтобы указать всех получателей.</span><span class="sxs-lookup"><span data-stu-id="35b69-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="35b69-219">Можно также щелкнуть **"Выбрать все"** и выборочно удалить отдельных получателей.</span><span class="sxs-lookup"><span data-stu-id="35b69-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="35b69-220">**Причина отправки:** **не следует заблокировать** (по умолчанию) или что это **значение следует заблокировать.**</span><span class="sxs-lookup"><span data-stu-id="35b69-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="35b69-221">По завершении нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="35b69-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="35b69-222">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="35b69-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="35b69-223">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="35b69-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="35b69-224">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="35b69-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="35b69-225">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="35b69-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="35b69-226">Рассмотрим следующий сценарий: john@gmail.com сообщение отправляется в faith@contoso.com и john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="35b69-226">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="35b69-227">Gmail позволяет перенести это сообщение в две копии, которые оба перенаправляются в карантин как фишинг в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35b69-227">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="35b69-228">Администратор снимает оба эти сообщения в admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="35b69-228">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="35b69-229">Доставляется первое опущенное сообщение, постуждавшее в почтовый ящик администратора.</span><span class="sxs-lookup"><span data-stu-id="35b69-229">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="35b69-230">Второе сообщение определяется как дублирование и пропускается.</span><span class="sxs-lookup"><span data-stu-id="35b69-230">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="35b69-231">Сообщение определяется как дубликаты при наличии одинаковых идентификаторов и времени получения.</span><span class="sxs-lookup"><span data-stu-id="35b69-231">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="35b69-232">**Удалить сообщения**: После нажатия кнопки **Да** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="35b69-232">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="35b69-233">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="35b69-233">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="35b69-234">Только ATP: использование Центра безопасности & для управления файлами на карантине</span><span class="sxs-lookup"><span data-stu-id="35b69-234">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="35b69-235">Процедуры для файлов в этом разделе, помещенных на карантин, доступны только для подписчиков ATP (план 1) и плана 2.</span><span class="sxs-lookup"><span data-stu-id="35b69-235">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="35b69-236">В организациях с ATP администраторы могут управлять файлами на карантине в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="35b69-236">In organizations with ATP, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="35b69-237">Просмотр файлов, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="35b69-237">View quarantined files</span></span>

1. <span data-ttu-id="35b69-238">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="35b69-238">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="35b69-239">Изменение представления **в карантине** на файлы **значений по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="35b69-239">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="35b69-240">Вы можете отсортировать данные по полю, щелкнув доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="35b69-240">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="35b69-241">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="35b69-241">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="35b69-242">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="35b69-242">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="35b69-243">Столбцы по умолчанию помечаются звездочкой ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="35b69-243">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="35b69-244">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-244">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-245">**Расположение**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-245">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-246">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-246">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-247">**URL-адрес файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-247">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-248">**Размер файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-248">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-249">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-249">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-250">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35b69-250">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="35b69-251">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="35b69-251">**Detected by**</span></span>

   - <span data-ttu-id="35b69-252">**Изменено по времени**</span><span class="sxs-lookup"><span data-stu-id="35b69-252">**Modified by time**</span></span>

4. <span data-ttu-id="35b69-253">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="35b69-253">To filter the results, click **Filter**.</span></span> <span data-ttu-id="35b69-254">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="35b69-254">The available filters are:</span></span>

   - <span data-ttu-id="35b69-255">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="35b69-255">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="35b69-256">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="35b69-256">**Today**</span></span>

     - <span data-ttu-id="35b69-257">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="35b69-257">**Next 2 days**</span></span>

     - <span data-ttu-id="35b69-258">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="35b69-258">**Next 7 days**</span></span>

     - <span data-ttu-id="35b69-259">Пользовательский диапазон дат и времени.</span><span class="sxs-lookup"><span data-stu-id="35b69-259">A custom date/time range.</span></span>

   - <span data-ttu-id="35b69-260">**Время получения**</span><span class="sxs-lookup"><span data-stu-id="35b69-260">**Received time**</span></span>

   - <span data-ttu-id="35b69-261">**Причина карантина:** доступно только значение **"Вредоносная программа".**</span><span class="sxs-lookup"><span data-stu-id="35b69-261">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="35b69-262">Когда вы найдете файл, помещенный в карантин, выберите его, чтобы просмотреть сведения о нем и принять к нему действие (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="35b69-262">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="35b69-263">Экспорт результатов файла</span><span class="sxs-lookup"><span data-stu-id="35b69-263">Export file results</span></span>

1. <span data-ttu-id="35b69-264">Выберите необходимые файлы и нажмите кнопку экспорта **результатов.**</span><span class="sxs-lookup"><span data-stu-id="35b69-264">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="35b69-265">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="35b69-265">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="35b69-266">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="35b69-266">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="35b69-267">Просмотр сведений о файле, помещенном в карантин</span><span class="sxs-lookup"><span data-stu-id="35b69-267">View quarantined file details</span></span>

<span data-ttu-id="35b69-268">При выборе файла в списке в всплывающем окне "Сведения" **появляются** следующие сведения о файле:</span><span class="sxs-lookup"><span data-stu-id="35b69-268">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="35b69-269">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="35b69-269">**File Name**</span></span>

- <span data-ttu-id="35b69-270">**URL-адрес**файла: URL-адрес, определяющий расположение файла (например, в SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="35b69-270">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="35b69-271">**Обнаружение вредоносного содержимого** Дата и время помещения файла в карантин.</span><span class="sxs-lookup"><span data-stu-id="35b69-271">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="35b69-272">**Истекает:** дата удаления файла из карантина.</span><span class="sxs-lookup"><span data-stu-id="35b69-272">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="35b69-273">**Обнаружено:** ATP (Advanced Threat Protection) или антивредоносное средство Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35b69-273">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="35b69-274">**Выпущено?**</span><span class="sxs-lookup"><span data-stu-id="35b69-274">**Released?**</span></span>

- <span data-ttu-id="35b69-275">**Имя вредоносной программ**</span><span class="sxs-lookup"><span data-stu-id="35b69-275">**Malware Name**</span></span>

- <span data-ttu-id="35b69-276">**Идентификатор документа:** уникальный идентификатор документа.</span><span class="sxs-lookup"><span data-stu-id="35b69-276">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="35b69-277">**Размер файла:** в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="35b69-277">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="35b69-278">**Организация** Уникальный идентификатор организации.</span><span class="sxs-lookup"><span data-stu-id="35b69-278">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="35b69-279">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="35b69-279">**Last modified**</span></span>

- <span data-ttu-id="35b69-280">**Изменено пользователем:** пользователь, последним изменивший файл.</span><span class="sxs-lookup"><span data-stu-id="35b69-280">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="35b69-281">**256-разрядный алгоритм по хэш-алгоритму (SHA-256)**: это значение хэш-функции можно использовать для определения файла в других хранилищах репутации или в других местах в среде.</span><span class="sxs-lookup"><span data-stu-id="35b69-281">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="35b69-282">Выполнение действий с файлами, помещенные в карантин</span><span class="sxs-lookup"><span data-stu-id="35b69-282">Take action on quarantined files</span></span>

<span data-ttu-id="35b69-283">При выборе файла в списке в всплывающем элементе можно выполнить следующие действия: **Details**</span><span class="sxs-lookup"><span data-stu-id="35b69-283">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="35b69-284">**Файлы выпуска:** выберите (по умолчанию) или отмените выбор **файлов отчета в корпорацию Майкрософт для анализа,** а затем нажмите кнопку **"Выпустить файлы".**</span><span class="sxs-lookup"><span data-stu-id="35b69-284">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="35b69-285">**Скачивание файла**</span><span class="sxs-lookup"><span data-stu-id="35b69-285">**Download file**</span></span>

- <span data-ttu-id="35b69-286">**Удаление файла из карантина**</span><span class="sxs-lookup"><span data-stu-id="35b69-286">**Remove file from quarantine**</span></span>

<span data-ttu-id="35b69-287">Если вы не освободите или не удалите файлы, они будут удалены после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="35b69-287">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="35b69-288">Действия с несколькими файлами, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="35b69-288">Actions on multiple quarantined files</span></span>

<span data-ttu-id="35b69-289">При выборе нескольких файлов в карантине в списке (до 100) появляется **всплывающие** панели массовых действий, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="35b69-289">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="35b69-290">**Выпуск файлов**</span><span class="sxs-lookup"><span data-stu-id="35b69-290">**Release files**</span></span>

- <span data-ttu-id="35b69-291">**Удалите файлы:** после нажатия **кнопки "Да"** в появляющемся предупреждении файлы немедленно удаляются.</span><span class="sxs-lookup"><span data-stu-id="35b69-291">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="35b69-292">Используя рабочую или учебную учетную запись с правами глобального администратора (или соответствующими ролями в Центре соответствия требованиям &), выполните вход и перейдите в [Центр безопасности & соответствия](../../compliance/go-to-the-securitycompliance-center.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="35b69-292">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="35b69-293">Просмотр сообщений и файлов из карантина с помощью Exchange Online PowerShell или автономной службы EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="35b69-293">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="35b69-294">Командлеты, используемые для просмотра сообщений и файлов, помещенных на карантин, и управления ими являются:</span><span class="sxs-lookup"><span data-stu-id="35b69-294">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="35b69-295">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="35b69-295">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="35b69-296">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="35b69-296">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="35b69-297">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="35b69-297">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="35b69-298">[Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)обратите внимание, что этот командлет предназначен только для сообщений, а не файлов вредоносных программ из ATP для SharePoint Online, OneDrive для бизнеса или Teams.</span><span class="sxs-lookup"><span data-stu-id="35b69-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="35b69-299">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="35b69-299">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
