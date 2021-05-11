---
title: Подготовка CSV-файла для поиска контента списка ID
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
description: Используйте CSV-файл из существующего поиска контента для создания поиска списка ID, который возвращает определенные элементы электронной почты.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311542"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="4ad4d-103">Подготовка CSV-файла для поиска контента списка ID</span><span class="sxs-lookup"><span data-stu-id="4ad4d-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="4ad4d-104">Вы можете искать определенные сообщения электронной почты почтовых ящиков и другие элементы почтовых ящиков с помощью списка Exchange ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="4ad4d-105">Чтобы создать поиск по списку идентификаторов, нужно отправить CSV-файл, в котором указаны конкретные элементы почтового ящика для поиска.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="4ad4d-106">Для этого **CSV-файла** используетсяResults.csvили файл **Items.csvUnindexed,** которые включаются при экспорте результатов поиска контента или экспорте отчета о поиске контента из существующего поиска контента.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="4ad4d-107">Затем вы редактируете один из этих файлов, чтобы указать конкретные элементы для поиска, создать новый поиск списка ID и отправить файл CSV.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="4ad4d-108">**Зачем создавать поиск по списку ID?**</span><span class="sxs-lookup"><span data-stu-id="4ad4d-108">**Why create an ID list search?**</span></span> <span data-ttu-id="4ad4d-109">Если вы не можете определить, откликается ли элемент на запрос об обнаружении электронных данных на основе метаданных в файлах **Results.csv** или **Unindexed Items.csv,** вы можете использовать поиск по списку ID для поиска, предварительного просмотра и экспорта этого элемента, чтобы определить, реагирует ли он на исследуемом случае.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="4ad4d-110">Поиск в списке ID обычно используется для поиска и возврата определенного набора неиндексуальных элементов.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="4ad4d-111">Ниже представлен краткий обзор процесса создания поиска списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="4ad4d-112">Создание и запуск нового поиска в центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="4ad4d-113">Экспорт результатов поиска контента или отчета о поиске контента.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="4ad4d-114">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-114">For more information, see:</span></span>

    - [<span data-ttu-id="4ad4d-115">Экспорт результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="4ad4d-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="4ad4d-116">Экспорт отчета о поиске контента</span><span class="sxs-lookup"><span data-stu-id="4ad4d-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="4ad4d-117">Изменение файла **Results.csv** или **Items.csvUnindexed** и определение определенных элементов почтовых ящиков, которые необходимо включить в поиск по списку ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="4ad4d-118">Инструкции [по](#prepare-the-csv-file-for-an-id-list-search) подготовке CSV-файла для поиска списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="4ad4d-119">Создайте новый поиск списка ID (см. [инструкции)](#create-an-id-list-search)и отправьте подготовленный файл CSV.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="4ad4d-120">Созданный поисковый запрос будет искать только элементы, выбранные в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="4ad4d-121">Поиск в списке ID поддерживается только для элементов почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="4ad4d-122">Вы не можете искать SharePoint и OneDrive в поиске списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="4ad4d-123">Подготовка CSV-файла для поиска списка ID</span><span class="sxs-lookup"><span data-stu-id="4ad4d-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="4ad4d-124">После экспорта результатов поиска или отчета для поиска выполните следующие действия, чтобы подготовить CSV-файл для поиска списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="4ad4d-125">Этот CSV-файл определяет каждый элемент в поиске списка идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="4ad4d-126">Вы можете использовать CSV-файл из поиска, который включал SharePoint сайты и OneDrive учетные записи, но для поиска списка ID можно выбрать только элементы почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="4ad4d-127">Если вы выберете документ в SharePoint или OneDrive, при создании поиска списка ID файл CSV не пройдет проверку.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="4ad4d-128">Откройте файл **Results.csv** **или unindexed Items.csv** в Excel.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="4ad4d-129">В **выбранном столбце** введите **Да** в ячейке, соответствующей элементу, который необходимо искать.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="4ad4d-130">Повторите этот шаг для каждого элемента, который необходимо искать.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4ad4d-131">При открываемом CSV-файле в Excel формат данных для столбца **Document ID** может быть изменен на **Общий**.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="4ad4d-132">Это приводит к отображение документа для элемента в научной нотации.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="4ad4d-133">Например, код документа "481037338205" отображается как "4.81037E+11".</span><span class="sxs-lookup"><span data-stu-id="4ad4d-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="4ad4d-134">Если это произойдет, необходимо выполнить следующие действия, чтобы изменить формат данных столбца Document **ID** на **Номер,** чтобы восстановить правильный формат для документа.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="4ad4d-135">Если этого не сделать, поиск списка ID, использующий CSV-файл, не удастся.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="4ad4d-136">Щелкните правой кнопкой мыши весь **столбец ID документа** и выберите **Ячейки формата**.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="4ad4d-137">В поле **Category** щелкните **Номер**.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="4ad4d-138">Измените число десятичных мест до **0,** а затем нажмите **кнопку ОК,** чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="4ad4d-139">Обратите внимание, что значения в столбце Document ID изменены на числа.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="4ad4d-140">Вот пример CSV-файла, готового к отправке для поиска контента списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![Пример CSV-файла для целевого поиска контента](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="4ad4d-142">Сохраните CSV-файл или используйте **Сохранить Как** сохранить файл с другим именем файла.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="4ad4d-143">В обоих случаях обязательно сохраните файл в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="4ad4d-144">Создание поиска списка ID</span><span class="sxs-lookup"><span data-stu-id="4ad4d-144">Create an ID list search</span></span>

<span data-ttu-id="4ad4d-145">Следующим шагом является создание нового поиска списка ID и отправка CSV-файла, который был подготовлен на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ad4d-146">Поиск по списку ID следует создавать не более чем через 2 дня после экспорта результатов поиска или отчета.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="4ad4d-147">Если результаты поиска или отчет, экспорт которых был экспортируется более 2 дней назад, следует повторно экспортировать результаты поиска или отчеты для создания обновленных CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="4ad4d-148">Затем можно подготовить один из обновленных CSV-файлов и использовать его для создания поиска списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="4ad4d-149">Перейдите на <https://compliance.microsoft.com> и войдите.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="4ad4d-150">В расположенной слева области Центра соответствия требованиям Microsoft 365 щелкните **Показать все** и выберите **Поиск контента**.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="4ad4d-151">На странице **поиска контента** нажмите **кнопку Поиск по списку ID**.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="4ad4d-152">В **листе поиска** по списку ID назовите поиск (и необязательно опишите его) и нажмите кнопку **Обзор** и выберите CSV-файл, который был подготовлен на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="4ad4d-153">Microsoft 365 проверки CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="4ad4d-154">Если проверка не увенчалась успехом, отображается сообщение об ошибке, которое может помочь устранить ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="4ad4d-155">Файл CSV должен быть успешно проверен для создания поиска списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="4ad4d-156">После успешной проверки CSV-файла нажмите **кнопку Поиск** для создания поиска списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="4ad4d-157">Вот пример страницы вылетов из поиска списка ID, которая показывает созданный запрос и предполагаемое число результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![Поиск запроса для поиска списка ID](../media/SearchIDListFlyout.png)

    <span data-ttu-id="4ad4d-159">Количество предполагаемых элементов, отображаемого в статистике для поиска ID, должно соответствовать количеству элементов, выбранных в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="4ad4d-160">Просмотр или экспорт элементов, возвращаемой поиском списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="4ad4d-161">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4ad4d-161">More information</span></span>

<span data-ttu-id="4ad4d-162">Если после создания поиска списка ID вы переместили почтовый ящик, запрос на поиск не возвращает указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="4ad4d-163">Это происходит потому, что свойство **DocumentId** для элементов почтовых ящиков меняется при перемещении почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="4ad4d-164">В редких случаях, когда почтовый ящик перемещается после создания поиска списка ID, необходимо создать новый поиск контента (или обновить результаты поиска для существующего поиска), а затем экспортировать результаты поиска или отчеты для создания обновленных CSV-файлов, которые можно использовать для создания нового поиска списка ID.</span><span class="sxs-lookup"><span data-stu-id="4ad4d-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
