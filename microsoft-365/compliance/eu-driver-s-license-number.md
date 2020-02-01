---
title: Номер водительского удостоверения для драйвера ЕС
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации номера лицензии для драйвера ЕС. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592660"
---
# <a name="eu-drivers-license-number"></a>Номер водительского удостоверения для драйвера ЕС

В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации номера лицензии для драйвера ЕС. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
  
## <a name="austria"></a>Австрия

### <a name="format"></a>Format

Восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Восемь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_austria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_austria_eu_driver's_license_number` слово FROM. 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_austria_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/>  номер водительского удостоверения  <br/> длно #  <br/> фухрерсчеин  <br/> фухрерсчеин Републик остерреич  <br/> |
   
## <a name="belgium"></a>Бельгия

### <a name="format"></a>Format

10 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

10 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_belgium_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_belgium_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords__belgium_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> длно #  <br/> рижбевижс  <br/> рижбевижснуммер  <br/> фüхрерсчеиннуммер  <br/> фухрерсчеиннуммер  <br/> фуехрерсчеиннуммер  <br/> фüхрерсчеин — НР  <br/> фуехрерсчеин — НР  <br/> фуехрерсчеин — НР  <br/> |
   
## <a name="bulgaria"></a>Болгария

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Девять цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_bulgaria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_bulgaria_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_bulgaria_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> свидетелство за управление на МПС  <br/> свидетелство за управление на моторно превозно средство  <br/> сумпс  <br/> шофьорска книжка  <br/> |
   
## <a name="croatia"></a>Хорватия

### <a name="format"></a>Format

Восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Восемь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_croatia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_croatia_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_croatia_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> возаčка дозвола  <br/> |
   
## <a name="cyprus"></a>Кипр

### <a name="format"></a>Format

12 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

12 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_cyprus_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_cyprus_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_cyprus_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> άδεια οδήγησης  <br/> |
   
## <a name="czech-republic"></a>Чешская Республика

### <a name="format"></a>Format

Две буквы, за которыми следуют шесть цифр.
  
### <a name="pattern"></a>Шаблон

Восемь букв и цифр:
  
- Две буквы (без учета регистра)
    
- пробел (необязательно); 
    
- шесть цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_czech_republic_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_czech_republic_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_czech_republic_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> řидиčскý прúказ  <br/> |
   
## <a name="denmark"></a>Дания

### <a name="format"></a>Format

Восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Восемь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_denmark_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_denmark_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_denmark_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> кøрекорт  <br/> кøрекортнуммер  <br/> |
   
## <a name="estonia"></a>Эстония

### <a name="format"></a>Format

Две буквы, за которыми следуют шесть цифр.
  
### <a name="pattern"></a>Шаблон

Две буквы и шесть цифр:
  
-  Буквы "ET" (без учета регистра); 
    
- шесть цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_estonia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_estonia_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_estonia_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер водительского удостоверения  <br/> длно #  <br/> permis de conduire  <br/> |
   
## <a name="finland"></a>Финляндия

### <a name="format"></a>Format

10 цифр, содержащих дефис.
  
### <a name="pattern"></a>Шаблон

10 цифр, содержащих дефис:
  
-  Шесть цифр 
    
- дефис;
    
-  Четыре цифры 
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_finland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_finland_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_finland_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> ажокортти  <br/> |
   
## <a name="france"></a>Франция

Дополнительные сведения см. в разделе "номер водительского удостоверения для Франции" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Германия

Дополнительные сведения можно найти в разделе "номер водительского удостоверения для немецкого драйвера" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Греция

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

 Девять цифр. 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_greece_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_greece_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_greece_eu_driver "s_license_number**|
|:-----|
|Файл #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> δεια οδήγησης  <br/> Адеиа одигисис  <br/> |
   
## <a name="hungary"></a>Венгрия

### <a name="format"></a>Format

Две буквы, за которыми следуют шесть цифр.
  
### <a name="pattern"></a>Шаблон

Две буквы и шесть цифр:
  
-  Две буквы (без учета регистра) 
    
- шесть цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_hungary_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_hungary_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_hungary_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> везетои енжедели  <br/> |
   
## <a name="ireland"></a>Ireland (Ирландия)

### <a name="format"></a>Format

Шесть цифр, за которыми следуют четыре буквы
  
### <a name="pattern"></a>Шаблон

Шесть цифр и четыре буквы:
  
- Шесть цифр
    
- Четыре буквы (без учета регистра)
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_ireland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_ireland_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_ireland_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> цеадúнас тиомáна  <br/> |
   
## <a name="italy"></a>Италия

Дополнительные сведения см. в разделе "номер водительского удостоверения для Италии" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="latvia"></a>Латвия

### <a name="format"></a>Format

Три буквы, за которыми следуют шесть цифр.
  
### <a name="pattern"></a>Шаблон

Три буквы и шесть цифр:
  
-  Три буквы (без учета регистра) 
    
- шесть цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_latvia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_latvia_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_latvia_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> аутовадīтāжа аплиекīба  <br/> |
   
## <a name="lithuania"></a>Литва

### <a name="format"></a>Format

Восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

 Восемь цифр. 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_lithuania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_lithuania_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_lithuania_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> ваируотожо паžимėжимас  <br/> |
   
## <a name="luxemburg"></a>луксембург

### <a name="format"></a>Format

Шесть цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

 шесть цифр. 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_luxemburg_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_luxemburg_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_luxemburg_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> фахрерлаубнис  <br/> |
   
## <a name="malta"></a>Мальта

### <a name="format"></a>Format

Сочетание двух символов и шести цифр в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

Сочетание двух символов и шести цифр:
  
- Два символа (цифры или буквы без учета регистра);
    
- пробел (необязательно); 
    
- три цифры; 
    
- пробел (необязательно); 
    
- Три цифры
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_malta_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_malta_eu_driver's_license_number` слово FROM. 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_malta_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> лиċензжаные зада Севкан  <br/> |
   
## <a name="netherlands"></a>Нидерланды

### <a name="format"></a>Format

10 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

10 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_netherlands_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_netherlands_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_netherlands_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> permis de conduire  <br/> рижбевижс  <br/> рижбевижснуммер  <br/> |
   
## <a name="poland"></a>Польша

### <a name="format"></a>Format

14 цифр, содержащих 2 косых черты.
  
### <a name="pattern"></a>Шаблон

14 цифр и 2 косых черт:
  
-  Пять цифр 
    
- косая черта;
    
- Две цифры
    
- косая черта;
    
- семь цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_poland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_poland_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_poland_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> право жазди  <br/> |
   
## <a name="portugal"></a>Португалия

### <a name="format"></a>Format

Две буквы, за которыми следуют семь чисел в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют семь цифр со специальными символами:
  
-  Две буквы (без учета регистра) 
    
- дефис;
    
- Шесть цифр
    
- Пробел
    
- одна цифра.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_portugal_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_portugal_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_portugal_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> картеира de моториста  <br/> |
   
## <a name="romania"></a>Румыния

### <a name="format"></a>Format

Один символ, за которым следуют восемь цифр
  
### <a name="pattern"></a>Шаблон

Один символ, за которым следуют восемь цифр:
  
-  Одна буква (без учета регистра) или цифра 
    
- восемь цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_romania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_romania_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_romania_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> разрешение de кондуцере  <br/> |
   
## <a name="slovakia"></a>Словакия

### <a name="format"></a>Format

Один символ, за которым следуют семь цифр.
  
### <a name="pattern"></a>Шаблон

Один символ, за которым следуют семь цифр.
  
- Одна буква (без учета регистра) или цифра
    
-  семь цифр. 
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_slovakia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_slovakia_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_slovakia_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> водиčскý преуказ  <br/> |
   
## <a name="slovenia"></a>Словения

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Девять цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_slovenia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_slovenia_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_slovenia_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> возниšко доволженже  <br/> |
   
## <a name="spain"></a>Испания

### <a name="format"></a>Format

Восемь цифр, за которыми следует один символ
  
### <a name="pattern"></a>Шаблон

Восемь цифр, за которыми следует один символ:
  
-  восемь цифр. 
    
- Одна цифра или буква (без учета регистра)
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_spain_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_spain_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_spain_eu_driver "s_license_number**|
|:-----|
|длно #  <br/> DL #  <br/> Drivers лик.  <br/> Лицензия на драйвер  <br/> driver license  <br/> drivers licence  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> driving licence  <br/> driving license  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> драйвер номер лицензии  <br/> номер лицензии на драйверы  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> номер водительской лицензии  <br/> номер водительского удостоверения  <br/> движущие разрешение  <br/> движущие число разрешений  <br/> пермисо de кондукЦиóн  <br/> пермисо кондукЦиóн  <br/> нúмеро лиценЦиа кондуЦир  <br/> нúмеро de карнет де кондуЦир  <br/> нúмеро карнет кондуЦир  <br/> лиценЦиа кондуЦир  <br/> нúмеро de пермисо де кондуЦир  <br/> нúмеро де пермисо кондуЦир  <br/> нúмеро пермисо кондуЦир  <br/> пермисо кондуЦир  <br/> лиценЦиа de манежо  <br/> El карнет de кондуЦир  <br/> Карнет кондуЦир  <br/> |
   
## <a name="sweden"></a>Швеция

### <a name="format"></a>Format

Десять цифр, содержащие дефис
  
### <a name="pattern"></a>Шаблон

Десять цифр, содержащих дефис:
  
-  Шесть цифр 
    
- дефис;
    
- Четыре цифры
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_sweden_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_sweden_eu_driver's_license_number` слово FROM. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Ключевые слова

| |
|**Keywords_sweden_eu_driver "s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> номер водительского удостоверения  <br/> Лицензия на драйвер  <br/> Drivers лик.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> номер водительского удостоверения  <br/> номер лицензии на драйвер  <br/> номер водительского удостоверения  <br/> длно #  <br/> кöркорт  <br/> |
   
## <a name="uk"></a>ВОЗМЕЩЕН

Дополнительные сведения см. в разделе "Великобритания Номер водительского удостоверения, в [котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>См. также

[Что позволяют искать типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md)

