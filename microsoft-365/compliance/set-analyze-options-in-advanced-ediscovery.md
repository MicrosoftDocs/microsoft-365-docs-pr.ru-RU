---
title: Настройка параметров анализа в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: Просмотрите действия по настройки параметров для процесса анализа в Advanced eDiscovery, включая почти дубликаты, потоки электронной почты и темы.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ff51402cd79f2966730677a982fa5173b7e9b98
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663504"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a><span data-ttu-id="c9bde-103">Настройка параметров анализа в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="c9bde-103">Set Analyze options in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="c9bde-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="c9bde-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="c9bde-106">В Advanced eDiscovery установите параметры анализа перед запуском "Анализ".</span><span class="sxs-lookup"><span data-stu-id="c9bde-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="c9bde-107">Настройка параметров анализа</span><span class="sxs-lookup"><span data-stu-id="c9bde-107">Set Analyze options</span></span>

<span data-ttu-id="c9bde-108">Откройте **"Подготовка \> к анализу** \> **установки".**</span><span class="sxs-lookup"><span data-stu-id="c9bde-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="c9bde-109">Отобразилось следующее окно.</span><span class="sxs-lookup"><span data-stu-id="c9bde-109">The following window is displayed.</span></span>
  
![Настройка параметров анализа](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="c9bde-111">**Почти дубликаты и потоки электронной почты** Если вы хотите запустить анализ, поимите этот ящик.</span><span class="sxs-lookup"><span data-stu-id="c9bde-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="c9bde-112">Этот параметр выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c9bde-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="c9bde-113">**Сходство документов** Введите пороговое значение почти дубликатов или примите значение по умолчанию 65%.</span><span class="sxs-lookup"><span data-stu-id="c9bde-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="c9bde-114">**Темы** В этом поле можно обработать все файлы и назначить им темы.</span><span class="sxs-lookup"><span data-stu-id="c9bde-114">**Themes** Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="c9bde-115">По умолчанию этот ящик не выбран.</span><span class="sxs-lookup"><span data-stu-id="c9bde-115">By default, this check box is not selected.</span></span> <span data-ttu-id="c9bde-116">Если вы хотите выполнить обработку тем, введите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="c9bde-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="c9bde-117">**Максимальное количество тем** Введите или выберите значение для количества создавайте темы.</span><span class="sxs-lookup"><span data-stu-id="c9bde-117">**Max number of themes** Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="c9bde-118">По умолчанию используется значение 200.</span><span class="sxs-lookup"><span data-stu-id="c9bde-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c9bde-119">Увеличение числа тем влияет на производительность, а также на возможность обобщения темы.</span><span class="sxs-lookup"><span data-stu-id="c9bde-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="c9bde-120">Чем больше тем, тем более детализированной они являются.</span><span class="sxs-lookup"><span data-stu-id="c9bde-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="c9bde-121">Например, если набор из 50 тем включает тему, например "Федерация, юные, клипы, "Lakers"; 300 тем могут включать отдельные темы: "Музыка", "Клиперы", "Lakers".</span><span class="sxs-lookup"><span data-stu-id="c9bde-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="c9bde-122">Если вы не знаете тему "Федерация" и используете эту функцию для ECA, может оказаться полезной тема "Висячай".</span><span class="sxs-lookup"><span data-stu-id="c9bde-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="c9bde-123">Но если в обработке слишком много тем, возможно, вы никогда не увидите слово "Федерация" и не знаете, что "Стиминги" и "Клиперы" — это хорошие темы для просмотра, а не элементы, которые находятся в загрузке и используются для использования в качестве стрижков.</span><span class="sxs-lookup"><span data-stu-id="c9bde-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="c9bde-124">**Рекомендуемые темы** Вы можете предложить слова темы для управления обработкой тем.</span><span class="sxs-lookup"><span data-stu-id="c9bde-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="c9bde-125">Advanced eDiscovery сосредоточится на этих предлагаемых словах и попытается создать одну или несколько релевантной темы на основе параметров "Максимальное количество тем".</span><span class="sxs-lookup"><span data-stu-id="c9bde-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="c9bde-126">Например, если предлагаемым словом является "компьютер", а вы указали "2" как "Максимальное число тем", Advanced eDiscovery попытается создать две темы, которые относятся к слову "компьютер".</span><span class="sxs-lookup"><span data-stu-id="c9bde-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="c9bde-127">Эти две темы могут быть, например, "программное обеспечение компьютера" и "компьютерное оборудование".</span><span class="sxs-lookup"><span data-stu-id="c9bde-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![Добавление предложенной темы](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="c9bde-129">Чтобы просмотреть, добавить или изменить предложенные темы, нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="c9bde-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="c9bde-130">На панели **"Предложенные темы"** щелкните **значок** "Добавить ![ добавить", чтобы добавить ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) тему.</span><span class="sxs-lookup"><span data-stu-id="c9bde-130">In the **Suggested themes** panel, click the **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="c9bde-131">В области **"Добавить предложенную тему"** добавьте слова, разделенные запятой.</span><span class="sxs-lookup"><span data-stu-id="c9bde-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="c9bde-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span><span class="sxs-lookup"><span data-stu-id="c9bde-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="c9bde-133">Нажмите **кнопку** "Сохранить", а затем закроем диалог.</span><span class="sxs-lookup"><span data-stu-id="c9bde-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c9bde-134">Общее количество тем включает рекомендуемые темы.</span><span class="sxs-lookup"><span data-stu-id="c9bde-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="c9bde-135">Общее число предлагаемых тем не может превышать общее число тем.</span><span class="sxs-lookup"><span data-stu-id="c9bde-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="c9bde-136">Если по отношению к общему объему тем имеется много рекомендуемых тем, система обнаружит только несколько "новых" тем, так как большая часть тем будет выделена для рекомендуемых тем.</span><span class="sxs-lookup"><span data-stu-id="c9bde-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="c9bde-137">**Режим** В выпадаемом списке выберите параметр **"Темы":**</span><span class="sxs-lookup"><span data-stu-id="c9bde-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="c9bde-138">**Создание и применение модели:** вычисляет темы по моделям из сегмента файлов, а затем распределяет файлы между ними.</span><span class="sxs-lookup"><span data-stu-id="c9bde-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="c9bde-139">**Create model**: Calculates a themes model from a segment of the files.</span><span class="sxs-lookup"><span data-stu-id="c9bde-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="c9bde-140">Процесс применения деления файлов делается отдельно в другое время.</span><span class="sxs-lookup"><span data-stu-id="c9bde-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="c9bde-141">**Модель применения:** этот параметр отображается, только если модель была создана ранее и еще не применена.</span><span class="sxs-lookup"><span data-stu-id="c9bde-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="c9bde-142">При этом файлы будут делиться на основе тем.</span><span class="sxs-lookup"><span data-stu-id="c9bde-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="c9bde-143">Можно также настроить [игнорирование текста и](set-ignore-text-in-advanced-ediscovery.md) установить [дополнительные](set-analyze-advanced-settings-in-advanced-ediscovery.md) параметры анализа.</span><span class="sxs-lookup"><span data-stu-id="c9bde-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="c9bde-144">После настройки этих параметров нажмите кнопку **"Анализ** для запуска".</span><span class="sxs-lookup"><span data-stu-id="c9bde-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="c9bde-145">[Отображаются результаты анализа](view-analyze-results-in-advanced-ediscovery.md) представления.</span><span class="sxs-lookup"><span data-stu-id="c9bde-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="c9bde-146">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c9bde-146">Related topics</span></span>

[<span data-ttu-id="c9bde-147">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="c9bde-147">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c9bde-148">Понимание сходства документов</span><span class="sxs-lookup"><span data-stu-id="c9bde-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c9bde-149">Настройка игнорирования текста </span><span class="sxs-lookup"><span data-stu-id="c9bde-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c9bde-150">Настройка дополнительных параметров на вкладке "Анализ"</span><span class="sxs-lookup"><span data-stu-id="c9bde-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c9bde-151">Просмотр результатов анализа</span><span class="sxs-lookup"><span data-stu-id="c9bde-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

