---
title: Управление custodians в расширенном случае обнаружения электронных данных
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
description: Узнайте, как просмотреть сведения, изменить и массово изменить список custodians в расширенном случае обнаружения электронных данных.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95b7a7dbec5656a1ac0692ed465eb5a99d7ca11a
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024809"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="a8ed0-103">Управление custodians в расширенном случае обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="a8ed0-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="a8ed0-104">Страница custodians на вкладке **источники** в расширенном случае обнаружения электронных данных содержит список всех custodians, которые были добавлены в обращение.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="a8ed0-105">Когда вы добавите custodians в дело, сведения о каждом из них автоматически собираются из Azure Active Directory и доступны для просмотра в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Управление custodians](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="a8ed0-107">Просмотр сведений о хранитель</span><span class="sxs-lookup"><span data-stu-id="a8ed0-107">View custodian details</span></span>

<span data-ttu-id="a8ed0-108">Чтобы просмотреть сведения о хранитель, щелкните хранитель в списке на вкладке **custodians** . Откроется всплывающая страница со следующими сведениями о хранитель:</span><span class="sxs-lookup"><span data-stu-id="a8ed0-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="a8ed0-109">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="a8ed0-109">Contact information</span></span>

  - <span data-ttu-id="a8ed0-110">**Display Name** — имя, отображаемое в адресной книге для хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="a8ed0-111">Обычно это сочетание имени, инициала и фамилии хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="a8ed0-112">**Mail/SMTP** — основной SMTP-адрес для хранитель, например brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="a8ed0-113">Кроме того, приводятся имя участника-пользователя хранитель (UPN).</span><span class="sxs-lookup"><span data-stu-id="a8ed0-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="a8ed0-114">**Title** — название задания хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="a8ed0-115">**Department** — имя отдела, в котором работает хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="a8ed0-116">**Руководитель** — менеджер хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="a8ed0-117">Указанный руководитель получит все сообщения о эскалации для этого хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="a8ed0-118">Сведения о расположении</span><span class="sxs-lookup"><span data-stu-id="a8ed0-118">Location information</span></span>

  - <span data-ttu-id="a8ed0-119">**City** — город, в котором располагается хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="a8ed0-120">**State** — область или край в адресе хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="a8ed0-121">**Страна** или регион — страна или регион, где находится хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="a8ed0-122">**Office** — расположение комнаты бизнеса в хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="a8ed0-123">Сведения о делах</span><span class="sxs-lookup"><span data-stu-id="a8ed0-123">Case information</span></span>

  - <span data-ttu-id="a8ed0-124">**Состояние удержания** — указывает, был ли хранитель включен в удержание.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="a8ed0-125">**Состояние связи**: указывает, было ли хранитель было создано уведомление об удержании.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="a8ed0-126">Если хранитель было создано уведомление, это значение этого свойства **публикуется**.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="a8ed0-127">Если хранитель не выдал уведомление, состояние **отменяется**.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="a8ed0-128">**Status (состояние** ) — состояние хранитель в случае.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="a8ed0-129">Состояние **Active** указывает на то, что хранитель является частью дела.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="a8ed0-130">Если хранитель выпускается из случая, состояние изменится на " **выпущен**".</span><span class="sxs-lookup"><span data-stu-id="a8ed0-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="a8ed0-131">Источники данных и сведения об индексировании</span><span class="sxs-lookup"><span data-stu-id="a8ed0-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="a8ed0-132">**Источники данных** — отображает количество и тип источников данных (почтовые ящики, сайты и команды), которые связаны с хранитель и являются частью этого случая.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="a8ed0-133">**Обновлять время индексирования** — указывает время и дату последнего запуска задания расширенного индексирования.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="a8ed0-134">Это свойство также указывает, когда в данный момент выполняется расширенный процесс индексирования.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="a8ed0-135">Изменение хранитель</span><span class="sxs-lookup"><span data-stu-id="a8ed0-135">Edit a custodian</span></span>

<span data-ttu-id="a8ed0-136">По мере последовательного выполнения можно обнаружить, что могут быть дополнительные источники данных, относящиеся к определенному хранитель & вашем случае.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="a8ed0-137">В других сценариях может потребоваться удалить некоторые источники данных, которые были проверены и были признаны несвязанными.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="a8ed0-138">Обновление источников данных, связанных с хранитель:</span><span class="sxs-lookup"><span data-stu-id="a8ed0-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="a8ed0-139">Перейдите на **Обнаружение электронных данных > Advanced eDiscovery** и откройте обращение.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="a8ed0-140">Перейдите на вкладку **источники** .</span><span class="sxs-lookup"><span data-stu-id="a8ed0-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="a8ed0-141">На странице **custodians** выберите хранитель в списке и нажмите кнопку **изменить** на всплывающей странице.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Изменение источников данных](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="a8ed0-143">Нажмите кнопку **Выбор источников данных** , чтобы изменить параметры почтового ящика Exchange и учетной записи OneDrive хранитель, и выберите пункт **выбрать источники данных**.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="a8ed0-144">Перейдите на вкладку **выберите Дополнительные источники данных** , чтобы добавить или удалить Teams, SharePoint или почтовые ящики Exchange, связанные с хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="a8ed0-145">Для получения дополнительных сведений об источниках данных, связанных с хранитель, обратитесь к разделу "шаг 3: связывание дополнительных источников данных с хранитель" в разделе [Add custodians to Case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span><span class="sxs-lookup"><span data-stu-id="a8ed0-145">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="a8ed0-146">Нажмите кнопку **поместить кустодиал удержания** , чтобы включить или отключить удержание для хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="a8ed0-147">Повторное индексирование данных хранитель</span><span class="sxs-lookup"><span data-stu-id="a8ed0-147">Re-index custodian data</span></span>

<span data-ttu-id="a8ed0-148">В большинстве рабочих процессов обнаружения электронных данных для юридического расследования подмножество данных хранитель ищется после добавления хранитель в юридическое обращение.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="a8ed0-149">Из-за очень большого размера файлов или возможных повреждений данных некоторые элементы в источниках данных, связанных с хранитель, могут быть частично индексированы.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="a8ed0-150">С помощью [расширенной функции индексирования](indexing-custodian-data.md) расширенного обнаружения электронных данных большинство частично индексированных элементов можно автоматически исправить путем повторного индексирования этих элементов по запросу.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="a8ed0-151">Когда хранитель добавляется к случаю, данные, расположенные в источниках данных, связанных с хранитель, автоматически переиндексируются автоматически (с помощью расширенного процесса индексирования).</span><span class="sxs-lookup"><span data-stu-id="a8ed0-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="a8ed0-152">Это означает, что вы можете оставить данные на месте, а не загружать и исправлять их, а затем искать их в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="a8ed0-153">Однако во время жизненного цикла для юридического случая новые источники данных могут быть связаны с хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="a8ed0-154">В этом случае вы можете повторно индексировать данные хранитель, повторно выполнив расширенный процесс индексирования, чтобы исправить все элементы с частичным индексированием и обновить индекс для данных хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="a8ed0-155">Чтобы запустить процесс повторного индексирования для частично индексированных элементов:</span><span class="sxs-lookup"><span data-stu-id="a8ed0-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="a8ed0-156">Перейдите на **Обнаружение электронных данных > Advanced eDiscovery** и откройте обращение.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="a8ed0-157">Перейдите на вкладку **источники** .</span><span class="sxs-lookup"><span data-stu-id="a8ed0-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="a8ed0-158">На странице **custodians** выберите хранитель, данные которого необходимо переиндексировать.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="a8ed0-159">На всплывающей странице щелкните **обновить индекс**.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="a8ed0-160">Отображается диалоговое окно с сообщением о том, что было создано задание индексирования.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="a8ed0-161">Повторное индексирование данных хранитель — это длительный процесс; соответствующее созданное задание называется **повторная индексация данных хранитель**.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="a8ed0-162">Отслеживать ход выполнения можно на вкладке " **задания** " или на вкладке " **custodians** ", отслеживая состояние в столбце " **состояние задания индексирования** ".</span><span class="sxs-lookup"><span data-stu-id="a8ed0-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="a8ed0-163">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-163">For more information, see:</span></span>

- [<span data-ttu-id="a8ed0-164">Работа с ошибками обработки</span><span class="sxs-lookup"><span data-stu-id="a8ed0-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="a8ed0-165">Управление заданиями</span><span class="sxs-lookup"><span data-stu-id="a8ed0-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="a8ed0-166">Выпуск хранитель из обращения</span><span class="sxs-lookup"><span data-stu-id="a8ed0-166">Release a custodian from a case</span></span>

<span data-ttu-id="a8ed0-167">Хранитель размещается в ситуациях, когда обращение закрывается, хранитель больше не считается обязательством по сохранению содержимого для случая или когда хранитель считается нерелевантным для случая.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="a8ed0-168">Если вы выпустите хранитель после публикации уведомления об удержании, в Хранитель будет отправлено уведомление о выпуске.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="a8ed0-169">Кроме того, удаляются все удержания, размещенные в источниках данных, связанных с хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="a8ed0-170">Если хранитель размещается на *удержании в автоматическом режиме*, где они не получали уведомления о юридическом удержании, уведомление о выпуске не будет отправлено, но все удержания, размещенные на источниках данных, связанных с этим хранитель, удаляются.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="a8ed0-171">Чтобы освободить хранитель, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-171">To release a custodian:</span></span> 

1. <span data-ttu-id="a8ed0-172">Перейдите на **Обнаружение электронных данных > Advanced eDiscovery** и откройте обращение.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="a8ed0-173">Перейдите на вкладку **источники** .</span><span class="sxs-lookup"><span data-stu-id="a8ed0-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="a8ed0-174">На странице **custodians** , а затем выберите хранитель, который выпускается из этого случая.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="a8ed0-175">На всплывающей странице нажмите кнопку **Release хранитель**.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="a8ed0-176">Будет выведена страница с предупреждением о том, что если удержание помещается в источник данных, связанный с хранитель, то удержание будет удалено и все остальные удержания, связанные с другими дополнительными случаями обнаружения электронных данных, будут по-прежнему применяться.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="a8ed0-177">Включает другие типы сохранения и хранения (например, политика хранения Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="a8ed0-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="a8ed0-178">Нажмите кнопку **Да** , чтобы подтвердить, что вы хотите освободить хранитель.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="a8ed0-179">Для этого пользователя на вкладке **custodians** задано значение " **Пуск** ", а **состояние удержания** для всплывающей страницы изменяется на " **false**".</span><span class="sxs-lookup"><span data-stu-id="a8ed0-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="a8ed0-180">Хранитель может быть одновременно задействована в нескольких юридических случаях.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="a8ed0-181">При отпускании хранитель из случая удержания и уведомления на другие вопросы не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="a8ed0-182">Массовое изменение custodians</span><span class="sxs-lookup"><span data-stu-id="a8ed0-182">Bulk-edit custodians</span></span>

<span data-ttu-id="a8ed0-183">Можно использовать пакетный редактор для одновременного редактирования нескольких custodians.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="a8ed0-184">Для этого достаточно выбрать два или более custodians на вкладке **custodians** , чтобы отобразить Пакетный редактор, а затем выбрать одну из задач.</span><span class="sxs-lookup"><span data-stu-id="a8ed0-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Всплывающая страница для изменения параметров нескольких custodians](../media/AeDBulkEditCustodians.png)
