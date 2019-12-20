---
title: Обзор проверок ликвидации
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
description: При создании метки хранения, в которой хранится содержимое в Microsoft 365, вы можете активировать проверку ликвидации в конце периода хранения.
ms.openlocfilehash: 55a6f52a92c23d8c7fc2464c846faf730617ef2f
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806072"
---
# <a name="overview-of-disposition-reviews"></a><span data-ttu-id="6e8e7-103">Обзор проверок ликвидации</span><span class="sxs-lookup"><span data-stu-id="6e8e7-103">Overview of disposition reviews</span></span>

<span data-ttu-id="6e8e7-104">Когда содержимое достигает окончания срока хранения, существует несколько причин, по которым может потребоваться проверить, можно ли его удалить ("удалено").</span><span class="sxs-lookup"><span data-stu-id="6e8e7-104">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="6e8e7-105">Например, может потребоваться выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6e8e7-105">For example, you might need to:</span></span>
  
- <span data-ttu-id="6e8e7-106">Приостановка удаления ("расположения") релевантного контента в случае судебного разбирательства или аудита.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-106">Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="6e8e7-107">Удаление контента из списка расстановки для хранения в архиве, если это содержимое содержит исследование или историческое значение.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-107">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="6e8e7-108">Назначьте другой срок хранения содержимому, если исходная политика была временным или предустановленным решением.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-108">Assign a different retention period to the content, if the original policy was a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="6e8e7-109">Возврат контента клиентам или их передача в другую организацию.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-109">Return the content to clients or transfer it to another organization.</span></span>
    
<span data-ttu-id="6e8e7-110">Когда вы создаете метку хранения в центре соответствия требованиям Microsoft 365, центре безопасности 365 Майкрософт или Office 365 & центр соответствия требованиям, вы можете выбрать активацию расстановки в конце периода хранения.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-110">When you create a retention label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center, you can choose to trigger a disposition review at the end of the retention period.</span></span> <span data-ttu-id="6e8e7-111">При проверке ликвидации:</span><span class="sxs-lookup"><span data-stu-id="6e8e7-111">In a disposition review:</span></span>
  
- <span data-ttu-id="6e8e7-112">Выбранные пользователи получат уведомление по электронной почте о том, что у них есть контент для просмотра.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-112">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="6e8e7-113">Этими рецензентами могут быть отдельные пользователи, группы рассылки или группы безопасности или группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-113">These reviewers can be individual users, distribution or security groups, or Office 365 groups.</span></span> <span data-ttu-id="6e8e7-114">Обратите внимание, что уведомления отправляются еженедельно.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-114">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="6e8e7-115">Рецензенты отправляются на страницу **размещения** в центре соответствия &amp; требованиям безопасности для просмотра контента.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-115">The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content.</span></span> <span data-ttu-id="6e8e7-116">Проверяющие могут видеть, сколько элементов для каждой метки хранения ожидают расстановки, а затем выберите метку хранения, чтобы просмотреть все содержимое с этой меткой.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-116">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>
    
- <span data-ttu-id="6e8e7-117">Для каждого документа или электронной почты проверяющий может выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6e8e7-117">For each document or email, the reviewer can:</span></span>
    
  - <span data-ttu-id="6e8e7-118">Примените другую метку хранения.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-118">Apply a different retention label.</span></span>
    
  - <span data-ttu-id="6e8e7-119">Расширьте срок хранения.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-119">Extend its retention period.</span></span>
    
  - <span data-ttu-id="6e8e7-120">Окончательно удалить.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-120">Permanently delete it.</span></span>
    
- <span data-ttu-id="6e8e7-121">Проверяющие могут просматривать как ожидающие, так и завершенные расположения, а также экспортировать этот список в виде CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-121">Reviewers can view either pending or completed dispositions, and export that list as a .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="6e8e7-122">Для рецензирования расстановки требуется подписка на Office 365 корпоративный для Office.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-122">Disposition reviews require an Office 365 Enterprise E5 subscription.</span></span>
  
<span data-ttu-id="6e8e7-123">Обзор ликвидации может включать контент в почтовые ящики Exchange, сайты SharePoint, учетные записи OneDrive и группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-123">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups.</span></span> <span data-ttu-id="6e8e7-124">Содержимое, ожидающее проверки ликвидации в этих расположениях, удаляется только после того, как рецензент выберет окончательное удаление контента.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-124">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>
  
![Страница "расположения" в центре безопасности и соответствия требованиям](media/Retention-Dispositions-v2-page.png)

## <a name="setting-up-the-disposition-review-by-creating-a-retention-label"></a><span data-ttu-id="6e8e7-126">Настройка проверки ликвидации путем создания метки хранения</span><span class="sxs-lookup"><span data-stu-id="6e8e7-126">Setting up the disposition review by creating a retention label</span></span>

<span data-ttu-id="6e8e7-127">Это базовый рабочий процесс для настройки проверки ликвидации.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-127">This is the basic workflow for setting up a disposition review.</span></span> <span data-ttu-id="6e8e7-128">Обратите внимание, что в этом примере показана публикация метки хранения и ее применение вручную пользователем; Кроме того, метка хранения, инициирующая проверку ликвидации, может быть автоматически применена к содержимому.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-128">Note that this flow shows a retention label being published and then manually applied by a user; alternatively, a retention label that triggers a disposition review can be auto-applied to content.</span></span>
  
![Диаграмма, на которой показано, как работает процесс ликвидации](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="6e8e7-130">Проверка ликвидации является возможностью при создании метки хранения в Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-130">A disposition review is an option when you create a retention label in Office 365.</span></span> <span data-ttu-id="6e8e7-131">Обратите внимание, что этот параметр недоступен в политике хранения, но только в метке хранения, настроенной на хранение контента.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-131">Note that this option is not available in a retention policy but only in a retention label that's configured to retain content.</span></span>
  
<span data-ttu-id="6e8e7-132">Дополнительные сведения о метках хранения приведены в разделе [Обзор меток хранения](labels.md).</span><span class="sxs-lookup"><span data-stu-id="6e8e7-132">For more information about retention labels, see [Overview of retention labels](labels.md).</span></span>
  
![Параметры хранения для метки](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a><span data-ttu-id="6e8e7-134">Удаление контента</span><span class="sxs-lookup"><span data-stu-id="6e8e7-134">Disposing content</span></span>

<span data-ttu-id="6e8e7-135">Когда проверяющий получает уведомление по электронной почте о том, что контент готов к просмотру, он может перейти на страницу **размещения** в центре безопасности &amp; и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-135">When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="6e8e7-136">Проверяющие могут видеть, сколько элементов для каждой метки хранения ожидают расстановки, а затем выберите метку хранения, чтобы просмотреть все содержимое с этой меткой.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-136">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="6e8e7-137">После выбора метки хранения на следующей странице отображаются все ожидающие утверждения для этой метки.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-137">After you select a retention label, the next page shows all pending dispositions for that label.</span></span>

![Параметры расстановки](media/Retention-Disposition-options-v2.png)

<span data-ttu-id="6e8e7-139">Затем проверяющий может:</span><span class="sxs-lookup"><span data-stu-id="6e8e7-139">The reviewer can then:</span></span> 
  
- <span data-ttu-id="6e8e7-140">Примените другую метку хранения.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-140">Apply a different retention label.</span></span>
    
- <span data-ttu-id="6e8e7-141">Продлить срок хранения.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-141">Extend the retention period.</span></span>
    
- <span data-ttu-id="6e8e7-142">Окончательное удаление элемента.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-142">Permanently delete the item.</span></span>

<span data-ttu-id="6e8e7-143">Обратите внимание, что проверяющий может выбрать несколько элементов и удалить их одновременно.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-143">Note that a reviewer can select multiple items and dispose them at the same time.</span></span>
    
<span data-ttu-id="6e8e7-144">Проверяющий также может использовать ссылку для просмотра документа в его исходном расположении, если у проверяющего есть разрешения для этого расположения.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-144">A reviewer can also use the link to view the document in its original location, if the reviewer has permissions for that location.</span></span> <span data-ttu-id="6e8e7-145">Во время проверки ликвидации содержимое никогда не перемещается из исходного расположения и никогда не удаляется до тех пор, пока проверяющий не решит это.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-145">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="6e8e7-146">Обратите внимание, что уведомления по электронной почте автоматически отправляются проверяющим.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-146">Note that the email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="6e8e7-147">Таким образом, когда содержимое достигает окончания срока хранения, рецензентам может потребоваться до семи дней для получения уведомления по электронной почте о том, что содержимое ожидает расстановки.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-147">Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="6e8e7-148">Кроме того, обратите внимание на то, что все действия по размещению подлежат аудиту.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-148">Also note that all disposition actions are audited.</span></span> <span data-ttu-id="6e8e7-149">Для этого необходимо включить аудит по крайней мере один день перед первым действием обработки — дополнительные сведения можно найти в статье [Поиск в журнале аудита в центре безопасности &amp; и соответствия требованиям Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="6e8e7-149">To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 
  
## <a name="permissions-for-disposition"></a><span data-ttu-id="6e8e7-150">Разрешения для ликвидации</span><span class="sxs-lookup"><span data-stu-id="6e8e7-150">Permissions for disposition</span></span>

<span data-ttu-id="6e8e7-151">Чтобы получить доступ к странице **расстановки** , рецензенты должны быть членами роли **управления расстановкой** и **аудитом только для просмотра** .</span><span class="sxs-lookup"><span data-stu-id="6e8e7-151">To get access to the **Disposition** page, reviewers must be members of the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="6e8e7-152">Мы рекомендуем создать новую группу ролей с именем проверяющих, добавив эти две роли в эту группу ролей, а затем добавляя участников в группу ролей.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-152">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="6e8e7-153">Дополнительные сведения см в статье [предоставление пользователям доступа к центру безопасности &amp; и соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="6e8e7-153">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)</span></span>
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="6e8e7-154">Время до окончательного удаления ликвидации контента</span><span class="sxs-lookup"><span data-stu-id="6e8e7-154">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="6e8e7-155">Контент, ожидающий проверки ликвидации, удаляется только после того, как рецензент выберет окончательное удаление контента.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-155">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="6e8e7-156">Когда проверяющий выбирает этот параметр, контент на сайте SharePoint или в учетной записи OneDrive становится доступным для стандартного процесса очистки, описанного в этом разделе: [как политика хранения работает с контентом на месте](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="6e8e7-156">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="6e8e7-157">Это означает, что:</span><span class="sxs-lookup"><span data-stu-id="6e8e7-157">This means that:</span></span>
  
- <span data-ttu-id="6e8e7-158">Содержимое библиотеки документов будет перемещено в корзину первого уровня **в течение 7 дней** после завершения, а затем окончательно удалено через **93 дней** после этого.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-158">Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that.</span></span> <span data-ttu-id="6e8e7-159">Корзина не индексируется службой поиска, поэтому ее содержимое недоступно для удержания обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-159">The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold.</span></span>

- <span data-ttu-id="6e8e7-160">Контент из библиотеки хранения хранения будет окончательно удален **в течение 7 дней с момента** расстановки.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-160">Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition.</span></span>

- <span data-ttu-id="6e8e7-161">Элементы в почтовом ящике Exchange будут окончательно удалены **в течение 14 дней** до расстановки.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-161">Items in an Exchange mailbox will be permanently deleted **within 14 days** of disposition.</span></span> <span data-ttu-id="6e8e7-162">(Обратите внимание, что по умолчанию задано значение 14 дней, но его можно настроить до 30 дней.)</span><span class="sxs-lookup"><span data-stu-id="6e8e7-162">(Note that 14 days is the default setting but it can be configured up to 30 days.)</span></span>
    
## <a name="view-pending-dispositions-and-disposed-items"></a><span data-ttu-id="6e8e7-163">Просмотр ожидающих расстановки и откладываемых элементов</span><span class="sxs-lookup"><span data-stu-id="6e8e7-163">View pending dispositions and disposed items</span></span>

<span data-ttu-id="6e8e7-164">На странице **ожидания размещения** можно просматривать как ожидающие, так и завершенные расположения для определенной метки хранения:</span><span class="sxs-lookup"><span data-stu-id="6e8e7-164">On the **Pending disposition** page, you can view both pending and completed dispositions for a specific retention label:</span></span> 
  
- <span data-ttu-id="6e8e7-165">В **ожидающем** процессе обработки отображаются элементы, достигнутые в конце срока хранения и требующие проверки ликвидации.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-165">The **Pending disposition** shows items that have reached the end of their retention period and require a disposition review.</span></span> <span data-ttu-id="6e8e7-166">После проверки каждого элемента решите, следует ли применить к нему другую метку хранения, продлить срок хранения или окончательно удалить его.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-166">After reviewing each item, decide if you want to apply a different retention label to it, extend its retention period, or permanently delete it.</span></span> <span data-ttu-id="6e8e7-167">Можно выбрать несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-167">You can select multiple items.</span></span>
    
- <span data-ttu-id="6e8e7-168">На вкладке **списанные элементы** отображаются расстановки, которые были утверждены для удаления во время проверки ликвидации и теперь находятся в процессе окончательного удаления или элементов, помеченных как записи, которые теперь были удалены.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-168">The **Disposed items** tab shows dispositions were approved for deletion during a disposition review and are now in the process of being permanently deleted or items marked as records that have now been deleted.</span></span> <span data-ttu-id="6e8e7-169">Элементы, к которым применена другая метка хранения, или срок хранения, продленный в рамках проверки, не отображаются здесь.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-169">Items that had a different retention label applied or their retention period extended as part of a review won't appear here.</span></span>

![Вкладки расстановки](media/Retention-Disposition-tabs.png)
    
### <a name="filter-the-disposition-views"></a><span data-ttu-id="6e8e7-171">Фильтрация представлений расстановки</span><span class="sxs-lookup"><span data-stu-id="6e8e7-171">Filter the disposition views</span></span>

<span data-ttu-id="6e8e7-172">Вы можете отфильтровать эти представления по метке хранения или диапазону времени.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-172">You can filter these views by retention label or time range.</span></span> <span data-ttu-id="6e8e7-173">Для ожидающих расстановки диапазон времени зависит от даты истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-173">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="6e8e7-174">Для списанных элементов диапазон времени зависит от даты удаления.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-174">For disposed items, the time range is based on the deletion date.</span></span>
  
![Параметры фильтра расстановки](media/Retention-filter-options.png)

### <a name="export-the-disposition-items"></a><span data-ttu-id="6e8e7-176">Экспорт элементов ликвидации</span><span class="sxs-lookup"><span data-stu-id="6e8e7-176">Export the disposition items</span></span>

<span data-ttu-id="6e8e7-177">Кроме того, вы можете экспортировать элементы из любого представления в виде CSV-файла, который можно открыть в Excel.</span><span class="sxs-lookup"><span data-stu-id="6e8e7-177">In addition, you can export the items in either view as a .csv file that you can open in Excel.</span></span>
  
![Экспортированные данные о расположении в Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

