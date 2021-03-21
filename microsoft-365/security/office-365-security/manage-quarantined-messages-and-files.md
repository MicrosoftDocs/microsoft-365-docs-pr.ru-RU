---
title: Управление сообщениями и файлами на карантине в качестве администратора
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Администраторы могут узнать, как просматривать и управлять карантинными сообщениями для всех пользователей в Exchange Online Protection (EOP). Администраторы организаций с Microsoft Defender для Office 365 также могут управлять карантинными файлами в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7fef752e8a02f7ed0dd4ed51854810a0d36d718b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926800"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="4ab59-104">Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в EOP</span><span class="sxs-lookup"><span data-stu-id="4ab59-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4ab59-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="4ab59-105">**Applies to**</span></span>
- [<span data-ttu-id="4ab59-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4ab59-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4ab59-107">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="4ab59-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4ab59-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ab59-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4ab59-109">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ab59-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="4ab59-110">Дополнительные сведения см. в сообщении электронной почты с [карантином в EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="4ab59-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="4ab59-111">Администраторы могут просматривать, выпускать и удалять все типы карантинов для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="4ab59-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="4ab59-112">Только администраторы могут управлять сообщениями, которые были на карантине в качестве вредоносных программ, фишинга с высокой уверенностью или в результате правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="4ab59-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="4ab59-113">Администраторы также могут сообщать о ложных срабатывавах в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4ab59-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="4ab59-114">Администраторы в организациях с Microsoft Defender для Office 365 также могут просматривать, скачивать и удалять карантинные файлы в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4ab59-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="4ab59-115">Просмотр и управление карантинными сообщениями в Центре обеспечения безопасности & или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="4ab59-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4ab59-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="4ab59-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4ab59-117">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="4ab59-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="4ab59-118">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="4ab59-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="4ab59-119">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4ab59-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4ab59-120">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="4ab59-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4ab59-121">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="4ab59-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4ab59-122">Чтобы принять меры по карантинным сообщениям для всех пользователей, необходимо быть членом  группы ролей **"Управление** организацией", "Администратор безопасности" или "Администратор <sup>\*</sup> карантина".</span><span class="sxs-lookup"><span data-stu-id="4ab59-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="4ab59-123">Для доступа только для чтения к карантинным сообщениям для всех пользователей необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="4ab59-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4ab59-124">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="4ab59-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="4ab59-125">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-125">**Notes**:</span></span>

  - <span data-ttu-id="4ab59-126">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ab59-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4ab59-127">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4ab59-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="4ab59-128">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="4ab59-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="4ab59-129"><sup>\*</sup>Члены группы  ролей администратора карантина также должны  быть членами группы ролей управления гигиеной в [Exchange Online,](/Exchange/permissions-exo/permissions-exo#role-groups) чтобы делать карантинные процедуры в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ab59-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="4ab59-130">Карантинные сообщения сохраняются в течение определенного периода времени по умолчанию, прежде чем они будут автоматически удалены:</span><span class="sxs-lookup"><span data-stu-id="4ab59-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="4ab59-131">30 дней для сообщений, карантинов с помощью политики защиты от нежелательной почты (спам, фишинг и массовая электронная почта).</span><span class="sxs-lookup"><span data-stu-id="4ab59-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="4ab59-132">Это значение по умолчанию и максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="4ab59-132">This is the default and maximum value.</span></span> <span data-ttu-id="4ab59-133">Чтобы настроить (ниже) это значение, см. в [перенастройке политики по борьбе со спамом.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4ab59-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="4ab59-134">15 дней для сообщений, содержащих вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="4ab59-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="4ab59-135">15 дней для файлов, на карантин для файлов SharePoint, OneDrive и Microsoft Teams в Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ab59-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="4ab59-136">После истечения срока действия сообщения из карантина его не восстановить.</span><span class="sxs-lookup"><span data-stu-id="4ab59-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="4ab59-137">Используйте Центр & безопасности для управления карантинными сообщениями электронной почты</span><span class="sxs-lookup"><span data-stu-id="4ab59-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="4ab59-138">Просмотр карантиновой электронной почты</span><span class="sxs-lookup"><span data-stu-id="4ab59-138">View quarantined email</span></span>

1. <span data-ttu-id="4ab59-139">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="4ab59-140">**Убедитесь, что значение View в карантине** установлено для электронной почты значения по **умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="4ab59-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="4ab59-141">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="4ab59-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="4ab59-142">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="4ab59-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="4ab59-143">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="4ab59-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="4ab59-144">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-145">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-146">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-147">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-148">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-149">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="4ab59-150">**Expires**</span></span>
   - <span data-ttu-id="4ab59-151">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="4ab59-151">**Recipient**</span></span>
   - <span data-ttu-id="4ab59-152">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="4ab59-152">**Message ID**</span></span>
   - <span data-ttu-id="4ab59-153">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="4ab59-153">**Policy name**</span></span>
   - <span data-ttu-id="4ab59-154">**Размер**</span><span class="sxs-lookup"><span data-stu-id="4ab59-154">**Size**</span></span>
   - <span data-ttu-id="4ab59-155">**Направление**</span><span class="sxs-lookup"><span data-stu-id="4ab59-155">**Direction**</span></span>

   <span data-ttu-id="4ab59-156">Когда все будет готово, нажмите кнопку **сохранить** или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="4ab59-157">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4ab59-158">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="4ab59-158">The available filters are:</span></span>

   - <span data-ttu-id="4ab59-159">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="4ab59-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="4ab59-160">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="4ab59-160">**Today**</span></span>
     - <span data-ttu-id="4ab59-161">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="4ab59-161">**Next 2 days**</span></span>
     - <span data-ttu-id="4ab59-162">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="4ab59-162">**Next 7 days**</span></span>
     - <span data-ttu-id="4ab59-163">**Настраиваемые**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4ab59-164">**Время получения**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4ab59-165">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="4ab59-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="4ab59-166">**Политика.** Сообщение соответствует условиям правила потока почты (также известного как правило транспорта).</span><span class="sxs-lookup"><span data-stu-id="4ab59-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="4ab59-167">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="4ab59-167">**Bulk**</span></span>
     - <span data-ttu-id="4ab59-168">**Фишинг.** Решение фильтра  нежелательной почты было фишинговое сообщение или защита от фишинга на карантине сообщения (параметры [spoof](set-up-anti-phishing-policies.md#spoof-settings) или защита от [обезличения).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="4ab59-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="4ab59-169">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="4ab59-169">**Malware**</span></span>
     - <span data-ttu-id="4ab59-170">**Спам**</span><span class="sxs-lookup"><span data-stu-id="4ab59-170">**Spam**</span></span>
     - <span data-ttu-id="4ab59-171">**Фишинг с высокой уверенностью**</span><span class="sxs-lookup"><span data-stu-id="4ab59-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="4ab59-172">**Тип политики**: фильтрация сообщений по типу политики:</span><span class="sxs-lookup"><span data-stu-id="4ab59-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="4ab59-173">**Политика борьбы с вредоносными программами**</span><span class="sxs-lookup"><span data-stu-id="4ab59-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="4ab59-174">**Политика безопасных вложений**</span><span class="sxs-lookup"><span data-stu-id="4ab59-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="4ab59-175">**Политика защиты от фишинга**</span><span class="sxs-lookup"><span data-stu-id="4ab59-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="4ab59-176">**Политика фильтрации размещенного содержимого** (политика защиты от нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="4ab59-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="4ab59-177">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="4ab59-177">**Transport rule**</span></span>

   - <span data-ttu-id="4ab59-178">**Получатель** электронной почты: все пользователи или только сообщения, отправленные вам.</span><span class="sxs-lookup"><span data-stu-id="4ab59-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="4ab59-179">Конечные пользователи могут управлять только отправленными на карантин сообщениями.</span><span class="sxs-lookup"><span data-stu-id="4ab59-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="4ab59-180">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="4ab59-181">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="4ab59-182">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ab59-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="4ab59-183">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4ab59-183">Wildcards aren't supported.</span></span> <span data-ttu-id="4ab59-184">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="4ab59-184">You can search by the following values:</span></span>

   - <span data-ttu-id="4ab59-185">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ab59-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="4ab59-186">Например, вы [](message-trace-scc.md) использовали трассировку сообщений, чтобы найти сообщение, отправленное пользователю в организации, и вы определяете, что сообщение было поставлено на карантин, а не доставлено.</span><span class="sxs-lookup"><span data-stu-id="4ab59-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="4ab59-187">Обязательно включив полное значение ID сообщения, которое может включать угловые скобки ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="4ab59-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="4ab59-188">Пример: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="4ab59-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="4ab59-189">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="4ab59-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="4ab59-190">**Имя политики**: используйте полное имя политики сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ab59-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="4ab59-191">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="4ab59-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="4ab59-192">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="4ab59-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="4ab59-193">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ab59-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="4ab59-194">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="4ab59-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="4ab59-195">**Имя политики.** Имя политики, ответственной за карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ab59-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="4ab59-196">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="4ab59-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="4ab59-197">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="4ab59-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="4ab59-198">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="4ab59-198">View quarantined message details</span></span>

<span data-ttu-id="4ab59-199">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="4ab59-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4ab59-200">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ab59-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="4ab59-201">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="4ab59-201">**Sender address**</span></span>

- <span data-ttu-id="4ab59-202">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ab59-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="4ab59-203">**Тема**</span><span class="sxs-lookup"><span data-stu-id="4ab59-203">**Subject**</span></span>

- <span data-ttu-id="4ab59-204">**Причина карантина**: Показывает, было ли сообщение идентифицировано как **спам,** массовый **,** **фишинг,** соответствует правилу потока почты **(правило** транспорта), или было определено как содержащее вредоносные **программы**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="4ab59-205">**Количество получателей**</span><span class="sxs-lookup"><span data-stu-id="4ab59-205">**Recipient count**</span></span>

- <span data-ttu-id="4ab59-206">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="4ab59-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="4ab59-207">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="4ab59-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="4ab59-208">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="4ab59-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="4ab59-209">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="4ab59-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="4ab59-210">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="4ab59-210">Take action on quarantined email</span></span>

<span data-ttu-id="4ab59-211">После выбора сообщения у вас есть несколько вариантов действий с сообщениями в области flyout **Details:**</span><span class="sxs-lookup"><span data-stu-id="4ab59-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4ab59-212">**Сообщение о выпуске:** В области вылетов, которая отображается, выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4ab59-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="4ab59-213">**Сообщение в Корпорацию Майкрософт** для анализа. Это выбирается по умолчанию и сообщает ошибочное сообщение на карантин в Корпорацию Майкрософт как ложное срабатывающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="4ab59-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="4ab59-214">Если сообщение было карантином как нежелательное, массовое, фишинговое или содержащее вредоносные программы, сообщение также сообщается в Команду анализа нежелательной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4ab59-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="4ab59-215">В зависимости от их анализа правила фильтра спама для всей службы могут быть скорректированы, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="4ab59-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="4ab59-216">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="4ab59-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="4ab59-217">**Выпуск сообщений для всех получателей**</span><span class="sxs-lookup"><span data-stu-id="4ab59-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="4ab59-218">**Выпуск сообщений определенным получателям**</span><span class="sxs-lookup"><span data-stu-id="4ab59-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="4ab59-219">**Выпуск сообщений другим людям:** Обратите внимание, что выпуск сообщений о вредоносных программах для других людей, кроме исходных получателей, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4ab59-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="4ab59-220">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="4ab59-221">Заметки о выпуске сообщений:</span><span class="sxs-lookup"><span data-stu-id="4ab59-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="4ab59-222">Нельзя выпускать сообщение одному получателю несколько раз.</span><span class="sxs-lookup"><span data-stu-id="4ab59-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="4ab59-223">В списке потенциальных получателей будут отображаться только получатели, которые не получили сообщение.</span><span class="sxs-lookup"><span data-stu-id="4ab59-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="4ab59-224">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ab59-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="4ab59-225">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="4ab59-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="4ab59-226">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="4ab59-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="4ab59-227">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="4ab59-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="4ab59-228">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="4ab59-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="4ab59-229">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="4ab59-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="4ab59-230">**Удаление из карантина.** После нажатия кнопки **Да** в предостережение, которое появится, сообщение немедленно удаляется, не отослано первоначальным получателям.</span><span class="sxs-lookup"><span data-stu-id="4ab59-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="4ab59-231">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="4ab59-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="4ab59-232">**Отправка сообщения.** В области вылетов, которая появится, выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4ab59-232">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="4ab59-233">**Тип объекта:** **электронная почта** (по умолчанию), **URL-адрес** или **вложение.**</span><span class="sxs-lookup"><span data-stu-id="4ab59-233">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="4ab59-234">**Формат отправки:** **Сетевой ID** сообщения (по умолчанию, с соответствующим значением в поле Сетевой **ID** сообщения) или **Файл** (просмотрите локальный файл .eml или .msg).</span><span class="sxs-lookup"><span data-stu-id="4ab59-234">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="4ab59-235">Обратите внимание, что если выбрать **файл,** а затем выбрать **сетевой ID** сообщения, исходное значение исчезнет.</span><span class="sxs-lookup"><span data-stu-id="4ab59-235">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="4ab59-236">**Получатели.** Введите в аренду одного исходного получателя сообщения или нажмите **кнопку Выберите все,** чтобы определить всех получателей.</span><span class="sxs-lookup"><span data-stu-id="4ab59-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="4ab59-237">Вы также можете нажать **кнопку Выберите все,** а затем выборочно удалить отдельных получателей.</span><span class="sxs-lookup"><span data-stu-id="4ab59-237">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="4ab59-238">**Причина отправки.** **Не должно было быть заблокировано** (по умолчанию) или должно быть **заблокировано**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-238">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="4ab59-239">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-239">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="4ab59-240">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ab59-240">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="4ab59-241">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="4ab59-241">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="4ab59-242">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4ab59-242">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="4ab59-243">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-243">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4ab59-244">Рассмотрим следующий сценарий: john@gmail.com отправляет сообщение в faith@contoso.com и john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4ab59-244">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="4ab59-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ab59-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="4ab59-246">Администратор выпускает оба этих сообщения в admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4ab59-246">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="4ab59-247">Доставлено первое выпущенное сообщение, которое достигает почтового ящика администратора.</span><span class="sxs-lookup"><span data-stu-id="4ab59-247">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="4ab59-248">Второе выпущенное сообщение определено как дублирующее сообщение и пропущено.</span><span class="sxs-lookup"><span data-stu-id="4ab59-248">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="4ab59-249">Сообщение идентифицировано как дубликаты, если у них один и тот же ID сообщения и получено время.</span><span class="sxs-lookup"><span data-stu-id="4ab59-249">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="4ab59-250">**Удаление сообщений.** После **нажатия** да в предостережение, которое появится, сообщения немедленно удаляются, не отосланы первоначальным получателям.</span><span class="sxs-lookup"><span data-stu-id="4ab59-250">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="4ab59-251">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-251">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="4ab59-252">Только Microsoft Defender для Office 365: используйте Центр & безопасности для управления карантинными файлами</span><span class="sxs-lookup"><span data-stu-id="4ab59-252">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="4ab59-253">Процедуры для карантинов в этом разделе доступны только подписчикам Microsoft Defender для Office 365 Plan 1 и Plan 2.</span><span class="sxs-lookup"><span data-stu-id="4ab59-253">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="4ab59-254">В организациях с Defender для Office 365 администраторы могут управлять карантинными файлами в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4ab59-254">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="4ab59-255">Чтобы включить защиту для этих файлов, см. в раздел Включить безопасные вложения [для SharePoint, OneDrive и Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4ab59-255">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="4ab59-256">Просмотр карантиных файлов</span><span class="sxs-lookup"><span data-stu-id="4ab59-256">View quarantined files</span></span>

1. <span data-ttu-id="4ab59-257">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-257">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="4ab59-258">Изменение **представления на карантин в** файлы **значений.**</span><span class="sxs-lookup"><span data-stu-id="4ab59-258">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="4ab59-259">Вы можете сортировать на поле, щелкнув доступный заглавной столбец.</span><span class="sxs-lookup"><span data-stu-id="4ab59-259">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="4ab59-260">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="4ab59-260">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="4ab59-261">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="4ab59-261">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="4ab59-262">Столбцы по умолчанию помечены звездочкой <sup>\*</sup> ():</span><span class="sxs-lookup"><span data-stu-id="4ab59-262">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="4ab59-263">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-263">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-264">**Расположение**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-264">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-265">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-265">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-266">**URL-адрес файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-266">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-267">**Размер файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-267">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-268">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-268">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-269">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ab59-269">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ab59-270">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="4ab59-270">**Detected by**</span></span>
   - <span data-ttu-id="4ab59-271">**Изменение по времени**</span><span class="sxs-lookup"><span data-stu-id="4ab59-271">**Modified by time**</span></span>

4. <span data-ttu-id="4ab59-272">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-272">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4ab59-273">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="4ab59-273">The available filters are:</span></span>

   - <span data-ttu-id="4ab59-274">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="4ab59-274">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="4ab59-275">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="4ab59-275">**Today**</span></span>
     - <span data-ttu-id="4ab59-276">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="4ab59-276">**Next 2 days**</span></span>
     - <span data-ttu-id="4ab59-277">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="4ab59-277">**Next 7 days**</span></span>
     - <span data-ttu-id="4ab59-278">Настраиваемый диапазон дат и времени.</span><span class="sxs-lookup"><span data-stu-id="4ab59-278">A custom date/time range.</span></span>
   - <span data-ttu-id="4ab59-279">**Получено время**</span><span class="sxs-lookup"><span data-stu-id="4ab59-279">**Received time**</span></span>
   - <span data-ttu-id="4ab59-280">**Причина карантина.** Единственным доступным значением является вредоносное **ПО.**</span><span class="sxs-lookup"><span data-stu-id="4ab59-280">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="4ab59-281">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="4ab59-281">**Policy type**</span></span>

<span data-ttu-id="4ab59-282">После поиска определенного файла с карантином выберите файл для просмотра сведений о нем и принятия мер по этому файлу (например, просмотр, выпуск, скачивание или удаление сообщения).</span><span class="sxs-lookup"><span data-stu-id="4ab59-282">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="4ab59-283">Просмотр сведений о карантине файлов</span><span class="sxs-lookup"><span data-stu-id="4ab59-283">View quarantined file details</span></span>

<span data-ttu-id="4ab59-284">При выборе файла в списке в области flyout **Details** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="4ab59-284">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4ab59-285">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="4ab59-285">**File Name**</span></span>
- <span data-ttu-id="4ab59-286">**URL-адрес** файла: URL-адрес, определяя расположение файла (например, в SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="4ab59-286">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="4ab59-287">**Вредоносный контент, обнаруженный на** Дата и время карантина файла.</span><span class="sxs-lookup"><span data-stu-id="4ab59-287">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="4ab59-288">**Истекает.** Дата удаления файла из карантина.</span><span class="sxs-lookup"><span data-stu-id="4ab59-288">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="4ab59-289">**Обнаружено:** Защитник для Office 365 или антивирусный двигатель Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4ab59-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="4ab59-290">**Выпущено?**</span><span class="sxs-lookup"><span data-stu-id="4ab59-290">**Released?**</span></span>
- <span data-ttu-id="4ab59-291">**Имя вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="4ab59-291">**Malware Name**</span></span>
- <span data-ttu-id="4ab59-292">**Идентификатор документа:** уникальный идентификатор документа.</span><span class="sxs-lookup"><span data-stu-id="4ab59-292">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="4ab59-293">**Размер файла:** в килобайтах (KB).</span><span class="sxs-lookup"><span data-stu-id="4ab59-293">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="4ab59-294">**Организация** Уникальный ID организации.</span><span class="sxs-lookup"><span data-stu-id="4ab59-294">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="4ab59-295">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="4ab59-295">**Last modified**</span></span>
- <span data-ttu-id="4ab59-296">**Изменено:** пользователь, который в последний раз изменил файл.</span><span class="sxs-lookup"><span data-stu-id="4ab59-296">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="4ab59-297">**Значение Secure Hash Algorithm 256-bit (SHA-256).** Это значение можно использовать для идентификации файла в других магазинах репутации или в других расположениях в среде.</span><span class="sxs-lookup"><span data-stu-id="4ab59-297">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="4ab59-298">Действие по карантинным файлам</span><span class="sxs-lookup"><span data-stu-id="4ab59-298">Take action on quarantined files</span></span>

<span data-ttu-id="4ab59-299">При выборе файла в списке можно принять следующие действия в  файле в области flyout Details:</span><span class="sxs-lookup"><span data-stu-id="4ab59-299">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4ab59-300">**Файлы выпуска:** Выберите (по умолчанию) или отклоните файлы **отчетов в Microsoft** для анализа, а затем нажмите **файлы выпуска**.</span><span class="sxs-lookup"><span data-stu-id="4ab59-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="4ab59-301">**Скачивание файла**</span><span class="sxs-lookup"><span data-stu-id="4ab59-301">**Download file**</span></span>
- <span data-ttu-id="4ab59-302">**Удаление файла из карантина**</span><span class="sxs-lookup"><span data-stu-id="4ab59-302">**Remove file from quarantine**</span></span>

<span data-ttu-id="4ab59-303">Если вы не отпустите или не удалите файлы, они будут удалены по истечении срока хранения карантина по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ab59-303">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="4ab59-304">Действия по нескольким карантинным файлам</span><span class="sxs-lookup"><span data-stu-id="4ab59-304">Actions on multiple quarantined files</span></span>

<span data-ttu-id="4ab59-305">При выборе нескольких карантинов в списке (до 100) появляется поле для вылетов массовых действий, в котором можно принять следующие действия: </span><span class="sxs-lookup"><span data-stu-id="4ab59-305">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="4ab59-306">**Файлы выпуска**</span><span class="sxs-lookup"><span data-stu-id="4ab59-306">**Release files**</span></span>
- <span data-ttu-id="4ab59-307">**Удаление файлов.** После нажатия **да** в предостережение, которое появится, файлы немедленно удаляются.</span><span class="sxs-lookup"><span data-stu-id="4ab59-307">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="4ab59-308">Используйте Exchange Online PowerShell или автономный EOP PowerShell для просмотра и управления карантинными сообщениями и файлами</span><span class="sxs-lookup"><span data-stu-id="4ab59-308">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="4ab59-309">Для просмотра и управления сообщениями и файлами в карантине используются такие коды, как:</span><span class="sxs-lookup"><span data-stu-id="4ab59-309">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="4ab59-310">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4ab59-310">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="4ab59-311">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4ab59-311">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="4ab59-312">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4ab59-312">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="4ab59-313">[Preview-QuarantineMessage.](/powershell/module/exchange/preview-quarantinemessage)Обратите внимание, что этот командлет только для сообщений, а не вредоносных файлов из безопасных вложений для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4ab59-313">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="4ab59-314">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4ab59-314">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)