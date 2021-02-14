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
description: Узнайте, как обнаруживать ошибки и опечатки в запросе по ключевым словам для поиска контента, прежде чем запускать поиск.
ms.openlocfilehash: 250db272014d5801bfb3927d14072eea94bd635f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818098"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="2e414-103">Проверка запроса веб-части "Поиск контента" на ошибки</span><span class="sxs-lookup"><span data-stu-id="2e414-103">Check your Content Search query for errors</span></span>

<span data-ttu-id="2e414-104">При создании или редактировании поиска контента microsoft 365 может проверить запрос на неподсвеченные символы и операторы boolean нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="2e414-104">When you create or edit a Content Search, you can have Microsoft 365 check your query for unsupported characters and lowercase Boolean operators.</span></span> <span data-ttu-id="2e414-105">Как это сделать?</span><span class="sxs-lookup"><span data-stu-id="2e414-105">How?</span></span> <span data-ttu-id="2e414-106">Просто **щелкните "Проверить запрос на опечатки"** на странице запроса "Поиск контента".</span><span class="sxs-lookup"><span data-stu-id="2e414-106">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![Щелкните "Проверить запрос на опечатки", чтобы проверить поисковый запрос на неподтверченные символы](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="2e414-108">Вот список неподтверченных символов, которые мы проверяем.</span><span class="sxs-lookup"><span data-stu-id="2e414-108">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="2e414-109">Неподтвердимые символы часто скрыты, и они обычно вызывают ошибку поиска или возвращают непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="2e414-109">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="2e414-110">**Смарт-кавычка** — смарт-одиночные и двойные кавычка (также называемые курсорами) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="2e414-110">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="2e414-111">В поисковом запросе можно использовать только прямые кавычки.</span><span class="sxs-lookup"><span data-stu-id="2e414-111">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="2e414-112">**Непечатаемые и печатные** символы — непечатаемые и печатные символы не представляют письменный символ, например букво-числовую символику.</span><span class="sxs-lookup"><span data-stu-id="2e414-112">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="2e414-113">К непечатаемым и управляющим символам относятся символы, которые форматируют текст или разделяют его на строки.</span><span class="sxs-lookup"><span data-stu-id="2e414-113">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="2e414-114">Знаки слева направо и справа налево **—** это символы управления, которые указывают направление текста для языков слева направо (например, английского и испанского) и языков с написанием справа налево (например, арабского и иврита).</span><span class="sxs-lookup"><span data-stu-id="2e414-114">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="2e414-115">**Операторы boolean** нижнего регистра. Если в поисковом запросе используется оператор Boolean, например **AND**, **OR** и **NOT,** он должен быть задан в верхнем регистре.</span><span class="sxs-lookup"><span data-stu-id="2e414-115">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="2e414-116">При проверке запроса на опечатки синтаксис запроса часто указывает на то, что используется boolean оператор, даже если могут использоваться операторы нижнего регистра; например,  `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="2e414-116">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="2e414-117">Что произойдет, если запрос имеет неподтверченный символ?</span><span class="sxs-lookup"><span data-stu-id="2e414-117">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="2e414-118">Если в вашем запросе найдены неподтверченные символы, отображается предупреждение о том, что найдены неподтверченные символы, и предлагается альтернатива.</span><span class="sxs-lookup"><span data-stu-id="2e414-118">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="2e414-119">Затем вы можете сохранить исходный запрос или заменить его предложенным измененным запросом.</span><span class="sxs-lookup"><span data-stu-id="2e414-119">You then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="2e414-120">Вот пример предупреждения, которое отображается после нажатия кнопки  "Проверить запрос на опечатки" для поискового запроса на предыдущем снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="2e414-120">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="2e414-121">Обратите внимание, что исходный запрос содержит интеллектуальные кавычка и буквы boolean в нижнем регистре.</span><span class="sxs-lookup"><span data-stu-id="2e414-121">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![Отображается предупреждение с рекомендуемой версией запроса](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="2e414-123">Предотвращение неподсвеченных символов в поисковых запросах</span><span class="sxs-lookup"><span data-stu-id="2e414-123">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="2e414-124">Как правило, неподтвержденные символы добавляются в запрос при копировании запроса или его частей из других приложений (например, Microsoft Word или Microsoft Excel) и их в paste в поле ключевых слов на странице запроса поиска контента.</span><span class="sxs-lookup"><span data-stu-id="2e414-124">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="2e414-125">Лучший способ избежать неподдерживаемых символов  просто ввести запрос в поле ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="2e414-125">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="2e414-126">Вы также можете скопировать запрос из Word или Excel, а затем вкопировать его в обычный текстовый редактор, например Microsoft Notepad.</span><span class="sxs-lookup"><span data-stu-id="2e414-126">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="2e414-127">Сохраните текстовый файл и выберите **ANSI** в выпадаемом списке "Кодировка". </span><span class="sxs-lookup"><span data-stu-id="2e414-127">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="2e414-128">Так вы удалите все форматирование и неподдерживаемые символы.</span><span class="sxs-lookup"><span data-stu-id="2e414-128">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="2e414-129">Затем вы можете скопировать запрос из текстового файла и вставить его в поле запроса по ключевым словам.</span><span class="sxs-lookup"><span data-stu-id="2e414-129">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
