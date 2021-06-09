---
title: Управление хранителями в Advanced eDiscovery случае
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
description: Сведения о просмотре сведений, редактировании и массовом редактировании списка хранителей в Advanced eDiscovery случае.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739872"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="f76d3-103">Управление хранителями в Advanced eDiscovery случае</span><span class="sxs-lookup"><span data-stu-id="f76d3-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="f76d3-104">Страница Custodians на вкладке **Источники** в Advanced eDiscovery содержит список всех хранителей, добавленных в дело.</span><span class="sxs-lookup"><span data-stu-id="f76d3-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="f76d3-105">После добавления хранителей в дело сведения о каждом хранители автоматически собираются из Azure Active Directory и просматриваются в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f76d3-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Управление хранителями](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="f76d3-107">Просмотр сведений о хранителях</span><span class="sxs-lookup"><span data-stu-id="f76d3-107">View custodian details</span></span>

<span data-ttu-id="f76d3-108">Чтобы просмотреть сведения о хранителях, щелкните хранителя из списка на вкладке **Custodians.** Отображается страница вылета и содержит следующую информацию о хранителе:</span><span class="sxs-lookup"><span data-stu-id="f76d3-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="f76d3-109">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="f76d3-109">Contact information</span></span>

  - <span data-ttu-id="f76d3-110">**Отображение имени** — имя, отображаемого в адресной книге для хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="f76d3-111">Обычно это сочетание имени, среднего начального и фамилии хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="f76d3-112">**Mail/SMTP** — основной smTP-адрес для хранителя, например, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="f76d3-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="f76d3-113">Кроме того, в списке указано основное имя пользователя хранителя (UPN).</span><span class="sxs-lookup"><span data-stu-id="f76d3-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="f76d3-114">**Название** . Название должности хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="f76d3-115">**Department** — имя отдела, в котором работает хранитель.</span><span class="sxs-lookup"><span data-stu-id="f76d3-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="f76d3-116">**Менеджер** - управляющий хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="f76d3-117">Назначенный диспетчер получит любые сообщения об эскалации для этого хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="f76d3-118">Сведения о расположении</span><span class="sxs-lookup"><span data-stu-id="f76d3-118">Location information</span></span>

  - <span data-ttu-id="f76d3-119">**Город** — город, в котором расположен хранитель.</span><span class="sxs-lookup"><span data-stu-id="f76d3-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="f76d3-120">**Состояние** — состояние или область в адресе хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="f76d3-121">**Страна/регион** — страна или регион, где находится хранитель.</span><span class="sxs-lookup"><span data-stu-id="f76d3-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="f76d3-122">**Office** — расположение офиса на месте бизнеса хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="f76d3-123">Сведения о деле</span><span class="sxs-lookup"><span data-stu-id="f76d3-123">Case information</span></span>

  - <span data-ttu-id="f76d3-124">**Состояние удержания** — указывает, был ли хранитель помещен на удержание.</span><span class="sxs-lookup"><span data-stu-id="f76d3-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="f76d3-125">**Состояние связи.** Указывает, был ли хранитель уведомлен о удержании.</span><span class="sxs-lookup"><span data-stu-id="f76d3-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="f76d3-126">Если хранителям было выдано уведомление, это значение этого **свойства публикуется.**</span><span class="sxs-lookup"><span data-stu-id="f76d3-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="f76d3-127">Если хранителям не было выдано уведомление, статус **не публикуется.**</span><span class="sxs-lookup"><span data-stu-id="f76d3-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="f76d3-128">**Состояние** — состояние хранителя в рамках дела.</span><span class="sxs-lookup"><span data-stu-id="f76d3-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="f76d3-129">Состояние Active **указывает,** что хранитель является частью дела.</span><span class="sxs-lookup"><span data-stu-id="f76d3-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="f76d3-130">Если хранитель освобожден из дела, его состояние меняется на **"Освобождено".**</span><span class="sxs-lookup"><span data-stu-id="f76d3-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="f76d3-131">Источники данных и сведения об индексации</span><span class="sxs-lookup"><span data-stu-id="f76d3-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="f76d3-132">**Источники данных** — показывает количество и тип источников данных (почтовые ящики, сайты и Teams), которые связаны с хранителями и являются частью дела.</span><span class="sxs-lookup"><span data-stu-id="f76d3-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="f76d3-133">**Время обновления индекса** — указывает время и дату последнего запуска задания по индексированию.</span><span class="sxs-lookup"><span data-stu-id="f76d3-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="f76d3-134">Это свойство также указывает, когда в настоящее время идет расширенный процесс индексации.</span><span class="sxs-lookup"><span data-stu-id="f76d3-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="f76d3-135">Изменение хранителя</span><span class="sxs-lookup"><span data-stu-id="f76d3-135">Edit a custodian</span></span>

<span data-ttu-id="f76d3-136">По мере развития дела вы можете обнаружить, что могут быть дополнительные источники данных, соответствующие конкретному & вашему делу.</span><span class="sxs-lookup"><span data-stu-id="f76d3-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="f76d3-137">В других сценариях может потребоваться удалить некоторые источники данных, которые были рассмотрены и признаны не соответствующими.</span><span class="sxs-lookup"><span data-stu-id="f76d3-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="f76d3-138">Обновление источников данных, связанных с хранителями:</span><span class="sxs-lookup"><span data-stu-id="f76d3-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="f76d3-139">Перейдите **в > Advanced eDiscovery** и откройте дело.</span><span class="sxs-lookup"><span data-stu-id="f76d3-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="f76d3-140">Щелкните **вкладку Источники.**</span><span class="sxs-lookup"><span data-stu-id="f76d3-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="f76d3-141">На странице **Хранители** выберите хранителя из списка и нажмите **кнопку Изменить** на странице flyout.</span><span class="sxs-lookup"><span data-stu-id="f76d3-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Изменение источников данных](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="f76d3-143">Нажмите **кнопку** Выберите вкладку Источники данных, чтобы изменить параметры Exchange почтового ящика и OneDrive учетной записи хранителя, выберите **источники данных.**</span><span class="sxs-lookup"><span data-stu-id="f76d3-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="f76d3-144">Щелкните **вкладку Выберите** дополнительные источники данных, чтобы добавить или удалить Teams, SharePoint или Exchange почтовых ящиков, связанных с хранителями.</span><span class="sxs-lookup"><span data-stu-id="f76d3-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="f76d3-145">Дополнительные сведения об источниках данных, связанных с хранителями, см. в добавлении [хранителей к делу.](add-custodians-to-case.md)</span><span class="sxs-lookup"><span data-stu-id="f76d3-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="f76d3-146">Нажмите **кнопку Удержание места,** чтобы включить или отключить удержание для хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="f76d3-147">Данные хранителя повторной индексации</span><span class="sxs-lookup"><span data-stu-id="f76d3-147">Re-index custodian data</span></span>

<span data-ttu-id="f76d3-148">В большинстве процессов по обнаружению электронных данных для юридических расследований подмножество данных хранителя будет искаться после того, как хранитель будет добавлен в судебное дело.</span><span class="sxs-lookup"><span data-stu-id="f76d3-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="f76d3-149">Из-за очень больших размеров файлов или возможного повреждения данных некоторые элементы в источниках данных, связанных с хранителями, могут быть частично проиндексируются.</span><span class="sxs-lookup"><span data-stu-id="f76d3-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="f76d3-150">Используя [расширенные](indexing-custodian-data.md) возможности индексации в Advanced eDiscovery, большинство частично индексированные элементы могут быть автоматически исправлены путем повторной индексации этих элементов по запросу.</span><span class="sxs-lookup"><span data-stu-id="f76d3-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="f76d3-151">При добавлении хранителя в дело данные, расположенные в источниках данных, связанных с хранителями, автоматически индексируются (в процессе предварительной индексации).</span><span class="sxs-lookup"><span data-stu-id="f76d3-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="f76d3-152">Это означает, что вы можете оставить данные на месте, а не загружать и устранять их, а затем искать их в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="f76d3-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="f76d3-153">Однако в течение жизненного цикла судебного дела новые источники данных могут быть связаны с хранителями.</span><span class="sxs-lookup"><span data-stu-id="f76d3-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="f76d3-154">В этом случае можно переиндексировать данные хранителя, повторно запуская расширенный процесс индексации, чтобы исправление любых частично индексных элементов и обновление индекса для данных хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="f76d3-155">Чтобы вызвать процесс повторной индексации для частичной индексации элементов:</span><span class="sxs-lookup"><span data-stu-id="f76d3-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="f76d3-156">Перейдите **в > Advanced eDiscovery** и откройте дело.</span><span class="sxs-lookup"><span data-stu-id="f76d3-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="f76d3-157">Щелкните **вкладку Источники.**</span><span class="sxs-lookup"><span data-stu-id="f76d3-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="f76d3-158">На странице **Хранители** выберите хранителя, данные которого необходимо реиндексовать.</span><span class="sxs-lookup"><span data-stu-id="f76d3-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="f76d3-159">На странице флажок нажмите кнопку **Update Index**.</span><span class="sxs-lookup"><span data-stu-id="f76d3-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="f76d3-160">Отображается диалоговое окно со словами, что задание индекса создано.</span><span class="sxs-lookup"><span data-stu-id="f76d3-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="f76d3-161">Переиндексация данных хранителя является длительным процессом; созданное задание называется данными об хранителях **повторной индексации.**</span><span class="sxs-lookup"><span data-stu-id="f76d3-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="f76d3-162">Вы можете отслеживать ход выполнения на вкладке **Jobs** или на вкладке **Custodians,** отслеживая состояние в столбце **Состояние задания индексации.**</span><span class="sxs-lookup"><span data-stu-id="f76d3-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="f76d3-163">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="f76d3-163">For more information, see:</span></span>

- [<span data-ttu-id="f76d3-164">Работа с ошибками обработки</span><span class="sxs-lookup"><span data-stu-id="f76d3-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="f76d3-165">Управление заданиями</span><span class="sxs-lookup"><span data-stu-id="f76d3-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="f76d3-166">Освобождение хранителя из дела</span><span class="sxs-lookup"><span data-stu-id="f76d3-166">Release a custodian from a case</span></span>

<span data-ttu-id="f76d3-167">Хранитель выпускается в ситуациях, когда дело закрыто, хранитель больше не обязан хранить контент для дела или если он считается более не соответствующим делу.</span><span class="sxs-lookup"><span data-stu-id="f76d3-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="f76d3-168">Если вы освобождаете хранителя после публикации уведомления об удержании, он отправляет уведомление об освобождении.</span><span class="sxs-lookup"><span data-stu-id="f76d3-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="f76d3-169">Кроме того, удаляются любые удерживаемые данные, размещенные на источниках данных, связанных с хранителями.</span><span class="sxs-lookup"><span data-stu-id="f76d3-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="f76d3-170">Если хранитель был помещен на молчаливое удержание, где ему не были выданы какие-либо юридические уведомления о удержании, уведомление об освобождении не будет отправлено, но любые удержания, размещенные на источниках данных, связанных с этим хранителя, удаляются.</span><span class="sxs-lookup"><span data-stu-id="f76d3-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="f76d3-171">Чтобы освободить хранителя:</span><span class="sxs-lookup"><span data-stu-id="f76d3-171">To release a custodian:</span></span> 

1. <span data-ttu-id="f76d3-172">Перейдите **в > Advanced eDiscovery** и откройте дело.</span><span class="sxs-lookup"><span data-stu-id="f76d3-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="f76d3-173">Щелкните **вкладку Источники.**</span><span class="sxs-lookup"><span data-stu-id="f76d3-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="f76d3-174">На странице **Хранители,** а затем выберите хранителя, который освобожден из дела.</span><span class="sxs-lookup"><span data-stu-id="f76d3-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="f76d3-175">На странице вылет нажмите кнопку **Release custodian**.</span><span class="sxs-lookup"><span data-stu-id="f76d3-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="f76d3-176">Отображается страница предупреждения, объясняя, что если удержание размещено на источнике данных, связанном с хранителями, удержание будет удалено, а любое другое удержание, связанное с другим случаем Advanced eDiscovery, будет по-прежнему применяться.</span><span class="sxs-lookup"><span data-stu-id="f76d3-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="f76d3-177">Это включает другие типы функций сохранения и хранения (например, Microsoft 365 хранения).</span><span class="sxs-lookup"><span data-stu-id="f76d3-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="f76d3-178">Нажмите **кнопку Да,** чтобы подтвердить, что вы хотите освободить хранителя.</span><span class="sxs-lookup"><span data-stu-id="f76d3-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="f76d3-179">Состояние этого пользователя на вкладке **Custodians** задано для Выпуска, а состояние **Удержания** на странице вылетов изменено на  **False**.</span><span class="sxs-lookup"><span data-stu-id="f76d3-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="f76d3-180">Хранитель может одновременно участвовать в нескольких судебных делах.</span><span class="sxs-lookup"><span data-stu-id="f76d3-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="f76d3-181">Когда хранитель освобожден из дела, на хранение и уведомления по другим вопросам не будет влиять.</span><span class="sxs-lookup"><span data-stu-id="f76d3-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="f76d3-182">Хранители с массовым изменением</span><span class="sxs-lookup"><span data-stu-id="f76d3-182">Bulk-edit custodians</span></span>

<span data-ttu-id="f76d3-183">Можно использовать основной редактор для редактирования нескольких хранителей в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="f76d3-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="f76d3-184">Для этого просто выберите двух или более хранителей на вкладке **Custodians,** чтобы отобразить основной редактор, а затем нажмите одну из задач.</span><span class="sxs-lookup"><span data-stu-id="f76d3-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Страница Flyout для редактирования параметров нескольких хранителей](../media/AeDBulkEditCustodians.png)
