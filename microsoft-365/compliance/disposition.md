---
title: Расстановка контента
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Мониторинг и управление выбытием содержимого независимо от того, используется ли обзор ликвидации или содержимое автоматически удаляется в соответствии с настроенными параметрами.
ms.openlocfilehash: cb48d2eb6d2d06093ddea74f13269faeb4798b97
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2020
ms.locfileid: "43950103"
---
# <a name="disposition-of-content"></a><span data-ttu-id="978e9-103">Расстановка контента</span><span class="sxs-lookup"><span data-stu-id="978e9-103">Disposition of content</span></span>

><span data-ttu-id="978e9-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="978e9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="978e9-105">Используйте вкладку " **положение** " из списка " **Управление записями** " в центре соответствия требованиям Microsoft 365 для управления проверками расстановки и просмотра [записей](records.md) , которые были автоматически удалены в конце срока хранения.</span><span class="sxs-lookup"><span data-stu-id="978e9-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="978e9-106">Необходимые условия для просмотра расстановки содержимого</span><span class="sxs-lookup"><span data-stu-id="978e9-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="978e9-107">Для управления обзорами ликвидации и подтверждения того, что записи удалены, необходимо иметь достаточные разрешения, и аудит должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="978e9-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="978e9-108">Разрешения для ликвидации</span><span class="sxs-lookup"><span data-stu-id="978e9-108">Permissions for disposition</span></span>

<span data-ttu-id="978e9-109">Для успешного доступа к вкладке " **положение** " в центре соответствия требованиям Microsoft 365 необходимо быть участником роли **управления ликвидацией** и ролью " **журналы аудита только для просмотра** ".</span><span class="sxs-lookup"><span data-stu-id="978e9-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, you must be members of the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="978e9-110">Мы рекомендуем создать новую группу ролей с именем **проверяющих**и добавить эти две роли в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="978e9-110">We recommend creating a new role group called **Disposition Reviewers**, and add these two roles to that role group.</span></span> 

<span data-ttu-id="978e9-111">Относится только к роли **журналов аудита только для просмотра** :</span><span class="sxs-lookup"><span data-stu-id="978e9-111">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="978e9-112">Так как базовый командлет, используемый для поиска в журнале аудита, является командлетом Exchange Online, ему необходимо назначить эту роль с помощью [центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), а не с помощью страницы **разрешений** в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="978e9-112">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="978e9-113">Инструкции см в разделе [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="978e9-113">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="978e9-114">Группы Microsoft 365 ([ранее группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) не поддерживаются для этой роли.</span><span class="sxs-lookup"><span data-stu-id="978e9-114">Microsoft 365 Groups ([formerly Office 365 Groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="978e9-115">Вместо этого назначьте почтовые ящики пользователей, почтовые пользователи или группы безопасности с включенной поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="978e9-115">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="978e9-116">Инструкции по предоставлению пользователям роли **управления ликвидацией** и созданию новой роли **проверяющих проверяющих** можно узнать в статье [предоставление пользователям доступа к центру безопасности &amp; и соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="978e9-116">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="978e9-117">Включение аудита</span><span class="sxs-lookup"><span data-stu-id="978e9-117">Enable auditing</span></span>

<span data-ttu-id="978e9-118">Убедитесь, что аудит включен по крайней мере один день перед первым действием ликвидации.</span><span class="sxs-lookup"><span data-stu-id="978e9-118">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="978e9-119">Дополнительные сведения можно найти в статье [Поиск в журнале аудита в центре безопасности &amp; и соответствия требованиям Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="978e9-119">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="978e9-120">Проверки перед ликвидацией</span><span class="sxs-lookup"><span data-stu-id="978e9-120">Disposition reviews</span></span>

<span data-ttu-id="978e9-121">Когда содержимое достигает окончания срока хранения, существует несколько причин, по которым может потребоваться проверить, можно ли его удалить ("удалено").</span><span class="sxs-lookup"><span data-stu-id="978e9-121">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="978e9-122">Например, может потребоваться выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="978e9-122">For example, you might need to:</span></span>
  
- <span data-ttu-id="978e9-123">Приостановить удаление релевантного контента в случае судебного разбирательства или аудита.</span><span class="sxs-lookup"><span data-stu-id="978e9-123">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="978e9-124">Удаление контента из списка расстановки для хранения в архиве, если это содержимое содержит исследование или историческое значение.</span><span class="sxs-lookup"><span data-stu-id="978e9-124">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="978e9-125">Назначьте другой срок хранения содержимому, возможно, из-за того, что первоначальные параметры хранения были временными или предварительными решениями.</span><span class="sxs-lookup"><span data-stu-id="978e9-125">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="978e9-126">Возврат контента клиентам или их передача в другую организацию.</span><span class="sxs-lookup"><span data-stu-id="978e9-126">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="978e9-127">Когда проверка ликвидации инициируется в конце периода хранения:</span><span class="sxs-lookup"><span data-stu-id="978e9-127">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="978e9-128">Выбранные пользователи получат уведомление по электронной почте о том, что у них есть контент для просмотра.</span><span class="sxs-lookup"><span data-stu-id="978e9-128">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="978e9-129">Этими рецензентами могут быть отдельные пользователи, группы рассылки или группы безопасности или группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="978e9-129">These reviewers can be individual users, distribution or security groups, or Office 365 groups.</span></span> <span data-ttu-id="978e9-130">Обратите внимание, что уведомления отправляются еженедельно.</span><span class="sxs-lookup"><span data-stu-id="978e9-130">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="978e9-131">Рецензенты отправляются на вкладку " **положение** " в центре соответствия требованиям Microsoft 365, чтобы проверить содержимое и решить, следует ли окончательно удалить его, продлить срок хранения или применить другую метку хранения.</span><span class="sxs-lookup"><span data-stu-id="978e9-131">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="978e9-132">Обзор ликвидации может включать контент в почтовые ящики Exchange, сайты SharePoint, учетные записи OneDrive и группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="978e9-132">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="978e9-133">Содержимое, ожидающее проверки ликвидации в этих расположениях, удаляется только после того, как рецензент выберет окончательное удаление контента.</span><span class="sxs-lookup"><span data-stu-id="978e9-133">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

<span data-ttu-id="978e9-134">Обзор всех ожидающих расстановки можно просмотреть на вкладке **Обзор** . Например:</span><span class="sxs-lookup"><span data-stu-id="978e9-134">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Общие сведения о ожидающих отположениях в управлении записями](../media/dispositions-overview.png)

<span data-ttu-id="978e9-136">Когда вы выбираете **Просмотр всех ожидающих расстановки**, вы перейдете на страницу " **положение** ".</span><span class="sxs-lookup"><span data-stu-id="978e9-136">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="978e9-137">Пример.</span><span class="sxs-lookup"><span data-stu-id="978e9-137">For example:</span></span>

![Страница "расположения" в центре соответствия требованиям Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="978e9-139">Рабочий процесс для проверки ликвидации</span><span class="sxs-lookup"><span data-stu-id="978e9-139">Workflow for a disposition review</span></span>

<span data-ttu-id="978e9-140">Это базовый рабочий процесс для проверки ликвидации, когда подпись хранения публикуется и затем вручную применяется пользователем.</span><span class="sxs-lookup"><span data-stu-id="978e9-140">This is the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="978e9-141">Кроме того, метка хранения, настроенная для проверки ликвидации, может быть автоматически применена к содержимому.</span><span class="sxs-lookup"><span data-stu-id="978e9-141">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Диаграмма, на которой показано, как работает процесс ликвидации](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="978e9-143">Включение проверки ликвидации в конце периода хранения — это параметр конфигурации, доступный только с [меткой хранения](labels.md).</span><span class="sxs-lookup"><span data-stu-id="978e9-143">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a [retention label](labels.md).</span></span> <span data-ttu-id="978e9-144">Этот параметр недоступен в политике хранения.</span><span class="sxs-lookup"><span data-stu-id="978e9-144">This option is not available in a retention policy.</span></span>
  
![Параметры хранения для метки](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="978e9-146">При выборе параметра **уведомлять этих пользователей о наличии элементов, готовых к просмотру**, укажите пользователя или группу безопасности с включенной поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="978e9-146">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="978e9-147">Группы Microsoft 365 ([ранее группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) не поддерживаются этим параметром.</span><span class="sxs-lookup"><span data-stu-id="978e9-147">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="978e9-148">Просмотр и удаление контента</span><span class="sxs-lookup"><span data-stu-id="978e9-148">Viewing and disposing of content</span></span>

<span data-ttu-id="978e9-149">Когда проверяющий получает уведомление по электронной почте о том, что контент готов к просмотру, он переходит на вкладку " **положение** " в разделе **Управление записями** в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="978e9-149">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="978e9-150">Проверяющие могут видеть, сколько элементов для каждой метки хранения ожидают расстановки, а затем выберите метку хранения, чтобы просмотреть все содержимое с этой меткой.</span><span class="sxs-lookup"><span data-stu-id="978e9-150">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="978e9-151">После выбора метки хранения вы увидите все ожидающие утверждения для этой метки на вкладке **Отложенное расположение** . Выберите один или несколько элементов, в которых можно выбрать действие и ввести комментарий по обоснования:</span><span class="sxs-lookup"><span data-stu-id="978e9-151">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Параметры расстановки](../media/retention-disposition-options.png)

<span data-ttu-id="978e9-153">Как видно на рисунке, поддерживаемые действия:</span><span class="sxs-lookup"><span data-stu-id="978e9-153">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="978e9-154">Окончательное удаление элемента</span><span class="sxs-lookup"><span data-stu-id="978e9-154">Permanently delete the item</span></span>
- <span data-ttu-id="978e9-155">Продление срока хранения</span><span class="sxs-lookup"><span data-stu-id="978e9-155">Extend the retention period</span></span>
- <span data-ttu-id="978e9-156">Применение другой метки хранения</span><span class="sxs-lookup"><span data-stu-id="978e9-156">Apply a different retention label</span></span>

<span data-ttu-id="978e9-157">Если у вас есть разрешения на доступ к расположению и содержимому, вы можете использовать ссылку в столбце " **Расположение** ", чтобы просматривать документы в их исходном расположении.</span><span class="sxs-lookup"><span data-stu-id="978e9-157">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="978e9-158">Во время проверки ликвидации содержимое никогда не перемещается из исходного расположения и никогда не удаляется до тех пор, пока проверяющий не решит это.</span><span class="sxs-lookup"><span data-stu-id="978e9-158">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="978e9-159">Уведомления по электронной почте автоматически отправляются рецензентам по неделям.</span><span class="sxs-lookup"><span data-stu-id="978e9-159">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="978e9-160">Этот запланированный процесс означает, что когда содержимое достигает окончания срока хранения, рецензентам может потребоваться до семи дней, чтобы рецензенты получали уведомление о том, что содержимое ожидает расстановки.</span><span class="sxs-lookup"><span data-stu-id="978e9-160">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="978e9-161">Все действия ликвидации можно подвергать аудиту.</span><span class="sxs-lookup"><span data-stu-id="978e9-161">All disposition actions can be audited.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="978e9-162">Время до окончательного удаления ликвидации контента</span><span class="sxs-lookup"><span data-stu-id="978e9-162">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="978e9-163">Контент, ожидающий проверки ликвидации, удаляется только после того, как рецензент выберет окончательное удаление контента.</span><span class="sxs-lookup"><span data-stu-id="978e9-163">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="978e9-164">Когда проверяющий выбирает этот параметр, контент на сайте SharePoint или в учетной записи OneDrive становится доступным для стандартного процесса очистки, описанного в разделе [как политика хранения работает с контентом на месте](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="978e9-164">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="978e9-165">Расстановка записей</span><span class="sxs-lookup"><span data-stu-id="978e9-165">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="978e9-166">Возможность просматривать записи, которые были автоматически удалены без проверки ликвидации, постепенно превышена до клиентов в течение апреля и мая 2020, поэтому вы можете не видеть этот интерфейс немедленно.</span><span class="sxs-lookup"><span data-stu-id="978e9-166">The ability to see records that were automatically deleted without a disposition review is gradually rolling out to tenants during April and May 2020, so you might not see this experience immediately.</span></span>

<span data-ttu-id="978e9-167">Используйте вкладку " **расстановка** " на странице " **Управление записями** ", чтобы определить записи, которые автоматически удаляются.</span><span class="sxs-lookup"><span data-stu-id="978e9-167">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="978e9-168">Эти элементы отображают **записи** , которые удалены в столбце **тип** .</span><span class="sxs-lookup"><span data-stu-id="978e9-168">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="978e9-169">При сравнении списанные записи, которые утверждены для удаления с помощью проверки ликвидации, **ожидаются**.</span><span class="sxs-lookup"><span data-stu-id="978e9-169">In comparison, disposed records that are approved to be deleted through a disposition review display **Pending Disposition**.</span></span> <span data-ttu-id="978e9-170">Пример.</span><span class="sxs-lookup"><span data-stu-id="978e9-170">For example:</span></span>

![Элементы, которые были удалены без проверки ликвидации](../media/records-disposed2.png)

<span data-ttu-id="978e9-172">Элементы, отображаемые на вкладке **выгруженных элементов** для меток записи, хранятся в течение 7 лет после удаления элемента с предельным числом 1 000 000 элементов на запись для этого периода.</span><span class="sxs-lookup"><span data-stu-id="978e9-172">Items that are shown in the **Disposed Items** tab for record labels are kept for up to 7 years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="978e9-173">Если вы **видите число, близкое к этому** ограничению 1 000 000, и вам требуется подтверждение расстановки записей, обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="978e9-173">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="978e9-174">Эта функция основана на сведениях из [единого журнала аудита](search-the-audit-log-in-security-and-compliance.md) и, следовательно, требует [включения и поиска](turn-audit-log-search-on-or-off.md) соответствующих событий.</span><span class="sxs-lookup"><span data-stu-id="978e9-174">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="978e9-175">Фильтрация и экспорт представлений</span><span class="sxs-lookup"><span data-stu-id="978e9-175">Filter and export the views</span></span>

<span data-ttu-id="978e9-176">При выборе метки хранения на странице **размещения** , вкладка **ожидающее расположение** (если это возможно) и вкладка **Удаленные элементы** позволяют фильтровать представления для упрощения поиска элементов.</span><span class="sxs-lookup"><span data-stu-id="978e9-176">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="978e9-177">Для ожидающих расстановки диапазон времени зависит от даты истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="978e9-177">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="978e9-178">Для списанных элементов диапазон времени зависит от даты удаления.</span><span class="sxs-lookup"><span data-stu-id="978e9-178">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="978e9-179">Вы можете экспортировать информацию о элементах в любом представлении в виде CSV-файла, который можно сортировать и управлять с помощью Excel:</span><span class="sxs-lookup"><span data-stu-id="978e9-179">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Параметр Export для ликвидации](../media/retention-export-option.png)
  
![Экспортированные данные о расположении в Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


