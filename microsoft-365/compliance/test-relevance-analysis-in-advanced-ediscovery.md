---
title: Анализ релевантности в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как использовать вкладку Test после вычисления пакета в Advanced eDiscovery для проверки, сравнения и проверки общего качества обработки.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769174"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="f4cf5-103">Анализ релевантности в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f4cf5-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="f4cf5-104">Вкладка Test в Advanced eDiscovery позволяет протестировать, сравнить и проверить общее качество обработки.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="f4cf5-105">Эти тесты выполняются после вычисления пакета.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="f4cf5-106">Пометив файлы в коллекции, эксперт принимает окончательное решение о том, относится ли каждый помеченный файл к делу.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="f4cf5-107">В сценариях с одним и несколькими выпусками обычно выполняются тесты по одной проблеме.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="f4cf5-108">Результаты можно просматривать после каждого теста, а результаты тестов можно переработать с помощью указанных тестовых файлов.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="f4cf5-109">Тестирование остальных</span><span class="sxs-lookup"><span data-stu-id="f4cf5-109">Testing the rest</span></span>

<span data-ttu-id="f4cf5-110">Тест "Test the Rest" используется для проверки решений выбраковки, например, для проверки только файлов, превыше определенной оценки отсечь релевантности на основе окончательных Advanced eDiscovery результатов.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="f4cf5-111">Эксперт проверяет пример файлов в выбранной оценке отсечь, чтобы оценить количество соответствующих файлов в этом наборе.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="f4cf5-112">Этот тест содержит статистику и сравнение между набором Обзор и населением Test the Rest.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="f4cf5-113">Результаты набора обзоров — это результаты, рассчитанные по релевантности во время обучения.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="f4cf5-114">Результаты включают вычисления на основе параметров и параметров ввода, таких как:</span><span class="sxs-lookup"><span data-stu-id="f4cf5-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="f4cf5-115">Проверьте пример статистики количества файлов в примере и идентифицировали соответствующие файлы.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="f4cf5-116">Табулярное сравнение параметров Population в наборе Review и Rest, например, количество файлов, предполагаемое количество соответствующих файлов, предполагаемое богатство и средняя стоимость поиска другого соответствующего файла.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="f4cf5-117">Параметры затрат могут быть заданы администратором.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="f4cf5-118">Чтобы выполнить тест "Test the Rest":</span><span class="sxs-lookup"><span data-stu-id="f4cf5-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="f4cf5-119">Откройте **вкладку Тест \> релевантности.**</span><span class="sxs-lookup"><span data-stu-id="f4cf5-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="f4cf5-120">На **вкладке Тест** нажмите **кнопку Новый тест**.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="f4cf5-121">Отображается **диалоговое окно Create** test, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![Результаты теста "Тестирование остальных элементов" при определении релевантности](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="f4cf5-123">В **тесте имя** и **описание** введите имя и описание.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="f4cf5-124">В **списке тестового** типа выберите **Test the Rest**</span><span class="sxs-lookup"><span data-stu-id="f4cf5-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="f4cf5-125">В **списке Issue / Category** выберите имя проблемы.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="f4cf5-126">В **списке Нагрузка** выберите нагрузку.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="f4cf5-127">В **%Read %** примите значение по умолчанию или выберите значение для оценки релевантности отсека.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="f4cf5-128">В **наборе размера** или принять значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="f4cf5-129">Значки восстановления восстановят значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="f4cf5-130">Нажмите **кнопку Начните метки**.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-130">Click **Start tagging**.</span></span> <span data-ttu-id="f4cf5-131">Создается тестовый образец.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-131">A test sample is generated.</span></span>

10. <span data-ttu-id="f4cf5-132">Просмотрите и пометить каждый из файлов на вкладке **Релевантность \> Тег** и когда это будет сделано, щелкните **Вычислять**.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="f4cf5-133">На вкладке Тест можно нажать **кнопку Просмотр результатов,** чтобы просмотреть результаты тестирования.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="f4cf5-134">Пример показан на следующем скриншоте.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-134">An example is shown in the following screenshot.</span></span>

    ![Тестирование остальных элементов](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="f4cf5-136">На предыдущем снимке экрана в разделе **Примеры** параметров таблицы содержатся сведения о количестве файлов в примере, помеченном экспертом, и количестве соответствующих файлов, найденных в этом примере.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="f4cf5-137">Раздел **Параметры** population в таблице содержит результаты тестирования, в том числе набор просмотров файлов со показателем ниже выбранного отсечения и "Остальная" популяция файлов с показателем выше выбранного отсечения.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="f4cf5-138">Для каждого населения отображаются следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="f4cf5-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="f4cf5-139">Включает файлы со считываемой % - Заявленное отсечь</span><span class="sxs-lookup"><span data-stu-id="f4cf5-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="f4cf5-140">Общее число файлов</span><span class="sxs-lookup"><span data-stu-id="f4cf5-140">The total number of files</span></span>

- <span data-ttu-id="f4cf5-141">Предполагаемое число соответствующих файлов</span><span class="sxs-lookup"><span data-stu-id="f4cf5-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="f4cf5-142">Предполагаемое богатство</span><span class="sxs-lookup"><span data-stu-id="f4cf5-142">The estimated richness</span></span>

- <span data-ttu-id="f4cf5-143">Средняя стоимость проверки поиска другого релевантного файла</span><span class="sxs-lookup"><span data-stu-id="f4cf5-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="f4cf5-144">Тестирование среза</span><span class="sxs-lookup"><span data-stu-id="f4cf5-144">Testing the slice</span></span>

<span data-ttu-id="f4cf5-145">Тест "Test the Slice" выполняет тестирование, аналогичное тесту "Test the Rest", но к сегменту набора файлов, как указано в релевантности Read %.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="f4cf5-146">Чтобы выполнить тест "Test the Slice":</span><span class="sxs-lookup"><span data-stu-id="f4cf5-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="f4cf5-147">Откройте **вкладку Тест \> релевантности.**</span><span class="sxs-lookup"><span data-stu-id="f4cf5-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="f4cf5-148">На **вкладке Тест** нажмите **кнопку Новый тест**.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="f4cf5-149">Отображается диалоговое окно **Create test.**</span><span class="sxs-lookup"><span data-stu-id="f4cf5-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="f4cf5-150">В **тестовом имени** **и описании** введите сведения.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="f4cf5-151">В **списке тестового** типа выберите **Test the Slice**.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="f4cf5-152">В **списке выпусков** выберите имя проблемы.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="f4cf5-153">В **списке Нагрузка** выберите нагрузку.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="f4cf5-154">В **режиме Чтение % между** значениями значения низкого и высокого диапазона по умолчанию или выберите значения для баллов релевантности отсечь.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="f4cf5-155">В **set size** выберите значение или примите значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="f4cf5-156">Значки восстановления восстановят значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="f4cf5-157">Нажмите **кнопку Начните метки**.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-157">Click **Start tagging**.</span></span> <span data-ttu-id="f4cf5-158">Создается тестовый образец.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-158">A test sample is generated.</span></span>

10. <span data-ttu-id="f4cf5-159">Просмотрите и пометить каждый из файлов на вкладке **Релевантность \> Тег** и когда это будет сделано, щелкните **Вычислять**.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="f4cf5-160">На вкладке Тест можно нажать **кнопку Просмотр результатов,** чтобы просмотреть результаты тестирования.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-160">In the Test tab, you can click **View results** to see the test results.</span></span>
