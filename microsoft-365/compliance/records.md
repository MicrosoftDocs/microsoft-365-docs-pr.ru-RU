---
title: Узнайте о записях
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Узнайте о записях, которые помогут вам внедрить решение для управления записями в Microsoft 365.
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372524"
---
# <a name="learn-about-records"></a><span data-ttu-id="a6366-103">Узнайте о записях</span><span class="sxs-lookup"><span data-stu-id="a6366-103">Learn about records</span></span>

><span data-ttu-id="a6366-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a6366-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a6366-105">Управление записями в Microsoft 365 помогает организации соблюдать корпоративные политики, правовые и нормативные положения, а также уменьшить риски и правовые последствия.</span><span class="sxs-lookup"><span data-stu-id="a6366-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="a6366-106">Когда содержимое помечается как запись:</span><span class="sxs-lookup"><span data-stu-id="a6366-106">When content is marked as a record:</span></span>

- <span data-ttu-id="a6366-107">На элементы накладываются ограничения в отношении того, какие[действия разрешены или запрещены](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="a6366-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="a6366-108">дополнительные действия, связанные с элементом, фиксируются в журнале;</span><span class="sxs-lookup"><span data-stu-id="a6366-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="a6366-109">Когда элементы удаляются по истечении периода хранения, вы должны подтвердить их ликвидацию.</span><span class="sxs-lookup"><span data-stu-id="a6366-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="a6366-110">Чтобы пометить содержимое как запись, используются [метки хранения](retention.md#retention-labels).</span><span class="sxs-lookup"><span data-stu-id="a6366-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="a6366-111">Вы можете либо опубликовать эти метки, чтобы пользователи и администраторы могли вручную применить их к содержимому, либо автоматически применить эти метки к содержимому, которое вы хотите пометить как запись.</span><span class="sxs-lookup"><span data-stu-id="a6366-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="a6366-112">Используя метки хранения для того, чтобы помечать содержимое как записи, вы можете реализовать единую и последовательную стратегию управления записями в своей среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a6366-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="a6366-113">Сравните ограничения на то, какие действия разрешены или запрещены</span><span class="sxs-lookup"><span data-stu-id="a6366-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="a6366-114">Используйте приведенную ниже таблицу, чтобы определить, какие ограничения накладываются на контент в результате применения стандартной метки хранения, а также меток хранения, помечающих содержимое как запись.</span><span class="sxs-lookup"><span data-stu-id="a6366-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="a6366-115">Конфигурация стандартной метки хранения позволяет сохранять данные, не помечая содержимое как запись.</span><span class="sxs-lookup"><span data-stu-id="a6366-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="a6366-116">Таблица также содержит столбцы для заблокированной и разблокированной записи, которая применима к содержимому в SharePoint и OneDrive, но не в Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6366-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="a6366-117">Для блокировки и разблокировки записи используется [Управление версиями записи](#record-versioning), которое не поддерживается для элементов Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6366-117">The ability to lock and unlock a record uses [record versioning](#record-versioning) that isn't supported for Exchange items.</span></span> <span data-ttu-id="a6366-118">Таким образом, для всех элементов Exchange, которые помечены как записи, действие сопоставляется со столбцом **Запись заблокирована**, а столбец **Запись разблокирована** не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="a6366-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="a6366-119">Действие</span><span class="sxs-lookup"><span data-stu-id="a6366-119">Action</span></span>| <span data-ttu-id="a6366-120">Метка хранения</span><span class="sxs-lookup"><span data-stu-id="a6366-120">Retention label</span></span> |<span data-ttu-id="a6366-121">Запись заблокирована</span><span class="sxs-lookup"><span data-stu-id="a6366-121">Record - locked</span></span>| <span data-ttu-id="a6366-122">Запись разблокирована</span><span class="sxs-lookup"><span data-stu-id="a6366-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a6366-123">Изменение содержаний</span><span class="sxs-lookup"><span data-stu-id="a6366-123">Edit contents</span></span>|<span data-ttu-id="a6366-124">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-124">Allowed</span></span> | <span data-ttu-id="a6366-125">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="a6366-125">**Blocked**</span></span> | <span data-ttu-id="a6366-126">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-126">Allowed</span></span>|
|<span data-ttu-id="a6366-127">Изменение свойств, включая переименование</span><span class="sxs-lookup"><span data-stu-id="a6366-127">Edit properties, including rename</span></span>|<span data-ttu-id="a6366-128">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-128">Allowed</span></span> |<span data-ttu-id="a6366-129">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-129">Allowed</span></span> | <span data-ttu-id="a6366-130">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-130">Allowed</span></span>|
|<span data-ttu-id="a6366-131">Удалить</span><span class="sxs-lookup"><span data-stu-id="a6366-131">Delete</span></span>|<span data-ttu-id="a6366-132">Разрешено <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6366-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="a6366-133">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="a6366-133">**Blocked**</span></span> | <span data-ttu-id="a6366-134">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="a6366-134">**Blocked**</span></span>|
|<span data-ttu-id="a6366-135">Копировать</span><span class="sxs-lookup"><span data-stu-id="a6366-135">Copy</span></span>|<span data-ttu-id="a6366-136">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-136">Allowed</span></span> |<span data-ttu-id="a6366-137">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-137">Allowed</span></span> | <span data-ttu-id="a6366-138">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-138">Allowed</span></span>|
|<span data-ttu-id="a6366-139">Перемещение в контейнере <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a6366-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="a6366-140">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-140">Allowed</span></span> |<span data-ttu-id="a6366-141">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-141">Allowed</span></span> | <span data-ttu-id="a6366-142">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-142">Allowed</span></span>|
|<span data-ttu-id="a6366-143">Перемещение между контейнерами <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a6366-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="a6366-144">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-144">Allowed</span></span> |<span data-ttu-id="a6366-145">Разрешено, если никогда не будет разблокировано</span><span class="sxs-lookup"><span data-stu-id="a6366-145">Allowed if never unlocked</span></span> | <span data-ttu-id="a6366-146">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-146">Allowed</span></span>|
|<span data-ttu-id="a6366-147">Открыть/читать</span><span class="sxs-lookup"><span data-stu-id="a6366-147">Open/Read</span></span>|<span data-ttu-id="a6366-148">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-148">Allowed</span></span> |<span data-ttu-id="a6366-149">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-149">Allowed</span></span> | <span data-ttu-id="a6366-150">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-150">Allowed</span></span>|
|<span data-ttu-id="a6366-151">Изменить метку</span><span class="sxs-lookup"><span data-stu-id="a6366-151">Change label</span></span>|<span data-ttu-id="a6366-152">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-152">Allowed</span></span> |<span data-ttu-id="a6366-153">Разрешено только для администраторов контейнера</span><span class="sxs-lookup"><span data-stu-id="a6366-153">Allowed - container admin only</span></span> | <span data-ttu-id="a6366-154">Разрешено только для администраторов контейнера</span><span class="sxs-lookup"><span data-stu-id="a6366-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="a6366-155">Удалить метку</span><span class="sxs-lookup"><span data-stu-id="a6366-155">Remove label</span></span>|<span data-ttu-id="a6366-156">Разрешено</span><span class="sxs-lookup"><span data-stu-id="a6366-156">Allowed</span></span> |<span data-ttu-id="a6366-157">Разрешено только для администраторов контейнера</span><span class="sxs-lookup"><span data-stu-id="a6366-157">Allowed - container admin only</span></span> | <span data-ttu-id="a6366-158">Разрешено только для администраторов контейнера</span><span class="sxs-lookup"><span data-stu-id="a6366-158">Allowed - container admin only</span></span>|

<span data-ttu-id="a6366-159">Сноски:</span><span class="sxs-lookup"><span data-stu-id="a6366-159">Footnotes:</span></span>

<span data-ttu-id="a6366-160"><sup>1</sup> Поддерживается OneDrive и Exchange путем сохранения копии в защищенном месте, но заблокировано в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a6366-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="a6366-161">Сообщение, которое видит пользователь, когда пытается удалить помеченный документ в SharePoint:</span><span class="sxs-lookup"><span data-stu-id="a6366-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Сообщение о том, что элемент не был удален из SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="a6366-163"><sup>2</sup> Контейнеры включают библиотеки документов SharePoint и почтовые ящики Exhange.</span><span class="sxs-lookup"><span data-stu-id="a6366-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>


## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="a6366-164">Использование меток хранения для объявления элементов записями</span><span class="sxs-lookup"><span data-stu-id="a6366-164">Using retention labels to declare records</span></span>

<span data-ttu-id="a6366-165">Когда вы создаете метку хранения, у вас есть возможность использовать метку хранения, чтобы пометить содержимое как запись.</span><span class="sxs-lookup"><span data-stu-id="a6366-165">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="a6366-166">В Центре соответствия требованиям Microsoft 365 перейти в раздел **Управление записями** \> **План хранения**.</span><span class="sxs-lookup"><span data-stu-id="a6366-166">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="a6366-167">На странице **План хранения** выберите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="a6366-167">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="a6366-168">На странице мастера**Параметры метки** выберите параметр для классификации содержимого как записи.</span><span class="sxs-lookup"><span data-stu-id="a6366-168">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Нажмите "Использовать метку", чтобы обозначить содержимое как "Запись" с помощью флажка.](../media/recordversioning6.png)

3. <span data-ttu-id="a6366-170">При необходимости можно применить метку хранения к документам SharePoint или OneDrive и электронным письмам Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6366-170">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="a6366-171">Для получения инструкций:</span><span class="sxs-lookup"><span data-stu-id="a6366-171">For instructions:</span></span>
    
    - [<span data-ttu-id="a6366-172">Создание меток хранения и их применение в приложениях</span><span class="sxs-lookup"><span data-stu-id="a6366-172">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="a6366-173">Автоматическое применение метки хранения к контенту</span><span class="sxs-lookup"><span data-stu-id="a6366-173">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="a6366-174">Применение сконфигурированной метки хранения к содержимому</span><span class="sxs-lookup"><span data-stu-id="a6366-174">Applying the configured retention label to content</span></span>

<span data-ttu-id="a6366-175">Когда метки хранения, помечающие содержимое как запись, становятся доступны для пользователей для применения их в приложениях:</span><span class="sxs-lookup"><span data-stu-id="a6366-175">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="a6366-176">Любой пользователь в Exchange, имеющий доступ к почтовому ящику с возможностью ввода текста, может применить метку хранения.</span><span class="sxs-lookup"><span data-stu-id="a6366-176">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="a6366-177">Применить метки в SharePoint и OneDrive может любой пользователь, который (на уровне разрешения "Участие") входит в группу "Участники", используемую по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a6366-177">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="a6366-178">Пример документа, помеченного как запись, с помощью метки хранения:</span><span class="sxs-lookup"><span data-stu-id="a6366-178">Example of a document marked as record by using a retention label:</span></span>

![Область сведений о документе, отмеченном как запись](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="a6366-180">Управление версиями</span><span class="sxs-lookup"><span data-stu-id="a6366-180">Record versioning</span></span>

<span data-ttu-id="a6366-181">Возможность пометить документ как запись и ограничить действия, которые можно выполнять с записью, является основной целью любого решения по управлению записями.</span><span class="sxs-lookup"><span data-stu-id="a6366-181">The ability to mark a document as a record and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="a6366-182">Однако для создания последующих версий может также потребоваться совместная работа.</span><span class="sxs-lookup"><span data-stu-id="a6366-182">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="a6366-183">Например, контракт продажи можно пометить как запись, и затем, когда требуется этот контракт обновить и внести новые положение, пометить последнюю версию как новую запись, и при этом сохраняется и предыдущая версия записи.</span><span class="sxs-lookup"><span data-stu-id="a6366-183">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="a6366-184">Для таких случаев в SharePoint и OneDrive поддерживается *управление версиями записей*.</span><span class="sxs-lookup"><span data-stu-id="a6366-184">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="a6366-185">Папки записных книжек OneNote не поддерживают управление версиями записей.</span><span class="sxs-lookup"><span data-stu-id="a6366-185">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="a6366-186">Чтобы использовать управление версиями записей, сначала отметьте документ и пометьте его как запись.</span><span class="sxs-lookup"><span data-stu-id="a6366-186">To use record versioning, first label the document and mark it as a record.</span></span> <span data-ttu-id="a6366-187">В этот момент рядом с меткой хранения отобразится свойство документа под названием *Состояние записи*, а изначальное состояние записи сменится на**Заблокировано**.</span><span class="sxs-lookup"><span data-stu-id="a6366-187">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="a6366-188">Доступны перечисленные ниже действия:</span><span class="sxs-lookup"><span data-stu-id="a6366-188">You can now do the following things:</span></span>

  - <span data-ttu-id="a6366-189">**Периодическое редактирование и сохранение отдельных версий документа как записей с разблокировкой и блокировкой свойства "Состояние записи".**</span><span class="sxs-lookup"><span data-stu-id="a6366-189">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="a6366-190">Только когда свойство**Состояние записи** имеет значение**Заблокировано**, новая версия записи сохраняется.</span><span class="sxs-lookup"><span data-stu-id="a6366-190">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="a6366-191">Это переключение между заблокированными и разблокированными версиями уменьшает риск сохранения ненужных версий и копий документа.</span><span class="sxs-lookup"><span data-stu-id="a6366-191">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="a6366-192">**Автоматическое сохранение записей в репозитории записей на месте, который размещается внутри семейства веб-сайтов.**</span><span class="sxs-lookup"><span data-stu-id="a6366-192">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="a6366-193">Содержимое любого семейства веб-сайтов в SharePoint и OneDrive сохраняется в соответствующей архивной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="a6366-193">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="a6366-194">Место хранения версий записей в этой библиотеке —папка "Записи".</span><span class="sxs-lookup"><span data-stu-id="a6366-194">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="a6366-195">**Сохранение всегда актуального документа, включающего в себя все версии.**</span><span class="sxs-lookup"><span data-stu-id="a6366-195">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="a6366-196">В каждом документе SharePoint и OneDrive по умолчанию имеется журнал версий, который можно найти в меню элемента.</span><span class="sxs-lookup"><span data-stu-id="a6366-196">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="a6366-197">Благодаря такому журналу версий можно легко определить, какие версии являются записями, и просмотреть эти документы.</span><span class="sxs-lookup"><span data-stu-id="a6366-197">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="a6366-198">Управление версиями записей автоматически предлагается для любого документа с меткой хранения, помечающей его как запись.</span><span class="sxs-lookup"><span data-stu-id="a6366-198">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="a6366-199">При просмотре пользователем свойств документа с использованием области сведений **Состояние записи** может переключиться с**Заблокировано** на **Разблокировано**.</span><span class="sxs-lookup"><span data-stu-id="a6366-199">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="a6366-200">Одним действием в папке архивной библиотеки "Записи" создается запись, которая остается там в течение оставшегося периода хранения.</span><span class="sxs-lookup"><span data-stu-id="a6366-200">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="a6366-201">Пока документ разблокирован, редактировать файл может любой пользователь со стандартными разрешениями на редактирование.</span><span class="sxs-lookup"><span data-stu-id="a6366-201">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="a6366-202">При этом, однако, удалить файл пользователи не могут, так как он все еще является записью.</span><span class="sxs-lookup"><span data-stu-id="a6366-202">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="a6366-203">После завершения редактирования пользователь может переключить **Состояние записи** с**Разблокировано** на**Заблокировано**, что запрещает дальнейшие правки в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="a6366-203">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Свойство состояния записи в документе, обозначенном как запись](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="a6366-205">Блокировка и разблокировка записи</span><span class="sxs-lookup"><span data-stu-id="a6366-205">Locking and unlocking a record</span></span>

<span data-ttu-id="a6366-206">После того, как метка, которая помечает содержимое как запись, применена к документу, любой пользователь с разрешениями Contribute или более узким уровнем разрешения может разблокировать запись или заблокировать разблокированную запись.</span><span class="sxs-lookup"><span data-stu-id="a6366-206">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Состояние записи демонстрирует, что документ, имеющий статус записи, разблокирован](../media/recordversioning9.png)

<span data-ttu-id="a6366-208">Разблокировка записи пользователем приводит к нижеуказанным результатам.</span><span class="sxs-lookup"><span data-stu-id="a6366-208">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="a6366-209">При отсутствии в текущем семействе веб-сайтов библиотеки хранения архивов такая библиотека создается.</span><span class="sxs-lookup"><span data-stu-id="a6366-209">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="a6366-210">При отсутствии в архивной библиотеке папки записи такая запись создается.</span><span class="sxs-lookup"><span data-stu-id="a6366-210">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="a6366-211">При использовании действия**Копировать в** самая последняя версия документа копируется в папку "Записи".</span><span class="sxs-lookup"><span data-stu-id="a6366-211">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="a6366-212">Действие **Копировать в** относится только к последней версии документа и не затрагивает предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="a6366-212">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="a6366-213">Скопированный документ теперь рассматривается как версия документа в виде записи, и файл приобретает следующий формат: \[Title GUID Version\#\]</span><span class="sxs-lookup"><span data-stu-id="a6366-213">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="a6366-214">Копия, созданная в папке «Записи», добавлена в журнал версий исходного документа, и в поле примечаний к этой версии отображается слово **Запись**.</span><span class="sxs-lookup"><span data-stu-id="a6366-214">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="a6366-215">Исходный документ — это новая версия, которую можно редактировать, но не удалять.</span><span class="sxs-lookup"><span data-stu-id="a6366-215">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="a6366-216">В столбце библиотеки документов **Элемент является записью**по-прежнему содержится значение **Да**, так как документ все равно является записью, несмотря на то, что его теперь можно редактировать.</span><span class="sxs-lookup"><span data-stu-id="a6366-216">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="a6366-217">После того как пользователь заблокирует запись, внесение изменений в исходный документ снова станет невозможным.</span><span class="sxs-lookup"><span data-stu-id="a6366-217">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="a6366-218">Однако именно благодаря действию по разблокировке записи ее версия появляется в папке "Записи", расположенной в архивной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="a6366-218">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="a6366-219">Версии записей</span><span class="sxs-lookup"><span data-stu-id="a6366-219">Record versions</span></span>

<span data-ttu-id="a6366-220">Каждый раз, когда пользователь производит разблокировку записи, копия последней версии этой записи появляется в архивной библиотеке со значением **Запись** в поле**Примечания** журнала версий.</span><span class="sxs-lookup"><span data-stu-id="a6366-220">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Отображение записи в архивной библиотеке](../media/recordversioning10.png)

<span data-ttu-id="a6366-222">Чтобы просмотреть журнал версий, выберите документ в библиотеке документов, а затем в меню элемента выберите **Журнал версий**.</span><span class="sxs-lookup"><span data-stu-id="a6366-222">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="a6366-223">Место хранения записей</span><span class="sxs-lookup"><span data-stu-id="a6366-223">Where records are stored</span></span>

<span data-ttu-id="a6366-224">Записи хранятся в папке "Записи" архивной библиотеки на сайте верхнего уровня в семействе веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="a6366-224">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="a6366-225">В левой панели навигации на сайте верхнего уровня выберите**Содержание сайта** \> **Архивная библиотека**.</span><span class="sxs-lookup"><span data-stu-id="a6366-225">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Архивная библиотека](../media/recordversioning11.png)

<br/><br/>

![Папка "Записи" в архивной библиотеке](../media/recordversioning12.png)

<span data-ttu-id="a6366-228">Архивная библиотека отображается только для администраторов семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="a6366-228">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="a6366-229">Кроме того, архивная библиотека не существует по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a6366-229">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="a6366-230">Такая библиотека создается только тогда, когда содержимое, к которому относится метка хранения или политика хранения, впервые удаляется в семействе веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="a6366-230">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="a6366-231">Поиск событий управления версиями записей в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="a6366-231">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="a6366-232">Действия по блокировке и разблокировке записей регистрируются в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="a6366-232">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="a6366-233">Определенные действия, а именно**Для записи установлено новое состояние: "Заблокировано"** и**Для записи установлено новое состояние: "Разблокировано"** можно найти в разделе **Действия с файлами и страницами**раскрывающегося списка**Действия** на странице**Поиск в журнале аудита** Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a6366-233">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![Поиск событий управления версиями записей в журнале аудита](../media/recordversioning13.png)

<span data-ttu-id="a6366-235">Подробнее о том, как производится поиск таких событий, можно прочитать в разделе "Действия с файлами и страницами" статьи [Поиск в журнале аудита в Центре безопасности и соответствия требованиям](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="a6366-235">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a6366-236">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a6366-236">Next steps</span></span>

<span data-ttu-id="a6366-237">Если у вас еще нет меток хранения для управления записями, см. статью [Начало работы с политиками хранения и метками хранения](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="a6366-237">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="a6366-238">Информацию о ликвидации записей см. в разделе [Ликвидация содержимого](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="a6366-238">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
