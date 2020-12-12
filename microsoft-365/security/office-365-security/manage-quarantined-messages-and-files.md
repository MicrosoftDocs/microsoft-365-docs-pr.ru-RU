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
description: Администраторы могут узнать, как просматривать сообщения в карантине и управлять ими для всех пользователей в Exchange Online Protection (EOP). Администраторы в организациях с Microsoft Defender для Office 365 также могут управлять файлами, которые были на карантине, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.openlocfilehash: 5f4d63576e57ac50abe1ec1eb378221c4d457280
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659990"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="59048-104">Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в EOP</span><span class="sxs-lookup"><span data-stu-id="59048-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="59048-105">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="59048-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="59048-106">Дополнительные сведения см. в сообщениях электронной почты, отправленных на карантин, [в EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="59048-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="59048-107">Администраторы могут просматривать, освободить и удалять все типы сообщений на карантине для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="59048-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="59048-108">Только администраторы могут управлять сообщениями, которые были отправлены на карантин как вредоносные программы, фишинг с высокой достоверности или в результате правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="59048-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="59048-109">Администраторы также могут сообщать о ложных срабатывах в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="59048-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="59048-110">Администраторы организаций с Microsoft Defender для Office 365 также могут просматривать, скачивать и удалять файлы на карантине в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="59048-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="59048-111">Сообщения на карантине можно просматривать и управлять ими в Центре безопасности и & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="59048-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="59048-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="59048-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="59048-113">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="59048-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="59048-114">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="59048-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="59048-115">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="59048-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="59048-116">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="59048-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="59048-117">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="59048-117">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="59048-118">Чтобы принять меры в отношении сообщений в карантине для всех пользователей, необходимо быть  членом группы ролей "Управление организацией", "Администратор безопасности" или "Администратор <sup>\*</sup> карантина".</span><span class="sxs-lookup"><span data-stu-id="59048-118">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="59048-119">Для доступа только для чтения к сообщениям в карантине для всех пользователей  необходимо быть членом группы ролей **"Глобальный** читатель" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="59048-119">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="59048-120">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="59048-120">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="59048-121">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="59048-121">**Notes**:</span></span>

  - <span data-ttu-id="59048-122">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59048-122">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="59048-123">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="59048-123">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="59048-124">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="59048-124">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="59048-125"><sup>\*</sup>Для процедур  карантина в Exchange Online PowerShell члены группы ролей администратора карантина также должны быть членами группы ролей "Управление санатурой" в [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) </span><span class="sxs-lookup"><span data-stu-id="59048-125"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="59048-126">Сообщения на карантине сохраняются в течение периода времени по умолчанию перед их автоматическим удалением:</span><span class="sxs-lookup"><span data-stu-id="59048-126">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="59048-127">30 дней для сообщений, отправленных в карантин политиками защиты от нежелательной почты (спам, фишинг и массовая рассылка).</span><span class="sxs-lookup"><span data-stu-id="59048-127">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="59048-128">Это значение по умолчанию и максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="59048-128">This is the default and maximum value.</span></span> <span data-ttu-id="59048-129">Чтобы настроить (ниже) это значение, см. "Настройка политик борьбы [с нежелательной почтой".](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="59048-129">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="59048-130">15 дней для сообщений, содержащих вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="59048-130">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="59048-131">15 дней для файлов, которые ATP на карантине для SharePoint, OneDrive и Microsoft Teams в Защитнике Office 365.</span><span class="sxs-lookup"><span data-stu-id="59048-131">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="59048-132">По истечении срока действия сообщения из карантина восстановить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="59048-132">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="59048-133">Использование Центра безопасности & соответствия требованиям для управления сообщениями электронной почты, отправленными на карантин</span><span class="sxs-lookup"><span data-stu-id="59048-133">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="59048-134">Просмотр электронной почты, отправленной на карантин</span><span class="sxs-lookup"><span data-stu-id="59048-134">View quarantined email</span></span>

1. <span data-ttu-id="59048-135">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="59048-135">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="59048-136">**Убедитесь, что для просмотра сообщения** электронной почты в карантине установлено значение по **умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="59048-136">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="59048-137">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="59048-137">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="59048-138">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="59048-138">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="59048-139">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="59048-139">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="59048-140">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-140">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-141">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-141">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-142">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-142">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-143">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-143">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-144">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-144">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-145">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-145">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-146">**Expires**</span><span class="sxs-lookup"><span data-stu-id="59048-146">**Expires**</span></span>
   - <span data-ttu-id="59048-147">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="59048-147">**Recipient**</span></span>
   - <span data-ttu-id="59048-148">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="59048-148">**Message ID**</span></span>
   - <span data-ttu-id="59048-149">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="59048-149">**Policy name**</span></span>
   - <span data-ttu-id="59048-150">**Размер**</span><span class="sxs-lookup"><span data-stu-id="59048-150">**Size**</span></span>
   - <span data-ttu-id="59048-151">**Направление**</span><span class="sxs-lookup"><span data-stu-id="59048-151">**Direction**</span></span>

   <span data-ttu-id="59048-152">Когда все будет готово, нажмите кнопку **сохранить** или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="59048-152">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="59048-153">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="59048-153">To filter the results, click **Filter**.</span></span> <span data-ttu-id="59048-154">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="59048-154">The available filters are:</span></span>

   - <span data-ttu-id="59048-155">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="59048-155">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="59048-156">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="59048-156">**Today**</span></span>
     - <span data-ttu-id="59048-157">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="59048-157">**Next 2 days**</span></span>
     - <span data-ttu-id="59048-158">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="59048-158">**Next 7 days**</span></span>
     - <span data-ttu-id="59048-159">**Настраиваемые**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="59048-159">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="59048-160">**Время получения**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="59048-160">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="59048-161">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="59048-161">**Quarantine reason**:</span></span>
     - <span data-ttu-id="59048-162">**Политика:** сообщение соответствует условиям правила потока почты (также известного как правило транспорта).</span><span class="sxs-lookup"><span data-stu-id="59048-162">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="59048-163">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="59048-163">**Bulk**</span></span>
     - <span data-ttu-id="59048-164">**Фишинг**: решение фильтра нежелательной почты о том, что сообщение было отправлено на карантин фишинговой электронной почты или защита от фишинга [(](set-up-anti-phishing-policies.md#spoof-settings) параметры спуфинга или защита от  подмены). [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="59048-164">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="59048-165">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="59048-165">**Malware**</span></span>
     - <span data-ttu-id="59048-166">**Спам**</span><span class="sxs-lookup"><span data-stu-id="59048-166">**Spam**</span></span>
     - <span data-ttu-id="59048-167">**Фишинг с высокой достоверности**</span><span class="sxs-lookup"><span data-stu-id="59048-167">**High Confidence Phish**</span></span>

   - <span data-ttu-id="59048-168">**Тип политики**: фильтрация сообщений по типу политики:</span><span class="sxs-lookup"><span data-stu-id="59048-168">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="59048-169">**Политика борьбы с вредоносными программами**</span><span class="sxs-lookup"><span data-stu-id="59048-169">**Anti-malware policy**</span></span>
     - <span data-ttu-id="59048-170">**Политика безопасных вложений**</span><span class="sxs-lookup"><span data-stu-id="59048-170">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="59048-171">**Политика защиты от фишинга**</span><span class="sxs-lookup"><span data-stu-id="59048-171">**Anti-phish policy**</span></span>
     - <span data-ttu-id="59048-172">**Политика фильтрации размещенного содержимого** (политика защиты от нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="59048-172">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="59048-173">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="59048-173">**Transport rule**</span></span>

   - <span data-ttu-id="59048-174">**Получатель электронной** почты: все пользователи или только сообщения, отправленные вам.</span><span class="sxs-lookup"><span data-stu-id="59048-174">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="59048-175">Конечные пользователи могут управлять только отправленными на карантин сообщениями.</span><span class="sxs-lookup"><span data-stu-id="59048-175">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="59048-176">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="59048-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="59048-177">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="59048-177">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="59048-178">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="59048-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="59048-179">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="59048-179">Wildcards aren't supported.</span></span> <span data-ttu-id="59048-180">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="59048-180">You can search by the following values:</span></span>

   - <span data-ttu-id="59048-181">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="59048-181">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="59048-182">Например, вы [](message-trace-scc.md) использовали трассировку сообщений для искомого сообщения, отправленного пользователю в вашей организации, и определили, что сообщение было отправлено на карантин, а не доставлено.</span><span class="sxs-lookup"><span data-stu-id="59048-182">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="59048-183">Не забудьте включить полное значение ИД сообщения, которое может включать угловые скобки ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="59048-183">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="59048-184">Пример: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="59048-184">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="59048-185">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="59048-185">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="59048-186">**Имя политики**: используйте полное имя политики сообщения.</span><span class="sxs-lookup"><span data-stu-id="59048-186">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="59048-187">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="59048-187">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="59048-188">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="59048-188">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="59048-189">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="59048-189">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="59048-190">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="59048-190">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="59048-191">**Имя политики:** имя политики, ответственной за карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="59048-191">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="59048-192">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="59048-192">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="59048-193">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="59048-193">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="59048-194">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="59048-194">View quarantined message details</span></span>

<span data-ttu-id="59048-195">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="59048-195">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="59048-196">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="59048-196">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="59048-197">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="59048-197">**Sender address**</span></span>

- <span data-ttu-id="59048-198">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="59048-198">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="59048-199">**Тема**</span><span class="sxs-lookup"><span data-stu-id="59048-199">**Subject**</span></span>

- <span data-ttu-id="59048-200">Причина карантина: показывает, было ли сообщение определено как нежелательное, массовое, фишинговое, соответствует правилу потока почты **(** правило транспорта) или определено как содержащее **вредоносную программу.** </span><span class="sxs-lookup"><span data-stu-id="59048-200">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="59048-201">**Количество получателей**</span><span class="sxs-lookup"><span data-stu-id="59048-201">**Recipient count**</span></span>

- <span data-ttu-id="59048-202">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="59048-202">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="59048-203">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="59048-203">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="59048-204">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="59048-204">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="59048-205">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="59048-205">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="59048-206">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="59048-206">Take action on quarantined email</span></span>

<span data-ttu-id="59048-207">После выбора сообщения у вас есть несколько вариантов действий  с сообщениями во flyout области сведений:</span><span class="sxs-lookup"><span data-stu-id="59048-207">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="59048-208">**Сообщение о выпуске:** в отобра следующей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="59048-208">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="59048-209">**Сообщить о сообщениях** в корпорацию Майкрософт для анализа: этот выбор выбран по умолчанию, и сообщение о ошибочном карантине сообщается корпорации Майкрософт о ложном срабатывании.</span><span class="sxs-lookup"><span data-stu-id="59048-209">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="59048-210">Если сообщение было в карантине как нежелательное, массовое, фишинговое или содержащее вредоносную программу, сообщение также передается в службу анализа нежелательной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="59048-210">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="59048-211">В зависимости от их анализа правила фильтрации нежелательной почты для всей службы могут быть настроены, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="59048-211">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="59048-212">Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="59048-212">Choose one of the following options:</span></span>
    - <span data-ttu-id="59048-213">**Освобождение сообщений для всех получателей**</span><span class="sxs-lookup"><span data-stu-id="59048-213">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="59048-214">**Освобождение сообщений для определенных получателей**</span><span class="sxs-lookup"><span data-stu-id="59048-214">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="59048-215">**Освобождать сообщения другим людям:** обратите внимание, что освобождение вредоносных сообщений для людей, кроме исходных получателей, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="59048-215">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="59048-216">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="59048-216">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="59048-217">Примечания об освобождении сообщений:</span><span class="sxs-lookup"><span data-stu-id="59048-217">Notes about releasing messages:</span></span>

  - <span data-ttu-id="59048-218">Вы не можете освободить сообщение для одного и того же получателя более одного раза.</span><span class="sxs-lookup"><span data-stu-id="59048-218">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="59048-219">В списке потенциальных получателей будут отображаться только те получатели, которые не получили сообщение.</span><span class="sxs-lookup"><span data-stu-id="59048-219">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="59048-220">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="59048-220">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="59048-221">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="59048-221">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="59048-222">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="59048-222">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="59048-223">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="59048-223">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="59048-224">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="59048-224">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="59048-225">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="59048-225">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="59048-226">**Удаление из** карантина:  после нажатия кнопки "Да" в отображемом предупреждении сообщение немедленно удаляется, не отправив его исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="59048-226">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="59048-227">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="59048-227">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="59048-228">**Отправка сообщения:** в отобра следующей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="59048-228">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="59048-229">**Тип объекта:** **электронная почта** (по умолчанию), **URL-адрес** или **вложение.**</span><span class="sxs-lookup"><span data-stu-id="59048-229">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="59048-230">**Формат отправки:** **сетевой** ИД сообщения (по  умолчанию с соответствующим значением в поле "ИД сетевого сообщения") или **"Файл"** (перейдите к локальному EML-файлу или MSG-файлу).</span><span class="sxs-lookup"><span data-stu-id="59048-230">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="59048-231">Обратите внимание, что если **выбрать** файл и затем **выбрать** сетевой ИД сообщения, исходное значение исчезнет.</span><span class="sxs-lookup"><span data-stu-id="59048-231">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="59048-232">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span><span class="sxs-lookup"><span data-stu-id="59048-232">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="59048-233">Можно также **щелкнуть "Выбрать все",** а затем выборочно удалить отдельных получателей.</span><span class="sxs-lookup"><span data-stu-id="59048-233">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="59048-234">**Причина отправки:** **не должна быть заблокирована (по** умолчанию) или **должна быть заблокирована.**</span><span class="sxs-lookup"><span data-stu-id="59048-234">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="59048-235">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="59048-235">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="59048-236">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="59048-236">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="59048-237">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="59048-237">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="59048-238">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="59048-238">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="59048-239">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="59048-239">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="59048-240">Рассмотрим следующий сценарий: john@gmail.com отправляет сообщение faith@contoso.com и john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="59048-240">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="59048-241">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59048-241">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="59048-242">Администратор освобождает оба этих сообщения для admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="59048-242">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="59048-243">Доставляется первое выпущенное сообщение, которое достигает почтового ящика администратора.</span><span class="sxs-lookup"><span data-stu-id="59048-243">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="59048-244">Второе выпущенное сообщение будет определено как дублирующееся и пропущено.</span><span class="sxs-lookup"><span data-stu-id="59048-244">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="59048-245">Сообщения идентифицированы как дубликаты, если они имеют одинаковый ИД сообщения и получили время.</span><span class="sxs-lookup"><span data-stu-id="59048-245">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="59048-246">**Удаление сообщений:** после нажатия кнопки **"Да"** в отображемом предупреждении сообщения немедленно удаляются, не отправив их исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="59048-246">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="59048-247">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="59048-247">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="59048-248">Только Microsoft Defender для Office 365: управление файлами на карантине с помощью Центра безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="59048-248">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="59048-249">Процедуры для файлов на карантине в этом разделе доступны только в Microsoft Defender для подписчиков Office 365 (план 1) и 2 (план 2).</span><span class="sxs-lookup"><span data-stu-id="59048-249">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="59048-250">В организациях с Защитником Office 365 администраторы могут управлять файлами на карантине в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="59048-250">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="59048-251">Чтобы включить защиту для этих файлов, см. раздел ["Включить ATP для SharePoint, OneDrive и Microsoft Teams".](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="59048-251">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="59048-252">Просмотр файлов на карантине</span><span class="sxs-lookup"><span data-stu-id="59048-252">View quarantined files</span></span>

1. <span data-ttu-id="59048-253">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="59048-253">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="59048-254">Измените **представление в карантине** на файлы **значений.**</span><span class="sxs-lookup"><span data-stu-id="59048-254">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="59048-255">Можно отсортировать поле, щелкнув доступный заголок столбца.</span><span class="sxs-lookup"><span data-stu-id="59048-255">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="59048-256">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="59048-256">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="59048-257">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="59048-257">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="59048-258">Столбцы по умолчанию помечены звездочкой ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="59048-258">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="59048-259">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-259">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-260">**Расположение**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-260">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-261">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-261">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-262">**URL-адрес файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-262">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-263">**Размер файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-263">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-264">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-264">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-265">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="59048-265">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="59048-266">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="59048-266">**Detected by**</span></span>
   - <span data-ttu-id="59048-267">**Изменено по времени**</span><span class="sxs-lookup"><span data-stu-id="59048-267">**Modified by time**</span></span>

4. <span data-ttu-id="59048-268">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="59048-268">To filter the results, click **Filter**.</span></span> <span data-ttu-id="59048-269">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="59048-269">The available filters are:</span></span>

   - <span data-ttu-id="59048-270">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="59048-270">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="59048-271">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="59048-271">**Today**</span></span>
     - <span data-ttu-id="59048-272">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="59048-272">**Next 2 days**</span></span>
     - <span data-ttu-id="59048-273">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="59048-273">**Next 7 days**</span></span>
     - <span data-ttu-id="59048-274">Настраиваемый диапазон дат и времени.</span><span class="sxs-lookup"><span data-stu-id="59048-274">A custom date/time range.</span></span>
   - <span data-ttu-id="59048-275">**Получено время**</span><span class="sxs-lookup"><span data-stu-id="59048-275">**Received time**</span></span>
   - <span data-ttu-id="59048-276">**Причина карантина:** единственное доступное значение — **вредоносная программа.**</span><span class="sxs-lookup"><span data-stu-id="59048-276">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="59048-277">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="59048-277">**Policy type**</span></span>

<span data-ttu-id="59048-278">После того как вы найдете определенный файл на карантине, выберите его, чтобы просмотреть сведения о нем и принять с него меры (например, просмотреть, освободить, скачать или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="59048-278">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="59048-279">Просмотр сведений о файле в карантине</span><span class="sxs-lookup"><span data-stu-id="59048-279">View quarantined file details</span></span>

<span data-ttu-id="59048-280">При выборе файла в списке в области "Сведения" отображаются следующие сведения о файле: </span><span class="sxs-lookup"><span data-stu-id="59048-280">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="59048-281">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="59048-281">**File Name**</span></span>
- <span data-ttu-id="59048-282">**URL-адрес** файла: URL-адрес, который определяет расположение файла (например, в SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="59048-282">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="59048-283">**Вредоносный контент, обнаруженный в** Дата и время, когда файл был карантин.</span><span class="sxs-lookup"><span data-stu-id="59048-283">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="59048-284">**Истекает** срок действия: дата удаления файла из карантина.</span><span class="sxs-lookup"><span data-stu-id="59048-284">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="59048-285">**Обнаружено :** Защитник Office 365 или антивредоносный механизм Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="59048-285">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="59048-286">**Выпущено?**</span><span class="sxs-lookup"><span data-stu-id="59048-286">**Released?**</span></span>
- <span data-ttu-id="59048-287">**Имя вредоносной программы**</span><span class="sxs-lookup"><span data-stu-id="59048-287">**Malware Name**</span></span>
- <span data-ttu-id="59048-288">**Идентификатор документа:** уникальный идентификатор документа.</span><span class="sxs-lookup"><span data-stu-id="59048-288">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="59048-289">**Размер файла:** в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="59048-289">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="59048-290">**Организация** Уникальный ИД организации.</span><span class="sxs-lookup"><span data-stu-id="59048-290">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="59048-291">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="59048-291">**Last modified**</span></span>
- <span data-ttu-id="59048-292">**Изменено** пользователем, который последним изменил файл.</span><span class="sxs-lookup"><span data-stu-id="59048-292">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="59048-293">Значение **secure Hash Algorithm 256-bit (SHA-256):** это значение можно использовать для идентификации файла в других хранилищах репутации или в других расположениях в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="59048-293">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="59048-294">Действие с файлами в карантине</span><span class="sxs-lookup"><span data-stu-id="59048-294">Take action on quarantined files</span></span>

<span data-ttu-id="59048-295">При выборе файла в списке можно сделать следующие действия с  файлом во flyout pane:</span><span class="sxs-lookup"><span data-stu-id="59048-295">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="59048-296">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span><span class="sxs-lookup"><span data-stu-id="59048-296">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="59048-297">**Скачивание файла**</span><span class="sxs-lookup"><span data-stu-id="59048-297">**Download file**</span></span>
- <span data-ttu-id="59048-298">**Удаление файла из карантина**</span><span class="sxs-lookup"><span data-stu-id="59048-298">**Remove file from quarantine**</span></span>

<span data-ttu-id="59048-299">Если вы не освободите или не удалите файлы, они будут удалены по истечении срока хранения карантина по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="59048-299">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="59048-300">Действия с несколькими файлами на карантине</span><span class="sxs-lookup"><span data-stu-id="59048-300">Actions on multiple quarantined files</span></span>

<span data-ttu-id="59048-301">При выборе нескольких файлов на карантине в списке (до  100) появляется flyout pane массовых действий, где можно сделать следующие действия:</span><span class="sxs-lookup"><span data-stu-id="59048-301">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="59048-302">**Выпуск файлов**</span><span class="sxs-lookup"><span data-stu-id="59048-302">**Release files**</span></span>
- <span data-ttu-id="59048-303">**Удаление файлов:** после нажатия кнопки **"Да"** в от имени предупреждения файлы немедленно удаляются.</span><span class="sxs-lookup"><span data-stu-id="59048-303">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="59048-304">Использование Exchange Online PowerShell или автономный EOP PowerShell для просмотра сообщений и файлов на карантине и управления ими</span><span class="sxs-lookup"><span data-stu-id="59048-304">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="59048-305">Для просмотра сообщений и файлов в карантине и управления ими используются:</span><span class="sxs-lookup"><span data-stu-id="59048-305">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="59048-306">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="59048-306">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="59048-307">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="59048-307">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="59048-308">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="59048-308">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="59048-309">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): обратите внимание, что этот командлет только для сообщений, а не для файлов вредоносных программ из ATP для SharePoint Online, OneDrive для бизнеса или Teams.</span><span class="sxs-lookup"><span data-stu-id="59048-309">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="59048-310">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="59048-310">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
