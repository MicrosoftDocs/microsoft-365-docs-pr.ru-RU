---
title: Подготовка CSV-файла для поиска контента по списку идентификаторов
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Используйте CSV-файлы из существующего поиска контента, чтобы создать поиск списка ИДЕНТИФИКАТОРов, который возвращает определенные сообщения электронной почты.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817978"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="c55dc-103">Подготовка CSV-файла для поиска контента по списку идентификаторов</span><span class="sxs-lookup"><span data-stu-id="c55dc-103">Prepare a CSV file for an ID list Content Search</span></span>

<span data-ttu-id="c55dc-104">Вы можете выполнять поиск определенных сообщений электронной почты и других элементов почтовых ящиков с помощью списка идентификаторов Exchange.</span><span class="sxs-lookup"><span data-stu-id="c55dc-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="c55dc-105">Чтобы создать запрос на поиск списка ИДЕНТИФИКАТОРов (формально называется целевой поиском), необходимо предоставить файл данных с разделителями-запятыми (CSV), который определяет конкретные элементы почтового ящика для поиска.</span><span class="sxs-lookup"><span data-stu-id="c55dc-105">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="c55dc-106">Для этого CSV-файла используется **Results.csv** файл или **неиндексируемый Items.csv** файл, который включается при экспорте результатов поиска контента или экспорте отчета о поиске контента из и существующего поиска контента.</span><span class="sxs-lookup"><span data-stu-id="c55dc-106">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="c55dc-107">Затем вы редактируете один из этих файлов, чтобы указать конкретные искомые элементы, а затем создайте новый список ИДЕНТИФИКАТОРов и отправит CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="c55dc-107">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span>

<span data-ttu-id="c55dc-108">Ниже приведен краткий обзор процесса создания поиска списка ИДЕНТИФИКАТОРов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-108">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="c55dc-109">Создание и запуск нового или интерактивного поиска контента в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c55dc-109">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="c55dc-110">Экспорт результатов поиска контента или экспорт отчета о поиске контента.</span><span class="sxs-lookup"><span data-stu-id="c55dc-110">Export the content search results or export the content search report.</span></span> <span data-ttu-id="c55dc-111">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="c55dc-111">For more information, see:</span></span>

    - [<span data-ttu-id="c55dc-112">Экспорт результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="c55dc-112">Export Content Search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="c55dc-113">Экспорт отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="c55dc-113">Export a Content Search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="c55dc-114">Измените **Results.csv** файл или **неиндексируемый Items.csv** и определите элементы почтового ящика, которые необходимо включить в поиск списка идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-114">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="c55dc-115">В этой [статье приведены инструкции](#prepare-the-csv-file-for-an-id-list-search) по подготовке CSV-файла для поиска в списке идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-115">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="c55dc-116">Создайте новый поисковый список ИДЕНТИФИКАТОРов (ознакомьтесь с [инструкциями](#create-an-id-list-search)) и передайте подготовленный CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="c55dc-116">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="c55dc-117">Созданный запрос поиска будет искать только элементы, выбранные в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="c55dc-117">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="c55dc-118">Поиск в списке ИДЕНТИФИКАТОРов поддерживается только для элементов почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c55dc-118">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="c55dc-119">Поиск документов SharePoint и OneDrive в поиске списка ИДЕНТИФИКАТОРов невозможен.</span><span class="sxs-lookup"><span data-stu-id="c55dc-119">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

 <span data-ttu-id="c55dc-120">**Зачем создавать Поиск списка ИДЕНТИФИКАТОРов?**</span><span class="sxs-lookup"><span data-stu-id="c55dc-120">**Why create an ID list search?**</span></span> <span data-ttu-id="c55dc-121">Если вы не можете определить, отвечает ли элемент на запрос обнаружения электронных данных на основе метаданных в **Results.csv** или **неиндексируемых Items.csv** файлах, можно использовать поиск списка идентификаторов для поиска, предварительного просмотра и экспорта этого элемента, чтобы определить, отвечает ли он на обращение, которое вы изучаете.</span><span class="sxs-lookup"><span data-stu-id="c55dc-121">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="c55dc-122">Поиск по списку ИДЕНТИФИКАТОРов обычно используется для поиска и возврата определенного набора неиндексированных элементов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-122">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="c55dc-123">Подготовка CSV-файла для поиска списка ИДЕНТИФИКАТОРов</span><span class="sxs-lookup"><span data-stu-id="c55dc-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="c55dc-124">После экспорта результатов поиска или отчета по поиску контента можно выполнить следующие действия, чтобы подготовить CSV-файл для поиска в списке ИДЕНТИФИКАТОРов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-124">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="c55dc-125">Этот CSV-файл определяет каждый элемент в поиске списка ИДЕНТИФИКАТОРов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-125">This CSV file will identify every item in the ID list search.</span></span>

<span data-ttu-id="c55dc-126">Обратите внимание, что вы можете использовать CSV-файл из поиска, включающего сайты SharePoint и учетные записи OneDrive, но вы можете выбрать *только* элементы почтового ящика для поиска в списке идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-126">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="c55dc-127">При выборе документа в SharePoint или OneDrive при создании поиска списка ИДЕНТИФИКАТОРов CSV-файл пройдет проверку на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="c55dc-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="c55dc-128">Откройте **Results.csvный** или **неиндексируемый Items.csv** файл в Excel.</span><span class="sxs-lookup"><span data-stu-id="c55dc-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="c55dc-129">В столбце **выбранный** столбец введите **Да** в ячейке, которая соответствует элементу, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="c55dc-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="c55dc-130">Повторите этот шаг для каждого элемента, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="c55dc-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c55dc-131">При открытии CSV-файла в Excel формат данных для столбца " **идентификатор документа** " изменяется на " **Общий**".</span><span class="sxs-lookup"><span data-stu-id="c55dc-131">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="c55dc-132">Это приводит к отображению идентификатора документа для элемента в экспоненциальной нотации.</span><span class="sxs-lookup"><span data-stu-id="c55dc-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="c55dc-133">Например, идентификатор документа "481037338205" отображается как "4.81037 E + 11", поэтому необходимо выполнить следующие действия, чтобы изменить формат данных столбца **идентификаторов документов** на **Number** для восстановления правильного формата идентификатора документа.</span><span class="sxs-lookup"><span data-stu-id="c55dc-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="c55dc-134">Если этого не сделать, поиск в списке ИДЕНТИФИКАТОРов, использующий CSV-файл, завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="c55dc-134">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="c55dc-135">Щелкните правой кнопкой мыши весь столбец " **идентификатор документа** " и выберите пункт **Формат ячеек**.</span><span class="sxs-lookup"><span data-stu-id="c55dc-135">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="c55dc-136">В поле **Категория** выберите **число**.</span><span class="sxs-lookup"><span data-stu-id="c55dc-136">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="c55dc-137">Измените число десятичных разрядов на **0**и нажмите кнопку **ОК** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="c55dc-137">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="c55dc-138">Обратите внимание, что значения в столбце Идентификатор документа изменяются на числа.</span><span class="sxs-lookup"><span data-stu-id="c55dc-138">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="c55dc-139">Ниже приведен пример CSV-файла, готового к отправке для поиска контента списка ИДЕНТИФИКАТОРов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-139">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>

    ![Пример CSV-файла для целевого поиска контента](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. <span data-ttu-id="c55dc-141">Сохраните CSV-файл или используйте параметр **Сохранить как** , чтобы сохранить файл с другим именем файла.</span><span class="sxs-lookup"><span data-stu-id="c55dc-141">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="c55dc-142">В обоих случаях обязательно сохраните файл в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="c55dc-142">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="c55dc-143">Создание поискового списка ИДЕНТИФИКАТОРов</span><span class="sxs-lookup"><span data-stu-id="c55dc-143">Create an ID list search</span></span>

<span data-ttu-id="c55dc-144">Следующий шаг состоит в создании нового списка ИДЕНТИФИКАТОРов поиска контента и отсылке CSV-файла, подготовленного на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="c55dc-144">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c55dc-145">Вы должны создать список ИДЕНТИФИКАТОРов, не превышающий 2 дня после экспорта результатов или отчета из поиска контента.</span><span class="sxs-lookup"><span data-stu-id="c55dc-145">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="c55dc-146">Если результаты поиска или отчет, где экспортируется более двух дней назад, необходимо повторно экспортировать результаты или отчет, чтобы создать обновленные CSV-файлы.</span><span class="sxs-lookup"><span data-stu-id="c55dc-146">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="c55dc-147">Затем вы можете подготовить один из обновленных CSV-файлов и использовать его для создания поискового списка ИДЕНТИФИКАТОРов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-147">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="c55dc-148">В центре безопасности & соответствия требованиям **перейдите к разделу** \> **Поиск контента**.</span><span class="sxs-lookup"><span data-stu-id="c55dc-148">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>

2. <span data-ttu-id="c55dc-149">На странице **поиска** щелкните стрелку рядом с кнопкой ![ Добавить значок ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Поиск**, а затем выберите **Поиск по идентификатору**.</span><span class="sxs-lookup"><span data-stu-id="c55dc-149">On the **Search** page, click the arrow next to ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>

    ![В раскрывающемся списке создать Поиск выберите пункт Поиск по ИДЕНТИФИКАТОРу](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. <span data-ttu-id="c55dc-151">В всплывающем меню **Поиск по идентификатору** введите имя поиска (и при необходимости опишите его), а затем нажмите кнопку **Обзор** и выберите CSV-файл, подготовленный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="c55dc-151">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="c55dc-152">Microsoft 365 пытается проверить CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="c55dc-152">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="c55dc-153">Если проверка завершилась неудачно, отображается сообщение об ошибке, которое может помочь при устранении ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="c55dc-153">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="c55dc-154">CSV-файл должен быть успешно проверен для создания запроса на поиск списка ИДЕНТИФИКАТОРов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-154">The CSV file has to be successfully validated to create an ID list search.</span></span>

4. <span data-ttu-id="c55dc-155">После успешной проверки CSV-файла нажмите кнопку **Поиск** , чтобы создать запрос на поиск списка идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-155">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="c55dc-156">Ниже приведен пример оценочных результатов поиска и запроса, созданного для поиска в списке ИДЕНТИФИКАТОРов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-156">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>

    ![Запрос поиска для целевого поиска контента в области сведений](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    <span data-ttu-id="c55dc-158">Обратите внимание, что количество оцененных элементов, отображаемых в статистике для поиска ИДЕНТИФИКАТОРов, должно быть равно количеству элементов, выбранных в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="c55dc-158">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

5. <span data-ttu-id="c55dc-159">Предварительный просмотр или экспорт элементов, возвращенных поиском списка ИДЕНТИФИКАТОРов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-159">Preview or export the items returned by the ID list search.</span></span>

> [!NOTE]
> <span data-ttu-id="c55dc-160">Если вы перемещаете почтовый ящик после создания поискового списка ИДЕНТИФИКАТОРов, запрос поиска не вернет указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="c55dc-160">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="c55dc-161">Это связано с тем, что свойство **DocumentID** для элементов почтового ящика изменяется при перемещении почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="c55dc-161">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="c55dc-162">В редких случаях при перемещении почтового ящика после создания поискового списка ИДЕНТИФИКАТОРов необходимо создать новый поиск контента (или обновить результаты поиска для существующего контента), а затем экспортировать результаты или отчет для создания обновленных CSV-файлов, которые можно использовать для создания нового поиска списка ИДЕНТИФИКАТОРов.</span><span class="sxs-lookup"><span data-stu-id="c55dc-162">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
