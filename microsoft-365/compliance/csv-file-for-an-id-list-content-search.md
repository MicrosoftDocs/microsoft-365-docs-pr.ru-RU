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
description: Используйте CSV-файлы из существующего поиска контента, чтобы создать поиск в списке ID, который возвращает определенные сообщения электронной почты.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817978"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="84302-103">Подготовка CSV-файла для поиска контента по списку идентификаторов</span><span class="sxs-lookup"><span data-stu-id="84302-103">Prepare a CSV file for an ID list Content Search</span></span>

<span data-ttu-id="84302-104">Вы можете искать определенные сообщения электронной почты и другие элементы почтового ящика, используя список ИД Exchange.</span><span class="sxs-lookup"><span data-stu-id="84302-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="84302-105">Чтобы создать поиск в списке идентификаторов (официально называемый целевым поиском), необходимо отправить CSV-файл, в котором указаны конкретные элементы почтового ящика, которые необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="84302-105">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="84302-106">Для этого CSV-файла  используетсяResults.csv-файл или файл **Items.csv,которые** включаются при экспорте результатов поиска контента или экспорте отчета о поиске контента из существующего и существующего поиска контента.</span><span class="sxs-lookup"><span data-stu-id="84302-106">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="84302-107">Затем вы редактируете один из этих файлов, чтобы указать конкретные элементы для поиска, а затем создадите новый поиск в списке ИД и отправьте CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="84302-107">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span>

<span data-ttu-id="84302-108">Ниже представлен краткий обзор процесса создания поиска в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-108">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="84302-109">Создайте и запустите новый или управляемый поиск контента в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="84302-109">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="84302-110">Экспорт результатов поиска контента или экспорт отчета о поиске контента.</span><span class="sxs-lookup"><span data-stu-id="84302-110">Export the content search results or export the content search report.</span></span> <span data-ttu-id="84302-111">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="84302-111">For more information, see:</span></span>

    - [<span data-ttu-id="84302-112">Экспорт результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="84302-112">Export Content Search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="84302-113">Экспорт отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="84302-113">Export a Content Search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="84302-114">**Отредактируете** Results.csvили **неиndexed Items.csv** и определите конкретные элементы почтового ящика, которые необходимо включить в поиск в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-114">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="84302-115">См. [инструкции по](#prepare-the-csv-file-for-an-id-list-search) подготовке CSV-файла для поиска в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-115">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="84302-116">Создайте новый поиск по списку ID (см. [инструкции)](#create-an-id-list-search)и отправьте CSV-файл, который вы подготовили.</span><span class="sxs-lookup"><span data-stu-id="84302-116">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="84302-117">Созданный поисковый запрос будет искать только элементы, выбранные в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="84302-117">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="84302-118">Поиск в списке ID поддерживается только для элементов почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="84302-118">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="84302-119">Вы не можете искать документы SharePoint и OneDrive в поиске по списку ID.</span><span class="sxs-lookup"><span data-stu-id="84302-119">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

 <span data-ttu-id="84302-120">**Зачем создавать поиск в списке ID?**</span><span class="sxs-lookup"><span data-stu-id="84302-120">**Why create an ID list search?**</span></span> <span data-ttu-id="84302-121">Если вы не можете определить, отвечает ли элемент на запрос на eDiscovery на основе метаданных в файлах **Results.csv** или **Unindexed Items.csv,** вы можете использовать поиск в списке ID, чтобы найти, просмотреть и экспортировать этот элемент, чтобы определить, отвечает ли он на исследуемого дела.</span><span class="sxs-lookup"><span data-stu-id="84302-121">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="84302-122">Поиск в списке ID обычно используется для поиска и возврата определенного набора неиndexed элементов.</span><span class="sxs-lookup"><span data-stu-id="84302-122">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="84302-123">Подготовка CSV-файла для поиска в списке ID</span><span class="sxs-lookup"><span data-stu-id="84302-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="84302-124">После экспорта результатов поиска или отчета для поиска контента можно выполнить следующие действия, чтобы подготовить CSV-файл для поиска в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-124">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="84302-125">Этот CSV-файл определяет каждый элемент в поиске в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-125">This CSV file will identify every item in the ID list search.</span></span>

<span data-ttu-id="84302-126">Обратите внимание, что вы можете использовать CSV-файл из поиска, включаемую  сайты SharePoint и учетные записи OneDrive, но для поиска в списке ID можно выбрать только элементы почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="84302-126">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="84302-127">Если вы выберете документ в SharePoint или OneDrive, CSV-файл не пройдет проверку при создании поиска в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="84302-128">Откройте файл **Results.csv** **или Items.csv** в Excel.</span><span class="sxs-lookup"><span data-stu-id="84302-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="84302-129">В **столбце "Выбранный"** введите **"Да"** в ячейке, соответствующей элементу, который нужно найти.</span><span class="sxs-lookup"><span data-stu-id="84302-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="84302-130">Повторите этот шаг для каждого элемента, который нужно найти.</span><span class="sxs-lookup"><span data-stu-id="84302-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="84302-131">При открываемом CSV-файле в Excel формат данных для столбца **"ИД** документа" меняется на **"Общие".**</span><span class="sxs-lookup"><span data-stu-id="84302-131">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="84302-132">Это приводит к отобралку ИД документа для элемента в нотации в социуме.</span><span class="sxs-lookup"><span data-stu-id="84302-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="84302-133">Например, код документа "481037338205" отображается как "4.81037E+11". Чтобы восстановить правильный формат для ИД  документа, необходимо  выполнить следующие действия, чтобы изменить формат данных столбца "Код документа" на "Номер".</span><span class="sxs-lookup"><span data-stu-id="84302-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="84302-134">Если этого не сделать, поиск в списке ID, использующий CSV-файл, не удастся.</span><span class="sxs-lookup"><span data-stu-id="84302-134">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="84302-135">Щелкните правой кнопкой мыши весь **столбец "ИД документа"** и выберите **"Формат ячеек".**</span><span class="sxs-lookup"><span data-stu-id="84302-135">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="84302-136">В поле **"Категория"** щелкните **"Номер".**</span><span class="sxs-lookup"><span data-stu-id="84302-136">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="84302-137">Измените число десятичных заметок на **0** и нажмите кнопку **"ОК",** чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="84302-137">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="84302-138">Обратите внимание, что значения в столбце "ИД документа" изменены на числа.</span><span class="sxs-lookup"><span data-stu-id="84302-138">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="84302-139">Вот пример CSV-файла, который готов к отправке для поиска контента в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-139">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>

    ![Пример CSV-файла для целевого поиска контента](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. <span data-ttu-id="84302-141">Сохраните CSV-файл или используйте "Сохранить **как"** для сохранения файла с другим именем.</span><span class="sxs-lookup"><span data-stu-id="84302-141">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="84302-142">В обоих случаях сохраните файл в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="84302-142">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="84302-143">Создание поиска в списке ID</span><span class="sxs-lookup"><span data-stu-id="84302-143">Create an ID list search</span></span>

<span data-ttu-id="84302-144">Следующим шагом является создание нового списка ID Content Search и отправка CSV-файла, подготовленного на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="84302-144">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84302-145">Поиск по списку ID следует создавать не более чем через 2 дня после экспорта результатов или отчетов из поиска контента.</span><span class="sxs-lookup"><span data-stu-id="84302-145">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="84302-146">Если результаты поиска или отчет, экспорт которых был экспортируется более 2 дней назад, следует повторно экспортировать результаты поиска или отчет для создания обновленных CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="84302-146">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="84302-147">Затем можно подготовить один из обновленных CSV-файлов и использовать его для создания поиска в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-147">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="84302-148">В Центре безопасности & соответствия требованиям перейдите к **поиску** \> **контента поиска.**</span><span class="sxs-lookup"><span data-stu-id="84302-148">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>

2. <span data-ttu-id="84302-149">На странице **поиска щелкните** стрелку рядом со значком "Добавить новый поиск" и выберите "Поиск ![ по ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)  **списку ID".**</span><span class="sxs-lookup"><span data-stu-id="84302-149">On the **Search** page, click the arrow next to ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>

    ![Click Search by ID List from the New search dropdown list](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. <span data-ttu-id="84302-151">Во **flyout search by ID List** name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span><span class="sxs-lookup"><span data-stu-id="84302-151">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="84302-152">Microsoft 365 пытается проверить CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="84302-152">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="84302-153">Если проверка неуспешна, отображается сообщение об ошибке, которое может помочь устранить ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="84302-153">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="84302-154">Чтобы создать поиск в списке ID, необходимо успешно проверить CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="84302-154">The CSV file has to be successfully validated to create an ID list search.</span></span>

4. <span data-ttu-id="84302-155">После успешной проверки CSV-файла нажмите кнопку **"Поиск",** чтобы создать поиск в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-155">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="84302-156">Ниже приводится пример предполагаемых результатов поиска и запроса, сгенерированного для поиска в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-156">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>

    ![Поисковый запрос для целевого поиска контента в области сведений](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    <span data-ttu-id="84302-158">Обратите внимание, что число предполагаемых элементов, отображаемого в статистике для поиска по ИД, должно соответствовать количеству элементов, выбранных в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="84302-158">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

5. <span data-ttu-id="84302-159">Предварительный просмотр или экспорт элементов, возвращенных при поиске в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-159">Preview or export the items returned by the ID list search.</span></span>

> [!NOTE]
> <span data-ttu-id="84302-160">Если почтовый ящик перемещается после создания поиска в списке ID, запрос на поиск не возвращает указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="84302-160">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="84302-161">Это происходит потому, что свойство **DocumentId** для элементов почтового ящика меняется при перемещении почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="84302-161">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="84302-162">В редких случаях, когда почтовый ящик перемещается после создания поиска в списке ID, необходимо создать новый поиск контента (или обновить результаты поиска для существующего поиска контента), а затем экспортировать результаты поиска или отчет для создания обновленных CSV-файлов, которые можно использовать для создания нового поиска в списке ID.</span><span class="sxs-lookup"><span data-stu-id="84302-162">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
