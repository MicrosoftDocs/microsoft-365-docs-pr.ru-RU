---
title: Настройка параметра "Игнорировать текст" для анализа в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: Узнайте, как определить правило для игнорирования определенного текста при использовании модулей анализа и обработки в Advanced eDiscovery.
ms.openlocfilehash: f61724e3964ff4ba7f099dbfb4411e19db258adc
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663474"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a><span data-ttu-id="7723c-103">Настройка параметра "Игнорировать текст" для анализа в Advanced eDiscovery (классическая)</span><span class="sxs-lookup"><span data-stu-id="7723c-103">Set Ignore Text option for Analyze in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="7723c-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="7723c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7723c-106">Функция "Игнорировать текст" может применяться к всем или любым из следующих модулей Advanced eDiscovery: анализ (почти дубликаты, потоки электронной почты, темы) и релевантность.</span><span class="sxs-lookup"><span data-stu-id="7723c-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="7723c-107">Пропущенный текст не будет отображаться в файлах, отображаемом в релевантности, а анализ и вычисления отклонят пропущенный текст.</span><span class="sxs-lookup"><span data-stu-id="7723c-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="7723c-108">Если функция "Игнорировать текст" ранее была определена для уже запускаемого модуля, параметр "Игнорировать текст" теперь будет защищен от изменения.</span><span class="sxs-lookup"><span data-stu-id="7723c-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="7723c-109">Тем не менее, функцию "Игнорировать текст" для модуля релевантности можно изменить в любое время.</span><span class="sxs-lookup"><span data-stu-id="7723c-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="7723c-110">Как применяются фильтры игнорирования текста</span><span class="sxs-lookup"><span data-stu-id="7723c-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="7723c-111">Несколько фильтров ignore Text применяются в том порядке, в который они были введены.</span><span class="sxs-lookup"><span data-stu-id="7723c-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="7723c-112">Чтобы изменить порядок их применении, их необходимо удалить и повторно ввели в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="7723c-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="7723c-113">Например, если текстовое содержимое имеет следующий текст: "BOB BOB ALICEРОВОГО СИБ", примеры записей ignore Text и результаты, полученные этими записями:</span><span class="sxs-lookup"><span data-stu-id="7723c-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results these entries produce:</span></span>

|<span data-ttu-id="7723c-114">**Игнорирование текстовых записей**</span><span class="sxs-lookup"><span data-stu-id="7723c-114">**Ignore Text entries**</span></span> <br/> |<span data-ttu-id="7723c-115">**Results**</span><span class="sxs-lookup"><span data-stu-id="7723c-115">**Results**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="7723c-116">"ALICE", "BOB ALICE"</span><span class="sxs-lookup"><span data-stu-id="7723c-116">"ALICE", "BOB CAROL"</span></span>  <br/> |<span data-ttu-id="7723c-117">"DAVE DAVE"</span><span class="sxs-lookup"><span data-stu-id="7723c-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="7723c-118">"ALICE", "BOB ALICE ALICE ALICE ALICE"</span><span class="sxs-lookup"><span data-stu-id="7723c-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |<span data-ttu-id="7723c-119">"BOB BOB DAVE"</span><span class="sxs-lookup"><span data-stu-id="7723c-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="7723c-120">Вторая запись "Игнорировать текст" не реализована, так как строка не найдена после первого обращения к тексту игнорирования.</span><span class="sxs-lookup"><span data-stu-id="7723c-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="7723c-121">Использование регулярных выражений при определении игнорирования текста</span><span class="sxs-lookup"><span data-stu-id="7723c-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="7723c-122">Регулярные выражения поддерживаются для использования при определении игнорирования текста.</span><span class="sxs-lookup"><span data-stu-id="7723c-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="7723c-123">Ниже примеры синтаксиса регулярных выражений и их использования.</span><span class="sxs-lookup"><span data-stu-id="7723c-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="7723c-124">Чтобы удалить (игнорировать) текст из begin до конца строки:</span><span class="sxs-lookup"><span data-stu-id="7723c-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="7723c-125">где "Begin" — это начальный вхождение этой строки в строке.</span><span class="sxs-lookup"><span data-stu-id="7723c-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="7723c-126">Например, для следующего текста:</span><span class="sxs-lookup"><span data-stu-id="7723c-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="7723c-127">**"Это первое предложение и первая строка**</span><span class="sxs-lookup"><span data-stu-id="7723c-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="7723c-128">**Это второе предложение и вторая строка"**</span><span class="sxs-lookup"><span data-stu-id="7723c-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="7723c-129">Регулярное выражение сначала(. \* ) $ приведет к:</span><span class="sxs-lookup"><span data-stu-id="7723c-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="7723c-130">**"Это**</span><span class="sxs-lookup"><span data-stu-id="7723c-130">**"This is**</span></span>
    
    <span data-ttu-id="7723c-131">**Это второе предложение и вторая строка"**</span><span class="sxs-lookup"><span data-stu-id="7723c-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="7723c-132">Чтобы удалить заявления об отказе и юридические заявления, автоматически вставляемые в конце потока электронной почты:</span><span class="sxs-lookup"><span data-stu-id="7723c-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="7723c-133">где "Begin" и "End" — это уникальные строки в начале и конце текстового абзаца.</span><span class="sxs-lookup"><span data-stu-id="7723c-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="7723c-134">Например, следующее регулярное выражение удаляет заявления об отказе и юридические заявления, которые находились в потоке электронной почты между строками Begin и End:</span><span class="sxs-lookup"><span data-stu-id="7723c-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="7723c-135">**Это сообщение содержит конфиденциальную информацию (.| \s) \* Если требуется проверка, запросим версию жесткого копирования**</span><span class="sxs-lookup"><span data-stu-id="7723c-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="7723c-136">Чтобы удалить заявление об отказе (включая специальные символы):</span><span class="sxs-lookup"><span data-stu-id="7723c-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="7723c-137">Например, для следующего текста (с заявлением об отказе, представленным здесь x's):</span><span class="sxs-lookup"><span data-stu-id="7723c-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="7723c-138">**/\*\ Это сообщение содержит конфиденциальную информацию. xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="7723c-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="7723c-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="7723c-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="7723c-140">\**Xxxx xxxx Если требуется проверка, запросив версию жесткого копирования. /\*\**</span><span class="sxs-lookup"><span data-stu-id="7723c-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="7723c-141">Регулярное выражение для удаления вышеуказанного заявление об отказе должно быть:</span><span class="sxs-lookup"><span data-stu-id="7723c-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="7723c-142">**\/\\*\\Это сообщение содержит конфиденциальную \. информацию (.| \s) \* Если требуется проверка, запросим версию жесткого копирования \.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="7723c-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="7723c-143">Правила регулярных выражений:</span><span class="sxs-lookup"><span data-stu-id="7723c-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="7723c-144">Перед любыми символами, которые не являются частью алфавита, кроме пробелов, "_" и "-", должны предшествовать символы " \" .</span><span class="sxs-lookup"><span data-stu-id="7723c-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="7723c-145">Обычное поле eExpression может иметь неограниченную длину.</span><span class="sxs-lookup"><span data-stu-id="7723c-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="7723c-146">Пояснения и подробный синтаксис регулярных выражений см. в кратком справочнике по языку [регулярных выражений.](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7723c-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="7723c-147">Определение правила "Игнорировать текст"</span><span class="sxs-lookup"><span data-stu-id="7723c-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="7723c-148">На **вкладке "Управление \> \> анализом параметров"** в разделе "Игнорировать текст" щелкните значок, чтобы добавить  **+** правило.</span><span class="sxs-lookup"><span data-stu-id="7723c-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="7723c-149">В **диалоговом** окте "Добавить игнорировать текст" в поле **"Имя"** введите имя правила "Игнорировать текст".</span><span class="sxs-lookup"><span data-stu-id="7723c-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![Добавление текста, который нужно игнорировать](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="7723c-151">В **текстовом** поле введите текст, который будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="7723c-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="7723c-152">Текстовое поле допускает неограниченное количество символов.</span><span class="sxs-lookup"><span data-stu-id="7723c-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="7723c-153">Как показано в окне выше, щелкните **световой** шарик, чтобы увидеть общие рекомендации по синтаксис для правила "Игнорировать текст".</span><span class="sxs-lookup"><span data-stu-id="7723c-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="7723c-154">При **желании, в поле "С** конфиденциальным делом" выберите нужный.</span><span class="sxs-lookup"><span data-stu-id="7723c-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="7723c-155">В **списке "Применить к"** выберите модули Advanced eDiscovery, в которых необходимо применить определение.</span><span class="sxs-lookup"><span data-stu-id="7723c-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="7723c-156">Если вы хотите запустить тест для примера текста, введите пример текста в текстовое поле ввода и нажмите кнопку **"Тест".** </span><span class="sxs-lookup"><span data-stu-id="7723c-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="7723c-157">Результаты отображаются в текстовом поле **вывода.**</span><span class="sxs-lookup"><span data-stu-id="7723c-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="7723c-158">Нажмите **кнопку "ОК",** чтобы сохранить правило "Игнорировать текст".</span><span class="sxs-lookup"><span data-stu-id="7723c-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="7723c-159">Отобразилось определенное правило "Игнорировать текст".</span><span class="sxs-lookup"><span data-stu-id="7723c-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![Указание имени для игнорируемого текста](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="7723c-161">См. также</span><span class="sxs-lookup"><span data-stu-id="7723c-161">See also</span></span>

[<span data-ttu-id="7723c-162">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="7723c-162">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7723c-163">Понимание сходства документов</span><span class="sxs-lookup"><span data-stu-id="7723c-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7723c-164">Настройка параметров анализа</span><span class="sxs-lookup"><span data-stu-id="7723c-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7723c-165">Настройка дополнительных параметров анализа</span><span class="sxs-lookup"><span data-stu-id="7723c-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7723c-166">Просмотр результатов анализа</span><span class="sxs-lookup"><span data-stu-id="7723c-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

