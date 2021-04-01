---
title: Проверка запроса веб-части "Поиск контента" на ошибки
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Узнайте, как обнаруживать ошибки и опечатки в запросе по ключевому слову для поиска контента перед запуском поиска.
ms.openlocfilehash: 939ac3d227f176a0b74138107ced5dd5b7142bcd
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488216"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="55a38-103">Проверка запроса веб-части "Поиск контента" на ошибки</span><span class="sxs-lookup"><span data-stu-id="55a38-103">Check your Content Search query for errors</span></span>
  
<span data-ttu-id="55a38-104">Вот список неподтверченных символов, которые мы проверяем.</span><span class="sxs-lookup"><span data-stu-id="55a38-104">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="55a38-105">Неподтвердимые символы часто скрыты, и они обычно вызывают ошибку поиска или возвращают непреднамеренные результаты.</span><span class="sxs-lookup"><span data-stu-id="55a38-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="55a38-106">**Смарт-кавычка** — смарт-одиночные и двойные кавычка (также называемые вьющимися кавычками) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="55a38-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="55a38-107">В поисковом запросе можно использовать только прямые кавычки.</span><span class="sxs-lookup"><span data-stu-id="55a38-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="55a38-108">**Непечатаемые** символы и символы управления — непечатные и неконтентируемые символы не представляют письменного символа, например альфа-числительный символ.</span><span class="sxs-lookup"><span data-stu-id="55a38-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="55a38-109">К непечатаемым и управляющим символам относятся символы, которые форматируют текст или разделяют его на строки.</span><span class="sxs-lookup"><span data-stu-id="55a38-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="55a38-110">**Метки** слева направо и справа налево — это знаки управления, используемые для указания направления текста для языков слева направо (таких как английский и испанский) и справа налево (например, арабского и иврита).</span><span class="sxs-lookup"><span data-stu-id="55a38-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="55a38-111">**Операторы lowercase Boolean** . Если вы используете оператора Boolean,  например **AND,** **OR,** и не в запросе поиска, он должен быть верхним шкафом.</span><span class="sxs-lookup"><span data-stu-id="55a38-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="55a38-112">При проверке запроса на опечатки синтаксис запросов часто указывает на то, что используется оператор Boolean, даже если могут использоваться операторы нижнего регистра; например,  `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="55a38-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="55a38-113">Что произойдет, если запрос имеет неподтверченный символ?</span><span class="sxs-lookup"><span data-stu-id="55a38-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="55a38-114">Если в запросе находятся неподтверченные символы, отображается сообщение с предупреждением о том, что неподтверченные символы найдены, и предлагает альтернативу.</span><span class="sxs-lookup"><span data-stu-id="55a38-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="55a38-115">Затем можно сохранить исходный запрос или заменить его предложенным пересмотренным запросом.</span><span class="sxs-lookup"><span data-stu-id="55a38-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="55a38-116">Вот пример предупреждаемого сообщения, отображаемого после  нажатия запроса Проверить опечатки для запроса поиска на предыдущем скриншоте.</span><span class="sxs-lookup"><span data-stu-id="55a38-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="55a38-117">Обратите внимание, что в исходном запросе использовались интеллектуальные кавычка и операторы нижнего регистра boolean.</span><span class="sxs-lookup"><span data-stu-id="55a38-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![Предупреждение отображается с предложенным изменением для запроса](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="55a38-119">Предотвращение неподтверченных символов в поисковых запросах</span><span class="sxs-lookup"><span data-stu-id="55a38-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="55a38-120">Неподтвержденные символы обычно добавляются в запрос при копировании запроса или частей запроса из других приложений (например, Microsoft Word или Microsoft Excel) и вклеить их в поле ключевого слова на странице запроса поиска контента.</span><span class="sxs-lookup"><span data-stu-id="55a38-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="55a38-121">Лучший способ избежать неподдерживаемых символов  просто ввести запрос в поле ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="55a38-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="55a38-122">Или вы можете скопировать запрос из Word или Excel, а затем вклеить его в обычный текстовый редактор, например Microsoft Notepad.</span><span class="sxs-lookup"><span data-stu-id="55a38-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="55a38-123">Сохраните текстовый файл и выберите **ANSI** в выпадаемом списке кодировок. </span><span class="sxs-lookup"><span data-stu-id="55a38-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="55a38-124">Так вы удалите все форматирование и неподдерживаемые символы.</span><span class="sxs-lookup"><span data-stu-id="55a38-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="55a38-125">Затем вы можете скопировать запрос из текстового файла и вставить его в поле запроса по ключевым словам.</span><span class="sxs-lookup"><span data-stu-id="55a38-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
