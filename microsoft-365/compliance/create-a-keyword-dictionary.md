---
title: Создание словаря ключевых слов
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
description: Для определения конфиденциальной информации иногда требуется искать ключевые слова, в частности, при определении универсального контента (например, коммуникаций в сфере здравоохранения) либо неприемлемой или нецензурной лексики. Списки ключевых слов можно создавать в типах конфиденциальной информации, но размер этих списков ограничен, а для их создания и редактирования требуется модифицировать XML. Словари ключевых слов упрощают управление ключевыми словами и позволяют управлять ими в намного более крупных масштабах — до 100 000 терминов на словарь.
ms.openlocfilehash: 73ca1e83f716af076f99b1bcb8fba4fbb6e69d9d
ms.sourcegitcommit: 547bfc5f1fec7545cbe71b1919454425556c9227
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "38687426"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="12898-105">Создание словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="12898-105">Create a keyword dictionary</span></span>

<span data-ttu-id="12898-p102">Защита от потери данных (DLP) в Office 365 позволяет определять, отслеживать и защищать конфиденциальные данные. Для определения конфиденциальной информации иногда требуется поиск ключевых слов, особенно при определении общего контента (например, для общения с учетом здравоохранения) или неуместного или явного языка. Несмотря на то, что вы можете создавать списки ключевых слов в типах конфиденциальных данных, списки ключевых слов ограничены и требуют изменения XML для создания или изменения. Словари ключевых слов обеспечивают упрощенное управление ключевыми словами и на более крупном масштабе, поддерживающем до 100 000 терминов для каждого словаря.</span><span class="sxs-lookup"><span data-stu-id="12898-p102">Data loss prevention (DLP) in Office 365 can identify, monitor, and protect your sensitive information. Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language. Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them. Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="12898-110">Основные этапы создания словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="12898-110">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="12898-p103">Ключевые слова можно брать из различных источников, наиболее распространенными из которых являются файлы (например, списки в формате CSV или TXT), импортированные в службу или добавленные с помощью командлета PowerShell, списки, вводимые непосредственно в командлете PowerShell, и имеющиеся словари. При создании словаря ключевых слов всегда используются одни и те же основные действия:</span><span class="sxs-lookup"><span data-stu-id="12898-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="12898-113">Воспользуйтесь **центром безопасности & соответствия требованиям** ([https://protection.office.com](https://protection.office.com)) или подключитесь к **PowerShell центра &amp; безопасности Office 365 для обеспечения соответствия требованиям**.</span><span class="sxs-lookup"><span data-stu-id="12898-113">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Office 365 Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="12898-114">**Определите или загрузите ключевые слова из предполагаемого источника**.</span><span class="sxs-lookup"><span data-stu-id="12898-114">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="12898-115">Мастер и командлет принимают разделенный запятыми список ключевых слов для создания пользовательского словаря ключевых слов, поэтому этот шаг будет слегка отличаться в зависимости от того, откуда берутся ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="12898-115">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="12898-116">После загрузки они кодируются и преобразуются в байтовый массив, а затем импортируются.</span><span class="sxs-lookup"><span data-stu-id="12898-116">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="12898-117">**Создайте словарь**.</span><span class="sxs-lookup"><span data-stu-id="12898-117">**Create your dictionary**.</span></span> <span data-ttu-id="12898-118">Выберите имя и описание и создайте словарь.</span><span class="sxs-lookup"><span data-stu-id="12898-118">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="12898-119">Создание словаря ключевых слов с помощью центра безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="12898-119">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="12898-120">Используйте указанные ниже действия, чтобы создать и импортировать ключевые слова для пользовательского словаря:</span><span class="sxs-lookup"><span data-stu-id="12898-120">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="12898-121">Подключитесь к центру безопасности & соответствия требованиям[https://protection.office.com](https://protection.office.com)().</span><span class="sxs-lookup"><span data-stu-id="12898-121">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="12898-122">Перейдите в раздел **Классификации > Типы конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="12898-122">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="12898-123">Нажмите кнопку **Создать** и введите **имя** и **описание** для типа конфиденциальной информации, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="12898-123">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="12898-124">Нажмите кнопку **Добавить элемент** и выберите вариант **Словарь (большие ключевые слова)** в раскрывающемся списке **Обнаруживать содержимое с указанными элементами**.</span><span class="sxs-lookup"><span data-stu-id="12898-124">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="12898-125">Выберите команду **Добавить словарь**.</span><span class="sxs-lookup"><span data-stu-id="12898-125">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="12898-126">В разделе управления поиском щелкните ссылку **Создать словари ключевых слов можно здесь**.</span><span class="sxs-lookup"><span data-stu-id="12898-126">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="12898-127">Введите **имя** для пользовательского словаря.</span><span class="sxs-lookup"><span data-stu-id="12898-127">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="12898-128">Нажмите кнопку **Импорт** и выберите параметр **Из текста** или **Из CSV** в зависимости от типа файла ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="12898-128">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="12898-129">В диалоговом окне поиска файла выберите файл ключевых слов на локальном компьютере или в общей сетевой папке и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="12898-129">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="12898-130">Нажмите кнопку **Сохранить**, затем выберите пользовательский словарь из списка **Словари ключевых слов**.</span><span class="sxs-lookup"><span data-stu-id="12898-130">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="12898-131">Нажмите кнопку **Добавить**, а затем **Далее**.</span><span class="sxs-lookup"><span data-stu-id="12898-131">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="12898-132">Проверьте и выберите окончательные параметры типа конфиденциальной информации, затем нажмите кнопку **Готово**. </span><span class="sxs-lookup"><span data-stu-id="12898-132">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="12898-133">Создание словаря ключевых слов из файла с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="12898-133">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="12898-134">Часто при создании большого словаря необходимо использовать ключевые слова из файла или списка, экспортированного из другого источника.</span><span class="sxs-lookup"><span data-stu-id="12898-134">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="12898-135">В этом случае вы создадите словарь ключевых слов, содержащий список неуместного языка для внешнего сообщения.</span><span class="sxs-lookup"><span data-stu-id="12898-135">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="12898-136">Необходимо сначала [подключиться к оболочке PowerShell центра &amp; безопасности Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="12898-136">You must first [connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="12898-137">Скопируйте ключевые слова в текстовый файл и убедитесь, что каждое ключевое слово находится на отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="12898-137">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="12898-p107">Сохраните текст с кодировкой Юникода. В Блокноте выберите пункты **Сохранить как** \> **Кодировка** \> **Юникод**.</span><span class="sxs-lookup"><span data-stu-id="12898-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="12898-140">Считайте файл в переменную с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="12898-140">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="12898-141">Создайте словарь с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="12898-141">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="12898-142">Изменение имеющегося словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="12898-142">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="12898-143">Иногда требуется изменить ключевые слова в одном из встроенных или своих собственных словарей.</span><span class="sxs-lookup"><span data-stu-id="12898-143">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="12898-144">Сейчас обновить пользовательский словарь ключевых слов можно только с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12898-144">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="12898-145">Например, мы изменим некоторые термины в PowerShell, сохраняйте термины, которые вы можете изменить в редакторе, а затем обновляйте предыдущие термины на месте.</span><span class="sxs-lookup"><span data-stu-id="12898-145">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="12898-146">Прежде всего получаем объект словаря:</span><span class="sxs-lookup"><span data-stu-id="12898-146">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="12898-147">При `$dict` печати будут показаны различные переменные.</span><span class="sxs-lookup"><span data-stu-id="12898-147">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="12898-148">Сами ключевые слова хранятся в объекте на внутреннем стороне, но `$dict.KeywordDictionary` содержат строковые представления, которые используются для изменения словаря.</span><span class="sxs-lookup"><span data-stu-id="12898-148">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="12898-149">Перед изменением словаря необходимо снова превратить строку терминов в массив с помощью `.split(',')` метода.</span><span class="sxs-lookup"><span data-stu-id="12898-149">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="12898-150">Затем вы удалите ненужные пробелы между ключевыми словами с `.trim()` методом, оставив только ключевые слова для работы.</span><span class="sxs-lookup"><span data-stu-id="12898-150">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="12898-p111">Теперь мы удалим некоторые термины из словаря. Так как наш словарь содержит лишь несколько ключевых слов, можно просто перейти к экспорту словаря и его редактированию в Блокноте. Однако словари обычно содержат большое количество текста, поэтому сначала следует научиться редактировать их в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12898-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="12898-p112">На предыдущем этапе мы сохранили ключевые слова в массив. Существует несколько способов [удаления элементов из массива](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), но для простоты мы создадим массив терминов, которые требуется удалить из словаря, а затем скопируем из словаря только те термины, которых нет в этом списке.</span><span class="sxs-lookup"><span data-stu-id="12898-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="12898-p113">Выполните команду `$terms`, чтобы вывести текущий список терминов. Выходные данные этой команды выглядят так:</span><span class="sxs-lookup"><span data-stu-id="12898-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="12898-157">Выполните следующую команду, чтобы указать удаляемые элементы:</span><span class="sxs-lookup"><span data-stu-id="12898-157">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="12898-158">Выполните следующую команду, чтобы фактически удалить термины из списка:</span><span class="sxs-lookup"><span data-stu-id="12898-158">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="12898-p114">Выполните команду `$updatedTerms`, чтобы вывести обновленный список элементов. Выходные данные команды выглядят так (указанные термины были удалены):</span><span class="sxs-lookup"><span data-stu-id="12898-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="12898-p115">Теперь просто откройте файл, добавьте нужные термины и сохраните его в кодировке Юникода (UTF-16). Затем мы отправим обновленные термины и обновим словарь на месте.</span><span class="sxs-lookup"><span data-stu-id="12898-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="12898-p116">Теперь словарь был обновлен на месте. Обратите внимание, что поле `Identity` принимает имя словаря. Если требуется изменить имя словаря, можно просто добавить в приведенный выше командлет `set-` параметр `-Name` с новым именем.</span><span class="sxs-lookup"><span data-stu-id="12898-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="12898-166">Использование словарей ключевых слов в типах конфиденциальной информации и политиках защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="12898-166">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="12898-167">Словари ключевых слов можно использовать в качестве части требований к соответствию для настраиваемого типа конфиденциальной информации или как сам тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="12898-167">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="12898-168">Для обоих требуется создать [настраиваемый тип конфиденциальной информации](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="12898-168">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="12898-169">Следуйте инструкциям в связанной статье, чтобы создать тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="12898-169">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="12898-170">Когда у вас есть XML, вам потребуется идентификатор GUID для словаря, чтобы его использовать.</span><span class="sxs-lookup"><span data-stu-id="12898-170">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="12898-171">Чтобы получить идентификатор словаря, выполните следующую команду и скопируйте значение свойства **Identity**:</span><span class="sxs-lookup"><span data-stu-id="12898-171">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="12898-172">Выходные данные команды выглядят так:</span><span class="sxs-lookup"><span data-stu-id="12898-172">The output of the command looks like this:</span></span>
  
<span data-ttu-id="12898-173">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="12898-173"></span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="12898-p118">Вставьте идентификатор в XML-код вашего типа конфиденциальной информации и отправьте код. Словарь появится в списке типов конфиденциальной информации, и вы сможете использовать его непосредственно в политике, указав, сколько ключевых слов требуется для совпадения.</span><span class="sxs-lookup"><span data-stu-id="12898-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```
