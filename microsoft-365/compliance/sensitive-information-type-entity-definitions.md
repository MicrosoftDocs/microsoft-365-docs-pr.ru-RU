---
title: Определения типов конфиденциальной информации
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
description: Защита от потери данных (DLP) в центре безопасности для обеспечения &amp; соответствия требованиям включает типы конфиденциальной информации 80, готовые к использованию в политиках защиты от потери данных. В этой статье перечислены все эти типы конфиденциальной информации и показано, каким именно образом политика защиты от потери данных выявляет каждый тип.
ms.openlocfilehash: 8716a6d4e29f94ff3d7bedaaadece2449fcec8a3
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950287"
---
# <a name="sensitive-information-type-entity-definitions"></a>Определения типов конфиденциальной информации

Защита от потери данных (DLP) в центре соответствия требованиям включает множество типов конфиденциальной информации, готовых к использованию в политиках защиты от потери данных. В этой статье перечислены все эти типы конфиденциальной информации и показано, каким именно образом политика защиты от потери данных выявляет каждый тип. Тип конфиденциальной информации определяется шаблоном, который можно идентифицировать регулярным выражением или функцией. Кроме того, для идентификации типа конфиденциальной информации могут использоваться подкрепляющие доказательства, такие как ключевые слова и контрольные суммы. Уровень вероятности и расположение слов и знаков также используются в процессе оценки.
  
## <a name="aba-routing-number"></a>Номер маршрутизации код банка ABA

### <a name="format"></a>Format

девять цифр, которые могут быть в форматированном или неформатированном шаблоне

### <a name="pattern"></a>Шаблон

Форматируемые
- четыре цифры, начинающиеся с 0, 1, 2, 3, 6, 7 или 8.
- дефис
- четыре цифры
- дефис
- цифра

Неформатированный: девять последовательных цифр, начиная с 0, 1, 2, 3, 6, 7 или 8. 

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_aba_routing находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_ABA_Routing.

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>Keywords

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- код банка ABA
- aba#
- aba routing #
- aba routing number
- код банка ABA #
- абараутинг #
- aba number
- абараутингнумбер
- american bank association routing #
- american bank association routing number
- американбанкассоЦиатионраутинг #
- американбанкассоЦиатионраутингнумбер
- bank routing number
- банкраутинг #
- банкраутингнумбер
- routing transit number
- ртн 
   
## <a name="argentina-national-identity-dni-number"></a>Внутренний идентификационный номер (DNI), Аргентина

### <a name="format"></a>Format

Восемь цифр, разделенных точками.

### <a name="pattern"></a>Шаблон

Восемь цифр:
- две цифры
- точка
- три цифры
- точка
- три цифры

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_argentina_national_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_argentina_national_id.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- Удостоверение 
- Идентификация национальной идентификационной карточки 
- DNI 
- Национальная реестр пользователей NIC 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- идентидад 
- идентификаЦиóн 
   
## <a name="australia-bank-account-number"></a>Номер банковского счета для Австралии

### <a name="format"></a>Format

шесть – ТВН цифрами с номером филиала банка или без него

### <a name="pattern"></a>Шаблон

Номер счета — от шести до десяти цифр.

Номер филиала государственного банка Австралии
- три цифры 
- дефис 
- три цифры

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_australia_bank_account_number.
- регулярное выражение Regex_australia_bank_account_number_bsb находит содержимое, которое соответствует шаблону.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_australia_bank_account_number.

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bank code
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- иаеа

## <a name="australia-business-number"></a>Бизнес-номер Австралии

### <a name="format"></a>Format

11 цифр с необязательными ограничителями

### <a name="pattern"></a>Шаблон

11 цифр с необязательными ограничителями:

- две цифры
- параметр "дефис" или "пробел"
- три цифры
- параметр "дефис" или "пробел"
- три цифры
- параметр "дефис" или "пробел"
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_australian_business_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_australian_business_number.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_australian_business_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- Бизнес-деятельность Австралии
- Рабочий номер
- абн #
- бусинессид #
- Идентификатор бизнеса
- абн
- бусинессно #

## <a name="australia-company-number"></a>Номер компании Австралии

### <a name="format"></a>Format

девять цифр с разделителями

### <a name="pattern"></a>Шаблон

девять цифр с разделителями:

- три цифры
- пробел
- три цифры
- пробел
- три цифры


### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_Australian_Company_Number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keyword_Australian_Company_Number.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Функция Func_Australian_Company_Number находит содержимое, которое соответствует шаблону;

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- можно
- номер компании Австралии
- номер компании Австралии #
- номер компании Австралии
- Компания No для Австралии (Австралия)
- Компания No для Австралии (Австралия) #
- Австралийский номер компании

## <a name="australia-drivers-license-number"></a>Номер водительского удостоверения для Австралии

### <a name="format"></a>Format

девять букв и цифр

### <a name="pattern"></a>Шаблон

девять букв и цифр: 

- две цифры или буквы (без учета регистра). 
- две цифры 
- пять цифр или букв (без учета регистра)

OR

- один-два необязательных буквы (без учета регистра) 
- от четырех до девяти цифр

OR

- девять цифр или букв (без учета регистра);

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_australia_drivers_license_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_australia_drivers_license_number;
- ни одно ключевое слово из Keyword_australia_drivers_license_number_exclusions не находится.

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
- international driving permit
- дриверлиценце
- дриверлиценцес
- Driver Lic
- Driver Licence
- Driver Licences
- дриверслик
- дриверслиценце
- дриверслиценцес
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver ' LIC
- Driver ' LICS
- Driver ' Licence
- Driver ' Licences
- Driver' Lic
- Driver' Lics
- Driver' Licence
- Driver' Licences
- дривер'слик
- дривер'сликс
- дривер'слиценце
- дривер'слиценцес
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- дриверлик #
- дриверликс #
- дриверлиценце #
- дриверлиценцес #
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- дриверслик #
- дриверсликс #
- дриверслиценце #
- дриверслиценцес #
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver ' LIC #
- Driver ' LICS #
- Driver ' Licence #
- Driver ' Licences #
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- дривер'слик #
- дривер'сликс #
- дривер'слиценце #
- дривер'слиценцес #
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences# 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- AAA
- дриверлиценсе
- дриверлиценсес
- Driver License
- Driver Licenses
- дриверслиценсе
- дриверслиценсес
- Drivers License
- Drivers Licenses
- Driver ' License
- Driver ' Licenses
- Driver' License
- Driver' Licenses
- дривер'слиценсе
- дривер'слиценсес
- Driver's License
- Driver's Licenses
- дриверлиценсе #
- дриверлиценсес #
- Driver License#
- Driver Licenses#
- дриверслиценсе #
- дриверслиценсес #
- Drivers License#
- Drivers Licenses#
- Driver ' License #
- Driver ' Licenses #
- Driver' License#
- Driver' Licenses#
- дривер'слиценсе #
- дривер'слиценсес #
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>Номер медицинской учетной записи Австралии

### <a name="format"></a>Format

10–11 цифр.

### <a name="pattern"></a>Шаблон

10–11 цифр.
- Первая цифра находится в диапазоне 2-6
- девятая цифра — это контрольная цифра
- Десятая цифра — это цифра, связанная с вопросом
- Одиннадцатая цифра (необязательно) — индивидуальный номер

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_australian_medical_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_Australia_Medical_Account_Number;
- Контрольная сумма проходит проверку.


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- медикаре

   
## <a name="australia-passport-number"></a>Номер паспорта для Австралии

### <a name="format"></a>Format

Буква, за которой следуют семь цифр.

### <a name="pattern"></a>Шаблон

Буква (без учета регистра), за которой следуют семь цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_australia_passport_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keyword_passport или Keyword_australia_passport_number.

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Службу #
- пасспортид
- пасспортно
- пасспортнумбер
- パスポート
- パスポート番号
- パスポートのнум
- パスポート＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- пассепорт #
- пассепортнон
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- службу
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- Visa
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>Номер файла налога для Австралии

### <a name="format"></a>Format

от восьми до девяти цифр

### <a name="pattern"></a>Шаблон

от восьми до девяти цифр, как правило, представляются пробелы следующим образом:
- три цифры 
- необязательный пробел 
- три цифры 
- необязательный пробел 
- две и три цифры, где последняя цифра — проверочная.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_australian_tax_file_number находит содержимое, которое соответствует шаблону;
- ни одно ключевое слово из Keyword_Australia_Tax_File_Number или Keyword_number_exclusions не найдено;
- Контрольная сумма проходит проверку.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- тфн

## <a name="austria-drivers-license-number"></a>Номер водительского удостоверения для Австрии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

восемь цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение  `Regex_austria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_austria_eu_driver's_license_number` . 
    
```xml
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- driver's licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- фухрерсчеин
- фухрерсчеин Републик остерреич

## <a name="austria-identity-card"></a>Австрийская идентификационная карточка

### <a name="format"></a>Format

24 – символическое сочетание букв, цифр и специальных символов;
  
### <a name="pattern"></a>Шаблон

24 символа:
  
-  22 буквы (без учета регистра), цифры, обратные косые черты, косые черты и знаки плюса 
    
- две буквы (без учета регистра), цифры, обратные косые черты, знаки косой черты, знаки плюса и знаки равенства.
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение  `Regex_austria_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_austria_eu_national_id_card` . 
   
```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- идентификационный номер
- 
national id
- персоналаусвеис Републик öстерреич

## <a name="austria-passport-number"></a>Номер паспорта для Австрии
Этот объект типа конфиденциальной информации доступен только в типе сенситивеинформатион Passport Number.

### <a name="format"></a>Format

Одна буква, за которой следует необязательный пробел и семь цифр
  
### <a name="pattern"></a>Шаблон

Сочетание одной буквы, семи цифр и одного пробела:
  
- одна буква (без учета регистра)
- один пробел (необязательно)
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_austria_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- passport number
- Австрийский номер паспорта
- паспорт нет
- реисепасс
- öстерреичисч реисепасс

## <a name="austria-social-security-number-or-equivalent-identification"></a>Австрийский номер социального страхования или эквивалентная идентификация
Этот объект типа конфиденциальной информации доступен только в номере социального страхования ЕС или эквивалентного идентификатора.

### <a name="format"></a>Format

10 цифр в указанном формате
  
### <a name="pattern"></a>Шаблон

10 цифр:
  
- три цифры, соответствующие серийному номеру. 
- одна контрольная цифра
- шесть цифр, соответствующих дате рождения (ДДММГГ —)
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция "Func_austria_eu_
- _or_equivalent ' находит содержимое, которое соответствует шаблону; 
- Найдено ключевое слово FROM  `Keywords_austria_eu_ssn_or_equivalent` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_austria_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- социальное страхование нет
- social security number
- social security code
- страховой номер
- Австрийский SSN
- SSN #
- SSN
- код страхования
- код страхования #
- соЦиалсекуритино #
- созиалверсичерунгснуммер
- созиале сичерхеит Кеин
- версичерунгснуммер

## <a name="austria-tax-identification-number"></a>Налоговый идентификационный номер для Австрии

### <a name="format"></a>Format

девять цифр с необязательным дефисом и косой чертой.
  
### <a name="pattern"></a>Шаблон

девять цифр с необязательным дефисом и косой чертой.
  
- две цифры
- дефис (необязательно)
- три цифры
- косая черта (необязательно)
- четыре цифры
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_austria_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Функция  `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- öстерреич
- st.nr.
- стеуернуммер
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- Налоговый номер
 
## <a name="austria-value-added-tax"></a>Налог на добавленную стоимость (Австрия)

### <a name="format"></a>Format

11-буквенно-буквенно-буквенный шаблон

### <a name="pattern"></a>Шаблон

11-буквенно-цифровой буквенно-значный шаблон:

- A или a
- T или t
- Необязательный пробел
- U или u
- необязательный пробел
- две или три цифры
- необязательный пробел
- четыре цифры
- необязательный пробел
- одна или две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_Austria_Value_Added_Tax находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keyword_Austria_Value_Added_Tax.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_Austria_Value_Added_Tax находит содержимое, которое соответствует шаблону;

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- номер НДС
- процент #
- Австрийский номер НДС
- НДС номер
- ватно #
- Налоговый номер добавленной стоимости
- Австрийский НДС
- мвст
- умсатзстеуернуммер
- мвстнуммер
- уст. идентификатионснуммер
- умсатзстеуер — идентификатионснуммер
- идентификационный номер НДС
- номер Ату
- UID Number


## <a name="azure-documentdb-auth-key"></a>Ключ проверки подлинности Azure DocumentDB

### <a name="format"></a>Format

Строка "DocumentDb", за которой следуют символы и строки, описанные в приведенном ниже шаблоне.

### <a name="pattern"></a>Шаблон

- Строка "DocumentDb"
- Любая комбинация из 3-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- Символ "больше" (>), знак равенства (=), кавычки (") или апостроф (')
- Любая комбинация 86 строчных или прописных букв, цифр, символов косой черты (/) или знака плюса (+).
- Два знака равенства (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureDocumentDBAuthKey находит содержимое, которое соответствует шаблону;
- Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- компанией
- компании
- базу
- песочниц
- онебокс
- localhost
- 127.0.0.1
- тестакс.<!--no-hyperlink-->порта
- s — int.<!--no-hyperlink-->команде

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Строка подключения к базе данных Azure IAAS и строка подключения к SQL Azure

### <a name="format"></a>Format

Строка "Server", "Server" или "Data Source", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "клаудапп. Azure".<!--no-hyperlink-->com "или" клаудапп. Azure.<!--no-hyperlink-->NET "или" Database. Windows.<!--no-hyperlink-->NET ", а также строку" Password "или" Password "или" pwd ".

### <a name="pattern"></a>Шаблон

- строка "Server", "Server" или "Data Source"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- Строка "клаудапп. Azure.<!--no-hyperlink-->com "," клаудапп. Azure.<!--no-hyperlink-->NET "или" Database. Windows.<!--no-hyperlink-->команде
- Любая комбинация из 1-300 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- строка "Password", "Password" или "pwd"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- один или несколько символов, не отделяющая точку с запятой (;), кавычки (") или апостроф (')
- точка с запятой (;), кавычки (") или апостроф (')

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureConnectionString находит содержимое, которое соответствует шаблону;
- Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- компанией
- компании
- базу
- песочниц
- онебокс
- localhost
- 127.0.0.1
- тестакс.<!--no-hyperlink-->порта
- s — int.<!--no-hyperlink-->команде

## <a name="azure-iot-connection-string"></a>Строка подключения Azure IoT

### <a name="format"></a>Format

Строка "HostName", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, включая строки "Azure — Devices.<!--no-hyperlink-->NET "и" Шаредакцесскэй ".

### <a name="pattern"></a>Шаблон

- строка "HostName"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- строка "Azure — Devices.<!--no-hyperlink-->команде
- Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- строка "Шаредакцесскэй"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- Любая комбинация 43 строчных или прописных букв, цифр, символов косой черты (/) или знака плюса (+).
- знак равенства (=);

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureIoTConnectionString находит содержимое, которое соответствует шаблону;
- Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- компанией
- компании
- базу
- песочниц
- онебокс
- localhost
- 127.0.0.1
- тестакс.<!--no-hyperlink-->порта
- s — int.<!--no-hyperlink-->команде

## <a name="azure-publish-setting-password"></a>Пароль для параметра публикации Azure

### <a name="format"></a>Format

Строка "усерпвд =", за которой следует буквенно-цифровая строка.

### <a name="pattern"></a>Шаблон

- строка "усерпвд ="
- Любая комбинация букв или цифр в нижнем регистре 60
- знак кавычек (")

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzurePublishSettingPasswords находит содержимое, которое соответствует шаблону;
- Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- компанией
- компании
- базу
- песочниц
- онебокс
- localhost
- 127.0.0.1
- тестакс.<!--no-hyperlink-->порта
- s — int.<!--no-hyperlink-->команде

## <a name="azure-redis-cache-connection-string"></a>Строка подключения к кэшу Azure Redis

### <a name="format"></a>Format

Строка "Redis. Cache. Windows.<!--no-hyperlink-->NET, за которыми следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "Password" или "pwd".

### <a name="pattern"></a>Шаблон

- строка "Redis. Cache. Windows.<!--no-hyperlink-->команде
- Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- строка "Password" или "pwd"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- любое сочетание 43 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).
- знак равенства (=);

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureRedisCacheConnectionString находит содержимое, которое соответствует шаблону..
- Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- компанией
- компании
- базу
- песочниц
- онебокс
- localhost
- 127.0.0.1
- тестакс.<!--no-hyperlink-->порта
- s — int.<!--no-hyperlink-->команде

## <a name="azure-sas"></a>SAS Azure

### <a name="format"></a>Format

Строка "SIG", за которой следуют символы и строки, описанные в приведенном ниже шаблоне.

### <a name="pattern"></a>Шаблон

- строка "SIG"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- любое сочетание 43-53 символов, которые являются буквами нижнего или верхнего регистра, цифрами или знаком процента (%)
- строка "% 3D"
- любой символ, который не является буквой нижнего или верхнего регистра, цифрой или знаком процента (%)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureSAS находит содержимое, которое соответствует шаблону;

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Строка подключения к служебной шине Azure

### <a name="format"></a>Format

Строка "EndPoint", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строки "сервицебус. Windows.<!--no-hyperlink-->NET "и" Шаредакцескэй ".

### <a name="pattern"></a>Шаблон

- строка "EndPoint"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- строка "сервицебус. Windows.<!--no-hyperlink-->команде
- Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- строка "Шаредакцесскэй"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- любое сочетание 43 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).
- знак равенства (=);

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureServiceBusConnectionString находит содержимое, которое соответствует шаблону..
- Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- компанией
- компании
- базу
- песочниц
- онебокс
- localhost
- 127.0.0.1
- тестакс.<!--no-hyperlink-->порта
- s — int.<!--no-hyperlink-->команде

## <a name="azure-storage-account-key"></a>Ключ учетной записи хранилища Azure

### <a name="format"></a>Format

Строка "Дефаултендпоинтспротокол", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "AccountKey".

### <a name="pattern"></a>Шаблон

- строка "Дефаултендпоинтспротокол"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- строка "AccountKey"
- ноль — два символа пробела
- знак равенства (=);
- ноль — два символа пробела
- любое сочетание 86 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).
- два знака равенства (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureStorageAccountKey находит содержимое, которое соответствует шаблону;
- Регулярное выражение CEP_AzureEmulatorStorageAccountFilter не **находит содержимое** , которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/Кбхбексогмгв = =

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- компанией
- компании
- базу
- песочниц
- онебокс
- localhost
- 127.0.0.1
- тестакс.<!--no-hyperlink-->порта
- s — int.<!--no-hyperlink-->команде

## <a name="azure-storage-account-key-generic"></a>Ключ учетной записи хранилища Azure (общий)

### <a name="format"></a>Format

Любая комбинация 86 строчных или прописных букв, цифр, знаков косой черты (/) или знака плюса (+) перед или за ними следуют символы, указанные в приведенном ниже шаблоне.

### <a name="pattern"></a>Шаблон

- ноль к одному символу "больше" (>), апостроф ('), знак равенства (=), кавычки (") или решетку (#)
- любое сочетание 86 символов, которые представляют собой буквы в нижнем или верхнем регистре, цифры, косую черту (/) или знак плюса (+).
- два знака равенства (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureStorageAccountKeyGeneric находит содержимое, которое соответствует шаблону;

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Номер водительского удостоверения для бельгийского драйвера
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

десять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_belgium_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_belgium_eu_driver's_license_number` .
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

**Keywords__belgium_eu_driver "s_license_number**

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- длно #
- рижбевижс
- рижбевижснуммер
- фüхрерсчеиннуммер
- фухрерсчеиннуммер
- фуехрерсчеиннуммер
- фüхрерсчеин — НР
- фуехрерсчеин — НР
- фуехрерсчеин — НР

## <a name="belgium-national-number"></a>Бельгийский национальный номер

### <a name="format"></a>Format

11 цифр, а также необязательные разделители

### <a name="pattern"></a>Шаблон

11 цифр, а также разделители:
- шесть цифр и две дополнительные точки в формате гг. Мм. DD для даты рождения 
- Необязательный разделитель из точки, тире, пробела 
- три последовательные цифры (нечетные для мужчин, даже для женщин). 
- Необязательный разделитель из точки, тире, пробела 
- две контрольные цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_belgium_national_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_belgium_national_number;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- функция Func_belgium_national_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- аантал
- бнн #
- бнн
- д'идентитé корзины
- Идентификация National
- идентифиантнатионал #
- идентификатие
- процедура
- идентификатион
- идентификатионснуммер
- идентифизиерунг
- идентитé
- идентитеит
- идентитеитскаарт
- хищения
- инскриптион
- номер страны
- Национальный регистр
- натионалнумбер #
- натионалнумбер
- включена #
- включена
- нумéро д'ассурé
- нумéро de регистре National
- numéro de sécurité

- numéro d'identification
- numéro d'immatriculation
- Национальный нумéро
- нумéронатионал #
- личный идентификационный номер
- персоналаусвеис
- персоналиднумбер #
- регистратие
- зарегистрировал
- регистратионснумме
- регистриерунг
- social security number

- SSN #
- SSN
- стеуернуммер
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #

## <a name="belgium-passport-number"></a>Номер паспорта Бельгии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

две буквы, за которыми следуют шесть цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

две буквы, за которыми следуют шесть цифр.
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_belgium_eu_passport_number` .

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- passport number
- Бельгийский номер паспорта
- паспорт нет
- паспурт
- паспуртнуммер
- реисепасс Кеин
- реисепасс

## <a name="belgium-social-security-number-or-equivalent-identification"></a>Бельгийский номер социального страхования или идентификатор эквивалентной идентификации
Этот объект типа конфиденциальной информации доступен только в номере социального страхования ЕС или эквивалентного идентификатора.

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция  `Func_belgium_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_belgium_eu_ssn_or_equivalent` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_belgium_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

- Бельгийский национальный номер
- номер страны
- social security number
- натионалнумбер #
- SSN #
- SSN
- натионалнумбер
- бнн #
- бнн
- личный идентификационный номер
- персоналиднумбер #
- Национальный нумéро
- numéro de sécurité
- нумéро д'ассурé
- Идентификация National
- идентифиантнатионал #
- нумéронатионал #


## <a name="belgium-value-added-tax-number"></a>Налоговый номер добавленной стоимости (Бельгия)

### <a name="format"></a>Format

12-буквенно-буквенно-буквенный шаблон

### <a name="pattern"></a>Шаблон

12-буквенно-буквенно-символьный шаблон:

- буква B или b
- буква E или e
- цифра 0
- цифра от 1 до 9
- Необязательная точка или дефис или пробел
- четыре цифры
- Необязательная точка или дефис или пробел
- четыре цифры


### <a name="checksum"></a>Контрольная сумма

Да


### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_belgium_value_added_tax_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_belgium_value_added_tax_number.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_belgium_value_added_tax_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- n º тва
- номер НДС
- НДС No
- нумéро t. v. a
- умсатзстеуер — идентификатионснуммер
- умсатзстеуернуммер
- бтв
- бтв #
- процент #


## <a name="brazil-cpf-number"></a>Номер CPF для Бразилии

### <a name="format"></a>Format

11 цифр, которые включают проверочную цифру и могут быть форматированными или неформатированными.

### <a name="pattern"></a>Шаблон

Форматируемые
- три цифры
- точка
- три цифры
- точка
- три цифры
- дефис
- две цифры, которые проверяются

Неформатированные
- 11 цифр, где две последние цифры — проверочные.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_brazil_cpf;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Процедура
- Registration
- Реализации
- Cadastro de Pessoas Físicas 
- импосто 
- идентификаçãо 
- инскриçãо 
- рецеита 

   
## <a name="brazil-legal-entity-number-cnpj"></a>Номер юридического лица в Бразилии (CNPJ)

### <a name="format"></a>Format

14 цифр, которые включают регистрационный номер, номер филиала и проверочные цифры, а также разделители.

### <a name="pattern"></a>Шаблон

14 цифр, а также разделители:

- две цифры 
- точка 
- три цифры 
- точка 
- три цифры (эти первые восемь цифр — регистрационный номер). 
- косая черта 
- номер филиала из четырех цифр 
- дефис 
- две цифры, которые проверяются

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_brazil_cnpj;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ – MF 
- National Registry of Legal Entities 
- Taxpayers Registry 
- Legal entity 
- Legal entities 
- Registration Status 
- Для бизнеса 
- Company
- CNPJ 
- Cadastro Nacional da Pessoa Jurídica 
- Cadastro Geral de Contribuintes 
- кгк 
- Pessoa jurídica 
- Pessoas jurídicas 
- Situação cadastral 
- инскриçãо 
- емпреса 

   
## <a name="brazil-national-identification-card-rg"></a>Национальная идентификационная карточка Бразилии (RG)

### <a name="format"></a>Format

Registro Geral (старый формат): девять цифр

Registro de identidade (RIC) (новый формат): 11 цифр

### <a name="pattern"></a>Шаблон

Registro Geral (старый формат):
- две цифры 
- точка 
- три цифры 
- точка 
- три цифры 
- дефис 
- одна цифра, представляющая собой контрольная цифра

Registro de identidade (RIC) (новый формат):
- десять цифр 
- дефис 
- одна цифра, представляющая собой контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_brazil_rg находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_brazil_rg;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_brazil_rg находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- identity card
- national id 
- número de rregistro
- registro de Iidentidade 
- registro geral
- RG (ключевое слово с учетом регистра) 
- RIC (ключевое слово с учетом регистра) 


## <a name="bulgaria-drivers-license-number"></a>Номер водительского удостоверения для Болгария
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_bulgaria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_bulgaria_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver "s_license_number
- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- свидетелство за управление на МПС
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка


## <a name="bulgaria-uniform-civil-number"></a>Номер унифицированного гражданства Болгария

### <a name="format"></a>Format

десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

десять цифр без пробелов и разделителей
  
- шесть цифр, соответствующих дате рождения (ГГММДД) 
- две цифры, соответствующие порядку рождения
- одна цифра, соответствующая Пол: четное число для пола и нечетная цифра для розетки
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_bulgaria_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_bulgaria_eu_national_id_card` . 

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_bulgaria_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- бнн #
- бнн
- букн #
- букн
- единен граздански номер
- егн #
- егн
- identification number

- 
national id
- номер страны
- натионалнумбер #
- натионалнумбер
- личный идентификатор
- личный номер
- персональный номер
- персоналиднумбер #
- social security number

- SSN #
- SSN
- унифицированный гражданский идентификатор
- равномерный гражданский номер
- единое гражданское число
- униформЦивилно #
- униформЦивилно
- униформЦивилнумбер #
- униформЦивилнумбер
- уникальный номер гражданства
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- Идентификатор униформ
- униформ граждански ID
- униформ граждански не
- униформ граждански номер
- униформгражданскиид #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Номер паспорта для Болгария
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_bulgaria_eu_passport_number` . 

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- passport number
- номер паспорта для болгарского языка
- паспорт нет
- номер на паспорта


## <a name="canada-bank-account-number"></a>Номер банковского счета для Канады

### <a name="format"></a>Format

семь или двенадцать цифр

### <a name="pattern"></a>Шаблон

Номер банковского счета для Канады — семь или двенадцать цифр.

Транзитный номер банковского счета в Канаде имеет указанный ниже формат.
- пять цифр 
- дефис 
- три цифры или
- ноль "0" 
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_canada_bank_account_number.
- регулярное выражение Regex_canada_bank_account_transit_number находит содержимое, которое соответствует шаблону.

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_canada_bank_account_number.

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit

   
## <a name="canada-drivers-license-number"></a>Номер водительского удостоверения для Канады

### <a name="format"></a>Format

Зависит от провинции.

### <a name="pattern"></a>Шаблон

Различные шаблоны, соответствующие провинциям Альберта, Британская Колумбия, Манитоба, Нью-Брансуик, Ньюфаундленд и Лабрадор, Новая Шотландия, Онтарио, Остров Принца Эдуарда, Квебек и Саскачеван.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_[province_name]_drivers_license_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_[province_name]_drivers_license_name;
- находится ключевое слово из Keyword_canada_drivers_license.

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_ [province_name] _drivers_license_name

- Аббревиатура провинции, например AB.
- Название провинции, например Альберта.

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- БИБЛИОТЕК
- кдл
- кдлс
- дриверлик
- дриверликс
- дриверлиценсе
- дриверлиценсес
- дриверлиценце
- дриверлиценцес
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- дриверслик
- дриверсликс
- дриверслиценце
- дриверслиценцес
- дриверслиценсе
- дриверслиценсес
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver ' LIC
- Driver ' LICS
- Driver ' License
- Driver ' Licenses
- Driver ' Licence
- Driver ' Licences
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- дривер'слик
- дривер'сликс
- дривер'слиценсе
- дривер'слиценсес
- дривер'слиценце
- дривер'слиценцес
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- ids
- idcard number
- idcard numbers
- idcard#
- idcard #s
- idcard card
- idcard cards
- идкард
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- процедура 
- DL #
- БИБЛИОТЕК # 
- кдл # 
- кдлс # 
- дриверлик # 
- дриверликс # 
- дриверлиценсе # 
- дриверлиценсес # 
- дриверлиценце # 
- дриверлиценцес # 
- Driver Lic#
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- Driver License# 
- Driver Licences# 
- дриверслик # 
- дриверсликс # 
- дриверслиценсе # 
- дриверслиценсес # 
- дриверслиценце # 
- дриверслиценцес # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Drivers Licence# 
- Drivers Licences# 
- Driver ' LIC # 
- Driver ' LICS # 
- Driver ' License # 
- Driver ' Licenses # 
- Driver ' Licence # 
- Driver ' Licences # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver' Licence# 
- Driver' Licences# 
- дривер'слик # 
- дривер'сликс # 
- дривер'слиценсе # 
- дривер'слиценсес # 
- дривер'слиценце # 
- дривер'слиценцес # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- Driver's Licence# 
- Driver's Licences# 
- Permis de Conduire# 
- кодов # 
- идентификаторы # 
- idcard card# 
- idcard cards# 
- идкард # 
- identification card# 
- identification cards# 
- процедура # 

   
## <a name="canada-health-service-number"></a>Номер службы здравоохранения для Канады

### <a name="format"></a>Format

десять цифр

### <a name="pattern"></a>Шаблон

десять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_canada_health_service_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_canada_health_service_number.

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- псичиатрист
- workers compensation
- ограничен

      
## <a name="canada-passport-number"></a>Номер паспорта для Канады

### <a name="format"></a>Format

две прописные буквы, за которыми следуют шесть цифр.

### <a name="pattern"></a>Шаблон

две прописные буквы, за которыми следуют шесть цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_canada_passport_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keyword_canada_passport_number или Keyword_passport.

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- canadian citizenship
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Службу #
- пасспортид
- пасспортно
- пасспортнумбер
- パスポート
- パスポート番号
- パスポートのнум
- パスポート #
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- пассепорт #
- пассепортнон
- Passeportn °

   
## <a name="canada-personal-health-identification-number-phin"></a>Идентификационный номер персонального контроля работоспособности для Канады (PHIN)

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_canada_phin находит содержимое, которое соответствует шаблону;
- Найдены по крайней мере два ключевых слова от Keyword_canada_phin или Keyword_canada_provinces.

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- social insurance number
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- нунавут
- Квебека
- Northwest Territories
- Онтарио
- British Columbia
- Альберта
- Саскачеван
- Манитоба
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- Канада

   
## <a name="canada-social-insurance-number"></a>Номер социального страхования для Канады

### <a name="format"></a>Format

девять цифр с необязательными дефисами или пробелами

### <a name="pattern"></a>Шаблон

Форматируемые
- три цифры 
- дефис или пробел 
- три цифры 
- дефис или пробел 
- три цифры

Неформатированные: девять цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_canadian_sin находит содержимое, которое соответствует шаблону.
- Выполняются по меньшей мере два из таких условий:
    - найдено ключевое слово из Keyword_sin;
    - найдено ключевое слово из Keyword_sin_collaborative;
    - функция Func_eu_date находит дату в правильном формате.
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_unformatted_canadian_sin находит содержимое, которое соответствует шаблону;
- найдено ключевое слово из Keyword_sin;
- Контрольная сумма проходит проверку.

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_sin"></a>Keyword_sin

- sin 
- social insurance 
- numero d'assurance sociale 
- грехов 
- SSN 
- ssNS 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- Синус # 
- soc ins 
- social ins 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- доб 
- Birthdate 
- Birthday 
- Date of Birth 

   
## <a name="chile-identity-card-number"></a>Номер идентификационной карточки Чили

### <a name="format"></a>Format

семь и 8 цифр, а также разделители и контрольная цифра или буква

### <a name="pattern"></a>Шаблон

семь до восьми цифр, а также разделители:
- одна – две цифры 
- точка 
- три цифры 
- точка 
- три цифры 
- тире 
- одна цифра или буква (без учета регистра), которая является контрольной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_chile_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_chile_id_card;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_chile_id_card находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- National Identification Number 
- Identity card 
- ID 
- Процедура 
- Rol Único Nacional 
- ВЫПОЛНЯЕМ 
- Rol Único Tributario 
- СНИЖАТЬСЯ 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- идентификаЦиóн 

   
## <a name="china-resident-identity-card-prc-number"></a>Номер почтовых карточек для Китая (КНР)

### <a name="format"></a>Format

18 цифр.

### <a name="pattern"></a>Шаблон

18 цифр:
- шесть цифр, которые являются кодом адреса 
- восемь цифр в формате ГГГГММДД, представляющие собой дату рождения 
- три цифры, которые являются кодом заказа 
- одна цифра, представляющая собой контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_china_resident_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_china_resident_id;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_china_resident_id находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Resident Identity Card 
- NO7 
- National Identification Card 
- 身份证 
- 居民 身份证 
- 居民身份证 
- 鉴定 
- 身分證 
- 居民 身份證
- 鑑定 

   
## <a name="credit-card-number"></a>Номер кредитной карты

### <a name="format"></a>Format

14 – 16 цифр, которые можно форматировать или неформатированные (цццццццццццццццц) и которые должны пройти проверку Луна.

### <a name="pattern"></a>Шаблон

Очень сложный и надежный шаблон, который определяет карты всех основных мировых стандартов, включая Visa, MasterCard, Discover Card, JCB, American Express, подарочные карты и карты Diners Club.

### <a name="checksum"></a>Контрольная сумма

Да (рассчитывается по алгоритму Луна).

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_credit_card находит содержимое, которое соответствует шаблону;
- Верно одно из условий ниже:
    - найдено ключевое слово из Keyword_cc_verification;
    - найдено ключевое слово из Keyword_cc_name;
    - функция Func_expiration_date находит дату в правильном формате.
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- функция Func_credit_card находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- 
card verification

- card identification number
- квн
- cid
- cvc2
- cvv2
- 
pin block
- security code

- security number

- security no

- issue number

- issue no
- криптограмме
- 
numéro de sécurité
- numero de securite
- кредиткартенпрüфнуммер
- кредиткартенпруфнуммер
- прüфзиффер
- пруфзиффер
- sicherheits Kode
- сичерхеитскоде
- сичерхеитснуммер
- верфаллдатум
- codice di verifica
- наложен.сикурезза
- 
cod sicurezza
- n autorizzazione
- кóдиго
- кодиго
- наложен.сег
- 
cod seg
- código de segurança

- codigo de seguranca

- codigo de segurança

- código de seguranca
- кóд.сегуранçа
- наложен.сегуранка
- наложен.сегуранçа
- кóд.сегуранка
- кóд сегуранçа
- сегуранка наложенного платежа
- сегуранçа наложенного платежа
- кóд сегуранка
- número de verificação

- numero de verificacao
- аблауф
- gültig bis
- гüлтигкеитсдатум
- gultig bis
- гултигкеитсдатум
- скаденза
- 
data scad
- fecha de expiracion

- fecha de venc
- венЦимиенто
- 
válido hasta
- valido hasta
- вто
- 
data de expiração
- data de expiracao

- data em que expira
- валидаде
- валор
- венЦименто
- операций
- номер транзакции
- Справочный номер
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- амекс
- american express
- американекспресс
- americano espresso

- Visa
- MasterCard
- master card
- MC
- мастеркардс
- 
master cards
- Клуб Динер
- diners club
- динерсклуб
- Повтор
- discover card
- дисковеркард
- discover cards
- JCB
- брандсмарт
- japanese card bureau

- carte blanche
- картебланче
- credit card
- Центральной #
- CC #:
- Дата истечения срока действия
- exp date

- 
expiry date
- 
date d’expiration
- 
date d'exp
- 
date expiration
- bank card
- банккард
- 
card number
- card num
- карднумбер
- карднумберс
- card numbers
- кредиткард
- credit cards
- кредиткардс
- CCN
- card holder
- банков
- card holders
- карты
- check card
- чекккард
- check cards
- чекккардс
- debit card
- дебиткард
- debit cards
- дебиткардс
- atm card
- атмкард
- atm cards
- атмкардс
- енрауте
- 
en route
- card type

- Acct кардмембер
- Учетная запись кардмембер
- кардно
- Корпоративная карта
- Корпоративные карты
- Тип карточки
- номер счета карточки
- Учетная запись члена карточки
- Кардмембер acct.
- card no.

- карточка нет
- card number

- carte bancaire

- carte de crédit

- carte de credit

- numéro de carte

- numero de carte

- nº de la carte

- nº de carte
- кредиткарте
- карте
- картенинхабер
- картенинхаберс
- кредиткартенинхабер
- кредиткартенинститут
- кредиткартентип
- еижентüмернаме
- картеннр
- картеннуммер
- кредиткартеннуммер
- кредиткартен — нуммер
- 
carta di credito
- carta credito
- .\n\n\-.Корзина "
- n carta
- НР.Корзина "
- 
nr carta
- numero carta

- numero della carta

- numero di carta

- tarjeta credito

- tarjeta de credito

- 
tarjeta crédito
- 
tarjeta de crédito
- tarjeta de atm

- tarjeta atm

- tarjeta debito

- tarjeta de debito

- 
tarjeta débito
- 
tarjeta de débito
- nº de tarjeta
- Нет.de tarjeta
- нет де таржета
- numero de tarjeta

- número de tarjeta

- tarjeta no
- таржетахабиенте
- 
cartão de crédito
- cartão de credito

- cartao de crédito

- cartao de credito

- cartão de débito

- cartao de débito

- cartão de debito

- cartao de debito

- débito automático
- debito automatico

- 
número do cartão
- numero do cartão

- número do cartao

- numero do cartao

- número de cartão

- numero de cartão

- número de cartao

- numero de cartao

- n º Do картãо
- nº do cartao
- n º.do cartão
- не выполнять картãо
- не выполнять картао
- Нет.do cartão
- Нет.do cartao
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード #
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード #
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- висаカード
- カード Visa
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>Номер водительского удостоверения для драйвера Хорватия
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

восемь цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение  `Regex_croatia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_croatia_eu_driver's_license_number` . 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- возаčка дозвола


## <a name="croatia-identity-card-number"></a>Номер идентификационной карточки (Хорватия)
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации страны ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_croatia_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_croatia_id_card.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- мажсторски Брож граđана
- основной номер в соотношении
- наЦионални идентификаЦижски Брож
- Национальный идентификационный номер
- OIB #
- OIB
- особна исказника
- Идентификатор особни
- особни идентификаЦижски Брож
- персональный идентификационный номер
- порезни Брож
- порезни идентификаЦижски Брож
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="croatia-passport-number"></a>Номер паспорта для выхорватия
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_croatia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- passport number
- номер паспорта для хорватского языка
- паспорт нет
- Брож путовнице

   
## <a name="croatia-personal-identification-oib-number"></a>Номер личного кода (OIB), Хорватия

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр:
- десять цифр 
- Последняя цифра — контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_croatia_eu_tax_file_number.
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- мажсторски Брож граđана
- основной номер в соотношении
- наЦионални идентификаЦижски Брож
- Национальный идентификационный номер
- OIB #
- OIB
- особна исказника
- Идентификатор особни
- особни идентификаЦижски Брож
- персональный идентификационный номер
- порезни Брож
- порезни идентификаЦижски Брож
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #

## <a name="croatia-social-security-number-or-equivalent-identification"></a>Хорватия номер социального страхования или эквивалентная идентификация
Этот объект типа конфиденциальной информации доступен только в номере социального страхования ЕС или эквивалентного идентификатора.

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
- десять цифр
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция  `Func_croatia_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_croatia_eu_ssn_or_equivalent` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция  `Func_croatia_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

- персональный идентификационный номер
- основной номер в соотношении
- national identification number
- social security number
- натионалнумбер #
- SSN #
- SSN
- натионалнумбер
- бнн #
- бнн
- личный идентификационный номер
- персоналиднумбер #
- OIB
- особни идентификаЦижски Брож

   
## <a name="cyprus-drivers-license-number"></a>Номер лицензии на драйверы Кипр
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

12 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

12 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_cyprus_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_cyprus_eu_driver's_license_number` .

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- άδεια οδήγησης


## <a name="cyprus-identity-card"></a>Идентификационная карточка Кипр

### <a name="format"></a>Format

десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

десять цифр 
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_cyprus_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_cyprus_eu_national_id_card` . 
    
```xml 
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- идентификационный номер карточки
- Номер идентификационной карточки
- кимлик Карти
- Национальный идентификационный номер
- личный идентификационный номер
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Номер паспорта для Кипр
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

одна буква, за которой следуют 6-8 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

одна буква, за которой следуют шесть и восемь цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Найдено ключевое слово FROM  `Keywords_cyprus_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- passport number
- номер паспорта для Кипр
- паспорт нет
- αριθμό διαβατηρίου


## <a name="cyprus-tax-identification-number"></a>Идентификационный номер налогоплательщика (Кипр)

### <a name="format"></a>Format

восемь цифр и одна буква в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

восемь цифр и одна буква:
  
- "0" или "9"
- семь цифр
- одна буква (без учета регистра)
    
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_cyprus_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id

- Налоговый код идентификации
- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- тик #
- тик
- Идентификатор Tin
- номер Tin
- ИНН #
- Верги кимлик коду
- Верги кимлик нумарасı
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Номер водительского удостоверения для чешского языка
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

две буквы, за которыми следуют шесть цифр.
  
### <a name="pattern"></a>Шаблон

восемь букв и цифр:
  
- две буквы (без учета регистра)
- пробел (необязательно)
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_czech_republic_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_czech_republic_eu_driver's_license_number` . 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Keywords

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- řидиčскý прúказ


## <a name="czech-passport-number"></a>Номер паспорта для чешского языка
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

восемь цифр без пробелов и разделителей
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_czech_republic_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- passport number
- номер паспорта для чешского языка
- паспорт нет
- цестовнí PAS
- соответствующий


## <a name="czech-personal-identity-number"></a>Номер личного удостоверения для чешского языка

### <a name="format"></a>Format

девять цифр с необязательной косой чертой (старый формат), десять цифрами с необязательной косой чертой (новый формат)

### <a name="pattern"></a>Шаблон

девять цифр (старый формат):
- шесть цифр, представляющих дату рождения
- косая черта
- три цифры

десять цифр (новый формат):
- шесть цифр, представляющих дату рождения
- косая черта 
- четыре цифры, где последняя цифра является контрольной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:

- функция Func_czech_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_czech_id_card;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:

- Функция Func_czech_id_card_new_format находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- номер рождения
- идентификационный номер Чешской Республики
- кзечидно #
- даňовé číсло
- идентификаčнí číсло
- Идентификатор
- идентификационный номер
- идентитино #
- идентитино
- страховой номер
- Национальный идентификационный номер
- натионалнумбер #
- номер страны
- особнí číсло
- персоналиднумбер #
- личный идентификационный номер
- персональный идентификационный номер
- персональный номер
- вязки #
- pid
- пожиšтěнí číсло
- рč
- родне Цисло
- роднé číсло
- SSN
- SSN #
- social security number

- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- уникальный идентификационный номер


## <a name="czech-social-security-number-or-equivalent-identification"></a>Номер социального страхования для чешского или эквивалентного кода

Этот объект типа конфиденциальной информации доступен только в номере социального страхования ЕС или эквивалентного идентификатора.

### <a name="format"></a>Format

десять цифр и обратная косая черта в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

десять цифр и обратная косая черта:
  
- шесть цифр, соответствующих дате рождения (ГГММДД): 
- Обратная косая черта
- три цифры, которые соответствуют серийному номеру, которые отделяют пользователей на одну и ту же дату.
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_czech_republic_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_czech_republic_eu_ssn_or_equivalent` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_czech_republic_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 

```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

- номер рождения
- national identification number
- персональный идентификационный номер
- social security number
- натионалнумбер #
- SSN #
- SSN
- номер страны
- личный идентификационный номер
- персоналиднумбер #
- рč
- роднé číсло
- родне Цисло


## <a name="denmark-drivers-license-number"></a>Номер водительского удостоверения для Дании
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

восемь цифр
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_denmark_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_denmark_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver "s_license_number

- | DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- кøрекорт
- кøрекортнуммер


## <a name="denmark-passport-number"></a>Номер паспорта для Дании
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_denmark_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- passport number
- номер паспорта для датского языка
- паспорт нет
- соответствующий
- паснуммер


## <a name="denmark-personal-identification-number"></a>Личный идентификационный номер для Дании
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации страны ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

десять цифр, содержащие дефис

### <a name="pattern"></a>Шаблон

десять цифр:
- шесть цифр в формате ддммгг — Дата рождения; 
- дефис 
- четыре цифры, где последняя цифра является контрольной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение Func_denmark_eu_tax_file_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_denmark_id;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Регулярное выражение Func_denmark_eu_tax_file_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Denmark Personal Identification Number -->
      <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- централе персонрегистер
- Гражданский регистрерингссистем
- CPR
- CPR #
- жесундхеитскарте нуммер
- жесундхеитсверсичерунгкарте нуммер
- карточка работоспособности
- номер карточки страхования здоровья
- номер страховки здоровья
- identification number

- идентификатионснуммер
- идентификатионснуммер #
- идентификационный номер
- кранкенкассеннуммер
- натионалид #
- натионалнумбер #
- номер страны
- персоналиднумбер #
- персоналидентитино #
- личный идентификационный номер
- персоннуммер
- персоннуммер #
- реисекранкенверсичерунгскартенуммер
- режсесижесикрингскорт
- SSN
- SSN #
- Идентификатор Скат
- Скат коде
- Скат нуммер
- скаттенуммер
- social security number

- сундхедсфорсикрингскорт
- сундхедсфорсикрингснуммер
- сундхедскорт
- сундхедскортнуммер
- сижесикринг
- сижесикрингкортнуммер
- Налоговый код
- Карточка страхования здравоохранения
- уникуеидентитино #
- Налоговый номер
- Регистрационный номер налогоплательщика
- tax id

- идентификационный номер налога
- такси #
- такснумбер #
- налог без
- таксно #
- такснумбер
- Налоговый идентификатор
- ИНН #
- таксидно #
- таксиднумбер #
- налог без #
- Идентификатор Tin
- номер Tin
- cpr.nr
- кпрнр
- кпрнуммер
- персоннр
- персонрегистер
- сижесикрингсбевис
- сижесикрингсбевиснр
- сижесикрингсбевиснуммер
- сижесикрингскорт
- сижесикрингскортнр
- сижесикрингскортнуммер
- сижесикрингснр
- сижесикрингснуммер


## <a name="denmark-social-security-number-or-equivalent-identification"></a>Номер социального страхования для Дании или эквивалентная идентификация
Этот объект типа конфиденциальной информации доступен только для номера социального страхования ЕС или эквивалентного типа конфиденциальной информации.

### <a name="format"></a>Format

десять цифр и дефис в заданном шаблоне
  
### <a name="pattern"></a>Шаблон

десять цифр и дефис:
  
- шесть цифр, соответствующих дате рождения (ДДММГГ —) 
- дефис
- четыре цифры, которые соответствуют порядковому номеру

### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_denmark_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_denmark_eu_ssn_or_equivalent` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_denmark_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

- персональный идентификационный номер
- national identification number
- social security number
- натионалнумбер #
- SSN #
- SSN
- номер страны
- личный идентификационный номер
- персоналиднумбер #
- CPR — нуммер
- персоннуммер


## <a name="drug-enforcement-agency-dea-number"></a>Номер агентства для применения наркотиков (DEA)

### <a name="format"></a>Format

две буквы, за которыми следуют семь цифр.

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.
- одна буква (без учета регистра) из этого набора возможных букв: abcdefghjklmnprstux, который является кодом Регистрант 
- одна буква (без учета регистра), представляющая собой первую букву фамилии Регистрант 
- семь цифр, последняя из которых — контрольная цифра.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_dea_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

Нет


## <a name="estonia-drivers-license-number"></a>Номер водительского удостоверения для драйвера Эстонии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

две буквы, за которыми следуют шесть цифр.
  
### <a name="pattern"></a>Шаблон

две буквы и шесть цифр:
  
- буквы "ET" (без учета регистра); 
- шесть цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_estonia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_estonia_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер водительского удостоверения
- длно #
- permis de conduire


## <a name="estonia-personal-identification-code"></a>Эстонии персональный идентификационный код

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
- одна цифра, соответствующая упоминанию секса и столетию рождения (нечетный номер, четная розетка), 1-2:19 века; 3-4:20 века; 5-6:21 столетие)
- шесть цифр, соответствующих дате рождения (ГГММДД)
- три цифры, которые соответствуют порядковому номеру, разделенному на одну и ту же дату.
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_estonia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_estonia_eu_national_id_card` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_estonia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- ID — каарт
- фигуры
- исикукуд #
- исикукуд
- Идентификатор Максу
- максукохустусласе идентифитсиримиснумбер
- максунумбер
- Национальный идентификационный номер
- номер страны
- персональный код
- личный идентификационный номер
- персональный идентификационный код
- персональный идентификационный номер
- персоналиднумбер #
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="estonia-passport-number"></a>Номер паспорта для Эстонии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

одна буква, за которой следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

одна буква, за которой следуют семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_estonia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

- passport number
- номер паспорта для Эстонии
- паспорт нет
- Исти коданику Pass

## <a name="eu-debit-card-number"></a>Номер дебетовой карты ЕС

### <a name="format"></a>Format

16 цифр.

### <a name="pattern"></a>Шаблон

Очень сложный и надежный шаблон.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_eu_debit_card находит содержимое, которое соответствует шаблону.
- Верно по меньшей мере одно из условий ниже:
    - найдено ключевое слово из Keyword_eu_debit_card;
    - найдено ключевое слово из Keyword_card_terms_dict;
    - найдено ключевое слово из Keyword_card_security_terms_dict;
    - найдено ключевое слово из Keyword_card_expiration_terms_dict;
    - функция Func_expiration_date находит дату в правильном формате.
- Контрольная сумма проходит проверку.

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number 
- card number 
- card no. 
- security number 
- Центральной # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- американекспресс 
- americano espresso 
- амекс 
- atm card 
- atm cards 
- atm kaart 
- атмкард 
- атмкардс 
- атмкаарт 
- атмкаартен 
- банконтакт 
- bank card 
- банккаарт 
- card holder 
- card holders 
- card num 
- card number 
- card numbers 
- card type 
- cardano numerico 
- банков 
- карты 
- карднумбер 
- карднумберс 
- carta bianca 
- carta credito 
- carta di credito 
- cartao de credito 
- cartao de crédito 
- cartao de debito 
- cartao de débito 
- carte bancaire 
- carte blanche 
- carte bleue 
- carte de credit 
- carte de crédit 
- carte di credito 
- картебланче 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- CCN 
- check card 
- check cards 
- чекккард
- чекккардс 
- чекуекаарт 
- Logic 
- Cirrus центр EDC — Маестро 
- контролекаарт 
- контролекаартен 
- credit card 
- credit cards 
- кредиткард 
- кредиткардс 
- дебеткаарт 
- дебеткаартен 
- debit card 
- debit cards 
- дебиткард 
- дебиткардс 
- debito automatico 
- diners club 
- динерсклуб 
- Повтор 
- discover card 
- discover cards 
- дисковеркард 
- дисковеркардс 
- débito automático
- центр EDC 
- еижентüмернаме 
- european debit card 
- хуфдкаарт 
- хуфдкаартен 
- in viaggio 
- japanese card bureau 
- japanse kaartdienst 
- JCB 
- каарт 
- kaart num 
- каартаантал 
- каартаанталлен 
- каарсаудер 
- каарсаудерс 
- карте  
- картенинхабер 
- картенинхаберс
- картеннр 
- картеннуммер 
- кредиткарте 
- кредиткартен — нуммер 
- кредиткартенинхабер 
- кредиткартенинститут 
- кредиткартеннуммер 
- кредиткартентип 
- маестро 
- master card 
- master cards 
- MasterCard 
- мастеркардс 
- MC 
- mister cash 
- n carta 
- Корзина " 
- no de tarjeta 
- no do cartao 
- no do cartão 
- Нет. de tarjeta 
- Нет. do cartao 
- Нет. do cartão 
- nr carta 
- НР. Корзина " 
- numeri di scheda 
- numero carta 
- numero de cartao 
- numero de carte 
- numero de cartão 
- numero de tarjeta
- numero della carta 
- numero di carta 
- numero di scheda 
- numero do cartao 
- numero do cartão 
- numéro de carte 
- nº carta 
- nº de carte 
- nº de la carte 
- nº de tarjeta 
- nº do cartao 
- nº do cartão 
- n º. do cartão 
- número de cartao 
- número de cartão 
- número de tarjeta 
- número do cartao 
- scheda dell'assegno 
- scheda dell'atmosfera 
- scheda dell'atmosfera 
- scheda della banca 
- scheda di controllo 
- scheda di debito 
- scheda matrice 
- schede dell'atmosfera 
- schede di controllo 
- schede di debito 
- schede matrici 
- scoprono la scheda 
- scoprono le schede 
- ОС 
- supporti di scheda 
- supporto di scheda 
- отключен 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta no
- таржетахабиенте 
- tipo della scheda 
- ufficio giapponese della 
- счеда 
- v pay 
- v — оплата 
- Visa 
- visa plus 
- visa electron 
- висто 
- висум 
- впай   

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica 
- cid 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- наложен. сег 
- наложен. сегуранка 
- наложен. сегуранçа 
- наложен. сикурезза 
- codice di sicurezza 
- codice di verifica 
- кодиго 
- codigo de seguranca 
- codigo de segurança 
- криттограмма 
- криптограм 
- криптограмме 
- cv2 
- квк 
- cvc2 
- квн 
- квв 
- cvv2 
- cód seguranca 
- cód segurança 
- кóд. сегуранка 
- кóд. сегуранçа 
- кóдиго 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft nr uit 
- issue no 
- issue number 
- каартидентификатиенуммер 
- кредиткартенпруфнуммер 
- кредиткартенпрüфнуммер 
- квестиеаантал 
- Нет. делл'едизионе 
- Нет. di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- счеда 
- numero di sicurezza 
- numero van veiligheid 
- numéro de sécurité 
- nº autorizzazione 
- número de verificação 
- perno il blocco 
- pin block 
- пруфзиффер 
- прüфзиффер 
- security code 
- security no 
- security number 
- sicherheits kode 
- сичерхеитскоде 
- сичерхеитснуммер 
- спелдблок 
- veiligheid nr 
- веилигхеидсаантал 
- веилигхеидскоде 
- веилигхеидснуммер 
- верфаллдатум 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- аблауф 
- data de expiracao 
- data de expiração 
- data del exp 
- data di exp 
- data di scadenza 
- data em que expira 
- data scad 
- data scadenza 
- date de validité 
- datum afloop 
- datum van exp 
- de afloop 
- еспира 
- еспира 
- exp date 
- exp datum 
- срока действия 
- истекает 
- истекает 
- окончания срока действия 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- гултигкеитсдатум 
- gültig bis 
- гüлтигкеитсдатум 
- la scadenza 
- скаденза 
- валабле 
- валидаде 
- valido hasta 
- валор 
- венк 
- венЦименто 
- венЦимиенто 
- верлупт 
- вервалдаг 
- вервалдатум 
- вто 
- válido hasta 


## <a name="eu-drivers-license-number"></a>Номер водительского удостоверения для драйвера ЕС

Это сущности в типе конфиденциальной информации номера водительского удостоверения.

- [Австрия](#austria-drivers-license-number) 
- [Бельгия](#belgium-drivers-license-number)
- [Болгария](#bulgaria-drivers-license-number)
- [Хорватия](#croatia-drivers-license-number)
- [Кипр](#cyprus-drivers-license-number)
- [Чешский](#czech-drivers-license-number)
- [Дания](#denmark-drivers-license-number)
- [Эстония](#estonia-drivers-license-number)
- [Финляндия](#finland-drivers-license-number)
- [Франция](#france-drivers-license-number) 
- [Германия](#germany-drivers-license-number)
- [Греция](#greece-drivers-license-number)
- [Венгрия](#hungary-drivers-license-number)
- [Ирландия](#ireland-drivers-license-number)
- [Италия](#italy-drivers-license-number)
- [Латвия](#latvia-drivers-license-number)
- [Литва](#lithuania-drivers-license-number)
- [луксембург](#luxemburg-drivers-license-number)
- [Мальта](#malta-drivers-license-number)
- [Нидерланды](#netherlands-drivers-license-number)
- [Польша](#poland-drivers-license-number) 
- [Португалия](#portugal-drivers-license-number)
- [Румыния](#romania-drivers-license-number)
- [Словакия](#slovakia-drivers-license-number)
- [Словения](#slovenia-drivers-license-number)
- [Испания](#spain-drivers-license-number)
- [Швеция](#sweden-drivers-license-number)
- [Королевств](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Национальный идентификационный номер ЕС

Это сущности в типе конфиденциальной информации национальной идентификационной информации ЕС.

- [Австрия](#austria-identity-card)
- [Бельгия](#belgium-national-number)
- [Болгария](#bulgaria-uniform-civil-number)
- [Хорватия](#croatia-identity-card-number)
- [Кипр](#cyprus-identity-card)
- [Чешский](#czech-personal-identity-number)
- [Дания](#denmark-personal-identification-number)
- [Эстония](#estonia-personal-identification-code)
- [Финляндия](#finland-national-identification-number)
- [Франция](#france-national-identification-card-cni)
- [Германия](#germany-identity-card-number)
- [Греция](#greece-national-id-card)
- [Венгрия](#hungary-national-identification-number)
- [Ирландия](#ireland-national-identification-number)
- [Италия](#italy-national-identification-number)
- [Латвия](#latvia-national-identification-number)
- [Литва](#lithuania-national-identification-number)
- [луксембург](#luxemburg-national-identification-number)
- [Мальта](#malta-national-identification-number)
- [Нидерланды](#netherlands-national-identification-number)
- [Польша](#poland-national-id-pesel)
- [Португалия](#portugal-citizen-card-number)
- [Румыния](#romania-national-identification-number)
- [Словакия](#slovakia-national-identification-number)
- [Словения](#slovenia-national-identification-number)
- [Испания](#spain-national-identification-number)
- [Королевств](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>Номер паспорта ЕС 

Это сущности в номере паспорта ЕС конфиденциальной информации Типесесе являются сущностями в пакете номеров паспорта ЕС.

- [Австрия](#austria-passport-number)
- [Бельгия](#belgium-passport-number)
- [Болгария](#bulgaria-passport-number)
- [Хорватия](#croatia-passport-number)
- [Кипр](#cyprus-passport-number)
- [Чешский](#czech-passport-number)
- [Дания](#denmark-passport-number)
- [Эстония](#estonia-passport-number)
- [Финляндия](#finland-passport-number)
- [Франция](#france-passport-number)
- [Германия](#germany-passport-number)
- [Греция](#greece-passport-number)
- [Венгрия](#hungary-passport-number)
- [Ирландия](#ireland-passport-number)
- [Италия](#italy-passport-number)
- [Латвия](#latvia-passport-number)
- [Литва](#lithuania-passport-number)
- [луксембург](#luxemburg-passport-number)
- [Мальта](#malta-passport-number)
- [Нидерланды](#netherlands-passport-number)
- [Польша](#poland-passport-number)
- [Португалия](#portugal-passport-number)
- [Румыния](#romania-passport-number)
- [Словакия](#slovakia-passport-number)
- [Словения](#slovenia-passport-number)
- [Испания](#spain-passport-number)
- [Швеция](#sweden-passport-number)
- [Королевств](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Номер социального страхования ЕС или эквивалентная идентификация

Это сущности, которые входят в номер социального страхования ЕС или эквивалентный тип конфиденциальной информации.

- [Австрия](#austria-social-security-number-or-equivalent-identification)
- [Бельгия](#belgium-social-security-number-or-equivalent-identification)
- [Хорватия](#croatia-social-security-number-or-equivalent-identification)
- [Чешский](#czech-social-security-number-or-equivalent-identification)
- [Дания](#denmark-social-security-number-or-equivalent-identification)
- [Финляндия](#finland-social-security-number-or-equivalent-identification)
- [Франция](#france-social-security-number-insee-or-equivalent-identification)
- [Германия](#germany-identity-card-number)
- [Греция](#greece-national-id-card)
- [Венгрия](#hungary-social-security-number-or-equivalent-identification)
- [Португалия](#portugal-citizen-card-number)
- [Испания](#spain-social-security-number-ssn)
- [Швеция](#sweden-social-security-number-or-equivalent-identification)


## <a name="eu-tax-identification-number"></a>Идентификационный номер налогоплательщика ЕС

Эти сущности находятся в типе конфиденциальной информации по идентификационному номеру ЕС.

- [Австрия](#austria-tax-identification-number)
- [Кипр](#cyprus-tax-identification-number)
- [Франция](#france-tax-identification-number)
- [Германия](#germany-tax-identification-number)
- [Греция](#greece-tax-identification-number)
- [Венгрия](#hungary-tax-identification-number)
- [Ирландия](#ireland-tax-identification-number)
- [Италия](#italy-tax-identification-number)
- [Латвия](#latvia-tax-identification-number)
- [Литва](#lithuania-tax-identification-number)
- [луксембург](#luxemburg-tax-identification-number)
- [Мальта](#malta-tax-identification-number)
- [Нидерланды](#netherlands-tax-identification-number)
- [Польша](#poland-tax-identification-number)
- [Португалия](#portugal-tax-identification-number)
- [Румыния](#romania-tax-identification-number)
- [Словакия](#slovakia-tax-identification-number)
- [Словения](#slovenia-tax-identification-number)
- [Испания](#spain-tax-identification-number)
- [Швеция](#sweden-tax-identification-number)
- [Королевств](#uk-tax-identification-number)


## <a name="finland-drivers-license-number"></a>Номер водительского удостоверения для Финляндии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

десять цифр, содержащие дефис
  
### <a name="pattern"></a>Шаблон

десять цифр, содержащих дефис:
  
- шесть цифр 
- дефис
- четыре цифры 
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_finland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_finland_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- ажокортти


## <a name="finland-european-health-insurance-number"></a>Номер страховки для Финляндии (Европейский)

### <a name="format"></a>Format

20 цифр номер

### <a name="pattern"></a>Шаблон

20 – значный номер:

- десять цифр — 8024680246
- необязательный пробел или дефис
- десять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение Regex_Finland_European_Health_Insurance_Number находит содержимое, которое соответствует шаблону.
- Найдено ключевое слово из Keyword_Finland_European_Health_Insurance_Number.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ехик #
- ехик
- финландехикнумбер #
- финска сжукфöрсäкрингскорт
- карточка работоспособности
- Карточка страхования здоровья
- номер страховки здоровья
- хäлсокорт
- саираанхоитокортин
- саираусвакуутускортти
- саираусвакуутуснумеро
- сжукфöрсäкринг нуммер
- сжукфöрсäкрингскорт
- Суомен саираусвакуутускортти
- тервэйскортти


## <a name="finland-national-identification-number"></a>Национальный идентификационный номер Финляндии

### <a name="format"></a>Format

шесть цифр плюс символ, указывающий на столетие плюс три цифры плюс контрольная цифра

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.
- шесть цифр в формате формата ддммгг —, представляющие собой дату рождения 
- маркер века ("-", "+" или "a") 
- трехзначный идентификационный номер, соличный с тремя цифрами 
- цифра или буква (без учета регистра), которая является контрольной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_finnish_national_id находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keyword_finnish_national_id
- Контрольная сумма проходит

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_finnish_national_id находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

- аинутлаатуинен хенкилöкохтаинен туннус
- хенкилöкохтаинен туннус
- хенкилöтуннус
- хенкилöтуннуснумеро #
- хенкилöтуннуснумеро
- хету
- ID No
- идентификационный номер
- identification number

- идентититти нумеро
- идентификационный номер
- иднумбер
- кансаллинен хенкилöтуннус
- кансаллисен хенкилöкортин
- номер национальной идентификационной карточки
- код страны
- личный идентификатор
- код персонального удостоверения
- персоналиднумбер #
- персонбетеккнинг
- персоннуммер
- social security number

- сосиаалитурватуннус
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- туннистенумеро
- туннус нумеро
- туннуслуку
- туннуснумеро
- верокортти
- веронумеро
- веротуннисте
- веротуннус


## <a name="finland-passport-number"></a>Номер паспорта для Финляндии
Этот объект типа конфиденциальной информации доступен в типе конфиденциальной информации номера паспорта ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format
сочетание девяти букв и цифр

### <a name="pattern"></a>Шаблон
сочетание девяти букв и цифр:
- две буквы (без учета регистра) 
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_finland_passport_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_finland_passport_number.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords

- Keyword_finland_passport_number
- Службу
- пасси


## <a name="finland-social-security-number-or-equivalent-identification"></a>Номер социального страхования для Финляндии или эквивалентная идентификация
Этот объект типа конфиденциальной информации доступен только в номере социального страхования ЕС или эквивалентного идентификатора.

### <a name="format"></a>Format

11 символов в указанном формате.
  
### <a name="pattern"></a>Шаблон

сочетание из 11 символов в указанном формате:
  
- шесть цифр 
- один из следующих экземпляров:
  - символ "плюс"
  - символ "минус"
  - буква "A" (без учета регистра)
- три цифры
- одна буква или одна цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_finland_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_finland_eu_ssn_or_equivalent` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_finland_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a>Keywords_finland_eu_ssn_or_equivalent

- identification number
- личный идентификатор
- идентификационный номер
- Финский национальный идентификационный номер
- персоналиднумбер #
- national identification number
- идентификационный номер
- код страны
- Национальный идентификационный номер
- ID No
- туннистенумеро
- хенкилöтуннус
- иксилöллинен хенкилöкохтаинен туннистенумеро
- аинутлаатуинен хенкилöкохтаинен туннус
- идентититти нумеро
- Суомен кансаллинен хенкилöтуннус
- хенкилöтуннуснумеро #
- кансаллисен туннистенумеро
- туннуснумеро
- кансаллинен туннус нумеро
- хету


## <a name="france-drivers-license-number"></a>Номер водительского удостоверения для Франции
Этот объект типа конфиденциальной информации доступен в типе конфиденциальной информации номера водительского удостоверения для ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

12 цифр.

### <a name="pattern"></a>Шаблон

12 цифр с проверкой подлинности, чтобы избежать путаницы с похожими шаблонами, например французскими номерами телефонов.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_french_drivers_license находит содержимое, которое соответствует шаблону;
- выполняется по крайней мере одно из следующих условий:
- Найдено ключевое слово из Keyword_french_drivers_license.
- Функция Func_eu_date обнаружила дату в правильном формате даты.

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- drivers licence
- drivers license
- driving licence
- driving license
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers


## <a name="france-health-insurance-number"></a>Номер страховки для Франции

### <a name="format"></a>Format

21 цифра цифра

### <a name="pattern"></a>Шаблон

21 цифра:

- десять цифр
- необязательный пробел
- десять цифр
- необязательный пробел
- цифра


### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_France_Health_Insurance_Number находит содержимое, которое соответствует шаблону.
- Найдено ключевое слово из Keyword_France_Health_Insurance_Number.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- Карточка страхования
- Витале корзины
- Корзина д'ассурé социальных сетей


## <a name="france-national-identification-card-cni"></a>Национальный идентификационный номер страны Франции (CNI)

### <a name="format"></a>Format

12 цифр.

### <a name="pattern"></a>Шаблон

12 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- регулярное выражение Regex_france_cni находит содержимое, которое соответствует шаблону.
- Найдено ключевое слово из Keywords_france_eu_national_id_card.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number

- Национальный д'идентитé для корзины
- Национальный д'идените для корзины
- CNI #
- CNI
- Компте банкаире
- Национальный идентификационный номер
- Национальная идентификация
- натионалидно #
- нумéро д'ассуранце маладие
- нумéро де корзина Витале

   
## <a name="france-passport-number"></a>Номер паспорта для Франции
Этот объект типа конфиденциальной информации доступен в типе конфиденциальной информации номера паспорта ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

девять цифр и букв

### <a name="pattern"></a>Шаблон

девять цифр и букв:
- две цифры 
- две буквы (без учета регистра) 
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_fr_passport находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_passport.

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Службу #
- пасспортид
- пасспортно
- пасспортнумбер
- パスポート
- パスポート番号
- パスポートのнум
- パスポート＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- пассепорт #
- пассепортнон
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>Номер социального страхования для Франции (INSEE) или эквивалентная идентификация
Этот объект типа конфиденциальной информации включен в номер социального страхования ЕС и эквивалентный тип конфиденциальной информации и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

15 цифр.

### <a name="pattern"></a>Шаблон

Должен соответствовать одному из двух шаблонов:
- 13 цифр, за которыми следует пробел, за которым следуют две цифры.<br/>
или
- 15 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_fr_insee;
- контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.
- ни одно ключевое слово из Keyword_fr_insee не находится;
- Контрольная сумма проходит проверку.

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- INSEE
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- Нет. д'идентитé
- numero d'identite
- no d'identite
- Нет. д'идентите
- social security number
- social security code
- social insurance number
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- code sécu 

## <a name="france-tax-identification-number"></a>Налоговый идентификационный номер для Франции

### <a name="format"></a>Format

13 цифр.
  
### <a name="pattern"></a>Шаблон

13 цифр.
  
- Одна цифра, которая должна быть равна 0, 1, 2 или 3
- 1 цифра
- пробел (необязательно); 
- 2 цифры 
- пробел (необязательно); 
- 3 цифры 
- пробел (необязательно); 
- 3 цифры 
- пробел (необязательно); 
- 3 контрольные цифры 

  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_france_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Keywords

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- нумéро д'идентификатион Фин.
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="france-value-added-tax-number"></a>Значение налогового номера, добавленного в Франции

### <a name="format"></a>Format

13-буквенно-буквенно-цифровой шаблон

### <a name="pattern"></a>Шаблон

13 символов буквенно-цифрового шаблона:

- две буквы — FR (без учета регистра)
- необязательный пробел или дефис
- две буквы или цифры
- необязательный пробел, точка, дефис или запятая
- три цифры
- необязательный пробел, точка, дефис или запятая
- три цифры
- необязательный пробел, точка, дефис или запятая
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_france_value_added_tax_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_france_value_added_tax_number.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_france_value_added_tax_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- номер НДС
- НДС No
- процент #
- налог на добавленную стоимость
- Siren идентификация No нумéро д'идентификатион таксе Сур валеур ажаутéе
- таксе валеур ажаутéе
- таксе Сур Ла валеур ажаутéе
- n ° тва
- нумéро de тва
- нумéро д'идентификатион Siren


## <a name="germany-drivers-license-number"></a>Номер водительского удостоверения для Германии
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации номера лицензии для драйвера ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

сочетание 11 цифр и букв

### <a name="pattern"></a>Шаблон

11 цифр и букв (без учета регистра)
- цифра или буква; 
- две цифры 
- шесть цифр или букв 
- цифра 
- цифра или буква;

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_german_drivers_license находит содержимое, которое соответствует шаблону;
- Верно по меньшей мере одно из условий ниже:
    - найдено ключевое слово из Keyword_german_drivers_license_number;
    - найдено ключевое слово из Keyword_german_drivers_license_collaborative;
    - найдено ключевое слово из Keyword_german_drivers_license.
- Контрольная сумма проходит проверку.

```xml
<!-- Germany Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- фüхрерсчеин
- фухрерсчеин
- фуехрерсчеин
- фüхрерсчеиннуммер
- фухрерсчеиннуммер
- фуехрерсчеиннуммер
- Фüхрерсчеин — 
- Фухрерсчеин — 
- Фуехрерсчеин — 
- фüхрерсчеиннуммернр
- фухрерсчеиннуммернр
- фуехрерсчеиннуммернр
- фüхрерсчеиннуммерклассе
- фухрерсчеиннуммерклассе
- фуехрерсчеиннуммерклассе
- Führerschein- Nr
- Fuhrerschein- Nr
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse
- фüхрерсчеиннуммернр 
- фухрерсчеиннуммернр 
- фуехрерсчеиннуммернр 
- фüхрерсчеиннуммерклассе 
- фухрерсчеиннуммерклассе 
- фуехрерсчеиннуммерклассе 
- Führerschein- Nr 
- Fuhrerschein- Nr 
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse 
- DL 
- БИБЛИОТЕК
- Driv Lic 
- Driv Licen 
- Driv License
- Driv Licenses 
- Driv Licence 
- Driv Licences 
- Driv Lic 
- Driver Licen 
- Driver License 
- Driver Licenses 
- Driver Licence 
- Driver Licences 
- Drivers Lic 
- Drivers Licen 
- Drivers License 
- Drivers Licenses 
- Drivers Licence 
- Drivers Licences 
- Driver's Lic 
- Driver's Licen 
- Driver's License 
- Driver's Licenses 
- Driver's Licence 
- Driver's Licences 
- Driving Lic 
- Driving Licen 
- Driving License 
- Driving Licenses 
- Driving Licence 
- Driving Licences

#### <a name="keyword_german_drivers_license_collaborative"></a>Keyword_german_drivers_license_collaborative

- НР — Фüхрерсчеин 
- НР — Фухрерсчеин 
- НР — Фуехрерсчеин 
- Нет — Фüхрерсчеин 
- Нет — Фухрерсчеин 
- Нет — Фуехрерсчеин 
- N — Фüхрерсчеин 
- N — Фухрерсчеин 
- N — Фуехрерсчеин
- НР — Фüхрерсчеин 
- НР — Фухрерсчеин 
- НР — Фуехрерсчеин 
- Нет — Фüхрерсчеин 
- Нет — Фухрерсчеин 
- Нет — Фуехрерсчеин 
- N — Фüхрерсчеин 
- N — Фухрерсчеин 
- N — Фуехрерсчеин 

#### <a name="keyword_german_drivers_license"></a>Keyword_german_drivers_license

- аусстеллунгсдатум
- аусстеллунгсорт
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde


## <a name="germany-identity-card-number"></a>Номер идентификационной карточки для Германии

### <a name="format"></a>Format

с 1 ноября 2010: девять букв и цифр

от 1 апреля 1987 до 31 октября 2010:10 цифр.

### <a name="pattern"></a>Шаблон

с 1 ноября 2010:
- одна буква (без учета регистра) 
- восемь цифр

от 1 апреля 1987 до 31 октября 2010:
- десять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- регулярное выражение Regex_germany_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_germany_id_card.

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- аусвеис
- гпид
- процедура
- идентификатион
- идентифизиерунгснуммер
- идентификационная карточка
- идентификационный номер
- ID — нуммер
- личный идентификатор
- персоналаусвеис
- Идентификатор персöнличе нуммер
- персöнличе идентификатионснуммер
- персöнличе — ID — нуммер


## <a name="germany-passport-number"></a>Номер паспорта для Германии
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации номера паспорта ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

десять цифр или букв

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.
- Первый символ — цифра или буква из этого набора (C, F, G, H, J, K) 
- три цифры 
- пять цифр или букв из этого набора (C,-H, J-N, P, R, T, V-Z) 
- цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_german_passport находит содержимое, которое соответствует шаблону;
- находится любое ключевое слово из пяти соответствующих списков;
- контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_german_passport_data находит содержимое, которое соответствует шаблону;
- находится любое ключевое слово из пяти соответствующих списков;
- контрольная сумма проходит проверку.

```xml
<!-- Germany Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- реисепасс
- реисепассе
- реисепасснуммер
- службу
- паспорты

#### <a name="keyword_german_passport_collaborative"></a>Keyword_german_passport_collaborative

- жебуртсдатум
- аусстеллунгсдатум
- аусстеллунгсорт

#### <a name="keyword_german_passport_number"></a>Keyword_german_passport_number

No — Реисепасс НР — Реисепасс

#### <a name="keyword_german_passport1"></a>Keyword_german_passport1

Реисепасс — НР

#### <a name="keyword_german_passport2"></a>Keyword_german_passport2

бнатионалит. t


## <a name="germany-tax-identification-number"></a>Идентификационный номер налогоплательщика (Германия)

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
- Две цифры 
- Необязательный пробел
- Три цифры 
- Необязательный пробел
- Три цифры 
- Необязательный пробел
- Две цифры
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_germany_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- идентификатионснуммер
- Идентификатор стеуер
- стеуеридентификатионснуммер
- стеуернуммер
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- зинн #
- зинн
- зинннуммер


## <a name="germany-value-added-tax-number"></a>Значение налогового номера добавленного в Германии

### <a name="format"></a>Format

11 буквенно-цифрового шаблона

### <a name="pattern"></a>Шаблон

11-буквенно-цифровой буквенно-значный шаблон:

- буква D или d
- буква E или e
- необязательный пробел
- три цифры
- необязательный пробел или запятая
- три цифры
- необязательный пробел или запятая
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_germany_value_added_tax_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_germany_value_added_tax_number.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_germany_value_added_tax_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- номер НДС
- НДС No
- процент #
- НДС # мехрвертстеуер
- мвст
- мехрвертстеуер идентификатионснуммер
- мехрвертстеуер нуммер


## <a name="greece-drivers-license-number"></a>Номер водительского удостоверения для драйвера Греция
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации номера лицензии для драйвера ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_greece_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_greece_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver "s_license_number

- Файл #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- δεια οδήγησης
- Адеиа одигисис


## <a name="greece-national-id-card"></a>Национальный идентификационный номер карты (Греция)

### <a name="format"></a>Format

Сочетание 7–8 букв и чисел, а также тире.

### <a name="pattern"></a>Шаблон

Семь букв и чисел (старый формат):
- одна буква (любая буква греческого алфавита); 
- тире; 
- шесть цифр.

Восемь букв и чисел (новый формат):
- две буквы, которые в прописном виде есть как в греческом, так и латинском алфавите (ABEZHIKMNOPTYX); 
- тире; 
- шесть цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_greece_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_greece_id_card.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- регулярное выражение Regex_greece_id_card находит содержимое, которое соответствует шаблону;

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- Греческий идентификатор
- Греческая национальная идентификация
- Греческая личная идентификационная карточка
- код греческой политики
- идентификационная карточка
- таутотита
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Номер паспорта для Греция

Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

Две буквы, за которыми следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение  `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_greece_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- passport number
- номер паспорта греческого алфавита
- паспорт нет
- διαβατηριο

## <a name="greece-tax-identification-number"></a>Идентификационный номер налога в Греция

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Девять цифр.
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение  `Regex_greece_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_greece_eu_tax_file_number` . 
    
```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- афм #
- афм
- аφμ | аφμ αριθμός
- аφμ
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- реестр налога нет
- Налоговый номер реестра
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- таксрегистрино #
- Идентификатор Tin
- номер Tin
- ИНН #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου Νο


## <a name="hong-kong-identity-card-hkid-number"></a>Номер идентификационной карточки Гонконг (HKID)

### <a name="format"></a>Format

Сочетание 8–9 букв и чисел, а также необязательные скобки вокруг последнего символа.

### <a name="pattern"></a>Шаблон

Сочетание 8–9 букв:
- 1–2 буквы (без учета регистра); 
- шесть цифр;  
- последний символ (любая цифра или буква "A") является проверочной цифрой и заключен в скобки (необязательно).

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_hong_kong_id_card;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- идентификационная карточка Гонконг
- хкидк
- id card
- identity card
- идентификационная карточка HK
- Идентификатор Гонконг
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証

   
## <a name="hungary-drivers-license-number"></a>Номер водительского удостоверения для драйвера Венгрии

Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

Две буквы, за которыми следуют шесть цифр.
  
### <a name="pattern"></a>Шаблон

Две буквы и шесть цифр:
  
- Две буквы (без учета регистра) 
- шесть цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение  `Regex_hungary_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_hungary_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- везетои енжедели


## <a name="hungary-national-identification-number"></a>Венгерский идентификационный номер

Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

11 цифр.
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
-  Одна цифра, соответствующая пол (1-м-штекер, 2-гнездо, другие номера также могут иметь гражданские телефоны перед 1900 или гражданами с удвоенной гражданией) 
- Шесть цифр, соответствующих дате рождения (ГГММДД)
- Три цифры, соответствующие серийному номеру.
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция  `Func_hungary_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_hungary_eu_national_id_card` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция  `Func_hungary_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- идентификационный номер
- identification number

- СЗ IG
- СЗ.IG.
- СЗ. IG.
- сземéлязоносíтó игазолвáни
- сземéли игазолвáни


## <a name="hungary-passport-number"></a>Номер паспорта для Венгрии

Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

Две буквы, за которыми следуют шесть или семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют шесть или семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение  `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_hungary_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- passport number
- Венгерский номер паспорта
- паспорт нет
- úтлевéл сзáма


## <a name="hungary-social-security-number-or-equivalent-identification"></a>Венгерский номер социального страхования или идентификация эквивалентных прав

Этот объект типа конфиденциальной информации доступен только в номере социального страхования ЕС или эквивалентного идентификатора.

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Девять цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция  `Func_hungary_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_hungary_eu_ssn_or_equivalent` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция  `Func_hungary_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- Венгерский номер социального страхования
- social security number
- соЦиалсекуритинумбер #
- хссн #
- соЦиалсекуритинно
- хссн
- таж
- таж #
- SSN
- SSN #
- социальное страхование нет
- áфа
- кöзöссéги адóсзáм
- áлталáнос форгалми адó сзáм
- хоззáадоттéртéк адó
- áфа сзáм
- магяр áфа сзáм


## <a name="hungary-tax-identification-number"></a>Идентификационный номер венгерского налога

Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

Десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Десять цифр:
  
- Одна цифра, которая должна быть "8" 
- Пять цифр, которые соответствуют количеству дней между датой 01/01/1867 и датой рождения отдельного лица.
- Три цифры, которые соответствуют номеру, созданному шансом выделить людей, которые поставили один и тот же день.
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция  `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_hungary_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция  `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- адóазоносíтó сзáм
- адóхатóсáг сзáм
- адóсзáм
- Венгерский Tin
- хунгатиантин #
- Налоговый орган без
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- номер НДС


## <a name="hungary-value-added-tax-number"></a>Венгерский номер добавленного значения налога

### <a name="format"></a>Format

10-буквенно-буквенно-цифровой шаблон

### <a name="pattern"></a>Шаблон

10 буквенно-цифровых буквенных символов:

- 2 буквы — HU или HU
- необязательный пробел
- 8 цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:

- Функция Func_hungarian_value_added_tax_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_hungarian_value_added_tax_number.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:

- Функция Func_hungarian_value_added_tax_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- процент
- Налоговый номер добавленной стоимости
- процент #
- ватно #
- хунгарианватно #
- налог но.
- налог на добавленное значение áфа
- кöзöссéги адóсзáм
- áлталáнос форгалми адó сзáм
- хоззáадоттéртéк адó
- áфа сзáм


## <a name="india-permanent-account-number-pan"></a>Номер постоянного счета Индии (PAN)

### <a name="format"></a>Format

10 букв или цифр.

### <a name="pattern"></a>Шаблон

10 букв или цифр:
- пять букв (без учета регистра); 
- четыре цифры; 
- буква, которая является алфавитным проверочным символом.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_india_permanent_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_india_permanent_account_number;
- Контрольная сумма проходит проверку.

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number 
- ПАНОРАМИРОВАНИЕ 
   
## <a name="india-unique-identification-aadhaar-number"></a>Уникальный идентификационный номер (Aadhaar) Индии

### <a name="format"></a>Format

12 цифр, содержащих необязательные пробелы или тире.

### <a name="pattern"></a>Шаблон

12 цифр:
- четыре цифры; 
- необязательный пробел или тире; 
- четыре цифры; 
- необязательный пробел или тире; 
- последняя цифра — проверочная.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_india_aadhaar находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_india_aadhar;
- Контрольная сумма проходит проверку.
- 
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:

- функция Func_india_aadhaar находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- аадхар
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>Номер идентификационной карточки Индонезия (KTP)

### <a name="format"></a>Format

16 цифр, содержащих необязательные точки.

### <a name="pattern"></a>Шаблон

16 цифр:
- две цифры (код провинции); 
- точка (необязательно); 
- две цифры (код округа или города); 
- две цифры (код района); 
- точка (необязательно); 
- шесть цифр в формате ДДММГГ (дата рождения); 
- точка (необязательно); 
- четыре цифры.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:

- регулярное выражение Regex_indonesia_id_card находит содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_indonesia_id_card.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>Международный номер банковского счета (IBAN)

### <a name="format"></a>Format

Код страны (две буквы), а также проверочные цифры (две) и номер bban (до 30 символов)

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.

- Двухбуквенный код страны
- Две проверочные цифры (после которых может следовать пробел)  
- 1–7 групп из четырех букв или цифр (могут разделяться пробелами)
- 1–3 буквы или цифры

Формат для названия каждой из стран немного отличается. Тип конфиденциальной информации IBAN применяется к следующим 60 странам:

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:

- функция Func_iban находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

Нет

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Международная классификация Diseases (ICD-10-CM)

### <a name="format"></a>Format

Dictionary

### <a name="pattern"></a>Шаблон

Ключевое слово

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Найдено ключевое слово из Dictionary_icd_10_updated.
- Найдено ключевое слово из Dictionary_icd_10_codes.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Найдено ключевое слово из Dictionary_icd_10_ "Обновлено".

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

### <a name="keywords"></a>Keywords

Любой термин из словаря Dictionary_icd_10_updated ключевых слов, основанный на [международной классификации Diseases, десятой версии, Клиникал модификации (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Этот тип ищет только термин, а не коды страхования.

Любой термин из словаря Dictionary_icd_10_codes ключевых слов, основанный на [международной классификации Diseases, десятой версии, Клиникал модификации (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Этот тип ищет только страховые коды, а не описание.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Международная классификация Diseases (ICD-9-CM)

### <a name="format"></a>Format

Dictionary

### <a name="pattern"></a>Шаблон

Ключевое слово

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Найдено ключевое слово из Dictionary_icd_9_updated.
- Найдено ключевое слово из Dictionary_icd_9_codes.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Найдено ключевое слово из Dictionary_icd_9_updated.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

Любой термин из словаря Dictionary_icd_9_updated ключевых слов, основанный на [международной классификации Diseases, девятой редакции, Клиникал модификации (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Этот тип ищет только термин, а не коды страхования.

Любой термин из словаря Dictionary_icd_9_codes ключевых слов, основанный на [международной классификации Diseases, девятой редакции, Клиникал модификации (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Этот тип ищет только страховые коды, а не описание.

## <a name="ip-address"></a>IP-адрес

### <a name="format"></a>Format

#### <a name="ipv4"></a>IPv4
Сложный шаблон, ответственный за форматированные (с точками) и неформатированные (без точек) версии IPv4-адресов.

#### <a name="ipv6"></a>Поддерживающ
 Сложный шаблон, ответственный за форматированные номера IPv6 (вместе с двоеточиями).

### <a name="pattern"></a>Шаблон

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

В случае с протоколом IPv6 политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- регулярное выражение Regex_ipv6_address находит содержимое, которое соответствует шаблону;
- ни одно ключевое слово из Keyword_ipaddress не находится.

В случае с протоколом IPv4 политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- регулярное выражение Regex_ipv4_address находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_ipaddress.

В случае с протоколом IPv6 политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- регулярное выражение Regex_ipv6_address находит содержимое, которое соответствует шаблону;
- ни одно ключевое слово из Keyword_ipaddress не находится.

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (ключевое слово с учетом регистра)
- ip address 
- ip addresses
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>Номер водительского удостоверения для Ирландии

Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

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
  
- Регулярное выражение  `Regex_ireland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_ireland_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- цеадúнас тиомáна


## <a name="ireland-national-identification-number"></a>Национальный идентификационный номер для Ирландии

Этот объект типа конфиденциальной информации включается только в тип конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

Сочетание букв, цифр и пробела в указанном шаблоне.
  
### <a name="pattern"></a>Шаблон

Сочетание букв, цифр и пробела в указанном шаблоне.
  
От 01 января 2013 до Now:
  
- семь цифр; 
- Одна контрольная цифра
- Один пробел или буква в верхнем регистре "W" (с учетом регистра)
    
До 01 января 2013:
  
- семь цифр; 
- Одна контрольная цифра
- Один пробел или буква в верхнем регистре (с учетом регистра)
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция находит содержимое, которое соответствует шаблону.
- Найдено ключевое слово FROM.
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция находит содержимое, которое соответствует шаблону.
    
```xml
 <!--Ireland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- Служба удостоверений клиента
- identification number

- личный идентификационный номер
- номер личной общедоступной службы
- Личная служба
- феарсанта сеирбхíсе поиблí
- PPS нет
- номер PPS
- Служба PPS нет
- PPS уимх
- ппсн
- ппсно #
- ппсно
- общедоступная служба
- публиксервицено #
- публиксервицено
- номер дохода и социального страхования
- RSI нет
- номер RSI
- рсин
- Клиент сеирбхíс аисеантаис
- уимх.настроен
- уимхир аисеантаис чáнач
- уимхир аисеантаис феарсанта
- уимхир феарсанта сеирбхíсе поиблí

## <a name="ireland-passport-number"></a>Номер паспорта для Ирландии

Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

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
  
- Регулярное выражение  `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_ireland_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passport number
- Ирландский номер паспорта
- паспорт нет
- соответствующий
- службу
- пассепорт
- пассепорт нумеро

## <a name="ireland-personal-public-service-pps-number"></a>Номер личной общедоступной службы (PPS) Ирландии

### <a name="format"></a>Format

Старый формат (до 31 декабря 2012):
- семь цифр, за которыми следует 1-2 букв 

Новый формат (1 января 2013 и после):
- семь цифр, за которыми следуют две буквы

### <a name="pattern"></a>Шаблон

Старый формат (до 31 декабря 2012):
- семь цифр 
- одна-2 буквы (без учета регистра) 

Новый формат (1 января 2013 и после):
- семь цифр 
- буква (без учета регистра), которая является буквенной контрольной цифрой 
- буква "A" или "H" (без учета регистра)

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_ireland_pps находит содержимое, которое соответствует шаблону.
- Верно одно из условий ниже:
    - найдено ключевое слово из Keyword_ireland_pps;
    - функция Func_eu_date находит дату в правильном формате.
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- функция Func_ireland_pps находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ireland_pps"></a>Keyword_ireland_pps

- Personal Public Service Number 
- PPS Number 
- PPS Num 
- PPS No. 
- PPS # 
- PPS # 
- ппсн 
- Public Services Card 
- Uimhir Phearsanta Seirbhíse Poiblí 
- Уимх. НАСТРОЕН 
- НАСТРОЕН 


## <a name="ireland-tax-identification-number"></a>Идентификационный номер налога для Ирландии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

семь цифр, за которыми следует буква без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

семь цифр, за которыми следует буква:
  
- семь цифр 
- одна буква (без учета регистра)
    
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_ireland_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_ireland_eu_tax_file_number"></a>Keywords_ireland_eu_tax_file_number

- Служба удостоверений клиента
- identification number

- личный идентификационный номер
- номер личной общедоступной службы
- Личная служба
- феарсанта сеирбхíсе поиблí
- PPS нет
- номер PPS
- Служба PPS нет
- PPS уимх
- ппсн
- ппсно #
- ппсно
- общедоступная служба
- публиксервицено #
- публиксервицено
- номер дохода и социального страхования
- RSI нет
- номер RSI
- рсин
- Клиент сеирбхíс аисеантаис
- уимх.настроен
- уимхир аисеантаис чáнач
- уимхир аисеантаис феарсанта
- уимхир феарсанта сеирбхíсе поиблí


## <a name="israel-bank-account-number"></a>Номер банковского счета для Израиля

### <a name="format"></a>Format

13 цифр.

### <a name="pattern"></a>Шаблон

Форматируемые
- две цифры 
- тире 
- три цифры 
- тире 
- восемь цифр

Неформатированные
- 	13 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_israel_bank_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_israel_bank_account_number.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number 
- Bank Account 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>Национальный идентификационный номер Израиля

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_israeli_national_id_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_Israel_National_ID;
- Контрольная сумма проходит проверку.

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

- מספר זהות 
- National ID Number
   
## <a name="italy-drivers-license-number"></a>Номер водительского удостоверения для Италии
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации номера лицензии для драйвера ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

сочетание из 10 букв и цифр

### <a name="pattern"></a>Шаблон

- сочетание из 10 букв и цифр:
- одна буква (без учета регистра) 
- буква "A" или "V" (без учета регистра) 
- семь букв (без учета регистра), цифр или символ подчеркивания. 
- одна буква (без учета регистра)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_italy_drivers_license_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_italy_drivers_license_number.

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente di guida 
- patente di guida 

## <a name="italy-national-identification-number"></a>Национальный идентификационный номер для Италии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

16 – символическое сочетание букв и цифр в указанном шаблоне.
  
### <a name="pattern"></a>Шаблон

16 – буквенное сочетание букв и цифр:
- три буквы, соответствующие первым трем согласным в имени семейства
- три буквы, соответствующие первым, третьим и четвертым согласным в имени.
- две цифры, соответствующие последним цифрам года рождения
- одна буква, соответствующая букве дня рождения, буквы используются в алфавитном порядке, но используются только буквы от A до E, H, L, M, P, R — T (то есть Январь — это R, а Октябрь — R)
- две цифры, которые соответствуют дню месяца рождения, для различения пола, 40 добавляется в день рождения для женщин
- четыре цифры, соответствующие коду города, который относится к органу государственной власти, в котором был создан пользователь, (для иностранных стран используются коды уровня страны).
- одна цифра четности
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_italy_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_italy_eu_national_id_card` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_italy_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
<!-- Italy national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- налоговые кости
- финансовый отчет по сокостям
- личные коды для сокодовых костей
- Персональные подкодеки
- Финансовый код
- Нумеро цертификато персональный
- Нумеро di идентификазионе Фин.
- личный идентификатор нумеро
- персональные настройки нумеро
- личный номер сертификата
- персональный код
- личный код
- личный идентификационный номер
- персоналкодено #
- Налоговый код
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- идентификационный номер налогоплательщика
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="italy-passport-number"></a>Номер паспорта для Италии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

две буквы или цифры, за которыми следуют семь цифр:
  
- две цифры или буквы (без учета регистра).
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_italy_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- номер паспорта для итальянского языка
- Репубблика итальянский пассапорто
- пассапорто
- пассапорто итальянский
- passport number
- Итальянский пассапорто нумеро
- пассапорто нумеро
- нумéро пассепорт италиен
- нумéро пассепорт


## <a name="italy-tax-identification-number"></a>Идентификационный номер налога для Италии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

16 букв и цифр в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

16 букв и цифр:
  
- три буквы, соответствующие первым трем согласным в имени семейства 
- три буквы, соответствующие первым, третьим и четвертым согласным в имени.
- две цифры, соответствующие последним цифрам года рождения
- одна цифра, соответствующая месяцу рождения, буквы используются в алфавитном порядке, но используются только буквы от A до E, H, L, M, P, R — T (то есть Январь — это R, а Октябрь — R)
- две цифры, которые соответствуют дню рождения, где 40 добавляется к дню рождения женщин, чтобы отличать от мужчин
- четыре цифры, соответствующие коду города, соответствующему органу государственной власти, в котором был создан пользователь, — коды уровня страны используются для иностранных стран
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_italy_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_italy_eu_tax_file_number"></a>Keywords_italy_eu_tax_file_number

- налоговые кости
- финансовый отчет по сокостям
- личные коды для сокодовых костей
- Персональные подкодеки
- Финансовый код
- Нумеро цертификато персональный
- Нумеро di идентификазионе Фин.
- личный идентификатор нумеро
- персональные настройки нумеро
- личный номер сертификата
- персональный код
- личный код
- личный идентификационный номер
- персоналкодено #
- Налоговый код
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- идентификационный номер налогоплательщика
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="italy-value-added-tax-number"></a>Налоговый номер добавленной стоимости (Италия)

### <a name="format"></a>Format

13-буквенно-цифровой буквенный шаблон с необязательными ограничителями

### <a name="pattern"></a>Шаблон

13-буквенно-цифровой буквенно-цифровой шаблон с необязательными ограничителями:

- I или i
- T или t
- необязательный пробел, точка, дефис или запятая
- 11 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_italy_value_added_tax_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_italy_value_added_tax_number.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_italy_value_added_tax_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- номер НДС
- НДС No
- процент #
- ива
- ива #


## <a name="japan-bank-account-number"></a>Номер банковского счета для Японии

### <a name="format"></a>Format

семь или восемь цифр

### <a name="pattern"></a>Шаблон

номер банковского счета:
- семь или восемь цифр
- код филиала банковского счета:
- четыре цифры 
- пробел или тире (необязательно) 
- три цифры

Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_jp_bank_account находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_jp_bank_account.
- Верно одно из условий ниже:
- функция Func_jp_bank_account_branch_code находит содержимое, которое соответствует шаблону;
- найдено ключевое слово из Keyword_jp_bank_branch_code.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_jp_bank_account находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_jp_bank_account.

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 
- 口座番号を当座預金口座の確認 
- #アカウントの確認 、 勘定番号の確認 
- #勘定の確認 
- 勘定番号の確認 
- 口座番号の確認 
- 銀行口座番号 
- 銀行口座 
- 銀行口座 # 
- 銀行の勘定番号 
- 銀行のаккт # 
- 銀行の勘定いいえ 
- 銀行口座番号
- 普通預金口座番号 
- 預金口座 
- 貯蓄口座 # 
- 貯蓄勘定の数 
- 貯蓄勘定 # 
- 貯蓄勘定番号 
- 普通預金口座番号 
- 引き落とし口座番号 
- 口座番号 
- 口座番号 # 
- デビットのаккт番号 
- デビット勘定 # 
- デビットакктの番号 
- デビット口座番号 

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

отемачи

## <a name="japan-drivers-license-number"></a>Номер водительского удостоверения для Японии

### <a name="format"></a>Format

12 цифр.

### <a name="pattern"></a>Шаблон

12 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_jp_drivers_license_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_jp_drivers_license_number.

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- DL # 
- DL 
- библиотек # 
- БИБЛИОТЕК 
- driver license 
- driver licenses 
- drivers license 
- driver's license 
- drivers licenses 
- driver's licenses 
- driving licence 
- лик # 
- Лик # 
- ликс # 
- state id 
- state identification 
- state identification number 
- 低所得国 # 
- 免許証 
- 状態ид
- 状態の識別 
- 状態の識別番号 
- 運転免許 
- 運転免許証 
- 運転免許証番号 


## <a name="japan-my-number---corporate"></a>Мой номер для Японии — корпоративный

### <a name="format"></a>Format

13 цифра, цифра

### <a name="pattern"></a>Шаблон

13 цифра:

- одна цифра от 1 до девяти
- 12 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_japanese_my_number_corporate находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_japanese_my_number_corporate.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_japanese_my_number_corporate находит содержимое, которое соответствует шаблону;

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- корпоративный номер
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>Япония мой номер — личное

### <a name="format"></a>Format

12 цифр номера

### <a name="pattern"></a>Шаблон

12 цифр:

- четыре цифры
- необязательный пробел, точка или дефис
- четыре цифры
- необязательный пробел, точка или дефис
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_japanese_my_number_personal находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_japanese_my_number_personal.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Функция Func_japanese_my_number_personal находит содержимое, которое соответствует шаблону;

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- мой номер
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード

   
## <a name="japan-passport-number"></a>Номер паспорта для Японии

### <a name="format"></a>Format

две буквы, за которыми следуют семь цифр.

### <a name="pattern"></a>Шаблон

две буквы (без учета регистра), за которыми следуют семь цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_jp_passport находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_jp_passport.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- パスポート 
- パスポート番号 
- パスポートのнум 
- パスポート # 

## <a name="japan-residence-card-number"></a>Номер карточки для Японии (Япония)

### <a name="format"></a>Format

12 букв и цифр

### <a name="pattern"></a>Шаблон

12 букв и цифр:
- две буквы (без учета регистра)
- восемь цифр 
- две буквы (без учета регистра)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение Regex_jp_residence_card_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keyword_jp_residence_card_number.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Номер карточки проживания
- Номер карточки проживания
- Карточка проживания #
- 在留カード番号

## <a name="japan-resident-registration-number"></a>Номер резидентного регистрационного номера для Японии

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

11 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_jp_resident_registration_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_jp_resident_registration_number.

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Resident Register Number 
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 住民登録番号 、 登録番号をレジデント 
- 住民基本登録番号 、 登録番号 
- 住民基本レジストリ番号を常駐 
- 登録番号を常駐住民基本台帳登録番号 

   
## <a name="japan-social-insurance-number-sin"></a>Номер социального страхования для Японии (SIN)

### <a name="format"></a>Format

7–12 цифр.

### <a name="pattern"></a>Шаблон

7–12 цифр
- четыре цифры 
- дефис (необязательно) 
- шесть цифр или
- 7–12 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_jp_sin находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_jp_sin.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_jp_sin_pre_1997 находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_jp_sin.

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 社会保険のテンキー 
- 社会保険番号 

## <a name="latvia-drivers-license-number"></a>Номер водительского удостоверения для Латвии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

три буквы, за которыми следуют шесть цифр.
  
### <a name="pattern"></a>Шаблон

три буквы и шесть цифр:
  
- три буквы (без учета регистра) 
- шесть цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_latvia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_latvia_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- аутовадīтāжа аплиекīба

## <a name="latvia-national-identification-number"></a>Национальный идентификационный номер для Латвии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

11 цифр и дефис в указанном формате.
  
### <a name="pattern"></a>Шаблон

11 цифр и дефис:
  
- шесть цифр, соответствующих дате рождения (ДДММГГ —) 
- дефис
- одна цифра, соответствующая столетию рождения ("0" для 19 века, "1" для 20-й век) и "2" для 21 века)
- четыре цифры, созданные случайным образом
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_latvia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_latvia_eu_national_id_card` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_latvia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
<!-- Latvia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- Административный номер
- алвас нē
- номер рождения
- номер для согражданства
- гражданское число
- номер электронного переписи
- электронный номер
- Финансовый код
- номер пользователя для сферы здравоохранения
- кодов #
- ID — код
- identification number

- идентификāЦижас нумурс
- ID — номер
- индивидуальный номер
- латвижа Алва
- Идентификатор наЦионāлаис
- 
national id
- Национальный идентификационный номер
- Национальный идентификационный номер
- national insurance number

- номер национальной регистрации
- нодокļа нумурс
- Идентификатор нодокļу
- нодокļу идентификāЦижа нумурс
- личный номер сертификата
- персональный код
- личный код
- личный идентификационный номер
- персональный идентификационный код
- личный идентификатор
- личный номер удостоверения
- персональный номер
- персональный числовой код
- персоналкодено #
- Пользователи Кодс
- код идентификации заполнения
- номер общедоступной службы
- 
registration number
- номер дохода
- страховой номер
- social security number

- Налоговый код штата
- номер налогового файла
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- номер Вотер

## <a name="latvia-passport-number"></a>Номер паспорта для Латвии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

две буквы или цифры, за которыми следуют семь цифр:
  
- две цифры или буквы (без учета регистра).
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_latvia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- passport number
- номер паспорта для Латвии
- паспорт нет
- ПАСЕ нумурс    

## <a name="latvia-tax-identification-number"></a>Идентификационный номер налога в Латвии
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр в указанном шаблоне
  
- шесть цифр, соответствующих дате рождения (ДДММГГ —) 
- одна цифра, соответствующая столетию рождения, где "0" соответствует 19 века, "1" соответствует 20 столетию, а "2" соответствует 21 столетию
- четыре цифры
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_latvia_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_latvia_eu_tax_file_number"></a>Keywords_latvia_eu_tax_file_number

- Административный номер
- алвас нē
- номер рождения
- номер для согражданства
- гражданское число
- номер электронного переписи
- электронный номер
- Финансовый код
- номер пользователя для сферы здравоохранения
- кодов #
- ID — код
- identification number

- идентификāЦижас нумурс
- ID — номер
- индивидуальный номер
- латвижа Алва
- Идентификатор наЦионāлаис
- 
national id
- Национальный идентификационный номер
- Национальный идентификационный номер
- national insurance number

- номер национальной регистрации
- нодокļа нумурс
- Идентификатор нодокļу
- нодокļу идентификāЦижа нумурс
- личный номер сертификата
- персональный код
- личный код
- личный идентификационный номер
- персональный идентификационный код
- личный идентификатор
- личный номер удостоверения
- персональный номер
- персональный числовой код
- персоналкодено #
- Пользователи Кодс
- код идентификации заполнения
- номер общедоступной службы
- 
registration number
- номер дохода
- страховой номер
- social security number

- Налоговый код штата
- номер налогового файла
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- номер Вотер

## <a name="lithuania-drivers-license-number"></a>Литва номер водительского удостоверения
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

восемь цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_lithuania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_lithuania_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- ваируотожо паžимėжимас

## <a name="lithuania-national-identification-number"></a>Литва Национальный идентификационный номер
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр без пробелов и разделителей:
  
- одна цифра, соответствующая пол и век рождения человека
- шесть цифр, соответствующих дате рождения (ГГММДД) 
- три цифры, которые соответствуют серийному числу даты рождения.
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_lithuania_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_lithuania_eu_national_id_card` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_lithuania_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
<!-- Lithuania national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- асменинис скаитменинис кодас
- асменс кодас
- номер службы для себя
- Идентификатор мокесčиų
- мокесčиų идентификавимас нумерис
- мокесčиų идентификавимо нумерис
- мокесčиų нумерис
- Национальный идентификационный номер
- персональный код
- персональный числовой код
- пилиеčио паслаугос нумерис
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- уникалус идентификавимо кодас
- уникалус идентификавимо нумерис
- уникальный идентификационный номер
- уникальный идентификационный номер
- уникуеидентитино #

## <a name="lithuania-passport-number"></a>Литва номер паспорта
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

восемь цифр или букв без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

восемь цифр или букв (без учета регистра)
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_lithuania_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- passport number
- номер паспорта лисуниан
- паспорт нет
- Пасо нумерис

## <a name="lithuania-tax-identification-number"></a>Код налога на Литва
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр.
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_lithuania_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_lithuania_eu_tax_file_number"></a>Keywords_lithuania_eu_tax_file_number

- асменинис скаитменинис кодас
- асменс кодас
- номер службы для себя
- Идентификатор мокесčиų
- мокесčиų идентификавимас нумерис
- мокесčиų идентификавимо нумерис
- мокесčиų нумерис
- Национальный идентификационный номер
- персональный код
- пилиеčио паслаугос нумерис
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- уникалус идентификавимо кодас
- уникалус идентификавимо нумерис
- уникальный идентификационный номер
- уникальный идентификационный номер
- уникуеидентитино #

## <a name="luxemburg-drivers-license-number"></a>Номер водительского удостоверения Луксембург
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

шесть цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

шесть цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_luxemburg_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_luxemburg_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- фахрерлаубнис

## <a name="luxemburg-national-identification-number"></a>Национальный идентификационный номер Луксембург
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр.
  
- одна цифра, соответствующая пол и век рождения человека
- шесть цифр, соответствующих дате рождения (ГГММДД) 
- три цифры, которые соответствуют серийному числу даты рождения.
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_luxemburg_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_luxemburg_eu_national_id_card` . 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- Идентификатор еиндеутиже
- Идентификатор еиндеутиже — нуммер
- еиндеутижеид #
- ID персоннелле
- идперсоннелле #
- идперсоннелле
- отдельный код
- индивидуальный идентификатор
- индивидуальная идентификация
- индивидуальное удостоверение
- нумéро д'идентификатион сотрудники
- личный идентификатор
- Личная идентификация
- личное удостоверение
- персоналидно #
- персоналиднумбер #
- персöнличе идентификатионснуммер
- уникальный идентификатор
- уникальное удостоверение
- уникуеидкэй #

## <a name="luxemburg-passport-number"></a>Номер паспорта Луксембург
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

восемь цифр или букв без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

восемь цифр или букв (без учета регистра)
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_nation_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_nation_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_nation_eu_passport_number"></a>Keywords_nation_eu_passport_number

- passport number
- номер паспорта для Латвии
- паспорт нет
- пасснуммер

## <a name="luxemburg-tax-identification-number"></a>Идентификационный номер налога на Луксембург
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

13 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

13 цифр:
  
- 11 цифр. 
- две контрольные цифры
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_luxemburg_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- Корзина де сéкуритé социального страхования
- éтаин не
- éтаин #
- Идентификация д'импôт
- налог на Люксембург идентификатиаунснуммер
- нумéро д'éтаин
- нумéро д'идентификатион финансовых луксембауржеоис
- нумéро д'идентификатион Фин.
- социальное обеспечение безопасности
- созиалунтерстüтзунг
- созиалверсéчерунг
- созиалверсичерунгсаусвеис
- Идентификатор стеиер
- стеиер идентификатиаунснуммер
- стеиер нуммер
- Идентификатор стеуер
- стеуеридентификатионснуммер
- стеуернуммер
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- зинн #
- зинн
- зиннзахл


## <a name="malaysia-identification-card-number"></a>Идентификационный номер карты Малайзии

### <a name="format"></a>Format

12 цифр, содержащих необязательные дефисы.

### <a name="pattern"></a>Шаблон

12 цифр:
- шесть цифр в формате ГГММДД Дата рождения; 
- тире (необязательно) 
- код места рождения из двух букв 
- тире (необязательно) 
- три случайные цифры 
- код пола из одной цифры;

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_malaysia_id_card_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_malaysia_id_card_number.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- карточка цифрового приложения
- i/c
- i/c нет
- внутренних
- МФ нет
- id card
- идентификационная карточка
- identity card
- k/p
- k/p
- кад акуан Дири
- кад апликаси Digital
- кад пенженалан Малайзии
- ключев
- ключевой номер
- микад
- микас
- микид
- мипр
- митентера
- идентификационная карточка Малайзии
- идентификационная карточка малайсиан
- NRIC
- Личная идентификационная карточка

## <a name="malta-drivers-license-number"></a>Номер водительского удостоверения для драйвера Мальта
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

Сочетание двух символов и шести цифр в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

сочетание двух символов и шести цифр:
  
- два символа (цифры или буквы без учета регистра);
- пробел (необязательно)
- три цифры
- пробел (необязательно)
- три цифры
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_malta_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_malta_eu_driver's_license_number` . 
    
```xml
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- лиċензжаные зада Севкан

## <a name="malta-national-identification-number"></a>Национальный идентификационный номер Мальта
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

семь цифр, за которыми следует одна буква
  
### <a name="pattern"></a>Шаблон

семь цифр, за которыми следует одна буква:
  
- семь цифр 
- одна прописная буква (с учетом регистра)
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_malta_eu_national_id_card` . 
    
Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Регулярное выражение  `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!--Malta national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- номер службы для себя
- ID ТАТ — такскса
- идентифика нумру Тал билжетт
- кодиċи нумерали персонали
- нумру Ta ' идентификаззжони персонали
- нумру Ta ' идентификаззжони ТАТ такскса
- нумру Ta ' идентификаззжони унику
- нумру Ta ' идентитà унику
- нумруные зада сервизз таċ ċиттадин
- нумру ТАТ — такскса
- персональный числовой код
- уникальный идентификационный номер
- уникальный идентификационный номер
- уникуеидентитино #


## <a name="malta-passport-number"></a>Номер паспорта для Мальта
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

семь цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_malta_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- passport number
- номер паспорта Мальтийский
- паспорт нет
- нумру Тал — пассапорт

## <a name="malta-tax-identification-number"></a>Идентификационный номер налога Мальта
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

Для национальных Мальтийский:
- семь цифр и одна буква в указанном шаблоне
  
Мальтийскийные страны и Мальтийский, не являющиеся субъектами:
- девять цифр
  
### <a name="pattern"></a>Шаблон

Мальтийский Nationals: семь цифр и одна буква
  
- семь цифр 
- одна буква (без учета регистра)
    
Мальтийскийные страны и Мальтийский, не связанные с организациями: девять цифр
  
- девять цифр 
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_malta_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Функция  `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- номер службы для себя
- ID ТАТ — такскса
- идентифика нумру Тал билжетт
- кодиċи нумерали персонали
- нумру Ta ' идентификаззжони персонали
- нумру Ta ' идентификаззжони ТАТ такскса
- нумру Ta ' идентификаззжони унику
- нумру Ta ' идентитà унику
- нумруные зада сервизз таċ ċиттадин
- нумру ТАТ — такскса
- персональный числовой код
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- уникальный идентификационный номер
- уникальный идентификационный номер
- уникуеидентитино #

## <a name="netherlands-citizens-service-bsn-number"></a>Номер службы (BSN) для Нидерландов

### <a name="format"></a>Format

восемь девяти цифр, содержащих необязательные пробелы

### <a name="pattern"></a>Шаблон

восемь девяти цифр:
- три цифры 
- пробел (необязательно) 
- три цифры 
- пробел (необязательно) 
- две три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_netherlands_bsn находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_netherlands_bsn;
- функция Func_eu_date2 находит дату в правильном формате.
- Контрольная сумма проходит проверку.

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_netherlands_bsn"></a>Keyword_netherlands_bsn
  
- BSN #
- BSN
- буржерсервиценуммер
- номер службы для себя
- номер пользователя
- персональный номер
- персональный числовой код
- номер, связанный с человеком
- персунлижк нуммер
- персунлижке нумериеке код
- персунсжебонден
- персунснуммер
- соЦиаал — фискаал нуммер
- социальное — финансовый номер
- софи
- софинуммер
- униек идентификатиенуммер
- униек идентитеитснуммер
- уникальный идентификационный номер
- уникальный идентификационный номер
- уникуеидентитино #

## <a name="netherlands-drivers-license-number"></a>Номер водительского удостоверения для Нидерландов
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

десять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_netherlands_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_netherlands_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- permis de conduire
- рижбевижс
- рижбевижснуммер

## <a name="netherlands-national-identification-number"></a>Национальный идентификационный номер Нидерландов
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять цифр
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_netherlands_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM.
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_netherlands_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!--Netherland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- BSN #
- BSN
- буржерсервиценуммер
- номер службы для себя
- номер пользователя
- персональный номер
- персональный числовой код
- номер, связанный с человеком
- персунлижк нуммер
- персунлижке нумериеке код
- персунсжебонден
- персунснуммер
- соЦиаал — фискаал нуммер
- социальное — финансовый номер
- софи
- софинуммер
- униек идентификатиенуммер
- униек идентитеитснуммер
- уникальный идентификационный номер
- уникальный идентификационный номер
- уникуеидентитино #

## <a name="netherlands-passport-number"></a>Номер паспорта Нидерландов
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

девять букв или цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять букв или цифр;
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_netherlands_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- номер паспорта для нидерландского языка
- passport number
- номер паспорта Нидерландов
- недерланден паспурт нуммер
- паспурт
- недерланден паспуртнуммер
- паспуртнуммер

## <a name="netherlands-tax-identification-number"></a>Идентификационный номер налога Нидерландов
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_netherlands_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- БТВ нуммер
- Идентификация налога на холлâнске
- идентификационный номер импуесто хуландес
- хуландес импуесто идентификация
- идентификатиенуммер
- идентификатиенуммер Van
- идентификационный номер импуесто
- номер импуесто
- Недерландс — идентификатор нуммер
- Недерландс идентификатие
- Недерландс идентификатиенуммер
- Недерландс беластингнуммер
- Недерландсе идентификатие
- Идентификация налога Нидерландов
- Налоговый код несерланд
- Tin Нидерландов
- Tin несерланд
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- Тал идентификации налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- Налоговая Тал
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="netherlands-value-added-tax-number"></a>Номер налога добавленных значений в Нидерландов

### <a name="format"></a>Format

14-буквенно-буквенно-цифровой шаблон

### <a name="pattern"></a>Шаблон

14-буквенно-буквенно-символьный шаблон:

- N или n
- L или l
- необязательный пробел, точка или дефис
- девять цифр
- необязательный пробел, точка или дефис
- B или b
- две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_netherlands_value_added_tax_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_netherlands_value_added_tax_number.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_netherlands_value_added_tax_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- номер НДС
- НДС No
- процент #
- веарде тафоеже налога на жетал
- БТВ нûмер
- БТВ — нуммер


## <a name="new-zealand-bank-account-number"></a>Номер банковского счета Новой Зеландии

### <a name="format"></a>Format

шаблон с 14 до 16 цифр с необязательным разделителем

### <a name="pattern"></a>Шаблон

шаблон с 14 до 16 цифр с необязательным разделителем:

- две цифры
- Необязательный дефис или пробел
- от трех до четырех цифр
- Необязательный дефис или пробел
- семь цифр
- Необязательный дефис или пробел
- две до трех цифр
- Параметры дефис или пробел

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_new_zealand_bank_account_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_new_zealand_bank_account_number.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_new_zealand_bank_account_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- номер счета
- банковский счет
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>Номер водительского удостоверения для Новой Зеландии

### <a name="format"></a>Format

8-буквенно-цифровой шаблон

### <a name="pattern"></a>Шаблон

8-буквенно-цифровой шаблон

- две буквы 
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_newzealand_driver_license_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_newzealand_driver_license_number.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Функция Func_newzealand_driver_license_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- дриверлиценце
- дриверлиценцес
- драйвер Лик
- Лицензия на драйвер
- лицензии на драйверы
- дриверслик
- дриверслиценце
- дриверслиценцес
- драйверы Лик
- драйверы ликс
- Лицензия на драйверы
- лицензии на драйверы
- Driver ' LIC
- Driver ' LICS
- Driver ' Licence
- Driver ' Licences
- драйвер "Лик
- драйвер "ЛИКС
- Лицензия на драйвер
- лицензии на драйвер
- дривер'слик
- дривер'сликс
- дривер'слиценце
- дривер'слиценцес
- Лик драйвера
- ликс драйвера
- Лицензия на драйвер
- лицензии на драйвер
- дриверлик #
- дриверликс #
- дриверлиценце #
- дриверлиценцес #
- драйвер Лик #
- драйвер ликс #
- Лицензия на драйвер #
- лицензии на драйверы #
- дриверслик #
- дриверсликс #
- дриверслиценце #
- дриверслиценцес #
- драйверы Лик #
- драйверы ликс #
- Лицензия на драйверы #
- лицензии на драйверы #
- Driver ' LIC #
- Driver ' LICS #
- Driver ' Licence #
- Driver ' Licences #
- драйвер "Лик #
- драйвер "ЛИКС #
- Лицензия на драйвер #
- лицензии на драйвер #
- дривер'слик #
- дривер'сликс #
- дривер'слиценце #
- дривер'слиценцес #
- Лик драйвера #
- ликс драйвера #
- Лицензия на драйвер #
- лицензии на драйвер #
- 
international driving permit
- international driving permits
- Ассоциация автомобилей
- связь с автомобилем Новой Зеландии


## <a name="new-zealand-inland-revenue-number"></a>Номер дохода по некоторому контакту для Новой Зеландии

### <a name="format"></a>Format

восемь или девять цифр с необязательными ограничителями

### <a name="pattern"></a>Шаблон

восемь или девять цифр с необязательными ограничителями

- две или три цифры
- необязательный пробел или дефис
- три цифры
- необязательный пробел или дефис
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_new_zealand_inland_revenue_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_new_zealand_inland_revenue_number.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_new_zealand_inland_revenue_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ИРД но.
- ИРД нет #
- NZ ИРД
- Новая Зеландия ИРД
- номер ИРД
- номер дохода на землю


## <a name="new-zealand-ministry-of-health-number"></a>Номер министерства здоровья Новой Зеландии

### <a name="format"></a>Format

три буквы, пробел (необязательно) и четыре цифры

### <a name="pattern"></a>Шаблон

три буквы (без учета регистра), пробел (необязательно) из четырех цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_new_zealand_ministry_of_health_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_nz_terms;
- Контрольная сумма проходит проверку.

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- нхи 
- Новая Зеландия 
- Здравоохранение 
- обращения 


## <a name="new-zealand-social-wlefare-number"></a>Номер социального влефареа Новой Зеландии

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять цифр

- три цифры
- Необязательный перенос
- три цифры
- Необязательный перенос
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_newzealand_social_welfare_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_newzealand_social_welfare_number.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Функция Func_newzealand_social_welfare_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- социальные велфаре #
- социальные велфаре #
- социальное велфаре No.
- номер социального велфаре
- свн #

   
## <a name="norway-identification-number"></a>Идентификационный номер Норвегии

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр:
- шесть цифр в формате ддммгг — Дата рождения; 
- индивидуальный номер из трех цифр 
- две контрольные цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_norway_id_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_norway_id_number;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_norway_id_numbe находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- Процедура
- персоннуммер
- фøдселснуммер

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>Идентификационный номер единой системы для различных целей Филиппины

### <a name="format"></a>Format

12 цифр, разделенных дефисами.

### <a name="pattern"></a>Шаблон

12 цифр:
- четыре цифры 
- дефис 
- семь цифр 
- дефис 
- одна цифра

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_philippines_unified_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_philippines_id.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID 
- умид 
- Identity Card 
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>Номер водительского удостоверения для драйвера Польша
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

14 цифр, содержащих 2 косых черты.
  
### <a name="pattern"></a>Шаблон

14 цифр и 2 косых черт:
  
- пять цифр 
- косая черта
- две цифры
- косая черта
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_poland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_poland_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- право жазди

## <a name="poland-identity-card"></a>Идентификационная карточка Польша

### <a name="format"></a>Format

три буквы и шесть цифр.

### <a name="pattern"></a>Шаблон

три буквы (без учета регистра), за которыми следуют шесть цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_polish_national_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_polish_national_id_passport_number;
- Контрольная сумма проходит проверку.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Довóд особисти
- Нумер доводу особистего
- Назва i нумер доводу особистего
- Назва i НР доводу особистего
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- Dow. совместим.

   
## <a name="poland-national-id-pesel"></a>Национальный идентификатор Польша (PESEL)
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации страны ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

11 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_pesel_identification_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_pesel_identification_number;
- Контрольная сумма проходит проверку.

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- довóд особисти
- довóдособисти
- ниеповтарзални нумер
- ниеповтарзалнинумер
- НР. PESEL
- НР — PESEL
- Нумер идентификацижни
- PESEL
- тоżсамоśЦи народовеж

   
## <a name="poland-passport-number"></a>Номер паспорта для Польша
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации номера паспорта ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

две буквы и семь цифр.

### <a name="pattern"></a>Шаблон

Две буквы (без учета регистра), за которыми следуют семь цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_polish_passport_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_polish_national_id_passport_number;
- Контрольная сумма проходит проверку.

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Нумер пасзпорту
- НР. пасзпорту
- пасзпорт

## <a name="poland-regon-number"></a>Номер РЕГОНа Польша

### <a name="format"></a>Format

девять цифр или номер из 14 цифр

### <a name="pattern"></a>Шаблон

девять цифр или 14 цифр:

- девять цифр или 
- девять цифр
- дискрецион
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_polish_regon_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_polish_regon_number.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Функция Func_polish_regon_number находит содержимое, которое соответствует шаблону;

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- Идентификатор РЕГОН
- Статистический номер
- Идентификатор статистики
- Статистическая нет
- номер РЕГОН
- регонид #
- регонно #
- Код компании
- компанид #
- компанидно #
- Нумер статистикзни
- нумеру РЕГОН
- нумерстатистикзни #
- нумерурегон #


## <a name="poland-tax-identification-number"></a>Идентификационный номер для таможенного учета Польша
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_poland_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- нип #
- нип
- Нумер идентификакжи податковеж
- нумеридентификакжиподатковеж #
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- Код НДС #
- Код НДС
- НДС No
- номер НДС
- ватид #
- ватид
- ватно #
   

## <a name="portugal-citizen-card-number"></a>Номер карточки с префиксом "Португалия"
- Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации страны ЕС и доступен как отдельный объект типа конфиденциальной информации.
- Этот объект типа конфиденциальной информации включен в номер социального страхования ЕС или эквивалентный тип конфиденциальной информации.


### <a name="format"></a>Format

восемь цифр

### <a name="pattern"></a>Шаблон

восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_portugal_citizen_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_portugal_citizen_card.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- билхете de identidade
- картãо de Цидадãо
- карточка "гражданская"
- номер документа
- документо de идентификаçãо
- идентификационный номер
- Идентификация нет
- identification number

- удостоверение идентификационной карточки
- Номер идентификационной карточки
- номер национальной идентификационной карточки
- используемый
- нúмеро BI — немецкий (Португалия)
- нúмеро де идентификаçãо граждан
- нúмеро de идентификаçãо Фин.
- нúмеро Do документо
- номер бизнес-аналитики (Португалия)


## <a name="portugal-drivers-license-number"></a>Номер водительского удостоверения для драйвера Португалия
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

две буквы, за которыми следуют семь чисел в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

две буквы, за которыми следуют семь цифр со специальными символами:
  
- две буквы (без учета регистра) 
- дефис
- шесть цифр
- пробел
- одна цифра
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_portugal_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_portugal_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- картеира de моториста

## <a name="portugal-passport-number"></a>Номер паспорта для Португалия
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

одна буква, за которой следуют шесть цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

одна буква, за которой следуют шесть цифр:
  
- одна буква (без учета регистра)
- шесть цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_portugal_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- passport number
- номер паспорта для португальского языка
- паспорт нет
- нúмеро Do пассапорте

## <a name="portugal-tax-identification-number"></a>Идентификационный номер для налога на Португалия
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять цифр
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_portugal_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- CPF #
- CPF
- включена #
- включена
- нúмеро де идентификаçãо Фиска
- финансовый нумеро
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="romania-drivers-license-number"></a>Номер водительского удостоверения для драйвера Румыния
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

один символ, за которым следуют восемь цифр
  
### <a name="pattern"></a>Шаблон

один символ, за которым следуют восемь цифр:
  
- одна буква (без учета регистра) или цифра 
- восемь цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_romania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_romania_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- разрешение de кондуцере

## <a name="romania-national-identification-number"></a>Национальный идентификационный номер Румыния
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

13 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

13 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_romania_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_romania_eu_national_id_card` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_romania_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!--Romania national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- кнп #
- кнп
- Личный идентификаре наложенного платежа
- цифровой платеж, персональный
- наложенный Уник идентификаре
- коднумерикперсонал #
- финансовый НР кодул.
- идентификареа фискалă НР #
- ID — UL таксеи
- страховой номер
- инсуранценумбер #
- идентификатор страны #
- 
national id
- Национальный идентификационный номер
- нумăр идентификаре персональный
- нумăр идентитате
- нумăр Personal Уник
- нумăридентитате #
- нумăридентитате
- нумăрперсоналуник #
- нумăрперсоналуник
- нумăру де идентификаре фискалă
- нумăрул де идентификаре фискалă
- персональный числовой код
- крепления #
- крепления
- Налоговый файл нет
- номер налогового файла
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- уникальный идентификационный номер
- уникальный идентификационный номер
- уникуеидентитино #
- уникуеидентитино

## <a name="romania-passport-number"></a>Номер паспорта для Румыния
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

восемь или девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

восемь или девять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_romania_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

- passport number
- номер паспорта для румынского языка
- паспорт нет
- нумăрул паșапортулуи

## <a name="romania-tax-identification-number"></a>Идентификационный номер для налога на Румыния
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

13 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

13 цифр.
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_romania_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_romania_eu_tax_file_number` . 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_romania_eu_tax_file_number"></a>Keywords_romania_eu_tax_file_number

- кнп #
- кнп
- Личный идентификаре наложенного платежа
- цифровой платеж, персональный
- наложенный Уник идентификаре
- коднумерикперсонал #
- финансовый НР кодул.
- идентификареа фискалă НР #
- ID — UL таксеи
- страховой номер
- инсуранценумбер #
- идентификатор страны #
- 
national id
- Национальный идентификационный номер
- нумăр идентификаре персональный
- нумăр идентитате
- нумăр Personal Уник
- нумăридентитате #
- нумăридентитате
- нумăрперсоналуник #
- нумăрперсоналуник
- нумăру де идентификаре фискалă
- нумăрул де идентификаре фискалă
- персональный числовой код
- крепления #
- крепления
- Налоговый файл нет
- номер налогового файла
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #
- уникальный идентификационный номер
- уникальный идентификационный номер
- уникуеидентитино #
- уникуеидентитино


## <a name="russia-passport-number-domestic"></a>Номер паспорта для России (Россия)

### <a name="format"></a>Format

номер из десяти цифр

### <a name="pattern"></a>Шаблон

номер из десяти цифр:

- две цифры
- необязательный пробел или дефис
- две цифры
- необязательный пробел
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение Regex_Russian_Passport_Number_Domestic находит содержимое, которое соответствует шаблону.
- Найдено ключевое слово из Keyword_Russian_Passport_Number.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- номер паспорта
- паспорт нет
- службу #
- идентификатор паспорта
- пасспортно #
- пасспортнумбер #
- паспорт нет
- Идентификатор паспорт
- поссийской паспорт
- пусский номер паспорта
- паспорт #
- паспортид #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Номер паспорта для России Международная

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять цифр:

- две цифры
- необязательный пробел или дефис
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение Regex_Russian_Passport_Number_International находит содержимое, которое соответствует шаблону.
- Найдено ключевое слово из Keyword_Russian_Passport_Number.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- номер паспорта
- паспорт нет
- службу #
- идентификатор паспорта
- пасспортно #
- пасспортнумбер #
- паспорт нет
- Идентификатор паспорт
- поссийской паспорт
- пусский номер паспорта
- паспорт #
- паспортид #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Национальный идентификатор для Саудовской Аравии

### <a name="format"></a>Format

десять цифр

### <a name="pattern"></a>Шаблон

десять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_saudi_arabia_national_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_saudi_arabia_national_id.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Номер национальной идентификационной карточки для регистрации (NRIC), Сингапур

### <a name="format"></a>Format

девять букв и цифр

### <a name="pattern"></a>Шаблон

- девять букв и цифр:
- буква "F", "G", "S" или "T" (без учета регистра) 
- семь цифр 
- цифра алфавитной проверки

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_singapore_nric;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card 
- Identity Card Number 
- NRIC 
- ВНУТРЕННИХ 
- Foreign Identification Number 
- ПРОЦЕНТ 
- 身份证 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>Номер водительского удостоверения для драйвера Словакия
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

один символ, за которым следуют семь цифр.
  
### <a name="pattern"></a>Шаблон

один символ, за которым следуют семь цифр.
  
- одна буква (без учета регистра) или цифра
- семь цифр 
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_slovakia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_slovakia_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- водиčскý преуказ

## <a name="slovakia-national-identification-number"></a>Словакия Национальный идентификационный номер
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

десять цифр, содержащих одну обратную косую черту;
  
### <a name="pattern"></a>Шаблон

десять цифр, содержащих одну обратную косую черту:
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_slovakia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_slovakia_eu_national_id_card` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_slovakia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!-- Slovakia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- азоносíтó сзáм
- номер рождения
- číсло нáроднеж идентификаčнеж Карти
- číсло обčианскéхо преуказу
- даňовé číсло
- идентификационный номер
- Идентификация нет
- identification number

- идентификаčнá карта č
- идентификаčнé číсло
- удостоверение идентификационной карточки
- Номер идентификационной карточки
- нáроднá идентификаčнá знаčка č
- номер страны
- натионалнумбер #
- Немзети сземéлязоносíтó игазолвáни
- персоналиднумбер #
- рč
- родне Цисло
- роднé číсло
- social security number

- SSN #
- SSN
- сземéли игазолвáни сзáм
- сземéли игазолвáни сзáма
- сземéлигазолвáни сзáм
- Налоговый файл нет
- номер налогового файла
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #

## <a name="slovakia-passport-number"></a>Словакия — номер паспорта
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

одна цифра или буква, за которой следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

одна цифра или буква (без учета регистра), за которой следуют семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_slovakia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- passport number
- номер паспорта словакиан
- паспорт нет
- číсло Пасу

## <a name="slovakia-tax-identification-number"></a>Идентификационный номер налогоплательщика (Словакия)
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

десять цифр
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_slovakia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_slovakia_eu_tax_file_number` . 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovakia_eu_tax_file_number"></a>Keywords_slovakia_eu_tax_file_number

- азоносíтó сзáм
- номер рождения
- číсло нáроднеж идентификаčнеж Карти
- číсло обčианскéхо преуказу
- даňовé číсло
- идентификационный номер
- Идентификация нет
- identification number

- идентификаčнá карта č
- идентификаčнé číсло
- удостоверение идентификационной карточки
- Номер идентификационной карточки
- нáроднá идентификаčнá знаčка č
- номер страны
- натионалнумбер #
- Немзети сземéлязоносíтó игазолвáни
- персоналиднумбер #
- рč
- родне Цисло
- роднé číсло
- social security number

- SSN #
- SSN
- сземéли игазолвáни сзáм
- сземéли игазолвáни сзáма
- сземéлигазолвáни сзáм
- Налоговый файл нет
- номер налогового файла
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="slovenia-drivers-license-number"></a>Номер водительского удостоверения для драйвера Словения
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

девять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_slovenia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_slovenia_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver "s_license_number

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license 
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- возниšко доволженже

## <a name="slovenia-national-identification-number"></a>Национальный идентификационный номер (Словения)
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

13 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

13 цифр в указанном шаблоне:
  
- семь цифр, которые соответствуют дате рождения (ДДММЛЛЛ), где "ЛЛЛ" соответствует последним трем цифрам года рождения 
- две цифры, соответствующие области рождения
- три цифры, которые соответствуют сочетанию пола и серийного номера для людей, которые приставили один и тот же день (000-499 для пола и 500-999 для розетки)
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_slovenia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_slovenia_eu_national_id_card` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_slovenia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!-- Slovenia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- единствена šтевилка главнега дрžавлжана
- емšо
- енотна матикна šтевилка обкана
- идентификационная карточка
- identification number

- идентификаЦижска šтевилка
- идентификационная карточка
- Идентификатор наЦионална
- наЦионални потни List
- 
national id
- осебна изказника
- осебни кода
- осебни Ne
- осебни šтевилка
- персональный код
- персональный номер
- персональный числовой код
- šтевилка дрžавлжана
- уникальный номер соряда
- уникальный идентификационный номер
- уникальный идентификационный номер
- уникальный основной номер
- уникальный регистрационный номер
- уникуеидентитино #
- уникуеидентитино #

## <a name="slovenia-passport-number"></a>Номер паспорта для Словения
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

две буквы, за которыми следуют семь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

две буквы, за которыми следуют семь цифр:
  
- буква "P"
- одна прописная буква
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_slovenia_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- passport number
- номер паспорта для словенского языка
- паспорт нет
- Список потнега šтевилка

## <a name="slovenia-tax-identification-number"></a>Идентификационный номер для налога на Словения
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

восемь цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

восемь цифр
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_slovenia_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- давčна šтевилка
- идентификаЦижска šтевилка Давка
- šтевилка давčне датотеке
- Налоговый файл нет
- номер налогового файла
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="south-africa-identification-number"></a>Идентификационный номер Южно-Африканского Республика

### <a name="format"></a>Format

13 цифр, которые могут содержать пробелы.

### <a name="pattern"></a>Шаблон

13 цифр:
- шесть цифр в формате ГГММДД Дата рождения; 
- четыре цифры 
- Индикатор гражданства, состоящих из одной цифры 
- цифра "8" или "9" 
- одна цифра контрольной суммы

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_south_africa_identification_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_south_africa_identification_number;
- Контрольная сумма проходит проверку.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- Процедура 
   
## <a name="south-korea-resident-registration-number"></a>Регистрационный номер резидентной Южной Кореи

### <a name="format"></a>Format

13 цифр, содержащих дефис.

### <a name="pattern"></a>Шаблон

13 цифр:
- шесть цифр в формате ГГММДД Дата рождения; 
- дефис 
- одна цифра, определяемая столетием и пол 
- код региона рождения из четырех цифр 
- одна цифра, используемая для различения людей, для которых предыдущие числа идентичны 
- контрольная цифра.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_south_korea_resident_number;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card 
- Citizen's Registration Number 
- Jumin deungnok beonho 
- ррн 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Номер водительского удостоверения для Испании
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

восемь цифр, за которыми следует один символ
  
### <a name="pattern"></a>Шаблон

восемь цифр, за которыми следует один символ:
  
- восемь цифр 
- одна цифра или буква (без учета регистра)
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_spain_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_spain_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver "s_license_number

- длно #
- DL #
- Drivers лик.
- Лицензия на драйвер
- driver license
- drivers licence
- drivers license
- driver's licence
- driver's license
- driving licence
- driving license
- номер лицензии на драйвер
- номер водительского удостоверения
- драйвер номер лицензии
- номер лицензии на драйверы
- номер лицензии на драйвер
- номер водительского удостоверения
- номер водительской лицензии
- номер водительского удостоверения
- движущие разрешение
- движущие число разрешений
- пермисо de кондукЦиóн
- пермисо кондукЦиóн
- нúмеро лиценЦиа кондуЦир
- нúмеро de карнет де кондуЦир
- нúмеро карнет кондуЦир
- лиценЦиа кондуЦир
- нúмеро de пермисо де кондуЦир
- нúмеро де пермисо кондуЦир
- нúмеро пермисо кондуЦир
- пермисо кондуЦир
- лиценЦиа de манежо
- El карнет de кондуЦир
- Карнет кондуЦир

## <a name="spain-national-identification-number"></a>Национальный идентификационный номер Испания
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации ЕС по национальному идентификационному номеру.

### <a name="format"></a>Format

семь цифр, за которыми следует один символ
  
### <a name="pattern"></a>Шаблон

семь цифр, за которыми следует один символ
  
- семь цифр
- одна цифра или буква (без учета регистра)
    
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_spain_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_spain_eu_national_id_card"` . 
    
```xml
<!-- Spain national identification number -->
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- карнé de ИДЕНТИДАД
- DNI #
- DNI
- днинúмеро #
- документо наЦионал де ИДЕНТИДАД
- ИДЕНТИДАД úнико
- идентидадúнико #
- страховой номер
- Национальный идентификационный номер
- Национальная идентификация
- натионалид #
- натионалидно #
- ние #
- ние
- ниенúмеро #
- нúмеро de идентификаЦиóн
- нúмеро наЦионал ИДЕНТИДАД
- персональный идентификационный номер
- личный идентификатор
- уникальный идентификационный номер
- уникальным #

## <a name="spain-passport-number"></a>Номер паспорта для Испании
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера паспорта ЕС.

### <a name="format"></a>Format

сочетание букв и цифр из восьми или девяти символов без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

сочетание букв и цифр из восьми или девяти символов:
  
- две цифры или буквы 
- одна цифра или буква (необязательно)
- шесть цифр
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_spain_eu_passport_number` . 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- службу
- Служба Passport, Испания
- Книга Passport
- passport number
- паспорт нет
- либрета пасапорте
- нúмеро пасапорте
- еспаñа пасапорте
- пасапорте


## <a name="spain-social-security-number-ssn"></a>Номер социального страхования (SSN) Испания
Этот объект типа конфиденциальной информации включен в номер социального страхования ЕС или эквивалентный тип конфиденциальной информации и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

11–12 цифр.

### <a name="pattern"></a>Шаблон

11-12 цифр:
- две цифры 
- косая черта (необязательно) 
- семь и восемь цифр 
- косая черта (необязательно) 
- две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_spanish_social_security_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

Нет

## <a name="spain-tax-identification-number"></a>Налоговый идентификационный номер Испания
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

семь или восемь цифр, а также одна или две буквы в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

Испанские пользователи с национальной идентификационной карточкой Испании Испания:
  
- восемь цифр 
- одна прописная буква (с учетом регистра) 
    
Нерезидентские Спаниардс без национальной идентификационной карточки Испании
  
- одна прописная буква L (с учетом регистра)
- семь цифр
- одна прописная буква (с учетом регистра) 
    
Резидентный Спаниардс в течение 14 лет без международной идентификационной карточки для Испании:
  
- одна прописная буква K (с учетом регистра)
- семь цифр 
- одна прописная буква (с учетом регистра)
    
Фореигнерс с идентификационным номером внешнего получателя
  
- одна прописная буква "X", "Y" или "Z" (с учетом регистра) 
- семь цифр
- одна прописная буква (с учетом регистра) 
    
Фореигнерс без идентификационного номера внешнего получателя
  
- одна прописная буква "M" (с учетом регистра) 
- семь цифр
- одна прописная буква (с учетом регистра) 
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_spain_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- CIF
- Цифид #
- Цифнúмеро #
- нúмеро de контрибуйенте
- нúмеро de идентификаЦиóн Фин.
- нúмеро де импуесто корпоративо
- спанишЦифид #
- спанишЦифид
- спанишЦифно #
- спанишЦифно
- Налоговый файл нет
- номер налогового файла
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="sql-server-connection-string"></a>Строка подключения к SQL Server

### <a name="format"></a>Format

Строка "идентификатор пользователя", "идентификатор пользователя", "UID" или "UserId", за которыми следуют символы и строки, описанные в приведенном ниже шаблоне.

### <a name="pattern"></a>Шаблон

- строка "идентификатор пользователя", "идентификатор пользователя", "UID" или "UserId"
- Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.
- строка "Password" или "pwd", где "pwd" не предшествует буква нижнего регистра
- знак равенства (=);
- любой символ, не являющийся знаком доллара ($), символ процента (%), символ "больше" (>), символ "@", "символ" (@), знак кавычек ("), точка с запятой (;), левая фигурная скобка ([) или левая квадратная скобка ({)
- Любая комбинация 7-128 символов, не отделяющая точку с запятой (;), косая черта (/) или кавычки (").
- точка с запятой (;) или кавычки (")

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_SQLServerConnectionString находит содержимое, которое соответствует шаблону;
- **Не** найдено ключевое слово из CEP_GlobalFilter.
- Регулярное выражение CEP_PasswordPlaceHolder не **находит содержимое** , которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- Некоторые пароли
- сомепассворд
- секретпассворд
- примером

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- Пароль или pwd, за которым следует 0-2 пробелов, знак равенства (=), 0-2 пробелы и звездочка (*)--или--
- Пароль или pwd, а затем:
    - Знак равенства (=)
    - Символ "меньше" (<)
    - Любое сочетание 1-200 символов, которые являются буквами верхнего или нижнего регистра, цифрами, звездочкой (*), дефисом (-), подчеркиванием (_) или символом пробела
    - Символ "больше" (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- компанией
- компании
- базу
- песочниц
- онебокс
- localhost
- 127.0.0.1
- тестакс.<!--no-hyperlink-->порта
- s — int.<!--no-hyperlink-->команде

## <a name="sweden-drivers-license-number"></a>Номер водительского удостоверения драйвера Швеции
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации номера лицензии для драйвера ЕС.

### <a name="format"></a>Format

десять цифр, содержащие дефис
  
### <a name="pattern"></a>Шаблон

десять цифр, содержащих дефис:
  
- шесть цифр 
- дефис
- четыре цифры
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение  `Regex_sweden_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_sweden_eu_driver's_license_number` . 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Keywords

**Keywords_sweden_eu_driver "s_license_number**

- DL #
- driver license
- номер водительского удостоверения
- Лицензия на драйвер
- Drivers лик.
- drivers license
- drivers licence
- driver's license
- номер водительского удостоверения
- номер лицензии на драйвер
- номер водительского удостоверения
- длно #
- кöркорт

## <a name="sweden-national-id"></a>Национальный идентификатор, Швеция
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации страны ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

десять или 12 цифр и необязательный разделитель

### <a name="pattern"></a>Шаблон

десять или 12 цифр, а также необязательный разделитель:
- две до четырех цифр (необязательно) 
- Шесть цифр в формате даты ГГММДД. 
- разделитель "-" или "+" (необязательно), а также
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_swedish_national_identifier находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

Нет
   
## <a name="sweden-passport-number"></a>Номер паспорта Швеции
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации номера паспорта ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

восемь цифр

### <a name="pattern"></a>Шаблон

восемь последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_sweden_passport_number находит содержимое, которое соответствует шаблону;
- выполняется одно из следующих условий:
    - Найдено ключевое слово из Keyword_passport.
    - Найдено ключевое слово из Keyword_sweden_passport.

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- visa requirements 
- Alien Registration Card 
- Schengen visas 
- Schengen visa 
- Visa Processing 
- Visa Type 
- Single Entry 
- Multiple Entry 
- G3 Processing Fees 

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport# 
- Службу # 
- пасспортид 
- пасспортно 
- пасспортнумбер 
- パスポート 
- パスポート番号 
- パスポートのнум 
- パスポート # 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport# 
- пассепорт # 
- пассепортнон 
- Passeportn ° 

## <a name="sweden-social-security-number-or-equivalent-identification"></a>Номер социального страхования для Швеции или эквивалентная идентификация
Этот объект типа конфиденциальной информации доступен только в номере социального страхования ЕС или эквивалентного идентификатора.

### <a name="format"></a>Format

12 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

12 цифр:
  
- восемь цифр, которые соответствуют дате рождения (ГГГГММДД) 
- три цифры, которые соответствуют серийному номеру, где: 
  - Последняя цифра в числовом номере указывает на пол, назначая нечетное число для пола и четное число для розетки.
  - до 1990, назначение серийного номера соответствует району, в котором был выпущен номер, или (если он родился до 1947), где он был удален, в соответствии с налоговыми записями на 1 января 1947 с особым кодом (как правило, 9 в седьмой цифре) для иммигрантс 
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_sweden_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_sweden_eu_ssn_or_equivalent` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_sweden_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

- личный идентификационный номер
- identification number
- личный идентификатор
- Идентификатор
- Идентификация нет
- персональный идентификационный номер
- Идентификатор персоннуммер
- Идентификатор персонлигт — нуммер
- Идентификатор уникт — нуммер
- персоннуммер
- идентификатионснумрет
- персоннуммер #
- идентификатионснумрет #

## <a name="sweden-tax-identification-number"></a>Идентификационный номер налога для Швеции
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.

### <a name="format"></a>Format

десять цифр и символ в указанном шаблоне;
  
### <a name="pattern"></a>Шаблон

десять цифр и символ:
  
- шесть цифр, соответствующих дате рождения (ГГММДД) 
- знак плюс, знак минус или обратная косая черта
- три цифры, которые делают идентификационный номер уникальным, где: 
  - для номеров, выпущенных до 1990, седьмой и восьмой цифрой определяют район рождения или пользователей, порожденных иностранным пользователем.
  - цифра в девятой позиции указывает на пол, который нечетен для пола или даже для розетки.
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_sweden_eu_tax_file_number` . 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
    
```xml
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

### <a name="keywords"></a>Keywords

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- личный идентификационный номер
- персоннуммер
- Идентификатор СКАТТ нуммер
- СКАТТ идентификатион
- скаттебеталаренс идентификатионснуммер
- Tin свериже
- Налоговый файл
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Налоговый номер
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #


## <a name="swift-code"></a>Код SWIFT

### <a name="format"></a>Format

четыре буквы, за которыми следует 5-31 букв или цифр

### <a name="pattern"></a>Шаблон

четыре буквы, за которыми следует 5-31 букв или цифр:
- код банка из четырех букв (без учета регистра) 
- необязательный пробел 
- 4–28 букв или цифр (основной номер банковского счета, BBAN) 
- необязательный пробел 
- одна – три буквы или цифры (остаток от BBAN)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_swift находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_swift.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362 
- iso 9362 
- iso9362 
- SWIFT\# 
- свифткоде 
- свифтнумбер 
- свифтраутингнумбер 
- swift code 
- swift number # 
- swift routing number 
- bic number 
- bic code 
- БИК \# 
- БИК\# 
- bank identifier code 
- 標準化 9362 
- 迅速 # 
- свифтコード 
- свифт番号 
- 迅速なルーティング番号 
- бик番号 
- бикコード 
- 銀行識別コードのための国際組織 
- Organisation internationale de normalisation 9362 
- Быстрая \# 
- code SWIFT 
- le numéro de swift 
- swift numéro d'acheminement 
- le numéro BIC 
- \# БИК 
- code identificateur de banque 


## <a name="swiss-ssn-ahv-number"></a>Номер АХВа для швейцарского страхования

### <a name="format"></a>Format

13 цифра, цифра

### <a name="pattern"></a>Шаблон

13 цифра:

- три цифры — 756
- Необязательная точка
- четыре цифры
- Необязательная точка
- четыре цифры
- Необязательная точка
- две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_swiss_social_security_number_ahv находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keywords_swiss_social_security_number_ahv.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_swiss_social_security_number_ahv находит содержимое, которое соответствует шаблону;

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ахв
- SSN
- pid
- страховой номер
- персоналидно #
- social security number

- личный идентификационный номер
- персональный идентификационный номер
- инсуранцено #
- уникуеидно #
- уникальный идентификационный номер
- номер AVS
- личное удостоверение нет версичерунгснуммер
- идентификатионснуммер
- еинзигартиже идентитäт ничт
- созиалверсичерунгснуммер
- Идентификация персоннелле ID
- 
numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>Национальный идентификационный номер для Тайваня

### <a name="format"></a>Format

одна буква (на английском языке), за которой следуют девять цифр.

### <a name="pattern"></a>Шаблон

одна буква (на английском языке), за которой следуют девять цифр:
- одна буква (на английском языке, без учета регистра) 
- цифра "1" или "2" 
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_taiwanese_national_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_taiwanese_national_id;
- Контрольная сумма проходит проверку.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_taiwanese_national_id находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號 
- 身份證 
- 身份證號碼 
- 身份證號 
- 身分證字號 
- 身分證 
- 身分證號碼 
- 身份證號 
- 身分證統一編號 
- 國民身分證統一編號 
- 簽名 
- 蓋章 
- 簽名或蓋章 
- 簽章   
   
## <a name="taiwan-passport-number"></a>Номер паспорта для Тайваня

### <a name="format"></a>Format

- номер биометрического паспорта: девять цифр
- номер биометрической службы Passport: девять цифр

### <a name="pattern"></a>Шаблон
номер биометрического паспорта:
- символ "3" 
- восемь цифр

номер биометрической службы Passport:
- девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_taiwan_passport находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_taiwan_passport.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC passport number 
- Passport number 
- Passport no 
- Passport Num 
- Passport # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Номер сертификата резидента (ARC/TARC) для Тайваня

### <a name="format"></a>Format

десять букв и цифр

### <a name="pattern"></a>Шаблон

десять букв и цифр:
- две буквы (без учета регистра) 
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_taiwan_resident_certificate находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_taiwan_resident_certificate.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Resident Certificate 
- Resident Cert 
- Resident Cert. 
- Identification card 
- Alien Resident Certificate 
- ARC 
- Taiwan Area Resident Certificate 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>Код идентификации для тайского заполнения

### <a name="format"></a>Format

13 цифр.

### <a name="pattern"></a>Шаблон

13 цифр:
- Первая цифра не равна нулю или девять 
- 12 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_Thai_Citizen_Id находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keyword_Thai_Citizen_Id.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_Thai_Citizen_Id находит содержимое, которое соответствует шаблону;

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- ID Number
- Идентификационный номер
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>Турецкий национальный идентификационный номер

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_Turkish_National_Id находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово из Keyword_Turkish_National_Id.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_Turkish_National_Id находит содержимое, которое соответствует шаблону;

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Кимлик No
- TC Кимлик нумарасı
- Ватандаşлıк нумарасı
- Ватандаşлıк нет

## <a name="uk-drivers-license-number"></a>Королевств номер водительского удостоверения
Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации номера лицензии для драйвера ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

Сочетание 18 букв и цифр в указанном формате.

### <a name="pattern"></a>Шаблон

18 букв и цифр
- пять букв (без учета регистра) или цифра 9 вместо буквы 
- одна цифра 
- пять цифр в формате даты ММДДИ для даты рождения (седьмой символ увеличивается на 50, если драйвер — гнездо, то есть 51 – 62, а не с 01 – 12)
- две буквы (без учета регистра) или цифра "9" вместо буквы 
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_uk_drivers_license находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_uk_drivers_license;
- Контрольная сумма проходит проверку.

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- двла 
- light vans 
- куадбикес 
- motor cars 
- 125cc 
- сидекар 
- трициклес 
- моторциклес 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>Королевств номер рулона електорал

### <a name="format"></a>Format

две буквы, за которыми следуют 1-4 цифр.

### <a name="pattern"></a>Шаблон

две буквы (без учета регистра), за которыми следуют 1-4 номера

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_uk_electoral находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_uk_electoral.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>Королевств Национальный номер службы работоспособности

### <a name="format"></a>Format

10–17 цифр, разделенных пробелами.

### <a name="pattern"></a>Шаблон

10-17 цифр
- либо три, либо десять цифр. 
- пробел 
- три цифры 
- пробел 
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_uk_nhs_number находит содержимое, которое соответствует шаблону.
- Верно одно из условий ниже:
    - найдено ключевое слово из Keyword_uk_nhs_number;
    - найдено ключевое слово из Keyword_uk_nhs_number1;
    - найдено ключевое слово из Keyword_uk_nhs_number_dob.
- Контрольная сумма проходит проверку.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords
   
#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service 
- NHS 
- health services authority 
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id 
- patient identification 
- patient no 
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- ГРУПП 
- доб 
- D. O. B 
- Date of Birth 
- Birth Date 
   
## <a name="uk-national-insurance-number-nino"></a>Королевств Национальный страховой номер (Нино)
Этот объект типа конфиденциальной информации включен в тип конфиденциальной конфиденциальной информации ЕС Идентификаитон и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

семь символов или девять символов, разделенных пробелами или тире

### <a name="pattern"></a>Шаблон

два возможных шаблона:

- две буквы (допустимые Нинос используют только определенные символы в этом префиксе, которые пропускаются при проверке этого шаблона; без учета регистра)
- шесть цифр
- "A", "B", "C", или "'D" (например, префикс, в суффиксе допускаются только определенные символы; без учета регистра)

OR

- две буквы
- пробел или тире
- две цифры
- пробел или тире
- две цифры
- пробел или тире
- две цифры
- пробел или тире
- значение "A", "B", "C" или "'D"

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_uk_nino находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_uk_nino.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_uk_nino находит содержимое, которое соответствует шаблону;
- ни одно ключевое слово из Keyword_uk_nino не находится.

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number

- national insurance contributions

- protection act
- страхования
- social security number

- insurance application

- medical application

- social insurance

- medical attention

- социальное обеспечение безопасности
- great britain

- Номер NI
- NI но.
- NI #
- NI #
- страхования #
- инсуранценумбер
- натионалинсуранце #
- натионалинсуранценумбер

    
## <a name="uk-tax-identification-number"></a>Королевств идентификационный номер налога
Этот объект типа конфиденциальной информации доступен только в типе конфиденциальной информации по идентификационному номеру Европейского налога ЕС.


### <a name="format"></a>Format

Уникальная справочная информация о налогоплательщиках (утр): 10 цифр без пробелов и разделителей
 
  
### <a name="pattern"></a>Шаблон

Уникальная справочная информация о налогоплательщиках (утр): 10 цифр

  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция  `Func_uk_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое слово FROM  `Keywords_uk_eu_tax_file_number` . 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- Налоговый номер
- Налоговый файл
- tax id

- Налоговый идентификатор
- идентификационный номер налога
- налог без #
- налог без
- Регистрационный номер налогоплательщика
- такси #
- таксидно #
- таксиднумбер #
- таксно #
- такснумбер #
- такснумбер
- Идентификатор Tin
- номер Tin
- ИНН #

## <a name="us-bank-account-number"></a>Номер банковского счета США

### <a name="format"></a>Format

8-17 цифр

### <a name="pattern"></a>Шаблон

8–17 последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- регулярное выражение Regex_usa_bank_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_usa_Bank_Account.

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account. 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 

## <a name="us-drivers-license-number"></a>Номер водительского удостоверения для драйвера США

### <a name="format"></a>Format

Зависит от штата.

### <a name="pattern"></a>Шаблон

зависит от штата — например, Нью Йорк:
- девять цифр, отформатированных как DDD DDD DDD, будут совпадают.
- девять цифр, такие как ццццццццц, не совпадают.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_[state_name]_drivers_license_name;
- обнаружено ключевое слово из списка Keyword_us_drivers_license.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_[state_name]_drivers_license_name;
- находится ключевое слово из Keyword_us_drivers_license_abbreviations.
- ни одно ключевое слово из Keyword_us_drivers_license не находится.

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL 
- БИБЛИОТЕК 
- кдл 
- кдлс 
- ID 
- Идентификаторы 
- DL # 
- БИБЛИОТЕК # 
- кдл # 
- кдлс # 
- КОДОВ #
- Идентификаторы # 
- ID number 
- ID numbers 
- лик 
- лик # 

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- дриверлик 
- дриверликс 
- дриверлиценсе 
- дриверлиценсес 
- Driver Lic 
- Driver Lics 
- Driver License 
- Driver Licenses 
- дриверслик 
- дриверсликс 
- дриверслиценсе 
- дриверслиценсес 
- Drivers Lic 
- Drivers Lics 
- Drivers License 
- Drivers Licenses 
- Driver ' LIC 
- Driver ' LICS 
- Driver ' License 
- Driver ' Licenses 
- Driver' Lic 
- Driver' Lics 
- Driver' License 
- Driver' Licenses
- дривер'слик 
- дривер'сликс 
- дривер'слиценсе 
- дривер'слиценсес 
- Driver's Lic 
- Driver's Lics 
- Driver's License 
- Driver's Licenses 
- identification number 
- identification numbers 
- identification # 
- id card 
- id cards 
- identification card 
- identification cards 
- дриверлик # 
- дриверликс # 
- дриверлиценсе # 
- дриверлиценсес # 
- Driver Lic# 
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- дриверслик # 
- дриверсликс # 
- дриверслиценсе # 
- дриверслиценсес # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Driver ' LIC # 
- Driver ' LICS # 
- Driver ' License # 
- Driver ' Licenses # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- дривер'слик # 
- дривер'сликс # 
- дривер'слиценсе # 
- дривер'слиценсес # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- id card# 
- id cards# 
- identification card# 
- identification cards# 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_ [state_name] _drivers_license_name

- сокращение состояния (например, "Москва") 
- имя состояния (например, "Нью-Йорк")

## <a name="us-individual-taxpayer-identification-number-itin"></a>Индивидуальный идентификационный номер налогоплательщика (SHAREPOINTВ) для США

### <a name="format"></a>Format

девять цифр, начинающиеся с цифры "9" и содержащие "7" или "8" в качестве четвертой цифры, при необходимости отформатированные с помощью пробелов или тире

### <a name="pattern"></a>Шаблон

форматируемые
- цифра "9" 
- две цифры 
- пробел или тире 
- "7" или "8" 
- цифра 
- пробел или тире 
- четыре цифры

неформатированные
- цифра "9" 
- две цифры 
- "7" или "8" 
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_formatted_itin находит содержимое, которое соответствует шаблону.
- Верно по меньшей мере одно из условий ниже:
    - найдено ключевое слово из Keyword_itin;
    - функция Func_us_address находит адрес в правильном формате;
    - функция Func_us_date находит дату в правильном формате.
    - найдено ключевое слово из Keyword_itin_collaborative.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_unformatted_itin находит содержимое, которое соответствует шаблону.
- Верно по меньшей мере одно из условий ниже:
    - найдено ключевое слово из Keyword_itin_collaborative;
    - функция Func_us_address находит адрес в правильном формате;
    - функция Func_us_date находит дату в правильном формате.

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_itin"></a>Keyword_itin

- дубликат 
- tax id 
- tax identification 
- SharePointв 
- SSN 
- ИНН 
- social security 
- tax payer 
- итинс 
- такси 
- individual taxpayer 

#### <a name="keyword_itin_collaborative"></a>Keyword_itin_collaborative

- Лицензия 
- DL 
- доб 
- Birthdate 
- Birthday 
- Date of Birth 

## <a name="us-social-security-number-ssn"></a>Номер социального страхования (SSN) США

### <a name="format"></a>Format

девять цифр, которые могут быть в форматированном или неформатированном шаблоне

> [!NOTE]
> Есть SSN выдан до середины 2011 г., он отличается строгим форматированием, при котором определенные части номера должны входить в указанные диапазоны (при этом нет контрольной суммы).

### <a name="pattern"></a>Шаблон

четыре функции ищут служб SSNs в четырех различных шаблонах:
- Func_ssn находит SSN со строгим форматированием с тире или пробелами, выданные до 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);
- Func_unformatted_ssn находит SSN со строгим форматированием, выданные до 2011 г. (без форматирования в виде девяти последовательных цифр — ццццццццц);
- Func_randomized_formatted_ssn находит SSN с тире или пробелами, выданные после 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);
- Func_randomized_unformatted_ssn находит SSN без форматирования в виде девяти последовательных цифр, выданные после 2011 г. (ццццццццц).

### <a name="checksum"></a>Контрольная сумма

Нет


### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_ssn находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_ssn.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_unformatted_ssn находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_ssn.

Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
- Функция Func_randomized_formatted_ssn находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_ssn.

Политика защиты от потери данных с вероятностью в 55 % верно обнаружила этот тип конфиденциальной информации, если в пределах ближайших 300 знаков:
- Функция Func_randomized_unformatted_ssn находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_ssn.


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ssn"></a>Keyword_ssn

- Номер адаптера SSA
- social security number
- социальное обеспечение безопасности #
- социальное обеспечение безопасности #
- социальное страхование нет
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN #
- НН #
- SSID
   
## <a name="us--uk-passport-number"></a>США/ВЕЛИКОБРИТАНИЯ passport number
Великобритания Объект типа конфиденциальной информации номера паспорта доступен в типе конфиденциальной информации номера паспорта ЕС и доступен как отдельный объект типа конфиденциальной информации.

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- функция Func_usa_uk_passport находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_passport.

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport# 
- Службу # 
- пасспортид 
- пасспортно 
- пасспортнумбер 
- パスポート 
- パスポート番号 
- パスポートのнум 
- パスポート # 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport# 
- пассепорт # 
- пассепортнон 
- Passeportn ° 

## <a name="ukraine-passport-domestic"></a>Украина Passport Россия

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение Regex_Ukraine_Passport_Domestic находит содержимое, которое соответствует шаблону.
- Найдено ключевое слово из Keyword_Ukraine_Passport_Domestic.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- паспорт "Украина"
- номер паспорта
- паспорт нет
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Украина Passport International

### <a name="format"></a>Format

буквенно-цифровой шаблон из восьми символов

### <a name="pattern"></a>Шаблон

8-значный буквенно-цифровой шаблон:
- две буквы или цифры
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение Regex_Ukraine_Passport_International находит содержимое, которое соответствует шаблону.
- Найдено ключевое слово из Keyword_Ukraine_Passport_International.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- паспорт "Украина"
- номер паспорта
- паспорт нет
- паспорт України
- номер паспорта
