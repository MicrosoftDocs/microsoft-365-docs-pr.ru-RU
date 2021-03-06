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
ms.openlocfilehash: 8d313650f298f2ab26989bec9df1260918f7dd5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300114"
---
# <a name="create-a-keyword-dictionary"></a>Создание словаря ключевых слов

Служба защиты от потери данных позволяет обнаруживать, отслеживать и защищать конфиденциальные элементы.. Для обнаружения конфиденциальных элементов иногда требуется поиск по ключевым словам, в частности при обнаружении стандартного контента (например, обмена данными, касающимися здравоохранения), а также неуместной или нецензурной лексики. Хотя вы можете создавать списки ключевых слов в типах конфиденциальной информации, они ограничены по размеру и требуют изменения XML-кода для их создания или изменения. Словари ключевых слов обеспечивают более простое и масштабное управление ключевыми словами, поддерживая до 1МБ терминов (после сжатия) в словаре и любой язык. Ограничение клиента также составляет 1МБ после сжатия. Ограничение в 1 МБ после сжатия означает, что все словари, объединенные в клиенте, могут содержать до 1 миллиона символов.

## <a name="keyword-dictionary-limits"></a>Ограничения словаря ключевых слов

Существует ограничение в 50 слов для словаря ключевых слов на основе типов конфиденциальной информации, которые можно создать для каждого клиента. Чтобы узнать, сколько словарей ключевых слов находится в клиенте, подключите его с помощью процедур, указанных в статье[Подключение к Центру безопасности и соответствия требованиям PowerShell](/powershell/exchange/connect-to-scc-powershell) для подключения к вашему клиенту и запуску этого сценария PowerShell.

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Основные этапы создания словаря ключевых слов

Ключевые слова можно брать из различных источников, наиболее распространенными из которых являются файлы (например, списки в формате CSV или TXT), импортированные в службу или добавленные с помощью командлета PowerShell, списки, вводимые непосредственно в командлете PowerShell, и имеющиеся словари. При создании словаря ключевых слов всегда используются одни и те же основные действия:
  
1. Использование **Центра безопасности и соответствия требованиям** ([https://protection.office.com](https://protection.office.com)) или подключение к **интерфейсу&amp; PowerShell Центра безопасности и соответствия требованиям**.
    
2. **Определите или загрузите ключевые слова из предполагаемого источника**. Мастер и командлет оба принимают разделенный запятыми список ключевых слов для создания пользовательского словаря ключевых слов, поэтому данный этап может слегка меняться в зависимости от источника ключевых слов. После загрузки они кодируются и преобразуются в байтовый массив, а затем импортируются.
    
3. **Создайте ваш словарь**. Выберите имя и описание, а затем создайте словарь.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Создание словаря ключевых слов с помощью Центра безопасности и соответствия требованиям

Следуйте указанным ниже действиям, чтобы создать и импортировать ключевые слова для пользовательского словаря:

1. Подключитесь к Центру безопасности и соответствия требованиям ([https://protection.office.com](https://protection.office.com)).

2. Перейдите в раздел **Классификации > Типы конфиденциальной информации**.

3. Нажмите кнопку **Создать** и введите **имя** и **описание** для типа конфиденциальной информации, затем нажмите кнопку **Далее**.

4. Нажмите кнопку **Добавить элемент** и выберите вариант **Словарь (большие ключевые слова)** в раскрывающемся списке **Обнаруживать содержимое с указанными элементами**.

5. Выберите команду **Добавить словарь**.

6. В разделе управления поиском щелкните ссылку **Создать словари ключевых слов можно здесь**.

7. Введите **имя** для пользовательского словаря.

8. Нажмите кнопку **Импорт** и выберите параметр **Из текста** или **Из CSV** в зависимости от типа файла ключевых слов.

9. В диалоговом окне поиска файла выберите файл ключевых слов на локальном компьютере или в общей сетевой папке и нажмите кнопку **Открыть**.

10. Нажмите кнопку **Сохранить**, затем выберите пользовательский словарь из списка **Словари ключевых слов**.

11. Нажмите кнопку **Добавить**, а затем **Далее**.

12. Проверьте и выберите окончательные параметры типа конфиденциальной информации, затем нажмите кнопку **Готово**. 
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>Создание словаря ключевых слов из файла с помощью PowerShell

Зачастую при необходимости создать большой словарь бывает удобно использовать ключевые слова из файла или списка, экспортированного из какого-то другого источника. В данном случае вы создаете словарь ключевых слов, содержащий список выражений, непригодных для внешних сообщений электронной почты. Сначала [выполните подключение к Центру безопасности&amp; и соответствия требованиям PowerShell](/powershell/exchange/connect-to-scc-powershell).
  
1. Скопируйте ключевые слова в текстовый файл и убедитесь, что каждое ключевое слово находится на отдельной строке.
    
2. Сохраните текст с кодировкой Юникода. В Блокноте выберите пункты **Сохранить как** \> **Кодировка** \> **Юникод**.
    
3. Считайте файл в переменную с помощью следующего командлета:
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. Создайте словарь с помощью следующего командлета:
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Использование словарей ключевых слов в типах конфиденциальной информации и политиках защиты от потери данных

Словари ключевых слов можно использовать как часть требований соответствия для пользовательских типов конфиденциальных данных или как сами эти типы. В обоих случаях необходимо создать[пользовательский тип конфиденциальных данных](create-a-custom-sensitive-information-type-in-scc-powershell.md). Следуя инструкциям в связанной статье, создайте тип конфиденциальных данных. После того как вы получите XML-файл, вам потребуется GUID-идентификатор для словаря.
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Чтобы получить идентификатор словаря, выполните следующую команду и скопируйте значение свойства **Identity**: 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

Выходные данные команды выглядят так:
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Вставьте идентификатор в XML-код вашего типа конфиденциальной информации и отправьте код. Словарь появится в списке типов конфиденциальной информации, и вы сможете использовать его непосредственно в политике, указав, сколько ключевых слов требуется для совпадения.
  
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
> Служба защиты информации Microsoft 365 поддерживает языки с двухбайтовой кодировкой:
> - Китайский (упрощенное письмо)
> - Китайский (традиционное письмо)
> - Корейский
> - Японский
>
>Эта поддержка доступна для конфиденциальных типов информации. Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).

> [!TIP]
> Для выявления шаблонов, содержащих символы китайского или японского языков и однобайтовые символы, или шаблонов, содержащих элементы китайского/японского и английского языков, определите два варианта ключевого слова или регулярного выражения. 
>
> Например, для выявления такого ключевого слова, как "机密的document", используйте два варианта ключевого слова: один с пробелом между японским и английским текстом, а другой без пробела между японским и английским текстом. Поэтому в SIT следует добавить ключевые слова "机密的 document" и "机密的document". Аналогично, для выявления фразы "東京オリンピック2020" следует использовать два варианта: "東京オリンピック 2020" и "東京オリンピック2020".
>
> При создании регулярного выражения с использованием двухбайтового дефиса или двухбайтовой точки необходимо исключить оба этих символа точно так же, как из регулярных выражений исключаются дефис и точка. Пример регулярного выражения:
>
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> В списке ключевых слов рекомендуется использовать соответствие по строкам вместо соответствия по словам.
