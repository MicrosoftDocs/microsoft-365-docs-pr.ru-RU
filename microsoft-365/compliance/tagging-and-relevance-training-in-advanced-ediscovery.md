---
title: Расстановка тегов и релевантности в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: 'В этой статье рассказывается о том, как отмечать тегами, а затем работать с обучающим образцом, в котором находится 40 файлов, на этапе обучающего обучения Advanced eDiscovery.  '
ms.openlocfilehash: 8d03061401cab2014d33e9e3238af42a4d01738a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636267"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery-classic"></a><span data-ttu-id="b30cb-103">Расстановка тегов и релевантности в Advanced eDiscovery (классический)</span><span class="sxs-lookup"><span data-stu-id="b30cb-103">Tagging and Relevance training in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="b30cb-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="b30cb-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b30cb-106">В этом разделе описывается процедура работы с дополнительным модулем обучения по релевантности eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b30cb-106">This topic describes the procedure for working with the Advanced eDiscovery Relevance training module.</span></span> 
  
<span data-ttu-id="b30cb-107">После завершения оценки в Advanced eDiscovery и перехода к этапу обучения релевантности учебный пример из 40 файлов добавляется на вкладку Теги для тегирования.</span><span class="sxs-lookup"><span data-stu-id="b30cb-107">After Assessment is completed in Advanced eDiscovery, and you enter the Relevance training stage, a training sample of 40 files is brought into the Tag tab for tagging.</span></span> 
  
## <a name="performing-relevance-training"></a><span data-ttu-id="b30cb-108">Обучение по релевантности</span><span class="sxs-lookup"><span data-stu-id="b30cb-108">Performing Relevance training</span></span>

1. <span data-ttu-id="b30cb-109">На вкладке **тег \> релевантности** область тегов отображается по умолчанию в левой области, а на экране отображаются файлы образцов, по одному для маркировки.</span><span class="sxs-lookup"><span data-stu-id="b30cb-109">In the **Relevance \> Tag** tab, the Tagging pane is displayed by default in the left pane and the sample files are displayed, one at a time for tagging.</span></span> 
    
    ![Панель на вкладке "Релевантность" > "Добавление тегов"](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    <span data-ttu-id="b30cb-111">На вкладке **тег** отображается отображаемое имя файла.</span><span class="sxs-lookup"><span data-stu-id="b30cb-111">In the **Tag** tab, the file's display name is shown.</span></span> <span data-ttu-id="b30cb-112">Это может быть путь, тема сообщения электронной почты, название или определенное пользователем имя.</span><span class="sxs-lookup"><span data-stu-id="b30cb-112">This could be the path, email subject, title, or user-defined name.</span></span> <span data-ttu-id="b30cb-113">Чтобы скопировать идентификатор, путь к файлу или текстовый путь, щелкните правой кнопкой мыши путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="b30cb-113">The ID, file path or text path can be copied by right-clicking on the file's path.</span></span> 
    
    <span data-ttu-id="b30cb-114">В статистике с помощью вкладки **тегов** отображается номер примера файла (в верхней части левой области), число файлов, отображаемых в текущий момент, из итоговых файлов в примере (Нижняя часть правой области) и текущее общее число файлов с тегами в примере (внизу левой области), которые изменяются при разметке файлов.</span><span class="sxs-lookup"><span data-stu-id="b30cb-114">The **Tag** tab tagging statistics show the file sample number (at the top of the left pane), the number of the currently displayed file out of the total files in the sample (bottom of right pane), and the current total number of tagged files in the sample (bottom of the left pane), which changes as you tag files.</span></span> <span data-ttu-id="b30cb-115">Это применимо ко всем разметке релевантности, будь то оценка, обучение, анализ или тестирование.</span><span class="sxs-lookup"><span data-stu-id="b30cb-115">This applies for any Relevance tagging done, whether in Assessment, Training, Catch-up, or Test.</span></span> 
    
    <span data-ttu-id="b30cb-116">Значки, указывающие на наличие комментариев, тегов и файлов семьи, отображаются в представлении файлов на панели над файлом.</span><span class="sxs-lookup"><span data-stu-id="b30cb-116">Icons indicating the existence of comments, tags, and family files are displayed in the file view in a bar above the file.</span></span>
    
2. <span data-ttu-id="b30cb-117">Определите релевантность файла для этой ситуации и пометьте файл с помощью кнопок значка метки или сочетаний клавиш, как показано в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="b30cb-117">Determine the file's relevance for the case issue and tag the file using either the Tagging option icon buttons or keyboard shortcuts, as shown in the following table:</span></span>

|<span data-ttu-id="b30cb-118">**Параметр тегирования**</span><span class="sxs-lookup"><span data-stu-id="b30cb-118">**Tagging option**</span></span>|<span data-ttu-id="b30cb-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b30cb-119">**Description**</span></span>|<span data-ttu-id="b30cb-120">**Сочетание клавиш**</span><span class="sxs-lookup"><span data-stu-id="b30cb-120">**Keyboard shortcut**</span></span>|<span data-ttu-id="b30cb-121">**Несколько проблем — сочетание клавиш для массовых тегов**</span><span class="sxs-lookup"><span data-stu-id="b30cb-121">**For multiple issues - bulk tag keyboard shortcut**</span></span>|
|-----|-----|-----|-----|
|<span data-ttu-id="b30cb-122">R</span><span class="sxs-lookup"><span data-stu-id="b30cb-122">R</span></span>  <br/> |<span data-ttu-id="b30cb-123">Существенно</span><span class="sxs-lookup"><span data-stu-id="b30cb-123">Relevant</span></span>  <br/> |<span data-ttu-id="b30cb-124">Z</span><span class="sxs-lookup"><span data-stu-id="b30cb-124">Z</span></span>  <br/> |<span data-ttu-id="b30cb-125">Shift + Z</span><span class="sxs-lookup"><span data-stu-id="b30cb-125">Shift + Z</span></span>  <br/> |
|<span data-ttu-id="b30cb-126">нр</span><span class="sxs-lookup"><span data-stu-id="b30cb-126">NR</span></span>  <br/> |<span data-ttu-id="b30cb-127">Не релевантно</span><span class="sxs-lookup"><span data-stu-id="b30cb-127">Not relevant</span></span>  <br/> |<span data-ttu-id="b30cb-128">X</span><span class="sxs-lookup"><span data-stu-id="b30cb-128">X</span></span>  <br/> |<span data-ttu-id="b30cb-129">SHIFT + X</span><span class="sxs-lookup"><span data-stu-id="b30cb-129">Shift + X</span></span>  <br/> |
|<span data-ttu-id="b30cb-130">Пропустить</span><span class="sxs-lookup"><span data-stu-id="b30cb-130">Skip</span></span>  <br/> |<span data-ttu-id="b30cb-131">Пропустить</span><span class="sxs-lookup"><span data-stu-id="b30cb-131">Skip</span></span>  <br/> |<span data-ttu-id="b30cb-132">C</span><span class="sxs-lookup"><span data-stu-id="b30cb-132">C</span></span>  <br/> |<span data-ttu-id="b30cb-133">Shift + A</span><span class="sxs-lookup"><span data-stu-id="b30cb-133">Shift + A</span></span>  <br/> |
   
  - <span data-ttu-id="b30cb-134">Если для файла существует несколько проблем, после разметки одной проблемы выделение перемещается на следующий вопрос (при наличии).</span><span class="sxs-lookup"><span data-stu-id="b30cb-134">When multiple issues exist for a file, after tagging one issue, the selection moves to the next issue (if any).</span></span> 
    
  - <span data-ttu-id="b30cb-135">Ключевые слова, которые были определены администратором или управляющим делами при выделении ключевых слов \> (параметры релевантности выделены ключевые слова), будут отображаться (в указанных цветах) для определения релевантных файлов при разметке тегами.</span><span class="sxs-lookup"><span data-stu-id="b30cb-135">Keywords that were defined by the Administrator or Case manager when highlighting keywords (Relevance setup \> Highlighted keywords), will be displayed (in specified colors) to help identify relevant files while tagging.</span></span> <span data-ttu-id="b30cb-136">Если у ключевого слова есть двойное подчеркивание, его можно щелкнуть, чтобы отобразить подсказку с описанием ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="b30cb-136">If a keyword has a double underline, it can be clicked to display a tool-tip with the keyword's description.</span></span> 
    
    <span data-ttu-id="b30cb-137">При необходимости на вкладке **тег** щелкните **параметры тегов** , чтобы задать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b30cb-137">Optionally, in the **Tag** tab, click **Tag settings** to set the following options:</span></span> 
    
    ![Задание параметров на вкладке "Релевантность" > "Добавление тегов"](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - <span data-ttu-id="b30cb-139">**Групповой тег**: Используйте этот параметр, чтобы назначить несколько проблем для файла, выбрав пункт **все** , чтобы задать тег для выбранного файла для всех проблем (переопределения, которые уже были помечены) или выбрав **остальные** , чтобы применить тег к оставшимся проблемам без тегов.</span><span class="sxs-lookup"><span data-stu-id="b30cb-139">**Bulk tag**: Use this option to assign multiple issues for a file by selecting **All** to set the tag for the selected file for all issues (overrides already tagged issues) or by selecting **The rest** to apply the tag to the remaining untagged issues.</span></span> <span data-ttu-id="b30cb-140">Выбранный параметр действует во всех случаях этого пользователя до тех пор, пока он не будет изменен пользователем (значение параметра — для всех пользовательских вариантов).</span><span class="sxs-lookup"><span data-stu-id="b30cb-140">The selected option remains in effect for all of this user's cases until changed by that user (setting is per user for all the user's cases).</span></span> 
    
  - <span data-ttu-id="b30cb-141">**Автоматический тег**: Установите этот флажок, чтобы задать другие проблемы для файла, как неприменимо после одной соответствующей разметки.</span><span class="sxs-lookup"><span data-stu-id="b30cb-141">**Auto tag**: Select this check box to set other issues for a file as Not relevant after a single Relevant tagging.</span></span>
    
  - <span data-ttu-id="b30cb-142">**Автоматический**перевод: Установите этот флажок, чтобы при разметке для последней или только непомеченной задачи при разметке отображался выбранный файл.</span><span class="sxs-lookup"><span data-stu-id="b30cb-142">**Auto advance**: Select this check box to move the displayed file selection to the next file when tagging the last or only untagged issue.</span></span> 
    
    <span data-ttu-id="b30cb-143">Пропущенные файлы не будут учитываться для обучения релевантности и оценки релевантности.</span><span class="sxs-lookup"><span data-stu-id="b30cb-143">Skipped files will not be considered for Relevance training and Relevance scoring purposes.</span></span>
    
3. <span data-ttu-id="b30cb-144">Комментарии с произвольным текстом, связанные с файлом, можно просматривать и редактировать с помощью параметра **Комментарий** в раскрывающемся списке области слева.</span><span class="sxs-lookup"><span data-stu-id="b30cb-144">Free-text comments, associated with a file, can be viewed and edited via the **Comment** option in the left pane drop-down list.</span></span> <span data-ttu-id="b30cb-145">(необязательный)</span><span class="sxs-lookup"><span data-stu-id="b30cb-145">(optional)</span></span> 
    
4. <span data-ttu-id="b30cb-146">Инструкции по разметке можно просмотреть, выбрав параметр **рекомендации по разметке** в раскрывающемся списке области слева.</span><span class="sxs-lookup"><span data-stu-id="b30cb-146">Guidelines for tagging can be viewed by selecting the **Tagging guidelines** option in the left pane drop-down list.</span></span> 
    
5. <span data-ttu-id="b30cb-147">После того как вы закончите маркировку всех файлов в списке и будете готовы вычислить результаты, нажмите кнопку **вычислить**.</span><span class="sxs-lookup"><span data-stu-id="b30cb-147">After you finish tagging all files in the list and are ready to calculate the results, click **Calculate**.</span></span> <span data-ttu-id="b30cb-148">Отображается вкладка **Отслеживание** .</span><span class="sxs-lookup"><span data-stu-id="b30cb-148">The **Track** tab is displayed.</span></span> 
    
## <a name="working-with-the-sample-files-list"></a><span data-ttu-id="b30cb-149">Работа со списком образцов файлов</span><span class="sxs-lookup"><span data-stu-id="b30cb-149">Working with the sample files list</span></span>

<span data-ttu-id="b30cb-150">Список "примеры файлов" позволяет просматривать список файлов в учебном образце и выполнять различные действия с одним или несколькими файлами.</span><span class="sxs-lookup"><span data-stu-id="b30cb-150">The sample files list allows you to view a list of the files in a training sample and perform various action on one or more files.</span></span> <span data-ttu-id="b30cb-151">На вкладке **тег** **релевантности** \> в области слева " **примеры файлов** " отображается список образцов файлов для обработки с процессами оценки, обучения, отслеживания и несоответствий.</span><span class="sxs-lookup"><span data-stu-id="b30cb-151">In the **Relevance** \> **Tag** tab, the **Sample files** left pane displays a list of sample files for processing with Assessment, Training, Catch-up, and Inconsistencies processes.</span></span> 
  
1. <span data-ttu-id="b30cb-152">На вкладке **тег \> релевантности** в раскрывающемся списке области слева выберите пункт файлы примеров.</span><span class="sxs-lookup"><span data-stu-id="b30cb-152">In the **Relevance \> Tag** tab, select the Sample files in the left pane drop-down list.</span></span> <span data-ttu-id="b30cb-153">Примеры файлов перечислены в левой области.</span><span class="sxs-lookup"><span data-stu-id="b30cb-153">The sample files are listed in the left pane.</span></span> 
    
    ![Список примеров файлов на вкладке "Релевантность" > "Добавление тегов"](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. <span data-ttu-id="b30cb-155">Выберите определенный пример или номер файла, введя или выбрав его номер в полях **Sample** или **File** .</span><span class="sxs-lookup"><span data-stu-id="b30cb-155">Select a specific sample or file number by entering or selecting its number in the **Sample** or **File** boxes.</span></span> 
    
  -   - <span data-ttu-id="b30cb-156">Номер последовательности файлов указан в левом столбце списка отображаемых файлов на вкладке **тег** . Щелкнув заголовок, исходный порядок отображения файлов возвращается в исходный порядок.</span><span class="sxs-lookup"><span data-stu-id="b30cb-156">A file sequence number is listed in the left column of the displayed file list on the **Tag** tab. By clicking the header, the original displayed order of the files returns to its original order.</span></span> 
    
  - <span data-ttu-id="b30cb-157">При нажатии строки файла в правой панели отображается его содержимое.</span><span class="sxs-lookup"><span data-stu-id="b30cb-157">Clicking on a file row displays its content in the right pane.</span></span>
    
  - <span data-ttu-id="b30cb-158">Переходить между файлами в текущем примере с помощью нижних параметров строки меню.</span><span class="sxs-lookup"><span data-stu-id="b30cb-158">Navigate between files in the current sample by using the lower menu bar options.</span></span> <span data-ttu-id="b30cb-159">Кроме того, доступны сочетания клавиш для навигации.</span><span class="sxs-lookup"><span data-stu-id="b30cb-159">In addition, navigational keyboard shortcuts are available:</span></span>
    
    <span data-ttu-id="b30cb-160">Переход к первому файлу в примере: Shift + Ctrl +\<</span><span class="sxs-lookup"><span data-stu-id="b30cb-160">To navigate to the first file in the sample: Shift + Ctrl + \<</span></span>
    
    <span data-ttu-id="b30cb-161">Переход к предыдущему файлу в примере: Shift +\<</span><span class="sxs-lookup"><span data-stu-id="b30cb-161">To navigate to the previous file in the sample: Shift + \<</span></span>
    
    <span data-ttu-id="b30cb-162">Переход к следующему файлу в примере: Shift +\></span><span class="sxs-lookup"><span data-stu-id="b30cb-162">To navigate to the next file in the sample: Shift + \></span></span>
    
    <span data-ttu-id="b30cb-163">Переход к последнему файлу в примере: Shift + Ctrl +\></span><span class="sxs-lookup"><span data-stu-id="b30cb-163">To navigate to the last file in the sample: Shift + Ctrl + \></span></span>
    
## <a name="see-also"></a><span data-ttu-id="b30cb-164">См. также</span><span class="sxs-lookup"><span data-stu-id="b30cb-164">See also</span></span>

[<span data-ttu-id="b30cb-165">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="b30cb-165">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b30cb-166">Понимание оценки релевантности</span><span class="sxs-lookup"><span data-stu-id="b30cb-166">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b30cb-167">Маркировка и оценка</span><span class="sxs-lookup"><span data-stu-id="b30cb-167">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b30cb-168">Анализ релевантности отслеживания</span><span class="sxs-lookup"><span data-stu-id="b30cb-168">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b30cb-169">Выбор на основе результатов</span><span class="sxs-lookup"><span data-stu-id="b30cb-169">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b30cb-170">Анализ релевантности тестирования</span><span class="sxs-lookup"><span data-stu-id="b30cb-170">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

