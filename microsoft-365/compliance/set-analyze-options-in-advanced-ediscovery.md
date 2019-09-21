---
title: Настройка параметров анализа в Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Ознакомьтесь с инструкциями по настройке параметров для процесса анализа в Office 365 Advanced eDiscovery, включая почти повторяющиеся, почтовые потоки и темы.  '
ms.openlocfilehash: 6d853d701613fcbe61c6e98b3bf55ae99eefd901
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090607"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ece5e-103">Настройка параметров анализа в Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ece5e-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="ece5e-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ece5e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ece5e-106">В разделе Advanced eDiscovery задайте параметры анализа перед выполнением анализа.</span><span class="sxs-lookup"><span data-stu-id="ece5e-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="ece5e-107">Настройка параметров анализа</span><span class="sxs-lookup"><span data-stu-id="ece5e-107">Set Analyze options</span></span>

<span data-ttu-id="ece5e-108">Откройте **окно \> подготовка к анализу** \> **программы установки**.</span><span class="sxs-lookup"><span data-stu-id="ece5e-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="ece5e-109">Отображается следующее окно.</span><span class="sxs-lookup"><span data-stu-id="ece5e-109">The following window is displayed.</span></span>
  
![Настройка параметров анализа](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="ece5e-111">**Почти повторяющиеся и почтовые потоки** Установите этот флажок, если хотите выполнить анализ.</span><span class="sxs-lookup"><span data-stu-id="ece5e-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="ece5e-112">Этот параметр выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ece5e-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="ece5e-113">**Сходство документов** Введите пороговое значение почти дублирующихся или примите значение по умолчанию, равное 65%.</span><span class="sxs-lookup"><span data-stu-id="ece5e-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="ece5e-114">**Темы** Установите этот флажок, чтобы обработать все файлы и назначить им темы.</span><span class="sxs-lookup"><span data-stu-id="ece5e-114">**Themes**Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="ece5e-115">По умолчанию этот флажок не установлен.</span><span class="sxs-lookup"><span data-stu-id="ece5e-115">By default, this check box is not selected.</span></span> <span data-ttu-id="ece5e-116">Введите следующие параметры, если хотите выполнить обработку тем.</span><span class="sxs-lookup"><span data-stu-id="ece5e-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="ece5e-117">**Максимальное число тем** Введите или выберите значение количества создаваемых тем.</span><span class="sxs-lookup"><span data-stu-id="ece5e-117">**Max number of themes**Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="ece5e-118">По умолчанию используется значение 200.</span><span class="sxs-lookup"><span data-stu-id="ece5e-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ece5e-119">Увеличение числа тем влияет на производительность, а также на возможность обобщения темы.</span><span class="sxs-lookup"><span data-stu-id="ece5e-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="ece5e-120">Чем больше количество тем, тем больше их детализация.</span><span class="sxs-lookup"><span data-stu-id="ece5e-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="ece5e-121">Например, если в наборе 50 тем есть тема, например "Баскетбалл, Спурс, обтравочные части, Лакерс"; 300 темы могут включать в себя отдельные темы: "Спурс", "обтравочные отделы", "Лакерс".</span><span class="sxs-lookup"><span data-stu-id="ece5e-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="ece5e-122">Если у вас нет сведений о теме "Баскетбалл" и эта функция не используется для ЕКА, то, возможно, будет полезна тема "Баскетбалл".</span><span class="sxs-lookup"><span data-stu-id="ece5e-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="ece5e-123">Но если в обработке слишком много тем, слово "Баскетбалл" может оказаться недоступным, и оно может не знать о том, что Спурс и отрезки хорошо подходят Баскетбалл темы для проверки, а не элементы, которые переходят на загрузку и используют для перекрестия.</span><span class="sxs-lookup"><span data-stu-id="ece5e-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="ece5e-124">**Предлагаемые темы** Вы можете предложить слова темы для управления обработкой тем.</span><span class="sxs-lookup"><span data-stu-id="ece5e-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="ece5e-125">Расширенное обнаружение электронных данных позволяет сосредоточиться на этих предложенных словах и попытаться создать одну или несколько релевантных тем на основе параметров "максимальное количество тем".</span><span class="sxs-lookup"><span data-stu-id="ece5e-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="ece5e-126">Например, если предлагаемое слово "Computer" и вы указали "2" как "максимальное количество тем", Расширенное обнаружение электронных данных попытается создать две темы, которые относятся к слову "Computer".</span><span class="sxs-lookup"><span data-stu-id="ece5e-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="ece5e-127">Эти две темы могут быть "программным обеспечением компьютера" и "компьютерным аппаратным обеспечением", например.</span><span class="sxs-lookup"><span data-stu-id="ece5e-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![Добавление предложенной темы](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="ece5e-129">Чтобы просмотреть, добавить или изменить предложенные темы, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="ece5e-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="ece5e-130">На панели **Предлагаемые темы** нажмите значок **Добавить** ![значок](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) , чтобы добавить тему.</span><span class="sxs-lookup"><span data-stu-id="ece5e-130">In the **Suggested themes** panel, click the **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="ece5e-131">В области **Добавление предлагаемой темы** добавьте слова, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="ece5e-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="ece5e-132">В разделе **число тем**выберите значение, чтобы определить число тем, которые будут попытаться создать дополнительное обнаружение электронных данных для этих слов (по умолчанию — 1 тема).</span><span class="sxs-lookup"><span data-stu-id="ece5e-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="ece5e-133">Нажмите кнопку **сохранить** , а затем закройте диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="ece5e-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ece5e-134">Общее число тем включает Рекомендуемые темы.</span><span class="sxs-lookup"><span data-stu-id="ece5e-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="ece5e-135">Общее количество предлагаемых тем не может превышать общее количество тем.</span><span class="sxs-lookup"><span data-stu-id="ece5e-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="ece5e-136">При наличии большого количества предлагаемых тем, относящихся к общим темам, система обнаруживает только несколько тем "романских" тем, так как большинство тем выделено для предлагаемых тем.</span><span class="sxs-lookup"><span data-stu-id="ece5e-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="ece5e-137">**Режим** В раскрывающемся списке выберите **темы** :</span><span class="sxs-lookup"><span data-stu-id="ece5e-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="ece5e-138">**Create and Apply Model**: вычисляет темы по моделям из сегмента файлов, а затем распространяет файлы между ними.</span><span class="sxs-lookup"><span data-stu-id="ece5e-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="ece5e-139">**CREATE Model**: вычисляет модель тем из сегмента файлов.</span><span class="sxs-lookup"><span data-stu-id="ece5e-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="ece5e-140">Процесс применения разделения файлов выполняется отдельно в другое время.</span><span class="sxs-lookup"><span data-stu-id="ece5e-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="ece5e-141">**Apply Model**: этот параметр отображается только в том случае, если модель была создана ранее и еще не применена.</span><span class="sxs-lookup"><span data-stu-id="ece5e-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="ece5e-142">Это позволит разделить файлы на основе тем.</span><span class="sxs-lookup"><span data-stu-id="ece5e-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="ece5e-143">Вы также можете [задать игнорировать текст](set-ignore-text-in-advanced-ediscovery.md) и [задать анализ расширенных параметров](set-analyze-advanced-settings-in-advanced-ediscovery.md) для анализа.</span><span class="sxs-lookup"><span data-stu-id="ece5e-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="ece5e-144">После настройки этих параметров нажмите кнопку **анализ** для запуска.</span><span class="sxs-lookup"><span data-stu-id="ece5e-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="ece5e-145">Отображаются [результаты анализа просмотра](view-analyze-results-in-advanced-ediscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="ece5e-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ece5e-146">См. также</span><span class="sxs-lookup"><span data-stu-id="ece5e-146">See also</span></span>

[<span data-ttu-id="ece5e-147">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ece5e-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ece5e-148">Сведения о сходстве документов</span><span class="sxs-lookup"><span data-stu-id="ece5e-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ece5e-149">Настройка игнорируемого текста</span><span class="sxs-lookup"><span data-stu-id="ece5e-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ece5e-150">Настройка дополнительных параметров на вкладке "Анализ"</span><span class="sxs-lookup"><span data-stu-id="ece5e-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ece5e-151">Просмотр результатов анализа</span><span class="sxs-lookup"><span data-stu-id="ece5e-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

