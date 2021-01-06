---
title: Тестирование анализа релевантности в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как использовать вкладку "Тестирование" после пакетного вычисления в Advanced eDiscovery для тестирования, сравнения и проверки общего качества обработки.
ms.openlocfilehash: 52198dc5218c49598403c3f1ece201fc4f00dd47
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760325"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery-classic"></a><span data-ttu-id="d47cf-103">Тестирование анализа релевантности в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="d47cf-103">Test Relevance analysis in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="d47cf-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="d47cf-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d47cf-106">Вкладка "Тестирование" в Advanced eDiscovery позволяет тестировать, сравнивать и проверять общее качество обработки.</span><span class="sxs-lookup"><span data-stu-id="d47cf-106">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="d47cf-107">Эти тесты выполняются после пакетного вычисления.</span><span class="sxs-lookup"><span data-stu-id="d47cf-107">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="d47cf-108">Помечая файлы в коллекции, эксперт принимает окончательное решение о том, действительно ли каждый помеченный файл относится к делу.</span><span class="sxs-lookup"><span data-stu-id="d47cf-108">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="d47cf-109">В сценариях с одним и несколькими вопросами тесты обычно выполняются для каждого вопроса.</span><span class="sxs-lookup"><span data-stu-id="d47cf-109">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="d47cf-110">Результаты можно просмотреть после каждого теста, а результаты тестирования можно переработать с помощью указанных примеров тестовых файлов.</span><span class="sxs-lookup"><span data-stu-id="d47cf-110">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="d47cf-111">Тестирование остальных</span><span class="sxs-lookup"><span data-stu-id="d47cf-111">Testing the rest</span></span>

<span data-ttu-id="d47cf-112">Тест "Тестирование остальных" используется для проверки решений по выбору, например для просмотра только файлов, которые выше определенной оценки релевантности на основе окончательных результатов Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="d47cf-112">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="d47cf-113">Эксперт проверяет пример файлов в выбранной оценке вырезания, чтобы оценить количество соответствующих файлов в этом наборе.</span><span class="sxs-lookup"><span data-stu-id="d47cf-113">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="d47cf-114">Этот тест предоставляет статистику и сравнение между набором "Проверка" и "Тестирование для остальной части".</span><span class="sxs-lookup"><span data-stu-id="d47cf-114">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="d47cf-115">Результаты набора для проверки вычисляются по релевантности во время обучения.</span><span class="sxs-lookup"><span data-stu-id="d47cf-115">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="d47cf-116">Результаты включают вычисления на основе параметров и входных параметров, например:</span><span class="sxs-lookup"><span data-stu-id="d47cf-116">The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="d47cf-117">Протестировать статистику по количеству файлов в примере и определить соответствующие файлы.</span><span class="sxs-lookup"><span data-stu-id="d47cf-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="d47cf-118">Табличные сравнения параметров Population в наборе "Проверка" и "Rest", например количество файлов, предполагаемое количество соответствующих файлов, предполагаемое значение параметров и средние затраты на поиск дополнительного релевантного файла.</span><span class="sxs-lookup"><span data-stu-id="d47cf-118">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file.</span></span> <span data-ttu-id="d47cf-119">Параметры затрат могут быть заданы администратором.</span><span class="sxs-lookup"><span data-stu-id="d47cf-119">Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="d47cf-120">Откройте **вкладку \> "Проверка релевантности".**</span><span class="sxs-lookup"><span data-stu-id="d47cf-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="d47cf-121">На **вкладке "Тестирование"** нажмите **кнопку "Новый тест".**</span><span class="sxs-lookup"><span data-stu-id="d47cf-121">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="d47cf-122">**Отобразилось** диалоговое окно создания тестов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d47cf-122">The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Результаты теста "Тестирование остальных элементов" при определении релевантности](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="d47cf-124">Введите **имя** и описание тестового имени и описания.</span><span class="sxs-lookup"><span data-stu-id="d47cf-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="d47cf-125">In the **Test type** list, select Test **the Rest**</span><span class="sxs-lookup"><span data-stu-id="d47cf-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="d47cf-126">В **списке "Проблема/ Категория"** выберите имя проблемы.</span><span class="sxs-lookup"><span data-stu-id="d47cf-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="d47cf-127">В **списке загрузки** выберите загрузку.</span><span class="sxs-lookup"><span data-stu-id="d47cf-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="d47cf-128">В **%чтения** примите значение по умолчанию или выберите значение для оценки релевантности вырезания.</span><span class="sxs-lookup"><span data-stu-id="d47cf-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="d47cf-129">В **значении "Установить размер"** или примите значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d47cf-129">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="d47cf-130">Обратите внимание, что значки восстановления восстановят значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d47cf-130">Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="d47cf-131">Нажмите **кнопку "Начать добавление тегов"**.</span><span class="sxs-lookup"><span data-stu-id="d47cf-131">Click **Start tagging**.</span></span> <span data-ttu-id="d47cf-132">Создается тестовый пример.</span><span class="sxs-lookup"><span data-stu-id="d47cf-132">A test sample is generated.</span></span>
    
10. <span data-ttu-id="d47cf-133">Просмотрите и помечайте каждый из файлов на вкладке **"Тег \>** релевантности", а затем нажмите кнопку **"Вычислить".**</span><span class="sxs-lookup"><span data-stu-id="d47cf-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="d47cf-134">На вкладке "Тестирование" можно щелкнуть **"Просмотреть результаты",** чтобы просмотреть результаты тестирования.</span><span class="sxs-lookup"><span data-stu-id="d47cf-134">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="d47cf-135">Пример показан на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="d47cf-135">An example is shown in the following figure.</span></span> 
    
    ![Тестирование остальных элементов](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="d47cf-137">На рисунке выше  раздел "Примеры параметров" таблицы содержит сведения о количестве файлов в примере, отмеченном экспертом, и количестве соответствующих файлов, найденных в этом примере.</span><span class="sxs-lookup"><span data-stu-id="d47cf-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="d47cf-138">Раздел параметров **Population** таблицы содержит результаты тестирования, включая набор "Проверка" для файлов с показателем ниже выбранного кадра и "Остальной" с показателем выше выбранного.</span><span class="sxs-lookup"><span data-stu-id="d47cf-138">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="d47cf-139">Для каждого из них отображаются следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="d47cf-139">For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="d47cf-140">Включает файлы с %- Указано вырезание</span><span class="sxs-lookup"><span data-stu-id="d47cf-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="d47cf-141">Общее количество файлов</span><span class="sxs-lookup"><span data-stu-id="d47cf-141">The total number of files</span></span> 
    
- <span data-ttu-id="d47cf-142">Предполагаемое количество соответствующих файлов</span><span class="sxs-lookup"><span data-stu-id="d47cf-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="d47cf-143">Приблизительными объемами</span><span class="sxs-lookup"><span data-stu-id="d47cf-143">The estimated richness</span></span> 
    
- <span data-ttu-id="d47cf-144">Средняя стоимость проверки при поиске другого релевантного файла</span><span class="sxs-lookup"><span data-stu-id="d47cf-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="d47cf-145">Тестирование среза</span><span class="sxs-lookup"><span data-stu-id="d47cf-145">Testing the slice</span></span>

<span data-ttu-id="d47cf-146">Тест "Тестирование фрагмента" выполняет тестирование, аналогичное тесту "Тестирование остального", но к сегменту набора файлов, указанному в %чтения релевантности.</span><span class="sxs-lookup"><span data-stu-id="d47cf-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="d47cf-147">Откройте **вкладку \> "Проверка релевантности".**</span><span class="sxs-lookup"><span data-stu-id="d47cf-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="d47cf-148">На **вкладке "Тестирование"** нажмите **кнопку "Новый тест".**</span><span class="sxs-lookup"><span data-stu-id="d47cf-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="d47cf-149">**Отобразилось** диалоговое окно создания тестов.</span><span class="sxs-lookup"><span data-stu-id="d47cf-149">The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="d47cf-150">Введите **сведения** в **области**"Имя теста" и "Описание".</span><span class="sxs-lookup"><span data-stu-id="d47cf-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="d47cf-151">В **списке тестового** типа выберите **"Тестирование фрагмента".**</span><span class="sxs-lookup"><span data-stu-id="d47cf-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="d47cf-152">В **списке проблем** выберите имя проблемы.</span><span class="sxs-lookup"><span data-stu-id="d47cf-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="d47cf-153">В **списке загрузки** выберите загрузку.</span><span class="sxs-lookup"><span data-stu-id="d47cf-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="d47cf-154">В **%чтения между** значениями примите значения низкого и высокого диапазона по умолчанию или выберите значения для оценки релевантности.</span><span class="sxs-lookup"><span data-stu-id="d47cf-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="d47cf-155">В **области "Установить размер"** выберите значение или примите значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d47cf-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="d47cf-156">Значки восстановления восстановят значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d47cf-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="d47cf-157">Нажмите **кнопку "Начать добавление тегов"**.</span><span class="sxs-lookup"><span data-stu-id="d47cf-157">Click **Start tagging**.</span></span> <span data-ttu-id="d47cf-158">Создается тестовый пример.</span><span class="sxs-lookup"><span data-stu-id="d47cf-158">A test sample is generated.</span></span>
    
10. <span data-ttu-id="d47cf-159">Просмотрите и помечайте каждый из файлов на вкладке **"Тег \>** релевантности", а затем нажмите кнопку **"Вычислить".**</span><span class="sxs-lookup"><span data-stu-id="d47cf-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="d47cf-160">На вкладке "Тестирование" можно щелкнуть **"Просмотреть результаты",** чтобы просмотреть результаты тестирования.</span><span class="sxs-lookup"><span data-stu-id="d47cf-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
