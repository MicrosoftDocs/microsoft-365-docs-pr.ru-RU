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
description: В этой статье описывается настройка базового аудита, чтобы можно было приступить к поиску действий аудита, выполняемой пользователями и администраторами в вашей организации.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564833"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a><span data-ttu-id="3fc91-103">Настройка базового аудита в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3fc91-103">Set up Basic Audit in Microsoft 365</span></span>

<span data-ttu-id="3fc91-104">Базовый аудит Microsoft 365 позволяет искать записи аудита для действий, выполняемых в различных службах Microsoft 365 пользователями и администраторами.</span><span class="sxs-lookup"><span data-stu-id="3fc91-104">Basic Audit in Microsoft 365 lets you search for audit records for activities performed in the different Microsoft 365 services by users and admins.</span></span> <span data-ttu-id="3fc91-105">Так как базовый аудит включен по умолчанию для большинства Microsoft 365 и Office 365 организаций, для поиска журнала аудита необходимо сделать только несколько вещей.</span><span class="sxs-lookup"><span data-stu-id="3fc91-105">Because Basic Audit is enabled by default for most Microsoft 365 and Office 365 organizations, there's only a few things you need to do before you and others in your organization can search the audit log.</span></span>

<span data-ttu-id="3fc91-106">В этой статье обсуждаются следующие действия, необходимые для настройка базового аудита.</span><span class="sxs-lookup"><span data-stu-id="3fc91-106">This article discusses the following steps necessary to set up Basic Audit.</span></span>

![Действия по настройкам базового аудита](../media/BasicAuditingWorkflow.png)

<span data-ttu-id="3fc91-108">Эти действия включают обеспечение надлежащих организационных подписок и лицензирования пользователей, необходимых для создания и сохранения записей аудита, а также назначения разрешений членам группы операций безопасности, ИТ,соответствия требованиям и юридических групп, чтобы можно было искать журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="3fc91-108">These steps include ensuring the proper organizational subscriptions and user licensing required to generate and preserve audit records and assigning permissions to team members of your security operations, IT, compliance, and legal teams so that can search the audit log.</span></span>

<span data-ttu-id="3fc91-109">Дополнительные сведения см. в [элементарной проверке в Microsoft 365.](auditing-solutions-overview.md#basic-audit)</span><span class="sxs-lookup"><span data-stu-id="3fc91-109">For more information, see [Basic Audit in Microsoft 365](auditing-solutions-overview.md#basic-audit).</span></span>

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a><span data-ttu-id="3fc91-110">Шаг 1. Проверка подписки на организацию и лицензирования пользователей</span><span class="sxs-lookup"><span data-stu-id="3fc91-110">Step 1: Verify organization subscription and user licensing</span></span>

<span data-ttu-id="3fc91-111">Для лицензирования базового аудита требуется соответствующая подписка организации, которая предоставляет доступ к средству поиска журналов аудита и лицензированию для каждого пользователя, необходимому для входа и сохранения записей аудита.</span><span class="sxs-lookup"><span data-stu-id="3fc91-111">Licensing for Basic Audit requires the appropriate organization subscription that provides access to audit log search tool and per-user licensing that's required to log and retain audit records.</span></span>

<span data-ttu-id="3fc91-112">Когда проверяемое действие выполняется пользователем или администратором, запись аудита создается и сохраняется в журнале аудита для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3fc91-112">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="3fc91-113">В basic Audit записи аудита сохраняются и в журнале аудита можно искать в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="3fc91-113">In Basic Audit, audit records are retained and searchable in the audit log for 90 days.</span></span>

<span data-ttu-id="3fc91-114">Список требований к подписке и лицензированию для базового аудита см. в [Microsoft 365.](auditing-solutions-overview.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="3fc91-114">For a list of subscription and licensing requirements for Basic Audit, see [Auditing solutions in Microsoft 365](auditing-solutions-overview.md#licensing-requirements).</span></span>

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a><span data-ttu-id="3fc91-115">Шаг 2. Назначение разрешений для поиска журнала аудита</span><span class="sxs-lookup"><span data-stu-id="3fc91-115">Step 2: Assign permissions to search the audit log</span></span>

<span data-ttu-id="3fc91-116">Администраторам и членам групп расследований необходимо View-Only журналы аудита или журналы аудита в Exchange Online для поиска журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="3fc91-116">Admins and members of investigation teams must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="3fc91-117">Эти роли по умолчанию назначены группам ролей "Управление соответствием" и "Управление организацией" на странице **Разрешения** в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="3fc91-117">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="3fc91-118">Глобальные администраторы в Office 365 и Microsoft 365 автоматически добавляются в качестве членов группы ролей управления организацией в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fc91-118">Global administrators in Office 365 and Microsoft 365 are automatically added as members of the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3fc91-119">Чтобы предоставить пользователю возможность поиска в журнале аудита с минимальным уровнем привилегий, вы можете создать пользовательскую группу ролей в Exchange Online, добавить роль «Журналы аудита только для просмотра» или «Журналы аудита», а затем добавить пользователя в качестве члена группы. новая ролевая группа.</span><span class="sxs-lookup"><span data-stu-id="3fc91-119">To give a user the ability to search the audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="3fc91-120">Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="3fc91-120">For more information, see [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>

<span data-ttu-id="3fc91-121">На следующем скриншоте показаны две роли, связанные с аудитом, которые назначены группе ролей управления организацией в центре администрирования Exchange организации.</span><span class="sxs-lookup"><span data-stu-id="3fc91-121">The following screenshot shows the two audit-related roles assigned to the Organization Management role group in the Exchange admin center.</span></span>

![Роли аудита, назначенные группе ролей в Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a><span data-ttu-id="3fc91-123">Шаг 3. Поиск журнала аудита</span><span class="sxs-lookup"><span data-stu-id="3fc91-123">Step 3: Search the audit log</span></span>

<span data-ttu-id="3fc91-124">Теперь вы готовы к поиску журнала аудита в центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3fc91-124">Now you're ready to search the audit log in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="3fc91-125">Перейдите и войдите в учетную запись, которая была <https://compliance.microsoft.com> назначена соответствующие разрешения аудита.</span><span class="sxs-lookup"><span data-stu-id="3fc91-125">Go to <https://compliance.microsoft.com> and sign in using an account that has been assigned the appropriate audit permissions.</span></span>

2. <span data-ttu-id="3fc91-126">В левой области навигации центра Microsoft 365 нажмите кнопку **Показать** все и нажмите **кнопку Аудит**.</span><span class="sxs-lookup"><span data-stu-id="3fc91-126">In the left navigation pane of the Microsoft 365 compliance center, click **Show all** and then click **Audit**.</span></span>

3. <span data-ttu-id="3fc91-127">На странице **Аудит** настройте поиск с помощью следующих условий на вкладке **Поиск.**</span><span class="sxs-lookup"><span data-stu-id="3fc91-127">On the **Audit** page, configure the search using the following conditions on the **Search** tab.</span></span> 

   ![Параметры конфигурации для поиска журнала аудита](../media/AuditLogSearchToolMCCCallouts.png)

   1. <span data-ttu-id="3fc91-129">**Диапазон дат и времени.**</span><span class="sxs-lookup"><span data-stu-id="3fc91-129">**Date and time range**.</span></span> <span data-ttu-id="3fc91-130">Выберите диапазон дат и времени, чтобы просмотреть события, которые произошли за этот период.</span><span class="sxs-lookup"><span data-stu-id="3fc91-130">Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="3fc91-131">Дата и время представлены по местному времени.</span><span class="sxs-lookup"><span data-stu-id="3fc91-131">The date and time are presented in local time.</span></span> <span data-ttu-id="3fc91-132">Последние семь дней выбираются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3fc91-132">The last seven days are selected by default.</span></span>
  
   2. <span data-ttu-id="3fc91-133">**Действия**.</span><span class="sxs-lookup"><span data-stu-id="3fc91-133">**Activities**.</span></span> <span data-ttu-id="3fc91-134">Выберите действия для поиска.</span><span class="sxs-lookup"><span data-stu-id="3fc91-134">Select the activities to search for.</span></span> <span data-ttu-id="3fc91-135">Используйте поле поиска для поиска действий для добавления в список.</span><span class="sxs-lookup"><span data-stu-id="3fc91-135">Use the search box to search for activities to add to the list.</span></span> <span data-ttu-id="3fc91-136">Неполный список проверенных действий см. в [перечне проверенных действий.](search-the-audit-log-in-security-and-compliance.md#audited-activities)</span><span class="sxs-lookup"><span data-stu-id="3fc91-136">For a partial list of audited activities, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="3fc91-137">Оставьте это поле пустым, чтобы вернуть записи для всех проверенных действий.</span><span class="sxs-lookup"><span data-stu-id="3fc91-137">Leave this box blank to return entries for all audited activities.</span></span>
  
   3. <span data-ttu-id="3fc91-138">**Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3fc91-138">**Users**.</span></span>  <span data-ttu-id="3fc91-139">Щелкните в этом поле и начните вводить имя пользователей, чтобы отобразить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="3fc91-139">Click in this box and start typing the name of users to display search results for.</span></span> <span data-ttu-id="3fc91-140">Записи журнала аудита для выбранных действий, выполняемые выбранными пользователями в этом поле, отображаются в списке результатов.</span><span class="sxs-lookup"><span data-stu-id="3fc91-140">The audit log entries for the selected activities performed by the users you select in this box are displayed in the list of results.</span></span> <span data-ttu-id="3fc91-141">Чтобы получить результаты для всех пользователей (и учетных записей служб) в организации, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="3fc91-141">Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
  
   4. <span data-ttu-id="3fc91-142">**Файл, папка или сайт.**</span><span class="sxs-lookup"><span data-stu-id="3fc91-142">**File, folder, or site**.</span></span> <span data-ttu-id="3fc91-143">Введите некоторое или все имя файла или папки для поиска действий, связанных с файлом папки, содержащем указанное ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="3fc91-143">Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword.</span></span> <span data-ttu-id="3fc91-144">Также можно указать URL-адрес файла или папки.</span><span class="sxs-lookup"><span data-stu-id="3fc91-144">You can also specify a URL of a file or folder.</span></span> <span data-ttu-id="3fc91-145">Если используется URL-адрес файла или папки, убедитесь, что введите полный URL-адрес или введите часть URL-адреса, не включайте специальные символы или пробелы.</span><span class="sxs-lookup"><span data-stu-id="3fc91-145">If you use a URL of a file or folder, be sure the type the full URL path or if you type a portion of the URL, don't include any special characters or spaces.</span></span> <span data-ttu-id="3fc91-146">Чтобы получить результаты для всех файлов и папок в организации, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="3fc91-146">Leave this box blank to return entries for all files and folders in your organization.</span></span>

4. <span data-ttu-id="3fc91-147">Нажмите **кнопку Поиск** для запуска поиска.</span><span class="sxs-lookup"><span data-stu-id="3fc91-147">Click **Search** to run the search.</span></span>

<span data-ttu-id="3fc91-148">На новой странице отображается запущен поиск журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="3fc91-148">A new page is display that shows the audit log search is running.</span></span> <span data-ttu-id="3fc91-149">После завершения поиска на странице отображаются записи аудита.</span><span class="sxs-lookup"><span data-stu-id="3fc91-149">When the search is completed, audit records are displayed on the page.</span></span> <span data-ttu-id="3fc91-150">Щелкните запись, чтобы отобразить страницу с подробными свойствами.</span><span class="sxs-lookup"><span data-stu-id="3fc91-150">Click a record to display a flyout page with detailed properties.</span></span>

<span data-ttu-id="3fc91-151">Дополнительные инструкции см. в [журнале поиска аудита в центре соответствия](search-the-audit-log-in-security-and-compliance.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="3fc91-151">For more detailed instructions, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md).</span></span>
