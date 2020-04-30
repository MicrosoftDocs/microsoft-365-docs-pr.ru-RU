---
title: Номер паспорта ЕС
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС Passport Number. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: 56eb79dd067ca89600f92ea57eaaf01e562f9388
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938743"
---
# <a name="eu-passport-number"></a>Номер паспорта ЕС

В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС Passport Number. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
  
## <a name="austria"></a>Австрия

### <a name="format"></a>Format

Одна буква, за которой следует необязательный пробел и семь цифр
  
### <a name="pattern"></a>Шаблон

Сочетание одной буквы, семи цифр и одного пробела:
  
- Одна буква (без учета регистра)
    
- Один пробел (необязательно)
    
- семь цифр.
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_austria_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|passport number  <br/> Австрийский номер паспорта  <br/> паспорт нет  <br/> реисепасс  <br/> öстерреичисч реисепасс  <br/> |
   
## <a name="belgium"></a>Бельгия

### <a name="format"></a>Format

Две буквы, за которыми следуют шесть цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют шесть цифр.
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_belgium_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|passport number  <br/> Бельгийский номер паспорта  <br/> паспорт нет  <br/> паспурт  <br/> паспуртнуммер  <br/> реисепасс Кеин  <br/> реисепасс  <br/> |
   
## <a name="bulgaria"></a>Болгария

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

 Девять цифр. 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_bulgaria_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для болгарского языка  <br/> паспорт нет  <br/> номер на паспорта  <br/> |
   
## <a name="croatia"></a>Хорватия

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

 Девять цифр. 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_croatia_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для хорватского языка  <br/> паспорт нет  <br/> Брож путовнице  <br/> |
   
## <a name="cyprus"></a>Кипр

### <a name="format"></a>Format

Одна буква, за которой следуют 6-8 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Одна буква, за которой следуют шесть и восемь цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_cyprus_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для Кипр  <br/> паспорт нет  <br/> αριθμό διαβατηρίου  <br/> |
   
## <a name="czech-republic"></a>Чехия

### <a name="format"></a>Format

Восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Восемь цифр без пробелов и разделителей
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_czech_republic_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для чешского языка  <br/> паспорт нет  <br/> цестовнí PAS  <br/> соответствующий  <br/> |
   
## <a name="denmark"></a>Дания

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

 Девять цифр. 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_denmark_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для датского языка  <br/> паспорт нет  <br/> соответствующий  <br/> паснуммер  <br/> |
   
## <a name="estonia"></a>Эстония

### <a name="format"></a>Format

Одна буква, за которой следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Одна буква, за которой следуют семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_estonia_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для Эстонии  <br/> паспорт нет  <br/> Исти коданику Pass  <br/> |
   
## <a name="finland"></a>Финляндия

Дополнительные сведения можно найти в разделе "Финляндия Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Франция

Дополнительные сведения можно найти в разделе "Франция Passport Number", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Германия

Дополнительные сведения можно найти в разделе "немецкий паспорт номер", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Греция

### <a name="format"></a>Format

Две буквы, за которыми следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_greece_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта греческого алфавита  <br/> паспорт нет  <br/> διαβατηριο  <br/> |
   
## <a name="hungary"></a>Венгрия

### <a name="format"></a>Format

Две буквы, за которыми следуют шесть или семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют шесть или семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_hungary_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|passport number  <br/> Венгерский номер паспорта  <br/> паспорт нет  <br/> úтлевéл сзáма  <br/> |
   
## <a name="ireland"></a>Ирландия

### <a name="format"></a>Format

Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Две буквы или цифры, за которыми следуют семь цифр:
  
- две цифры или буквы (без учета регистра);
    
- семь цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_ireland_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|passport number  <br/> Ирландский номер паспорта  <br/> паспорт нет  <br/> соответствующий  <br/> службу  <br/> пассепорт  <br/> пассепорт нумеро  <br/> |
   
## <a name="italy"></a>Италия

### <a name="format"></a>Format

Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Две буквы или цифры, за которыми следуют семь цифр:
  
- две цифры или буквы (без учета регистра);
    
- семь цифр.
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_italy_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|номер паспорта для итальянского языка  <br/> Репубблика итальянский пассапорто  <br/> пассапорто  <br/> пассапорто итальянский  <br/> passport number  <br/> Итальянский пассапорто нумеро  <br/> пассапорто нумеро  <br/> нумéро пассепорт италиен  <br/> нумéро пассепорт  <br/> |
   
## <a name="latvia"></a>Латвия

### <a name="format"></a>Format

Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Две буквы или цифры, за которыми следуют семь цифр:
  
- две цифры или буквы (без учета регистра);
    
- семь цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_latvia_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для Латвии  <br/> паспорт нет  <br/> ПАСЕ нумурс  <br/> |
   
## <a name="lithuania"></a>Литва

### <a name="format"></a>Format

Восемь цифр или букв без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Восемь цифр или букв (без учета регистра)
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_lithuania_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта лисуниан  <br/> паспорт нет  <br/> Пасо нумерис  <br/> |
   
## <a name="luxemburg"></a>луксембург

### <a name="format"></a>Format

Восемь цифр или букв без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Восемь цифр или букв (без учета регистра)
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_nation_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_nation_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для Латвии  <br/> паспорт нет  <br/> пасснуммер  <br/> |
   
## <a name="malta"></a>Мальта

### <a name="format"></a>Format

Семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

 семь цифр. 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_malta_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта Мальтийский  <br/> паспорт нет  <br/> нумру Тал — пассапорт  <br/> |
   
## <a name="netherlands"></a>Нидерланды

### <a name="format"></a>Format

Девять букв или цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Девять букв или цифр;
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_netherlands_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|номер паспорта для нидерландского языка  <br/> passport number  <br/> номер паспорта Нидерландов  <br/> недерланден паспурт нуммер  <br/> паспурт  <br/> недерланден паспуртнуммер  <br/> паспуртнуммер  <br/> |
   
## <a name="poland"></a>Польша

Дополнительные сведения можно найти в разделе "Польша Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Португалия

### <a name="format"></a>Format

Одна буква, за которой следуют шесть цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Одна буква, за которой следуют шесть цифр:
  
- Одна буква (без учета регистра)
    
- шесть цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_portugal_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для португальского языка  <br/> паспорт нет  <br/> нúмеро Do пассапорте  <br/> |
   
## <a name="romania"></a>Румыния

### <a name="format"></a>Format

Восемь или девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Восемь или девять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_romania_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для румынского языка  <br/> паспорт нет  <br/> нумăрул паșапортулуи  <br/> |
   
## <a name="slovakia"></a>Словакия

### <a name="format"></a>Format

Одна цифра или буква, за которой следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Одна цифра или буква (без учета регистра), за которой следуют семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_slovakia_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта словакиан  <br/> паспорт нет  <br/> číсло Пасу  <br/> |
   
## <a name="slovenia"></a>Словения

### <a name="format"></a>Format

Две буквы, за которыми следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют семь цифр:
  
- Буква "P"
    
- Одна прописная буква
    
- семь цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_slovenia_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|passport number  <br/> номер паспорта для словенского языка  <br/> паспорт нет  <br/> Список потнега šтевилка  <br/> |
   
## <a name="spain"></a>Испания

### <a name="format"></a>Format

Сочетание букв и цифр из восьми или девяти символов без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Сочетание букв и цифр из восьми или девяти символов:
  
-  Две цифры или буквы 
    
- Одна цифра или буква (необязательно)
    
- шесть цифр.
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_spain_eu_passport_number` слово FROM. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|службу  <br/> Служба Passport, Испания  <br/> Книга Passport  <br/> passport number  <br/> паспорт нет  <br/> либрета пасапорте  <br/> нúмеро пасапорте  <br/> еспаñа пасапорте  <br/> пасапорте  <br/> |
   
## <a name="sweden"></a>Швеция

Дополнительные сведения можно найти в разделе "Швеции Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="uk"></a>ВОЗМЕЩЕН

Дополнительные сведения см. в разделе "США/Великобритания Номер паспорта [, который ищет типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>См. также

[Что позволяют искать типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md)

