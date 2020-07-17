---
title: Добавление источников данных, не относящихся к кустодиал, к расширенному варианту обнаружения электронных данных
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
description: Вы можете добавить источники данных, не относящиеся к кустодиал, в расширенное дело обнаружения электронных данных и разместить удержание на источнике данных. Источники данных, не относящиеся к кустодиал, переиндексируются, поэтому весь контент, который был признан частичным индексированием, переобрабатывается, чтобы сделать его полным и быстрым для поиска.
ms.openlocfilehash: 2009a8cc82dc9407e9871409e85cdcd321ea9bb0
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024749"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="966e3-104">Добавление источников данных, не относящихся к кустодиал, к расширенному варианту обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="966e3-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="966e3-105">В расширенных случаях обнаружения электронных данных это не всегда соответствует требованиям для связи источника данных Microsoft 365 с хранитель в случае.</span><span class="sxs-lookup"><span data-stu-id="966e3-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="966e3-106">Но все равно может потребоваться связать эти данные с обращением, чтобы выполнить его поиск, добавить в набор проверки и проверить его.</span><span class="sxs-lookup"><span data-stu-id="966e3-106">But you may still need to associate that data with a case so that you search it, add it to review set, and review it.</span></span> <span data-ttu-id="966e3-107">Новая функция, называемая *некустодиалными источниками данных* , позволяет добавлять данные к случаю без необходимости связывать эти данные с хранитель.</span><span class="sxs-lookup"><span data-stu-id="966e3-107">The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian.</span></span> <span data-ttu-id="966e3-108">Она также применяет те же расширенные функции обнаружения электронных данных для кустодиал данных, которые доступны для данных, связанных с хранитель.</span><span class="sxs-lookup"><span data-stu-id="966e3-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="966e3-109">Две наиболее полезная функции, которые можно применить к данным, не относящимся к кустодиал, помещают их на удержание и обработку с помощью [расширенной индексации](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="966e3-109">Two of the most useful features that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="966e3-110">Добавление источника данных, отличного от кустодиал</span><span class="sxs-lookup"><span data-stu-id="966e3-110">Add a non-custodial data source</span></span>

<span data-ttu-id="966e3-111">Выполните следующие действия, чтобы добавить источники данных, не относящиеся к кустодиал, и управлять ими в расширенном случае обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="966e3-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="966e3-112">На домашней странице **Advanced eDiscovery** щелкните обращение, в которое нужно добавить данные.</span><span class="sxs-lookup"><span data-stu-id="966e3-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="966e3-113">На странице **источники** перейдите на вкладку **расположения данных** и нажмите кнопку **Добавить расположение данных**.</span><span class="sxs-lookup"><span data-stu-id="966e3-113">On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.</span></span>

3. <span data-ttu-id="966e3-114">Нажмите кнопку **Добавить расположение данных** и выберите источники данных, которые нужно добавить в обращение.</span><span class="sxs-lookup"><span data-stu-id="966e3-114">Click **Add data location** and choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="966e3-115">Вы можете добавить несколько почтовых ящиков и сайтов.</span><span class="sxs-lookup"><span data-stu-id="966e3-115">You can add multiple mailboxes and sites.</span></span>

4. <span data-ttu-id="966e3-116">На странице **Выбор расположений** мастера добавьте почтовые ящики или сайты (или и то, и другое) в качестве источников данных, не связанных с кустодиал, в случае.</span><span class="sxs-lookup"><span data-stu-id="966e3-116">On the **Choose locations** page in the wizard, add mailboxes or sites (or both) as non-custodial data sources to the case.</span></span>

5. <span data-ttu-id="966e3-117">После добавления источников данных нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="966e3-117">After adding the data sources, click **Next**.</span></span>

6. <span data-ttu-id="966e3-118">На странице " **место** хранения" выберите источники данных, которые необходимо включить в удержание, путем установки или отмены выбора соответствующего флажка.</span><span class="sxs-lookup"><span data-stu-id="966e3-118">On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.</span></span>

7. <span data-ttu-id="966e3-119">Проверьте выбранные варианты хранения и нажмите кнопку **послать**.</span><span class="sxs-lookup"><span data-stu-id="966e3-119">Verify the hold selections and then click **Submit**.</span></span>

   <span data-ttu-id="966e3-120">Каждый добавленный источник данных, не относящийся к кустодиал, указан на странице **Источники данных** .</span><span class="sxs-lookup"><span data-stu-id="966e3-120">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span>

   <span data-ttu-id="966e3-121">Кроме того, создается задание с именем " *переиндексация данных не кустодиал* " и отображается на вкладке " **задания** ".</span><span class="sxs-lookup"><span data-stu-id="966e3-121">Also, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="966e3-122">После создания задания расширенный процесс индексирования, запущенный в процессе инициализации и переиндексация источников данных, переиндексируются.</span><span class="sxs-lookup"><span data-stu-id="966e3-122">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="managing-the-hold-on-non-custodial-data-sources"></a><span data-ttu-id="966e3-123">Управление удержанием на источниках данных, не являющихся кустодиал</span><span class="sxs-lookup"><span data-stu-id="966e3-123">Managing the hold on non-custodial data sources</span></span>

<span data-ttu-id="966e3-124">После размещения удержания в источнике данных, отличном от кустодиал, автоматически создается политика удержания, которая содержит все источники данных, не связанные с кустодиал, для случая.</span><span class="sxs-lookup"><span data-stu-id="966e3-124">After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="966e3-125">При помещении дополнительных источников данных, не являющихся кустодиал, на удержание они добавляются в эту политику удержания.</span><span class="sxs-lookup"><span data-stu-id="966e3-125">When you place additional non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="966e3-126">На **домашней** странице примера перейдите на вкладку **удержания** .</span><span class="sxs-lookup"><span data-stu-id="966e3-126">On the **Home** page of the case, click the **Holds** tab.</span></span>

2. <span data-ttu-id="966e3-127">На странице **удержания** нажмите \*\*нкдшолд- \<GUID\> \*\*, где значение GUID уникально для этого случая.</span><span class="sxs-lookup"><span data-stu-id="966e3-127">On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

3. <span data-ttu-id="966e3-128">На всплывающей странице нажмите кнопку **изменить удержание** , чтобы просмотреть все источники данных, не относящиеся к кустодиал, которые были размещены на удержании.</span><span class="sxs-lookup"><span data-stu-id="966e3-128">On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.</span></span>

<span data-ttu-id="966e3-129">В источниках данных, не являющихся кустодиал, можно выполнять следующие задачи управления:</span><span class="sxs-lookup"><span data-stu-id="966e3-129">You can perform the following management task on non-custodial data sources:</span></span>

- <span data-ttu-id="966e3-130">Вы можете изменить удержание, чтобы создать удержание на основе запроса, которое применяется ко всем источникам данных, не связанным с кустодиал, в этом случае.</span><span class="sxs-lookup"><span data-stu-id="966e3-130">You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.</span></span>

- <span data-ttu-id="966e3-131">Вы можете отпустить источник данных, отличный от кустодиал, из удержания.</span><span class="sxs-lookup"><span data-stu-id="966e3-131">You can release a non-custodial data source from the hold.</span></span> <span data-ttu-id="966e3-132">При освобождении источника данных не удаляется источник данных, не являющийся кустодиал, из этого случая.</span><span class="sxs-lookup"><span data-stu-id="966e3-132">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="966e3-133">Он только удаляет удержание, которое было включено в источник данных.</span><span class="sxs-lookup"><span data-stu-id="966e3-133">It only removes the hold that was placed on the data source.</span></span>
