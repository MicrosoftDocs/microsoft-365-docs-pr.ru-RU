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
description: Администраторы могут узнать, как просматривать и управлять сообщениями, помещенными в карантин, для всех пользователей в Exchange Online Protection (EOP). Администраторы в организациях с защитником Майкрософт для Office 365 также могут управлять файлами, помещенными в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.openlocfilehash: 8f4ca5caef9bf244315db2271011126ad4d7976e
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616780"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="a5430-104">Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в EOP</span><span class="sxs-lookup"><span data-stu-id="a5430-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a5430-105">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="a5430-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="a5430-106">Дополнительные сведения см. [в статье сообщения электронной почты, помещенные в карантин в EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a5430-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="a5430-107">Администраторы могут просматривать, освобождать и удалять все типы сообщений, помещенных в карантин, для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a5430-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="a5430-108">Только администраторы могут управлять сообщениями, помещенными на карантин, высокой достоверностью фишинга, или в результате правил для процесса обработки почты (также называемых правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="a5430-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a5430-109">Администраторы также могут сообщать ложные срабатывания корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a5430-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="a5430-110">Администраторы в организациях с защитником Майкрософт для Office 365 также могут просматривать, загружать и удалять файлы, помещенные в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5430-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="a5430-111">Вы просматриваете и управляете сообщения, помещенные в карантин, в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="a5430-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a5430-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="a5430-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a5430-113">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="a5430-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="a5430-114">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="a5430-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="a5430-115">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a5430-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a5430-116">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a5430-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a5430-117">Для управления карантином в качестве администратора необходимо назначить разрешения. Управление разрешениями осуществляется ролью **карантина** в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a5430-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="a5430-118">По умолчанию эта роль назначается группам ролей " **Управление организацией** " (глобальными администраторами), " **Администратор карантина**" и " **Администраторы безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a5430-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="a5430-119">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a5430-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a5430-120">Сообщения, помещенные в карантин, хранятся в течение определенного периода времени, по истечении которого они будут автоматически удалены:</span><span class="sxs-lookup"><span data-stu-id="a5430-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="a5430-121">30 дней для сообщений, помещенных в карантин политиками защиты от нежелательной почты (спама, фишинга и массовых сообщений электронной почты).</span><span class="sxs-lookup"><span data-stu-id="a5430-121">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="a5430-122">Это значение по умолчанию и максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="a5430-122">This is the default and maximum value.</span></span> <span data-ttu-id="a5430-123">Чтобы настроить (нижнее) это значение, ознакомьтесь со статьей [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a5430-123">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="a5430-124">15 дней для сообщений, содержащих вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="a5430-124">15 days for messages that contain malware.</span></span>

  - <span data-ttu-id="a5430-125">15 дней для файлов, помещенных на карантин для SharePoint, OneDrive и Microsoft Teams в защитник для Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5430-125">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="a5430-126">При истечении срока действия сообщения из карантина его невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="a5430-126">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="a5430-127">Использование центра безопасности & соответствия требованиям для управления сообщениями электронной почты, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="a5430-127">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="a5430-128">Просмотр электронной почты, помещенной в карантин</span><span class="sxs-lookup"><span data-stu-id="a5430-128">View quarantined email</span></span>

1. <span data-ttu-id="a5430-129">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="a5430-129">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="a5430-130">Убедитесь, что для свойства **Просмотр в карантине** задано значение **электронной почты** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a5430-130">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="a5430-131">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="a5430-131">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="a5430-132">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="a5430-132">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a5430-133">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="a5430-133">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="a5430-134">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-134">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-135">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-135">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-136">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-136">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-137">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-137">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-138">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-138">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-139">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-139">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-140">**Expires**</span><span class="sxs-lookup"><span data-stu-id="a5430-140">**Expires**</span></span>
   - <span data-ttu-id="a5430-141">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="a5430-141">**Recipient**</span></span>
   - <span data-ttu-id="a5430-142">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="a5430-142">**Message ID**</span></span>
   - <span data-ttu-id="a5430-143">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="a5430-143">**Policy name**</span></span>
   - <span data-ttu-id="a5430-144">**Размер**</span><span class="sxs-lookup"><span data-stu-id="a5430-144">**Size**</span></span>
   - <span data-ttu-id="a5430-145">**Направление**</span><span class="sxs-lookup"><span data-stu-id="a5430-145">**Direction**</span></span>

   <span data-ttu-id="a5430-146">Когда все будет готово, нажмите кнопку **сохранить** или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="a5430-146">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="a5430-147">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="a5430-147">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a5430-148">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="a5430-148">The available filters are:</span></span>

   - <span data-ttu-id="a5430-149">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="a5430-149">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="a5430-150">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="a5430-150">**Today**</span></span>
     - <span data-ttu-id="a5430-151">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="a5430-151">**Next 2 days**</span></span>
     - <span data-ttu-id="a5430-152">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="a5430-152">**Next 7 days**</span></span>
     - <span data-ttu-id="a5430-153">**Настраиваемые**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="a5430-153">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a5430-154">**Время получения**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="a5430-154">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a5430-155">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="a5430-155">**Quarantine reason**:</span></span>
     - <span data-ttu-id="a5430-156">**Политика**: сообщение, соответствующее условиям правила для обработки почтового ящика (которое также называется правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="a5430-156">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="a5430-157">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="a5430-157">**Bulk**</span></span>
     - <span data-ttu-id="a5430-158">**Фишинг**: фильтр нежелательной почты вредоносности **фишинга электронной почты** или защита от фишинга. сообщение помещено в карантин ([Параметры подмены](set-up-anti-phishing-policies.md#spoof-settings) или [Защита от олицетворения](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="a5430-158">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="a5430-159">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="a5430-159">**Malware**</span></span>
     - <span data-ttu-id="a5430-160">**Спам**</span><span class="sxs-lookup"><span data-stu-id="a5430-160">**Spam**</span></span>
     - <span data-ttu-id="a5430-161">**Фишинг с высокой степенью вероятности**</span><span class="sxs-lookup"><span data-stu-id="a5430-161">**High Confidence Phish**</span></span>

   - <span data-ttu-id="a5430-162">**Тип политики**: Фильтрация сообщений по типу политики:</span><span class="sxs-lookup"><span data-stu-id="a5430-162">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="a5430-163">**Политика защиты от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="a5430-163">**Anti-malware policy**</span></span>
     - <span data-ttu-id="a5430-164">**Политика безопасных вложений**</span><span class="sxs-lookup"><span data-stu-id="a5430-164">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="a5430-165">**Политика защиты от фишинга**</span><span class="sxs-lookup"><span data-stu-id="a5430-165">**Anti-phish policy**</span></span>
     - <span data-ttu-id="a5430-166">**Политика фильтрации размещенного содержимого** (политика защиты от нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="a5430-166">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="a5430-167">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="a5430-167">**Transport rule**</span></span>

   - <span data-ttu-id="a5430-168">**Получатель электронной почты**: все пользователи или сообщения, отправленные вам.</span><span class="sxs-lookup"><span data-stu-id="a5430-168">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="a5430-169">Конечные пользователи могут управлять только отправленными ими сообщениями из карантина.</span><span class="sxs-lookup"><span data-stu-id="a5430-169">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="a5430-170">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="a5430-170">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="a5430-171">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="a5430-171">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="a5430-172">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="a5430-172">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="a5430-173">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a5430-173">Wildcards aren't supported.</span></span> <span data-ttu-id="a5430-174">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="a5430-174">You can search by the following values:</span></span>

   - <span data-ttu-id="a5430-175">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="a5430-175">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="a5430-176">Например, [Трассировка сообщений](message-trace-scc.md) используется для поиска сообщения, отправленного пользователю в Организации, и определения того, что сообщение помещено в карантин, а не доставлено.</span><span class="sxs-lookup"><span data-stu-id="a5430-176">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="a5430-177">Обязательно укажите полное значение идентификатора сообщения, которое может включать угловые скобки ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="a5430-177">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="a5430-178">Пример: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="a5430-178">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="a5430-179">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="a5430-179">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="a5430-180">**Имя политики**: используйте полное имя политики сообщения.</span><span class="sxs-lookup"><span data-stu-id="a5430-180">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="a5430-181">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="a5430-181">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="a5430-182">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="a5430-182">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="a5430-183">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="a5430-183">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="a5430-184">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="a5430-184">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="a5430-185">**Имя политики**: имя политики, ответственной за помещение сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="a5430-185">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="a5430-186">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="a5430-186">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="a5430-187">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="a5430-187">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="a5430-188">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="a5430-188">View quarantined message details</span></span>

<span data-ttu-id="a5430-189">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a5430-189">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a5430-190">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="a5430-190">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="a5430-191">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="a5430-191">**Sender address**</span></span>

- <span data-ttu-id="a5430-192">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="a5430-192">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="a5430-193">**Тема**</span><span class="sxs-lookup"><span data-stu-id="a5430-193">**Subject**</span></span>

- <span data-ttu-id="a5430-194">**Причина карантина**: показывает, что сообщение было определено как **Нежелательная** почта, **массовый**, **Фишинг**, сопоставляемое правило обработки почты (**правило транспорта**) или оно было определено как содержащее **вредоносную** программу.</span><span class="sxs-lookup"><span data-stu-id="a5430-194">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="a5430-195">**Количество получателей**</span><span class="sxs-lookup"><span data-stu-id="a5430-195">**Recipient count**</span></span>

- <span data-ttu-id="a5430-196">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="a5430-196">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="a5430-197">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="a5430-197">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="a5430-198">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="a5430-198">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="a5430-199">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="a5430-199">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="a5430-200">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="a5430-200">Take action on quarantined email</span></span>

<span data-ttu-id="a5430-201">После выбора сообщения у вас есть несколько вариантов действий с сообщениями в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="a5430-201">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a5430-202">**Сообщение об освобождении**: в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a5430-202">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="a5430-203">**Сообщения отчетов в корпорацию Майкрософт для анализа**: этот параметр выбран по умолчанию и сообщает о том, что сообщение помещено в карантин в корпорацию Майкрософт как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="a5430-203">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="a5430-204">Если сообщение помещено в карантин, является пакетным, фишингом или содержит вредоносные программы, сообщение также передается группе анализа нежелательной почты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a5430-204">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a5430-205">В зависимости от их анализа можно настроить правила фильтрации нежелательной почты на уровне службы, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="a5430-205">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="a5430-206">Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="a5430-206">Choose one of the following options:</span></span>
    - <span data-ttu-id="a5430-207">**Освобождение сообщений всем получателям**</span><span class="sxs-lookup"><span data-stu-id="a5430-207">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="a5430-208">**Освобождение сообщений определенным получателям**</span><span class="sxs-lookup"><span data-stu-id="a5430-208">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="a5430-209">**Отпустите сообщения другим людям**: Обратите внимание на то, что сообщения от вредоносных программ, не отличных от исходных получателей, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a5430-209">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="a5430-210">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="a5430-210">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="a5430-211">Примечания по выпуску сообщений:</span><span class="sxs-lookup"><span data-stu-id="a5430-211">Notes about releasing messages:</span></span>

  - <span data-ttu-id="a5430-212">Вы не можете выпустить сообщение для одного и того же получателя несколько раз.</span><span class="sxs-lookup"><span data-stu-id="a5430-212">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="a5430-213">В списке потенциальных получателей будут отображаться только получатели, не получившие сообщение.</span><span class="sxs-lookup"><span data-stu-id="a5430-213">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="a5430-214">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="a5430-214">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="a5430-215">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="a5430-215">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="a5430-216">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="a5430-216">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="a5430-217">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="a5430-217">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="a5430-218">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="a5430-218">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="a5430-219">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="a5430-219">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="a5430-220">**Удалить из карантина**: после нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется без отправки первоначальным получателям.</span><span class="sxs-lookup"><span data-stu-id="a5430-220">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="a5430-221">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="a5430-221">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="a5430-222">**Сообщение о отсылке**: в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a5430-222">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="a5430-223">**Тип объекта**: **адрес электронной почты** (по умолчанию), **URL-адрес** или **вложение**.</span><span class="sxs-lookup"><span data-stu-id="a5430-223">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="a5430-224">**Формат отправки**: **идентификатор сетевого сообщения** (по умолчанию с соответствующим ЗНАЧЕНИЕМ в поле " **идентификатор сетевого сообщения** ") или " **файл** " (перейдите в локальный файл. EML или. MSG).</span><span class="sxs-lookup"><span data-stu-id="a5430-224">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="a5430-225">Обратите внимание, что если выбрать пункт **файл** , а затем выбрать **идентификатор сетевого сообщения**, исходное значение исчезнет.</span><span class="sxs-lookup"><span data-stu-id="a5430-225">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="a5430-226">**Recipients**: введите в поле аренда одного исходного получателя сообщения или нажмите кнопку **выбрать все** , чтобы определить всех получателей.</span><span class="sxs-lookup"><span data-stu-id="a5430-226">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="a5430-227">Вы также можете выбрать команду **выделить все** , а затем удалить отдельных получателей.</span><span class="sxs-lookup"><span data-stu-id="a5430-227">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="a5430-228">**Причина отправки**: **не должен быть заблокирован** (по умолчанию) или **должен быть заблокирован**.</span><span class="sxs-lookup"><span data-stu-id="a5430-228">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="a5430-229">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a5430-229">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="a5430-230">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a5430-230">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="a5430-231">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="a5430-231">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="a5430-232">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a5430-232">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="a5430-233">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="a5430-233">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a5430-234">Рассмотрим следующий сценарий: john@gmail.com отправляет сообщение в faith@contoso.com и john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a5430-234">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="a5430-235">Gmail получателей это сообщение на две копии, которые направляются на карантин в качестве фишинга в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a5430-235">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="a5430-236">Администратор освобождает оба этих сообщения в admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a5430-236">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="a5430-237">Доставляется Первое выпущенное сообщение, которое достигает почтового ящика администратора.</span><span class="sxs-lookup"><span data-stu-id="a5430-237">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="a5430-238">Второе выпущенное сообщение идентифицируется как повторяющаяся Доставка и пропускается.</span><span class="sxs-lookup"><span data-stu-id="a5430-238">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="a5430-239">Сообщение идентифицируется как дубликаты, если у них одинаковый идентификатор сообщения и время получения.</span><span class="sxs-lookup"><span data-stu-id="a5430-239">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="a5430-240">**Удалить сообщения**: после нажатия кнопки **Да** в появившемся предупреждении сообщения немедленно удаляются без отправки первоначальным получателям.</span><span class="sxs-lookup"><span data-stu-id="a5430-240">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="a5430-241">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a5430-241">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="a5430-242">Защитник Майкрософт для Office 365: использование центра безопасности & соответствия требованиям для управления файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="a5430-242">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="a5430-243">Процедуры для файлов, помещенных в карантин, в этом разделе доступны только для Microsoft Defender для Office 365 Plan 1 and Plan 2 подписчики.</span><span class="sxs-lookup"><span data-stu-id="a5430-243">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="a5430-244">В организациях с защитником для Office 365 администраторы могут управлять файлами, помещенными в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5430-244">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="a5430-245">Чтобы включить защиту для этих файлов, ознакомьтесь [со статьей включение ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a5430-245">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="a5430-246">Просмотр файлов, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="a5430-246">View quarantined files</span></span>

1. <span data-ttu-id="a5430-247">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="a5430-247">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="a5430-248">Изменение **представления, помещенного в карантин** , в **файлы** значений.</span><span class="sxs-lookup"><span data-stu-id="a5430-248">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="a5430-249">Можно выполнить сортировку по полю, щелкнув доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="a5430-249">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="a5430-250">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="a5430-250">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="a5430-251">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="a5430-251">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a5430-252">По умолчанию столбцы помечаются звездочкой ( <sup>\*</sup> ).</span><span class="sxs-lookup"><span data-stu-id="a5430-252">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="a5430-253">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-253">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-254">**Расположение**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-254">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-255">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-255">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-256">**URL-адрес файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-256">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-257">**Размер файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-257">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-258">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-258">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-259">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5430-259">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="a5430-260">**Определяется**</span><span class="sxs-lookup"><span data-stu-id="a5430-260">**Detected by**</span></span>
   - <span data-ttu-id="a5430-261">**Изменено временем**</span><span class="sxs-lookup"><span data-stu-id="a5430-261">**Modified by time**</span></span>

4. <span data-ttu-id="a5430-262">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="a5430-262">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a5430-263">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="a5430-263">The available filters are:</span></span>

   - <span data-ttu-id="a5430-264">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="a5430-264">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="a5430-265">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="a5430-265">**Today**</span></span>
     - <span data-ttu-id="a5430-266">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="a5430-266">**Next 2 days**</span></span>
     - <span data-ttu-id="a5430-267">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="a5430-267">**Next 7 days**</span></span>
     - <span data-ttu-id="a5430-268">Настраиваемый диапазон дат и времени.</span><span class="sxs-lookup"><span data-stu-id="a5430-268">A custom date/time range.</span></span>
   - <span data-ttu-id="a5430-269">**Время получения**</span><span class="sxs-lookup"><span data-stu-id="a5430-269">**Received time**</span></span>
   - <span data-ttu-id="a5430-270">**Причина карантина**: единственным доступным значением является **вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="a5430-270">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="a5430-271">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="a5430-271">**Policy type**</span></span>

<span data-ttu-id="a5430-272">Когда вы обнаружите определенный файл в карантине, выберите его, чтобы просмотреть сведения о нем, и выполните действия с ним (например, просмотр, освобождение, Загрузка или удаление сообщения).</span><span class="sxs-lookup"><span data-stu-id="a5430-272">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="a5430-273">Просмотр сведений о файле, помещенном в карантин</span><span class="sxs-lookup"><span data-stu-id="a5430-273">View quarantined file details</span></span>

<span data-ttu-id="a5430-274">При выборе файла в списке в всплывающей области **сведений** отображаются следующие сведения о файлах:</span><span class="sxs-lookup"><span data-stu-id="a5430-274">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a5430-275">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="a5430-275">**File Name**</span></span>
- <span data-ttu-id="a5430-276">**URL-адрес файла**: URL-адрес, определяющий расположение файла (например, в SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="a5430-276">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="a5430-277">**Обнаружено вредоносное содержимое в** Дата и время, когда файл помещен в карантин.</span><span class="sxs-lookup"><span data-stu-id="a5430-277">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="a5430-278">**Expires**: Дата, когда файл будет удален из карантина.</span><span class="sxs-lookup"><span data-stu-id="a5430-278">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="a5430-279">**Определяется: защитник** для Office 365 или антивредоносный модуль корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a5430-279">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="a5430-280">**Выпущено?**</span><span class="sxs-lookup"><span data-stu-id="a5430-280">**Released?**</span></span>
- <span data-ttu-id="a5430-281">**Имя вредоносной программы**</span><span class="sxs-lookup"><span data-stu-id="a5430-281">**Malware Name**</span></span>
- <span data-ttu-id="a5430-282">**Идентификатор документа**: уникальный идентификатор документа.</span><span class="sxs-lookup"><span data-stu-id="a5430-282">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="a5430-283">**Размер файла**: в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="a5430-283">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="a5430-284">**Организация** Уникальный идентификатор организации.</span><span class="sxs-lookup"><span data-stu-id="a5430-284">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="a5430-285">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="a5430-285">**Last modified**</span></span>
- <span data-ttu-id="a5430-286">**Изменено**: пользователь, который последним изменил файл.</span><span class="sxs-lookup"><span data-stu-id="a5430-286">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="a5430-287">**Безопасное значение хэш-алгоритма 256-bit (SHA-256)**: вы можете использовать это значение хэша, чтобы определить файл в других хранилищах репутации или в других расположениях в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="a5430-287">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="a5430-288">Выполнение действий с файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="a5430-288">Take action on quarantined files</span></span>

<span data-ttu-id="a5430-289">При выборе файла в списке можно выполнить следующие действия с файлом в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="a5430-289">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a5430-290">**Выпуски файлов**: выберите (по умолчанию) или отменить выбор **файлов отчета в корпорацию Майкрософт для анализа**, а затем нажмите кнопку **освободить файлы**.</span><span class="sxs-lookup"><span data-stu-id="a5430-290">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="a5430-291">**Скачивание файла**</span><span class="sxs-lookup"><span data-stu-id="a5430-291">**Download file**</span></span>
- <span data-ttu-id="a5430-292">**Удаление файла из карантина**</span><span class="sxs-lookup"><span data-stu-id="a5430-292">**Remove file from quarantine**</span></span>

<span data-ttu-id="a5430-293">Если вы не Освободите или не удалите эти файлы, они будут удалены по истечении периода хранения на карантине по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a5430-293">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="a5430-294">Действия с несколькими файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="a5430-294">Actions on multiple quarantined files</span></span>

<span data-ttu-id="a5430-295">При выборе нескольких файлов, помещенных в карантин, в списке (до 100) отображается раскрывающаяся панель **массовых действий** , в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a5430-295">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="a5430-296">**Выпустить файлы**</span><span class="sxs-lookup"><span data-stu-id="a5430-296">**Release files**</span></span>
- <span data-ttu-id="a5430-297">**Удалить файлы**: после нажатия кнопки **Да** в появившемся предупреждении файлы сразу же удаляются.</span><span class="sxs-lookup"><span data-stu-id="a5430-297">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="a5430-298">Просмотр сообщений и файлов, помещенных в карантин, и управление ими с помощью Exchange Online PowerShell или отдельного EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5430-298">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="a5430-299">Для просмотра и управления сообщениями и файлами в карантине используются следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="a5430-299">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="a5430-300">Delete — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a5430-300">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="a5430-301">Export — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a5430-301">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="a5430-302">Get — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a5430-302">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="a5430-303">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Обратите внимание, что этот командлет предназначен только для сообщений, а не от вредоносных файлов из ATP для SharePoint Online, OneDrive для бизнеса или Teams.</span><span class="sxs-lookup"><span data-stu-id="a5430-303">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="a5430-304">Release — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a5430-304">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
