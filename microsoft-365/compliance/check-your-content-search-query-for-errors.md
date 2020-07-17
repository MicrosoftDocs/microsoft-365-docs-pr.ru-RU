---
title: Проверка запроса веб-части "Поиск контента" на ошибки
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Узнайте, как обнаруживать ошибки и опечатки в запросе ключевых слов для поиска контента перед выполнением поиска.
ms.openlocfilehash: 250db272014d5801bfb3927d14072eea94bd635f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818098"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="1f45c-103">Проверка запроса веб-части "Поиск контента" на ошибки</span><span class="sxs-lookup"><span data-stu-id="1f45c-103">Check your Content Search query for errors</span></span>

<span data-ttu-id="1f45c-104">При создании или изменении поиска контента можно использовать Microsoft 365, чтобы проверить запрос на наличие неподдерживаемых символов и логических операторов нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="1f45c-104">When you create or edit a Content Search, you can have Microsoft 365 check your query for unsupported characters and lowercase Boolean operators.</span></span> <span data-ttu-id="1f45c-105">Как это сделать?</span><span class="sxs-lookup"><span data-stu-id="1f45c-105">How?</span></span> <span data-ttu-id="1f45c-106">Просто нажмите кнопку **проверить запрос на наличие опечаток** на странице запрос поиска контента.</span><span class="sxs-lookup"><span data-stu-id="1f45c-106">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![Нажмите кнопку "проверить запрос на опечатки", чтобы проверить запрос поиска на наличие неподдерживаемых символов](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="1f45c-108">Ниже приведен список неподдерживаемых символов, которые мы проверяем.</span><span class="sxs-lookup"><span data-stu-id="1f45c-108">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="1f45c-109">Неподдерживаемые символы часто скрываются, и они, как правило, вызывают ошибку поиска или возвращают нежелательные результаты.</span><span class="sxs-lookup"><span data-stu-id="1f45c-109">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="1f45c-110">**Парные** кавычки — разумные одинарные и двойные кавычки (также называемые фигурными кавычками) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1f45c-110">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="1f45c-111">В поисковом запросе можно использовать только прямые кавычки.</span><span class="sxs-lookup"><span data-stu-id="1f45c-111">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="1f45c-112">Непечатаемые и непечатаемые **символы** — непечатаемые и непечатаемые символы не представляют собой записанный символ, например, буквенно-цифровой символ.</span><span class="sxs-lookup"><span data-stu-id="1f45c-112">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="1f45c-113">К непечатаемым и управляющим символам относятся символы, которые форматируют текст или разделяют его на строки.</span><span class="sxs-lookup"><span data-stu-id="1f45c-113">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="1f45c-114">**Метки слева направо и справа налево** — эти метки представляют собой управляющие символы, используемые для обозначения направления текста для языков с письмом слева направо (например, английский и испанский) и языков с письмом справа налево (например, арабского языка и иврита).</span><span class="sxs-lookup"><span data-stu-id="1f45c-114">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="1f45c-115">**Логические операторы в нижнем регистре** — если вы используете логический оператор (например, **and**, **or**), а **не** в поисковом запросе, он должен быть задан в верхнем регистре.</span><span class="sxs-lookup"><span data-stu-id="1f45c-115">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="1f45c-116">Когда мы проверяем запрос на опечатки, синтаксис запроса часто указывает на то, что логический оператор используется, несмотря на то, что можно использовать операторы нижнего регистра; Пример: `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="1f45c-116">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="1f45c-117">Что произойдет, если запрос содержит неподдерживаемый символ?</span><span class="sxs-lookup"><span data-stu-id="1f45c-117">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="1f45c-118">Если в запросе найдены неподдерживаемые символы, отображается предупреждение с сообщением о том, что обнаружены неподдерживаемые символы, и предлагается альтернативный вариант.</span><span class="sxs-lookup"><span data-stu-id="1f45c-118">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="1f45c-119">После этого вы можете оставить исходный запрос или заменить его предложенным исправленным запросом.</span><span class="sxs-lookup"><span data-stu-id="1f45c-119">You then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="1f45c-120">Ниже приведен пример сообщения с предупреждением, которое отображается после нажатия кнопки **проверить запрос на наличие опечаток** для поискового запроса на предыдущем снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="1f45c-120">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="1f45c-121">Обратите внимание, что исходный запрос содержит логические операторы и логические операторы для кавычек и строчных букв.</span><span class="sxs-lookup"><span data-stu-id="1f45c-121">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![Отображается предупреждающее сообщение с предлагаемой версией запроса](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="1f45c-123">Как предотвратить неподдерживаемые символы в поисковых запросах</span><span class="sxs-lookup"><span data-stu-id="1f45c-123">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="1f45c-124">Неподдерживаемые символы обычно добавляются в запрос при копировании запроса или частей запроса из других приложений (например, Microsoft Word или Microsoft Excel) и их вставке в поле ключевое слово на странице запрос поиска контента.</span><span class="sxs-lookup"><span data-stu-id="1f45c-124">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="1f45c-125">Лучший способ избежать неподдерживаемых символов  просто ввести запрос в поле ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="1f45c-125">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="1f45c-126">Кроме того, вы можете скопировать запрос из Word или Excel, а затем вставить его в виде обычного текстового редактора, например Microsoft Notepad.</span><span class="sxs-lookup"><span data-stu-id="1f45c-126">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="1f45c-127">Сохраните текстовый файл и выберите **ANSI** в раскрывающемся списке **Кодировка** .</span><span class="sxs-lookup"><span data-stu-id="1f45c-127">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="1f45c-128">Так вы удалите все форматирование и неподдерживаемые символы.</span><span class="sxs-lookup"><span data-stu-id="1f45c-128">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="1f45c-129">Затем вы можете скопировать запрос из текстового файла и вставить его в поле запроса по ключевым словам.</span><span class="sxs-lookup"><span data-stu-id="1f45c-129">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
