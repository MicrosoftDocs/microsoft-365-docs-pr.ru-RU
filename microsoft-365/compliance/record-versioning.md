---
title: Использование управления версиями записей для обновления записей, хранящихся в SharePoint или OneDrive
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
ms.openlocfilehash: 86fbd84e03263ca5d99e1bfe6ab572589dc98bbd
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226135"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="86bb8-103">Использование управления версиями записей для обновления записей, хранящихся в SharePoint или OneDrive</span><span class="sxs-lookup"><span data-stu-id="86bb8-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="86bb8-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="86bb8-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="86bb8-105">Так как нормативные записи блокируют редактирование, управление версиями записей для них недоступно.</span><span class="sxs-lookup"><span data-stu-id="86bb8-105">Because regulatory records block editing, record versioning is not available for regulatory records.</span></span>

<span data-ttu-id="86bb8-106">Возможность пометить документ как [запись](records-management.md#records) и ограничить действия, которые можно выполнять с записью, является основной целью любого решения по управлению записями.</span><span class="sxs-lookup"><span data-stu-id="86bb8-106">The ability to mark a document as a [record](records-management.md#records) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="86bb8-107">Однако для создания последующих версий может также потребоваться совместная работа.</span><span class="sxs-lookup"><span data-stu-id="86bb8-107">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="86bb8-108">Например, контракт продажи можно пометить как запись, и затем, когда требуется этот контракт обновить и внести новые положение, пометить последнюю версию как новую запись, и при этом сохраняется и предыдущая версия записи.</span><span class="sxs-lookup"><span data-stu-id="86bb8-108">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="86bb8-109">Для таких случаев в SharePoint и OneDrive поддерживается *управление версиями записей*.</span><span class="sxs-lookup"><span data-stu-id="86bb8-109">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="86bb8-110">Папки записных книжек OneNote не поддерживают управление версиями записей.</span><span class="sxs-lookup"><span data-stu-id="86bb8-110">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="86bb8-111">Чтобы использовать управление версиями записей, сначала [отметьте документ и пометьте его как запись](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="86bb8-111">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="86bb8-112">В этот момент рядом с меткой хранения отобразится свойство документа под названием *Состояние записи*, а изначальное состояние записи сменится на **Заблокировано**.</span><span class="sxs-lookup"><span data-stu-id="86bb8-112">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span>

<span data-ttu-id="86bb8-113">Доступны перечисленные ниже действия:</span><span class="sxs-lookup"><span data-stu-id="86bb8-113">You can now do the following things:</span></span>

- <span data-ttu-id="86bb8-114">**Периодическое редактирование и сохранение отдельных версий документа как записей с разблокировкой и блокировкой свойства "Состояние записи".**</span><span class="sxs-lookup"><span data-stu-id="86bb8-114">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="86bb8-115">Только когда свойство **Состояние записи** имеет значение **Заблокировано**, новая версия записи сохраняется.</span><span class="sxs-lookup"><span data-stu-id="86bb8-115">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="86bb8-116">Это переключение между заблокированными и разблокированными версиями уменьшает риск сохранения ненужных версий и копий документа.</span><span class="sxs-lookup"><span data-stu-id="86bb8-116">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

- <span data-ttu-id="86bb8-117">**Автоматическое сохранение записей в репозитории записей на месте, который размещается внутри семейства веб-сайтов.**</span><span class="sxs-lookup"><span data-stu-id="86bb8-117">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="86bb8-118">Содержимое любого семейства веб-сайтов в SharePoint и OneDrive сохраняется в соответствующей архивной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="86bb8-118">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="86bb8-119">Место хранения версий записей в этой библиотеке —папка "Записи".</span><span class="sxs-lookup"><span data-stu-id="86bb8-119">Record versions are stored in the Records folder in this library.</span></span>

- <span data-ttu-id="86bb8-120">**Сохранение всегда актуального документа, включающего в себя все версии.**</span><span class="sxs-lookup"><span data-stu-id="86bb8-120">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="86bb8-121">В каждом документе SharePoint и OneDrive по умолчанию имеется журнал версий, который можно найти в меню элемента.</span><span class="sxs-lookup"><span data-stu-id="86bb8-121">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="86bb8-122">Благодаря такому журналу версий можно легко определить, какие версии являются записями, и просмотреть эти документы.</span><span class="sxs-lookup"><span data-stu-id="86bb8-122">In this version history, you can easily see which versions are records and view those documents.</span></span>

> [!TIP]
> <span data-ttu-id="86bb8-123">При управлении версиями записей с помощью метки хранения, предусматривающей удаление, рекомендуется также присвоить параметру хранения **Началом периода хранения считается:** значение **Дата создания меток хранения элементов**.</span><span class="sxs-lookup"><span data-stu-id="86bb8-123">When you use record versioning with a retention label that has a delete action, consider configuring the retention setting **Start the retention period based on:** to be **When items were labeled**.</span></span> <span data-ttu-id="86bb8-124">При использовании этого параметра метки начало периода хранения сбрасывается для каждой новой версии записи, что гарантирует удаление более старых версий перед новыми версиями.</span><span class="sxs-lookup"><span data-stu-id="86bb8-124">With this label setting, the start of the retention period is reset for each new record version, which ensures that older versions will be deleted before newer versions.</span></span>

<span data-ttu-id="86bb8-125">Управление версиями записей автоматически предлагается для любого документа с меткой хранения, помечающей его как запись.</span><span class="sxs-lookup"><span data-stu-id="86bb8-125">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="86bb8-126">При просмотре пользователем свойств документа с использованием области сведений **Состояние записи** может переключиться с **Заблокировано** на **Разблокировано**.</span><span class="sxs-lookup"><span data-stu-id="86bb8-126">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="86bb8-127">Одним действием в папке архивной библиотеки "Записи" создается запись, которая остается там в течение оставшегося периода хранения.</span><span class="sxs-lookup"><span data-stu-id="86bb8-127">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span>

<span data-ttu-id="86bb8-128">Пока документ разблокирован, редактировать файл может любой пользователь со стандартными разрешениями на редактирование.</span><span class="sxs-lookup"><span data-stu-id="86bb8-128">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="86bb8-129">При этом, однако, удалить файл пользователи не могут, так как он все еще является записью.</span><span class="sxs-lookup"><span data-stu-id="86bb8-129">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="86bb8-130">После завершения редактирования пользователь может переключить **Состояние записи** с **Разблокировано** на **Заблокировано**, что запрещает дальнейшие правки в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="86bb8-130">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Свойство состояния записи в документе, обозначенном как запись](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="86bb8-132">Блокировка и разблокировка записи</span><span class="sxs-lookup"><span data-stu-id="86bb8-132">Locking and unlocking a record</span></span>

<span data-ttu-id="86bb8-133">После того, как метка, которая помечает содержимое как запись, применена к документу, любой пользователь с разрешениями Contribute или более узким уровнем разрешения может разблокировать запись или заблокировать разблокированную запись.</span><span class="sxs-lookup"><span data-stu-id="86bb8-133">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Состояние записи демонстрирует, что документ, имеющий статус записи, разблокирован](../media/recordversioning9.png)

<span data-ttu-id="86bb8-135">Разблокировка записи пользователем приводит к нижеуказанным результатам.</span><span class="sxs-lookup"><span data-stu-id="86bb8-135">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="86bb8-136">При отсутствии в текущем семействе веб-сайтов библиотеки хранения архивов такая библиотека создается.</span><span class="sxs-lookup"><span data-stu-id="86bb8-136">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="86bb8-137">При отсутствии в архивной библиотеке папки записи такая запись создается.</span><span class="sxs-lookup"><span data-stu-id="86bb8-137">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="86bb8-138">При использовании действия **Копировать в** самая последняя версия документа копируется в папку "Записи".</span><span class="sxs-lookup"><span data-stu-id="86bb8-138">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="86bb8-139">Действие **Копировать в** относится только к последней версии документа и не затрагивает предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="86bb8-139">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="86bb8-140">Скопированный документ теперь рассматривается как версия документа в виде записи, и файл приобретает следующий формат: \[Title GUID Version\#\]</span><span class="sxs-lookup"><span data-stu-id="86bb8-140">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="86bb8-141">Копия, созданная в папке «Записи», добавлена в журнал версий исходного документа, и в поле примечаний к этой версии отображается слово **Запись**.</span><span class="sxs-lookup"><span data-stu-id="86bb8-141">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="86bb8-142">Исходный документ — это новая версия, которую можно редактировать, но не удалять.</span><span class="sxs-lookup"><span data-stu-id="86bb8-142">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="86bb8-143">В столбце библиотеки документов **Элемент является записью** по-прежнему содержится значение **Да**, так как документ все равно является записью, несмотря на то, что его теперь можно редактировать.</span><span class="sxs-lookup"><span data-stu-id="86bb8-143">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="86bb8-144">После того как пользователь заблокирует запись, внесение изменений в исходный документ снова станет невозможным.</span><span class="sxs-lookup"><span data-stu-id="86bb8-144">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="86bb8-145">Однако именно благодаря действию по разблокировке записи ее версия появляется в папке "Записи", расположенной в архивной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="86bb8-145">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="86bb8-146">Версии записей</span><span class="sxs-lookup"><span data-stu-id="86bb8-146">Record versions</span></span>

<span data-ttu-id="86bb8-147">Каждый раз, когда пользователь производит разблокировку записи, копия последней версии этой записи появляется в архивной библиотеке со значением **Запись** в поле **Примечания** журнала версий.</span><span class="sxs-lookup"><span data-stu-id="86bb8-147">Each time a user unlocks a record, the latest version is copied to the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Отображение записи в архивной библиотеке](../media/recordversioning10.png)

<span data-ttu-id="86bb8-149">Чтобы просмотреть журнал версий, выберите документ в библиотеке документов, а затем в меню элемента выберите **Журнал версий**.</span><span class="sxs-lookup"><span data-stu-id="86bb8-149">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="86bb8-150">Место хранения записей</span><span class="sxs-lookup"><span data-stu-id="86bb8-150">Where records are stored</span></span>

<span data-ttu-id="86bb8-151">Записи хранятся в папке "Записи" архивной библиотеки на сайте верхнего уровня в семействе веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="86bb8-151">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="86bb8-152">В левой панели навигации на сайте верхнего уровня выберите **Содержание сайта** \> **Архивная библиотека**.</span><span class="sxs-lookup"><span data-stu-id="86bb8-152">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Архивная библиотека](../media/recordversioning11.png)

<br/><br/>

![Папка "Записи" в архивной библиотеке](../media/recordversioning12.png)

<span data-ttu-id="86bb8-155">Подробнее о принципах работы архивной библиотеки см. в статье [Как работает хранение для SharePoint и OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span><span class="sxs-lookup"><span data-stu-id="86bb8-155">For more information about how the Preservation Hold library works, see [How retention works for SharePoint and OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="86bb8-156">Поиск событий управления версиями записей в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="86bb8-156">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="86bb8-157">Действия по блокировке и разблокировке записей регистрируются в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="86bb8-157">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="86bb8-158">В разделе **Действия с файлами и страницами** выберите **Для записи установлено новое состояние: "заблокирована"** и **Для записи установлено новое состояние: "разблокирована"**.</span><span class="sxs-lookup"><span data-stu-id="86bb8-158">From **File and page activities**, select **Changed record status to locked** and **Changed record status to unlocked**.</span></span>

<span data-ttu-id="86bb8-159">Дополнительные сведения о поиске таких событий см. в статье [Поиск в журнале аудита в Центре безопасности и соответствия требованиям](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="86bb8-159">For more information about searching for these events, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="86bb8-160">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="86bb8-160">Next steps</span></span>

<span data-ttu-id="86bb8-161">Другие сценарии, поддерживаемые службой управления записей, см. в разделе [Обычные сценарии для управления записями](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="86bb8-161">For other scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
