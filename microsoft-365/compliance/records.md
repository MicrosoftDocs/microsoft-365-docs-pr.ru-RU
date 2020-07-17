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
ms.openlocfilehash: aa5952b26549f9ba9b1c584eb55e203fd53c50e5
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127506"
---
# <a name="learn-about-records"></a><span data-ttu-id="dc343-103">Узнайте о записях</span><span class="sxs-lookup"><span data-stu-id="dc343-103">Learn about records</span></span>

><span data-ttu-id="dc343-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="dc343-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dc343-105">Управление записями в Microsoft 365 помогает организации соблюдать корпоративные политики, правовые и нормативные положения, а также уменьшить риски и правовые последствия.</span><span class="sxs-lookup"><span data-stu-id="dc343-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="dc343-106">Если содержимое помечается как запись:</span><span class="sxs-lookup"><span data-stu-id="dc343-106">When content is marked as an record:</span></span>

- <span data-ttu-id="dc343-107">элемент становится неизменным, т. е. его нельзя изменить или удалить;</span><span class="sxs-lookup"><span data-stu-id="dc343-107">The item becomes immutable, which means that it can't be modified or deleted.</span></span>

- <span data-ttu-id="dc343-108">дополнительные действия, связанные с элементом, фиксируются в журнале;</span><span class="sxs-lookup"><span data-stu-id="dc343-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="dc343-109">когда элемент удаляется по истечении периода хранения, его ликвидация подтверждается.</span><span class="sxs-lookup"><span data-stu-id="dc343-109">You have proof of disposition when they are deleted at the end of their retention period.</span></span>

<span data-ttu-id="dc343-110">Чтобы пометить содержимое как запись, используются [метки хранения](retention.md#retention-labels).</span><span class="sxs-lookup"><span data-stu-id="dc343-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="dc343-111">После создания меток хранения, которые объявляют элементы записями, вы можете либо опубликовать эти метки, чтобы пользователи и администраторы могли вручную применить их к содержимому, либо автоматически применить эти метки к содержимому, которое вы хотите пометить как запись.</span><span class="sxs-lookup"><span data-stu-id="dc343-111">After you create retention labels that declare records, you can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="dc343-112">Используя метки хранения для объявления записей, вы можете реализовать единую согласованную стратегию управления записями в своей среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc343-112">By using retention labels to declare records, you can implement a single, consistent records-management strategy across your Microsoft 365 environment.</span></span>

<span data-ttu-id="dc343-113">По поводу записей необходимо учитывать нижеуказанные нюансы.</span><span class="sxs-lookup"><span data-stu-id="dc343-113">Keep the following things in mind about records:</span></span>

  - <span data-ttu-id="dc343-114">**Записи невозможно изменить.**</span><span class="sxs-lookup"><span data-stu-id="dc343-114">**Records are immutable.**</span></span> <span data-ttu-id="dc343-115">Метку хранения, которая помечает содержимое как запись, можно применить к содержимому не только в SharePoint и OneDrive, но и в Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc343-115">A retention label that marks content as a record can be applied to content in Exchange, in addition to SharePoint and OneDrive.</span></span> <span data-ttu-id="dc343-116">При этом[управление версиями записей](#record-versioning) возможно только в SharePoint и OneDrive, но не в Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc343-116">However, [record versioning](#record-versioning) is available only in SharePoint and OneDrive, and not for Exchange.</span></span>

    <span data-ttu-id="dc343-117">В Exchange содержимое, обозначенное в качестве записи, невозможно изменить до окончательного удаления.</span><span class="sxs-lookup"><span data-stu-id="dc343-117">In Exchange, content labeled as a record is immutable until its final deletion.</span></span> <span data-ttu-id="dc343-118">Если элемент Exchange помечен как запись, для него действуют следующие четыре правила:</span><span class="sxs-lookup"><span data-stu-id="dc343-118">When an Exchange item is labeled as a record, four things happen:</span></span>

    - <span data-ttu-id="dc343-119">элемент невозможно безвозвратно удалить;</span><span class="sxs-lookup"><span data-stu-id="dc343-119">The item can't be permanently deleted.</span></span>

    - <span data-ttu-id="dc343-120">элемент невозможно изменить;</span><span class="sxs-lookup"><span data-stu-id="dc343-120">The item can't be edited.</span></span>

    - <span data-ttu-id="dc343-121">метку невозможно изменить;</span><span class="sxs-lookup"><span data-stu-id="dc343-121">The label can't be changed.</span></span>

    - <span data-ttu-id="dc343-122">метку невозможно удалить.</span><span class="sxs-lookup"><span data-stu-id="dc343-122">The label can't be removed.</span></span>

  - <span data-ttu-id="dc343-123">**Записи и папки.**</span><span class="sxs-lookup"><span data-stu-id="dc343-123">**Records and folders.**</span></span> <span data-ttu-id="dc343-124">Метку хранения можно применить к папке в Exchange, SharePoint или OneDrive.</span><span class="sxs-lookup"><span data-stu-id="dc343-124">You can apply a retention label to a folder in Exchange, SharePoint, and OneDrive.</span></span> <span data-ttu-id="dc343-125">Если папка помечена как запись, и после этого в нее перемещается элемент, то этот элемент также помечается как запись.</span><span class="sxs-lookup"><span data-stu-id="dc343-125">If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record.</span></span> <span data-ttu-id="dc343-126">Если затем переместить его из папки в другое место, этот элемент останется помеченным как запись.</span><span class="sxs-lookup"><span data-stu-id="dc343-126">When you move the item out of the folder, the item remains labeled as a record.</span></span>

    <span data-ttu-id="dc343-127">Кроме того, если изменить метку записи, примененную к папке (в SharePoint и OneDrive), на метку хранения, которая не объявляет содержимое записью, у элементов в этой папке сохранится существующая метка записи.</span><span class="sxs-lookup"><span data-stu-id="dc343-127">Also, if you change the record label that's applied to a folder (in SharePoint and OneDrive) to a retention label that does not declare content as a record, items in the folder keep their existing record label.</span></span>

    <span data-ttu-id="dc343-128">Дополнительные сведения о применении меток хранения к папкам SharePoint и OneDrive см. в разделе [Применение метки хранения по умолчанию ко всему содержимому в библиотеке SharePoint, папке или набору документов](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="dc343-128">For more information about applying retention labels to SharePoint and OneDrive folders, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>

  - <span data-ttu-id="dc343-129">**Записи невозможно удалить**.</span><span class="sxs-lookup"><span data-stu-id="dc343-129">**Records can't be deleted**.</span></span> <span data-ttu-id="dc343-130">Когда пользователь пытается удалить запись в Exchange, элемент перемещается в папку "Элементы с возможностью восстановления", как рассказывается в разделе [Как работает хранение в Exchange](retention-policies-exchange.md#how-retention-works-for-exchange).</span><span class="sxs-lookup"><span data-stu-id="dc343-130">If a user attempts to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How retention works for Exchange](retention-policies-exchange.md#how-retention-works-for-exchange).</span></span>

    <span data-ttu-id="dc343-131">При попытке пользователя удалить запись в SharePoint отображается ошибка с сообщением о том, что элемент не был удален и остается в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="dc343-131">If a user attempts to delete a record in a SharePoint, an error is displayed say that the item wasn't deleted, and remains in the library.</span></span>

    ![Сообщение о том, что элемент не был удален из SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    <span data-ttu-id="dc343-133">Если пользователь пытается удалить запись в OneDrive, элемент перемещается в архивную библиотеку, как описано в разделе [Как работает хранение в SharePoint и OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span><span class="sxs-lookup"><span data-stu-id="dc343-133">If a user attempts to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in [How retention works for SharePoint and OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span></span>

  - <span data-ttu-id="dc343-134">**Метки записей удалить невозможно.**</span><span class="sxs-lookup"><span data-stu-id="dc343-134">**Records labels can't be removed.**</span></span> <span data-ttu-id="dc343-135">После присвоения метки записи элементу ее может удалить только администратор этого расположения (например, администратор семейства веб-сайтов, в том числе сайта SharePoint).</span><span class="sxs-lookup"><span data-stu-id="dc343-135">After a record label has been applied to an item, only the admin of that location (for example, a site collection admin of a SharePoint site) can remove that record label.</span></span>

## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="dc343-136">Использование меток хранения для объявления элементов записями</span><span class="sxs-lookup"><span data-stu-id="dc343-136">Using retention labels to declare records</span></span>

<span data-ttu-id="dc343-137">Когда вы создаете метку хранения, у вас есть возможность использовать метку хранения, чтобы пометить содержимое как запись.</span><span class="sxs-lookup"><span data-stu-id="dc343-137">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="dc343-138">В Центре соответствия требованиям Microsoft 365 перейти в раздел **Управление записями** \> **План хранения**.</span><span class="sxs-lookup"><span data-stu-id="dc343-138">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="dc343-139">На странице **План хранения** выберите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="dc343-139">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="dc343-140">На странице мастера **Параметры метки** нужно выбрать параметр, согласно которому метка хранения обозначит содержимое в качестве записи.</span><span class="sxs-lookup"><span data-stu-id="dc343-140">On the **Label settings** page in the wizard, choose the option to set the retention label to declare content as a record.</span></span>
    
   ![Далее нужно применить команду "Использовать метку", чтобы обозначить содержимое как "Запись" с помощью флажка.](../media/recordversioning6.png)

3. <span data-ttu-id="dc343-142">Применение метки хранения к сайтам SharePoint и учетным записям OneDrive:</span><span class="sxs-lookup"><span data-stu-id="dc343-142">Apply the retention label to SharePoint sites and OneDrive accounts:</span></span>
    
    - [<span data-ttu-id="dc343-143">Создание меток хранения и их применение в приложениях</span><span class="sxs-lookup"><span data-stu-id="dc343-143">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="dc343-144">Автоматическое применение метки хранения к контенту</span><span class="sxs-lookup"><span data-stu-id="dc343-144">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


### <a name="applying-a-retention-label-to-content"></a><span data-ttu-id="dc343-145">Применение метки хранения к содержимому</span><span class="sxs-lookup"><span data-stu-id="dc343-145">Applying a retention label to content</span></span>

<span data-ttu-id="dc343-146">Любой пользователь в Exchange, имеющий доступ к почтовому ящику с возможностью ввода текста, может применить метку хранения для любого сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="dc343-146">For Exchange, any user with write-access to the mailbox can apply a record label to an email message.</span></span> <span data-ttu-id="dc343-147">Применить метку записи к содержимому в SharePoint и OneDrive может любой пользователь, который (на уровне разрешений "Участие").входит в группу "Участники", используемую по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc343-147">For content in SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply a record label to content.</span></span> <span data-ttu-id="dc343-148">Удалить или изменить такую уже присвоенную записи метку может только администратор семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="dc343-148">Only a site collection admin can remove or change that record label after it's been applied.</span></span> <span data-ttu-id="dc343-149">Как говорилось выше, метка хранения, обозначающая содержимое как запись, может применяться к содержимому автоматически.</span><span class="sxs-lookup"><span data-stu-id="dc343-149">As previously explained, a retention label that classifies content as a record can be auto-applied to content.</span></span>

<span data-ttu-id="dc343-150">Вот что получается, если применить метку записи к документу на сайте SharePoint или в учетной записи OneDrive.</span><span class="sxs-lookup"><span data-stu-id="dc343-150">Here's what this looks like when a record label is applied to a document on a SharePoint site or OneDrive account.</span></span>
<br/><br/>

![Область сведений о документе, отмеченном как запись](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="dc343-152">Управление версиями</span><span class="sxs-lookup"><span data-stu-id="dc343-152">Record versioning</span></span>

<span data-ttu-id="dc343-153">Возможность классифицировать документ как запись и сделать эту запись неизменной — важный аспект управления записями.</span><span class="sxs-lookup"><span data-stu-id="dc343-153">An essential part of records management is the ability to declare a document as a record and have that record be immutable.</span></span> <span data-ttu-id="dc343-154">Вместе с тем невозможность изменять запись препятствует совместной работе над документом, если пользователям нужно создавать его последующие версии.</span><span class="sxs-lookup"><span data-stu-id="dc343-154">At the same time, record immutability prevents collaboration on the document if people need to create subsequent versions.</span></span> <span data-ttu-id="dc343-155">Например, контракт продажи можно обозначить как запись, и затем, когда требуется этот контракт обновить и внести новые положения, обозначить последнюю версию как новую запись, при этом сохраняется и предыдущая версия записи.</span><span class="sxs-lookup"><span data-stu-id="dc343-155">For example, you might declare a sales contract as a record, but then need to update the contract with new terms and declare the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="dc343-156">Для таких случаев в SharePoint и OneDrive поддерживается *управление версиями записей*.</span><span class="sxs-lookup"><span data-stu-id="dc343-156">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="dc343-157">Папки записных книжек OneNote не поддерживают управление версиями записей.</span><span class="sxs-lookup"><span data-stu-id="dc343-157">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="dc343-158">Чтобы воспользоваться управлением версиями записей, в первую очередь необходимо в Центре соответствия требованиям Microsoft 365 создать метки хранения, которые объявляют элементы записями, и опубликовать их на всех сайтах SharePoint и в учетных записях OneDrive или опубликовать их на определенных сайтах SharePoint или в учетных записях OneDrive.</span><span class="sxs-lookup"><span data-stu-id="dc343-158">To use record versioning, the first step is to use the Microsoft 365 compliance center to create retention labels that declare records and and publish them to all SharePoint sites and OneDrive accounts, or publish them to specific SharePoint sites or OneDrive accounts.</span></span> <span data-ttu-id="dc343-159">Следующий этап — применение опубликованной метки записи к документу.</span><span class="sxs-lookup"><span data-stu-id="dc343-159">The next step is to apply a published retention record label to a document.</span></span> <span data-ttu-id="dc343-160">При этом рядом с меткой хранения отобразится свойство документа под названием *Состояние записи*, а изначальное состояние записи сменится на**Заблокировано**.</span><span class="sxs-lookup"><span data-stu-id="dc343-160">When this happens, a document property, called *Record status* is displayed next to the retention label, and the initial record status will be **Locked**.</span></span> <span data-ttu-id="dc343-161">На этом этапе можно совершать нижеуказанные действия.</span><span class="sxs-lookup"><span data-stu-id="dc343-161">At this point, you can do the following things:</span></span>

  - <span data-ttu-id="dc343-162">**Периодическое редактирование и обозначение отдельных версий документа как записей с разблокировкой и блокировкой свойства "Состояние записи".**</span><span class="sxs-lookup"><span data-stu-id="dc343-162">**Continually edit and declare individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="dc343-163">Когда свойство **Состояние записи** установлено как **Заблокировано**, сохраняются только версии, обозначенные как записи.</span><span class="sxs-lookup"><span data-stu-id="dc343-163">Only the versions declared as records are retained when the **Record status** property is set to **Locked**.</span></span> <span data-ttu-id="dc343-164">Это уменьшает риск сохранения ненужных версий и копий документа.</span><span class="sxs-lookup"><span data-stu-id="dc343-164">This reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="dc343-165">**Автоматическое сохранение записей в репозитории записей на месте, который размещается внутри семейства веб-сайтов.**</span><span class="sxs-lookup"><span data-stu-id="dc343-165">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="dc343-166">Содержимое любого семейства веб-сайтов в SharePoint и OneDrive сохраняется в соответствующей архивной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="dc343-166">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="dc343-167">Место хранения версий записей в этой библиотеке —папка "Записи".</span><span class="sxs-lookup"><span data-stu-id="dc343-167">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="dc343-168">**Сохранение всегда актуального документа, включающего в себя все версии.**</span><span class="sxs-lookup"><span data-stu-id="dc343-168">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="dc343-169">В каждом документе SharePoint и OneDrive по умолчанию имеется журнал версий, который можно найти в меню элемента.</span><span class="sxs-lookup"><span data-stu-id="dc343-169">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="dc343-170">Благодаря такому журналу версий можно легко определить, какие версии являются записями, и просмотреть эти документы.</span><span class="sxs-lookup"><span data-stu-id="dc343-170">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="dc343-171">Управление версиями записей автоматически предлагается для любого документа с меткой хранения, обозначающей его как запись.</span><span class="sxs-lookup"><span data-stu-id="dc343-171">Record versioning is automatically available for any document that has a retention label that declares the item as a record.</span></span> <span data-ttu-id="dc343-172">При просмотре пользователем свойств документа в области сведений **Состояние записи** переключается с**Заблокировано** на **Разблокировано**.</span><span class="sxs-lookup"><span data-stu-id="dc343-172">When a user views the document properties through the details pane, they toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="dc343-173">Так всего одним щелчком в папке архивной библиотеки "Записи" создается запись, которая остается там в течение оставшегося периода хранения.</span><span class="sxs-lookup"><span data-stu-id="dc343-173">This single click creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="dc343-174">Пока документ разблокирован, редактировать файл может любой пользователь, у которого есть соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="dc343-174">While the document is unlocked, any user with permissions can edit the file.</span></span> <span data-ttu-id="dc343-175">При этом, однако, удалить файл пользователи не могут, так как он считается записью.</span><span class="sxs-lookup"><span data-stu-id="dc343-175">However, users can't delete the file, because it's considered a record.</span></span> <span data-ttu-id="dc343-176">После внесения нужных изменений пользователь может переключить **Состояние записи** с**Разблокировано**на **Заблокировано**. Таким образом документ снова обозначается как запись, и его нельзя редактировать.</span><span class="sxs-lookup"><span data-stu-id="dc343-176">After the necessary changes are made, the user can then toggle the **Record status** from **Unlocked** to **Locked**, so that the document is again declared a record and can't be edited.</span></span>
<br/><br/>

![Свойство состояния записи в документе, обозначенном как запись](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="dc343-178">Блокировка и разблокировка записи</span><span class="sxs-lookup"><span data-stu-id="dc343-178">Locking and unlocking a record</span></span>

<span data-ttu-id="dc343-179">После того, как метка записи назначена документу, любой пользователь с разрешениями Contribute или более узким уровнем разрешений может разблокировать запись или заблокировать незаблокированную запись.</span><span class="sxs-lookup"><span data-stu-id="dc343-179">After a record label is assigned to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Состояние записи демонстрирует, что документ, имеющий статус записи, разблокирован](../media/recordversioning9.png)

<span data-ttu-id="dc343-181">Разблокировка записи пользователем приводит к нижеуказанным результатам.</span><span class="sxs-lookup"><span data-stu-id="dc343-181">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="dc343-182">При отсутствии в текущем семействе веб-сайтов библиотеки хранения архивов такая библиотека создается.</span><span class="sxs-lookup"><span data-stu-id="dc343-182">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="dc343-183">При отсутствии в архивной библиотеке папки записи такая запись создается.</span><span class="sxs-lookup"><span data-stu-id="dc343-183">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="dc343-184">При использовании действия**Копировать в** самая последняя версия документа копируется в папку "Записи".</span><span class="sxs-lookup"><span data-stu-id="dc343-184">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="dc343-185">Действие **Копировать в** относится только к последней версии документа и не затрагивает предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="dc343-185">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="dc343-186">Скопированный документ теперь рассматривается как версия документа в виде записи, и файл приобретает следующий формат: \[Title GUID Version\#\]</span><span class="sxs-lookup"><span data-stu-id="dc343-186">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="dc343-187">Копия, созданная в папке "Записи", добавляется в журнал версий исходного документа, и в поле примечаний к этой версии отображается слово **Запись**.</span><span class="sxs-lookup"><span data-stu-id="dc343-187">The copy created in the Records folder added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="dc343-188">Исходный документ — это новая версия, которую можно редактировать (но не удалять).</span><span class="sxs-lookup"><span data-stu-id="dc343-188">The original document is a new version that can be edited (but not deleted).</span></span> <span data-ttu-id="dc343-189">В столбце библиотеки документов **Элемент является записью**по-прежнему содержится значение **Да**, так как документ все так же рассматривается как запись, несмотря на то, что его теперь можно редактировать.</span><span class="sxs-lookup"><span data-stu-id="dc343-189">The document library column **Item is a Record** still shows the **Yes** value because the document is still considered a record, even if it can now be edited.</span></span>

<span data-ttu-id="dc343-190">После того как пользователь заблокирует запись, внесение изменений в исходный документ снова станет невозможным.</span><span class="sxs-lookup"><span data-stu-id="dc343-190">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="dc343-191">Однако именно благодаря действию по разблокировке записи ее версия появляется в папке "Записи", расположенной в архивной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="dc343-191">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="dc343-192">Версии записей</span><span class="sxs-lookup"><span data-stu-id="dc343-192">Record versions</span></span>

<span data-ttu-id="dc343-193">Каждый раз, когда пользователь производит разблокировку записи, копия последней версии этой записи появляется в архивной библиотеке со значением **Запись** в поле**Примечания** журнала версий.</span><span class="sxs-lookup"><span data-stu-id="dc343-193">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Отображение записи в архивной библиотеке](../media/recordversioning10.png)

<span data-ttu-id="dc343-195">Чтобы просмотреть журнал версий, выберите документ в библиотеке документов, а затем в меню элемента выберите **Журнал версий**.</span><span class="sxs-lookup"><span data-stu-id="dc343-195">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="dc343-196">Место хранения записей</span><span class="sxs-lookup"><span data-stu-id="dc343-196">Where records are stored</span></span>

<span data-ttu-id="dc343-197">Записи хранятся в папке "Записи" архивной библиотеки на сайте верхнего уровня в семействе веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="dc343-197">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="dc343-198">В левой панели навигации на сайте верхнего уровня выберите **Содержимое сайта** \> **Архивная библиотека**.</span><span class="sxs-lookup"><span data-stu-id="dc343-198">In the left nav on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Архивная библиотека](../media/recordversioning11.png)

<br/><br/>

![Папка "Записи" в архивной библиотеке](../media/recordversioning12.png)

<span data-ttu-id="dc343-201">Архивная библиотека отображается только для администраторов семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="dc343-201">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="dc343-202">Кроме того, архивная библиотека не существует по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc343-202">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="dc343-203">Такая библиотека создается только тогда, когда содержимое, к которому относится метка хранения или политика хранения, впервые удаляется в семействе веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="dc343-203">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="dc343-204">Поиск событий управления версиями записей в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="dc343-204">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="dc343-205">Действия по блокировке и разблокировке записей регистрируются в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="dc343-205">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="dc343-206">Определенные действия, а именно**Для записи установлено новое состояние: "Заблокировано"** и**Для записи установлено новое состояние: "Разблокировано"** можно найти в разделе **Действия с файлами и страницами**раскрывающегося списка**Действия** на странице**Поиск в журнале аудита** Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="dc343-206">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![Поиск событий управления версиями записей в журнале аудита](../media/recordversioning13.png)

<span data-ttu-id="dc343-208">Подробнее о том, как производится поиск таких событий, можно прочитать в разделе "Действия с файлами и страницами" статьи [Поиск в журнале аудита в Центре безопасности и соответствия требованиям](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="dc343-208">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="dc343-209">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="dc343-209">Next steps</span></span>

<span data-ttu-id="dc343-210">Если у вас еще нет меток хранения для управления записями, см. статью [Начало работы с политиками хранения и метками хранения](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="dc343-210">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="dc343-211">Видео о настройке и использовании управления записями представлены в [подборке на сайте YouTube](https://go.microsoft.com/fwlink/?linkid=867039).</span><span class="sxs-lookup"><span data-stu-id="dc343-211">To watch videos related to configuring and using records management, see the [Data governance selections on YouTube](https://go.microsoft.com/fwlink/?linkid=867039).</span></span>
