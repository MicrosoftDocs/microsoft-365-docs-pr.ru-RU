---
title: Настройка базового аудита в Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: В этой статье описывается, как настроить базовый аудит, чтобы можно было придумать аудиторские действия, выполняемые пользователями и администраторами в вашей организации.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564833"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a><span data-ttu-id="405c8-103">Настройка базового аудита в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="405c8-103">Set up Basic Audit in Microsoft 365</span></span>

<span data-ttu-id="405c8-104">Basic Audit in Microsoft 365 позволяет искать аудиторские записи для действий, выполняемых в различных Microsoft 365 сервисов пользователями и администраторами.</span><span class="sxs-lookup"><span data-stu-id="405c8-104">Basic Audit in Microsoft 365 lets you search for audit records for activities performed in the different Microsoft 365 services by users and admins.</span></span> <span data-ttu-id="405c8-105">Поскольку базовый аудит включен по умолчанию для большинства организаций Microsoft 365 и Office 365, есть только несколько вещей, которые необходимо сделать, прежде чем вы и другие организации с можете искать в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="405c8-105">Because Basic Audit is enabled by default for most Microsoft 365 and Office 365 organizations, there's only a few things you need to do before you and others in your organization can search the audit log.</span></span>

<span data-ttu-id="405c8-106">В этой статье рассматриваются следующие шаги, необходимые для настройки базового аудита.</span><span class="sxs-lookup"><span data-stu-id="405c8-106">This article discusses the following steps necessary to set up Basic Audit.</span></span>

![Шаги по настройке базового аудита](../media/BasicAuditingWorkflow.png)

<span data-ttu-id="405c8-108">Эти меры включают обеспечение надлежащих организационных подписок и лицензирования пользователей, необходимых для создания и сохранения аудиторских записей, а также назначение разрешений членам группы ваших операций по обеспечению безопасности, ИТ, комплаенсу и юридическим группам, с тем чтобы можно было искать в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="405c8-108">These steps include ensuring the proper organizational subscriptions and user licensing required to generate and preserve audit records and assigning permissions to team members of your security operations, IT, compliance, and legal teams so that can search the audit log.</span></span>

<span data-ttu-id="405c8-109">Для получения дополнительной информации с [Microsoft 365 м.](auditing-solutions-overview.md#basic-audit)</span><span class="sxs-lookup"><span data-stu-id="405c8-109">For more information, see [Basic Audit in Microsoft 365](auditing-solutions-overview.md#basic-audit).</span></span>

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a><span data-ttu-id="405c8-110">Шаг 1: Проверка подписки организации и лицензирования пользователей</span><span class="sxs-lookup"><span data-stu-id="405c8-110">Step 1: Verify organization subscription and user licensing</span></span>

<span data-ttu-id="405c8-111">Лицензирование для базового аудита требует соответствующей подписки организации, которая обеспечивает доступ к инструменту поиска журналов аудита и лицензированию на одного пользователя, который необходим для регистрации и сохранения аудиторских записей.</span><span class="sxs-lookup"><span data-stu-id="405c8-111">Licensing for Basic Audit requires the appropriate organization subscription that provides access to audit log search tool and per-user licensing that's required to log and retain audit records.</span></span>

<span data-ttu-id="405c8-112">Когда проверяемое действие выполняется пользователем или администратором, запись аудита создается и сохраняется в журнале аудита для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="405c8-112">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="405c8-113">В базовом аудите аудиторские записи сохраняются и ищутся в журнале аудита в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="405c8-113">In Basic Audit, audit records are retained and searchable in the audit log for 90 days.</span></span>

<span data-ttu-id="405c8-114">Список требований к подписке и лицензированию для basic Audit можно [найти в журнале Auditing solutions Microsoft 365.](auditing-solutions-overview.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="405c8-114">For a list of subscription and licensing requirements for Basic Audit, see [Auditing solutions in Microsoft 365](auditing-solutions-overview.md#licensing-requirements).</span></span>

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a><span data-ttu-id="405c8-115">Шаг 2: Назначить разрешения на поиск в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="405c8-115">Step 2: Assign permissions to search the audit log</span></span>

<span data-ttu-id="405c8-116">Администраторам и членам следственных групп должна быть назначена View-Only журналов аудита или журналов аудита Exchange Online поиска в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="405c8-116">Admins and members of investigation teams must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="405c8-117">Эти роли по умолчанию назначены группам ролей "Управление соответствием" и "Управление организацией" на странице **Разрешения** в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="405c8-117">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="405c8-118">Глобальные администраторы в Office 365 и Microsoft 365 автоматически добавляются в качестве членов ролевой группы управления Организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="405c8-118">Global administrators in Office 365 and Microsoft 365 are automatically added as members of the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="405c8-119">Чтобы предоставить пользователю возможность поиска в журнале аудита с минимальным уровнем привилегий, вы можете создать пользовательскую группу ролей в Exchange Online, добавить роль «Журналы аудита только для просмотра» или «Журналы аудита», а затем добавить пользователя в качестве члена группы. новая ролевая группа.</span><span class="sxs-lookup"><span data-stu-id="405c8-119">To give a user the ability to search the audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="405c8-120">Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="405c8-120">For more information, see [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>

<span data-ttu-id="405c8-121">На следующем скриншоте показаны две функции, связанные с аудитом, возложенные на группу по управлению организацией в Exchange административного центра.</span><span class="sxs-lookup"><span data-stu-id="405c8-121">The following screenshot shows the two audit-related roles assigned to the Organization Management role group in the Exchange admin center.</span></span>

![Роли аудита, назначенные ролевой группе в Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a><span data-ttu-id="405c8-123">Шаг 3: Поиск в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="405c8-123">Step 3: Search the audit log</span></span>

<span data-ttu-id="405c8-124">Теперь вы готовы искать журнал аудита в центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="405c8-124">Now you're ready to search the audit log in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="405c8-125">Перейдите и <https://compliance.microsoft.com> войдите в систему с помощью учетной записи, на которую были назначены соответствующие разрешения аудита.</span><span class="sxs-lookup"><span data-stu-id="405c8-125">Go to <https://compliance.microsoft.com> and sign in using an account that has been assigned the appropriate audit permissions.</span></span>

2. <span data-ttu-id="405c8-126">В левом навигационном стекле центра соответствия Microsoft 365, нажмите Показать **все, а** затем нажмите **Аудит**.</span><span class="sxs-lookup"><span data-stu-id="405c8-126">In the left navigation pane of the Microsoft 365 compliance center, click **Show all** and then click **Audit**.</span></span>

3. <span data-ttu-id="405c8-127">На странице **Аудита** настройте поиск, используя следующие условия во **вкладке Поиск.**</span><span class="sxs-lookup"><span data-stu-id="405c8-127">On the **Audit** page, configure the search using the following conditions on the **Search** tab.</span></span> 

   ![Настройки конфигурации для поиска в журнале аудита](../media/AuditLogSearchToolMCCCallouts.png)

   1. <span data-ttu-id="405c8-129">**Дата и диапазон времени**.</span><span class="sxs-lookup"><span data-stu-id="405c8-129">**Date and time range**.</span></span> <span data-ttu-id="405c8-130">Выберите диапазон дат и времени, чтобы просмотреть события, которые произошли за этот период.</span><span class="sxs-lookup"><span data-stu-id="405c8-130">Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="405c8-131">Дата и время представлены по местному времени.</span><span class="sxs-lookup"><span data-stu-id="405c8-131">The date and time are presented in local time.</span></span> <span data-ttu-id="405c8-132">Последние семь дней выбираются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="405c8-132">The last seven days are selected by default.</span></span>
  
   2. <span data-ttu-id="405c8-133">**Мероприятия**.</span><span class="sxs-lookup"><span data-stu-id="405c8-133">**Activities**.</span></span> <span data-ttu-id="405c8-134">Выберите действия для поиска.</span><span class="sxs-lookup"><span data-stu-id="405c8-134">Select the activities to search for.</span></span> <span data-ttu-id="405c8-135">Используйте поле поиска для поиска действий, чтобы добавить в список.</span><span class="sxs-lookup"><span data-stu-id="405c8-135">Use the search box to search for activities to add to the list.</span></span> <span data-ttu-id="405c8-136">Для частичного перечня проверенных видов деятельности [см.](search-the-audit-log-in-security-and-compliance.md#audited-activities)</span><span class="sxs-lookup"><span data-stu-id="405c8-136">For a partial list of audited activities, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="405c8-137">Оставьте это поле пустым, чтобы вернуть записи для всех проверенных действий.</span><span class="sxs-lookup"><span data-stu-id="405c8-137">Leave this box blank to return entries for all audited activities.</span></span>
  
   3. <span data-ttu-id="405c8-138">**Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="405c8-138">**Users**.</span></span>  <span data-ttu-id="405c8-139">Нажмите в этом поле и начните вводить имя пользователей для отображения результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="405c8-139">Click in this box and start typing the name of users to display search results for.</span></span> <span data-ttu-id="405c8-140">Записи журнала аудита для выбранных действий, выполняемых пользователями, выбранными в этом поле, отображаются в списке результатов.</span><span class="sxs-lookup"><span data-stu-id="405c8-140">The audit log entries for the selected activities performed by the users you select in this box are displayed in the list of results.</span></span> <span data-ttu-id="405c8-141">Чтобы получить результаты для всех пользователей (и учетных записей служб) в организации, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="405c8-141">Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
  
   4. <span data-ttu-id="405c8-142">**Файл, папка или сайт**.</span><span class="sxs-lookup"><span data-stu-id="405c8-142">**File, folder, or site**.</span></span> <span data-ttu-id="405c8-143">Ввемите некоторые или все имена файлов или папок для поиска действий, связанных с файлом папки, которая содержит указанное ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="405c8-143">Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword.</span></span> <span data-ttu-id="405c8-144">Также можно указать URL-адрес файла или папки.</span><span class="sxs-lookup"><span data-stu-id="405c8-144">You can also specify a URL of a file or folder.</span></span> <span data-ttu-id="405c8-145">Если вы используете URL-адрес файла или папки, убедитесь, что тип полного пути URL или если вы вводите часть URL, не включают в себя какие-либо специальные символы или пробелы.</span><span class="sxs-lookup"><span data-stu-id="405c8-145">If you use a URL of a file or folder, be sure the type the full URL path or if you type a portion of the URL, don't include any special characters or spaces.</span></span> <span data-ttu-id="405c8-146">Чтобы получить результаты для всех файлов и папок в организации, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="405c8-146">Leave this box blank to return entries for all files and folders in your organization.</span></span>

4. <span data-ttu-id="405c8-147">Нажмите **Поиск** для запуска поиска.</span><span class="sxs-lookup"><span data-stu-id="405c8-147">Click **Search** to run the search.</span></span>

<span data-ttu-id="405c8-148">Отображается новая страница, на которую отображается поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="405c8-148">A new page is display that shows the audit log search is running.</span></span> <span data-ttu-id="405c8-149">После завершения поиска записи аудита отображаются на странице.</span><span class="sxs-lookup"><span data-stu-id="405c8-149">When the search is completed, audit records are displayed on the page.</span></span> <span data-ttu-id="405c8-150">Нажмите на запись, чтобы отобразить страницу вылета с подробными свойствами.</span><span class="sxs-lookup"><span data-stu-id="405c8-150">Click a record to display a flyout page with detailed properties.</span></span>

<span data-ttu-id="405c8-151">Более подробные инструкции можно [найти в журнале аудита в центре соответствия](search-the-audit-log-in-security-and-compliance.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="405c8-151">For more detailed instructions, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md).</span></span>
