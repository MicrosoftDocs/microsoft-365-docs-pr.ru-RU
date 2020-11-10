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
ms.openlocfilehash: 9d58f8c08d994e5e9736c8223239b54e52c4edab
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951051"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="d742d-104">Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в EOP</span><span class="sxs-lookup"><span data-stu-id="d742d-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d742d-105">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="d742d-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="d742d-106">Дополнительные сведения см. [в статье сообщения электронной почты, помещенные в карантин в EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="d742d-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="d742d-107">Администраторы могут просматривать, освобождать и удалять все типы сообщений, помещенных в карантин, для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="d742d-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="d742d-108">Только администраторы могут управлять сообщениями, помещенными на карантин, высокой достоверностью фишинга, или в результате правил для процесса обработки почты (также называемых правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="d742d-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d742d-109">Администраторы также могут сообщать ложные срабатывания корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d742d-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="d742d-110">Администраторы в организациях с защитником Майкрософт для Office 365 также могут просматривать, загружать и удалять файлы, помещенные в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d742d-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="d742d-111">Вы просматриваете и управляете сообщения, помещенные в карантин, в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="d742d-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d742d-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d742d-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d742d-113">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="d742d-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="d742d-114">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="d742d-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="d742d-115">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d742d-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d742d-116">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d742d-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d742d-117">Для управления карантином в качестве администратора необходимо назначить разрешения. Управление разрешениями осуществляется ролью **карантина** в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d742d-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="d742d-118">По умолчанию эта роль назначается группам ролей " **Управление организацией** " (глобальными администраторами), " **Администратор карантина** " и " **Администраторы безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d742d-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator** , and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="d742d-119">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d742d-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d742d-120">Сообщения, помещенные в карантин, хранятся в течение определенного периода времени, по истечении которого они будут автоматически удалены:</span><span class="sxs-lookup"><span data-stu-id="d742d-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="d742d-121">Сообщения, помещенные в карантин политиками защиты от нежелательной почты (спама, фишинга и массовые сообщения электронной почты): 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d742d-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="d742d-122">Это значение по умолчанию и максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="d742d-122">This is the default and maximum value.</span></span> <span data-ttu-id="d742d-123">Чтобы настроить это значение, ознакомьтесь со статьей [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d742d-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="d742d-124">Сообщения, содержащие вредоносную программу: 15 дней.</span><span class="sxs-lookup"><span data-stu-id="d742d-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="d742d-125">При истечении срока действия сообщения из карантина его невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="d742d-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="d742d-126">Использование центра безопасности & соответствия требованиям для управления сообщениями электронной почты, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="d742d-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="d742d-127">Просмотр электронной почты, помещенной в карантин</span><span class="sxs-lookup"><span data-stu-id="d742d-127">View quarantined email</span></span>

1. <span data-ttu-id="d742d-128">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="d742d-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="d742d-129">Убедитесь, что для свойства **Просмотр в карантине** задано значение **электронной почты** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d742d-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="d742d-130">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="d742d-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="d742d-131">Нажмите кнопку **изменить столбцы** , чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="d742d-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="d742d-132">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="d742d-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="d742d-133">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-133">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-134">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-134">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-135">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-135">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-136">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-136">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-137">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-137">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-138">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-138">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-139">**Expires**</span><span class="sxs-lookup"><span data-stu-id="d742d-139">**Expires**</span></span>
   - <span data-ttu-id="d742d-140">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="d742d-140">**Recipient**</span></span>
   - <span data-ttu-id="d742d-141">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="d742d-141">**Message ID**</span></span>
   - <span data-ttu-id="d742d-142">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="d742d-142">**Policy name**</span></span>
   - <span data-ttu-id="d742d-143">**Размер**</span><span class="sxs-lookup"><span data-stu-id="d742d-143">**Size**</span></span>
   - <span data-ttu-id="d742d-144">**Направление**</span><span class="sxs-lookup"><span data-stu-id="d742d-144">**Direction**</span></span>

   <span data-ttu-id="d742d-145">Когда все будет готово, нажмите кнопку **сохранить** или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="d742d-145">When you're finished, click **Save** , or click **Set to default**.</span></span>

4. <span data-ttu-id="d742d-146">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d742d-146">To filter the results, click **Filter**.</span></span> <span data-ttu-id="d742d-147">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="d742d-147">The available filters are:</span></span>

   - <span data-ttu-id="d742d-148">**Срок действия истекает** : Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="d742d-148">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="d742d-149">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="d742d-149">**Today**</span></span>
     - <span data-ttu-id="d742d-150">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="d742d-150">**Next 2 days**</span></span>
     - <span data-ttu-id="d742d-151">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="d742d-151">**Next 7 days**</span></span>
     - <span data-ttu-id="d742d-152">**Настраиваемые** : введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="d742d-152">**Custom** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="d742d-153">**Время получения** : введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="d742d-153">**Received time** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="d742d-154">**Причина карантина** :</span><span class="sxs-lookup"><span data-stu-id="d742d-154">**Quarantine reason** :</span></span>
     - <span data-ttu-id="d742d-155">**Политика** : сообщение, соответствующее условиям правила для обработки почтового ящика (которое также называется правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="d742d-155">**Policy** : The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="d742d-156">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="d742d-156">**Bulk**</span></span>
     - <span data-ttu-id="d742d-157">**Фишинг** : фильтр нежелательной почты вредоносности **фишинга электронной почты** или защита от фишинга. сообщение помещено в карантин ( [Параметры подмены](set-up-anti-phishing-policies.md#spoof-settings) или [Защита от олицетворения](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="d742d-157">**Phish** : The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="d742d-158">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="d742d-158">**Malware**</span></span>
     - <span data-ttu-id="d742d-159">**Спам**</span><span class="sxs-lookup"><span data-stu-id="d742d-159">**Spam**</span></span>
     - <span data-ttu-id="d742d-160">**Фишинг с высокой степенью вероятности**</span><span class="sxs-lookup"><span data-stu-id="d742d-160">**High Confidence Phish**</span></span>

   - <span data-ttu-id="d742d-161">**Тип политики** : фильтрация сообщений по типу политики:</span><span class="sxs-lookup"><span data-stu-id="d742d-161">**Policy Type** : Filter messages by policy type:</span></span>
     - <span data-ttu-id="d742d-162">**Политика защиты от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="d742d-162">**Anti-malware policy**</span></span>
     - <span data-ttu-id="d742d-163">**Политика безопасных вложений**</span><span class="sxs-lookup"><span data-stu-id="d742d-163">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="d742d-164">**Политика защиты от фишинга**</span><span class="sxs-lookup"><span data-stu-id="d742d-164">**Anti-phish policy**</span></span>
     - <span data-ttu-id="d742d-165">**Политика фильтрации размещенного содержимого** (политика защиты от нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="d742d-165">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="d742d-166">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="d742d-166">**Transport rule**</span></span>

   - <span data-ttu-id="d742d-167">**Получатель электронной почты** : все пользователи или сообщения, отправленные вам.</span><span class="sxs-lookup"><span data-stu-id="d742d-167">**Email recipient** : All users or only messages sent to you.</span></span> <span data-ttu-id="d742d-168">Конечные пользователи могут управлять только отправленными ими сообщениями из карантина.</span><span class="sxs-lookup"><span data-stu-id="d742d-168">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="d742d-169">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="d742d-169">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="d742d-170">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d742d-170">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="d742d-171">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="d742d-171">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="d742d-172">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d742d-172">Wildcards aren't supported.</span></span> <span data-ttu-id="d742d-173">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="d742d-173">You can search by the following values:</span></span>

   - <span data-ttu-id="d742d-174">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="d742d-174">**Message ID** : The globally unique identifier of the message.</span></span>

     <span data-ttu-id="d742d-175">Например, [Трассировка сообщений](message-trace-scc.md) используется для поиска сообщения, отправленного пользователю в Организации, и определения того, что сообщение помещено в карантин, а не доставлено.</span><span class="sxs-lookup"><span data-stu-id="d742d-175">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="d742d-176">Обязательно укажите полное значение идентификатора сообщения, которое может включать угловые скобки ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="d742d-176">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="d742d-177">Пример: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="d742d-177">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="d742d-178">**Адрес электронной почты отправителя** : адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="d742d-178">**Sender email address** : A single sender's email address.</span></span>

   - <span data-ttu-id="d742d-179">**Имя политики** : используйте полное имя политики сообщения.</span><span class="sxs-lookup"><span data-stu-id="d742d-179">**Policy name** : Use the entire policy name of the message.</span></span> <span data-ttu-id="d742d-180">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="d742d-180">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="d742d-181">**Адрес электронной почты получателя** : адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="d742d-181">**Recipient email address** : A single recipient's email address.</span></span>

   - <span data-ttu-id="d742d-182">**Тема** : Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="d742d-182">**Subject** : Use the entire subject of the message.</span></span> <span data-ttu-id="d742d-183">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="d742d-183">The search is not case-sensitive.</span></span>
  
   - <span data-ttu-id="d742d-184">**Имя политики** : имя политики, ответственной за помещение сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="d742d-184">**Policy name** : The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="d742d-185">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить** , чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="d742d-185">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="d742d-186">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="d742d-186">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="d742d-187">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="d742d-187">View quarantined message details</span></span>

<span data-ttu-id="d742d-188">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d742d-188">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d742d-189">**Идентификатор сообщения** : Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="d742d-189">**Message ID** : The globally unique identifier for the message.</span></span>

- <span data-ttu-id="d742d-190">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="d742d-190">**Sender address**</span></span>

- <span data-ttu-id="d742d-191">**Получено** : Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="d742d-191">**Received** : The date/time when the message was received.</span></span>

- <span data-ttu-id="d742d-192">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d742d-192">**Subject**</span></span>

- <span data-ttu-id="d742d-193">**Причина карантина** : показывает, что сообщение было определено как **Нежелательная** почта, **массовый** , **Фишинг** , сопоставляемое правило обработки почты ( **правило транспорта** ) или оно было определено как содержащее **вредоносную** программу.</span><span class="sxs-lookup"><span data-stu-id="d742d-193">**Quarantine reason** : Shows if a message has been identified as **Spam** , **Bulk** , **Phish** , matched a mail flow rule ( **Transport rule** ), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="d742d-194">**Количество получателей**</span><span class="sxs-lookup"><span data-stu-id="d742d-194">**Recipient count**</span></span>

- <span data-ttu-id="d742d-195">**Получатели** : Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения** , чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="d742d-195">**Recipients** : If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="d742d-196">**Истекает** : дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="d742d-196">**Expires** : The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="d742d-197">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="d742d-197">**Released to** : All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="d742d-198">**Пока не выпустили** : все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="d742d-198">**Not yet released to** : All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="d742d-199">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="d742d-199">Take action on quarantined email</span></span>

<span data-ttu-id="d742d-200">После выбора сообщения у вас есть несколько вариантов действий с сообщениями в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="d742d-200">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d742d-201">**Сообщение об освобождении** : в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d742d-201">**Release message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="d742d-202">**Сообщения отчетов в корпорацию Майкрософт для анализа** : этот параметр выбран по умолчанию и сообщает о том, что сообщение помещено в карантин в корпорацию Майкрософт как ложное срабатывание.</span><span class="sxs-lookup"><span data-stu-id="d742d-202">**Report messages to Microsoft for analysis** : This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="d742d-203">Если сообщение помещено в карантин, является пакетным, фишингом или содержит вредоносные программы, сообщение также передается группе анализа нежелательной почты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d742d-203">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="d742d-204">В зависимости от их анализа можно настроить правила фильтрации нежелательной почты на уровне службы, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="d742d-204">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="d742d-205">Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d742d-205">Choose one of the following options:</span></span>
    - <span data-ttu-id="d742d-206">**Освобождение сообщений всем получателям**</span><span class="sxs-lookup"><span data-stu-id="d742d-206">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="d742d-207">**Освобождение сообщений определенным получателям**</span><span class="sxs-lookup"><span data-stu-id="d742d-207">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="d742d-208">**Разблокирование сообщений для других пользователей**</span><span class="sxs-lookup"><span data-stu-id="d742d-208">**Release messages to other people**</span></span>

  <span data-ttu-id="d742d-209">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="d742d-209">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="d742d-210">Примечания по выпуску сообщений:</span><span class="sxs-lookup"><span data-stu-id="d742d-210">Notes about releasing messages:</span></span>

  - <span data-ttu-id="d742d-211">Вы не можете выпустить сообщение для одного и того же получателя несколько раз.</span><span class="sxs-lookup"><span data-stu-id="d742d-211">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="d742d-212">В списке потенциальных получателей будут отображаться только получатели, не получившие сообщение.</span><span class="sxs-lookup"><span data-stu-id="d742d-212">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="d742d-213">**Просмотр заголовка сообщения** : Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="d742d-213">**View message header** : Choose this link to see the message header text.</span></span> <span data-ttu-id="d742d-214">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer** , чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке** , если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="d742d-214">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="d742d-215">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки** :</span><span class="sxs-lookup"><span data-stu-id="d742d-215">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers** :</span></span>

- <span data-ttu-id="d742d-216">**Предварительный просмотр сообщения** : в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d742d-216">**Preview message** : In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="d742d-217">**Исходный вид** : показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="d742d-217">**Source view** : Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="d742d-218">**Текстовое представление** : показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="d742d-218">**Text view** : Shows the message body in plain text.</span></span>

- <span data-ttu-id="d742d-219">**Удалить из карантина** : после нажатия кнопки **Да** в появившемся предупреждении сообщение немедленно удаляется без отправки первоначальным получателям.</span><span class="sxs-lookup"><span data-stu-id="d742d-219">**Remove from quarantine** : After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="d742d-220">**Загрузка сообщения** : В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения** , чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="d742d-220">**Download message** : In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="d742d-221">**Сообщение о отсылке** : в открывшейся всплывающей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d742d-221">**Submit message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="d742d-222">**Тип объекта** : **адрес электронной почты** (по умолчанию), **URL-адрес** или **вложение**.</span><span class="sxs-lookup"><span data-stu-id="d742d-222">**Object type** : **Email** (default), **URL** , or **Attachment**.</span></span>

  - <span data-ttu-id="d742d-223">**Формат отправки** : **идентификатор сетевого сообщения** (по умолчанию с соответствующим ЗНАЧЕНИЕМ в поле " **идентификатор сетевого сообщения** ") или " **файл** " (перейдите в локальный файл. EML или. MSG).</span><span class="sxs-lookup"><span data-stu-id="d742d-223">**Submission format** : **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="d742d-224">Обратите внимание, что если выбрать пункт **файл** , а затем выбрать **идентификатор сетевого сообщения** , начальное значение исчезнет.</span><span class="sxs-lookup"><span data-stu-id="d742d-224">Note that if you select **File** and then select **Network Message ID** , the initially value is gone.</span></span>

  - <span data-ttu-id="d742d-225">**Recipients** : введите в поле аренда одного исходного получателя сообщения или нажмите кнопку **выбрать все** , чтобы определить всех получателей.</span><span class="sxs-lookup"><span data-stu-id="d742d-225">**Recipients** : Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="d742d-226">Вы также можете выбрать команду **выделить все** , а затем удалить отдельных получателей.</span><span class="sxs-lookup"><span data-stu-id="d742d-226">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="d742d-227">**Причина отправки** : **не должен быть заблокирован** (по умолчанию) или **должен быть заблокирован**.</span><span class="sxs-lookup"><span data-stu-id="d742d-227">**Reason for submission** : **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="d742d-228">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d742d-228">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="d742d-229">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d742d-229">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="d742d-230">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="d742d-230">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="d742d-231">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия** , в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d742d-231">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="d742d-232">**Выпуск сообщений** : параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям** ; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="d742d-232">**Release messages** : The options are the same as when you release a single message, except you can't select **Release messages to specific recipients** ; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d742d-233">Рассмотрим следующий сценарий: john@gmail.com отправляет сообщение в faith@contoso.com и john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d742d-233">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="d742d-234">Gmail получателей это сообщение на две копии, которые направляются на карантин в качестве фишинга в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d742d-234">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="d742d-235">Администратор освобождает оба этих сообщения в admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d742d-235">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="d742d-236">Доставляется Первое выпущенное сообщение, которое достигает почтового ящика администратора.</span><span class="sxs-lookup"><span data-stu-id="d742d-236">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="d742d-237">Второе выпущенное сообщение идентифицируется как повторяющаяся Доставка и пропускается.</span><span class="sxs-lookup"><span data-stu-id="d742d-237">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="d742d-238">Сообщение идентифицируется как дубликаты, если у них одинаковый идентификатор сообщения и время получения.</span><span class="sxs-lookup"><span data-stu-id="d742d-238">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="d742d-239">**Удалить сообщения** : После нажатия кнопки **Да** в появившемся предупреждении сообщение будет немедленно удалено без отправки исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="d742d-239">**Delete messages** :  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="d742d-240">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d742d-240">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="d742d-241">Защитник Майкрософт для Office 365: использование центра безопасности & соответствия требованиям для управления файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="d742d-241">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="d742d-242">Процедуры для файлов, помещенных в карантин, в этом разделе доступны только для Microsoft Defender для Office 365 Plan 1 and Plan 2 подписчики.</span><span class="sxs-lookup"><span data-stu-id="d742d-242">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="d742d-243">В организациях с защитником для Office 365 администраторы могут управлять файлами, помещенными в карантин, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d742d-243">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="d742d-244">Чтобы включить защиту для этих файлов, ознакомьтесь [со статьей включение ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d742d-244">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="d742d-245">Просмотр файлов, помещенных в карантин</span><span class="sxs-lookup"><span data-stu-id="d742d-245">View quarantined files</span></span>

1. <span data-ttu-id="d742d-246">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="d742d-246">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="d742d-247">Изменение **представления, помещенного в карантин** , в **файлы** значений.</span><span class="sxs-lookup"><span data-stu-id="d742d-247">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="d742d-248">Можно выполнить сортировку по полю, щелкнув доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="d742d-248">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="d742d-249">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="d742d-249">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="d742d-250">Нажмите кнопку **изменить столбцы** , чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="d742d-250">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="d742d-251">По умолчанию столбцы помечаются звездочкой ( <sup>\*</sup> ).</span><span class="sxs-lookup"><span data-stu-id="d742d-251">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="d742d-252">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-252">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-253">**Расположение**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-253">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-254">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-254">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-255">**URL-адрес файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-255">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-256">**Размер файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-256">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-257">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-257">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-258">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d742d-258">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="d742d-259">**Определяется**</span><span class="sxs-lookup"><span data-stu-id="d742d-259">**Detected by**</span></span>
   - <span data-ttu-id="d742d-260">**Изменено временем**</span><span class="sxs-lookup"><span data-stu-id="d742d-260">**Modified by time**</span></span>

4. <span data-ttu-id="d742d-261">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="d742d-261">To filter the results, click **Filter**.</span></span> <span data-ttu-id="d742d-262">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="d742d-262">The available filters are:</span></span>

   - <span data-ttu-id="d742d-263">**Срок действия истекает** : Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="d742d-263">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="d742d-264">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="d742d-264">**Today**</span></span>
     - <span data-ttu-id="d742d-265">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="d742d-265">**Next 2 days**</span></span>
     - <span data-ttu-id="d742d-266">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="d742d-266">**Next 7 days**</span></span>
     - <span data-ttu-id="d742d-267">Настраиваемый диапазон дат и времени.</span><span class="sxs-lookup"><span data-stu-id="d742d-267">A custom date/time range.</span></span>
   - <span data-ttu-id="d742d-268">**Время получения**</span><span class="sxs-lookup"><span data-stu-id="d742d-268">**Received time**</span></span>
   - <span data-ttu-id="d742d-269">**Причина карантина** : единственным доступным значением является **вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="d742d-269">**Quarantine reason** : The only available value is **Malware**.</span></span>
   - <span data-ttu-id="d742d-270">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="d742d-270">**Policy type**</span></span>

<span data-ttu-id="d742d-271">Когда вы обнаружите определенный файл в карантине, выберите его, чтобы просмотреть сведения о нем, и выполните действия с ним (например, просмотр, освобождение, Загрузка или удаление сообщения).</span><span class="sxs-lookup"><span data-stu-id="d742d-271">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="d742d-272">Просмотр сведений о файле, помещенном в карантин</span><span class="sxs-lookup"><span data-stu-id="d742d-272">View quarantined file details</span></span>

<span data-ttu-id="d742d-273">При выборе файла в списке в всплывающей области **сведений** отображаются следующие сведения о файлах:</span><span class="sxs-lookup"><span data-stu-id="d742d-273">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d742d-274">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="d742d-274">**File Name**</span></span>
- <span data-ttu-id="d742d-275">**URL-адрес файла** : URL-адрес, определяющий расположение файла (например, в SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="d742d-275">**File URL** : URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="d742d-276">**Обнаружено вредоносное содержимое в** Дата и время, когда файл помещен в карантин.</span><span class="sxs-lookup"><span data-stu-id="d742d-276">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="d742d-277">**Expires** : Дата, когда файл будет удален из карантина.</span><span class="sxs-lookup"><span data-stu-id="d742d-277">**Expires** : The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="d742d-278">**Определяется: защитник** для Office 365 или антивредоносный модуль корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d742d-278">**Detected By** : Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="d742d-279">**Выпущено?**</span><span class="sxs-lookup"><span data-stu-id="d742d-279">**Released?**</span></span>
- <span data-ttu-id="d742d-280">**Имя вредоносной программы**</span><span class="sxs-lookup"><span data-stu-id="d742d-280">**Malware Name**</span></span>
- <span data-ttu-id="d742d-281">**Идентификатор документа** : уникальный идентификатор документа.</span><span class="sxs-lookup"><span data-stu-id="d742d-281">**Document ID** : A unique identifier for the document.</span></span>
- <span data-ttu-id="d742d-282">**Размер файла** : в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="d742d-282">**File Size** : In kilobytes (KB).</span></span>
- <span data-ttu-id="d742d-283">**Организация** Уникальный идентификатор организации.</span><span class="sxs-lookup"><span data-stu-id="d742d-283">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="d742d-284">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="d742d-284">**Last modified**</span></span>
- <span data-ttu-id="d742d-285">**Изменено** : пользователь, который последним изменил файл.</span><span class="sxs-lookup"><span data-stu-id="d742d-285">**Modified By** : The user who last modified the file.</span></span>
- <span data-ttu-id="d742d-286">**Безопасное значение хэш-алгоритма 256-bit (SHA-256)** : вы можете использовать это значение хэша, чтобы определить файл в других хранилищах репутации или в других расположениях в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="d742d-286">**Secure Hash Algorithm 256-bit (SHA-256) value** : You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="d742d-287">Выполнение действий с файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="d742d-287">Take action on quarantined files</span></span>

<span data-ttu-id="d742d-288">При выборе файла в списке можно выполнить следующие действия с файлом в всплывающей панели **сведений** :</span><span class="sxs-lookup"><span data-stu-id="d742d-288">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d742d-289">**Выпуски файлов** : выберите (по умолчанию) или отменить выбор **файлов отчета в корпорацию Майкрософт для анализа** , а затем нажмите кнопку **освободить файлы**.</span><span class="sxs-lookup"><span data-stu-id="d742d-289">**Release files** : Select (default) or unselect **Report files to Microsoft for analysis** , and then click **Release files**.</span></span>
- <span data-ttu-id="d742d-290">**Скачивание файла**</span><span class="sxs-lookup"><span data-stu-id="d742d-290">**Download file**</span></span>
- <span data-ttu-id="d742d-291">**Удаление файла из карантина**</span><span class="sxs-lookup"><span data-stu-id="d742d-291">**Remove file from quarantine**</span></span>

<span data-ttu-id="d742d-292">Если вы не Освободите или не удалите эти файлы, они будут удалены по истечении периода хранения на карантине по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d742d-292">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="d742d-293">Действия с несколькими файлами, помещенными в карантин</span><span class="sxs-lookup"><span data-stu-id="d742d-293">Actions on multiple quarantined files</span></span>

<span data-ttu-id="d742d-294">При выборе нескольких файлов, помещенных в карантин, в списке (до 100) отображается раскрывающаяся панель **массовых действий** , в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d742d-294">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="d742d-295">**Выпустить файлы**</span><span class="sxs-lookup"><span data-stu-id="d742d-295">**Release files**</span></span>
- <span data-ttu-id="d742d-296">**Удалить файлы** : после нажатия кнопки **Да** в появившемся предупреждении файлы сразу же удаляются.</span><span class="sxs-lookup"><span data-stu-id="d742d-296">**Delete files** :  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="d742d-297">Просмотр сообщений и файлов, помещенных в карантин, и управление ими с помощью Exchange Online PowerShell или отдельного EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="d742d-297">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="d742d-298">Для просмотра и управления сообщениями и файлами в карантине используются следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="d742d-298">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="d742d-299">Delete — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d742d-299">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="d742d-300">Export — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d742d-300">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="d742d-301">Get — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d742d-301">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="d742d-302">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Обратите внимание, что этот командлет предназначен только для сообщений, а не от вредоносных файлов из ATP для SharePoint Online, OneDrive для бизнеса или Teams.</span><span class="sxs-lookup"><span data-stu-id="d742d-302">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="d742d-303">Release — QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d742d-303">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
