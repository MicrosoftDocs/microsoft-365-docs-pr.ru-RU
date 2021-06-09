---
title: Добавление неконтлиционных источников данных в Advanced eDiscovery случае
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
description: Вы можете добавить источники данных без хранения в Advanced eDiscovery и разместить удержание на источнике данных. Источники данных, которые не связаны с хранением, реиндексированы, поэтому любое содержимое, отмеченное как частично индексируемый, повторно, чтобы сделать его полностью и быстро найти.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740356"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="b83ff-104">Добавление неконтлиционных источников данных в Advanced eDiscovery случае</span><span class="sxs-lookup"><span data-stu-id="b83ff-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="b83ff-105">В Advanced eDiscovery случаях не всегда необходимо связать источник Microsoft 365 данных с хранителями в данном случае.</span><span class="sxs-lookup"><span data-stu-id="b83ff-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="b83ff-106">Но вам все равно может потребоваться связать эти данные с случаем, чтобы вы могли искать их, добавлять их в набор отзывов, анализировать и анализировать их.</span><span class="sxs-lookup"><span data-stu-id="b83ff-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="b83ff-107">Функция в Advanced eDiscovery называется источниками данных без хранения и позволяет добавлять данные в дело, не связывая их с хранителями. </span><span class="sxs-lookup"><span data-stu-id="b83ff-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="b83ff-108">Он также применяет те же Advanced eDiscovery к данным, не связанным с хранением, которые доступны для данных, связанных с хранителями.</span><span class="sxs-lookup"><span data-stu-id="b83ff-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="b83ff-109">Две наиболее полезные функции, которые можно применить к данным, не относя к данным, не отозвав данные, — это их удержание и обработка с помощью [индексации Advanced.](indexing-custodian-data.md)</span><span class="sxs-lookup"><span data-stu-id="b83ff-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="b83ff-110">Добавление источника данных без хранения</span><span class="sxs-lookup"><span data-stu-id="b83ff-110">Add a non-custodial data source</span></span>

<span data-ttu-id="b83ff-111">Выполните следующие действия, чтобы добавить и управлять источниками данных, не в отношении хранения, в Advanced eDiscovery случае.</span><span class="sxs-lookup"><span data-stu-id="b83ff-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="b83ff-112">На **Advanced eDiscovery** на домашней странице щелкните случай, в который необходимо добавить данные.</span><span class="sxs-lookup"><span data-stu-id="b83ff-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="b83ff-113">Щелкните **вкладку Источники** данных и нажмите **кнопку Добавить источник данных** Добавить расположения  >  **данных.**</span><span class="sxs-lookup"><span data-stu-id="b83ff-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="b83ff-114">На странице "Новые расположения данных, не **отбираемой** для хранения", выберите источники данных, которые необходимо добавить в дело.</span><span class="sxs-lookup"><span data-stu-id="b83ff-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="b83ff-115">Вы можете добавить несколько почтовых ящиков  и сайтов, расширив разделы SharePoint **или Exchange** и нажав **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b83ff-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Добавление SharePoint сайтов и Exchange почтовых ящиков в качестве источников данных, не входящих в опеку](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="b83ff-117">**SharePoint** нажмите **кнопку Изменить,** чтобы добавить сайты.</span><span class="sxs-lookup"><span data-stu-id="b83ff-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="b83ff-118">Выберите сайт в списке или вы можете найти сайт, введя URL-адрес сайта в панели поиска.</span><span class="sxs-lookup"><span data-stu-id="b83ff-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="b83ff-119">Выберите сайты, которые вы хотите добавить в качестве источников данных, не в качестве хранителя, и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b83ff-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="b83ff-120">**Exchange** нажмите **кнопку Изменить,** чтобы добавить почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="b83ff-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="b83ff-121">Введите имя или псевдоним (не менее трех символов) в поле поиска для почтовых ящиков или групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="b83ff-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="b83ff-122">Выберите почтовые ящики, которые необходимо добавить в качестве источников данных, не входящих в опеку, и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b83ff-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b83ff-123">Разделы SharePoint  **и Exchange** для добавления сайтов и почтовых ящиков, связанных с группой или группой Yammer, в качестве источников данных, не связанных с хранением.</span><span class="sxs-lookup"><span data-stu-id="b83ff-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="b83ff-124">Необходимо отдельно добавить почтовый ящик и сайт, связанный с группой или Yammer группой.</span><span class="sxs-lookup"><span data-stu-id="b83ff-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="b83ff-125">После добавления источников данных, не вво время хранения, у вас есть возможность разместить эти расположения на удержание или нет.</span><span class="sxs-lookup"><span data-stu-id="b83ff-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="b83ff-126">Выберите или отклонйте контрольный ящик **Hold** рядом с источником данных, чтобы разместить его на удержание.</span><span class="sxs-lookup"><span data-stu-id="b83ff-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="b83ff-127">Нажмите **кнопку** Добавить в нижней части страницы **вылетных** данных, не относящемся к местам хранения, чтобы добавить в дело источники данных.</span><span class="sxs-lookup"><span data-stu-id="b83ff-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="b83ff-128">Каждый добавленный источник данных, не в виде хранения, перечислены на странице **Источники** данных.</span><span class="sxs-lookup"><span data-stu-id="b83ff-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="b83ff-129">Источники данных без хранения идентифицированы по значению **расположение данных** в столбце **типа Source.**</span><span class="sxs-lookup"><span data-stu-id="b83ff-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Неконтлиционные источники данных на вкладке Источники данных](../media/NonCustodialDataSources2.png)

<span data-ttu-id="b83ff-131">После добавления в дело источников данных, не в отношении хранения, создается и отображается задание с именем *Reindexing* без хранения данных на вкладке **Jobs** в этом случае.</span><span class="sxs-lookup"><span data-stu-id="b83ff-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="b83ff-132">После создания задания начался процесс предварительной индексации и переиндексация источников данных.</span><span class="sxs-lookup"><span data-stu-id="b83ff-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="b83ff-133">Управление удержанием для источников данных, не отправляемых в хранение</span><span class="sxs-lookup"><span data-stu-id="b83ff-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="b83ff-134">После того, как вы поместите удержание на источник данных, не содержащийся в опеке, автоматически создается политика удержания, содержаная источники данных, не содержаные для дела.</span><span class="sxs-lookup"><span data-stu-id="b83ff-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="b83ff-135">При удержании других источников данных, не в отношении хранения, они добавляются в эту политику хранения.</span><span class="sxs-lookup"><span data-stu-id="b83ff-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="b83ff-136">Откройте Advanced eDiscovery и выберите вкладку  Удержание.</span><span class="sxs-lookup"><span data-stu-id="b83ff-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="b83ff-137">Щелкните **NCDSHold-, \<GUID\>** где значение GUID является уникальным для этого случая.</span><span class="sxs-lookup"><span data-stu-id="b83ff-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="b83ff-138">На странице вылетов отображаются сведения и статистические данные об источниках данных, которые не находятся на удержании.</span><span class="sxs-lookup"><span data-stu-id="b83ff-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![На странице вылетов для источников данных, не относяхся к хранителям, отображаются статистические данные](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="b83ff-140">Нажмите **кнопку Изменить** удержание, чтобы просмотреть источники данных, не вложенные в хранение, и выполнить следующие задачи управления:</span><span class="sxs-lookup"><span data-stu-id="b83ff-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="b83ff-141">На странице **Расположения** можно освободить источник данных без хранения, удалив его из удержания.</span><span class="sxs-lookup"><span data-stu-id="b83ff-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="b83ff-142">Освобождение источника данных не удаляет источник данных, не отбирающий данные из дела.</span><span class="sxs-lookup"><span data-stu-id="b83ff-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="b83ff-143">Он удаляет только удержание, которое было размещено на источнике данных.</span><span class="sxs-lookup"><span data-stu-id="b83ff-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="b83ff-144">На странице **Запрос** можно изменить удержание, чтобы создать удержание на основе запроса, которое применяется во всех источниках данных, не вложенных в хранение.</span><span class="sxs-lookup"><span data-stu-id="b83ff-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
