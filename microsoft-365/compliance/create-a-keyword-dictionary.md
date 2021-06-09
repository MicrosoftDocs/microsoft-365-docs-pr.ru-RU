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
ms.openlocfilehash: 1e1aa45c3bf4d31e4c969b0bc0949109fa716467
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841166"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="5c09f-103">Создание словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="5c09f-103">Create a keyword dictionary</span></span>

<span data-ttu-id="5c09f-104">Служба защиты от потери данных позволяет обнаруживать, отслеживать и защищать конфиденциальные элементы..</span><span class="sxs-lookup"><span data-stu-id="5c09f-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="5c09f-105">Для обнаружения конфиденциальных элементов иногда требуется поиск по ключевым словам, в частности при обнаружении стандартного контента (например, обмена данными, касающимися здравоохранения), а также неуместной или нецензурной лексики.</span><span class="sxs-lookup"><span data-stu-id="5c09f-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="5c09f-106">Хотя вы можете создавать списки ключевых слов в типах конфиденциальной информации, они ограничены по размеру и требуют изменения XML-кода для их создания или изменения.</span><span class="sxs-lookup"><span data-stu-id="5c09f-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="5c09f-107">Словари ключевых слов обеспечивают более простое и масштабное управление ключевыми словами, поддерживая до 1МБ терминов (после сжатия) в словаре и любой язык.</span><span class="sxs-lookup"><span data-stu-id="5c09f-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="5c09f-108">Ограничение клиента также составляет 1МБ после сжатия.</span><span class="sxs-lookup"><span data-stu-id="5c09f-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="5c09f-109">Ограничение в 1 МБ после сжатия означает, что все словари, объединенные в клиенте, могут содержать до 1 миллиона символов.</span><span class="sxs-lookup"><span data-stu-id="5c09f-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="5c09f-110">Ограничения словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="5c09f-110">Keyword dictionary limits</span></span>

<span data-ttu-id="5c09f-111">Существует ограничение в 50 слов для словаря ключевых слов на основе типов конфиденциальной информации, которые можно создать для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="5c09f-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="5c09f-112">Чтобы узнать, сколько словарей ключевых слов находится в клиенте, подключите его с помощью процедур, указанных в статье[Подключение к Центру безопасности и соответствия требованиям PowerShell](/powershell/exchange/connect-to-scc-powershell) для подключения к вашему клиенту и запуску этого сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c09f-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="5c09f-113">Основные этапы создания словаря ключевых слов</span><span class="sxs-lookup"><span data-stu-id="5c09f-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="5c09f-p103">Ключевые слова можно брать из различных источников, наиболее распространенными из которых являются файлы (например, списки в формате CSV или TXT), импортированные в службу или добавленные с помощью командлета PowerShell, списки, вводимые непосредственно в командлете PowerShell, и имеющиеся словари. При создании словаря ключевых слов всегда используются одни и те же основные действия:</span><span class="sxs-lookup"><span data-stu-id="5c09f-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="5c09f-116">Использование **Центра безопасности и соответствия требованиям** ([https://protection.office.com](https://protection.office.com)) или подключение к **интерфейсу&amp; PowerShell Центра безопасности и соответствия требованиям**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="5c09f-117">**Определите или загрузите ключевые слова из предполагаемого источника**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="5c09f-118">Мастер и командлет оба принимают разделенный запятыми список ключевых слов для создания пользовательского словаря ключевых слов, поэтому данный этап может слегка меняться в зависимости от источника ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="5c09f-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="5c09f-119">После загрузки они кодируются и преобразуются в байтовый массив, а затем импортируются.</span><span class="sxs-lookup"><span data-stu-id="5c09f-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="5c09f-120">**Создайте ваш словарь**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-120">**Create your dictionary**.</span></span> <span data-ttu-id="5c09f-121">Выберите имя и описание, а затем создайте словарь.</span><span class="sxs-lookup"><span data-stu-id="5c09f-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="5c09f-122">Создание словаря ключевых слов с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5c09f-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="5c09f-123">Следуйте указанным ниже действиям, чтобы создать и импортировать ключевые слова для пользовательского словаря:</span><span class="sxs-lookup"><span data-stu-id="5c09f-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="5c09f-124">Подключитесь к Центру безопасности и соответствия требованиям ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="5c09f-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="5c09f-125">Перейдите в раздел **Классификации > Типы конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="5c09f-126">Нажмите кнопку **Создать** и введите **имя** и **описание** для типа конфиденциальной информации, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="5c09f-127">Нажмите кнопку **Добавить элемент** и выберите вариант **Словарь (большие ключевые слова)** в раскрывающемся списке **Обнаруживать содержимое с указанными элементами**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="5c09f-128">Выберите команду **Добавить словарь**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="5c09f-129">В разделе управления поиском щелкните ссылку **Создать словари ключевых слов можно здесь**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="5c09f-130">Введите **имя** для пользовательского словаря.</span><span class="sxs-lookup"><span data-stu-id="5c09f-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="5c09f-131">Нажмите кнопку **Импорт** и выберите параметр **Из текста** или **Из CSV** в зависимости от типа файла ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="5c09f-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="5c09f-132">В диалоговом окне поиска файла выберите файл ключевых слов на локальном компьютере или в общей сетевой папке и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="5c09f-133">Нажмите кнопку **Сохранить**, затем выберите пользовательский словарь из списка **Словари ключевых слов**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="5c09f-134">Нажмите кнопку **Добавить**, а затем **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="5c09f-135">Проверьте и выберите окончательные параметры типа конфиденциальной информации, затем нажмите кнопку **Готово**. </span><span class="sxs-lookup"><span data-stu-id="5c09f-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="5c09f-136">Создание словаря ключевых слов из файла с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c09f-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="5c09f-137">Зачастую при необходимости создать большой словарь бывает удобно использовать ключевые слова из файла или списка, экспортированного из какого-то другого источника.</span><span class="sxs-lookup"><span data-stu-id="5c09f-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="5c09f-138">В данном случае вы создаете словарь ключевых слов, содержащий список выражений, непригодных для внешних сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="5c09f-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="5c09f-139">Сначала [выполните подключение к Центру безопасности&amp; и соответствия требованиям PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="5c09f-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="5c09f-140">Скопируйте ключевые слова в текстовый файл и убедитесь, что каждое ключевое слово находится на отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="5c09f-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="5c09f-p107">Сохраните текст с кодировкой Юникода. В Блокноте выберите пункты **Сохранить как** \> **Кодировка** \> **Юникод**.</span><span class="sxs-lookup"><span data-stu-id="5c09f-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="5c09f-143">Считайте файл в переменную с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="5c09f-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="5c09f-144">Создайте словарь с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="5c09f-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="5c09f-145">Использование словарей ключевых слов в типах конфиденциальной информации и политиках защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="5c09f-145">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="5c09f-146">Словари ключевых слов можно использовать как часть требований соответствия для пользовательских типов конфиденциальных данных или как сами эти типы.</span><span class="sxs-lookup"><span data-stu-id="5c09f-146">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="5c09f-147">В обоих случаях необходимо создать[пользовательский тип конфиденциальных данных](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5c09f-147">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="5c09f-148">Следуя инструкциям в связанной статье, создайте тип конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="5c09f-148">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="5c09f-149">После того как вы получите XML-файл, вам потребуется GUID-идентификатор для словаря.</span><span class="sxs-lookup"><span data-stu-id="5c09f-149">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="5c09f-150">Чтобы получить идентификатор словаря, выполните следующую команду и скопируйте значение свойства **Identity**:</span><span class="sxs-lookup"><span data-stu-id="5c09f-150">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="5c09f-151">Выходные данные команды выглядят так:</span><span class="sxs-lookup"><span data-stu-id="5c09f-151">The output of the command looks like this:</span></span>
  
<span data-ttu-id="5c09f-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="5c09f-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="5c09f-p109">Вставьте идентификатор в XML-код вашего типа конфиденциальной информации и отправьте код. Словарь появится в списке типов конфиденциальной информации, и вы сможете использовать его непосредственно в политике, указав, сколько ключевых слов требуется для совпадения.</span><span class="sxs-lookup"><span data-stu-id="5c09f-p109">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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

> [!NOTE]
> <span data-ttu-id="5c09f-155">Служба защиты информации Microsoft 365 поддерживает в предварительной версии языки с двухбайтовой кодировкой:</span><span class="sxs-lookup"><span data-stu-id="5c09f-155">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="5c09f-156">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="5c09f-156">Chinese (simplified)</span></span>
> - <span data-ttu-id="5c09f-157">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="5c09f-157">Chinese (traditional)</span></span>
> - <span data-ttu-id="5c09f-158">Корейский</span><span class="sxs-lookup"><span data-stu-id="5c09f-158">Korean</span></span>
> - <span data-ttu-id="5c09f-159">Японский</span><span class="sxs-lookup"><span data-stu-id="5c09f-159">Japanese</span></span>
>
><span data-ttu-id="5c09f-160">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="5c09f-160">This support is available for sensitive information types.</span></span> <span data-ttu-id="5c09f-161">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="5c09f-161">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
