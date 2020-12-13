---
title: Обучение тегам и релевантности в Advanced eDiscovery
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: Узнайте, как пометить теги, а затем работать с учебным образцом из 40 файлов на этапе обучения релевантности Advanced eDiscovery.
ms.openlocfilehash: d576b0a907a4c12eabe4f3cba9846de670b0ee12
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663454"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery-classic"></a><span data-ttu-id="80d66-103">Обучение тегам и релевантности в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="80d66-103">Tagging and Relevance training in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="80d66-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="80d66-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="80d66-106">В этом разделе описывается процедура работы с модулем обучения релевантности Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="80d66-106">This topic describes the procedure for working with the Advanced eDiscovery Relevance training module.</span></span> 
  
<span data-ttu-id="80d66-107">После завершения оценки в Advanced eDiscovery и выхода на этап обучения релевантности обучающий пример из 40 файлов будет доставлен на вкладку "Тег" для маркировки.</span><span class="sxs-lookup"><span data-stu-id="80d66-107">After Assessment is completed in Advanced eDiscovery, and you enter the Relevance training stage, a training sample of 40 files is brought into the Tag tab for tagging.</span></span> 
  
## <a name="performing-relevance-training"></a><span data-ttu-id="80d66-108">Выполнение обучения релевантности</span><span class="sxs-lookup"><span data-stu-id="80d66-108">Performing Relevance training</span></span>

1. <span data-ttu-id="80d66-109">На **вкладке "Тег \>** релевантности" по умолчанию в левой области отображается области тегов, а примеры файлов отображаются по одному для тегов.</span><span class="sxs-lookup"><span data-stu-id="80d66-109">In the **Relevance \> Tag** tab, the Tagging pane is displayed by default in the left pane and the sample files are displayed, one at a time for tagging.</span></span> 
    
    ![Панель на вкладке "Релевантность" > "Добавление тегов"](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    <span data-ttu-id="80d66-111">На **вкладке "Тег"** отображается отображаемая имя файла.</span><span class="sxs-lookup"><span data-stu-id="80d66-111">In the **Tag** tab, the file's display name is shown.</span></span> <span data-ttu-id="80d66-112">Это может быть путь, тема электронной почты, должность или имя, определенное пользователем.</span><span class="sxs-lookup"><span data-stu-id="80d66-112">This could be the path, email subject, title, or user-defined name.</span></span> <span data-ttu-id="80d66-113">ИД, путь к файлу или текстовый путь можно скопировать, щелкнув правой кнопкой мыши путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="80d66-113">The ID, file path or text path can be copied by right-clicking on the file's path.</span></span> 
    
    <span data-ttu-id="80d66-114">Статистика  тегов вкладок "Тег" показывает номер образца файла (в верхней части левой области), число отображаемого в данный момент файла из общего числа файлов в примере (внизу правой области) и текущее общее число файлов с тегами в примере (внизу левой области), которое изменяется по мере пометки файлов.</span><span class="sxs-lookup"><span data-stu-id="80d66-114">The **Tag** tab tagging statistics show the file sample number (at the top of the left pane), the number of the currently displayed file out of the total files in the sample (bottom of right pane), and the current total number of tagged files in the sample (bottom of the left pane), which changes as you tag files.</span></span> <span data-ttu-id="80d66-115">Это относится к любым тегам релевантности, которые были сделаны в области оценки, обучения, перенаверки или тестирования.</span><span class="sxs-lookup"><span data-stu-id="80d66-115">This applies for any Relevance tagging done, whether in Assessment, Training, Catch-up, or Test.</span></span> 
    
    <span data-ttu-id="80d66-116">Значки, указывающие на наличие комментариев, тегов и файлов семейства, отображаются в представлении файла на панели над файлом.</span><span class="sxs-lookup"><span data-stu-id="80d66-116">Icons indicating the existence of comments, tags, and family files are displayed in the file view in a bar above the file.</span></span>
    
2. <span data-ttu-id="80d66-117">Определите релевантность файла для проблемы с делом и помечаем файл с помощью кнопок значка параметра тегов или сочетания клавиш, как показано в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="80d66-117">Determine the file's relevance for the case issue and tag the file using either the Tagging option icon buttons or keyboard shortcuts, as shown in the following table:</span></span>

|<span data-ttu-id="80d66-118">**Параметр тегов**</span><span class="sxs-lookup"><span data-stu-id="80d66-118">**Tagging option**</span></span>|<span data-ttu-id="80d66-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="80d66-119">**Description**</span></span>|<span data-ttu-id="80d66-120">**Сочетания клавиш**</span><span class="sxs-lookup"><span data-stu-id="80d66-120">**Keyboard shortcut**</span></span>|<span data-ttu-id="80d66-121">**Для нескольких проблем — массовое теги сочетания клавиш**</span><span class="sxs-lookup"><span data-stu-id="80d66-121">**For multiple issues - bulk tag keyboard shortcut**</span></span>|
|-----|-----|-----|-----|
|<span data-ttu-id="80d66-122">R</span><span class="sxs-lookup"><span data-stu-id="80d66-122">R</span></span>  <br/> |<span data-ttu-id="80d66-123">Релевантно</span><span class="sxs-lookup"><span data-stu-id="80d66-123">Relevant</span></span>  <br/> |<span data-ttu-id="80d66-124">Z</span><span class="sxs-lookup"><span data-stu-id="80d66-124">Z</span></span>  <br/> |<span data-ttu-id="80d66-125">Shift + Z</span><span class="sxs-lookup"><span data-stu-id="80d66-125">Shift + Z</span></span>  <br/> |
|<span data-ttu-id="80d66-126">NR</span><span class="sxs-lookup"><span data-stu-id="80d66-126">NR</span></span>  <br/> |<span data-ttu-id="80d66-127">Не релевантно</span><span class="sxs-lookup"><span data-stu-id="80d66-127">Not relevant</span></span>  <br/> |<span data-ttu-id="80d66-128">X</span><span class="sxs-lookup"><span data-stu-id="80d66-128">X</span></span>  <br/> |<span data-ttu-id="80d66-129">Shift + X</span><span class="sxs-lookup"><span data-stu-id="80d66-129">Shift + X</span></span>  <br/> |
|<span data-ttu-id="80d66-130">Пропустить</span><span class="sxs-lookup"><span data-stu-id="80d66-130">Skip</span></span>  <br/> |<span data-ttu-id="80d66-131">Пропустить</span><span class="sxs-lookup"><span data-stu-id="80d66-131">Skip</span></span>  <br/> |<span data-ttu-id="80d66-132">C</span><span class="sxs-lookup"><span data-stu-id="80d66-132">C</span></span>  <br/> |<span data-ttu-id="80d66-133">Shift + A</span><span class="sxs-lookup"><span data-stu-id="80d66-133">Shift + A</span></span>  <br/> |
   
  - <span data-ttu-id="80d66-134">Если для файла существует несколько проблем, то после пометки одной проблемы выбор переходит к следующей проблеме (если таково).</span><span class="sxs-lookup"><span data-stu-id="80d66-134">When multiple issues exist for a file, after tagging one issue, the selection moves to the next issue (if any).</span></span> 
    
  - <span data-ttu-id="80d66-135">Ключевые слова, определенные администратором или руководителем дела при выделении ключевых слов (ключевые слова выделенной настройки релевантности), будут отображаться (в указанных цветах), чтобы помочь определить соответствующие файлы при \> маркировке.</span><span class="sxs-lookup"><span data-stu-id="80d66-135">Keywords that were defined by the Administrator or Case manager when highlighting keywords (Relevance setup \> Highlighted keywords), will be displayed (in specified colors) to help identify relevant files while tagging.</span></span> <span data-ttu-id="80d66-136">Если ключевое слово имеет двойное подчеркнутое, его можно щелкнуть, чтобы отобразить подсказку с описанием ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="80d66-136">If a keyword has a double underline, it can be clicked to display a tool-tip with the keyword's description.</span></span> 
    
    <span data-ttu-id="80d66-137">При желании на **вкладке "Тег"** щелкните параметры **тега,** чтобы установить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="80d66-137">Optionally, in the **Tag** tab, click **Tag settings** to set the following options:</span></span> 
    
    ![Задание параметров на вкладке "Релевантность" > "Добавление тегов"](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - <span data-ttu-id="80d66-139">Массовый **тег:** используйте этот параметр, чтобы назначить  файлу несколько проблем, выбрав "Все", чтобы задать тег для выбранного файла  для всех проблем (переопределив уже помеченные проблемы) или выбрав "Остальные", чтобы применить тег к оставшимся неавтомантным вопросам.</span><span class="sxs-lookup"><span data-stu-id="80d66-139">**Bulk tag**: Use this option to assign multiple issues for a file by selecting **All** to set the tag for the selected file for all issues (overrides already tagged issues) or by selecting **The rest** to apply the tag to the remaining untagged issues.</span></span> <span data-ttu-id="80d66-140">Выбранный параметр остается в силе для всех случаев этого пользователя до тех пор, пока он не изменится этим пользователем (параметр действует для каждого пользователя во всех случаях пользователя).</span><span class="sxs-lookup"><span data-stu-id="80d66-140">The selected option remains in effect for all of this user's cases until changed by that user (setting is per user for all the user's cases).</span></span> 
    
  - <span data-ttu-id="80d66-141">**Auto tag**: select this check box to set other issues for a file as Not relevant after a single Relevant tagging.</span><span class="sxs-lookup"><span data-stu-id="80d66-141">**Auto tag**: Select this check box to set other issues for a file as Not relevant after a single Relevant tagging.</span></span>
    
  - <span data-ttu-id="80d66-142">**Автоматическое предварительное** добавление: этот галочка перемещает отображаемую папку в следующий файл при пометке последней или только неотвеченной проблемы.</span><span class="sxs-lookup"><span data-stu-id="80d66-142">**Auto advance**: Select this check box to move the displayed file selection to the next file when tagging the last or only untagged issue.</span></span> 
    
    <span data-ttu-id="80d66-143">Пропущенные файлы не будут рассматриваться в целях обучения релевантности и релевантности.</span><span class="sxs-lookup"><span data-stu-id="80d66-143">Skipped files will not be considered for Relevance training and Relevance scoring purposes.</span></span>
    
3. <span data-ttu-id="80d66-144">Комментарии с бесплатным текстом, связанные с файлом,  можно просматривать и редактировать с помощью параметра "Комментарий" в выпадаемом списке левой области.</span><span class="sxs-lookup"><span data-stu-id="80d66-144">Free-text comments, associated with a file, can be viewed and edited via the **Comment** option in the left pane drop-down list.</span></span> <span data-ttu-id="80d66-145">(необязательный)</span><span class="sxs-lookup"><span data-stu-id="80d66-145">(optional)</span></span> 
    
4. <span data-ttu-id="80d66-146">Руководство по маркировке можно просмотреть,  выбрав параметр "Рекомендации по тегированию" в выпадаемом списке левой области.</span><span class="sxs-lookup"><span data-stu-id="80d66-146">Guidelines for tagging can be viewed by selecting the **Tagging guidelines** option in the left pane drop-down list.</span></span> 
    
5. <span data-ttu-id="80d66-147">После завершения пометки всех файлов в списке и завершения вычисления результатов нажмите кнопку **"Вычислить".**</span><span class="sxs-lookup"><span data-stu-id="80d66-147">After you finish tagging all files in the list and are ready to calculate the results, click **Calculate**.</span></span> <span data-ttu-id="80d66-148">**Отобразилась** вкладка "Отслеживание".</span><span class="sxs-lookup"><span data-stu-id="80d66-148">The **Track** tab is displayed.</span></span> 
    
## <a name="working-with-the-sample-files-list"></a><span data-ttu-id="80d66-149">Работа со списком примеров файлов</span><span class="sxs-lookup"><span data-stu-id="80d66-149">Working with the sample files list</span></span>

<span data-ttu-id="80d66-150">Список примеров файлов позволяет просматривать список файлов в обучающем примере и выполнять различные действия с одним или более файлами.</span><span class="sxs-lookup"><span data-stu-id="80d66-150">The sample files list allows you to view a list of the files in a training sample and perform various action on one or more files.</span></span> <span data-ttu-id="80d66-151">На **вкладке "Тег** релевантности" на левой области "Примеры файлов" отображается список примеров файлов для обработки с помощью процессов оценки, обучения, перебора и \>  несоответствий. </span><span class="sxs-lookup"><span data-stu-id="80d66-151">In the **Relevance** \> **Tag** tab, the **Sample files** left pane displays a list of sample files for processing with Assessment, Training, Catch-up, and Inconsistencies processes.</span></span> 
  
1. <span data-ttu-id="80d66-152">На **вкладке \> "Тег релевантности"** выберите примеры файлов в левом выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="80d66-152">In the **Relevance \> Tag** tab, select the Sample files in the left pane drop-down list.</span></span> <span data-ttu-id="80d66-153">Примеры файлов перечислены в левой области.</span><span class="sxs-lookup"><span data-stu-id="80d66-153">The sample files are listed in the left pane.</span></span> 
    
    ![Список примеров файлов на вкладке "Релевантность" > "Добавление тегов"](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. <span data-ttu-id="80d66-155">Выберите определенный пример или номер файла, введите или выберите его номер в **полях** "Образец" или **"Файл".**</span><span class="sxs-lookup"><span data-stu-id="80d66-155">Select a specific sample or file number by entering or selecting its number in the **Sample** or **File** boxes.</span></span> 
    
  -   - <span data-ttu-id="80d66-156">В левом столбце отображаемого списка файлов на вкладке **"Тег"** отображается номер последовательности файлов. Щелкнув заголовку, исходный порядок отображения файлов возвращается в исходный порядок.</span><span class="sxs-lookup"><span data-stu-id="80d66-156">A file sequence number is listed in the left column of the displayed file list on the **Tag** tab. By clicking the header, the original displayed order of the files returns to its original order.</span></span> 
    
  - <span data-ttu-id="80d66-157">Щелчок по строке файла отображает его содержимое в правой области.</span><span class="sxs-lookup"><span data-stu-id="80d66-157">Clicking on a file row displays its content in the right pane.</span></span>
    
  - <span data-ttu-id="80d66-158">Перейдите между файлами в текущем примере с помощью параметров нижней панели меню.</span><span class="sxs-lookup"><span data-stu-id="80d66-158">Navigate between files in the current sample by using the lower menu bar options.</span></span> <span data-ttu-id="80d66-159">Кроме того, доступны сочетания клавиш навигации:</span><span class="sxs-lookup"><span data-stu-id="80d66-159">In addition, navigational keyboard shortcuts are available:</span></span>
    
    <span data-ttu-id="80d66-160">Чтобы перейти к первому файлу в примере: Shift + CTRL + \<</span><span class="sxs-lookup"><span data-stu-id="80d66-160">To navigate to the first file in the sample: Shift + Ctrl + \<</span></span>
    
    <span data-ttu-id="80d66-161">Переход к предыдущему файлу в примере: Shift + \<</span><span class="sxs-lookup"><span data-stu-id="80d66-161">To navigate to the previous file in the sample: Shift + \<</span></span>
    
    <span data-ttu-id="80d66-162">Переход к следующему файлу в примере: Shift + \></span><span class="sxs-lookup"><span data-stu-id="80d66-162">To navigate to the next file in the sample: Shift + \></span></span>
    
    <span data-ttu-id="80d66-163">Переход к последнему файлу в примере: Shift + CTRL + \></span><span class="sxs-lookup"><span data-stu-id="80d66-163">To navigate to the last file in the sample: Shift + Ctrl + \></span></span>
    
## <a name="see-also"></a><span data-ttu-id="80d66-164">См. также</span><span class="sxs-lookup"><span data-stu-id="80d66-164">See also</span></span>

[<span data-ttu-id="80d66-165">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="80d66-165">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="80d66-166">Понимание оценки релевантности</span><span class="sxs-lookup"><span data-stu-id="80d66-166">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="80d66-167">Добавление тегов и оценка</span><span class="sxs-lookup"><span data-stu-id="80d66-167">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="80d66-168">Отслеживание анализа релевантности</span><span class="sxs-lookup"><span data-stu-id="80d66-168">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="80d66-169">Выбор на основе результатов</span><span class="sxs-lookup"><span data-stu-id="80d66-169">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="80d66-170">Тестирование анализа релевантности</span><span class="sxs-lookup"><span data-stu-id="80d66-170">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

