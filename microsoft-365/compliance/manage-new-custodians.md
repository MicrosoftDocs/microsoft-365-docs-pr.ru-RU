---
title: Управление хранителями в случае Advanced eDiscovery
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как просматривать сведения, изменять и массово редактировать список хранителей в деле Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739872"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="e388e-103">Управление хранителями в случае Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e388e-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="e388e-104">Страница Custodians на вкладке **"Источники"** в деле Advanced eDiscovery содержит список всех хранителей, добавленных в дело.</span><span class="sxs-lookup"><span data-stu-id="e388e-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="e388e-105">После добавления хранителей в дело сведения о каждом хранителях автоматически собираются из Azure Active Directory и становятся просматриваемыми в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e388e-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Управление хранителями](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="e388e-107">Просмотр сведений о хранителях</span><span class="sxs-lookup"><span data-stu-id="e388e-107">View custodian details</span></span>

<span data-ttu-id="e388e-108">Чтобы просмотреть сведения о хранителях, щелкните его в списке на вкладке **Custodians.** Отобразится эта выдавляемая страница, содержаная следующие сведения об хранителе:</span><span class="sxs-lookup"><span data-stu-id="e388e-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="e388e-109">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="e388e-109">Contact information</span></span>

  - <span data-ttu-id="e388e-110">**Отображаемого** имени — имя, отображаемого в адресной книге для хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="e388e-111">Обычно это сочетание имени, от первой и фамилии хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="e388e-112">**Mail/SMTP** — основной SMTP-адрес для хранителя, например, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e388e-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="e388e-113">Также указано имя пользователя-хранителя (UPN).</span><span class="sxs-lookup"><span data-stu-id="e388e-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="e388e-114">**Должность** — должность хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="e388e-115">**Отдел** — название отдела, в котором работает хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="e388e-116">**Руководитель** — руководитель хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="e388e-117">Назначенный руководитель получит все сообщения об эскалации для этого хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="e388e-118">Сведения о расположении</span><span class="sxs-lookup"><span data-stu-id="e388e-118">Location information</span></span>

  - <span data-ttu-id="e388e-119">**Город** — город, в котором находится хранители.</span><span class="sxs-lookup"><span data-stu-id="e388e-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="e388e-120">**Область** — область или край в адресе хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="e388e-121">**Страна или регион** — страна или регион, где находится хранитель.</span><span class="sxs-lookup"><span data-stu-id="e388e-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="e388e-122">**Office** — расположение офиса в месте работы хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="e388e-123">Сведения о делах</span><span class="sxs-lookup"><span data-stu-id="e388e-123">Case information</span></span>

  - <span data-ttu-id="e388e-124">**Состояние удержания** — указывает, помещен ли хранител на удержание.</span><span class="sxs-lookup"><span data-stu-id="e388e-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="e388e-125">**Состояние связи:** указывает, выдано ли хранителям уведомление об удержании.</span><span class="sxs-lookup"><span data-stu-id="e388e-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="e388e-126">Если хранителям выдано уведомление, это значение этого свойства **публикуется.**</span><span class="sxs-lookup"><span data-stu-id="e388e-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="e388e-127">Если хранителям не было выдано уведомление, состояние не **публикуется.**</span><span class="sxs-lookup"><span data-stu-id="e388e-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="e388e-128">**Состояние** — состояние хранителя в рамках дела.</span><span class="sxs-lookup"><span data-stu-id="e388e-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="e388e-129">Состояние **"Активный"** указывает, что хранители являются частью дела.</span><span class="sxs-lookup"><span data-stu-id="e388e-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="e388e-130">Если хранители отпущены из дела, состояние меняется на **"Освобождено".**</span><span class="sxs-lookup"><span data-stu-id="e388e-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="e388e-131">Источники данных и сведения об индексации</span><span class="sxs-lookup"><span data-stu-id="e388e-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="e388e-132">**Источники данных** — показывает количество и тип источников данных (почтовых ящиков, сайтов и Teams), связанных с хранителями и входящих в дело.</span><span class="sxs-lookup"><span data-stu-id="e388e-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="e388e-133">**Время обновления индекса** — указывает время и дату последнего запуска задания расширенных индексации.</span><span class="sxs-lookup"><span data-stu-id="e388e-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="e388e-134">Это свойство также указывает, когда в данный момент идет расширенный процесс индексации.</span><span class="sxs-lookup"><span data-stu-id="e388e-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="e388e-135">Изменение хранителя</span><span class="sxs-lookup"><span data-stu-id="e388e-135">Edit a custodian</span></span>

<span data-ttu-id="e388e-136">По мере продвижения дела вы можете обнаружить, что могут быть дополнительные источники данных, релевантные для конкретного хранителя & вашем случае.</span><span class="sxs-lookup"><span data-stu-id="e388e-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="e388e-137">В других сценариях может потребоваться удалить определенные источники данных, которые были рассмотрены и признаны не релевантно.</span><span class="sxs-lookup"><span data-stu-id="e388e-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="e388e-138">Обновление источников данных, связанных с хранителями:</span><span class="sxs-lookup"><span data-stu-id="e388e-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="e388e-139">Перейдите  **в > Advanced eDiscovery** и откройте дело.</span><span class="sxs-lookup"><span data-stu-id="e388e-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="e388e-140">Перейдите на **вкладку "Источники".**</span><span class="sxs-lookup"><span data-stu-id="e388e-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="e388e-141">На странице **Custodians** выберите хранителя в списке и нажмите кнопку **"Изменить"** на странице".</span><span class="sxs-lookup"><span data-stu-id="e388e-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Изменение источников данных](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="e388e-143">Щелкните **вкладку "Выбор источников** данных", чтобы изменить параметры почтового ящика Exchange и учетной записи OneDrive хранителя, а затем **выберите "Выбор источников данных".**</span><span class="sxs-lookup"><span data-stu-id="e388e-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="e388e-144">Щелкните **вкладку "Выбор дополнительных источников** данных", чтобы добавить или удалить почтовые ящики Teams, SharePoint или Exchange, связанные с хранителями.</span><span class="sxs-lookup"><span data-stu-id="e388e-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="e388e-145">Дополнительные сведения об источниках данных, связанных с хранителями, см. в подстройки ["Добавление хранителей к делу".](add-custodians-to-case.md)</span><span class="sxs-lookup"><span data-stu-id="e388e-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="e388e-146">Щелкните **"Разместить хранение",** чтобы включить или отключить удержание для хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="e388e-147">Переиндексация данных хранителя</span><span class="sxs-lookup"><span data-stu-id="e388e-147">Re-index custodian data</span></span>

<span data-ttu-id="e388e-148">В большинстве процессов eDiscovery для юридических расследований подмножество данных хранителя будет искаться после того, как он будет добавлен в судебный процесс.</span><span class="sxs-lookup"><span data-stu-id="e388e-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="e388e-149">Из-за очень большого размера файла или возможного повреждения данных некоторые элементы в источниках данных, связанных с хранителями, могут частично индексироваться.</span><span class="sxs-lookup"><span data-stu-id="e388e-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="e388e-150">Используя [расширенные](indexing-custodian-data.md) возможности индексации в Advanced eDiscovery, большинство частично индексированные элементы могут быть автоматически исправлены путем повторной индексации этих элементов по запросу.</span><span class="sxs-lookup"><span data-stu-id="e388e-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="e388e-151">При добавлении хранителя в дело данные, расположенные в источниках данных, связанных с хранителями, автоматически переиндексируются (в процессе дополнительного индексации).</span><span class="sxs-lookup"><span data-stu-id="e388e-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="e388e-152">Это означает, что вы можете оставить данные на месте, а не загружать и устранять их, а затем искать их в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="e388e-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="e388e-153">Однако в течение жизненного цикла судебного дела новые источники данных могут быть связаны с хранителями.</span><span class="sxs-lookup"><span data-stu-id="e388e-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="e388e-154">В этом случае можно переиндексировать данные хранителя, повторно задав расширенный процесс индексации, чтобы исправление всех частично индексных элементов и обновление индекса для данных хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="e388e-155">Чтобы активировать процесс переиндексации для обращения к частично индексным элементами:</span><span class="sxs-lookup"><span data-stu-id="e388e-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="e388e-156">Перейдите  **в > Advanced eDiscovery** и откройте дело.</span><span class="sxs-lookup"><span data-stu-id="e388e-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="e388e-157">Перейдите на **вкладку "Источники".**</span><span class="sxs-lookup"><span data-stu-id="e388e-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="e388e-158">На странице **Custodians** выберите хранителя, данные которого необходимо переиндексовать.</span><span class="sxs-lookup"><span data-stu-id="e388e-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="e388e-159">На странице "Flyout" щелкните **"Обновить индекс".**</span><span class="sxs-lookup"><span data-stu-id="e388e-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="e388e-160">Отобразилось диалоговое окно со словами, что задание индекса создано.</span><span class="sxs-lookup"><span data-stu-id="e388e-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="e388e-161">Переиндексация данных хранителя является длительным процессом; созданное задание называется **"Переиндексация данных хранителя".**</span><span class="sxs-lookup"><span data-stu-id="e388e-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="e388e-162">Вы можете отслеживать ход выполнения на вкладке **"Задания"** или на вкладке **Custodians,** отслеживая состояние в столбце "Состояние **задания индексации".**</span><span class="sxs-lookup"><span data-stu-id="e388e-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="e388e-163">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="e388e-163">For more information, see:</span></span>

- [<span data-ttu-id="e388e-164">Работа с ошибками обработки</span><span class="sxs-lookup"><span data-stu-id="e388e-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="e388e-165">Управление заданиями</span><span class="sxs-lookup"><span data-stu-id="e388e-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="e388e-166">Освобождение хранителя из дела</span><span class="sxs-lookup"><span data-stu-id="e388e-166">Release a custodian from a case</span></span>

<span data-ttu-id="e388e-167">Хранители отпущены в тех случаях, когда дело закрыто, он больше не обязан сохранять содержимое для дела или если он больше не относится к делу.</span><span class="sxs-lookup"><span data-stu-id="e388e-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="e388e-168">Если вы освобождаете хранителя после публикации уведомления об удержании, ему будет отправлено уведомление о выпуске.</span><span class="sxs-lookup"><span data-stu-id="e388e-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="e388e-169">Кроме того, удаляются все хранение источников данных, связанных с хранителями.</span><span class="sxs-lookup"><span data-stu-id="e388e-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="e388e-170">Если хранителя поместили на удержание в тихом режиме, где ему не выданы уведомления о удержании по юридическим вопросам, уведомление о выпуске не отправляется, но все удержания, размещенные на источниках данных, связанных с этим хранителями, удаляются.</span><span class="sxs-lookup"><span data-stu-id="e388e-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="e388e-171">Освобождение хранителя:</span><span class="sxs-lookup"><span data-stu-id="e388e-171">To release a custodian:</span></span> 

1. <span data-ttu-id="e388e-172">Перейдите  **в > Advanced eDiscovery** и откройте дело.</span><span class="sxs-lookup"><span data-stu-id="e388e-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="e388e-173">Перейдите на **вкладку "Источники".**</span><span class="sxs-lookup"><span data-stu-id="e388e-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="e388e-174">На странице **Custodians** выберите хранителя, который будет освобожден из дела.</span><span class="sxs-lookup"><span data-stu-id="e388e-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="e388e-175">На странице "Flyout" щелкните **"Освободить хранителя".**</span><span class="sxs-lookup"><span data-stu-id="e388e-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="e388e-176">Отображается страница предупреждения с объяснением того, что при удержании источника данных, связанного с хранитером, удержание будет удалено, а любое другое удержание, связанное с другим делом Advanced eDiscovery, будет по-прежнему применяться.</span><span class="sxs-lookup"><span data-stu-id="e388e-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="e388e-177">К ним относятся другие типы функций сохранения и хранения (например, политика хранения Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="e388e-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="e388e-178">Нажмите **кнопку** "Да", чтобы подтвердить освобождение хранителя.</span><span class="sxs-lookup"><span data-stu-id="e388e-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="e388e-179">Для этого пользователя на вкладке **Custodians** установлено  состояние "Освобождено", а состояние удержания на странице "Flyout" изменено на **False.** </span><span class="sxs-lookup"><span data-stu-id="e388e-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="e388e-180">Хранители могут быть одновременно вовлечены в несколько судебных дел.</span><span class="sxs-lookup"><span data-stu-id="e388e-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="e388e-181">Когда хранители отпущены из дела, на хранение и уведомления по другим вопросам это не повлияет.</span><span class="sxs-lookup"><span data-stu-id="e388e-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="e388e-182">Массовое редактирование хранителей</span><span class="sxs-lookup"><span data-stu-id="e388e-182">Bulk-edit custodians</span></span>

<span data-ttu-id="e388e-183">Вы можете использовать редактор для массовой рассылки нескольких хранителей одновременно.</span><span class="sxs-lookup"><span data-stu-id="e388e-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="e388e-184">Для этого просто выберите двух или более хранителей на вкладке **Custodians,** чтобы отобразить редактор массовой рассылки, а затем щелкните одну из задач.</span><span class="sxs-lookup"><span data-stu-id="e388e-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Flyout page to edit settings of multiple custodians](../media/AeDBulkEditCustodians.png)
