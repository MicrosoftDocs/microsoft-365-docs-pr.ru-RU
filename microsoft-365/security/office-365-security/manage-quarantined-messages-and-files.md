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
description: Администраторы могут узнать, как просматривать сообщения в карантине и управлять ими для всех пользователей в Exchange Online Protection (EOP). Администраторы в организациях с Microsoft Defender для Office 365 также могут управлять файлами, которые были на карантине, в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 22bcf0cefb746e92ccadf8254f4076b47ee475c4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287789"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="e0d5f-104">Управление сообщениями и файлами, помещенными в карантин, в качестве администратора в EOP</span><span class="sxs-lookup"><span data-stu-id="e0d5f-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e0d5f-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-105">**Applies to**</span></span>
- [<span data-ttu-id="e0d5f-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e0d5f-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e0d5f-107">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="e0d5f-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e0d5f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0d5f-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e0d5f-109">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="e0d5f-110">Дополнительные сведения см. в сообщениях электронной почты, отправленных на карантин, [в EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="e0d5f-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e0d5f-111">Администраторы могут просматривать, освободить и удалять все типы сообщений на карантине для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="e0d5f-112">Только администраторы могут управлять сообщениями, которые были отправлены на карантин как вредоносные программы, фишинг с высокой достоверности или в результате правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e0d5f-113">Администраторы также могут сообщать о ложных срабатывах в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="e0d5f-114">Администраторы организаций с Microsoft Defender для Office 365 также могут просматривать, скачивать и удалять файлы на карантине в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="e0d5f-115">Сообщения, отправленные на карантин, можно просматривать и управлять ими в Центре безопасности и & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e0d5f-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e0d5f-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e0d5f-117">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="e0d5f-118">Чтобы открыть страницу Карантина напрямую, перейдите на <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="e0d5f-119">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e0d5f-120">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e0d5f-121">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-121">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e0d5f-122">Чтобы принять меры в отношении сообщений на карантине для всех пользователей, необходимо быть  членом группы ролей "Управление организацией", "Администратор безопасности" или "Администратор <sup>\*</sup> карантина".</span><span class="sxs-lookup"><span data-stu-id="e0d5f-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="e0d5f-123">Для доступа всех пользователей к сообщениям в карантине, доступных только для  чтения, необходимо быть членом группы ролей **"Глобальный** читатель" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="e0d5f-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e0d5f-124">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="e0d5f-125">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-125">**Notes**:</span></span>

  - <span data-ttu-id="e0d5f-126">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e0d5f-127">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="e0d5f-128">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="e0d5f-129"><sup>\*</sup>Для процедур  карантина в Exchange Online PowerShell члены группы ролей администратора карантина также должны быть членами группы ролей "Управление санатурой" в [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) </span><span class="sxs-lookup"><span data-stu-id="e0d5f-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="e0d5f-130">Сообщения на карантине сохраняются в течение периода времени по умолчанию перед их автоматическим удалением:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="e0d5f-131">30 дней для сообщений, отправленных в карантин политиками защиты от нежелательной почты (спам, фишинг и массовая рассылка).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="e0d5f-132">Это значение по умолчанию и максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-132">This is the default and maximum value.</span></span> <span data-ttu-id="e0d5f-133">Чтобы настроить (ниже) это значение, см. "Настройка политик борьбы [с нежелательной почтой".](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e0d5f-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="e0d5f-134">15 дней для сообщений, содержащих вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="e0d5f-135">15 дней для файлов, вложенных в карантин с помощью безопасных вложений для SharePoint, OneDrive и Microsoft Teams в Защитнике Office 365.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="e0d5f-136">По истечении срока действия сообщения из карантина восстановить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="e0d5f-137">Использование Центра безопасности & соответствия требованиям для управления сообщениями электронной почты, отправленными на карантин</span><span class="sxs-lookup"><span data-stu-id="e0d5f-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="e0d5f-138">Просмотр электронной почты, отправленной на карантин</span><span class="sxs-lookup"><span data-stu-id="e0d5f-138">View quarantined email</span></span>

1. <span data-ttu-id="e0d5f-139">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e0d5f-140">**Убедитесь, что для просмотра сообщения** электронной почты в карантине установлено значение по **умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="e0d5f-141">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e0d5f-142">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e0d5f-143">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="e0d5f-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e0d5f-144">**Получено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-145">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-146">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-147">**Причина карантина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-148">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-149">**Тип политики**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-150">**Expires**</span></span>
   - <span data-ttu-id="e0d5f-151">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-151">**Recipient**</span></span>
   - <span data-ttu-id="e0d5f-152">**КОД сообщения**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-152">**Message ID**</span></span>
   - <span data-ttu-id="e0d5f-153">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-153">**Policy name**</span></span>
   - <span data-ttu-id="e0d5f-154">**Размер**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-154">**Size**</span></span>
   - <span data-ttu-id="e0d5f-155">**Направление**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-155">**Direction**</span></span>

   <span data-ttu-id="e0d5f-156">Когда все будет готово, нажмите кнопку **сохранить** или выберите пункт **назначить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="e0d5f-157">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e0d5f-158">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-158">The available filters are:</span></span>

   - <span data-ttu-id="e0d5f-159">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="e0d5f-160">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-160">**Today**</span></span>
     - <span data-ttu-id="e0d5f-161">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-161">**Next 2 days**</span></span>
     - <span data-ttu-id="e0d5f-162">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-162">**Next 7 days**</span></span>
     - <span data-ttu-id="e0d5f-163">**Настраиваемые**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e0d5f-164">**Время получения**: введите **дату начала** и **конечную дату**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e0d5f-165">**Причина карантина**:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="e0d5f-166">**Политика:** сообщение соответствует условиям правила потока почты (также известного как правило транспорта).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="e0d5f-167">**Массовая рассылка**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-167">**Bulk**</span></span>
     - <span data-ttu-id="e0d5f-168">**Фишинг**: решением  фильтра нежелательной почты было фишинговое сообщение или защита от фишинга, которое было отправлено на карантин сообщения [(параметры](set-up-anti-phishing-policies.md#spoof-settings) спуфинга или защита от [подмены).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="e0d5f-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="e0d5f-169">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-169">**Malware**</span></span>
     - <span data-ttu-id="e0d5f-170">**Спам**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-170">**Spam**</span></span>
     - <span data-ttu-id="e0d5f-171">**Фишинг с высокой достоверности**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="e0d5f-172">**Тип политики**: фильтрация сообщений по типу политики:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="e0d5f-173">**Политика борьбы с вредоносными программами**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="e0d5f-174">**Политика безопасных вложений**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="e0d5f-175">**Политика защиты от фишинга**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="e0d5f-176">**Политика фильтрации размещенного содержимого** (политика защиты от нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="e0d5f-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="e0d5f-177">**Правило транспорта**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-177">**Transport rule**</span></span>

   - <span data-ttu-id="e0d5f-178">**Получатель электронной** почты: все пользователи или только сообщения, отправленные вам.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="e0d5f-179">Конечные пользователи могут управлять только отправленными на карантин сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="e0d5f-180">Чтобы очистить фильтр, нажмите **Очистить**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="e0d5f-181">Чтобы скрыть всплывающую подсказку фильтра, снова нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="e0d5f-182">Используйте **Сортировку результатов по** (кнопка **ID сообщения** по умолчанию) и соответствующее значение, чтобы найти конкретные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="e0d5f-183">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-183">Wildcards aren't supported.</span></span> <span data-ttu-id="e0d5f-184">Вы можете искать по следующим значениям:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-184">You can search by the following values:</span></span>

   - <span data-ttu-id="e0d5f-185">**Идентификатор сообщения**. Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="e0d5f-186">Например, вы [](message-trace-scc.md) использовали трассировку сообщений для того, чтобы найти сообщение, отправленное пользователю в вашей организации, и определили, что сообщение было отправлено на карантин, а не доставлено.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="e0d5f-187">Не забудьте включить полное значение ИД сообщения, которое может включать угловые скобки ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="e0d5f-188">Пример: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="e0d5f-189">**Адрес электронной почты отправителя**: адрес электронной почты одного отправителя.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="e0d5f-190">**Имя политики**: используйте полное имя политики сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="e0d5f-191">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="e0d5f-192">**Адрес электронной почты получателя**: адрес электронной почты одного получателя.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="e0d5f-193">**Тема**: Используйте всю тему сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="e0d5f-194">При поиске регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="e0d5f-195">**Имя политики:** имя политики, ответственной за карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="e0d5f-196">После того, как вы ввели критерии поиска, нажмите ![кнопку Обновить](../../media/scc-quarantine-refresh.png) **Обновить**, чтобы обновить результаты.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="e0d5f-197">После того, как вы найдете конкретное сообщение на карантине, выберите сообщение, чтобы просмотреть сведения о нем и принять меры к нему (например, просмотреть, выпустить, загрузить или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="e0d5f-198">Просмотр сведений о карантине</span><span class="sxs-lookup"><span data-stu-id="e0d5f-198">View quarantined message details</span></span>

<span data-ttu-id="e0d5f-199">При выборе сообщения электронной почты в списке на всплывающей панели **Сведения** отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e0d5f-200">**Идентификатор сообщения**: Глобальный уникальный идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="e0d5f-201">**Адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-201">**Sender address**</span></span>

- <span data-ttu-id="e0d5f-202">**Получено**: Дата и время получения сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="e0d5f-203">**Тема**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-203">**Subject**</span></span>

- <span data-ttu-id="e0d5f-204">Причина карантина: показывает, было ли сообщение определено как нежелательное, массовое, фишинговое, соответствует правилу потока почты **(** правило транспорта) или определено как содержащее **вредоносную программу.** </span><span class="sxs-lookup"><span data-stu-id="e0d5f-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="e0d5f-205">**Количество получателей**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-205">**Recipient count**</span></span>

- <span data-ttu-id="e0d5f-206">**Получатели**: Если в сообщении содержится несколько получателей, вам необходимо нажать **Просмотр сообщения** или **Просмотреть заголовок сообщения**, чтобы просмотреть полный список получателей.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="e0d5f-207">**Истекает**: дата / время, когда сообщение будет автоматически и окончательно удалено из карантина.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="e0d5f-208">**Разблокировано для пользователей**. Все электронные адреса (если таковые имеются), для которых сообщение было освобождено.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="e0d5f-209">**Пока не выпустили**: все адреса электронной почты (если таковые имеются), на которые еще не было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="e0d5f-210">Выполнение действий с электронной почтой в карантине</span><span class="sxs-lookup"><span data-stu-id="e0d5f-210">Take action on quarantined email</span></span>

<span data-ttu-id="e0d5f-211">После выбора сообщения у вас есть несколько вариантов действий  с сообщениями во flyout области сведений:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e0d5f-212">**Сообщение о выпуске:** в отобра следующей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e0d5f-213">**Сообщить о сообщениях** в корпорацию Майкрософт для анализа: этот выбор выбран по умолчанию и сообщает о ошибочном срабатынии сообщения в карантине корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="e0d5f-214">Если сообщение было в карантине как нежелательное, массовое, фишинговое или содержащее вредоносную программу, сообщение также передается в службу анализа нежелательной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="e0d5f-215">В зависимости от их анализа правила фильтрации нежелательной почты для всей службы могут быть настроены, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="e0d5f-216">Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="e0d5f-217">**Освобождение сообщений для всех получателей**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="e0d5f-218">**Освобождение сообщений для определенных получателей**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="e0d5f-219">**Освобождать сообщения другим людям:** обратите внимание, что освобождение вредоносных сообщений для людей, кроме исходных получателей, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="e0d5f-220">Когда все будет готово, нажмите кнопку **Выпуск сообщений**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="e0d5f-221">Примечания об освобождении сообщений:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="e0d5f-222">Вы не можете освободить сообщение для одного и того же получателя более одного раза.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="e0d5f-223">В списке потенциальных получателей будут отображаться только те получатели, которые не получили сообщение.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="e0d5f-224">**Просмотр заголовка сообщения**: Выберите эту ссылку, чтобы просмотреть текст заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="e0d5f-225">Чтобы подробно проанализировать поля и значения заголовков, скопируйте текст заголовка сообщения в буфер обмена, а затем выберите **Microsoft Message Header Analyzer**, чтобы перейти к анализатору удаленных подключений (щелкните правой кнопкой мыши и выберите **Открыть на новой вкладке**, если вы не хотите закрывать Microsoft 365 для выполнения этой задачи).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="e0d5f-226">Вставьте заголовок сообщения на страницу в разделе «Анализатор заголовков сообщений» и выберите **Анализировать заголовки**:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="e0d5f-227">**Предварительный просмотр сообщения**: в появившейся всплывающей панели выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="e0d5f-228">**Исходный вид**: показывает HTML-версию тела сообщения со всеми отключенными ссылками.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="e0d5f-229">**Текстовое представление**: показывает текст сообщения в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="e0d5f-230">**Удаление из** карантина: после нажатия кнопки **"Да"** в отображемом предупреждении сообщение немедленно удаляется, не отправив его исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="e0d5f-231">**Загрузка сообщения**: В появившейся всплывающей панели выберите **Я понимаю риски, связанные с загрузкой этого сообщения**, чтобы сохранить локальную копию сообщения в формате .eml.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="e0d5f-232">**Отправка сообщения:** в отобра следующей области выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-232">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e0d5f-233">**Тип объекта:** **электронная почта** (по умолчанию), **URL-адрес** или **вложение.**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-233">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="e0d5f-234">**Формат отправки:** **сетевой** ИД сообщения (по  умолчанию с соответствующим значением в поле "ИД сетевого сообщения") или **"Файл"** (перейдите к локальному EML-файлу или MSG-файлу).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-234">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="e0d5f-235">Обратите внимание, что если **выбрать** файл и затем **выбрать** сетевой ИД сообщения, исходное значение исчезнет.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-235">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="e0d5f-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="e0d5f-237">Можно также **щелкнуть "Выбрать все",** а затем выборочно удалить отдельных получателей.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-237">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="e0d5f-238">**Причина отправки:** **не должна быть заблокирована (по** умолчанию) или **должна быть заблокирована.**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-238">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="e0d5f-239">По завершению нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-239">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="e0d5f-240">Если вы не отпустите или не удалите сообщение, оно будет удалено после истечения срока хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-240">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="e0d5f-241">Принять меры к нескольким сообщениям в карантине</span><span class="sxs-lookup"><span data-stu-id="e0d5f-241">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="e0d5f-242">При выборе нескольких сообщений в карантине в списке (до 100) появляется всплывающая панель **Массовые действия**, в которой можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-242">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e0d5f-243">**Выпуск сообщений**: параметры те же, что и при выпуске одного сообщения, за исключением того, что вы не можете выбрать **Отпускать сообщения конкретным получателям**; Вы можете выбрать только **Выпустить сообщение всем получателям** или **Выпустить сообщения другим людям**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-243">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e0d5f-244">Рассмотрим следующий сценарий: john@gmail.com отправляет сообщение faith@contoso.com и john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-244">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="e0d5f-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="e0d5f-246">Администратор освобождает оба этих сообщения для admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-246">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="e0d5f-247">Доставляется первое выпущенное сообщение, которое достигает почтового ящика администратора.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-247">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="e0d5f-248">Второе выпущенное сообщение будет определено как дублирующееся и пропущено.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-248">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="e0d5f-249">Сообщения идентифицированы как дубликаты, если они имеют одинаковый ИД сообщения и получили время.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-249">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="e0d5f-250">**Удаление сообщений:** после нажатия кнопки **"Да"** в отображемом предупреждении сообщения немедленно удаляются, не отправив их исходным получателям.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-250">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="e0d5f-251">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-251">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="e0d5f-252">Только Microsoft Defender для Office 365: управление файлами на карантине с помощью Центра безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="e0d5f-252">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="e0d5f-253">Процедуры для файлов на карантине, которые находятся в этом разделе, доступны только для подписчиков Office 365 (план 1) и Плана 2 (Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-253">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="e0d5f-254">В организациях с Защитником Office 365 администраторы могут управлять файлами на карантине в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-254">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="e0d5f-255">Чтобы включить защиту для этих файлов, см. раздел "Включить безопасные вложения для [SharePoint, OneDrive и Microsoft Teams".](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e0d5f-255">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="e0d5f-256">Просмотр файлов на карантине</span><span class="sxs-lookup"><span data-stu-id="e0d5f-256">View quarantined files</span></span>

1. <span data-ttu-id="e0d5f-257">В центре безопасности и соответствия требованиям выберите **управление угрозами** \> **просмотр** \> **карантина**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-257">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e0d5f-258">Измените **представление в карантине** на файлы **значений.**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-258">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="e0d5f-259">Можно отсортировать поле, щелкнув доступный заголок столбца.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-259">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="e0d5f-260">Вы можете отсортировать результаты, нажав на доступный заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-260">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e0d5f-261">Нажмите кнопку **изменить столбцы**, чтобы отобразить не более семи столбцов.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-261">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e0d5f-262">Столбцы по умолчанию помечены звездочкой ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="e0d5f-262">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e0d5f-263">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-263">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-264">**Расположение**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-264">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-265">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-265">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-266">**URL-адрес файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-266">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-267">**Размер файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-267">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-268">**Истекает**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-268">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-269">**Выпущено?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0d5f-269">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="e0d5f-270">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-270">**Detected by**</span></span>
   - <span data-ttu-id="e0d5f-271">**Изменено по времени**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-271">**Modified by time**</span></span>

4. <span data-ttu-id="e0d5f-272">Чтобы отфильтровать результаты, нажмите **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-272">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e0d5f-273">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-273">The available filters are:</span></span>

   - <span data-ttu-id="e0d5f-274">**Срок действия истекает**: Фильтрация сообщений по истечении срока действия из карантина.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-274">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="e0d5f-275">**Сегодня**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-275">**Today**</span></span>
     - <span data-ttu-id="e0d5f-276">**Следующие 2 дня**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-276">**Next 2 days**</span></span>
     - <span data-ttu-id="e0d5f-277">**Следующие 7 дней**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-277">**Next 7 days**</span></span>
     - <span data-ttu-id="e0d5f-278">Настраиваемый диапазон дат и времени.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-278">A custom date/time range.</span></span>
   - <span data-ttu-id="e0d5f-279">**Получено время**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-279">**Received time**</span></span>
   - <span data-ttu-id="e0d5f-280">**Причина карантина:** единственное доступное значение — **вредоносная программа.**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-280">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="e0d5f-281">**Тип политики**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-281">**Policy type**</span></span>

<span data-ttu-id="e0d5f-282">После того как вы найдете определенный файл на карантине, выберите его, чтобы просмотреть сведения о нем и принять с него меры (например, просмотреть, освободить, скачать или удалить сообщение).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-282">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="e0d5f-283">Просмотр сведений о файле в карантине</span><span class="sxs-lookup"><span data-stu-id="e0d5f-283">View quarantined file details</span></span>

<span data-ttu-id="e0d5f-284">При выборе файла в списке в области "Сведения" отображаются следующие сведения о файле: </span><span class="sxs-lookup"><span data-stu-id="e0d5f-284">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e0d5f-285">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-285">**File Name**</span></span>
- <span data-ttu-id="e0d5f-286">**URL-адрес** файла: URL-адрес, который определяет расположение файла (например, в SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-286">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="e0d5f-287">**Вредоносный контент, обнаруженный в** Дата и время, когда файл был карантин.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-287">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="e0d5f-288">**Истекает** срок действия: дата удаления файла из карантина.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-288">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="e0d5f-289">**Обнаружено :** Защитник Office 365 или антивредоносный механизм Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="e0d5f-290">**Выпущено?**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-290">**Released?**</span></span>
- <span data-ttu-id="e0d5f-291">**Имя вредоносной программы**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-291">**Malware Name**</span></span>
- <span data-ttu-id="e0d5f-292">**Идентификатор документа:** уникальный идентификатор документа.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-292">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="e0d5f-293">**Размер файла:** в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="e0d5f-293">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="e0d5f-294">**Организация** Уникальный ИД организации.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-294">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="e0d5f-295">**Дата последнего изменения**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-295">**Last modified**</span></span>
- <span data-ttu-id="e0d5f-296">**Кем изменен**: пользователь, который последним изменил файл.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-296">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="e0d5f-297">Значение **secure Hash Algorithm 256-bit (SHA-256):** это значение можно использовать для идентификации файла в других хранилищах репутации или в других расположениях в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-297">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="e0d5f-298">Действие с файлами в карантине</span><span class="sxs-lookup"><span data-stu-id="e0d5f-298">Take action on quarantined files</span></span>

<span data-ttu-id="e0d5f-299">При выборе файла в списке можно сделать следующие действия с  файлом во flyout области сведений:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-299">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e0d5f-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="e0d5f-301">**Скачивание файла**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-301">**Download file**</span></span>
- <span data-ttu-id="e0d5f-302">**Удаление файла из карантина**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-302">**Remove file from quarantine**</span></span>

<span data-ttu-id="e0d5f-303">Если вы не освободите или не удалите файлы, они будут удалены по истечении срока хранения карантина по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-303">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="e0d5f-304">Действия с несколькими файлами на карантине</span><span class="sxs-lookup"><span data-stu-id="e0d5f-304">Actions on multiple quarantined files</span></span>

<span data-ttu-id="e0d5f-305">При выборе нескольких файлов на карантине в списке (до  100) появляется flyout pane массовых действий, где можно сделать следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-305">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e0d5f-306">**Выпуск файлов**</span><span class="sxs-lookup"><span data-stu-id="e0d5f-306">**Release files**</span></span>
- <span data-ttu-id="e0d5f-307">**Удаление файлов:** после нажатия кнопки **"Да"** в от имени предупреждения файлы немедленно удаляются.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-307">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="e0d5f-308">Использование Exchange Online PowerShell или автономный EOP PowerShell для просмотра сообщений и файлов на карантине и управления ими</span><span class="sxs-lookup"><span data-stu-id="e0d5f-308">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="e0d5f-309">Для просмотра сообщений и файлов в карантине и управления ими используются:</span><span class="sxs-lookup"><span data-stu-id="e0d5f-309">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="e0d5f-310">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e0d5f-310">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="e0d5f-311">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e0d5f-311">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="e0d5f-312">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e0d5f-312">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="e0d5f-313">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): обратите внимание, что этот командлет только для сообщений, а не для файлов вредоносных программ из безопасных вложений для SharePoint, OneDrive и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0d5f-313">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="e0d5f-314">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e0d5f-314">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
