---
title: Изменение словаря ключевых слов
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как изменить словарь ключевых слов в центре Microsoft 365 соответствия требованиям.
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685214"
---
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="43615-103">Изменение словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="43615-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="43615-104">Иногда требуется изменить ключевые слова в одном из встроенных или своих собственных словарей.</span><span class="sxs-lookup"><span data-stu-id="43615-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="43615-105">Это можно сделать с помощью PowerShell или центра соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="43615-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="43615-106">Изменение словаря ключевых слов в центре соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="43615-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="43615-107">Словари ключевых слов можно использовать как шаблоны типа конфиденциальной информации `Primary elements` `Supporting elements` (SIT).</span><span class="sxs-lookup"><span data-stu-id="43615-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="43615-108">Вы можете изменить словарь ключевых слов при создании SIT или в существующем SIT.</span><span class="sxs-lookup"><span data-stu-id="43615-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="43615-109">Например, чтобы изменить существующий словарь ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="43615-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="43615-110">Откройте шаблон, который имеет словарь ключевых слов, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="43615-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="43615-111">Найдите словарь ключевых слов, который необходимо обновить, и выберите изменение.</span><span class="sxs-lookup"><span data-stu-id="43615-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="43615-112">Внося изменения, используя одно ключевое слово в строке.</span><span class="sxs-lookup"><span data-stu-id="43615-112">Make your edits, using one keyword per line.</span></span>

![ключевые слова редактирования экрана](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="43615-114">Выберите `Done` .</span><span class="sxs-lookup"><span data-stu-id="43615-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="43615-115">Изменение словаря ключевых слов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="43615-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="43615-116">Например, мы изменим некоторые термины в PowerShell, сохраним их локально там, где они будут доступны для изменения в редакторе, а затем на месте обновим предыдущие.</span><span class="sxs-lookup"><span data-stu-id="43615-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="43615-117">Прежде всего получаем объект словаря:</span><span class="sxs-lookup"><span data-stu-id="43615-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="43615-118">При вводе `$dict`t отображаются разные переменные.</span><span class="sxs-lookup"><span data-stu-id="43615-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="43615-119">Сами ключевые слова хранятся в объекте на внутреннем сервере, но  `$dict.KeywordDictionary` содержит представляющую его строку, с помощью которой вы можете изменить словарь.</span><span class="sxs-lookup"><span data-stu-id="43615-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="43615-120">Перед изменением словаря необходимо вернуть строку терминов обратно в массив с помощью `.split(',')`метода.</span><span class="sxs-lookup"><span data-stu-id="43615-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="43615-121">Затем вы удаляете ненужные пробелы между ключевыми словами с помощью  `.trim()` метода, оставляя только те слова, с которыми нужно работать.</span><span class="sxs-lookup"><span data-stu-id="43615-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="43615-p105">Теперь мы удалим некоторые термины из словаря. Так как наш словарь содержит лишь несколько ключевых слов, можно просто перейти к экспорту словаря и его редактированию в Блокноте. Однако словари обычно содержат большое количество текста, поэтому сначала следует научиться редактировать их в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43615-p105">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="43615-p106">На предыдущем этапе мы сохранили ключевые слова в массив. Существует несколько способов [удаления элементов из массива](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), но для простоты мы создадим массив терминов, которые требуется удалить из словаря, а затем скопируем из словаря только те термины, которых нет в этом списке.</span><span class="sxs-lookup"><span data-stu-id="43615-p106">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="43615-p107">Выполните команду `$terms`, чтобы вывести текущий список терминов. Выходные данные этой команды выглядят так:</span><span class="sxs-lookup"><span data-stu-id="43615-p107">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

<span data-ttu-id="43615-128">Выполните следующую команду, чтобы указать удаляемые элементы:</span><span class="sxs-lookup"><span data-stu-id="43615-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="43615-129">Выполните следующую команду, чтобы фактически удалить термины из списка:</span><span class="sxs-lookup"><span data-stu-id="43615-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="43615-p108">Выполните команду `$updatedTerms`, чтобы вывести обновленный список элементов. Выходные данные команды выглядят так (указанные термины были удалены):</span><span class="sxs-lookup"><span data-stu-id="43615-p108">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="43615-p109">Теперь откройте файл, добавьте другие термины и сохраните его в кодировке Юникода (UTF-16). Затем мы отправим обновленные термины и обновим словарь на месте.</span><span class="sxs-lookup"><span data-stu-id="43615-p109">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="43615-134">Словарь обновлен.</span><span class="sxs-lookup"><span data-stu-id="43615-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="43615-135">В поле `Identity` указывается имя словаря.</span><span class="sxs-lookup"><span data-stu-id="43615-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="43615-136">Если вы также хотите изменить имя словаря с помощью командлета `set-`, вам достаточно будет добавить параметр `-Name` с новым именем.</span><span class="sxs-lookup"><span data-stu-id="43615-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="43615-137">См. также</span><span class="sxs-lookup"><span data-stu-id="43615-137">See Also</span></span>
- [<span data-ttu-id="43615-138">Создание словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="43615-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="43615-139">Создание пользовательского типа конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="43615-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
