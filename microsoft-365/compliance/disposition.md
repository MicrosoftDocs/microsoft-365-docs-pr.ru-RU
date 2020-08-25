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
ms.openlocfilehash: e70160ef309ad421724f9ad40db0d7c6e00df136
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867214"
---
# <a name="disposition-of-content"></a><span data-ttu-id="7920d-103">Расстановка контента</span><span class="sxs-lookup"><span data-stu-id="7920d-103">Disposition of content</span></span>

><span data-ttu-id="7920d-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="7920d-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7920d-105">Используйте вкладку " **положение** " из списка " **Управление записями** " в центре соответствия требованиям Microsoft 365 для управления проверками расстановки и просмотра [записей](records-management.md#records) , которые были автоматически удалены в конце срока хранения.</span><span class="sxs-lookup"><span data-stu-id="7920d-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="7920d-106">Необходимые условия для просмотра расстановки содержимого</span><span class="sxs-lookup"><span data-stu-id="7920d-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="7920d-107">Для управления обзорами ликвидации и подтверждения того, что записи удалены, необходимо иметь достаточные разрешения, и аудит должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="7920d-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="7920d-108">Разрешения для ликвидации</span><span class="sxs-lookup"><span data-stu-id="7920d-108">Permissions for disposition</span></span>

<span data-ttu-id="7920d-109">Для успешного доступа к вкладке " **положение** " в центре соответствия требованиям Microsoft 365 пользователи должны иметь роль администратора **управления расстановкой** .</span><span class="sxs-lookup"><span data-stu-id="7920d-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="7920d-110">Эта роль включена в группы ролей "Администраторы" по умолчанию, **Администратор соответствия требованиям** и **администратор данных соответствия требованиям**.</span><span class="sxs-lookup"><span data-stu-id="7920d-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="7920d-111">Чтобы предоставить пользователям эту роль управления расстановкой, добавьте их в одну из этих групп ролей по умолчанию или создайте настраиваемую группу ролей (например, "расстановка рецензентов") и предоставьте этой группе роль управления ликвидацией.</span><span class="sxs-lookup"><span data-stu-id="7920d-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="7920d-112">Даже глобальному администратору должна быть назначена роль **управления расстановкой** .</span><span class="sxs-lookup"><span data-stu-id="7920d-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="7920d-113">Инструкции см. в статье [Предоставление пользователям доступа к Центру безопасности и соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7920d-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="7920d-114">Включение аудита</span><span class="sxs-lookup"><span data-stu-id="7920d-114">Enable auditing</span></span>

<span data-ttu-id="7920d-115">Убедитесь, что аудит включен по крайней мере один день перед первым действием ликвидации.</span><span class="sxs-lookup"><span data-stu-id="7920d-115">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="7920d-116">Дополнительные сведения можно найти в статье [Поиск в журнале аудита в центре безопасности и &amp; соответствия требованиям Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="7920d-116">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="7920d-117">Проверки перед ликвидацией</span><span class="sxs-lookup"><span data-stu-id="7920d-117">Disposition reviews</span></span>

<span data-ttu-id="7920d-118">Когда содержимое достигает окончания срока хранения, существует несколько причин, по которым может потребоваться проверить, можно ли его удалить ("удалено").</span><span class="sxs-lookup"><span data-stu-id="7920d-118">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="7920d-119">Например, может потребоваться выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7920d-119">For example, you might need to:</span></span>
  
- <span data-ttu-id="7920d-120">Приостановить удаление релевантного контента в случае судебного разбирательства или аудита.</span><span class="sxs-lookup"><span data-stu-id="7920d-120">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="7920d-121">Удаление контента из списка расстановки для хранения в архиве, если это содержимое содержит исследование или историческое значение.</span><span class="sxs-lookup"><span data-stu-id="7920d-121">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="7920d-122">Назначьте другой срок хранения содержимому, возможно, из-за того, что первоначальные параметры хранения были временными или предварительными решениями.</span><span class="sxs-lookup"><span data-stu-id="7920d-122">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="7920d-123">Возврат контента клиентам или их передача в другую организацию.</span><span class="sxs-lookup"><span data-stu-id="7920d-123">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="7920d-124">Когда проверка ликвидации инициируется в конце периода хранения:</span><span class="sxs-lookup"><span data-stu-id="7920d-124">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="7920d-125">Выбранные пользователи получат уведомление по электронной почте о том, что у них есть контент для просмотра.</span><span class="sxs-lookup"><span data-stu-id="7920d-125">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="7920d-126">Такими проверяющими могут быть отдельные пользователи, группы рассылки или группы безопасности или группы безопасности Microsoft 365 ([ранее — группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span><span class="sxs-lookup"><span data-stu-id="7920d-126">These reviewers can be individual users, distribution or security groups, or Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span></span> <span data-ttu-id="7920d-127">Обратите внимание, что уведомления отправляются еженедельно.</span><span class="sxs-lookup"><span data-stu-id="7920d-127">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="7920d-128">Рецензенты отправляются на вкладку " **положение** " в центре соответствия требованиям Microsoft 365, чтобы проверить содержимое и решить, следует ли окончательно удалить его, продлить срок хранения или применить другую метку хранения.</span><span class="sxs-lookup"><span data-stu-id="7920d-128">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="7920d-129">Обзор ликвидации может включать контент в почтовые ящики Exchange, сайты SharePoint, учетные записи OneDrive и группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7920d-129">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="7920d-130">Содержимое, ожидающее проверки ликвидации в этих расположениях, удаляется только после того, как рецензент выберет окончательное удаление контента.</span><span class="sxs-lookup"><span data-stu-id="7920d-130">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="7920d-131">Для поддержки проверок расстановки в почтовом ящике должно быть по крайней мере 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="7920d-131">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="7920d-132">Обзор всех ожидающих расстановки можно просмотреть на вкладке **Обзор** . Например:</span><span class="sxs-lookup"><span data-stu-id="7920d-132">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Общие сведения о ожидающих отположениях в управлении записями](../media/dispositions-overview.png)

<span data-ttu-id="7920d-134">Когда вы выбираете **Просмотр всех ожидающих расстановки**, вы перейдете на страницу " **положение** ".</span><span class="sxs-lookup"><span data-stu-id="7920d-134">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="7920d-135">Например,</span><span class="sxs-lookup"><span data-stu-id="7920d-135">For example:</span></span>

![Страница "расположения" в центре соответствия требованиям Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="7920d-137">Рабочий процесс для проверки ликвидации</span><span class="sxs-lookup"><span data-stu-id="7920d-137">Workflow for a disposition review</span></span>

<span data-ttu-id="7920d-138">На следующей схеме показан базовый рабочий процесс для проверки ликвидации при публикации метки хранения, а затем пользователь вручную применялся.</span><span class="sxs-lookup"><span data-stu-id="7920d-138">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="7920d-139">Кроме того, метка хранения, настроенная для проверки ликвидации, может быть автоматически применена к содержимому.</span><span class="sxs-lookup"><span data-stu-id="7920d-139">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Диаграмма, на которой показано, как работает процесс ликвидации](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="7920d-141">Включение проверки ликвидации в конце периода хранения — это параметр конфигурации, доступный только с меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="7920d-141">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="7920d-142">Этот параметр недоступен для политики хранения.</span><span class="sxs-lookup"><span data-stu-id="7920d-142">This option is not available for a retention policy.</span></span> <span data-ttu-id="7920d-143">Дополнительные сведения об этих двух решениях хранения приведены в [статье сведения о политиках хранения и метках хранения](retention.md).</span><span class="sxs-lookup"><span data-stu-id="7920d-143">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
![Параметры хранения для метки](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="7920d-145">При выборе параметра **уведомлять этих пользователей о наличии элементов, готовых к просмотру**, укажите пользователя или группу безопасности с включенной поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="7920d-145">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="7920d-146">Группы Microsoft 365 ([ранее группы Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) не поддерживаются этим параметром.</span><span class="sxs-lookup"><span data-stu-id="7920d-146">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="7920d-147">Просмотр и удаление контента</span><span class="sxs-lookup"><span data-stu-id="7920d-147">Viewing and disposing of content</span></span>

<span data-ttu-id="7920d-148">Когда проверяющий получает уведомление по электронной почте о том, что контент готов к просмотру, он переходит на вкладку " **положение** " в разделе **Управление записями** в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7920d-148">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7920d-149">Проверяющие могут видеть, сколько элементов для каждой метки хранения ожидают расстановки, а затем выберите метку хранения, чтобы просмотреть все содержимое с этой меткой.</span><span class="sxs-lookup"><span data-stu-id="7920d-149">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="7920d-150">После выбора метки хранения вы увидите все ожидающие утверждения для этой метки на вкладке **Отложенное расположение** . Выберите один или несколько элементов, в которых можно выбрать действие и ввести комментарий по обоснования:</span><span class="sxs-lookup"><span data-stu-id="7920d-150">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Параметры расстановки](../media/retention-disposition-options.png)

<span data-ttu-id="7920d-152">Как видно на рисунке, поддерживаемые действия:</span><span class="sxs-lookup"><span data-stu-id="7920d-152">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="7920d-153">Окончательное удаление элемента</span><span class="sxs-lookup"><span data-stu-id="7920d-153">Permanently delete the item</span></span>
- <span data-ttu-id="7920d-154">Продление срока хранения</span><span class="sxs-lookup"><span data-stu-id="7920d-154">Extend the retention period</span></span>
- <span data-ttu-id="7920d-155">Применение другой метки хранения</span><span class="sxs-lookup"><span data-stu-id="7920d-155">Apply a different retention label</span></span>

<span data-ttu-id="7920d-156">Если у вас есть разрешения на доступ к расположению и содержимому, вы можете использовать ссылку в столбце " **Расположение** ", чтобы просматривать документы в их исходном расположении.</span><span class="sxs-lookup"><span data-stu-id="7920d-156">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="7920d-157">Во время проверки ликвидации содержимое никогда не перемещается из исходного расположения и никогда не удаляется до тех пор, пока проверяющий не решит это.</span><span class="sxs-lookup"><span data-stu-id="7920d-157">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="7920d-158">Уведомления по электронной почте автоматически отправляются рецензентам по неделям.</span><span class="sxs-lookup"><span data-stu-id="7920d-158">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="7920d-159">Этот запланированный процесс означает, что когда содержимое достигает окончания срока хранения, рецензентам может потребоваться до семи дней, чтобы рецензенты получали уведомление о том, что содержимое ожидает расстановки.</span><span class="sxs-lookup"><span data-stu-id="7920d-159">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="7920d-160">Все действия ликвидации можно подвергать аудиту, а текст выравнивания, введенный рецензентом, сохраняется и отображается в столбце **Comments** на странице **ликвидированных элементов** .</span><span class="sxs-lookup"><span data-stu-id="7920d-160">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="7920d-161">Время до окончательного удаления ликвидации контента</span><span class="sxs-lookup"><span data-stu-id="7920d-161">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="7920d-162">Контент, ожидающий проверки ликвидации, удаляется только после того, как рецензент выберет окончательное удаление контента.</span><span class="sxs-lookup"><span data-stu-id="7920d-162">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="7920d-163">Когда проверяющий выбирает этот параметр, контент на сайте SharePoint или в учетной записи OneDrive становится доступным для стандартного процесса очистки, описанного в статье [Параметры хранения для работы с контентом на месте](retention.md#how-retention-settings-work-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="7920d-163">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="7920d-164">Ликвидация записей</span><span class="sxs-lookup"><span data-stu-id="7920d-164">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="7920d-165">Развертывание для подтверждения выбытия записей в SharePoint и OneDrive завершено.</span><span class="sxs-lookup"><span data-stu-id="7920d-165">The rollout for proof of disposal for records in SharePoint and OneDrive is complete.</span></span> <span data-ttu-id="7920d-166">Вы увидите список меток хранения, которые помечены как записи для SharePoint и OneDrive в разделе "расположение" страницы "Управление записями" в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7920d-166">You will see the list of retention labels that marked content as records for SharePoint and OneDrive in the Disposition section of the Records Management page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7920d-167">В разделе эти метки можно просмотреть список элементов в SharePoint и OneDrive, которые были удалены автоматически или после проверки ликвидации.</span><span class="sxs-lookup"><span data-stu-id="7920d-167">Under these labels, you can see the list of items in SharePoint and OneDrive that were disposed automatically or after a disposition review.</span></span>
>
> <span data-ttu-id="7920d-168">Подтверждение выбытия записей в Exchange пока еще не активно.</span><span class="sxs-lookup"><span data-stu-id="7920d-168">Proof of disposal for records in Exchange is not yet active.</span></span> <span data-ttu-id="7920d-169">Когда начинается этот выпуск и когда он будет завершен, мы будем обновлять эту заметку.</span><span class="sxs-lookup"><span data-stu-id="7920d-169">When this rollout begins and when it is complete, we will update this note.</span></span>

<span data-ttu-id="7920d-170">Используйте вкладку " **расстановка** " на странице " **Управление записями** ", чтобы определить записи, которые автоматически удаляются.</span><span class="sxs-lookup"><span data-stu-id="7920d-170">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="7920d-171">Эти элементы отображают **записи** , которые удалены в столбце **тип** .</span><span class="sxs-lookup"><span data-stu-id="7920d-171">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="7920d-172">Например,</span><span class="sxs-lookup"><span data-stu-id="7920d-172">For example:</span></span>

![Элементы, которые были удалены без проверки ликвидации](../media/records-disposed2.png)

<span data-ttu-id="7920d-174">Элементы, отображаемые на вкладке **выгруженных элементов** для меток записи, хранятся в течение семи лет после удаления элемента с предельным числом 1 000 000 элементов в записи для этого периода.</span><span class="sxs-lookup"><span data-stu-id="7920d-174">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="7920d-175">Если вы **видите число, близкое к этому** ограничению 1 000 000, и вам требуется подтверждение расстановки записей, обратитесь в [службу поддержки Майкрософт](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="7920d-175">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="7920d-176">Эта функция основана на сведениях из [единого журнала аудита](search-the-audit-log-in-security-and-compliance.md) и, следовательно, требует [включения и поиска](turn-audit-log-search-on-or-off.md) соответствующих событий.</span><span class="sxs-lookup"><span data-stu-id="7920d-176">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="7920d-177">Фильтрация и экспорт представлений</span><span class="sxs-lookup"><span data-stu-id="7920d-177">Filter and export the views</span></span>

<span data-ttu-id="7920d-178">При выборе метки хранения на странице **размещения** , вкладка **ожидающее расположение** (если это возможно) и вкладка **Удаленные элементы** позволяют фильтровать представления для упрощения поиска элементов.</span><span class="sxs-lookup"><span data-stu-id="7920d-178">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="7920d-179">Для ожидающих расстановки диапазон времени зависит от даты истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="7920d-179">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="7920d-180">Для списанных элементов диапазон времени зависит от даты удаления.</span><span class="sxs-lookup"><span data-stu-id="7920d-180">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="7920d-181">Вы можете экспортировать информацию о элементах в любом представлении в виде CSV-файла, который можно сортировать и управлять с помощью Excel:</span><span class="sxs-lookup"><span data-stu-id="7920d-181">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Параметр Export для ликвидации](../media/retention-export-option.png)
  
![Экспортированные данные о расположении в Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


