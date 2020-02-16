---
title: Установка параметра игнорировать текст для анализа в Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Узнайте, как определить правило для игнорирования определенного текста при использовании модулей анализа и обработки в Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 440393061fef9b5a3c946322307fcafd034be81c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081142"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2b6c3-103">Установка параметра игнорировать текст для анализа в Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2b6c3-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="2b6c3-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2b6c3-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="2b6c3-106">Функция ignore Text может быть применена ко всем или любым из следующих дополнительных модулей обнаружения электронных данных: Analyze (почти-дубликаты, цепочки электронной почты, темы) и релевантность.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="2b6c3-107">Пропущенный текст не будет отображаться в отображаемых файлах, а анализ и вычисления будут отклонять пропущенный текст.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="2b6c3-108">Если функция Ignore Text была ранее определена для модулей, которые уже запущены, то параметр игнорировать текст теперь будет защищен от изменения.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="2b6c3-109">Однако функция пропуска текста для модуля релевантности по-прежнему может измениться в любое время.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="2b6c3-110">Как применяются фильтры "игнорировать текстовые"</span><span class="sxs-lookup"><span data-stu-id="2b6c3-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="2b6c3-111">Несколько текстовых фильтров Ignore применяются в порядке их ввода.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="2b6c3-112">Чтобы изменить порядок, в котором они применяются, их необходимо удалить и повторно ввести в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="2b6c3-113">Например, если текстовое содержимое: "ДЕНИСА Боб Марии канун", ниже приведены примеры игнорируемых текстовых записей и результатов.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="2b6c3-114">**Игнорировать текстовые записи**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="2b6c3-115">**Results**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-115">**Results**</span></span> <br/> |
|<span data-ttu-id="2b6c3-116">"АЛИСА", "БОБ, ИВАН"</span><span class="sxs-lookup"><span data-stu-id="2b6c3-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="2b6c3-117">"КАНУН ДЕНИСА"</span><span class="sxs-lookup"><span data-stu-id="2b6c3-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="2b6c3-118">"АЛИСА", "БОБ ALICE"</span><span class="sxs-lookup"><span data-stu-id="2b6c3-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="2b6c3-119">"ДЕНИСА ИВАН, КАНУН"</span><span class="sxs-lookup"><span data-stu-id="2b6c3-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="2b6c3-120">Вторая запись Ignore Text не реализована, так как строка не найдена, как показано после применения первого игнорируемого текста.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="2b6c3-121">Использование регулярных выражений при определении игнорируемого текста</span><span class="sxs-lookup"><span data-stu-id="2b6c3-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="2b6c3-122">Регулярные выражения поддерживаются при определении игнорируемого текста.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="2b6c3-123">Ниже приведены примеры синтаксиса и использования регулярных выражений:</span><span class="sxs-lookup"><span data-stu-id="2b6c3-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="2b6c3-124">Чтобы удалить (пропустить) текст с начала до конца строки, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2b6c3-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="2b6c3-125">где "Begin" — это исходное вхождение этой строки в строке.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="2b6c3-126">Например, для следующего текста:</span><span class="sxs-lookup"><span data-stu-id="2b6c3-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="2b6c3-127">**"Это первое предложение и первая строка**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="2b6c3-128">**Это второе предложение и вторая строка "**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="2b6c3-129">Сначала регулярное выражение (.\*) $ приведет к следующим результатам:</span><span class="sxs-lookup"><span data-stu-id="2b6c3-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="2b6c3-130">**"Это**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-130">**"This is**</span></span>
    
    <span data-ttu-id="2b6c3-131">**Это второе предложение и вторая строка "**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="2b6c3-132">Для удаления заявлений об отказе и юридических заявлениях автоматически вставляется в конце почтовых потоков:</span><span class="sxs-lookup"><span data-stu-id="2b6c3-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="2b6c3-133">где "Begin" и "End" — это уникальные строки в начале и конце перенесенного текста абзаца.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="2b6c3-134">Например, следующее регулярное выражение удалит заявления об отказе и юридические заявления, которые были в цепочке электронной почты между начальной и конечной строкой:</span><span class="sxs-lookup"><span data-stu-id="2b6c3-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="2b6c3-135">**Это сообщение содержит конфиденциальные сведения (| \s)\*если необходима проверка, запросите версию для жесткого копирования.**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="2b6c3-136">Чтобы удалить заявление об отказе (в том числе специальные символы), выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="2b6c3-137">Например, для следующего текста (со сведениями об отказе, представленном здесь x):</span><span class="sxs-lookup"><span data-stu-id="2b6c3-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="2b6c3-138">**/\*\ В этом сообщении содержатся конфиденциальные данные. XXXX XXXX**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="2b6c3-139">**XXXX XXXX XXXX XXXX XXXX XXXX**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="2b6c3-140">\**XXXX XXXX если необходима проверка, запросите версию для жесткого копирования. /\*\**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="2b6c3-141">регулярное выражение для удаления приведенного выше заявления об отказе должно быть следующим:</span><span class="sxs-lookup"><span data-stu-id="2b6c3-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="2b6c3-142">**\/\\*\\Это сообщение содержит конфиденциальные\.сведения (| \s)\* если необходима проверка, запросите версию\. для жесткого копирования.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="2b6c3-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="2b6c3-143">Правила регулярных выражений:</span><span class="sxs-lookup"><span data-stu-id="2b6c3-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="2b6c3-144">Все символы, не входящие в алфавит, за исключением пробелов, "_" и "-" должны предшествоваться "\".</span><span class="sxs-lookup"><span data-stu-id="2b6c3-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="2b6c3-145">Регулярное поле Икспрессион может иметь неограниченную длину.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="2b6c3-146">Пояснение и подробные сведения о синтаксисе регулярных выражений приведены в статье: [Язык регулярных выражений — краткий справочник](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2b6c3-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="2b6c3-147">Определение правила игнорирования текста</span><span class="sxs-lookup"><span data-stu-id="2b6c3-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="2b6c3-148">На вкладке **Управление \> анализом параметров \> анализа** в разделе **игнорировать текст** щелкните **+** значок, чтобы добавить правило.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="2b6c3-149">В диалоговом окне **Добавление игнорируемого текста** в поле **имя** введите имя правила игнорировать текст.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![Добавление текста, который нужно игнорировать](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="2b6c3-151">В **текстовом** поле введите текст, который будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="2b6c3-152">Текстовое поле допускает неограниченное число символов.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="2b6c3-153">Как показано в предыдущем окне, нажмите **лампочка** , чтобы увидеть общие правила синтаксиса для правила игнорировать текст.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="2b6c3-154">При необходимости установите флажок учитывать **регистр** .</span><span class="sxs-lookup"><span data-stu-id="2b6c3-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="2b6c3-155">В списке **Применить к** выберите дополнительные модули обнаружения электронных данных, для которых применяется определение.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="2b6c3-156">Если вы хотите выполнить тестовый запуск для примера текста, введите образец текста в текстовом поле **Вход** и нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="2b6c3-157">Результаты отображаются в текстовом поле **вывод** .</span><span class="sxs-lookup"><span data-stu-id="2b6c3-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="2b6c3-158">Нажмите кнопку **ОК** , чтобы сохранить правило игнорирования текста.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="2b6c3-159">Отображается заданное правило игнорирования текста.</span><span class="sxs-lookup"><span data-stu-id="2b6c3-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![Указание имени для игнорируемого текста](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="2b6c3-161">См. также</span><span class="sxs-lookup"><span data-stu-id="2b6c3-161">See also</span></span>

[<span data-ttu-id="2b6c3-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2b6c3-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2b6c3-163">Сведения о сходстве документов</span><span class="sxs-lookup"><span data-stu-id="2b6c3-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b6c3-164">Настройка параметров анализа</span><span class="sxs-lookup"><span data-stu-id="2b6c3-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b6c3-165">Настройка дополнительных параметров анализа</span><span class="sxs-lookup"><span data-stu-id="2b6c3-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2b6c3-166">Просмотр результатов анализа</span><span class="sxs-lookup"><span data-stu-id="2b6c3-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

