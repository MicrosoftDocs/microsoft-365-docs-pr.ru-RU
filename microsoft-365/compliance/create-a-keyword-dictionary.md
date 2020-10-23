---
title: Создание словаря ключевых слов
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Ознакомьтесь с основными шагами по созданию словаря ключевых слов в Центре безопасности и соответствия требованиям Office 365.
ms.openlocfilehash: e6f6043efd4c5f38b7e9fa2a92c4fcb7ceb91e45
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681639"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="28800-103">Создание словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="28800-103">Create a keyword dictionary</span></span>

<span data-ttu-id="28800-104">Служба защиты от потери данных позволяет обнаруживать, отслеживать и защищать конфиденциальные элементы..</span><span class="sxs-lookup"><span data-stu-id="28800-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="28800-105">Для обнаружения конфиденциальных элементов иногда требуется поиск по ключевым словам, в частности при обнаружении стандартного контента (например, обмена данными, касающимися здравоохранения), а также неуместной или нецензурной лексики.</span><span class="sxs-lookup"><span data-stu-id="28800-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="28800-106">Хотя вы можете создавать списки ключевых слов в типах конфиденциальной информации, они ограничены по размеру и требуют изменения XML-кода для их создания или изменения.</span><span class="sxs-lookup"><span data-stu-id="28800-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="28800-107">Словари ключевых слов обеспечивают более простое и масштабное управление ключевыми словами, поддерживая до 100 КБ терминов (после сжатия) в словаре и любой язык.</span><span class="sxs-lookup"><span data-stu-id="28800-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100KB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="28800-108">Ограничение клиента также составляет 100 КБ после сжатия.</span><span class="sxs-lookup"><span data-stu-id="28800-108">The tenant limit is also 100KB after compression.</span></span>
  
> [!NOTE]
> <span data-ttu-id="28800-109">Служба защиты информации Microsoft 365 теперь в предварительный версии поддерживает языки с набором двухбайтовых символов:</span><span class="sxs-lookup"><span data-stu-id="28800-109">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="28800-110">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="28800-110">Chinese (simplified)</span></span>
> - <span data-ttu-id="28800-111">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="28800-111">Chinese (traditional)</span></span>
> - <span data-ttu-id="28800-112">Корейский</span><span class="sxs-lookup"><span data-stu-id="28800-112">Korean</span></span>
> - <span data-ttu-id="28800-113">Японский</span><span class="sxs-lookup"><span data-stu-id="28800-113">Japanese</span></span>
>
><span data-ttu-id="28800-114">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="28800-114">This support is available for sensitive information types.</span></span> <span data-ttu-id="28800-115">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="28800-115">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="28800-116">Основные этапы создания словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="28800-116">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="28800-p103">Ключевые слова можно брать из различных источников, наиболее распространенными из которых являются файлы (например, списки в формате CSV или TXT), импортированные в службу или добавленные с помощью командлета PowerShell, списки, вводимые непосредственно в командлете PowerShell, и имеющиеся словари. При создании словаря ключевых слов всегда используются одни и те же основные действия:</span><span class="sxs-lookup"><span data-stu-id="28800-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="28800-119">Использование**Центра безопасности и соответствия требованиям** ([https://protection.office.com](https://protection.office.com)) или подключение к **интерфейсу&amp; PowerShell Центра безопасности и соответствия требованиям**.</span><span class="sxs-lookup"><span data-stu-id="28800-119">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="28800-120">**Определите или загрузите ключевые слова из предполагаемого источника**.</span><span class="sxs-lookup"><span data-stu-id="28800-120">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="28800-121">Мастер и командлет оба принимают разделенный запятыми список ключевых слов для создания пользовательского словаря ключевых слов, поэтому данный этап может слегка меняться в зависимости от источника ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="28800-121">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="28800-122">После загрузки они кодируются и преобразуются в байтовый массив, а затем импортируются.</span><span class="sxs-lookup"><span data-stu-id="28800-122">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="28800-123">**Создайте ваш словарь**.</span><span class="sxs-lookup"><span data-stu-id="28800-123">**Create your dictionary**.</span></span> <span data-ttu-id="28800-124">Выберите имя и описание, а затем создайте словарь.</span><span class="sxs-lookup"><span data-stu-id="28800-124">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="28800-125">Создание словаря ключевых слов с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="28800-125">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="28800-126">Следуйте указанным ниже действиям, чтобы создать и импортировать ключевые слова для пользовательского словаря:</span><span class="sxs-lookup"><span data-stu-id="28800-126">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="28800-127">Подключитесь к Центру безопасности и соответствия требованиям ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="28800-127">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="28800-128">Перейдите в раздел **Классификации > Типы конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="28800-128">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="28800-129">Нажмите кнопку **Создать** и введите **имя** и **описание** для типа конфиденциальной информации, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="28800-129">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="28800-130">Нажмите кнопку **Добавить элемент** и выберите вариант **Словарь (большие ключевые слова)** в раскрывающемся списке **Обнаруживать содержимое с указанными элементами**.</span><span class="sxs-lookup"><span data-stu-id="28800-130">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="28800-131">Выберите команду **Добавить словарь**.</span><span class="sxs-lookup"><span data-stu-id="28800-131">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="28800-132">В разделе управления поиском щелкните ссылку **Создать словари ключевых слов можно здесь**.</span><span class="sxs-lookup"><span data-stu-id="28800-132">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="28800-133">Введите **имя** для пользовательского словаря.</span><span class="sxs-lookup"><span data-stu-id="28800-133">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="28800-134">Нажмите кнопку **Импорт** и выберите параметр **Из текста** или **Из CSV** в зависимости от типа файла ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="28800-134">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="28800-135">В диалоговом окне поиска файла выберите файл ключевых слов на локальном компьютере или в общей сетевой папке и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="28800-135">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="28800-136">Нажмите кнопку **Сохранить**, затем выберите пользовательский словарь из списка **Словари ключевых слов**.</span><span class="sxs-lookup"><span data-stu-id="28800-136">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="28800-137">Нажмите кнопку **Добавить**, а затем **Далее**.</span><span class="sxs-lookup"><span data-stu-id="28800-137">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="28800-138">Проверьте и выберите окончательные параметры типа конфиденциальной информации, затем нажмите кнопку **Готово**. </span><span class="sxs-lookup"><span data-stu-id="28800-138">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="28800-139">Создание словаря ключевых слов из файла с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="28800-139">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="28800-140">Зачастую при необходимости создать большой словарь бывает удобно использовать ключевые слова из файла или списка, экспортированного из какого-то другого источника.</span><span class="sxs-lookup"><span data-stu-id="28800-140">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="28800-141">В данном случае вы создаете словарь ключевых слов, содержащий список выражений, непригодных для внешних сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="28800-141">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="28800-142">Сначала [выполните подключение к Центру безопасности&amp; и соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="28800-142">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="28800-143">Скопируйте ключевые слова в текстовый файл и убедитесь, что каждое ключевое слово находится на отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="28800-143">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="28800-p107">Сохраните текст с кодировкой Юникода. В Блокноте выберите пункты **Сохранить как** \> **Кодировка** \> **Юникод**.</span><span class="sxs-lookup"><span data-stu-id="28800-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="28800-146">Считайте файл в переменную с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="28800-146">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="28800-147">Создайте словарь с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="28800-147">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="28800-148">Изменение имеющегося словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="28800-148">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="28800-149">Иногда требуется изменить ключевые слова в одном из встроенных или своих собственных словарей.</span><span class="sxs-lookup"><span data-stu-id="28800-149">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="28800-150">Сейчас обновить пользовательский словарь ключевых слов можно только с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28800-150">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="28800-151">Например, мы изменим некоторые термины в PowerShell, сохраним их локально там, где они будут доступны для изменения в редакторе, а затем на месте обновим предыдущие.</span><span class="sxs-lookup"><span data-stu-id="28800-151">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="28800-152">Прежде всего получаем объект словаря:</span><span class="sxs-lookup"><span data-stu-id="28800-152">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="28800-153">При вводе `$dict`t отображаются разные переменные.</span><span class="sxs-lookup"><span data-stu-id="28800-153">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="28800-154">Сами ключевые слова хранятся в объекте на внутреннем сервере, но  `$dict.KeywordDictionary` содержит представляющую его строку, с помощью которой вы можете изменить словарь.</span><span class="sxs-lookup"><span data-stu-id="28800-154">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="28800-155">Перед изменением словаря необходимо вернуть строку терминов обратно в массив с помощью `.split(',')`метода.</span><span class="sxs-lookup"><span data-stu-id="28800-155">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="28800-156">Затем вы удаляете ненужные пробелы между ключевыми словами с помощью  `.trim()` метода, оставляя только те слова, с которыми нужно работать.</span><span class="sxs-lookup"><span data-stu-id="28800-156">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="28800-p111">Теперь мы удалим некоторые термины из словаря. Так как наш словарь содержит лишь несколько ключевых слов, можно просто перейти к экспорту словаря и его редактированию в Блокноте. Однако словари обычно содержат большое количество текста, поэтому сначала следует научиться редактировать их в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28800-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="28800-p112">На предыдущем этапе мы сохранили ключевые слова в массив. Существует несколько способов [удаления элементов из массива](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), но для простоты мы создадим массив терминов, которые требуется удалить из словаря, а затем скопируем из словаря только те термины, которых нет в этом списке.</span><span class="sxs-lookup"><span data-stu-id="28800-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="28800-p113">Выполните команду `$terms`, чтобы вывести текущий список терминов. Выходные данные этой команды выглядят так:</span><span class="sxs-lookup"><span data-stu-id="28800-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="28800-163">Выполните следующую команду, чтобы указать удаляемые элементы:</span><span class="sxs-lookup"><span data-stu-id="28800-163">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="28800-164">Выполните следующую команду, чтобы фактически удалить термины из списка:</span><span class="sxs-lookup"><span data-stu-id="28800-164">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="28800-p114">Выполните команду `$updatedTerms`, чтобы вывести обновленный список элементов. Выходные данные команды выглядят так (указанные термины были удалены):</span><span class="sxs-lookup"><span data-stu-id="28800-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="28800-p115">Теперь просто откройте файл, добавьте нужные термины и сохраните его в кодировке Юникода (UTF-16). Затем мы отправим обновленные термины и обновим словарь на месте.</span><span class="sxs-lookup"><span data-stu-id="28800-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="28800-p116">Теперь словарь был обновлен на месте. Обратите внимание, что поле `Identity` принимает имя словаря. Если требуется изменить имя словаря, можно просто добавить в приведенный выше командлет `set-` параметр `-Name` с новым именем.</span><span class="sxs-lookup"><span data-stu-id="28800-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="28800-172">Использование словарей ключевых слов в типах конфиденциальной информации и политиках защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="28800-172">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="28800-173">Словари ключевых слов можно использовать как часть требований соответствия для пользовательских типов конфиденциальных данных или как сами эти типы.</span><span class="sxs-lookup"><span data-stu-id="28800-173">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="28800-174">В обоих случаях необходимо создать[пользовательский тип конфиденциальных данных](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="28800-174">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="28800-175">Следуя инструкциям в связанной статье, создайте тип конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="28800-175">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="28800-176">После того как вы получите XML-файл, вам потребуется GUID-идентификатор для словаря.</span><span class="sxs-lookup"><span data-stu-id="28800-176">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="28800-177">Чтобы получить идентификатор словаря, выполните следующую команду и скопируйте значение свойства **Identity**:</span><span class="sxs-lookup"><span data-stu-id="28800-177">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="28800-178">Выходные данные команды выглядят так:</span><span class="sxs-lookup"><span data-stu-id="28800-178">The output of the command looks like this:</span></span>
  
<span data-ttu-id="28800-179">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="28800-179">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="28800-p118">Вставьте идентификатор в XML-код вашего типа конфиденциальной информации и отправьте код. Словарь появится в списке типов конфиденциальной информации, и вы сможете использовать его непосредственно в политике, указав, сколько ключевых слов требуется для совпадения.</span><span class="sxs-lookup"><span data-stu-id="28800-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
