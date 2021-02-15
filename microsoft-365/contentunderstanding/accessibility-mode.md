---
title: 'Режим доступа к синтаксисе SharePoint '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Узнайте, как использовать режим доступности при обучении модели в синтаксисе SharePoint.
ms.openlocfilehash: 32e5bd132a7a0145f03e4620545d65d1d92ff223
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "50081023"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="d457e-103">Режим доступа к синтаксисе SharePoint</span><span class="sxs-lookup"><span data-stu-id="d457e-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="d457e-104">В [Синтаксисе SharePoint](index.md)пользователи могут включить режим доступности на всех этапах обучения модели (метка, обучение, тестирование) при работе с примерами документов.</span><span class="sxs-lookup"><span data-stu-id="d457e-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="d457e-105">Использование режима доступности поможет пользователям с низким зрением упростить работу с клавиатурой при навигации и пометке элементов в представлении документов.</span><span class="sxs-lookup"><span data-stu-id="d457e-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="d457e-106">Это помогает пользователям с помощью клавиатуры переходить по тексту в средствах просмотра документов и слышать закавистку не только выбранных значений, но и действий (например, пометки или удаления меток из выбранного текста) или прогнозируемых значений меток при подготовке модели к дополнительным примерам документов.</span><span class="sxs-lookup"><span data-stu-id="d457e-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Режим доступности](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="d457e-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="d457e-108">Requirements</span></span>

<span data-ttu-id="d457e-109">Чтобы прослушать звук закадного диктора, [](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) включите приложение "Диктор" в параметрах диктора в системе Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d457e-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Включить "Диктор"](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="d457e-111">Маркировка для пользователей клавиатуры</span><span class="sxs-lookup"><span data-stu-id="d457e-111">Labeling for keyboard users</span></span>

<span data-ttu-id="d457e-112">Для пользователей клавиатуры, использующих режим доступности, если вы пометить текст в примере документа в просматриваемом документе, можно использовать следующие клавиши:</span><span class="sxs-lookup"><span data-stu-id="d457e-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="d457e-113">Tab: перемещает вас вперед и выбирает следующее слово.</span><span class="sxs-lookup"><span data-stu-id="d457e-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="d457e-114">Tab + SHIFT: перемещает вас назад и выбирает предыдущее слово.</span><span class="sxs-lookup"><span data-stu-id="d457e-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="d457e-115">Enter: Label or removes a label from the selected word.</span><span class="sxs-lookup"><span data-stu-id="d457e-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="d457e-116">Стрелка вперед: перемещает вас вперед по отдельным символам в выбранном слове.</span><span class="sxs-lookup"><span data-stu-id="d457e-116">Forward arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="d457e-117">Стрелка в обратном направлении: перемещает вас назад по отдельным символам в выбранном слове.</span><span class="sxs-lookup"><span data-stu-id="d457e-117">Backward arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="d457e-118">Если вы пометить несколько слов для одной метки, необходимо пометить каждое слово.</span><span class="sxs-lookup"><span data-stu-id="d457e-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="d457e-119">Закавкация</span><span class="sxs-lookup"><span data-stu-id="d457e-119">Narration</span></span>

<span data-ttu-id="d457e-120">Для пользователей с диктором, использующих режим доступности, используйте ту же навигацию с помощью клавиатуры, описанную для пользователей клавиатуры, чтобы просмотреть пример документа в окте просмотра.</span><span class="sxs-lookup"><span data-stu-id="d457e-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="d457e-121">При переходе по примерам документов и значениям строки метки диктор будет давать пользователю следующие звуковые подсказки:</span><span class="sxs-lookup"><span data-stu-id="d457e-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="d457e-122">При использовании клавиатуры для навигации по просмотру документов в звуковом дикторе будет передана выбранная строка.</span><span class="sxs-lookup"><span data-stu-id="d457e-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="d457e-123">В выбранной строке в звуке диктора каждый символ в строке будет передан при выборе их с помощью стрелки вперед или назад.</span><span class="sxs-lookup"><span data-stu-id="d457e-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the forward or backward arrow.</span></span>
- <span data-ttu-id="d457e-124">Если вы выберете строку, которая была помечена, диктор уканит значение, а затем "помечено".</span><span class="sxs-lookup"><span data-stu-id="d457e-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="d457e-125">Например, если метка имеет значение "Contoso", она будет называться "Costoso помечена".</span><span class="sxs-lookup"><span data-stu-id="d457e-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="d457e-126">Если на вкладке обучения выбрать в просматриваемом документе строку, которая была прогнозируема, в звуке диктора будет запротигироваться значение, а затем —"predicted".</span><span class="sxs-lookup"><span data-stu-id="d457e-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="d457e-127">Это происходит, когда обучение дает прогноз значения в файле, которое не соответствует метке пользователя.</span><span class="sxs-lookup"><span data-stu-id="d457e-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="d457e-128">Если на вкладке обучения выбрать строку в просматриваемом документе, которая была помечена и предсказуема, в звуке диктора будет заносясь значение, а затем "помечено и предугадать".</span><span class="sxs-lookup"><span data-stu-id="d457e-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="d457e-129">Это происходит при успешном обучении и совпадении между прогнозируемым значением и меткой пользователя.</span><span class="sxs-lookup"><span data-stu-id="d457e-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="d457e-130">После того как строка помечена или метка удалена в представлении, звук диктора предупредит вас о том, что вы сохраните изменения перед выходом.</span><span class="sxs-lookup"><span data-stu-id="d457e-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="d457e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d457e-131">See Also</span></span>

[<span data-ttu-id="d457e-132">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="d457e-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="d457e-133">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="d457e-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



