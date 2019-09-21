---
title: Идентификационный номер налогоплательщика ЕС
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации для идентификационного номера ЕС. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090264"
---
# <a name="eu-tax-identification-number"></a>Идентификационный номер налогоплательщика ЕС

В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации налогоплательщика (TIN). Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
  
## <a name="austria"></a>Австрия

### <a name="format"></a>Format

Девять цифр с необязательным дефисом и косой чертой.
  
### <a name="pattern"></a>Шаблон

Девять цифр с необязательным дефисом и косой чертой.
  
-  Две цифры 
    
- Дефис (необязательно)
    
- Три цифры
    
- Косая черта (необязательно)
    
- Четыре цифры
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_austria_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

Налоговый номер
  
число
  
Регистрационный номер налогоплательщика
  
tax id
  
st.nr.
  
стеуернуммер
  
## <a name="belgium"></a>Бельгия

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
- Две цифры
    
- "0" или "1"
    
- Одна цифра
    
- "0" или "1" или "2" или "3" 
    
- шесть цифр.
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_belgium_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_belgium_eu_tax_file_number` слово FROM. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_belgium_eu_tax_file_number"></a>Keywords_belgium_eu_tax_file_number

Налоговый номер
  
Национальный регистрационный номер
  
Регистрационный номер налогоплательщика
  
tax id
  
включена
  
включена #
  
нумéро de регистре National
  
нумéро д'идентификатион Фин.
  
## <a name="bulgaria"></a>Болгария

### <a name="format"></a>Format

Десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

10 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_bulgaria_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_bulgaria_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_bulgaria_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_bulgaria_eu_tax_file_number"></a>Keywords_bulgaria_eu_tax_file_number

букн
  
единое гражданское число
  
букн #
  
униформЦивилнумбер #
  
унифицированный гражданский идентификатор
  
равномерный гражданский номер
  
егн
  
номер унифицированного гражданства болгарского языка
  
униформЦивилно #
  
егн #
  
униформ граждански номер
  
Идентификатор униформ
  
униформ граждански ID
  
униформ граждански не
  
## <a name="croatia"></a>Хорватия

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
- Десять цифр, выбран случайным образом
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_croatia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_croatia_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_croatia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_croatia_eu_tax_file_number"></a>Keywords_croatia_eu_tax_file_number

Налоговый номер
  
см
  
tax id
  
oid
  
идентификатора #
  
порезни Брож
  
## <a name="cyprus"></a>Кипр

### <a name="format"></a>Format

Восемь цифр и одна буква в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

Восемь цифр и одна буква:
  
-  "0" 
    
- семь цифр;
    
- Одна буква (без учета регистра)
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_cyprus_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

Налоговый номер
  
см
  
tax id
  
Налоговый код идентификации
  
тик
  
тик #
  
αριθμός φορολογικού μητρώου
  
φορολογική ταυτότητα
  
κωδικός φορολογικού μητρώου
  
## <a name="czech-republic"></a>Чешская Республика

### <a name="format"></a>Format

Девять или десять цифр с необязательной обратной косой чертой
  
### <a name="pattern"></a>Шаблон

Девять или десять цифр с необязательной обратной косой чертой.
  
- Шесть цифр 
    
- Обратная косая черта (необязательно)
    
- Три или четыре цифры
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_czech_republic_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_czech_republic_eu_tax_file_number` слово FROM. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_czech_republic_eu_tax_file_number"></a>Keywords_czech_republic_eu_tax_file_number

Налоговый номер
  
см
  
tax id
  
персональный номер
  
даňовé číсло
  
особнí číсло
  
## <a name="denmark"></a>Дания

### <a name="format"></a>Format

Десять цифр, содержащие дефис
  
### <a name="pattern"></a>Шаблон

Десять цифр с дефисом:
  
-  Шесть цифр, соответствующих дате рождения (ДДММГГ —) 
    
- дефис;
    
- Четыре цифры, которые соответствуют порядковому номеру, где первая цифра соответствует столетию рождения, а последняя цифра соответствует полу лица (нечетный для пола и даже для женщина)
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_denmark_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_denmark_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_denmark_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_denmark_eu_tax_file_number"></a>Keywords_denmark_eu_tax_file_number

Налоговый номер
  
см
  
tax id
  
CPR Number
  
CPR #
  
Скат нуммер
  
Идентификатор Скат
  
## <a name="estonia"></a>Эстония

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
-  Одна цифра, соответствующая пол и столетию рождения, где нечетное число означает "штекер", а четное число указывает на женщина следующим образом: 1, 2 для 19 века; 3, 4 — 20 века; и 5, 6 для 21 века 
    
- Шесть цифр, соответствующих дате рождения (ГГММДД)
    
- Три цифры, которые соответствуют порядковому номеру, разделенному на одну и ту же дату.
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_estonia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_estonia_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_estonia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_estonia_eu_tax_file_number"></a>Keywords_estonia_eu_tax_file_number

Налоговый номер
  
см
  
tax id
  
персональный код
  
максунумбер
  
Идентификатор Максу
  
исикукуд
  
## <a name="finland"></a>Финляндия

### <a name="format"></a>Format

Сочетание цифр, букв и плюса, а также знак минуса
  
### <a name="pattern"></a>Шаблон

Сочетание цифр, букв и плюса и знака "плюс" и "минус" (11 символов).
  
- Шесть цифр
    
- Один из следующих элементов: знак плюса, знак минуса или буква "A" (без учета регистра), где знак "плюс" (без учета регистра) означает 1900-1999, что знак "плюс" находится в диапазоне от 1 до 1800-1899, а "A" означает, что порожденный 2000 и после
    
- Три цифры
    
- Одна буква или один номер
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_finland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_finland_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_finland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_finland_eu_tax_file_number"></a>Keywords_finland_eu_tax_file_number

identification number
  
личный идентификатор
  
идентификационный номер
  
Финский национальный идентификационный номер
  
персоналиднумбер #
  
national identification number
  
идентификационный номер
  
код страны
  
Национальный идентификационный номер
  
ID No
  
туннистенумеро
  
хенкилöтуннус
  
иксилöллинен хенкилöкохтаинен туннистенумеро
  
аинутлаатуинен хенкилöкохтаинен туннус
  
идентититти нумеро
  
Суомен кансаллинен хенкилöтуннус
  
хенкилöтуннуснумеро #
  
кансаллисен туннистенумеро
  
туннуснумеро
  
кансаллинен туннус нумеро
  
## <a name="france"></a>Франция

### <a name="format"></a>Format

13 цифр для отдельных пользователей и девять цифр для сущностей
  
### <a name="pattern"></a>Шаблон

13 цифр для отдельных пользователей:
  
- Одна цифра, которая должна быть равна 0, 1, 2 или 3
    
- 12 цифр.
    
Девять цифр для сущностей
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_france_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

идентификационный номер налога
  
Налоговый номер
  
tax id
  
нумéро д'идентификатион Фин.
  
## <a name="germany"></a>Германия

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
-  Десять цифр 
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_germany_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

Налоговый номер
  
налог но.
  
таксно #
  
такснумбер #
  
такснумбер
  
tax id
  
такси #
  
идентификационный номер налога
  
Налоговый идентификатор
  
стеуернуммер
  
Идентификатор стеуер
  
стеуеридентификатионснуммер
  
## <a name="greece"></a>Греция

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Девять цифр.
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_greece_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_greece_eu_tax_file_number` слово FROM. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

афм
  
ИНН
  
Налоговый код но.
  
Налоговый код No
  
идентификационный номер налога
  
Налоговый номер реестра
  
реестр по номеру налога
  
афм #
  
ИНН #
  
таксидно #
  
таксрегистрино #
  
αριθμός φορολογικού μητρώου
  
аφμ
  
аφμ αριθμός
  
φορολογικού μητρώου Νο.
  
τον αριθμό φορολογικού μητρώου
  
## <a name="hungary"></a>Венгрия

### <a name="format"></a>Format

Десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Десять цифр:
  
-  Одна цифра, которая должна быть "8" 
    
- Пять цифр, которые соответствуют количеству дней между датой 01/01/1867 и датой рождения отдельного лица.
    
- Три цифры, которые соответствуют номеру, созданному шансом выделить людей, которые поставили один и тот же день.
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_hungary_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

идентификационный номер для венгерского налога
  
Венгерский Tin
  
номер налогового удостоверения
  
номер НДС
  
Налоговый орган без
  
идентификационный номер налогоплательщика для налогового кода
  
таксиднумбер #
  
ИНН #
  
хунгатиантин #
  
Налоговый идентификатор
  
таксидно #
  
адóазоносíтó сзáм
  
адóсзáм
  
адóхатóсáг сзáм
  
## <a name="ireland"></a>Ireland (Ирландия)

### <a name="format"></a>Format

Семь цифр, за которыми следует буква без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Семь цифр, за которыми следует буква:
  
-  семь цифр; 
    
- Одна буква (без учета регистра)
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_ireland_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_ireland_eu_tax_file_number"></a>Keywords_ireland_eu_tax_file_number

общедоступная служба
  
Личная общедоступная служба
  
PPS нет
  
Личная служба
  
Служба PPS нет
  
ппсно #
  
Ирландский PPS No
  
публиксервицено #
  
номер личной общедоступной службы
  
уимхир феарсанта сеирбхíсе поиблí
  
PPS уимх
  
уимхир аисеантаис феарсанта
  
## <a name="italy"></a>Италия

### <a name="format"></a>Format

16 букв и цифр в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

16 букв и цифр:
  
-  Три буквы, соответствующие первым трем согласным в имени семейства 
    
- Три буквы, соответствующие первым, третьим и четвертым согласным в имени.
    
- Две цифры, соответствующие последним цифрам года рождения
    
- Одна цифра, соответствующая месяцу рождения, буквы используются в алфавитном порядке, но используются только буквы от A до E, H, L, M, P, R — T (то есть Январь — это R, а Октябрь — R)
    
- Две цифры, которые соответствуют дню рождения, где 40 добавляется к дню рождения женщин, чтобы отличать от мужчин
    
- Четыре цифры, соответствующие коду города, соответствующему органу государственной власти, в котором был создан пользователь, — коды уровня страны используются для иностранных стран
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_italy_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_italy_eu_tax_file_number"></a>Keywords_italy_eu_tax_file_number

Налоговый номер
  
налог но.
  
таксно #
  
такснумбер #
  
такснумбер
  
tax id
  
такси #
  
Финансовый код
  
финансовый отчет по сокостям
  
## <a name="latvia"></a>Латвия

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр в указанном шаблоне
  
-  Шесть цифр, соответствующих дате рождения (ДДММГГ —) 
    
- Одна цифра, соответствующая столетию рождения, где "0" соответствует 19 века, "1" соответствует 20 столетию, а "2" соответствует 21 столетию
    
- Четыре цифры
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_latvia_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_latvia_eu_tax_file_number"></a>Keywords_latvia_eu_tax_file_number

Налоговый номер
  
налог но.
  
таксно #
  
такснумбер #
  
такснумбер
  
tax id
  
такси #
  
идентификационный номер налога
  
Налоговый идентификатор
  
нодокļа нумурс
  
нодокļу идентификāЦижас нумурс
  
нодокļу идентификāЦижа нумурс
  
## <a name="lithuania"></a>Литва

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_lithuania_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_lithuania_eu_tax_file_number"></a>Keywords_lithuania_eu_tax_file_number

Налоговый номер
  
налог но.
  
налог без #
  
такснумбер #
  
такснумбер
  
tax id
  
такси #
  
идентификационный номер налога
  
Налоговый идентификатор
  
Идентификатор мокесčиų
  
мокесčиų нумерис
  
мокесčиų идентификавимас нумерис
  
## <a name="luxemburg"></a>луксембург

### <a name="format"></a>Format

13 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

13 цифр:
  
-  11 цифр. 
    
- две проверочные цифры.
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_luxemburg_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

Налоговый номер
  
налог но.
  
таксно #
  
такснумбер #
  
такснумбер
  
tax id
  
такси #
  
идентификационный номер налога
  
Налоговый идентификатор
  
стеуернуммер
  
Идентификатор стеуер
  
стеуеридентификатионснуммер
  
## <a name="malta"></a>Мальта

### <a name="format"></a>Format

Для национальных замальтийский: 7 цифр и одна буква в указанном шаблоне
  
Мальтийскийные страны и Мальтийский, не являющиеся субъектами: 9 цифр
  
### <a name="pattern"></a>Шаблон

Мальтийский национальные условия: 7 цифр и одна буква
  
-  семь цифр; 
    
- Одна буква (без учета регистра)
    
Мальтийскийные страны и Мальтийский, не являющиеся субъектами: 9 цифр
  
-  девять цифр. 
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_malta_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
  
- Функция `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

Налоговый номер
  
налог но.
  
таксно #
  
такснумбер #
  
такснумбер
  
tax id
  
такси #
  
идентификационный номер налога
  
Налоговый идентификатор
  
нумру ТАТ — такскса
  
ID ТАТ — такскса
  
нумру Ta ' идентификаззжони ТАТ такскса
  
## <a name="netherlands"></a>Нидерланды

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Девять цифр. 
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_netherlands_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

идентификационный номер налога Нидерландов
  
Идентификация налога Нидерландов
  
идентификационный номер налога несерланд
  
Налоговый код несерланд
  
идентификационный номер налога
  
Налоговый идентификатор голландского налога
  
идентификационный номер налога на нидерландском языке
  
tax id
  
Налоговый код #
  
Налоговый номер
  
налог без #
  
см #
  
ИНН
  
ИНН #
  
Tin Нидерландов
  
Tin несерланд
  
Недерландс идентификатиенуммер
  
идентификатиенуммер Van
  
идентификатиенуммер
  
Недерландс идентификатие
  
Недерландс — идентификатор нуммер
  
Недерландс беластингнуммер
  
БТВ нуммер
  
Недерландсе идентификатие
  
## <a name="poland"></a>Польша

### <a name="format"></a>Format

Одиннадцать цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Одиннадцать цифр
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_poland_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

Налоговый номер
  
налог но.
  
таксно #
  
такснумбер #
  
такснумбер
  
нип
  
нип #
  
tax id
  
Налоговый код #
  
Идентификатор НИП
  
Идентификатор НИП #
  
идентификационный номер налога
  
Налоговый идентификатор
  
номер НДС
  
НДС номер
  
ватно #
  
Код НДС
  
Код НДС #
  
Нумер идентификакжи податковеж
  
полски нумер идентификакжи податковеж
  
нумеридентификакжиподатковеж #
  
## <a name="portugal"></a>Португалия

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Девять цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_portugal_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

Налоговый номер
  
налог но.
  
таксно #
  
такснумбер #
  
такснумбер
  
включена
  
включена #
  
финансовый нумеро
  
нúмеро de идентификаçãо Фин.
  
## <a name="romania"></a>Румыния

### <a name="format"></a>Format

13 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

13 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_romania_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_romania_eu_tax_file_number` слово FROM. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_romania_eu_tax_file_number"></a>Keywords_romania_eu_tax_file_number

tax id
  
номер налогового удостоверения
  
Налоговый файл нет
  
tax file number
  
налог без
  
Налоговый номер
  
такси #
  
таксно #
  
ID — UL таксеи
  
нумăрул де идентификаре фискалă
  
## <a name="slovakia"></a>Словакия

### <a name="format"></a>Format

10 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

10 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_slovakia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_slovakia_eu_tax_file_number` слово FROM. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_slovakia_eu_tax_file_number"></a>Keywords_slovakia_eu_tax_file_number

tax id
  
номер налогового удостоверения
  
Идентификатор Tin
  
номер Tin
  
Идентификатор Tin словакиан
  
ИНН
  
Налоговый файл нет
  
tax file number
  
налог без
  
Налоговый номер
  
такси #
  
таксно #
  
даňовé идентификаčнé číсло
  
даňовé číсло
  
даňовé číсло сúбору
  
## <a name="slovenia"></a>Словения

### <a name="format"></a>Format

Восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Восемь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_slovenia_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

tax id
  
номер налогового удостоверения
  
Идентификатор Tin
  
номер Tin
  
Словенский идентификатор Tin
  
ИНН
  
Налоговый файл нет
  
tax file number
  
налог без
  
Налоговый номер
  
такси #
  
таксно #
  
идентификаЦижска šтевилка Давка
  
давčна šтевилка
  
šтевилка давčне датотеке
  
## <a name="spain"></a>Испания

### <a name="format"></a>Format

Семь или восемь цифр, а также одна или две буквы в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

Испанские пользователи с национальной идентификационной карточкой Испании Испания:
  
-  восемь цифр. 
    
- Одна прописная буква (с учетом регистра) 
    
Нерезидентские Спаниардс без национальной идентификационной карточки Испании
  
- Одна прописная буква L (с учетом регистра)
    
- семь цифр;
    
- Одна прописная буква (с учетом регистра) 
    
Резидентный Спаниардс в течение 14 лет без международной идентификационной карточки для Испании:
  
- Одна прописная буква K (с учетом регистра)
    
-  семь цифр; 
    
- Одна прописная буква (с учетом регистра)
    
Фореигнерс с идентификационным номером внешнего получателя
  
- Одна прописная буква "X", "Y" или "Z" (с учетом регистра) 
    
- семь цифр;
    
- Одна прописная буква (с учетом регистра) 
    
Фореигнерс без идентификационного номера внешнего получателя
  
- Одна прописная буква "M" (с учетом регистра) 
    
- семь цифр;
    
- Одна прописная буква (с учетом регистра) 
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_spain_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

tax id
  
номер налогового удостоверения
  
Идентификатор CIF
  
CIF нет
  
код испанского CIF
  
CIF
  
Налоговый файл нет
  
номер испанского CIF
  
tax file number
  
Испанская CIF
  
налог без
  
Налоговый номер
  
такси #
  
таксно #
  
Цифид #
  
спанишЦифид #
  
спанишЦифно #
  
нúмеро de контрибуйенте
  
нúмеро де импуесто корпоративо
  
нúмеро de идентификаЦиóн Фин.
  
CIF нúмеро
  
Цифнúмеро #
  
## <a name="sweden"></a>Швеция

### <a name="format"></a>Format

Десять цифр и символ в указанном шаблоне;
  
### <a name="pattern"></a>Шаблон

Десять цифр и символ:
  
-  Шесть цифр, соответствующих дате рождения (ГГММДД) 
    
- Знак плюс, знак минус или обратная косая черта
    
- Три цифры, которые делают идентификационный номер уникальным, где: 
    
  - Для номеров, выпущенных до 1990, седьмой и восьмой цифрой определяют район рождения или пользователей, порожденных иностранным пользователем.
    
  - Цифра в девятой позиции указывает на пол, который нечетен для пола или даже для розетки.
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_sweden_eu_tax_file_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

tax id
  
Налоговый код но.
  
номер налогового удостоверения
  
tax identification
  
Идентификация налога #
  
налог но.
  
см #
  
такси #
  
Налоговый файл
  
Налоговый файл но.
  
личный идентификационный номер
  
Идентификатор СКАТТ нуммер
  
СКАТТ идентификатион
  
персоннуммер
  
## <a name="uk"></a>ВОЗМЕЩЕН

### <a name="format"></a>Format

Уникальная справочная информация о налогоплательщиках (утр): 10 цифр без пробелов и разделителей
  
Национальный страховой номер (Нино): Дополнительные сведения см. в разделе "Великобритания Национальный страховой номер (Нино) " [, чтобы найти типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
### <a name="pattern"></a>Шаблон

Уникальная справочная информация о налогоплательщиках (утр): 10 цифр
  
Национальный страховой номер (Нино): Дополнительные сведения см. в разделе "Великобритания Национальный страховой номер (Нино) " [, чтобы найти типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_uk_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_uk_eu_tax_file_number` слово FROM. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

tax id
  
Налоговый код но.
  
номер налогового удостоверения
  
tax identification
  
Идентификация налога #
  
налог но.
  
см #
  
такси #
  
Налоговый файл
  
Налоговый файл но.
  
## <a name="see-also"></a>См. также

[Что позволяют искать типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md)

