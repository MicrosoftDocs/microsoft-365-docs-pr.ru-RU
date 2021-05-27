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
# <a name="modify-a-keyword-dictionary"></a>Изменение словаря ключевых слов

Иногда требуется изменить ключевые слова в одном из встроенных или своих собственных словарей. Это можно сделать с помощью PowerShell или центра соответствия требованиям.

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>Изменение словаря ключевых слов в центре соответствия требованиям

Словари ключевых слов можно использовать как шаблоны типа конфиденциальной информации `Primary elements` `Supporting elements` (SIT). Вы можете изменить словарь ключевых слов при создании SIT или в существующем SIT. Например, чтобы изменить существующий словарь ключевых слов:

1. Откройте шаблон, который имеет словарь ключевых слов, который необходимо обновить.
2. Найдите словарь ключевых слов, который необходимо обновить, и выберите изменение. 
3.  Внося изменения, используя одно ключевое слово в строке.

![ключевые слова редактирования экрана](../media/edit-keyword-dictionary.png)

4. Выберите `Done` .

## <a name="modify-a-keyword-dictionary-using-powershell"></a>Изменение словаря ключевых слов с помощью PowerShell 

Например, мы изменим некоторые термины в PowerShell, сохраним их локально там, где они будут доступны для изменения в редакторе, а затем на месте обновим предыдущие. 

Прежде всего получаем объект словаря:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

При вводе `$dict`t отображаются разные переменные. Сами ключевые слова хранятся в объекте на внутреннем сервере, но  `$dict.KeywordDictionary` содержит представляющую его строку, с помощью которой вы можете изменить словарь. 

Перед изменением словаря необходимо вернуть строку терминов обратно в массив с помощью `.split(',')`метода. Затем вы удаляете ненужные пробелы между ключевыми словами с помощью  `.trim()` метода, оставляя только те слова, с которыми нужно работать. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Теперь мы удалим некоторые термины из словаря. Так как наш словарь содержит лишь несколько ключевых слов, можно просто перейти к экспорту словаря и его редактированию в Блокноте. Однако словари обычно содержат большое количество текста, поэтому сначала следует научиться редактировать их в PowerShell.
  
На предыдущем этапе мы сохранили ключевые слова в массив. Существует несколько способов [удаления элементов из массива](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), но для простоты мы создадим массив терминов, которые требуется удалить из словаря, а затем скопируем из словаря только те термины, которых нет в этом списке.
  
Выполните команду `$terms`, чтобы вывести текущий список терминов. Выходные данные этой команды выглядят так: 
  
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

Выполните следующую команду, чтобы указать удаляемые элементы:
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

Выполните следующую команду, чтобы фактически удалить термины из списка:
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Выполните команду `$updatedTerms`, чтобы вывести обновленный список элементов. Выходные данные команды выглядят так (указанные термины были удалены): 
  
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

Теперь откройте файл, добавьте другие термины и сохраните его в кодировке Юникода (UTF-16). Затем мы отправим обновленные термины и обновим словарь на месте.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Словарь обновлен. В поле `Identity` указывается имя словаря. Если вы также хотите изменить имя словаря с помощью командлета `set-`, вам достаточно будет добавить параметр `-Name` с новым именем. 

См. также
- [Создание словаря ключевых слов](create-a-keyword-dictionary.md)
- [Создание пользовательского типа конфиденциальных данных](create-a-custom-sensitive-information-type.md)
