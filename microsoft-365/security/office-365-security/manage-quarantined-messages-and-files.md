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
ms.openlocfilehash: b6f6f47dc227d3bada425d02784a8aff5da8b3d3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842932"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="72c7e-104">Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в EOP</span><span class="sxs-lookup"><span data-stu-id="72c7e-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="72c7e-105">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="72c7e-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="72c7e-106">Дополнительные сведения см. [в статье сообщения электронной почты, помещенные в карантин в EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="72c7e-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="72c7e-107">Администраторы могут просматривать, освобождать и удалять все типы сообщений, помещенных в карантин, для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="72c7e-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="72c7e-108">Только администраторы могут управлять сообщениями, помещенными на карантин, высокой достоверностью фишинга, или в результате правил для процесса обработки почты (также называемых правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="72c7e-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="72c7e-109">Администраторы также могут сообщать ложные срабатывания корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72c7e-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="72c7e-110">Администраторы в организациях с защитником Майкрософт для Office 365 также могут просматривать, загружать и удалять файлы, помещенные в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="72c7e-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="72c7e-111">Вы просматриваете и управляете сообщения, помещенные в карантин, в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="72c7e-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="72c7e-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="72c7e-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="72c7e-113">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="72c7e-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="72c7e-114">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="72c7e-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="72c7e-115">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="72c7e-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="72c7e-116">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="72c7e-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="72c7e-117">Для управления карантином в качестве администратора необходимо назначить разрешения. Управление разрешениями осуществляется ролью **карантина** в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="72c7e-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="72c7e-118">По умолчанию эта роль назначается группам ролей " **Управление организацией** " (глобальными администраторами), " **Администратор карантина** " и " **Администраторы безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="72c7e-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator** , and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="72c7e-119">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="72c7e-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="72c7e-120">Сообщения, помещенные в карантин, хранятся в течение определенного периода времени, по истечении которого они будут автоматически удалены:</span><span class="sxs-lookup"><span data-stu-id="72c7e-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="72c7e-121">Сообщения, помещенные в карантин политиками защиты от нежелательной почты (спама, фишинга и массовые сообщения электронной почты): 30 дней.</span><span class="sxs-lookup"><span data-stu-id="72c7e-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="72c7e-122">Это значение по умолчанию и максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="72c7e-122">This is the default and maximum value.</span></span> <span data-ttu-id="72c7e-123">Чтобы настроить это значение, ознакомьтесь со статьей [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="72c7e-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="72c7e-124">Сообщения, содержащие вредоносную программу: 15 дней.</span><span class="sxs-lookup"><span data-stu-id="72c7e-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="72c7e-125">При истечении срока действия сообщения из карантина его невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="72c7e-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="72c7e-126">Использование центра безопасности & соответствия требованиям для управления сообщениями электронной почты, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="72c7e-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="72c7e-127">Просмотр электронной почты, помещенной в карантин</span><span class="sxs-lookup"><span data-stu-id="72c7e-127">View quarantined email</span></span>

1. <span data-ttu-id="72c7e-128">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="72c7e-129">Убедитесь, что для свойства **Просмотр в карантине** задано значение **электронной почты** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="72c7e-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="72c7e-130">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="72c7e-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="72c7e-131">Нажмите кнопку **изменить столбцы** , чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="72c7e-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="72c7e-132">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="72c7e-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="72c7e-133">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-133">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-134">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-134">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-135">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-135">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-136">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-136">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-137">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-137">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-138">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-138">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-139">**Expires**</span><span class="sxs-lookup"><span data-stu-id="72c7e-139">**Expires**</span></span>
   - <span data-ttu-id="72c7e-140">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="72c7e-140">**Recipient**</span></span>
   - <span data-ttu-id="72c7e-141">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="72c7e-141">**Message ID**</span></span>
   - <span data-ttu-id="72c7e-142">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="72c7e-142">**Policy name**</span></span>
   - <span data-ttu-id="72c7e-143">**Размер**</span><span class="sxs-lookup"><span data-stu-id="72c7e-143">**Size**</span></span>
   - <span data-ttu-id="72c7e-144">**Направление**</span><span class="sxs-lookup"><span data-stu-id="72c7e-144">**Direction**</span></span>

   <span data-ttu-id="72c7e-145">Когда все будет готово, нажмите кнопку **сохранить** или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-145">When you're finished, click **Save** , or click **Set to default**.</span></span>

4. <span data-ttu-id="72c7e-146">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-146">To filter the results, click **Filter**.</span></span> <span data-ttu-id="72c7e-147">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="72c7e-147">The available filters are:</span></span>

   - <span data-ttu-id="72c7e-148">**Срок действия истекает** : Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="72c7e-148">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="72c7e-149">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="72c7e-149">**Today**</span></span>
     - <span data-ttu-id="72c7e-150">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="72c7e-150">**Next 2 days**</span></span>
     - <span data-ttu-id="72c7e-151">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="72c7e-151">**Next 7 days**</span></span>
     - <span data-ttu-id="72c7e-152">**Настраиваемые** : введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-152">**Custom** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="72c7e-153">**Время получения** : введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-153">**Received time** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="72c7e-154">**Причина карантина** :</span><span class="sxs-lookup"><span data-stu-id="72c7e-154">**Quarantine reason** :</span></span>
     - <span data-ttu-id="72c7e-155">**Политика** : сообщение, соответствующее условиям правила для обработки почтового ящика (которое также называется правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="72c7e-155">**Policy** : The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="72c7e-156">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="72c7e-156">**Bulk**</span></span>
     - <span data-ttu-id="72c7e-157">**Фишинг** : фильтр нежелательной почты вредоносности **фишинга электронной почты** или защита от фишинга. сообщение помещено в карантин ( [Параметры подмены](set-up-anti-phishing-policies.md#spoof-settings) или [Защита от олицетворения](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="72c7e-157">**Phish** : The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="72c7e-158">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="72c7e-158">**Malware**</span></span>
     - <span data-ttu-id="72c7e-159">**Спам**</span><span class="sxs-lookup"><span data-stu-id="72c7e-159">**Spam**</span></span>
     - <span data-ttu-id="72c7e-160">**Фишинг с высокой степенью вероятности**</span><span class="sxs-lookup"><span data-stu-id="72c7e-160">**High Confidence Phish**</span></span>

   - <span data-ttu-id="72c7e-161">**Тип политики** : фильтрация сообщений по типу политики:</span><span class="sxs-lookup"><span data-stu-id="72c7e-161">**Policy Type** : Filter messages by policy type:</span></span>
     - <span data-ttu-id="72c7e-162">**Политика защиты от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="72c7e-162">**Anti-malware policy**</span></span>
     - <span data-ttu-id="72c7e-163">**Политика безопасных вложений**</span><span class="sxs-lookup"><span data-stu-id="72c7e-163">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="72c7e-164">**Политика защиты от фишинга**</span><span class="sxs-lookup"><span data-stu-id="72c7e-164">**Anti-phish policy**</span></span>
     - <span data-ttu-id="72c7e-165">**Политика фильтрации размещенного содержимого** (политика защиты от нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="72c7e-165">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="72c7e-166">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="72c7e-166">**Transport rule**</span></span>

   - <span data-ttu-id="72c7e-167">**Получатель электронной почты** : все пользователи или сообщения, отправленные вам.</span><span class="sxs-lookup"><span data-stu-id="72c7e-167">**Email recipient** : All users or only messages sent to you.</span></span> <span data-ttu-id="72c7e-168">Конечные пользователи могут управлять только отправленными ими сообщениями из карантина.</span><span class="sxs-lookup"><span data-stu-id="72c7e-168">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="72c7e-169">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-169">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="72c7e-170">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-170">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="72c7e-171">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="72c7e-171">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="72c7e-172">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="72c7e-172">Wildcards aren't supported.</span></span> <span data-ttu-id="72c7e-173">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="72c7e-173">You can search by the following values:</span></span>

   - <span data-ttu-id="72c7e-174">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="72c7e-174">**Message ID** : The globally unique identifier of the message.</span></span>

     <span data-ttu-id="72c7e-175">Например, [Трассировка сообщений](message-trace-scc.md) используется для поиска сообщения, отправленного пользователю в Организации, и определения того, что сообщение помещено в карантин, а не доставлено.</span><span class="sxs-lookup"><span data-stu-id="72c7e-175">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="72c7e-176">Обязательно укажите полное значение идентификатора сообщения, которое может включать угловые скобки ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="72c7e-176">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="72c7e-177">Пример: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="72c7e-177">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="72c7e-178">**Адрес электронной почты отправителя** : адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="72c7e-178">**Sender email address** : A single sender's email address.</span></span>

   - <span data-ttu-id="72c7e-179">**Имя политики** : используйте полное имя политики сообщения.</span><span class="sxs-lookup"><span data-stu-id="72c7e-179">**Policy name** : Use the entire policy name of the message.</span></span> <span data-ttu-id="72c7e-180">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="72c7e-180">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="72c7e-181">**Адрес электронной почты получателя** : адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="72c7e-181">**Recipient email address** : A single recipient's email address.</span></span>

   - <span data-ttu-id="72c7e-182">**Тема** : Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="72c7e-182">**Subject** : Use the entire subject of the message.</span></span> <span data-ttu-id="72c7e-183">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="72c7e-183">The search is not case-sensitive.</span></span>
  
   - <span data-ttu-id="72c7e-184">**Имя политики** : имя политики, ответственной за помещение сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="72c7e-184">**Policy name** : The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="72c7e-185">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить** , чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="72c7e-185">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="72c7e-186">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="72c7e-186">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="72c7e-187">Экспортировать результаты сообщения</span><span class="sxs-lookup"><span data-stu-id="72c7e-187">Export message results</span></span>

1. <span data-ttu-id="72c7e-188">Выберите интересующие вас сообщения и нажмите **Экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-188">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="72c7e-189">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="72c7e-189">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="72c7e-190">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="72c7e-190">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="72c7e-191">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="72c7e-191">View quarantined message details</span></span>

<span data-ttu-id="72c7e-192">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="72c7e-192">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="72c7e-193">**Идентификатор сообщения** : Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="72c7e-193">**Message ID** : The globally unique identifier for the message.</span></span>

- <span data-ttu-id="72c7e-194">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="72c7e-194">**Sender address**</span></span>

- <span data-ttu-id="72c7e-195">**Получено** : Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="72c7e-195">**Received** : The date/time when the message was received.</span></span>

- <span data-ttu-id="72c7e-196">**Тема**</span><span class="sxs-lookup"><span data-stu-id="72c7e-196">**Subject**</span></span>

- <span data-ttu-id="72c7e-197">**Причина карантина** : показывает, что сообщение было определено как **Нежелательная** почта, **массовый** , **Фишинг** , сопоставляемое правило обработки почты ( **правило транспорта** ) или оно было определено как содержащее **вредоносную** программу.</span><span class="sxs-lookup"><span data-stu-id="72c7e-197">**Quarantine reason** : Shows if a message has been identified as **Spam** , **Bulk** , **Phish** , matched a mail flow rule ( **Transport rule** ), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="72c7e-198">**Количество получателей**</span><span class="sxs-lookup"><span data-stu-id="72c7e-198">**Recipient count**</span></span>

- <span data-ttu-id="72c7e-199">**Получатели** : Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения** , чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="72c7e-199">**Recipients** : If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="72c7e-200">**Истекает** : дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="72c7e-200">**Expires** : The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="72c7e-201">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="72c7e-201">**Released to** : All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="72c7e-202">**Пока не выпустили** : все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="72c7e-202">**Not yet released to** : All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="72c7e-203">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="72c7e-203">Take action on quarantined email</span></span>

<span data-ttu-id="72c7e-204">После выбора сообщения у вас есть несколько вариантов действий с сообщениями в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="72c7e-204">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="72c7e-205">**Сообщение об освобождении** : в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="72c7e-205">**Release message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="72c7e-206">**Сообщения отчетов в корпорацию Майкрософт для анализа** : этот параметр выбран по умолчанию и сообщает о том, что сообщение помещено в карантин в корпорацию Майкрософт как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="72c7e-206">**Report messages to Microsoft for analysis** : This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="72c7e-207">Если сообщение помещено в карантин, является пакетным, фишингом или содержит вредоносные программы, сообщение также передается группе анализа нежелательной почты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72c7e-207">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="72c7e-208">В зависимости от их анализа можно настроить правила фильтрации нежелательной почты на уровне службы, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="72c7e-208">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="72c7e-209">Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="72c7e-209">Choose one of the following options:</span></span>
    - <span data-ttu-id="72c7e-210">**Освобождение сообщений всем получателям**</span><span class="sxs-lookup"><span data-stu-id="72c7e-210">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="72c7e-211">**Освобождение сообщений определенным получателям**</span><span class="sxs-lookup"><span data-stu-id="72c7e-211">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="72c7e-212">**Разблокирование сообщений для других пользователей**</span><span class="sxs-lookup"><span data-stu-id="72c7e-212">**Release messages to other people**</span></span>

  <span data-ttu-id="72c7e-213">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-213">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="72c7e-214">Примечания по выпуску сообщений:</span><span class="sxs-lookup"><span data-stu-id="72c7e-214">Notes about releasing messages:</span></span>

  - <span data-ttu-id="72c7e-215">Вы не можете выпустить сообщение для одного и того же получателя несколько раз.</span><span class="sxs-lookup"><span data-stu-id="72c7e-215">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="72c7e-216">В списке потенциальных получателей будут отображаться только получатели, не получившие сообщение.</span><span class="sxs-lookup"><span data-stu-id="72c7e-216">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="72c7e-217">**Просмотр заголовка сообщения** : Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="72c7e-217">**View message header** : Choose this link to see the message header text.</span></span> <span data-ttu-id="72c7e-218">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer** , чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке** , если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="72c7e-218">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="72c7e-219">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки** :</span><span class="sxs-lookup"><span data-stu-id="72c7e-219">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers** :</span></span>

- <span data-ttu-id="72c7e-220">**Предварительный просмотр сообщения** : в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="72c7e-220">**Preview message** : In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="72c7e-221">**Исходный вид** : показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="72c7e-221">**Source view** : Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="72c7e-222">**Текстовое представление** : показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="72c7e-222">**Text view** : Shows the message body in plain text.</span></span>

- <span data-ttu-id="72c7e-223">**Удалить из карантина** : после нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется без отправки первоначальным получателям.</span><span class="sxs-lookup"><span data-stu-id="72c7e-223">**Remove from quarantine** : After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="72c7e-224">**Загрузка сообщения** : В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения** , чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="72c7e-224">**Download message** : In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="72c7e-225">**Сообщение о отсылке** : в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="72c7e-225">**Submit message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="72c7e-226">**Тип объекта** : **адрес электронной почты** (по умолчанию), **URL-адрес** или **вложение**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-226">**Object type** : **Email** (default), **URL** , or **Attachment**.</span></span>

  - <span data-ttu-id="72c7e-227">**Формат отправки** : **идентификатор сетевого сообщения** (по умолчанию с соответствующим ЗНАЧЕНИЕМ в поле " **идентификатор сетевого сообщения** ") или " **файл** " (перейдите в локальный файл. EML или. MSG).</span><span class="sxs-lookup"><span data-stu-id="72c7e-227">**Submission format** : **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="72c7e-228">Обратите внимание, что если выбрать пункт **файл** , а затем выбрать **идентификатор сетевого сообщения** , начальное значение исчезнет.</span><span class="sxs-lookup"><span data-stu-id="72c7e-228">Note that if you select **File** and then select **Network Message ID** , the initially value is gone.</span></span>

  - <span data-ttu-id="72c7e-229">**Recipients** : введите в поле аренда одного исходного получателя сообщения или нажмите кнопку **выбрать все** , чтобы определить всех получателей.</span><span class="sxs-lookup"><span data-stu-id="72c7e-229">**Recipients** : Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="72c7e-230">Вы также можете выбрать команду **выделить все** , а затем удалить отдельных получателей.</span><span class="sxs-lookup"><span data-stu-id="72c7e-230">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="72c7e-231">**Причина отправки** : **не должен быть заблокирован** (по умолчанию) или **должен быть заблокирован**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-231">**Reason for submission** : **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="72c7e-232">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-232">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="72c7e-233">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="72c7e-233">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="72c7e-234">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="72c7e-234">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="72c7e-235">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия** , в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="72c7e-235">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="72c7e-236">**Выпуск сообщений** : параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям** ; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-236">**Release messages** : The options are the same as when you release a single message, except you can't select **Release messages to specific recipients** ; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="72c7e-237">Рассмотрим следующий сценарий: john@gmail.com отправляет сообщение в faith@contoso.com и john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="72c7e-237">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="72c7e-238">Gmail получателей это сообщение на две копии, которые направляются на карантин в качестве фишинга в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72c7e-238">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="72c7e-239">Администратор освобождает оба этих сообщения в admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="72c7e-239">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="72c7e-240">Доставляется Первое выпущенное сообщение, которое достигает почтового ящика администратора.</span><span class="sxs-lookup"><span data-stu-id="72c7e-240">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="72c7e-241">Второе выпущенное сообщение идентифицируется как повторяющаяся Доставка и пропускается.</span><span class="sxs-lookup"><span data-stu-id="72c7e-241">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="72c7e-242">Сообщение идентифицируется как дубликаты, если у них одинаковый идентификатор сообщения и время получения.</span><span class="sxs-lookup"><span data-stu-id="72c7e-242">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="72c7e-243">**Удалить сообщения** : После нажатия кнопки **Да** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="72c7e-243">**Delete messages** :  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="72c7e-244">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-244">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="72c7e-245">Защитник Майкрософт для Office 365: использование центра безопасности & соответствия требованиям для управления файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="72c7e-245">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="72c7e-246">Процедуры для файлов, помещенных в карантин, в этом разделе доступны только для Microsoft Defender для Office 365 Plan 1 and Plan 2 подписчики.</span><span class="sxs-lookup"><span data-stu-id="72c7e-246">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="72c7e-247">В организациях с защитником для Office 365 администраторы могут управлять файлами, помещенными в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="72c7e-247">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="72c7e-248">Чтобы включить защиту для этих файлов, ознакомьтесь [со статьей включение ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="72c7e-248">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="72c7e-249">Просмотр файлов, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="72c7e-249">View quarantined files</span></span>

1. <span data-ttu-id="72c7e-250">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-250">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="72c7e-251">Изменение **представления, помещенного в карантин** , в **файлы** значений.</span><span class="sxs-lookup"><span data-stu-id="72c7e-251">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="72c7e-252">Можно выполнить сортировку по полю, щелкнув доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="72c7e-252">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="72c7e-253">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="72c7e-253">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="72c7e-254">Нажмите кнопку **изменить столбцы** , чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="72c7e-254">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="72c7e-255">По умолчанию столбцы помечаются звездочкой ( <sup>\*</sup> ).</span><span class="sxs-lookup"><span data-stu-id="72c7e-255">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="72c7e-256">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-256">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-257">**Расположение**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-257">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-258">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-258">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-259">**URL-адрес файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-259">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-260">**Размер файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-260">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-261">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-261">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-262">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="72c7e-262">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="72c7e-263">**Определяется**</span><span class="sxs-lookup"><span data-stu-id="72c7e-263">**Detected by**</span></span>
   - <span data-ttu-id="72c7e-264">**Изменено временем**</span><span class="sxs-lookup"><span data-stu-id="72c7e-264">**Modified by time**</span></span>

4. <span data-ttu-id="72c7e-265">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-265">To filter the results, click **Filter**.</span></span> <span data-ttu-id="72c7e-266">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="72c7e-266">The available filters are:</span></span>

   - <span data-ttu-id="72c7e-267">**Срок действия истекает** : Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="72c7e-267">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="72c7e-268">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="72c7e-268">**Today**</span></span>
     - <span data-ttu-id="72c7e-269">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="72c7e-269">**Next 2 days**</span></span>
     - <span data-ttu-id="72c7e-270">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="72c7e-270">**Next 7 days**</span></span>
     - <span data-ttu-id="72c7e-271">Настраиваемый диапазон дат и времени.</span><span class="sxs-lookup"><span data-stu-id="72c7e-271">A custom date/time range.</span></span>
   - <span data-ttu-id="72c7e-272">**Время получения**</span><span class="sxs-lookup"><span data-stu-id="72c7e-272">**Received time**</span></span>
   - <span data-ttu-id="72c7e-273">**Причина карантина** : единственным доступным значением является **вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-273">**Quarantine reason** : The only available value is **Malware**.</span></span>
   - <span data-ttu-id="72c7e-274">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="72c7e-274">**Policy type**</span></span>

<span data-ttu-id="72c7e-275">Когда вы обнаружите определенный файл в карантине, выберите его, чтобы просмотреть сведения о нем, и выполните действия с ним (например, просмотр, освобождение, Загрузка или удаление сообщения).</span><span class="sxs-lookup"><span data-stu-id="72c7e-275">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="72c7e-276">Результаты экспорта файлов</span><span class="sxs-lookup"><span data-stu-id="72c7e-276">Export file results</span></span>

1. <span data-ttu-id="72c7e-277">Выберите нужные файлы и нажмите **экспортировать результаты**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-277">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="72c7e-278">Нажмите кнопку **Да** в сообщении с подтверждением, предупреждающим вас о том, чтобы окно браузера оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="72c7e-278">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="72c7e-279">Когда экспорт будет готов, вы можете указать имя и выбрать место загрузки для файла .csv.</span><span class="sxs-lookup"><span data-stu-id="72c7e-279">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="72c7e-280">Просмотр сведений о файле, помещенном в карантин</span><span class="sxs-lookup"><span data-stu-id="72c7e-280">View quarantined file details</span></span>

<span data-ttu-id="72c7e-281">При выборе файла в списке в всплывающей области **сведений** отображаются следующие сведения о файлах:</span><span class="sxs-lookup"><span data-stu-id="72c7e-281">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="72c7e-282">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="72c7e-282">**File Name**</span></span>
- <span data-ttu-id="72c7e-283">**URL-адрес файла** : URL-адрес, определяющий расположение файла (например, в SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="72c7e-283">**File URL** : URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="72c7e-284">**Обнаружено вредоносное содержимое в** Дата и время, когда файл помещен в карантин.</span><span class="sxs-lookup"><span data-stu-id="72c7e-284">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="72c7e-285">**Expires** : Дата, когда файл будет удален из карантина.</span><span class="sxs-lookup"><span data-stu-id="72c7e-285">**Expires** : The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="72c7e-286">**Определяется: защитник** для Office 365 или антивредоносный модуль корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72c7e-286">**Detected By** : Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="72c7e-287">**Выпущено?**</span><span class="sxs-lookup"><span data-stu-id="72c7e-287">**Released?**</span></span>
- <span data-ttu-id="72c7e-288">**Имя вредоносной программы**</span><span class="sxs-lookup"><span data-stu-id="72c7e-288">**Malware Name**</span></span>
- <span data-ttu-id="72c7e-289">**Идентификатор документа** : уникальный идентификатор документа.</span><span class="sxs-lookup"><span data-stu-id="72c7e-289">**Document ID** : A unique identifier for the document.</span></span>
- <span data-ttu-id="72c7e-290">**Размер файла** : в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="72c7e-290">**File Size** : In kilobytes (KB).</span></span>
- <span data-ttu-id="72c7e-291">**Организация** Уникальный идентификатор организации.</span><span class="sxs-lookup"><span data-stu-id="72c7e-291">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="72c7e-292">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="72c7e-292">**Last modified**</span></span>
- <span data-ttu-id="72c7e-293">**Изменено** : пользователь, который последним изменил файл.</span><span class="sxs-lookup"><span data-stu-id="72c7e-293">**Modified By** : The user who last modified the file.</span></span>
- <span data-ttu-id="72c7e-294">**Безопасное значение хэш-алгоритма 256-bit (SHA-256)** : вы можете использовать это значение хэша, чтобы определить файл в других хранилищах репутации или в других расположениях в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="72c7e-294">**Secure Hash Algorithm 256-bit (SHA-256) value** : You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="72c7e-295">Выполнение действий с файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="72c7e-295">Take action on quarantined files</span></span>

<span data-ttu-id="72c7e-296">При выборе файла в списке можно выполнить следующие действия с файлом в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="72c7e-296">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="72c7e-297">**Выпуски файлов** : выберите (по умолчанию) или отменить выбор **файлов отчета в корпорацию Майкрософт для анализа** , а затем нажмите кнопку **освободить файлы**.</span><span class="sxs-lookup"><span data-stu-id="72c7e-297">**Release files** : Select (default) or unselect **Report files to Microsoft for analysis** , and then click **Release files**.</span></span>
- <span data-ttu-id="72c7e-298">**Скачивание файла**</span><span class="sxs-lookup"><span data-stu-id="72c7e-298">**Download file**</span></span>
- <span data-ttu-id="72c7e-299">**Удаление файла из карантина**</span><span class="sxs-lookup"><span data-stu-id="72c7e-299">**Remove file from quarantine**</span></span>

<span data-ttu-id="72c7e-300">Если вы не Освободите или не удалите эти файлы, они будут удалены по истечении периода хранения на карантине по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="72c7e-300">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="72c7e-301">Действия с несколькими файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="72c7e-301">Actions on multiple quarantined files</span></span>

<span data-ttu-id="72c7e-302">При выборе нескольких файлов, помещенных в карантин, в списке (до 100) отображается раскрывающаяся панель **массовых действий** , в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="72c7e-302">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="72c7e-303">**Выпустить файлы**</span><span class="sxs-lookup"><span data-stu-id="72c7e-303">**Release files**</span></span>
- <span data-ttu-id="72c7e-304">**Удалить файлы** : после нажатия кнопки **Да** в появившемся предупреждении файлы сразу же удаляются.</span><span class="sxs-lookup"><span data-stu-id="72c7e-304">**Delete files** :  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="72c7e-305">Просмотр сообщений и файлов, помещенных в карантин, и управление ими с помощью Exchange Online PowerShell или отдельного EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="72c7e-305">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="72c7e-306">Для просмотра и управления сообщениями и файлами в карантине используются следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="72c7e-306">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="72c7e-307">Delete — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="72c7e-307">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="72c7e-308">Export — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="72c7e-308">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="72c7e-309">Get — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="72c7e-309">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="72c7e-310">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Обратите внимание, что этот командлет предназначен только для сообщений, а не от вредоносных файлов из ATP для SharePoint Online, OneDrive для бизнеса или Teams.</span><span class="sxs-lookup"><span data-stu-id="72c7e-310">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="72c7e-311">Release — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="72c7e-311">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
