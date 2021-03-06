---
title: 'Режим специальных возможностей SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Узнайте, как использовать режим доступности при обучении модели в SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515152"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="4f772-103">Режим специальных возможностей SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4f772-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="4f772-104">В [SharePoint Syntex](index.md)пользователи могут включить режим доступности на всех этапах обучения модели (метка, поезд, тест) при работе с примерными документами.</span><span class="sxs-lookup"><span data-stu-id="4f772-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="4f772-105">Использование режима доступности может помочь пользователям с низкой точки зрения упростить доступ к клавиатуре при навигации и метке элементов в просмотре документов.</span><span class="sxs-lookup"><span data-stu-id="4f772-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="4f772-106">Это помогает пользователям использовать свои клавиатуры для навигации по тексту в зрительном окантовке документа и услышать повествование не только выбранных значений, но и действий (например, маркировки или удаления меток из выбранного текста) или предсказания значений меток при подготовке модели дополнительными примерными документами.</span><span class="sxs-lookup"><span data-stu-id="4f772-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Режим доступности](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="4f772-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4f772-108">Requirements</span></span>

<span data-ttu-id="4f772-109">Чтобы услышать звук повествования, включите приложение [Рассказчик](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) в настройках диктора в вашей системе Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4f772-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Включив рассказчик](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="4f772-111">Маркировка для пользователей клавиатуры</span><span class="sxs-lookup"><span data-stu-id="4f772-111">Labeling for keyboard users</span></span>

<span data-ttu-id="4f772-112">Для пользователей клавиатуры с помощью режима доступности, если вы помечены текстом в примере документа в зритель, вы можете использовать следующие клавиши:</span><span class="sxs-lookup"><span data-stu-id="4f772-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="4f772-113">Вкладка. Перемещает вас вперед и выбирает следующее слово.</span><span class="sxs-lookup"><span data-stu-id="4f772-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="4f772-114">Tab + Shift: перемещает вас назад и выбирает предыдущее слово.</span><span class="sxs-lookup"><span data-stu-id="4f772-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="4f772-115">Введите: Метка или удаление метки из выбранного слова.</span><span class="sxs-lookup"><span data-stu-id="4f772-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="4f772-116">Правая стрелка. Перемещает вас вперед через отдельные символы в выбранном слове.</span><span class="sxs-lookup"><span data-stu-id="4f772-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="4f772-117">Левая стрелка. Перемещает вас назад через отдельные символы в выбранном слове.</span><span class="sxs-lookup"><span data-stu-id="4f772-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="4f772-118">Если вы помечены несколькими словами для одной метки, необходимо пометить каждое слово.</span><span class="sxs-lookup"><span data-stu-id="4f772-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="4f772-119">Повествование</span><span class="sxs-lookup"><span data-stu-id="4f772-119">Narration</span></span>

<span data-ttu-id="4f772-120">Для пользователей narrator, использующих режим доступности, используйте ту же навигацию клавиатуры, что и для пользователей клавиатуры, чтобы просмотреть пример документа в зрительском окании.</span><span class="sxs-lookup"><span data-stu-id="4f772-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="4f772-121">При переходе по примеру документов и значениям строки меток диктор даст пользователю следующие звуковые подсказки:</span><span class="sxs-lookup"><span data-stu-id="4f772-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="4f772-122">При использовании клавиатуры для навигации по просмотру документов аудиовектор будет укаварить выбранную строку.</span><span class="sxs-lookup"><span data-stu-id="4f772-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="4f772-123">В выбранной строке аудиовектор будет укаварить каждого символа в строке при выборе их с помощью клавиш правой или левой стрелки.</span><span class="sxs-lookup"><span data-stu-id="4f772-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="4f772-124">Если выбрана строка, помеченная меткой, диктор указанит значение, а затем "помечено".</span><span class="sxs-lookup"><span data-stu-id="4f772-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="4f772-125">Например, если значение метки "Contoso", оно будет называться "Costoso метка".</span><span class="sxs-lookup"><span data-stu-id="4f772-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="4f772-126">На вкладке обучение, если выбрать строку в только предсказаемом зрительском документе, звук диктора будет оговарить значение, а затем "предсказать".</span><span class="sxs-lookup"><span data-stu-id="4f772-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="4f772-127">Это происходит, когда обучение предсказывает значение в файле, которое не совпадает с тем, что было помечено пользователем.</span><span class="sxs-lookup"><span data-stu-id="4f772-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="4f772-128">На вкладке обучение при выборе строки для просмотра документов, которая была помечена и предсказана, звук диктора будет оговарить значение, а затем "помечено и предсказано".</span><span class="sxs-lookup"><span data-stu-id="4f772-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="4f772-129">Это происходит при успешном обучении и совпадении между прогнозируемым значением и меткой пользователя.</span><span class="sxs-lookup"><span data-stu-id="4f772-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="4f772-130">После того, как строка будет помечена или метка удалена в зрительском окте, звук диктора предупредит вас сохранить изменения перед выходом.</span><span class="sxs-lookup"><span data-stu-id="4f772-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f772-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4f772-131">See Also</span></span>

[<span data-ttu-id="4f772-132">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="4f772-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="4f772-133">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="4f772-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



