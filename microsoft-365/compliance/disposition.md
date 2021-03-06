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
ms.openlocfilehash: 092067e676c1cbae3fae6e9d6a5ff77099ce4631
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461884"
---
# <a name="disposition-of-content"></a><span data-ttu-id="5d27c-103">Ликвидация содержимого</span><span class="sxs-lookup"><span data-stu-id="5d27c-103">Disposition of content</span></span>

><span data-ttu-id="5d27c-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="5d27c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="5d27c-105">Используйте вкладку **Ликвидация** из раздела **Управление записями** в Центре соответствие требованиям Microsoft 365, чтобы управлять проверками перед ликвидацией и просматривать [записи](records-management.md#records), которые были автоматически удалены по истечении периода хранения.</span><span class="sxs-lookup"><span data-stu-id="5d27c-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="5d27c-106">Предварительные требования для просмотра ликвидации содержимого</span><span class="sxs-lookup"><span data-stu-id="5d27c-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="5d27c-107">Для управления проверками перед ликвидацией и подтверждения того, что записи были удалены, необходимы соответствующие разрешения, и аудит должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="5d27c-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="5d27c-108">Разрешения на ликвидацию</span><span class="sxs-lookup"><span data-stu-id="5d27c-108">Permissions for disposition</span></span>

<span data-ttu-id="5d27c-109">Чтобы получить доступ к вкладке **Ликвидация** в Центре соответствия требованиям Microsoft 365, пользователи должны иметь роль администратора **Управлением ликвидацией**.</span><span class="sxs-lookup"><span data-stu-id="5d27c-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="5d27c-110">С декабря 2020 года эта роль теперь включена в группу ролей администратора по умолчанию **Управление записями**.</span><span class="sxs-lookup"><span data-stu-id="5d27c-110">From December 2020, this role is now included in the **Records Management** default admin role group.</span></span>

> [!NOTE]
> <span data-ttu-id="5d27c-111">По умолчанию даже глобальному администратору не предоставляется роль **Управление ликвидацией**.</span><span class="sxs-lookup"><span data-stu-id="5d27c-111">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="5d27c-112">Чтобы предоставить пользователям только те разрешения, которые им необходимы для проверок перед ликвидацией, без предоставления им разрешений на просмотр и настройку других возможностей для хранения и управления записями, создайте настраиваемую группу ролей (например, с именем "Рецензенты ликвидации") и предоставьте этой группе роль управления ликвидацией.</span><span class="sxs-lookup"><span data-stu-id="5d27c-112">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>

<span data-ttu-id="5d27c-113">Кроме того, чтобы просматривать содержимое элементов в процессе ликвидации, добавьте пользователей в следующие две группы ролей: **обзор содержимого, просмотр содержимого** и **обзор содержимого, просмотр списков**.</span><span class="sxs-lookup"><span data-stu-id="5d27c-113">Additionally, to view the contents of items during the disposition process, add users to the following two role groups: **Content Explorer Content Viewer** and **Content Explorer List Viewer**.</span></span> <span data-ttu-id="5d27c-114">Даже если пользователи не имеют разрешений для этих групп ролей, они могут выбрать действие проверки перед ликвидацией для выполнения такой проверки, однако им придется это делать без возможности просматривать содержимое элемента в центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5d27c-114">If users don't have the permissions from these role groups, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the compliance center.</span></span>

<span data-ttu-id="5d27c-115">Инструкции по настройке этих разрешений см. в статье [Предоставление пользователям доступа к Центру безопасности и соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5d27c-115">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="5d27c-116">Включить аудит</span><span class="sxs-lookup"><span data-stu-id="5d27c-116">Enable auditing</span></span>

<span data-ttu-id="5d27c-117">Убедитесь, что аудит включен как минимум за день до первого действия по ликвидации.</span><span class="sxs-lookup"><span data-stu-id="5d27c-117">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="5d27c-118">Дополнительные сведения см. в статье [Поиск по журналу аудита в Центре безопасности и соответствия требованиям Office 365&amp;](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="5d27c-118">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="5d27c-119">Проверки перед ликвидацией</span><span class="sxs-lookup"><span data-stu-id="5d27c-119">Disposition reviews</span></span>

<span data-ttu-id="5d27c-120">По окончании периода хранения содержимого в силу ряда причин вам может потребоваться проверить его и подтвердить, можно ли его необратимо удалить ("ликвидировать").</span><span class="sxs-lookup"><span data-stu-id="5d27c-120">When content reaches the end of its retention period, there are several reasons why you might want to review that content and confirm whether it can be permanently deleted ("disposed").</span></span> <span data-ttu-id="5d27c-121">Например, вместо удаления содержимого может потребоваться:</span><span class="sxs-lookup"><span data-stu-id="5d27c-121">For example, instead of deleting the content, you might need to:</span></span>
  
- <span data-ttu-id="5d27c-122">отложить удаление важного содержимого в случае судебного разбирательства или аудита;</span><span class="sxs-lookup"><span data-stu-id="5d27c-122">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>

- <span data-ttu-id="5d27c-123">назначить другой период хранения содержимого, возможно потому, что исходные параметры хранения носили временный или предварительный характер;</span><span class="sxs-lookup"><span data-stu-id="5d27c-123">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>

- <span data-ttu-id="5d27c-124">переместить содержимое из существующего расположения в архив, например, если это содержимое имеет научную или архивную ценность.</span><span class="sxs-lookup"><span data-stu-id="5d27c-124">Move the content from its existing location to an archive location, for example, if that content has research or historical value.</span></span>

<span data-ttu-id="5d27c-125">Когда проверка перед ликвидацией начинается по истечении периода хранения:</span><span class="sxs-lookup"><span data-stu-id="5d27c-125">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="5d27c-126">Выбранные вами люди получают по электронной почте уведомление о том, что есть содержимое для проверки.</span><span class="sxs-lookup"><span data-stu-id="5d27c-126">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="5d27c-127">Эти рецензенты могут быть отдельными пользователями или группами безопасности с поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="5d27c-127">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="5d27c-128">Обратите внимание, что уведомления отправляются еженедельно.</span><span class="sxs-lookup"><span data-stu-id="5d27c-128">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="5d27c-129">Рецензенты переходят на вкладку **Ликвидация** в Центре соответствия требованиям Microsoft 365, чтобы просмотреть содержимое и принять решение о том, следует ли удалить его навсегда, продлить период его хранения или применить другую метку хранения.</span><span class="sxs-lookup"><span data-stu-id="5d27c-129">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="5d27c-130">Проверка перед ликвидацией может включать содержимое почтовых ящиков Exchange, сайтов SharePoint, учетных записей OneDrive и групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5d27c-130">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="5d27c-131">Содержимое, ожидающее проверки перед ликвидацией на этих ресурсах, удаляется только после того, как проверяющий выберет окончательное удаление содержимого.</span><span class="sxs-lookup"><span data-stu-id="5d27c-131">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="5d27c-132">В почтовом ящике должно быть не менее 10 МБ данных для обеспечения поддержки проверок перед ликвидации.</span><span class="sxs-lookup"><span data-stu-id="5d27c-132">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="5d27c-133">Обзор всех незавершенных ликвидаций можно просмотреть на вкладке **Обзор**. Например:</span><span class="sxs-lookup"><span data-stu-id="5d27c-133">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Незавершенные ликвидации в разделе "»Обзор управления записями»](../media/dispositions-overview.png)

<span data-ttu-id="5d27c-135">При выборе **Просмотр всех незавершенных ликвидаций**, вы перейдете на страницу **Ликвидация**.</span><span class="sxs-lookup"><span data-stu-id="5d27c-135">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="5d27c-136">Пример.</span><span class="sxs-lookup"><span data-stu-id="5d27c-136">For example:</span></span>

![Страница «Ликвидация» в Центре соответствия требованиям Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="5d27c-138">Рабочий процесс проверки перед ликвидацией</span><span class="sxs-lookup"><span data-stu-id="5d27c-138">Workflow for a disposition review</span></span>

<span data-ttu-id="5d27c-139">На следующей схеме показан основной рабочий процесс проверки перед ликвидацией, когда метка хранения публикуется, а затем вручную применяется пользователем.</span><span class="sxs-lookup"><span data-stu-id="5d27c-139">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="5d27c-140">В качестве альтернативы метка хранения, настроенная для проверки перед ликвидацией, может быть автоматически применена к содержимому.</span><span class="sxs-lookup"><span data-stu-id="5d27c-140">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Схема, показывающая принцип действия ликвидации](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="5d27c-142">Запуск проверки перед ликвидацией в конце периода хранения — это вариант конфигурации, доступный только с меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="5d27c-142">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="5d27c-143">Этот параметр недоступен для политики хранения. </span><span class="sxs-lookup"><span data-stu-id="5d27c-143">This option is not available for a retention policy.</span></span> <span data-ttu-id="5d27c-144">Дополнительные сведения об этих двух решениях см. в разделе [Сведения о политиках и метках хранения](retention.md).</span><span class="sxs-lookup"><span data-stu-id="5d27c-144">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="5d27c-145">На странице **Определение параметров хранения** для метки хранения:</span><span class="sxs-lookup"><span data-stu-id="5d27c-145">From the **Define retention settings** page for a retention label:</span></span>

![Параметры хранения для метки](../media/disposition-review-option.png)
 
<span data-ttu-id="5d27c-147">После выбора параметра **Запустить проверку перед ликвидацией**, на следующей странице мастера необходимо указать рецензентов ликвидации:</span><span class="sxs-lookup"><span data-stu-id="5d27c-147">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![Указание рецензентов ликвидации](../media/disposition-reviewers.png)

<span data-ttu-id="5d27c-149">Для рецензентов укажите пользователя или группу безопасности с поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="5d27c-149">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="5d27c-150">Группы Microsoft 365 ([ранее — группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) не поддерживаются для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="5d27c-150">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="5d27c-151">Просмотр и ликвидация содержимого</span><span class="sxs-lookup"><span data-stu-id="5d27c-151">Viewing and disposing of content</span></span>

<span data-ttu-id="5d27c-152">Когда рецензент получает по электронной почте уведомление о том, что содержимое готово к проверке, он переходит на вкладку **Ликвидация** из раздела **Управление записями** в Центре безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5d27c-152">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5d27c-153">Рецензенты могут увидеть, сколько элементов для каждой метки хранения ожидают ликвидации, а затем выбрать метку хранения, чтобы увидеть все содержимое с этой меткой.</span><span class="sxs-lookup"><span data-stu-id="5d27c-153">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="5d27c-154">После выбора метки хранения на вкладке **Ожидание ликвидации** отображаются все незавершенные ликвидации для этой метки. Выберите один или несколько элементов, в которых можно выбрать действие и ввести примечание об обосновании:</span><span class="sxs-lookup"><span data-stu-id="5d27c-154">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Параметры ликвидации](../media/retention-disposition-options.png)

<span data-ttu-id="5d27c-156">Как видно на рисунке, поддерживаются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5d27c-156">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="5d27c-157">Окончательно удаление элемента</span><span class="sxs-lookup"><span data-stu-id="5d27c-157">Permanently delete the item</span></span>
- <span data-ttu-id="5d27c-158">Продление периода хранения</span><span class="sxs-lookup"><span data-stu-id="5d27c-158">Extend the retention period</span></span>
- <span data-ttu-id="5d27c-159">Применение другой метки хранения</span><span class="sxs-lookup"><span data-stu-id="5d27c-159">Apply a different retention label</span></span>

<span data-ttu-id="5d27c-160">При наличии разрешения на расположение и содержимое, можно использовать ссылку в столбце **Расположение** для просмотра документов в их исходном расположении.</span><span class="sxs-lookup"><span data-stu-id="5d27c-160">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="5d27c-161">При проверке перед ликвидацией содержимое никогда не перемещается из исходного расположения и не удаляется, пока проверяющий не выберет его удаление.</span><span class="sxs-lookup"><span data-stu-id="5d27c-161">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="5d27c-162">Уведомления отправляются проверяющим по электронной почте еженедельно.</span><span class="sxs-lookup"><span data-stu-id="5d27c-162">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="5d27c-163">Этот запланированный процесс означает, что после истечения срока хранения может пройти еще семь дней, прежде чем проверяющие получат уведомление о содержимом, ожидающем ликвидации.</span><span class="sxs-lookup"><span data-stu-id="5d27c-163">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="5d27c-164">Все действия по ликвидации могут быть проверены, а введенный рецензентом текст об обосновании сохраняется и отображается в столбце **Примечание** на странице **Ликвидированные элементы**.</span><span class="sxs-lookup"><span data-stu-id="5d27c-164">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="5d27c-165">Через какое время ликвидированное содержимое удаляется окончательно?</span><span class="sxs-lookup"><span data-stu-id="5d27c-165">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="5d27c-166">Содержимое, ожидающее проверки перед ликвидацией, удаляется только после того, как проверяющий выберет его окончательное удаление.</span><span class="sxs-lookup"><span data-stu-id="5d27c-166">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="5d27c-167">После выбора проверяющим этого действия к содержимому на сайте SharePoint или в учетной записи OneDrive применяется стандартный процесс очистки, описанный в разделе [Как параметры хранения применяются к имеющемуся содержимому](retention.md#how-retention-settings-work-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="5d27c-167">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="5d27c-168">Ликвидация записей</span><span class="sxs-lookup"><span data-stu-id="5d27c-168">Disposition of records</span></span>

<span data-ttu-id="5d27c-169">Используйте вкладку **Ликвидация** на странице **Управление записями**, чтобы определить, какие записи будут удалены автоматически или после проверки перед ликвидацией.</span><span class="sxs-lookup"><span data-stu-id="5d27c-169">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="5d27c-170">Эти элементы отображают **Ликвидированные записи** в столбце **Тип**.</span><span class="sxs-lookup"><span data-stu-id="5d27c-170">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="5d27c-171">Пример.</span><span class="sxs-lookup"><span data-stu-id="5d27c-171">For example:</span></span>

![Элементы, которые были удалены без проверки перед ликвидацией](../media/records-disposed2.png)

<span data-ttu-id="5d27c-173">Элементы, отображаемые на вкладке **Ликвидированные элементы** для меток хранения, хранятся в течение семи лет после ликвидации элемента с ограничением в один миллион элементов на запись для этого периода.</span><span class="sxs-lookup"><span data-stu-id="5d27c-173">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="5d27c-174">Если вы видите, что **Число**, приближающееся к этому пределу в один миллион, и вам требуется подтверждение ликвидации для ваших записей, обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="5d27c-174">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="5d27c-175">Эта функция основана на информации из [Единого журнала аудита](search-the-audit-log-in-security-and-compliance.md) и, поэтому требует, чтобы аудит был [включен и доступен для поиска](turn-audit-log-search-on-or-off.md), чтобы соответствующие события были записаны.</span><span class="sxs-lookup"><span data-stu-id="5d27c-175">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="5d27c-176">Для проведения аудита выполните поиск **удаленных файлов, помеченных как запись** в категории **действий с файлами и страницами**.</span><span class="sxs-lookup"><span data-stu-id="5d27c-176">For auditing, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="5d27c-177">Это событие аудита относится к документам и сообщениям электронной почты.</span><span class="sxs-lookup"><span data-stu-id="5d27c-177">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="5d27c-178">Фильтрация и экспорт представлений</span><span class="sxs-lookup"><span data-stu-id="5d27c-178">Filter and export the views</span></span>

<span data-ttu-id="5d27c-179">При выборе метки хранения на странице **Ликвидация**, вкладка **Ожидание ликвидации** (если применимо) и вкладка **Ликвидированные элементы** позволяют отфильтровать представления, чтобы облегчить поиск элементов.</span><span class="sxs-lookup"><span data-stu-id="5d27c-179">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="5d27c-180">Для ожидающих проверки элементов за основу интервала времени берется дата окончания периода хранения.</span><span class="sxs-lookup"><span data-stu-id="5d27c-180">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="5d27c-181">Для ликвидированных элементов временной диапазон основан на дате удаления.</span><span class="sxs-lookup"><span data-stu-id="5d27c-181">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="5d27c-182">Информацию об элементах в любом из представлений можно экспортировать в виде файла .csv, который затем можно сортировать и управлять с помощью Excel.</span><span class="sxs-lookup"><span data-stu-id="5d27c-182">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Параметр экспорта для ликвидации](../media/retention-export-option.png)

