---
title: Добавление источников данных, не в отношении хранения, в дело Advanced eDiscovery
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
description: Вы можете добавить источники данных, не личные, в дело Advanced eDiscovery и наложить удержание на источник данных. Источники данных, не личные, переиндексированы, поэтому любой контент, помеченный как частично индексируемый, повторно обработать, чтобы сделать его полностью и быстро найти.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740356"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="f6f61-104">Добавление источников данных, не в отношении хранения, в дело Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f6f61-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="f6f61-105">В случаях Advanced eDiscovery оно не всегда соответствует вашим требованиям, чтобы связать источник данных Microsoft 365 с хранителями в этом случае.</span><span class="sxs-lookup"><span data-stu-id="f6f61-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="f6f61-106">Но вам все равно может потребоваться связать эти данные с делом, чтобы можно было искать в них, добавлять их в набор для проверки, а также анализировать и анализировать.</span><span class="sxs-lookup"><span data-stu-id="f6f61-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="f6f61-107">Функция в Advanced eDiscovery  называется источниками данных без хранения и позволяет добавлять данные в дело, не связывая их с хранителями.</span><span class="sxs-lookup"><span data-stu-id="f6f61-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="f6f61-108">Он также применяет те же функции Advanced eDiscovery к данным, не связанным с хранением, которые доступны для данных, связанных с хранителями.</span><span class="sxs-lookup"><span data-stu-id="f6f61-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="f6f61-109">Две наиболее полезные функции, которые можно применить к данным, не относянымся к хранителям, — поместить их на удержание и обрабатывать с помощью [функции "Расширенный индексация".](indexing-custodian-data.md)</span><span class="sxs-lookup"><span data-stu-id="f6f61-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="f6f61-110">Добавление источника данных, не влияемого на хранение</span><span class="sxs-lookup"><span data-stu-id="f6f61-110">Add a non-custodial data source</span></span>

<span data-ttu-id="f6f61-111">Выполните следующие действия, чтобы добавить источники данных, не личные, и управлять ими в случае Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f6f61-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="f6f61-112">На **домашней странице Advanced eDiscovery** щелкните дело, в которое нужно добавить данные.</span><span class="sxs-lookup"><span data-stu-id="f6f61-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="f6f61-113">Перейдите **на вкладку "Источники** данных", а затем нажмите кнопку **"Добавить расположения** данных для источника  >  **данных".**</span><span class="sxs-lookup"><span data-stu-id="f6f61-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="f6f61-114">На странице **"Новые расположения для хранения** данных" выберите источники данных, которые нужно добавить в дело.</span><span class="sxs-lookup"><span data-stu-id="f6f61-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="f6f61-115">Вы можете добавить несколько почтовых ящиков и сайтов, расширив **разделы SharePoint** или **Exchange** и нажав кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="f6f61-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Добавление сайтов SharePoint и почтовых ящиков Exchange в качестве источников данных, не входящих в хранение](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="f6f61-117">**SharePoint** — нажмите **кнопку "Изменить",** чтобы добавить сайты.</span><span class="sxs-lookup"><span data-stu-id="f6f61-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="f6f61-118">Выберите сайт в списке или вы можете найти его, введя URL-адрес сайта в панели поиска.</span><span class="sxs-lookup"><span data-stu-id="f6f61-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="f6f61-119">Выберите сайты, которые нужно добавить в качестве источников данных, не относящых к хранителям, и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="f6f61-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="f6f61-120">**Exchange** — нажмите **кнопку** "Изменить", чтобы добавить почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="f6f61-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="f6f61-121">Введите имя или псевдоним (не менее трех символов) в поле поиска почтовых ящиков или групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="f6f61-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="f6f61-122">Выберите почтовые ящики, которые нужно добавить в качестве источников данных, не входящих в хранители, и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="f6f61-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f6f61-123">Разделы **SharePoint** и **Exchange** можно использовать для добавления сайтов и почтовых ящиков, связанных с группой или группой Yammer, в качестве источников данных, не связанных с хранением.</span><span class="sxs-lookup"><span data-stu-id="f6f61-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="f6f61-124">Необходимо отдельно добавить почтовый ящик и сайт, связанные с командой или группой Yammer.</span><span class="sxs-lookup"><span data-stu-id="f6f61-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="f6f61-125">После добавления источников данных, не в том числе для хранения, вы можете разместить эти расположения на удержании или нет.</span><span class="sxs-lookup"><span data-stu-id="f6f61-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="f6f61-126">Чтобы на удержание разместить его, выберите или отбрасыйте его рядом с источником данных. </span><span class="sxs-lookup"><span data-stu-id="f6f61-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="f6f61-127">Нажмите **кнопку** "Добавить" в нижней части страницы "Новые расположения не для хранения данных", чтобы добавить источники данных в дело. </span><span class="sxs-lookup"><span data-stu-id="f6f61-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="f6f61-128">Каждый добавленный источник данных, не относя близкий к хранителям, указан на **странице "Источники** данных".</span><span class="sxs-lookup"><span data-stu-id="f6f61-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="f6f61-129">Источники данных, не личные, идентифицированы значением расположения **данных** в **столбце "Тип источника".**</span><span class="sxs-lookup"><span data-stu-id="f6f61-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Источники данных, не личные, на вкладке "Источники данных"](../media/NonCustodialDataSources2.png)

<span data-ttu-id="f6f61-131">После добавления в дело источников данных, не в отношении хранения, создается и отображается на вкладке "Задания" дела задание с именем *"Переиндексовать* недедексные данные". </span><span class="sxs-lookup"><span data-stu-id="f6f61-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="f6f61-132">После создания задания инициален расширенный процесс индексации и переиндексация источников данных.</span><span class="sxs-lookup"><span data-stu-id="f6f61-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="f6f61-133">Управление удержанием для источников данных, не отправляемых в хранение</span><span class="sxs-lookup"><span data-stu-id="f6f61-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="f6f61-134">После того как вы поместите удержание на источник данных, не содержащий хранение, автоматически создается политика удержания, которая содержит источники данных, не личные для дела.</span><span class="sxs-lookup"><span data-stu-id="f6f61-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="f6f61-135">При удержании других источников данных, не в отношении хранения, они добавляются в эту политику удержания.</span><span class="sxs-lookup"><span data-stu-id="f6f61-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="f6f61-136">Откройте дело Advanced eDiscovery и выберите вкладку **"Удержание".**</span><span class="sxs-lookup"><span data-stu-id="f6f61-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="f6f61-137">Щелкните **NCDSHold- \<GUID\>**, где значение GUID уникально для дела.</span><span class="sxs-lookup"><span data-stu-id="f6f61-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="f6f61-138">На отображаемой странице отображаются сведения и статистика об источниках данных, не в том виде, в которые они находятся на удержании.</span><span class="sxs-lookup"><span data-stu-id="f6f61-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![На flyout page for non-custodial data sources hold displays statistics](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="f6f61-140">Нажмите **кнопку "Изменить** удержание", чтобы просмотреть источники данных, не вложенные в хранение, и выполнить следующие задачи управления:</span><span class="sxs-lookup"><span data-stu-id="f6f61-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="f6f61-141">На странице **"Расположения"** можно освободить источник данных, не относяющийся к хранителям, удалив его из удержания.</span><span class="sxs-lookup"><span data-stu-id="f6f61-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="f6f61-142">Освобождение источника данных не удаляет источник данных, не относяющийся к хранителям, из дела.</span><span class="sxs-lookup"><span data-stu-id="f6f61-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="f6f61-143">Он удаляет только удержание, которое было помещено на источник данных.</span><span class="sxs-lookup"><span data-stu-id="f6f61-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="f6f61-144">На странице **"Запрос"** можно изменить удержание, чтобы создать удержание на основе запроса, которое применяется во всех источниках данных, не вложенных в хранение, в этом случае.</span><span class="sxs-lookup"><span data-stu-id="f6f61-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
