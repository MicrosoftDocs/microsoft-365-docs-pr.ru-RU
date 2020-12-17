---
title: Ликвидация содержимого
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Отслеживайте и управляйте удалением содержимого, независимо от того, используете ли вы проверку перед ликвидацией или содержимое автоматически удаляется в соответствии с настроенными вами параметрами.
ms.openlocfilehash: 9c2e9055d0468270df4e46fe39115708762052f3
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682672"
---
# <a name="disposition-of-content"></a><span data-ttu-id="f8b14-103">Ликвидация содержимого</span><span class="sxs-lookup"><span data-stu-id="f8b14-103">Disposition of content</span></span>

><span data-ttu-id="f8b14-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="f8b14-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f8b14-105">Используйте вкладку **Ликвидация** из раздела **Управление записями** в Центре соответствие требованиям Microsoft 365, чтобы управлять проверками перед ликвидацией и просматривать [записи](records-management.md#records), которые были автоматически удалены по истечении периода хранения.</span><span class="sxs-lookup"><span data-stu-id="f8b14-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="f8b14-106">Предварительные требования для просмотра ликвидации содержимого</span><span class="sxs-lookup"><span data-stu-id="f8b14-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="f8b14-107">Для управления проверками перед ликвидацией и подтверждения того, что записи были удалены, необходимы соответствующие разрешения, и аудит должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="f8b14-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="f8b14-108">Разрешения на ликвидацию</span><span class="sxs-lookup"><span data-stu-id="f8b14-108">Permissions for disposition</span></span>

<span data-ttu-id="f8b14-109">Чтобы получить доступ к вкладке **Ликвидация** в Центре соответствия требованиям Microsoft 365, пользователи должны иметь роль администратора **Управлением ликвидацией**.</span><span class="sxs-lookup"><span data-stu-id="f8b14-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="f8b14-110">С декабря 2020 года эта роль теперь включена в группу ролей администратора по умолчанию **Управление записями**.</span><span class="sxs-lookup"><span data-stu-id="f8b14-110">From December 2020, this role is now included in the **Records Management** default admin role group.</span></span>

> [!NOTE]
> <span data-ttu-id="f8b14-111">По умолчанию даже глобальному администратору не предоставляется роль **Управление ликвидацией**.</span><span class="sxs-lookup"><span data-stu-id="f8b14-111">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="f8b14-112">Чтобы предоставить пользователям только те разрешения, которые им необходимы для проверок перед ликвидацией, без предоставления им разрешений на просмотр и настройку других возможностей для хранения и управления записями, создайте настраиваемую группу ролей (например, с именем "Рецензенты ликвидации") и предоставьте этой группе роль управления ликвидацией.</span><span class="sxs-lookup"><span data-stu-id="f8b14-112">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>

<span data-ttu-id="f8b14-113">Кроме того, чтобы просматривать содержимое элементов в процессе ликвидации, добавьте пользователей в следующие две группы ролей: **обзор содержимого, просмотр содержимого** и **обзор содержимого, просмотр списков**.</span><span class="sxs-lookup"><span data-stu-id="f8b14-113">Additionally, to view the contents of items during the disposition process, add users to the following two role groups: **Content Explorer Content Viewer** and **Content Explorer List Viewer**.</span></span> <span data-ttu-id="f8b14-114">Даже если пользователи не имеют разрешений для этих групп ролей, они могут выбрать действие проверки перед ликвидацией для выполнения такой проверки, однако им придется это делать без возможности просматривать содержимое элемента в центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f8b14-114">If users don't have the permissions from these role groups, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the compliance center.</span></span>

<span data-ttu-id="f8b14-115">Инструкции по настройке этих разрешений см. в статье [Предоставление пользователям доступа к Центру безопасности и соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f8b14-115">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="f8b14-116">Включить аудит</span><span class="sxs-lookup"><span data-stu-id="f8b14-116">Enable auditing</span></span>

<span data-ttu-id="f8b14-117">Убедитесь, что аудит включен как минимум за день до первого действия по ликвидации.</span><span class="sxs-lookup"><span data-stu-id="f8b14-117">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="f8b14-118">Дополнительные сведения см. в статье [Поиск по журналу аудита в Центре безопасности и соответствия требованиям Office 365&amp;](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="f8b14-118">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="f8b14-119">Проверки перед ликвидацией</span><span class="sxs-lookup"><span data-stu-id="f8b14-119">Disposition reviews</span></span>

<span data-ttu-id="f8b14-120">По окончании периода хранения содержимого в силу ряда причин вам может потребоваться проверить его и решить, можно ли его спокойно удалить («ликвидировать»).</span><span class="sxs-lookup"><span data-stu-id="f8b14-120">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="f8b14-121">Например, вам может потребоваться:</span><span class="sxs-lookup"><span data-stu-id="f8b14-121">For example, you might need to:</span></span>
  
- <span data-ttu-id="f8b14-122">Отложить удаление важного содержимого в случае судебного разбирательства или аудита;</span><span class="sxs-lookup"><span data-stu-id="f8b14-122">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="f8b14-123">Удалить содержимое из списка на ликвидацию, чтобы сохранить его в архиве, если оно представляет исследовательский или исторический интерес;</span><span class="sxs-lookup"><span data-stu-id="f8b14-123">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="f8b14-124">Назначить другой период хранения содержимого, возможно потому, что исходные параметры хранения носили временный или предварительный характер;</span><span class="sxs-lookup"><span data-stu-id="f8b14-124">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="f8b14-125">Вернуть содержимое клиентам или передать другой организации.</span><span class="sxs-lookup"><span data-stu-id="f8b14-125">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="f8b14-126">Когда проверка перед ликвидацией начинается по истечении периода хранения:</span><span class="sxs-lookup"><span data-stu-id="f8b14-126">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="f8b14-127">Выбранные вами люди получают по электронной почте уведомление о том, что есть содержимое для проверки.</span><span class="sxs-lookup"><span data-stu-id="f8b14-127">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="f8b14-128">Эти рецензенты могут быть отдельными пользователями или группами безопасности с поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="f8b14-128">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="f8b14-129">Обратите внимание, что уведомления отправляются еженедельно.</span><span class="sxs-lookup"><span data-stu-id="f8b14-129">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="f8b14-130">Рецензенты переходят на вкладку **Ликвидация** в Центре соответствия требованиям Microsoft 365, чтобы просмотреть содержимое и принять решение о том, следует ли удалить его навсегда, продлить период его хранения или применить другую метку хранения.</span><span class="sxs-lookup"><span data-stu-id="f8b14-130">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="f8b14-131">Проверка перед ликвидацией может включать содержимое почтовых ящиков Exchange, сайтов SharePoint, учетных записей OneDrive и групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8b14-131">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="f8b14-132">Содержимое, ожидающее проверки перед ликвидацией на этих ресурсах, удаляется только после того, как проверяющий выберет окончательное удаление содержимого.</span><span class="sxs-lookup"><span data-stu-id="f8b14-132">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="f8b14-133">В почтовом ящике должно быть не менее 10 МБ данных для обеспечения поддержки проверок перед ликвидации.</span><span class="sxs-lookup"><span data-stu-id="f8b14-133">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="f8b14-134">Обзор всех незавершенных ликвидаций можно просмотреть на вкладке **Обзор**. Например:</span><span class="sxs-lookup"><span data-stu-id="f8b14-134">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Незавершенные ликвидации в разделе "»Обзор управления записями»](../media/dispositions-overview.png)

<span data-ttu-id="f8b14-136">При выборе **Просмотр всех незавершенных ликвидаций**, вы перейдете на страницу **Ликвидация**.</span><span class="sxs-lookup"><span data-stu-id="f8b14-136">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="f8b14-137">Пример.</span><span class="sxs-lookup"><span data-stu-id="f8b14-137">For example:</span></span>

![Страница «Ликвидация» в Центре соответствия требованиям Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="f8b14-139">Рабочий процесс проверки перед ликвидацией</span><span class="sxs-lookup"><span data-stu-id="f8b14-139">Workflow for a disposition review</span></span>

<span data-ttu-id="f8b14-140">На следующей схеме показан основной рабочий процесс проверки перед ликвидацией, когда метка хранения публикуется, а затем вручную применяется пользователем.</span><span class="sxs-lookup"><span data-stu-id="f8b14-140">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="f8b14-141">В качестве альтернативы метка хранения, настроенная для проверки перед ликвидацией, может быть автоматически применена к содержимому.</span><span class="sxs-lookup"><span data-stu-id="f8b14-141">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Схема, показывающая принцип действия ликвидации](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="f8b14-143">Запуск проверки перед ликвидацией в конце периода хранения — это вариант конфигурации, доступный только с меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="f8b14-143">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="f8b14-144">Этот параметр недоступен для политики хранения. </span><span class="sxs-lookup"><span data-stu-id="f8b14-144">This option is not available for a retention policy.</span></span> <span data-ttu-id="f8b14-145">Дополнительные сведения об этих двух решениях см. в разделе [Сведения о политиках и метках хранения](retention.md).</span><span class="sxs-lookup"><span data-stu-id="f8b14-145">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="f8b14-146">На странице **Определение параметров хранения** для метки хранения:</span><span class="sxs-lookup"><span data-stu-id="f8b14-146">From the **Define retention settings** page for a retention label:</span></span>

![Параметры хранения для метки](../media/disposition-review-option.png)
 
<span data-ttu-id="f8b14-148">После выбора параметра **Запустить проверку перед ликвидацией**, на следующей странице мастера необходимо указать рецензентов ликвидации:</span><span class="sxs-lookup"><span data-stu-id="f8b14-148">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![Указание рецензентов ликвидации](../media/disposition-reviewers.png)

<span data-ttu-id="f8b14-150">Для рецензентов укажите пользователя или группу безопасности с поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="f8b14-150">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="f8b14-151">Группы Microsoft 365 ([ранее — группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) не поддерживаются для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="f8b14-151">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="f8b14-152">Просмотр и ликвидация содержимого</span><span class="sxs-lookup"><span data-stu-id="f8b14-152">Viewing and disposing of content</span></span>

<span data-ttu-id="f8b14-153">Когда рецензент получает по электронной почте уведомление о том, что содержимое готово к проверке, он переходит на вкладку **Ликвидация** из раздела **Управление записями** в Центре безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8b14-153">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f8b14-154">Рецензенты могут увидеть, сколько элементов для каждой метки хранения ожидают ликвидации, а затем выбрать метку хранения, чтобы увидеть все содержимое с этой меткой.</span><span class="sxs-lookup"><span data-stu-id="f8b14-154">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="f8b14-155">После выбора метки хранения на вкладке **Ожидание ликвидации** отображаются все незавершенные ликвидации для этой метки. Выберите один или несколько элементов, в которых можно выбрать действие и ввести примечание об обосновании:</span><span class="sxs-lookup"><span data-stu-id="f8b14-155">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Параметры ликвидации](../media/retention-disposition-options.png)

<span data-ttu-id="f8b14-157">Как видно на рисунке, поддерживаются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f8b14-157">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="f8b14-158">Окончательно удаление элемента</span><span class="sxs-lookup"><span data-stu-id="f8b14-158">Permanently delete the item</span></span>
- <span data-ttu-id="f8b14-159">Продление периода хранения</span><span class="sxs-lookup"><span data-stu-id="f8b14-159">Extend the retention period</span></span>
- <span data-ttu-id="f8b14-160">Применение другой метки хранения</span><span class="sxs-lookup"><span data-stu-id="f8b14-160">Apply a different retention label</span></span>

<span data-ttu-id="f8b14-161">При наличии разрешения на расположение и содержимое, можно использовать ссылку в столбце **Расположение** для просмотра документов в их исходном расположении.</span><span class="sxs-lookup"><span data-stu-id="f8b14-161">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="f8b14-162">При проверке перед ликвидацией содержимое никогда не перемещается из исходного расположения и не удаляется, пока проверяющий не выберет его удаление.</span><span class="sxs-lookup"><span data-stu-id="f8b14-162">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="f8b14-163">Уведомления отправляются проверяющим по электронной почте еженедельно.</span><span class="sxs-lookup"><span data-stu-id="f8b14-163">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="f8b14-164">Этот запланированный процесс означает, что после истечения срока хранения может пройти еще семь дней, прежде чем проверяющие получат уведомление о содержимом, ожидающем ликвидации.</span><span class="sxs-lookup"><span data-stu-id="f8b14-164">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="f8b14-165">Все действия по ликвидации могут быть проверены, а введенный рецензентом текст об обосновании сохраняется и отображается в столбце **Примечание** на странице **Ликвидированные элементы**.</span><span class="sxs-lookup"><span data-stu-id="f8b14-165">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="f8b14-166">Через какое время ликвидированное содержимое удаляется окончательно?</span><span class="sxs-lookup"><span data-stu-id="f8b14-166">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="f8b14-167">Содержимое, ожидающее проверки перед ликвидацией, удаляется только после того, как проверяющий выберет его окончательное удаление.</span><span class="sxs-lookup"><span data-stu-id="f8b14-167">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="f8b14-168">После выбора проверяющим этого действия к содержимому на сайте SharePoint или в учетной записи OneDrive применяется стандартный процесс очистки, описанный в разделе [Как параметры хранения применяются к имеющемуся содержимому](retention.md#how-retention-settings-work-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="f8b14-168">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="f8b14-169">Ликвидация записей</span><span class="sxs-lookup"><span data-stu-id="f8b14-169">Disposition of records</span></span>

<span data-ttu-id="f8b14-170">Используйте вкладку **Ликвидация** на странице **Управление записями**, чтобы определить, какие записи будут удалены автоматически или после проверки перед ликвидацией.</span><span class="sxs-lookup"><span data-stu-id="f8b14-170">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="f8b14-171">Эти элементы отображают **Ликвидированные записи** в столбце **Тип**.</span><span class="sxs-lookup"><span data-stu-id="f8b14-171">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="f8b14-172">Пример.</span><span class="sxs-lookup"><span data-stu-id="f8b14-172">For example:</span></span>

![Элементы, которые были удалены без проверки перед ликвидацией](../media/records-disposed2.png)

<span data-ttu-id="f8b14-174">Элементы, отображаемые на вкладке **Ликвидированные элементы** для меток хранения, хранятся в течение семи лет после ликвидации элемента с ограничением в один миллион элементов на запись для этого периода.</span><span class="sxs-lookup"><span data-stu-id="f8b14-174">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="f8b14-175">Если вы видите, что **Число**, приближающееся к этому пределу в один миллион, и вам требуется подтверждение ликвидации для ваших записей, обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="f8b14-175">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="f8b14-176">Эта функция основана на информации из [Единого журнала аудита](search-the-audit-log-in-security-and-compliance.md) и, поэтому требует, чтобы аудит был [включен и доступен для поиска](turn-audit-log-search-on-or-off.md), чтобы соответствующие события были записаны.</span><span class="sxs-lookup"><span data-stu-id="f8b14-176">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="f8b14-177">Для проведения аудита выполните поиск **удаленных файлов, помеченных как запись** в категории **действий с файлами и страницами**.</span><span class="sxs-lookup"><span data-stu-id="f8b14-177">For auditing, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="f8b14-178">Это событие аудита относится к документам и сообщениям электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f8b14-178">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="f8b14-179">Фильтрация и экспорт представлений</span><span class="sxs-lookup"><span data-stu-id="f8b14-179">Filter and export the views</span></span>

<span data-ttu-id="f8b14-180">При выборе метки хранения на странице **Ликвидация**, вкладка **Ожидание ликвидации** (если применимо) и вкладка **Ликвидированные элементы** позволяют отфильтровать представления, чтобы облегчить поиск элементов.</span><span class="sxs-lookup"><span data-stu-id="f8b14-180">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="f8b14-181">Для ожидающих проверки элементов за основу интервала времени берется дата окончания периода хранения.</span><span class="sxs-lookup"><span data-stu-id="f8b14-181">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="f8b14-182">Для ликвидированных элементов временной диапазон основан на дате удаления.</span><span class="sxs-lookup"><span data-stu-id="f8b14-182">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="f8b14-183">Информацию об элементах в любом из представлений можно экспортировать в виде файла .csv, который затем можно сортировать и управлять с помощью Excel.</span><span class="sxs-lookup"><span data-stu-id="f8b14-183">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Параметр экспорта для ликвидации](../media/retention-export-option.png)

