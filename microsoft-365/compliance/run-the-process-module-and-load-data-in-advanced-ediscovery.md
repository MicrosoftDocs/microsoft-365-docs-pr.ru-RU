---
title: Запуск модуля process и загрузка данных в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: Узнайте, как использовать Центр соответствия требованиям безопасности для доступа &amp; к Advanced eDiscovery и запуска модуля процесса для дела.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64172c0198418dbb0ba4d01a5adbd5aaef4c3a3b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662844"
---
# <a name="run-the-process-module-and-load-data-in-advanced-ediscovery-classic"></a><span data-ttu-id="f7f4d-103">Запуск модуля process и загрузка данных в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="f7f4d-103">Run the Process module and load data in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="f7f4d-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f7f4d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f7f4d-106">В этом разделе описаны функции модуля advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="f7f4d-107">Помимо данных файлов, метаданные, такие как тип файла, расширение, расположение или путь, дата и время создания, автор, хранитеель и тема, можно загрузить в Advanced eDiscovery и сохранить для каждого случая.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="f7f4d-108">Некоторые метаданные вычисляются с помощью Advanced eDiscovery, например при загрузке файлов native.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="f7f4d-109">Advanced eDiscovery предоставляет значения системных метаданных, например почти дубликаты групп или оценки релевантности.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="f7f4d-110">Администратор может добавить другие метаданные, например примечания к файлам.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="f7f4d-111">Запущенный процесс</span><span class="sxs-lookup"><span data-stu-id="f7f4d-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="f7f4d-112">Пакетные номера назначены файлу во время процесса, чтобы разрешить отслеживание файлов.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="f7f4d-113">Номер пакета также позволяет идентификации пакетов процессов для параметров повторной обработки.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="f7f4d-114">Для фильтрации по номерам пакетов и сеансам доступны дополнительные фильтры.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="f7f4d-115">Чтобы запустить процесс, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="f7f4d-116">[Открытие службы безопасности &amp; Центр соответствия требованиям.](go-to-the-securitycompliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="f7f4d-116">[Open the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="f7f4d-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="f7f4d-118">В Advanced eDiscovery выберите соответствующий случай  на странице "Дела" и нажмите кнопку **"Перейти к делу".**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="f7f4d-119">В **процессе** \>  \> **подготовки программы** установки выберите контейнер из списка доступных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![Щелкните "Процесс", чтобы добавить результаты поиска в дело](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="f7f4d-121">Нажмите **кнопку "Дополнительные параметры"...** Если вы хотите добавить контейнер в качестве файлов с замещями или в качестве предварительно помеченных файлов.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="f7f4d-122">Используйте файлы с заданными данными, чтобы ускорить обучение по вопросам с низкой насыщенностью (как правило, 2 % или меньше).</span><span class="sxs-lookup"><span data-stu-id="f7f4d-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="f7f4d-123">Для файлов с заданными значениями рекомендуется выбирать различные файлы и обрабатывать около 20–50 семечелей на проблему (слишком большое количество файлов с заместью релевантности может привести к перекосу результатов релевантности).</span><span class="sxs-lookup"><span data-stu-id="f7f4d-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="f7f4d-124">Файлы с заданными файлами должны быть просмотрены тем же человеком, который обучает проблему.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="f7f4d-125">Используйте предварительно помеченные файлы для автоматизации обучения релевантности.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="f7f4d-126">Необходимо пометить по крайней мере 1500 файлов и сохранить пропорции релевантных файлов так же, как и в коллекции, добавленной к релевантности.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="f7f4d-127">Эти файлы должны быть помечены вручную, и вы должны быть уверены в качестве тегов.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![Снимок экрана: страница "Дополнительные параметры" для обработки пакетных файлов](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="f7f4d-129">В разделе **"Seed":**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="f7f4d-130">Выберите **"Пометить как seed files",** чтобы пометить контейнер как файлы для хранения.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="f7f4d-131">Вам также необходимо назначить их для каждого вопроса в выпадаемом ок **недоуме.**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="f7f4d-132">Выберите **"Релевантно"** или "Не **релевантно"** в **выпадаемом теге.**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f7f4d-133">После того как вы настроили файлы как **seed,** вы не сможете пометить их как **предварительно помеченные.**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="f7f4d-134">В разделе **предварительно помеченных файлов:**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="f7f4d-135">Выберите **Mark как предварительно помеченные файлы,** чтобы пометить контейнер как предварительно помеченные файлы.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="f7f4d-136">Вам также необходимо назначить их для каждого вопроса из **выпадаемого переназначаемого** выпуска "For issue".</span><span class="sxs-lookup"><span data-stu-id="f7f4d-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="f7f4d-137">Выберите **"Релевантно"** или "Не **релевантно"** в **выпадаемом теге.**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f7f4d-138">После того как вы настроили файлы как **предварительно помеченные,** вы не сможете пометить их как **seed**.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="f7f4d-139">В разделе **тегов электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-139">In the **Email tagging** section.</span></span> <span data-ttu-id="f7f4d-140">установите, какая часть обработанного сообщения электронной почты будет помечена как "Seed" или "Pre-tagged".</span><span class="sxs-lookup"><span data-stu-id="f7f4d-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="f7f4d-141">Для начала щелкните **"Процесс".**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-141">To begin, click **Process**.</span></span> <span data-ttu-id="f7f4d-142">По завершению отображаются результаты процесса.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="f7f4d-143">(Необязательно) Если вам нужно назначить источники данных определенному хранителю, вы можете добавить и изменить имена хранителей в средстве **Custodians** Manage и назначить хранителей в \>  **custodians** \> **Assign.**</span><span class="sxs-lookup"><span data-stu-id="f7f4d-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="f7f4d-144">При добавлении в дело можно повторно обработать.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-144">If you add to the case, then you can process again.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f7f4d-145">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="f7f4d-145">Related topics</span></span>

[<span data-ttu-id="f7f4d-146">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="f7f4d-146">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f7f4d-147">Просмотр результатов модуля процесса</span><span class="sxs-lookup"><span data-stu-id="f7f4d-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

