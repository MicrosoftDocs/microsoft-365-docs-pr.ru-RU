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
description: Предотвращение потери данных (DLP) в Центре соответствия требованиям безопасности включает 80 типов конфиденциальной информации, готовых к использованию в политиках защиты от &amp; потери данных. В этой статье перечислены все эти типы конфиденциальной информации и показано, что политика DLP ищет при обнаружении каждого типа.
ms.openlocfilehash: 431349ffdfc1a9aa05d071ec5ef10d76919f7465
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094749"
---
# <a name="sensitive-information-type-entity-definitions"></a>Определения типов конфиденциальной информации

Предотвращение потери данных (DLP) в Центре соответствия требованиям включает множество типов конфиденциальной информации, готовых к использованию в политиках защиты от потери данных. В этой статье перечислены все эти типы конфиденциальной информации и показано, что политика DLP ищет при обнаружении каждого типа. Тип конфиденциальной информации определяется шаблоном, который можно идентифицировать регулярным выражением или функцией. Подтверждающее свидетельство, например ключевые слова и контрольные списки, можно использовать для идентификации типа конфиденциальной информации. Уровень вероятности и расположение слов и знаков также используются в процессе оценки.

Для типов конфиденциальной информации требуется одна из этих подписок:
- Microsoft 365 E3
- Microsoft 365 E5

Типы конфиденциальной информации используются в:

- [Политики защиты от потери данных](data-loss-prevention-policies.md) 
- [Метки конфиденциальности](sensitivity-labels.md)
- [Метки хранения](retention.md)
- [Соответствие требованиям к обмену данными](communication-compliance.md)
- [Политики автоматического маркировки](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="aba-routing-number"></a>Номер маршрутки ABA

### <a name="format"></a>Format

девять цифр, которые могут быть в форматированном или неформатированном шаблоне

### <a name="pattern"></a>Шаблон

Формат:
- четыре цифры, начиная с 0, 1, 2, 3, 6, 7 или 8
- дефис
- четыре цифры
- дефис
- цифра

Неформатированные: девять последовательных цифр, начиная с 0, 1, 2, 3, 6, 7 или 8 

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_aba_routing находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_ABA_Routing.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_aba_routing находит содержимое, которое соответствует шаблону;

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- aba #
- aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- routing #
- no routing
- номер маршрутной маршрутки
- routing transit number
- routing #
- RTN


## <a name="argentina-national-identity-dni-number"></a>Номер удостоверения личности (DNI) для Аргентины

### <a name="format"></a>Format

Восемь цифр с периодами или без них

### <a name="pattern"></a>Шаблон

Восемь цифр:
- две цифры
- необязательный период
- три цифры
- необязательный период
- три цифры

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- cedula 
- cédula 
- dni 
- documento nacional de identidad 
- documento número 
- documento numero 
- registro nacional de las personas 
- rnp 
   
## <a name="australia-bank-account-number"></a>Номер банковского счета для Австралии

### <a name="format"></a>Format

от шести до десяти цифр с номером филиала банковского состояния или без него

### <a name="pattern"></a>Шаблон

Номер учетной записи — от 6 до 10 цифр.

Номер филиала государственного банка Австралии
- три цифры 
- дефис 
- три цифры

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_australia_bank_account_number.
- регулярное выражение Regex_australia_bank_account_number_bsb находит содержимое, которое соответствует шаблону.

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

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
- овсяная

## <a name="australia-business-number"></a>Номер компании для Австралии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт


### <a name="format"></a>Format

11 цифр с необязательными делегаторами

### <a name="pattern"></a>Шаблон

11 цифр с необязательными делегаторами:

- две цифры
- необязательный дефис или пробел
- три цифры
- необязательный дефис или пробел
- три цифры
- необязательный дефис или пробел
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_australian_business_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_australian_business_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_australian_business_number находит содержимое, которое соответствует шаблону.

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
### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- australia business no
- бизнес-номер
- abn #
- businessid #
- business id
- abn
- businessno #

## <a name="australia-company-number"></a>Номер компании для Австралии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

девять цифр с делетерами

### <a name="pattern"></a>Шаблон

девять цифр с делетерами:

- три цифры
- пробел
- три цифры
- пробел
- три цифры


### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_Australian_Company_Number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_Australian_Company_Number.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_Australian_Company_Number находит содержимое, которое соответствует шаблону.

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
### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- can
- australia company no
- australia company no #
- номер компании в Австралии
- нет в австралийской компании
- нет в австралийской компании #
- номер компании в Австралии

## <a name="australia-drivers-license-number"></a>Номер водительского удостоверения для Австралии

### <a name="format"></a>Format

девять букв и цифр

### <a name="pattern"></a>Шаблон

девять букв и цифр: 

- две цифры или буквы (без чувствительность к буквам) 
- две цифры 
- пять цифр или букв (без чувствительность к буквам)

OR

- от одной до двух необязательных букв (без чувствительность к буквам); 
- от четырех до девяти цифр

OR

- девять цифр или букв (без чувствительность к буквам)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
- international driving permit
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'licence
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic #
- Driver'Lics #
- Driver'licence #
- Driver'Licences #
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences# 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Driver'ы License
- Driver'licenses
- Driver' License
- Driver' Licenses
- Driver'sLicense
- Driver'sLicenses
- Driver's License
- Driver's Licenses
- DriverLicense #
- DriverLicenses #
- Driver License#
- Driver Licenses#
- DriversLicense #
- DriversLicenses #
- Drivers License#
- Drivers Licenses#
- Driver'ы License #
- Driver'licenses #
- Driver' License#
- Driver' Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>Номер медицинской учетной записи для Австралии

### <a name="format"></a>Format

10–11 цифр.

### <a name="pattern"></a>Шаблон

10–11 цифр.
- 1-ая цифра находится в диапазоне от 2 до 6
- 9-ая цифра — это контрольная цифра
- 10-я цифра — это цифра проблемы
- 11-я цифра (необязательно) — это индивидуальный номер

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- 1

   
## <a name="australia-passport-number"></a>Номер паспорта гражданина Австралии

### <a name="format"></a>Format

Буква, за которой следуют семь цифр.

### <a name="pattern"></a>Шаблон

Буква (без чувствительность к букве), за которой следуют семь цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- регулярное выражение Regex_australia_passport_number находит содержимое, которое соответствует шаблону;
- Находится ключевое слово Keyword_passport или Keyword_australia_passport_number.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パкポ.
- パスポート＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- passport
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- visa
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>Номер налогового файла для Австралии

### <a name="format"></a>Format

от восьми до девяти цифр

### <a name="pattern"></a>Шаблон

От восьми до девяти цифр, как правило, представлены пробелами следующим образом:
- три цифры 
- дополнительное пространство 
- три цифры 
- дополнительное пространство 
- две-три цифры, где последняя цифра является провероной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- tfn

## <a name="austria-drivers-license-number"></a>Номер водительского удостоверения для Австрия

### <a name="format"></a>Format

восемь цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

восемь цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
  
- Регулярное выражение  `Regex_austria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_austria_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver s_license_number

- fuhrerschein
- fhrerschein
- Fhrerscheine
- Fhrerscheinnummer
- Fhrerscheinnummern

## <a name="austria-identity-card"></a>Удостоверение личности для Австрия
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

24-значное сочетание букв, цифр и специальных символов
  
### <a name="pattern"></a>Шаблон

24 символа:
  
-  22 буквы (без чувствительность к буквам), цифры, косые черты, косые черты или знаки плюса 
    
- две буквы (без чувствительность к буквам), цифры, косые черты, косая черта, знаки плюс или знаки равного знака
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
  
- Регулярное выражение  `Regex_austria_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_austria_eu_national_id_card` слово. 
   
```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- идентификациный номер
- national id
- personalausweis repubich österreich

## <a name="austria-passport-number"></a>Номер паспорта гражданина Австрия

### <a name="format"></a>Format

Одна буква, за которой следует необязательный пробел и семь цифр
  
### <a name="pattern"></a>Шаблон

Сочетание одной буквы, семи цифр и одного пробела:
  
- одна буква (без чувствительность к букве)
- одно пространство (необязательно)
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_austria_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_eu_passport_date1` ДД.ММ.YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_austria_eu_passport_number` найдено. 
    
```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepгsse


## <a name="austria-social-security-number"></a>Номер социального обеспечения для Австрия

### <a name="format"></a>Format

10 цифр в указанном формате
  
### <a name="pattern"></a>Шаблон

10 цифр:
  
- три цифры, соответствующие серийному номеру 
- одна контрольная цифра
- шесть цифр, соответствующие дате рождения (ДДММАЙ)
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_austria_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
- находится ключевое  `Keywords_austria_eu_ssn_or_equivalent` слово из. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_austria_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- ssn
- ehic number
- ehic no
- страховой код
- insurancecode #
- страховой номер
- insurance no
- kassennummer
- ungnkenversicherung
- socialsecurityno
- socialsecurityno #
- social security no
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- ssn #
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavpperanje

## <a name="austria-tax-identification-number"></a>Идентификационный номер налога для Австрия

### <a name="format"></a>Format

девять цифр с необязательным дефишем и косой чертой
  
### <a name="pattern"></a>Шаблон

девять цифр с необязательным дефишем и косой чертой:
  
- две цифры
- дефис (необязательно)
- три цифры
- косая черта (необязательно)
- четыре цифры
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_austria_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_austria_eu_tax_file_number` слово. 
    
Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_austria_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr.
- steuernummer
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- налоговый номер
 
## <a name="austria-value-added-tax"></a>Налог на добавленную стоимость для Австрия
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

11-символьный буквонумерный шаблон

### <a name="pattern"></a>Шаблон

11-символьный буквонумерный шаблон:

- A или a
- T или t
- Дополнительное пространство
- U или u
- дополнительное пространство
- две или три цифры
- дополнительное пространство
- четыре цифры
- дополнительное пространство
- одна или две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_Austria_Value_Added_Tax находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_Austria_Value_Added_Tax.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_Austria_Value_Added_Tax находит содержимое, которое соответствует шаблону.

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
### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- номер плательщика НДС
- vat #
- номер плательщика НДС
- vat no.
- vatno #
- номер налога на добавленную стоимость
- vat
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- идентификационный номер плательщика НДС
- atu number
- UID-номер


## <a name="azure-documentdb-auth-key"></a>Ключ проверки auth Azure DocumentDB

### <a name="format"></a>Format

Строка DocumentDb, за которой следуют символы и строки, описанные в шаблоне ниже.

### <a name="pattern"></a>Шаблон

- Строка DocumentDb
- Любое сочетание от 3 до 200 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- Больше символа (>), знака равного (=), кавычка (") или апостроф (')
- Любое сочетание 86 букв нижнего или верхнего регистра, цифр, косой черты (/) или знака плюса (+)
- Два знака равного (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение CEP_Regex_AzureDocumentDBAuthKey находит содержимое, которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Строка подключения к базе данных Azure IAAS и строка подключения Azure SQL Azure

### <a name="format"></a>Format

Строка "Server", "server" или "data source", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, включая строку "cloudapp.azure".<!--no-hyperlink-->com или cloudapp.azure.<!--no-hyperlink-->net" или "database.windows.<!--no-hyperlink-->net и строку "Password", "password" или "pwd".

### <a name="pattern"></a>Шаблон

- строка "Server", "server" или "data source"
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- любое сочетание от 1 до 200 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- Строка "cloudapp.azure.<!--no-hyperlink-->com, "cloudapp.azure.<!--no-hyperlink-->net или database.windows.<!--no-hyperlink-->net"
- любое сочетание от 1 до 300 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- строка "Password", "password" или "pwd"
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- один или несколько символов, которые не являются точками с запоем (;), кавычка (") или апостроф (')
- точка с зачетом (;), кавычка (") или апостроф (')

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение CEP_Regex_AzureConnectionString находит содержимое, которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Строка подключения Azure IoT

### <a name="format"></a>Format

Строка HostName, за которой следуют символы и строки, описанные в приведенном ниже шаблоне, включая строки "azure-devices".<!--no-hyperlink-->net" и "SharedAccessKey".

### <a name="pattern"></a>Шаблон

- строка "HostName"
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- любое сочетание от 1 до 200 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- строка "azure-devices.<!--no-hyperlink-->net"
- любое сочетание от 1 до 200 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- строка "SharedAccessKey"
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- любое сочетание 43 букв нижнего или верхнего регистра, цифр, косой черты (/) или знака плюса (+)
- знак равного (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение CEP_Regex_AzureIoTConnectionString находит содержимое, которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Пароль параметра публикации Azure

### <a name="format"></a>Format

Строка "userpwd=", за которой следует букво-цифровая строка.

### <a name="pattern"></a>Шаблон

- строка "userpwd="
- любая комбинация из 60 строчная букв или цифр
- кавычка ("")

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение CEP_Regex_AzurePublishSettingPasswords находит содержимое, которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не находит содержимое, которое соответствует шаблону.


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

### <a name="keywords"></a>Ключевые слова

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Строка подключения кэша Azure Redis

### <a name="format"></a>Format

Строка redis.cache.windows.<!--no-hyperlink-->net, за которыми следуют символы и строки, описанные в приведенной ниже схеме, включая строку "password" или "pwd".

### <a name="pattern"></a>Шаблон

- строка redis.cache.windows.<!--no-hyperlink-->net"
- любое сочетание от 1 до 200 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- строка "password" или "pwd"
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- любое сочетание 43 символов, которые являются буквами нижнего или верхнего регистра, цифрами, косой чертой (/) или знаком "плюс" (+)
- знак равного (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureRedisCacheConnectionString находит содержимое, которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>Format

Строка "sig", за которой следуют символы и строки, описанные в шаблоне ниже.

### <a name="pattern"></a>Шаблон

- строка "sig"
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- любое сочетание между 43–53 символами, которые являются буквами нижнего или верхнего регистра, цифрами или знаком процента (%)
- строка "%3d"
- любой символ, который не является буквой нижнего или верхнего регистра, цифрой или знаком процента (%)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение CEP_Regex_AzureSAS находит содержимое, которое соответствует шаблону.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Строка подключения к шине обслуживания Azure

### <a name="format"></a>Format

Строка "EndPoint", за которой следуют символы и строки, описанные в приведенной ниже схеме, включая строки "servicebus.windows".<!--no-hyperlink-->net" и "SharedAccesKey".

### <a name="pattern"></a>Шаблон

- строка "EndPoint"
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- любое сочетание от 1 до 200 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- строка "servicebus.windows.<!--no-hyperlink-->net"
- любое сочетание от 1 до 200 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- строка "SharedAccessKey"
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- любое сочетание 43 символов, которые являются буквами нижнего или верхнего регистра, цифрами, косой чертой (/) или знаком "плюс" (+)
- знак равного (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Регулярное выражение CEP_Regex_AzureServiceBusConnectionString находит содержимое, которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Ключ учетной записи хранения Azure

### <a name="format"></a>Format

Строка "DefaultEndpointsProtocol", за которой следуют символы и строки, описанные в приведенной ниже схеме, включая строку AccountKey.

### <a name="pattern"></a>Шаблон

- строка "DefaultEndpointsProtocol"
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- любое сочетание от 1 до 200 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- строка AccountKey
- от нуля до двух символов в белом пространстве
- знак равного (=)
- от нуля до двух символов в белом пространстве
- любое сочетание 86 символов, которые являются буквами нижнего или верхнего регистра, цифрами, косой чертой (/) или знаком "плюс" (+)
- два знака равного (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение CEP_Regex_AzureStorageAccountKey находит содержимое, которое соответствует шаблону.
- Регулярное выражение CEP_AzureEmulatorStorageAccountFilter не находит содержимое, которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

(Технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Ключ учетной записи хранилища Azure (универсальный)

### <a name="format"></a>Format

Любое сочетание 86 букв нижнего или верхнего регистра, цифр, косой черты (/) или знака плюса (+), предшествующего или за которым следуют символы, описанные в приведенном ниже шаблоне.

### <a name="pattern"></a>Шаблон

- от нуля до одного из символов больше чем (>), апострофа ('), знака равного (=), кавычка (") или знака числа (#)
- любое сочетание 86 символов, которые являются буквами нижнего или верхнего регистра, цифрами, косой чертой (/) или знаком "плюс" (+)
- два знака равного (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение CEP_Regex_AzureStorageAccountKeyGeneric находит содержимое, которое соответствует шаблону.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Номер водительского удостоверения для Бельгии

### <a name="format"></a>Format

10 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

10 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_belgium_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово `Keywords_eu_driver's_license_number` из или `Keywords_belgium_eu_driver's_license_number` найдено.
    
```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver s_license_number

- rijbewijs
- rijbewijsnummer
- fhrerschein
- fhrerscheinnummer
- füehrerscheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>Национальный номер для Бельгии

### <a name="format"></a>Format

11 цифр, а также необязательные селитари

### <a name="pattern"></a>Шаблон

11 цифр, а также разделители:
- шесть цифр и два необязательных периода в формате YY. MM.DD для даты рождения 
- Необязательный выбор точки, тире, пробела 
- три последовательной цифры (нечетные для самцов, даже для самок) 
- Необязательный выбор точки, тире, пробела 
- две контрольные цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_belgium_national_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_belgium_national_number;
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- bnn #
- bnn
- carte d'identité
- identifiant national
- identifiantnational #
- identificatie
- identification
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identity
- 2016
- national number
- national register
- nationalnumber #
- nationalnumber
- nif #
- nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- личный номер
- personalausweis
- personalidnumber #
- registratie
- registration
- registrationsnumme
- registrierung
- social security number
- ssn #
- ssn
- steuernummer
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="belgium-passport-number"></a>Номер паспорта гражданина Бельгии

### <a name="format"></a>Format

две буквы, за которыми следуют шесть цифр без пробелов или седиметров
  
### <a name="pattern"></a>Шаблон

две буквы, за которыми следуют шесть цифр
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

 Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_belgium_eu_passport_number` найдено. 
- Регулярное выражение `Regex_eu_passport_date2` находит дату в формате ДД ММ YY или ключевое слово из `Keywords_eu_passport_date` или `Keywords_belgium_eu_passport_number` найдено

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_belgium_eu_passport_number` найдено. 

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Карт-порт
- Livre Passeport
- Pass-Nr
- Passnummer
- reisepass kein


## <a name="belgium-value-added-tax-number"></a>Номер налога на добавленную стоимость в Бельгии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

12-символьный буквонумерный шаблон

### <a name="pattern"></a>Шаблон

12-символьный буквонумерный шаблон:

- буква B или b
- буква E или e
- цифра 0
- цифра от 1 до 9
- необязательная точка, дефис или пробел
- четыре цифры
- необязательная точка, дефис или пробел
- четыре цифры


### <a name="checksum"></a>Контрольная сумма

Да


### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_belgium_value_added_tax_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_belgium_value_added_tax_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_belgium_value_added_tax_number находит содержимое, которое соответствует шаблону.

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
### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- nº tva
- номер плательщика НДС
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- vat #


## <a name="brazil-cpf-number"></a>Номер CPF для Бразилии

### <a name="format"></a>Format

11 цифр, которые включают проверочную цифру и могут быть форматированными или неформатированными.

### <a name="pattern"></a>Шаблон

Формат:
- три цифры
- точка
- три цифры
- точка
- три цифры
- дефис
- две цифры, которые являются провероными цифрами

Неформатированные:
- 11 цифр, где две последние цифры — проверочные.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_brazil_cpf;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Идентификация
- Registration
- Доход
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 

   
## <a name="brazil-legal-entity-number-cnpj"></a>Номер юридического лица для Бразилии (CNPJ)

### <a name="format"></a>Format

14 цифр, которые включают регистрационный номер, номер филиала и проверочные цифры, а также разделители.

### <a name="pattern"></a>Шаблон

14 цифр, а также разделители:

- две цифры 
- точка 
- три цифры 
- точка 
- три цифры (эти первые восемь цифр являются регистрационным номером) 
- косая черта 
- четырехзначный номер филиала 
- дефис 
- две цифры, которые являются провероными цифрами

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_brazil_cnpj;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ-MF 
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
- CGC 
- Pessoa jurídica 
- Pessoas jurídicas 
- Situação cadastral 
- Inscrição 
- Empresa 

   
## <a name="brazil-national-identification-card-rg"></a>Национальный идентификационный номер для Бразилии (RG)

### <a name="format"></a>Format

Registro Geral (старый формат): девять цифр

Registro de Identidade (RIC) (новый формат): 11 цифр

### <a name="pattern"></a>Шаблон

Registro Geral (старый формат):
- две цифры 
- точка 
- три цифры 
- точка 
- три цифры 
- дефис 
- одна цифра, которая является провероной цифрой

Registro de Identidade (RIC) (новый формат):
- 10 цифр. 
- дефис 
- одна цифра, которая является провероной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_brazil_rg находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_brazil_rg;
- Контрольная сумма проходит проверку.


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- identity card
- national id 
- número de rregistro
- registro de Iidentidade 
- registro geral
- RG (это ключевое слово с чувствительностью к делу) 
- RIC (это ключевое слово с чувствительностью к делу) 


## <a name="bulgaria-drivers-license-number"></a>Номер водительского удостоверения для Болгарии

### <a name="format"></a>Format

девять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

девять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_bulgaria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_bulgaria_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>    
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Однородный номер для Болгарии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

10 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

10 цифр без пробелов и селитров
  
- шесть цифр, соответствующие дате рождения (YYMMDD) 
- две цифры, соответствующие порядку рождения
- одна цифра, соответствующая полу: четная цифра для самца и нечетная цифра для женщина
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_bulgaria_eu_national_id_card` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_bulgaria_eu_national_id_card` слово. 

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_bulgaria_eu_national_id_card` содержимое, которое соответствует шаблону. 
    
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn #
- bnn
- bucn #
- bucn
- edinenskihski nomer
- egn #
- egn
- identification number
- national id
- national number
- nationalnumber #
- nationalnumber
- личный ид
- personal no
- личный номер
- personalidnumber #
- social security number
- ssn #
- ssn
- uniform uniform id
- uniform uniform no
- однородный гражданский номер
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- уникальный номер гражданина
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- id
- ид
- униформ граждански не
- униформ граждански номер
- 000 000 #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Номер паспорта гражданина Болгарии

### <a name="format"></a>Format

девять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_bulgaria_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_eu_passport_date1` ДД.ММ.YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_bulgaria_eu_passport_number` найдено. 

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия

## <a name="canada-bank-account-number"></a>Номер банковского счета для Канады

### <a name="format"></a>Format

7 или 12 цифр

### <a name="pattern"></a>Шаблон

Номер банковского счета для Канады — 7 или 12 цифр.

Транзитный номер банковского счета в Канаде имеет указанный ниже формат.
- пять цифр 
- дефис 
- три цифры ИЛИ
- ноль "0" 
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_canada_bank_account_number.
- регулярное выражение Regex_canada_bank_account_transit_number находит содержимое, которое соответствует шаблону.

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

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

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- Аббревиатура провинции, например AB.
- Название провинции, например Альберта.

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'ы License
- Driver'licenses
- Driver'licence
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
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
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- identification 
- DL #
- DLS # 
- CDL # 
- CDLS # 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- Driver Lic#
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- Driver License# 
- Driver Licences# 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- DriversLicence # 
- DriversLicences # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Drivers Licence# 
- Drivers Licences# 
- Driver'Lic # 
- Driver'Lics # 
- Driver'ы License # 
- Driver'licenses # 
- Driver'licence # 
- Driver'Licences # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver' Licence# 
- Driver' Licences# 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- Driver's Licence# 
- Driver's Licences# 
- Permis de Conduire# 
- id # 
- ids # 
- idcard card# 
- idcard cards# 
- idcard # 
- identification card# 
- identification cards# 
- identification # 

   
## <a name="canada-health-service-number"></a>Номер службы здравоохранения для Канады

### <a name="format"></a>Format

 10 цифр.

### <a name="pattern"></a>Шаблон

10 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- 2016
- workers compensation
- disability

      
## <a name="canada-passport-number"></a>Номер паспорта гражданина Канады

### <a name="format"></a>Format

две буквы в верхнем регистре, за которыми следуют шесть цифр

### <a name="pattern"></a>Шаблон

две буквы в верхнем регистре, за которыми следуют шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- регулярное выражение Regex_canada_passport_number находит содержимое, которое соответствует шаблону;
- Находится ключевое слово Keyword_canada_passport_number или Keyword_passport.

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

### <a name="keywords"></a>Ключевые слова

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
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パкポ.
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

   
## <a name="canada-personal-health-identification-number-phin"></a>Персональный идентификационный номер медицинского удостоверения для Канады (PHIN)

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- регулярное выражение Regex_canada_phin находит содержимое, которое соответствует шаблону;
- Найдено по крайней мере два ключевых Keyword_canada_phin или Keyword_canada_provinces.

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

### <a name="keywords"></a>Ключевые слова

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

- Зуйкавут
- Канада
- Northwest Territories
- Канада
- British Columbia
- Алберта
- Саскачеван
- Манитоба
- Юйккон
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- Канада

   
## <a name="canada-social-insurance-number"></a>Номер социального страхования для Канады

### <a name="format"></a>Format

девять цифр с необязательными дефисами или пробелами

### <a name="pattern"></a>Шаблон

Формат:
- три цифры 
- дефис или пробел 
- три цифры 
- дефис или пробел 
- три цифры

Неформатированные: девять цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_canadian_sin находит содержимое, которое соответствует шаблону.
- Выполняются по меньшей мере два из таких условий:
    - найдено ключевое слово из Keyword_sin;
    - найдено ключевое слово из Keyword_sin_collaborative;
    - функция Func_eu_date находит дату в правильном формате.
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_sin"></a>Keyword_sin

- sin 
- social insurance 
- numero d'assurance sociale 
- sins 
- ssn 
- ssns 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- sin # 
- soc ins 
- social ins 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- DOB 
- Birthdate 
- Birthday 
- Date of Birth 

   
## <a name="chile-identity-card-number"></a>Номер удостоверения личности для Чили

### <a name="format"></a>Format

от семи до восьми цифр, а также делегировка контрольной цифры или буквы

### <a name="pattern"></a>Шаблон

семь–восемь цифр, а также делегаторы:
- одна–две цифры 
- необязательный период 
- три цифры 
- необязательный период 
- три цифры 
- тире 
- одна цифра или буква (без чувствительность к букве), которая является провероной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_chile_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_chile_id_card;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tributario
- RUN
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- RUN #
- RUT #
- nationaluniqueroleID #
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- Удостоверение для чилийского пользователя нет.
- Номер удостоверения для чилийского пользователя
- Чилийское удостоверение #
- Уникальный налоговый реестр
- Уникальная роль трибутаря
- Уникальная налоговая роль
- Уникальный трибутарный номер
- Уникальный номер для страны
- Уникальная роль для страны
- Национальные уникальные роли
- Удостоверение для Чили нет.
- Номер удостоверения для Чили
- Удостоверение чили #

   
## <a name="china-resident-identity-card-prc-number"></a>Номер удостоверения личности резидента Китая (КНР)

### <a name="format"></a>Format

18 цифр.

### <a name="pattern"></a>Шаблон

18 цифр:
- шесть цифр, которые являются кодом адреса 
- восемь цифр в виде YYYYMMDD, которые являются датой рождения 
- три цифры, которые являются кодом заказа 
- одна цифра, которая является провероной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_china_resident_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_china_resident_id;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Resident Identity Card 
- КНР 
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

От 14 до 16 цифр, которые могут быть отформатированы или неформатированы (dddddddd), и которые должны пройти проверку Luhn.

### <a name="pattern"></a>Шаблон

Сложный и надежный шаблон, который обнаруживает карточки от всех основных торговых марок по всему миру, включая Visa, MasterCard, Discover Card, JCB, American Express, карточки для карточек.

### <a name="checksum"></a>Контрольная сумма

Да (рассчитывается по алгоритму Луна).

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_credit_card находит содержимое, которое соответствует шаблону;
- Верно одно из условий ниже:
    - найдено ключевое слово из Keyword_cc_verification;
    - найдено ключевое слово из Keyword_cc_name;
    - функция Func_expiration_date находит дату в правильном формате.
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- card verification
- card identification number
- cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditprtenprüfnummer
- kreditprtenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- cod. seguranca
- cod. segurança
- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- transaction
- номер транзакции
- номер ссылки
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso
- Visa
- mastercard
- master card
- mc
- mastercards
- master cards
- diner's Club
- diners club
- док-1
- обнаружение
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- cc #
- cc#:
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- cardholder
- card holders
- cardholders
- check card
- checkcard
- check cards
- checkcards
- debit card
- debitcard
- debit cards
- debitcards
- atm card
- atmcard
- atm cards
- atmcards
- enroute
- en route
- card type
- Cardmember Acct
- учетная запись cardmember
- Cardno
- Корпоративная карточка
- Корпоративные карточки
- Тип карточки
- номер учетной записи карточки
- учетная запись участника карточки
- Cardmember Acct.
- card no.
- card no
- card number
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kredithabteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- n. carta
- n carta
- nr. carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- Нет. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº. do cartão
- no do cartão
- no do cartao
- Нет. do cartão
- Нет. do cartao
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカкド
- Visa カкド
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


## <a name="croatia-drivers-license-number"></a>Номер водительского удостоверения для Хорватии

### <a name="format"></a>Format

восемь цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

восемь цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
  
- Регулярное выражение  `Regex_croatia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово `Keywords_eu_driver's_license_number` из или `Keywords_croatia_eu_driver's_license_number` найдено. 

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver s_license_number

- vozazka dozvola
- vozazke dozvole


## <a name="croatia-identity-card-number"></a>Номер удостоверения личности для Хорватии
Этот объект типа конфиденциальной информации включается в тип конфиденциальной информации для национального идентификационных номеров ЕС. Он доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj graсана
- master citizen number
- nacionalni identifciocijski broj
- national identification number
- oib #
- oib
- osobna iskazвяз
- osobni id
- osobni identifskicijski broj
- персональный идентификационный номер
- broj
- ezni identifskicijski broj
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="croatia-passport-number"></a>Номер паспорта гражданина Хорватии

### <a name="format"></a>Format

девять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_croatia_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_eu_passport_date1` ДД.ММ.YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_croatia_eu_passport_number` найдено. 
    
```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice
   
## <a name="croatia-personal-identification-oib-number"></a>Индивидуальный идентификационный номер (OIB) для Хорватии

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр:
- 10 цифр. 
- окончательная цифра — это провероальная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;
- Находится ключевое слово из Keywords_croatia_eu_tax_file_number.
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj graсана
- master citizen number
- nacionalni identifciocijski broj
- national identification number
- oib #
- oib
- osobna iskazвяз
- osobni id
- osobni identifskicijski broj
- персональный идентификационный номер
- broj
- ezni identifskicijski broj
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="croatia-social-security-number-or-equivalent-identification"></a>Номер социального обеспечения хорватии или эквивалентная идентификация
Этот объект типа конфиденциальной информации доступен только в номере социального обеспечения ЕС или типе конфиденциальной информации эквивалентного ИД.

### <a name="format"></a>Format

11 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
- 10 цифр.
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция находит  `Func_croatia_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_croatia_eu_ssn_or_equivalent` слово. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция находит  `Func_croatia_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
    
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

- персональный идентификационный номер
- master citizen number
- national identification number
- social security number
- nationalnumber #
- ssn #
- ssn
- nationalnumber
- bnn #
- bnn
- личный номер
- personalidnumber #
- oib
- osobni identifskicijski broj

## <a name="cyprus-drivers-license-number"></a>Номер водительского удостоверения для Кипра

### <a name="format"></a>Format

12 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

12 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_cyprus_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_cyprus_eu_driver's_license_number` найдено.

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Удостоверение личности для Кипра
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

10 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

10 цифр. 
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_cyprus_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_cyprus_eu_national_id_card` слово. 
    
```xml 
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- id card number
- номер удостоверения личности
- kim kimti
- national identification number
- личный номер
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Номер паспорта гражданина Кипра

### <a name="format"></a>Format

одна буква, за которой следуют 6–8 цифр без пробелов или седиметров
  
### <a name="pattern"></a>Шаблон

одна буква, за которой следуют от шести до восьми цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_cyprus_eu_passport_number` найдено. 
- Регулярное выражение `Regex_cyprus_eu_passport_date` находит дату в формате ДД/ММ/YYYY или ключевое слово `Keywords_cyprus_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_cyprus_eu_passport_number` найдено.  
    
```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimlii
- pasaport numaras
- Pasaport no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- срок действия истекает
- выдан в


## <a name="cyprus-tax-identification-number"></a>Идентификационный номер налога на Кипре
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

восемь цифр и одна буква в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

восемь цифр и одна буква:
  
- "0" или "9"
- семь цифр
- одна буква (без чувствительность к букве)
    
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_cyprus_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_cyprus_eu_tax_file_number` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_cyprus_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id
- идентификационный код налога
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tic #
- tic
- tin id
- tin no
- tin #
- vergi kim kodu
- vergi kim kim де numaras
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Номер водительского удостоверения для Чешский

### <a name="format"></a>Format

две буквы, за которыми следуют шесть цифр
  
### <a name="pattern"></a>Шаблон

восемь букв и цифр:
  
- буква "E" (без чувствительность к букве)
- буква
- пробел (необязательно)
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_czech_republic_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_czech_republic_eu_driver's_license_number` найдено. 

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver s_license_number

- úidiúskú prúkaz
- idiiské prфикац
- íslo íidiíského príkakaka
- ísla íidiískích przkaz


## <a name="czech-passport-number"></a>Номер паспорта гражданина Чешский

### <a name="format"></a>Format

восемь цифр без пробелов или делегировок
  
### <a name="pattern"></a>Шаблон

восемь цифр без пробелов или делегировок
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_czech_republic_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_eu_passport_date1` ДД.ММ.YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_czech_republic_eu_passport_number` найдено. 
    
```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- íslo pasu
- cestovní pasu
- passeport no
- ísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="czech-personal-identity-number"></a>Номер личного удостоверения для чешских пользователей

### <a name="format"></a>Format

девять цифр с необязательной косой чертой (старый формат) 10 цифр с необязательной косой чертой (новый формат)

### <a name="pattern"></a>Шаблон

девять цифр (старый формат):
- шесть цифр, которые представляют дату рождения
- необязательная косая черта
- три цифры

10 цифр (новый формат):
- шесть цифр, которые представляют дату рождения
- необязательная косая черта 
- четыре цифры, где последняя цифра является провероной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:

- функция Func_czech_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_czech_id_card;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:

- Функция Func_czech_id_card_new_format находит содержимое, которое соответствует шаблону.
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
### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- birth number
- czech republic id
- czechidno #
- daíové ííslo
- identifííní ííslo
- identity no
- идентификациный номер
- identityno #
- identityno
- страховой номер
- national identification number
- nationalnumber #
- national number
- osobní ííslo
- personalidnumber #
- личный номер
- персональный идентификационный номер
- личный номер
- pid #
- pid
- pojiítíní ííslo
- r.
- rodne cislo
- rodné ííslo
- ssn
- ssn #
- social security number
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- уникальный идентификационный номер

## <a name="czech-social-security-number-or-equivalent-identification"></a>Номер социального обеспечения для Чешский или эквивалентная идентификация

Этот объект типа конфиденциальной информации доступен только в номере социального обеспечения ЕС или типе конфиденциальной информации эквивалентного ИД.

### <a name="format"></a>Format

10 цифр и знаки задней знаки в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

10 цифр и ответная знаки:
  
- шесть цифр, соответствующих дате рождения (YYMMDD): 
- замещенная на задний ряд
- три цифры, соответствующие серийному номеру, отделяя людей от одной и той же даты
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция находит  `Func_czech_republic_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_czech_republic_eu_ssn_or_equivalent` слово. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция находит  `Func_czech_republic_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

- birth number
- national identification number
- персональный идентификационный номер
- social security number
- nationalnumber #
- ssn #
- ssn
- national number
- личный номер
- personalidnumber #
- r.
- rodné ííslo
- rodne cislo

## <a name="denmark-drivers-license-number"></a>Номер водительского удостоверения для Дании

### <a name="format"></a>Format

восемь цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

восемь цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_denmark_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_denmark_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver s_license_number

- kгrekort
- kнеkortnummer


## <a name="denmark-passport-number"></a>Номер паспорта гражданина Дании

### <a name="format"></a>Format

девять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_denmark_eu_passport_number` найдено. 
- Регулярное выражение `Regex_eu_passport_date2` находит дату в формате ДД ММ YY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_denmark_eu_passport_number` найдено. 
    
```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="denmark-personal-identification-number"></a>Персональный идентификационный номер для Дании

### <a name="format"></a>Format

10 цифр, содержащих дефис.

### <a name="pattern"></a>Шаблон

10 цифр:
- шесть цифр в формате ДДММАЙ, которые являются датой рождения 
- дефис 
- четыре цифры, где последняя цифра является провероной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение Func_denmark_eu_tax_file_number находит содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_denmark_id;
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение Func_denmark_eu_tax_file_number находит содержимое, которое соответствует шаблону.
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- cpr
- cpr #
- gesundheitskarte nummer
- gesundheitsversicherungcherte nummer
- карточка состояния
- номер карты медицинской страхования
- номер медицинского страхования
- identification number
- identifikationsnummer
- identifikationsnummer #
- идентификациный номер
- kassennummer
- nationalid #
- nationalnumber #
- national number
- personalidnumber #
- personalidentityno #
- личный номер
- personnummer
- personnummer #
- reisekrankenversicherungschertenummer
- rejsesygesikringskort
- ssn
- ssn #
- id
- kode
- nummer
- доктенуммер
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- налоговый код
- карта медицинского страхования для путешествий
- uniqueidentityno #
- налоговый номер
- налоговый регистрационный номер
- tax id
- налоговый идентификационный номер
- ыd #
- taxnumber #
- tax no
- taxno #
- taxnumber
- tax identification no
- tin #
- аdno #
- ыdnumber #
- tax no #
- tin id
- tin no
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer

## <a name="denmark-social-security-number-or-equivalent-identification"></a>Номер социального обеспечения для Дании или эквивалентная идентификация
Этот объект типа конфиденциальной информации доступен только для номера социального обеспечения ЕС или типа конфиденциальной информации эквивалентного ИД.

### <a name="format"></a>Format

10 цифр и дефис в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

10 цифр и дефис:
  
- шесть цифр, соответствующие дате рождения (ДДММАЙ) 
- дефис
- четыре цифры, соответствующие последовательному номеру

### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция находит  `Func_denmark_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_denmark_eu_ssn_or_equivalent` слово. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция находит  `Func_denmark_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
    
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

- персональный идентификационный номер
- national identification number
- social security number
- nationalnumber #
- ssn #
- ssn
- national number
- личный номер
- personalidnumber #
- cpr-nummer
- personnummer

## <a name="drug-enforcement-agency-dea-number"></a>Номер агентства по правоохранительным органам (DEA)

### <a name="format"></a>Format

две буквы, за которыми следуют семь цифр

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.
- одна буква (без регистра) из этого набора возможных букв: abcdefghjklmnprstux, который является регистратором кода 
- одна буква (без регистра), которая является первой буквой фамилии регистратора или цифрой "9"
- семь цифр, последняя из которых является провероной.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_dea_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое `Keyword_dea_number` слово
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_dea_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- dea
- dea #
- администрирование принудительных органы
- агентство по правоохранительным органам


## <a name="estonia-drivers-license-number"></a>Номер водительского удостоверения для Эстонии

### <a name="format"></a>Format

две буквы, за которыми следуют шесть цифр
  
### <a name="pattern"></a>Шаблон

две буквы и шесть цифр:
  
- буквы "ET" (без чувствительность к буквам) 
- шесть цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_estonia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_estonia_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver s_license_number

-- permis de conduire
- juhilubade
- juhiloa number
- juhiluba


## <a name="estonia-personal-identification-code"></a>Персональный идентификационный код Для Эстонии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

11 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
- одна цифра, соответствующая полу и минуте рождения (нечетное число самца, четное число самка; 1-2: 19-й год; 3-4: 20-й год; 5-6: 21-й год)
- шесть цифр, соответствующие дате рождения (YYMMDD)
- три цифры, соответствующие серийному номеру, отделяющие пользователей от одной и той же даты
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_estonia_eu_national_id_card` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_estonia_eu_national_id_card` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_estonia_eu_national_id_card` содержимое, которое соответствует шаблону. 
    
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ik
- isikukood #
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- national number
- личный код
- личный номер
- персональный идентификационный код
- персональный идентификационный номер
- personalidnumber #
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="estonia-passport-number"></a>Номер паспорта гражданина Эстонии

### <a name="format"></a>Format

одна буква, за которой следуют семь цифр без пробелов или седиметров
  
### <a name="pattern"></a>Шаблон

одна буква, за которой следуют семь цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_estonia_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_eu_passport_date1` ДД.ММ.YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_estonia_eu_passport_number` найдено. 
    
```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi passi number passinumbrid document number document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="eu-debit-card-number"></a>Номер банковской карты для ЕС

### <a name="format"></a>Format

16 цифр.

### <a name="pattern"></a>Шаблон

Сложный и надежный шаблон

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number 
- card number 
- card no. 
- security number 
- cc # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- americanexpress 
- americano espresso 
- amex 
- atm card 
- atm cards 
- atm kaart 
- atmcard 
- atmcards 
- atmkaart 
- atmkaarten 
- bancontact 
- bank card 
- bankkaart 
- card holder 
- card holders 
- card num 
- card number 
- card numbers 
- card type 
- cardano numerico 
- cardholder 
- cardholders 
- cardnumber 
- cardnumbers 
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
- carteblanche 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- ccn 
- check card 
- check cards 
- checkcard
- checkcards 
- quekaart 
- cirrus 
- cirrus-edc-maestro 
- controlekaart 
- controlekaarten 
- credit card 
- credit cards 
- creditcard 
- creditcards 
- debetkaart 
- debetkaarten 
- debit card 
- debit cards 
- debitcard 
- debitcards 
- debito automatico 
- diners club 
- док-1 
- обнаружение 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- edc 
- eigentümername 
- european debit card 
- hoofdkaart 
- hoofdkaarten 
- in viaggio 
- japanese card bureau 
- japanse kaartdienst 
- jcb 
- kaart 
- kaart num 
- kaartaantal 
- kaartallenllen 
- kaarthouder 
- kaarthouders 
- karte  
- karteninhaber 
- karteninhabers
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten-nummer 
- kredithabteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- maestro 
- master card 
- master cards 
- mastercard 
- mastercards 
- mc 
- mister cash 
- n carta 
- carta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- Нет. de tarjeta 
- Нет. do cartao 
- Нет. do cartão 
- nr carta 
- nr. carta 
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
- nº. do cartão 
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
- 1 
- supporti di scheda 
- supporto di scheda 
- switch 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta no
- tarjetahabiente 
- tipo della scheda 
- ufficio giapponese della 
- scheda 
- v pay 
- v-pay 
- visa 
- visa plus 
- visa electron 
- visto 
- visum 
- vpay   

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica 
- cid 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- cod. seg 
- cod. seguranca 
- cod. segurança 
- cod. sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- cryptogram 
- cryptogramme 
- cv2 
- cvc 
- cvc2 
- cvn 
- cvv 
- cvv2 
- cód seguranca 
- cód segurança 
- cód. seguranca 
- cód. segurança 
- código 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft nr uit 
- issue no 
- issue number 
- kaartidentificatienummer 
- kreditprtenprufnummer 
- kreditprtenprüfnummer 
- kwestieaantal 
- Нет. dell'edizione 
- Нет. di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- scheda 
- numero di sicurezza 
- numero van veiligheid 
- numéro de sécurité 
- nº autorizzazione 
- número de verificação 
- perno il blocco 
- pin block 
- prufziffer 
- prüfziffer 
- security code 
- security no 
- security number 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- veiligheid nr 
- veilig иsaantal 
- veiligcodescode 
- veiligмеsnummer 
- verfalldatum 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf 
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
- espira 
- espira 
- exp date 
- exp datum 
- expiration 
- expire 
- истечении срока действия 
- истечение срока действия 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- gultigkeitsdatum 
- gültig bis 
- gültigkeitsdatum 
- la scadenza 
- scadenza 
- valable 
- validade 
- valido hasta 
- valor 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 


## <a name="eu-drivers-license-number"></a>Номер водительского удостоверения для ЕС

Эти сущности находятся в номере водительского удостоверения ЕС и являются типами конфиденциальной информации.

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
- [Мякременский](#luxemburg-drivers-license-number)
- [Мальта](#malta-drivers-license-number)
- [Нидерланды](#netherlands-drivers-license-number)
- [Польша](#poland-drivers-license-number) 
- [Португалия](#portugal-drivers-license-number)
- [Румыния](#romania-drivers-license-number)
- [Словакия](#slovakia-drivers-license-number)
- [Словения](#slovenia-drivers-license-number)
- [Испания](#spain-drivers-license-number)
- [Швеция](#sweden-drivers-license-number)
- [Сша](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Национальный идентификационный номер для ЕС

Эти сущности находятся в национальных идентификационных номерах ЕС и являются типами конфиденциальной информации.

- [Австрия](#austria-identity-card)
- [Бельгия](#belgium-national-number)
- [Болгария](#bulgaria-uniform-civil-number)
- [Хорватия](#croatia-identity-card-number)
- [Кипр](#cyprus-identity-card)
- [Чешский](#czech-personal-identity-number)
- [Дания](#denmark-personal-identification-number)
- [Эстония](#estonia-personal-identification-code)
- [Финляндия](#finland-national-id)
- [Франция](#france-national-id-card-cni)
- [Германия](#germany-identity-card-number)
- [Греция](#greece-national-id-card)
- [Венгрия](#hungary-personal-identification-number)
- [Ирландия](#ireland-personal-public-service-pps-number)
- [Италия](#italy-fiscal-code)
- [Латвия](#latvia-personal-code)
- [Литва](#lithuania-personal-code)
- [Мякременский](#luxemburg-national-identification-number-natural-persons)
- [Мальта](#malta-identity-card-number)
- [Нидерланды](#netherlands-citizens-service-bsn-number)
- [Польша](#poland-national-id-pesel)
- [Португалия](#portugal-citizen-card-number)
- [Румыния](#romania-personal-numeric-code-cnp)
- [Словакия](#slovakia-personal-number)
- [Словения](#slovenia-unique-master-citizen-number)
- [Испания](#spain-dni)
- [Сша](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>Номер паспорта гражданина ЕС 

Эти сущности имеют номер паспорта ЕС и являются типами конфиденциальной информации. Эти сущности находятся в пакете номеров паспортов ЕС.

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
- [Мякременский](#luxemburg-passport-number)
- [Мальта](#malta-passport-number)
- [Нидерланды](#netherlands-passport-number)
- [Польша](#poland-passport-number)
- [Португалия](#portugal-passport-number)
- [Румыния](#romania-passport-number)
- [Словакия](#slovakia-passport-number)
- [Словения](#slovenia-passport-number)
- [Испания](#spain-passport-number)
- [Швеция](#sweden-passport-number)
- [Сша](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Номер социального обеспечения ЕС или эквивалентная идентификация

Эти организации, которые находятся в номере социального обеспечения ЕС или эквивалентной идентификации и являются типами конфиденциальной информации.

- [Австрия](#austria-social-security-number)
- [Бельгия](#belgium-national-number)
- [Хорватия](#croatia-personal-identification-oib-number)
- [Чешский](#czech-personal-identity-number)
- [Дания](#denmark-personal-identification-number)
- [Финляндия](#finland-national-id)
- [Франция](#france-social-security-number-insee-or-equivalent-identification)
- [Германия](#germany-identity-card-number)
- [Греция](#greece-national-id-card)
- [Венгрия](#hungary-social-security-number-taj)
- [Португалия](#portugal-citizen-card-number)
- [Испания](#spain-social-security-number-ssn)
- [Швеция](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>Идентификационный номер налога для ЕС

Эти сущности находятся в типе конфиденциальной информации идентификационных номеров для идентификации налогов в ЕС.

- [Австрия](#austria-tax-identification-number)
- [Бельгия](#belgium-national-number)
- [Болгария](#bulgaria-uniform-civil-number)
- [Хорватия](#croatia-identity-card-number)
- [Кипр](#cyprus-tax-identification-number)
- [Чешский](#czech-personal-identity-number)
- [Дания](#denmark-personal-identification-number)
- [Эстония](#estonia-personal-identification-code)
- [Финляндия](#finland-national-id)
- [Франция](#france-tax-identification-number)
- [Германия](#germany-tax-identification-number)
- [Греция](#greece-tax-identification-number)
- [Венгрия](#hungary-tax-identification-number)
- [Ирландия](#ireland-personal-public-service-pps-number)
- [Италия](#italy-fiscal-code)
- [Латвия](#latvia-personal-code)
- [Литва](#lithuania-personal-code)
- [Мякременский](#luxemburg-national-identification-number-non-natural-persons)
- [Мальта](#malta-tax-identification-number)
- [Нидерланды](#netherlands-tax-identification-number)
- [Польша](#poland-tax-identification-number)
- [Португалия](#portugal-tax-identification-number)
- [Румыния](#romania-personal-numeric-code-cnp)
- [Словакия](#slovakia-personal-number)
- [Словения](#slovenia-tax-identification-number)
- [Испания](#spain-tax-identification-number)
- [Швеция](#sweden-tax-identification-number)
- [Сша](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Номер водительского удостоверения для Финляндии

### <a name="format"></a>Format

10 цифр, содержащих дефис.
  
### <a name="pattern"></a>Шаблон

10 цифр, содержащих дефис:
  
- шесть цифр 
- дефис
- три цифры 
- цифра или буква
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_finland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_finland_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Номер медицинского страхования для Финляндии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

20-значный номер

### <a name="pattern"></a>Шаблон

20-значный номер:

- 10 цифр — 8024680246
- необязательный пробел или дефис
- 10 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Regex Regex_Finland_European_Health_Insurance_Number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_Finland_European_Health_Insurance_Number.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandehicnumber #
- finska sjukförsökringskort
- карточка состояния
- карта медицинского страхования
- номер медицинского страхования
- hlsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsökring nummer
- sjukförsökringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>Национальный ИД Финляндии

### <a name="format"></a>Format

шесть цифр плюс символ, указывающий на время года, плюс три цифры плюс провероная цифра

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.
- шесть цифр в формате ДДММАЙ, которые являются датой рождения 
- маркер "-", "+" или "a" 
- трехзначный персональный идентификационный номер 
- цифра или буква (без чувствительность к делу), которая является проверокой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_finnish_national_id находит содержимое, которое соответствует шаблону
- находится ключевое слово из Keyword_finnish_national_id,
- контрольнаяума передается

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_finnish_national_id находит содержимое, которое соответствует шаблону
- контрольнаяума передается

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

### <a name="keywords"></a>Ключевые слова

- htutlaatuinen henkilökohtainen tunnus
- henkilkokohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id no
- id number
- identification number
- identitedent numero
- идентификациный номер
- idnumber
- kansallinen henkilötunnus
- kansaаsen henkilökortin
- national id card
- national id no.
- личный ид
- персональный код удостоверения
- personalidnumber #
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- tunnistenumero
- число tunnus
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Номер паспорта гражданина Финляндии

Этот объект типа конфиденциальной информации доступен в типе конфиденциальной информации номера паспорта ЕС и доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format
сочетание девяти букв и цифр.

### <a name="pattern"></a>Шаблон
сочетание из девяти букв и цифр:
- две буквы (без чувствительность к буквам) 
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- регулярное выражение Regex_finland_passport_number находит содержимое, которое соответствует шаблону;
- Находится ключевое слово Keywords_eu_passport_number_common или Keyword_finland_passport_number.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomaomaomaen passi
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- passi #
- passi number


## <a name="france-drivers-license-number"></a>Номер водительского удостоверения для Франции

Этот объект типа конфиденциальной информации доступен в типе конфиденциальной информации номера водительского удостоверения ЕС и доступен в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Format

12 цифр.

### <a name="pattern"></a>Шаблон

12 цифр с проверкой подлинности, чтобы избежать путаницы с похожими шаблонами, например французскими номерами телефонов.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_french_drivers_license находит содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_french_drivers_license.

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>Номер медицинского страхования для Франции
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

21-значный номер

### <a name="pattern"></a>Шаблон

21-значный номер:

- 10 цифр.
- дополнительное пространство
- 10 цифр.
- дополнительное пространство
- цифра


### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Regex Regex_France_Health_Insurance_Number находит содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_France_Health_Insurance_Number.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- страховая карта
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>Национальный удостоверение личности для Франции (CNI)

### <a name="format"></a>Format

12 цифр.

### <a name="pattern"></a>Шаблон

12 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- регулярное выражение Regex_france_cni находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_france_eu_national_id_card.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number
- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte bancaire
- national identification number
- national identity
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale

   
## <a name="france-passport-number"></a>Номер паспорта гражданина Франции
Этот объект типа конфиденциальной информации доступен в типе конфиденциальной информации номера паспорта ес. Он доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

девять цифр и букв

### <a name="pattern"></a>Шаблон

девять цифр и букв:
- две цифры 
- две буквы (без чувствительность к буквам) 
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パкポ.
- パスポート＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>Номер социального обеспечения для Франции (INSEE) или эквивалентная идентификация
Этот объект типа конфиденциальной информации включается в номер социального обеспечения ЕС и тип конфиденциальной информации эквивалентного ИД. Он доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

15 цифр.

### <a name="pattern"></a>Шаблон

Должен соответствовать одному из двух шаблонов:
- 13 цифр, за которыми следуют пробелы, за которыми следуют две цифры<br/>
или
- 15 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_fr_insee;
- Контрольная сумма проходит проверку.

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- insee
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- Нет. d'identité
- numero d'identite
- no d'identite
- Нет. d'identite
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

## <a name="france-tax-identification-number"></a>Идентификационный номер налога для Франции

### <a name="format"></a>Format

13 цифр.
  
### <a name="pattern"></a>Шаблон

13 цифр.
  
- Одна цифра, которая должна быть 0, 1, 2 или 3
- Одна цифра
- пробел (необязательно); 
- Две цифры 
- пробел (необязательно); 
- три цифры;  
- пробел (необязательно); 
- три цифры;  
- пробел (необязательно); 
- Три контрольных цифры 

  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_france_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_france_eu_tax_file_number` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_france_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="france-value-added-tax-number"></a>Номер налога на добавленную стоимость для Франции
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

13 символов букв и цифр

### <a name="pattern"></a>Шаблон

13 символов букв и цифр:

- две буквы — FR (без чувствительность к буквам)
- необязательный пробел или дефис
- две буквы или цифры
- дополнительное пространство, точка, дефис или запятая
- три цифры
- дополнительное пространство, точка, дефис или запятая
- три цифры
- дополнительное пространство, точка, дефис или запятая
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_france_value_added_tax_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_france_value_added_tax_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_france_value_added_tax_number находит содержимое, которое соответствует шаблону.

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
### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- номер плательщика НДС
- vat no
- vat #
- налог на добавленную стоимость
- siren identification no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>Номер водительского удостоверения для Германии

Этот объект типа конфиденциальной информации включается в тип конфиденциальной информации номера водительского удостоверения ДЛЯ ЕС. Он доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

сочетание 11 цифр и букв

### <a name="pattern"></a>Шаблон

11 цифр и букв (без чувствительность к буквам):
- цифра или буква 
- две цифры 
- шесть цифр или букв 
- цифра 
- цифра или буква

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_german_drivers_license находит содержимое, которое соответствует шаблону;
- найдено ключевое слово из Keyword_german_drivers_license_number;
- Контрольная сумма проходит проверку.

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- fhrerschein
- fuhrerschein
- fuehrerschein
- fhrerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- fhrerschein- 
- fuhrerschein- 
- fuehrerschein- 
- fhrerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- fhrerscheinnummerklasse
- fuhrerscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-fhrerschein
- nr-fuhrerschein
- nr-fuehrerschein
- no-fhrerschein
- no-fuhrerschein
- no-fuehrerschein
- n-fhrerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dlno


## <a name="germany-identity-card-number"></a>Номер удостоверения личности для Германии

### <a name="format"></a>Format

с 1 ноября 2010 г.: девять букв и цифр

с 1 апреля 1987 г. по 31 октября 2010 г.: 10 цифр

### <a name="pattern"></a>Шаблон

с 1 ноября 2010 г.:
- одна буква (без чувствительность к букве) 
- восемь цифр

с 1 апреля 1987 г. по 31 октября 2010 г.:
- 10 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- identification
- identifikation
- identifizierungsnummer
- identity card
- идентификациный номер
- id-nummer
- личный ид
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>Номер паспорта гражданина Германии

Этот объект типа конфиденциальной информации включается в тип конфиденциальной информации номера паспорта ес и доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

10 цифр или букв.

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.
- первый символ — это цифра или буква из этого набора (C, F, G, H, J, K) 
- три цифры 
- пять цифр или букв из этого набора (C, -H, J-N, P, R, T, V-Z) 
- цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_german_passport находит содержимое, которое соответствует шаблону;
- Ключевое слово `Keyword_german_passport` из или `Keywords_eu_passport_number_common` найдено.
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_german_passport_data находит содержимое, которое соответствует шаблону;
- Ключевое слово `Keyword_german_passport` из или `Keywords_eu_passport_number_common` найдено.
- Контрольная сумма проходит проверку.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepгsse
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers


## <a name="germany-tax-identification-number"></a>Идентификационный номер налога для Германии

### <a name="format"></a>Format

11 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

11 цифр.
  
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

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_germany_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_germany_eu_tax_file_number` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_germany_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- zinn #
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>Номер налога на добавленную стоимость в Германии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

11 символов букв и цифр

### <a name="pattern"></a>Шаблон

11-символьный буквонумерный шаблон:

- буква D или d
- буква E или e
- дополнительное пространство
- три цифры
- необязательный пробел или запятая
- три цифры
- необязательный пробел или запятая
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_germany_value_added_tax_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_germany_value_added_tax_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_germany_value_added_tax_number находит содержимое, которое соответствует шаблону.

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
### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- номер плательщика НДС
- vat no
- vat #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>Номер водительского удостоверения для Греция

Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации номера водительского удостоверения ЕС и доступен в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Format

девять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_greece_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_greece_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>Карточка национального удостоверения личности для Греция

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

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- регулярное выражение Regex_greece_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_greece_id_card.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- греческий ид
- греческий национальный ид
- греческий персональный id-карта
- греческий ид полиции
- identity card
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Номер паспорта гражданина Греция

### <a name="format"></a>Format

Две буквы, за которыми следуют семь цифр без пробелов или седиметров
  
### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_greece_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_greece_eu_passport_date` ДД MMM YY (пример — 28 августа 19) или находится ключевое слово `Keywords_greece_eu_passport_date`

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_greece_eu_passport_number` найдено. 
    
```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Номер социального обеспечения для Греция (AMKA)
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

Одиннадцати цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

- 6 цифр в качестве даты рождения YYMMDD
- 4 цифры
- проверяемая цифра
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_greece_eu_ssn` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_greece_eu_ssn_or_equivalent` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_greece_eu_ssn` содержимое, которое соответствует шаблону. 

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn #
- social security no
- socialsecurityno #
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Идентификационный номер налога для Греция
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

Девять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

Девять цифр.
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
  
- Регулярное выражение  `Regex_greece_eu_tax_file_number` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_greece_eu_tax_file_number` слово. 
    
```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm #
- afm
- a|a αριθμός
- aката
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- tax registry no
- налоговый номер реестра
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- tin id
- tin no
- tin #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Номер удостоверения личности в Гонконге (HKID)

### <a name="format"></a>Format

Сочетание 8–9 букв и чисел, а также необязательные скобки вокруг последнего символа.

### <a name="pattern"></a>Шаблон

Сочетание 8–9 букв:
- 1–2 буквы (без чувствительность к буквам) 
- шесть цифр;  
- последний символ (любая цифра или буква "A") является проверочной цифрой и заключен в скобки (необязательно).

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_hong_kong_id_card;
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- удостоверение личности в Гонконге
- HKIDC
- id card
- identity card
- удостоверение hk
- hong kong id
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

   
## <a name="hungary-drivers-license-number"></a>Номер водительского удостоверения для Венгрии

### <a name="format"></a>Format

Две буквы, за которыми следуют шесть цифр
  
### <a name="pattern"></a>Шаблон

Две буквы и шесть цифр:
  
- Две буквы (без чувствительность к буквам) 
- шесть цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
  
- Регулярное выражение  `Regex_hungary_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_hungary_eu_driver's_license_number` найдено. 
    
```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver s_license_number

- vezetoi engedely
- vezetфи engedély
- vezetфи engedélyek


## <a name="hungary-personal-identification-number"></a>Персональный идентификационный номер для Венгрии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

11 цифр.
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
- Одна цифра, соответствующая полу (1- и 2-женская, другая цифра также возможна для граждан, которые раньше 1900 г., или граждан с двойным паспортом) 
- Шесть цифр, соответствующих дате рождения (YYMMDD)
- Три цифры, соответствующие серийному номеру
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
  
- Функция находит  `Func_hungary_eu_national_id_card` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_hungary_eu_national_id_card` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
  
- Функция находит  `Func_hungary_eu_national_id_card` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id number
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>Номер паспорта гражданина Венгрии

### <a name="format"></a>Format

Две буквы, за которыми следуют шесть или семь цифр без пробелов или седиметров
  
### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют шесть или семь цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_hungary_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_hungary_eu_passport_date` ДД MMM/MMM YY (пример — 01 MÁR/MAR 12) или находится ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_hungary_eu_passport_number` найдено. 
    
```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám


## <a name="hungary-social-security-number-taj"></a>Номер социального обеспечения для Венгрии (TAJ)

### <a name="format"></a>Format

Девять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

Девять цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
  
- Функция находит  `Func_hungary_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_hungary_eu_ssn_or_equivalent` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
  
- Функция находит  `Func_hungary_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- венгерский номер социального обеспечения
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- taj
- taj #
- ssn
- ssn #
- social security no
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Идентификационный номер налога для Венгрии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

10 цифр без пробелов или селитров
  
### <a name="pattern"></a>Шаблон

10 цифр:
  
- Одна цифра, которая должна быть "8" 
- восемь цифр.
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
  
- Функция находит  `Func_hungary_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_hungary_eu_tax_file_number` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
  
- Функция находит  `Func_hungary_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- венгерский олово
- hungatiantin #
- tax authority no
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- номер плательщика НДС


## <a name="hungary-value-added-tax-number"></a>Номер налога на добавленную стоимость для Венгрии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

10 символов букв и цифр

### <a name="pattern"></a>Шаблон

10 символов букв и цифр:

- две буквы — HU или hu
- дополнительное пространство
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:

- Функция Func_hungarian_value_added_tax_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_hungarian_value_added_tax_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:

- Функция Func_hungarian_value_added_tax_number находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- vat
- номер налога на добавленную стоимость
- vat #
- vatno #
- hungarianvatno #
- tax no.
- налог на добавленную стоимость ( áfa)
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>Постоянный номер учетной записи Для Индии (PAN)

### <a name="format"></a>Format

10 букв или цифр.

### <a name="pattern"></a>Шаблон

10 букв или цифр:
- Три буквы (без чувствительность к буквам) 
- Буква в C, P, H, F, A, T, B, L, J, G (без чувствительность к букве)
- Буква
- Четыре цифры 
- Буква, которая является алфавитной провероной цифрой

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- регулярное выражение Regex_india_permanent_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_india_permanent_account_number;

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- регулярное выражение Regex_india_permanent_account_number находит содержимое, которое соответствует шаблону;


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number 
- PAN 
   
## <a name="india-unique-identification-aadhaar-number"></a>Уникальный идентификационный номер (Aadhaar) для Индии

### <a name="format"></a>Format

12 цифр, содержащих необязательные пробелы или тире.

### <a name="pattern"></a>Шаблон

12 цифр:
- Цифра, которая не является 0 или 1
- Три цифры 
- необязательный пробел или тире; 
- четыре цифры; 
- необязательный пробел или тире; 
- Последняя цифра, которая является провероной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_india_aadhaar находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_india_aadhar;
- Контрольная сумма проходит проверку.
- 
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:

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
### <a name="keywords"></a>Ключевые слова
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- aadhaar
- aadhar
- aadhar #
- uid
- आधार
- uidai
   
## <a name="indonesia-identity-card-ktp-number"></a>Номер удостоверения личности (KTP) для Индонезии

### <a name="format"></a>Format

16 цифр, содержащих необязательные точки.

### <a name="pattern"></a>Шаблон

16 цифр:
- две цифры (код провинции); 
- точка (необязательно); 
- две цифры (код округа или города); 
- две цифры (код района); 
- точка (необязательно); 
- Шесть цифр в формате ДДММАЙ, которые являются датой рождения 
- точка (необязательно); 
- четыре цифры.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:

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

### <a name="keywords"></a>Ключевые слова
   
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

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:

- функция Func_iban находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

Нет

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Международная классификация болезни (ICD-10-CM)

### <a name="format"></a>Format

Dictionary

### <a name="pattern"></a>Шаблон

Ключевое слово

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Находится ключевое слово из Dictionary_icd_10_updated.
- Находится ключевое слово из Dictionary_icd_10_codes.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Находится ключевое слово из Dictionary_icd_10_, обновленное.

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

### <a name="keywords"></a>Ключевые слова

Любой термин из словаря Dictionary_icd_10_updated ключевых слов, который основан на международной классификации "Болезни", "Десятая редакция", "Модификация" [(ICD-10-CM).](https://go.microsoft.com/fwlink/?linkid=852604) Этот тип ищет только термин, а не страховые коды.

Любой термин из словаря Dictionary_icd_10_codes ключевых слов, который основан на международной классификации "Болезни", "Десятая редакция", "Модификация" [(ICD-10-CM).](https://go.microsoft.com/fwlink/?linkid=852604) Этот тип ищет только страховые коды, а не описание.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Международная классификация болезни (ICD-9-CM)

### <a name="format"></a>Format

Dictionary

### <a name="pattern"></a>Шаблон

Ключевое слово

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Находится ключевое слово из Dictionary_icd_9_updated.
- Находится ключевое слово из Dictionary_icd_9_codes.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Находится ключевое слово из Dictionary_icd_9_updated.

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

### <a name="keywords"></a>Ключевые слова

Любой термин из словаря Dictionary_icd_9_updated ключевых слов, который основан на международной классификации", "Девятая редакция", "Модификация" [(ICD-9-CM).](https://go.microsoft.com/fwlink/?linkid=852605) Этот тип ищет только термин, а не страховые коды.

Любой термин из словаря Dictionary_icd_9_codes ключевых слов, который основан на международной классификации "Болезни", "Девятая редакция", "Модификация" [(ICD-9-CM).](https://go.microsoft.com/fwlink/?linkid=852605) Этот тип ищет только страховые коды, а не описание.

## <a name="ip-address"></a>IP-адрес

### <a name="format"></a>Format

#### <a name="ipv4"></a>IPv4:
Сложный шаблон, учитывая форматированные (периоды) и неформатированные (без периодов) версии IPv4-адресов

#### <a name="ipv6"></a>IPv6:
Сложный шаблон, который учитывает форматированные номера IPv6 (включая двоеточия)

### <a name="pattern"></a>Шаблон

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Для IPv6 политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP-адрес (это ключевое слово с чувствительностью к делу)
- ip address 
- ip addresses
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>Номер водительского удостоверения для Ирландии

### <a name="format"></a>Format

Шесть цифр, за которыми следуют четыре буквы
  
### <a name="pattern"></a>Шаблон

Шесть цифр и четыре буквы:
  
- Шесть цифр
- Четыре буквы (без чувствительность к буквам)
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
  
- Регулярное выражение  `Regex_ireland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_ireland_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Номер паспорта гражданина Ирландии

### <a name="format"></a>Format

Две буквы или цифры, за которыми следуют семь цифр без пробелов или делегировок
  
### <a name="pattern"></a>Шаблон

Две буквы или цифры, за которыми следуют семь цифр:
  
- Две цифры или буквы (без чувствительность к буквам)
- семь цифр.
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_ireland_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_ireland_eu_passport_date` ДД MMM/MMM ГГ ГГ (пример — 01 BEA/MAY 1988) или находится ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_ireland_eu_passport_number` найдено.
    
```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="ireland-personal-public-service-pps-number"></a>Номер личной службы (PPS) для Ирландии

### <a name="format"></a>Format

Старый формат (до 31 декабря 2012 г.):
- семь цифр, за которыми следуют 1–2 буквы 

Новый формат (1 января 2013 г. и после):
- семь цифр, за которыми следуют две буквы

### <a name="pattern"></a>Шаблон

Старый формат (до 31 декабря 2012 г.):
- семь цифр 
- от одной до двух букв (без чувствительность к буквам); 

Новый формат (1 января 2013 г. и после):
- семь цифр 
- буква (без регистрации буквы), которая является алфавитной провероной цифрой 
- Необязательная буква в диапазоне A-I или W

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_ireland_pps находит содержимое, которое соответствует шаблону;
- Находится ключевое слово из Keywords_ireland_eu_national_id_card.
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_ireland_pps находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- служба удостоверений клиентов
- identification number
- личный номер
- личный общедоступный номер службы
- personal service no
- phearsanta seirbhíse poiblí
- pps no
- PPS-номер
- pps num
- PPS service no
- ppsn
- ppsno #
- ppsno
- psp
- public service no
- publicserviceno #
- publicserviceno
- доход и номер социального страхования
- rsi no
- RSI-номер
- rsin
- клиент seirbhís aitheantais
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="israel-bank-account-number"></a>Номер банковского счета для Израиль

### <a name="format"></a>Format

13 цифр.

### <a name="pattern"></a>Шаблон

Формат:
- две цифры 
- тире 
- три цифры 
- тире 
- восемь цифр

Неформатированные:
- 	13 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number 
- Bank Account 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>Национальный идентификационный номер для Израиля

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber #
-   id number
-   identity no        
-   identitynumber #
-   идентификациный номер
-   многоядерный объект       
-   личный ид
-   уникальный ид  

   
## <a name="italy-drivers-license-number"></a>Номер водительского удостоверения для Италия

Этот объект типа конфиденциальной информации включен в тип конфиденциальной информации номера водительского удостоверения ЕС и доступен в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Format

сочетание из 10 букв и цифр.

### <a name="pattern"></a>Шаблон

сочетание из 10 букв и цифр:
- одна буква (без чувствительность к букве) 
- буква "A" или "V" (без чувствительность к букве) 
- семь цифр
- одна буква (без чувствительность к букве)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida 
- patente guida
- patenti di guida
- patenti guida

## <a name="italy-fiscal-code"></a>Финансовый код Для Италия
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

16-значное сочетание букв и цифр в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

16-значное сочетание букв и цифр:
- три буквы, соответствующие первым трем consonants в имени семейства
- три буквы, соответствующие первому, третьему и четвертому consonants в первом имени
- две цифры, соответствующие последним цифрам года рождения
- одна буква, соответствующая букве месяца рождения, — буквы используются в алфавитном порядке, но используются только буквы A к E, H, L, M, P, R to T (таким образом, январь A, а октябрь — R)
- две цифры, соответствующие дню месяца рождения, чтобы различать полы, 40 добавляется в день рождения для
- четыре цифры, соответствующие коду региона, определенному для страны, где был человек ( коды для внешних стран)
- одна цифра четности
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_italy_eu_national_id_card` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_italy_eu_national_id_card` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_italy_eu_national_id_card` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice fiscal
- codice fiscale
- codice id personale
- codice personale
- финансовый код
- numero certificato personale
- numero di identificone fiscale
- numero id personale
- numero personale
- личный номер сертификата
- личный код
- код личного кода
- личный номер
- personalcodeno #
- налоговый код
- tax id
- tax identification no
- налоговый идентификационный номер
- номер налогового удостоверения
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="italy-passport-number"></a>Номер паспорта гражданина Италия

### <a name="format"></a>Format

две буквы или цифры, за которыми следуют семь цифр без пробелов или делегировок
  
### <a name="pattern"></a>Шаблон

две буквы или цифры, за которыми следуют семь цифр:
  
- две цифры или буквы (без чувствительность к буквам)
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_italy_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_italy_eu_passport_date` ДД MMM/MMM ГГ ГГ (пример — 01 GEN/JAN 1988) или находится ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_italy_eu_passport_number` найдено. 
    
```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="italy-value-added-tax-number"></a>Номер налога на добавленную стоимость для Италия
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

13-символьный буквонумерный шаблон с необязательными делетерами

### <a name="pattern"></a>Шаблон

13 символов букв и цифр с необязательными разнородных символами:

- I или i
- T или t
- необязательное пространство, точка, дефис или запятая
- 11 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_italy_value_added_tax_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_italy_value_added_tax_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_italy_value_added_tax_number находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- номер плательщика НДС
- vat no
- vat #
- iva
- iva #


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

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_jp_bank_account находит содержимое, которое соответствует шаблону;
- Находится ключевое слово из Keyword_jp_bank_account.
- Верно одно из условий ниже:
- функция Func_jp_bank_account_branch_code находит содержимое, которое соответствует шаблону;
- найдено ключевое слово из Keyword_jp_bank_branch_code.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

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
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>Номер водительского удостоверения для Японии

### <a name="format"></a>Format

12 цифр.

### <a name="pattern"></a>Шаблон

12 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- срезы драйверов
- driverlicenses
- dl #
- dls #
- lic #
- lics #
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証no
- 運転免許no
- 免許証no
- 免許no
- 運転経歴証明書番号
- 運転経歴証明書
- 運転免許証No.
- 運転免許No.
- 免許証No.
- 免許No.
- 運転免許証 #
- 運転免許 #
- 免許証 #
- 免許 #


## <a name="japan-my-number---corporate"></a>Мой номер для Японии — корпоративный
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

13-значный номер

### <a name="pattern"></a>Шаблон

13-значный номер:

- одна цифра от одной до девяти
- 12 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_japanese_my_number_corporate находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_japanese_my_number_corporate.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_japanese_my_number_corporate находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

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


## <a name="japan-my-number---personal"></a>Мой номер для Японии — личный
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

12-значный номер

### <a name="pattern"></a>Шаблон

12-значный номер:

- четыре цифры
- дополнительное пространство, точка или дефис
- четыре цифры
- дополнительное пространство, точка или дефис
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_japanese_my_number_personal находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_japanese_my_number_personal.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_japanese_my_number_personal находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

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

   
## <a name="japan-passport-number"></a>Номер паспорта гражданина Японии

### <a name="format"></a>Format

две буквы, за которыми следуют семь цифр

### <a name="pattern"></a>Шаблон

две буквы (без чувствительность к буквам), за которыми следуют семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Passport
- Passport Number
- Passport No.
- Passport#
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パポ>.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Номер карты для проживания в Японии

### <a name="format"></a>Format

12 букв и цифр

### <a name="pattern"></a>Шаблон

12 букв и цифр:
- две буквы (без чувствительность к буквам)
- восемь цифр 
- две буквы (без чувствительность к буквам)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение Regex_jp_residence_card_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_jp_residence_card_number.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Номер карты для проживания
- Карты проживания нет
- Карточка для проживания #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>Номер регистрации резидента Японии

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

11 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証

   
## <a name="japan-social-insurance-number-sin"></a>Номер социального страхования для Японии (SIN)

### <a name="format"></a>Format

7–12 цифр.

### <a name="pattern"></a>Шаблон

7–12 цифр
- четыре цифры 
- дефис (необязательно) 
- шесть цифр ИЛИ
- 7–12 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_jp_sin находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_jp_sin.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 社会保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Номер водительского удостоверения для Латвии

### <a name="format"></a>Format

три буквы, за которыми следуют шесть цифр
  
### <a name="pattern"></a>Шаблон

три буквы и шесть цифр:
  
- три буквы (без чувствительность к буквам) 
- шесть цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_latvia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_latvia_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver s_license_number

- autovadja apliec
- autovadja apliecࡉ
- vadja apliec

## <a name="latvia-personal-code"></a>Персональный код для Латвии

### <a name="format"></a>Format

11 цифр и необязательный дефис
  
### <a name="pattern"></a>Шаблон

Старый формат

11 цифр и дефис:
  
- шесть цифр, соответствующие дате рождения (ДДММАЙ) 
- дефис
- одна цифра, соответствующая годовщине рождения ("0" для 19-го, "1" для 20-го и "2" для 21-го)
- четыре цифры, генерируемые случайным образом

Новый формат

11 цифр.

- Две цифры "32"
- девять цифр.
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция или  `Func_latvia_eu_national_id_card` regex находит `Regex_latvia_eu_national_id_card_new_format` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_latvia_eu_national_id_card` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция или  `Func_latvia_eu_national_id_card` regex находит `Regex_latvia_eu_national_id_card_new_format` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- административный номер
- a дейс n
- birth number
- номер гражданина
- number
- электронный номер переписи
- электронный номер
- финансовый код
- номер пользователя в сфере здравоохранения
- id #
- id-code
- identification number
- identifikjas nu nu
- id-number
- отдельный номер
- latvija a де aтхат
- nacionclais id
- national id
- national identifying number
- national identity number
- national insurance number
- national register number
- nodokokoka nu nu
- nodoku id
- nodoku identifik
- личный номер сертификата
- личный код
- код личного кода
- личный номер
- персональный идентификационный код
- личный идентификатор
- личный номер удостоверения
- личный номер
- личный числовой код
- personalcodeno #
- personas kods
- идентификационный код для пользователей
- общедоступный номер службы
- registration number
- revenue number
- social insurance number
- social security number
- налоговый код штата
- tax file number
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- номер голосуемого

## <a name="latvia-passport-number"></a>Номер паспорта гражданина Латвии

### <a name="format"></a>Format

две буквы или цифры, за которыми следуют семь цифр без пробелов или делегировок
  
### <a name="pattern"></a>Шаблон

две буквы или цифры, за которыми следуют семь цифр:
  
- две цифры или буквы (без чувствительность к буквам)
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_latvia_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_eu_passport_date1` ДД.ММ.YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_latvia_eu_passport_number` найдено. 
    
```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase nu nu
- pase nu nu
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="lithuania-drivers-license-number"></a>Номер водительского удостоверения для Литвы

### <a name="format"></a>Format

восемь цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

восемь цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_lithuania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_lithuania_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver s_license_number

- vairuotojo paymjimas
- vairuotojo paymjimo numeris
- vairuotojo paymjimo numeriai

## <a name="lithuania-personal-code"></a>Персональный код Для Литвы
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

11 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

11 цифр без пробелов и селитров:
  
- одна цифра (1–6), соответствующая полу и возрасту человека при рождения
- шесть цифр, соответствующие дате рождения (YYMMDD) 
- три цифры, соответствующие серийному номеру даты рождения
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_lithuania_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_lithuania_eu_tax_file_number` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_lithuania_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- citizen service number
- mokesвичi. id
- mokes трагик. identifmasvimas numeris
- mokes трагик. identifikavimo numeris
- mokesщуi. числи
- national identification number
- личный код
- личный числовой код
- numeris pilieio paslaugos
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- unlus identifikavimo kodas
- unlus identifikavimo numeris
- уникальный идентификационный номер
- уникальный идентификациный номер
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Номер паспорта гражданина Литвы

### <a name="format"></a>Format

восемь цифр или букв без пробелов или селитров
  
### <a name="pattern"></a>Шаблон

восемь цифр или букв (без чувствительность к буквам)
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_lithuania_eu_passport_number` найдено. 
- Регулярное выражение `Regex_eu_passport_date3` находит дату в формате ДД ММ YYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_lithuania_eu_passport_number` найдено. 
    
```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="luxemburg-drivers-license-number"></a>Номер водительского удостоверения Химмхета

### <a name="format"></a>Format

шесть цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

шесть цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_luxemburg_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_luxemburg_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver s_license_number

- fahrerlaubnis
- Fhrerschüin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Национальный идентификационный номер (естественные лица) для Нюксемнеса
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

13 цифр без пробелов или селитров
  
### <a name="pattern"></a>Шаблон

13 цифр:
  
- 11 цифр. 
- две контрольные цифры
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_luxemburg_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_luxemburg_eu_national_id_card` слово. 

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_luxemburg_eu_tax_file_number` содержимое, которое соответствует шаблону. 


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- отдельный код
- отдельный ид
- индивидуальная идентификация
- отдельное удостоверение
- numéro d'identification personnel
- личный ид
- личная идентификация
- личное удостоверение
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- уникальный ид
- уникальное удостоверение
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Номер паспорта Химмхета

### <a name="format"></a>Format

восемь цифр или букв без пробелов или селитров
  
### <a name="pattern"></a>Шаблон

восемь цифр или букв (без чувствительность к буквам)
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_luxemburg_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_luxemburg_eu_passport_number` найдено. 
- Регулярное выражение `Regex_eu_passport_date3` находит дату в формате ДД ММ YYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_luxemburg_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_luxemburg_eu_passport_number` найдено. 
    
```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- pass в Люксембурге
- passeport в Люксембурге
- паспорт люксембурга
- no de passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- passeport nombre
- reisepгsse
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Идентификационный номер национального идентификации для Нюмнеса (не является естественным лицом)

### <a name="format"></a>Format

11 цифр.
  
### <a name="pattern"></a>Шаблон

11 цифр.
  
- две цифры
- дополнительное пространство 
- три цифры 
- дополнительное пространство
- три цифры 
- дополнительное пространство
- две цифры
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_luxemburg_eu_tax_file_number_non_natural` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_luxemburg_eu_tax_file_number` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_luxemburg_eu_tax_file_number_non_natural` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité sociale
- étain non
- étain #
- identifiant d'impôt
- tax identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscaleois
- numéro d'identification fiscale
- social security
- sozialunterstzitzung
- sozialversécherung
- sozialversicherungsausweis
- steier id
- steier identifiertiounsnummer
- steier nummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Номер идентификационных карт для Малайзии

### <a name="format"></a>Format

12 цифр, содержащих необязательные дефисы.

### <a name="pattern"></a>Шаблон

12 цифр:
- шесть цифр в формате YYMMDD, которые являются датой рождения 
- Тире (необязательно) 
- двух буквный код места рождения 
- Тире (необязательно) 
- три случайные цифры 
- однозначный код пола

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- цифровая карточка приложения
- i/c
- i/c no
- ic
- ic no
- id card
- идентификация карточки
- identity card
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan malaysia
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- удостоверение личности в Малайзии
- удостоверение личности для малайзии
- nric
- личная идентификация

## <a name="malta-drivers-license-number"></a>Номер водительского удостоверения для Мальты

### <a name="format"></a>Format

Сочетание двух символов и шести цифр в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

сочетание двух символов и шести цифр:
  
- два символа (цифры или буквы без чувствительность к буквам)
- пробел (необязательно)
- три цифры
- пробел (необязательно)
- три цифры
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_malta_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_malta_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver s_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>Номер удостоверения личности для Мальты
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

семь цифр, за которыми следует одна буква
  
### <a name="pattern"></a>Шаблон

семь цифр, за которыми следует одна буква:
  
- семь цифр 
- одна буква в "M, G, A, P, L, H, B, Z" (без чувствительность к делу)
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_malta_eu_national_id_card` слово. 
    
Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- citizen service number
- id9-taxxa
- identifika numru tal-jett
- kodiċi numerali personali
- numru ta 'identifzzjoni personali
- numru ta 'identifzzjonident-taxxa
- numru ta 'identifzzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numruru-taxxa
- личный числовой код
- уникальный идентификационный номер
- уникальный идентификациный номер
- uniqueidentityno #


## <a name="malta-passport-number"></a>Номер паспорта гражданина Мальты

### <a name="format"></a>Format

семь цифр без пробелов или делегировок
  
### <a name="pattern"></a>Шаблон

семь цифр 
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_malta_eu_passport_number` найдено. 
- Найдено ключевое `Keywords_eu_passport_date` слово

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_malta_eu_passport_number` найдено. 
    
```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="malta-tax-identification-number"></a>Идентификационный номер налога на Мальте

### <a name="format"></a>Format

Для граждан Тайваня:
- семь цифр и одна буква в указанном шаблоне
  
Неконвионские граждане и подмайства:
- девять цифр
  
### <a name="pattern"></a>Шаблон

Граждане Тайваня: семь цифр и одна буква
  
- семь цифр 
- одна буква (без чувствительность к букве)
    
Нефрумовские граждане и сущностями, не относягими к сша: девять цифр
  
- девять цифр 
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Regex  `Regex_malta_eu_tax_file_number`  или `Regex_malta_eu_tax_file_number_non_maltese_national` находит содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_malta_eu_tax_file_number` слово. 
    
Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Regex  `Regex_malta_eu_tax_file_number` или `Regex_malta_eu_tax_file_number_non_maltese_national` находит содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- citizen service number
- id9-taxxa
- identifika numru tal-jett
- kodiċi numerali personali
- numru ta 'identifzzjoni personali
- numru ta 'identifzzjonident-taxxa
- numru ta 'identifzzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numruru-taxxa
- личный числовой код
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- уникальный идентификационный номер
- уникальный идентификациный номер
- uniqueidentityno #

## <a name="netherlands-citizens-service-bsn-number"></a>Номер службы гражданина Нидерландов (BSN)

### <a name="format"></a>Format

восемь или девять цифр, содержащих необязательные пробелы

### <a name="pattern"></a>Шаблон

восемь-девять цифр:
- три цифры 
- пробел (необязательно) 
- три цифры 
- пробел (необязательно) 
- две-три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_netherlands_bsn находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_netherlands_bsn;
- Контрольная сумма проходит проверку.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card
  
- bsn #
- bsn
- servicenummer
- citizen service number
- person number
- личный номер
- личный числовой код
- номер, связанный с человеком
- persoonlijk nummer
- persoonlijke numerieke code
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- social-fiscal number
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- уникальный идентификационный номер
- уникальный идентификациный номер
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Номер водительского удостоверения для Нидерландов

### <a name="format"></a>Format

десять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

десять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_netherlands_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_netherlands_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijцен
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Номер паспорта гражданина Нидерландов

### <a name="format"></a>Format

девять букв или цифр без пробелов или седиметров
  
### <a name="pattern"></a>Шаблон

девять букв или цифр
  
### <a name="checksum"></a>Контрольная сумма

неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_netherlands_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_netherlands_eu_passport_date` ДД MMM/MMM YYYY (пример — 26 MAA/MAR 2012)

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_netherlands_eu_passport_number` найдено. 
    
```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>Налоговый идентификационный номер для Нидерландов
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

девять цифр без пробелов или делегировок
  
### <a name="pattern"></a>Шаблон

девять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_netherlands_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_netherlands_eu_tax_file_number` слово. 
    
Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_netherlands_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- hollânske tax identification
- hulandes impuesto id number
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- идентификационный номер impuesto
- impuesto number
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- идентификация налогов в Нидерландах
- идентификация налогов в Нидерландах
- нидерланды, олово
- олово Нидерландов
- tax id
- tax identification no
- налоговый идентификационный номер
- tax identification tal
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- tax tal
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="netherlands-value-added-tax-number"></a>Номер налога на добавленную стоимость для Нидерландов
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

14-символьный буквонумерный шаблон

### <a name="pattern"></a>Шаблон

14-символьный буквонумерный шаблон:

- N или n
- L или l
- необязательное пространство, точка или дефис
- девять цифр
- необязательное пространство, точка или дефис
- B или b
- две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_netherlands_value_added_tax_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_netherlands_value_added_tax_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_netherlands_value_added_tax_number находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- номер плательщика НДС
- vat no
- vat #
- tax getal для wearde tafoege
- btw n уmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Номер банковского счета для Новой Зеландии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

От 14 до 16-значного шаблона с необязательными делегаторами

### <a name="pattern"></a>Шаблон

От 14 до 16-значного шаблона с необязательными делегаторами:

- две цифры
- необязательный дефис или пробел
- от трех до четырех цифр
- необязательный дефис или пробел
- семь цифр
- необязательный дефис или пробел
- две-три цифры
- дефис или пробел для параметров

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_new_zealand_bank_account_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_new_zealand_bank_account_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_new_zealand_bank_account_number находит содержимое, которое соответствует шаблону.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- bank account
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>Номер водительского удостоверения для Новой Зеландии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

восьми символьный букво-цифровая схема

### <a name="pattern"></a>Шаблон

восьми символьный букво-цифровая схема

- две буквы 
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_newzealand_driver_license_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_newzealand_driver_license_number.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_newzealand_driver_license_number находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- driver lic
- driver licence
- driver licences
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's licence
- driver's licences
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver licence #
- driver licences #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's licence #
- driver's licences #
- international driving permit
- international driving permits
- Связь автомобилей nz
- новая зеландия, автомобильная связь


## <a name="new-zealand-inland-revenue-number"></a>Номер выручки для новой Зеландии в стране
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

восемь или девять цифр с необязательными делегаторами

### <a name="pattern"></a>Шаблон

восемь или девять цифр с необязательными делегаторами

- две или три цифры
- необязательный пробел или дефис
- три цифры
- необязательный пробел или дефис
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_new_zealand_inland_revenue_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_new_zealand_inland_revenue_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_new_zealand_inland_revenue_number находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird no.
- ird no #
- nz ird
- новая Зеландия ird
- ird number
- inland revenue number


## <a name="new-zealand-ministry-of-health-number"></a>Министерство здравоохранения Новой Зеландии

### <a name="format"></a>Format

три буквы, пробел (необязательно) и четыре цифры

### <a name="pattern"></a>Шаблон

- три буквы (без чувствительность к буквам), кроме "I" и "O"
- пробел (необязательно) 
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_new_zealand_ministry_of_health_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_nz_terms;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_new_zealand_ministry_of_health_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- Новая Зеландия
- Здравоохранение
- обработка
- National Health Index Number
- nhi number
- nhi no.
- NHI #
- National Health Index No.
- National Health Index Id
- National Health Index #

## <a name="new-zealand-social-welfare-number"></a>Номер социальных сетей Новой Зеландии

Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять цифр

- три цифры
- необязательный дефис
- три цифры
- необязательный дефис
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_newzealand_social_welfare_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_newzealand_social_welfare_number.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_newzealand_social_welfare_number находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- social welfare #
- social welfare #
- social welfare No.
- номер социальных сетей
- swn #

   
## <a name="norway-identification-number"></a>Идентификационный номер для Норвегии

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр:
- шесть цифр в формате ДДММАЙ, которые являются датой рождения 
- трехзначный индивидуальный номер 
- две контрольные цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_norway_id_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_norway_id_number;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- Идентификация
- Personnummer
- Fфdselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>Единый многонамерный идентификационный номер для Филиппин

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

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID 
- UMID 
- Identity Card 
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>Номер водительского удостоверения для Польша

### <a name="format"></a>Format

14 цифр, содержащих 2 косой черты
  
### <a name="pattern"></a>Шаблон

14 цифр и 2 косой черты:
  
- пять цифр 
- косая черта
- две цифры
- косая черта
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_poland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_poland_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Удостоверение личности для Польша

### <a name="format"></a>Format

три буквы и шесть цифр

### <a name="pattern"></a>Шаблон

три буквы (без чувствительность к буквам), за которыми следуют шесть цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.

   
## <a name="poland-national-id-pesel"></a>Национальный ИД для Польша (PESEL)

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

- шесть цифр, представляющих дату рождения в формате YYMMDD
- четыре цифры
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_pesel_identification_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_pesel_identification_number;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_pesel_identification_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfcyjny
- pesel
- tosamoraswej

   
## <a name="poland-passport-number"></a>Номер паспорта гражданина Польша
Этот объект типа конфиденциальной информации включается в тип конфиденциальной информации номера паспорта ес. Он доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

две буквы и семь цифр

### <a name="pattern"></a>Шаблон

Две буквы (без чувствительность к буквам), за которыми следуют семь цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Numer paszportu
- Nr. Paszportu
- Paszport

## <a name="poland-regon-number"></a>Номер REGON для Польша
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

9-значный или 14-значный номер

### <a name="pattern"></a>Шаблон

девятизначное или 14-значное число:

- девять цифр или 
- девять цифр
- дефис
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_polish_regon_number находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_polish_regon_number.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_polish_regon_number находит содержимое, которое соответствует шаблону.

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
### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon id
- статистический номер
- статистический ид
- статистическая нет
- regon number
- regonid #
- regonno #
- company id
- companyid #
- companyidno #
- numer statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Налоговый идентификационный номер для Польша
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

11 цифр без пробелов или селитров
  
### <a name="pattern"></a>Шаблон

11 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_poland_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_poland_eu_tax_file_number` слово. 
    
  
```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip #
- nip
- numer identyfjicji podatkowej
- numeridentyfkocjipodatkowej #
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- vat id #
- vat id
- vat no
- номер плательщика НДС
- vatid #
- vatid
- vatno #
   

## <a name="portugal-citizen-card-number"></a>Номер карты гражданина Португалии

### <a name="format"></a>Format

восемь цифр

### <a name="pattern"></a>Шаблон

восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- de identidade
- cartão de cidadão
- citizen card
- номер документа
- documento de identificação
- id number
- identification no
- identification number
- identity card no
- номер удостоверения личности
- national id card
- nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- номер bi в Португалии


## <a name="portugal-drivers-license-number"></a>Номер водительского удостоверения для Португалии

### <a name="format"></a>Format

два шаблона: две буквы, за которыми следуют 5–8 цифр со специальными символами
  
### <a name="pattern"></a>Шаблон

Шаблон 1: две буквы, за которыми следуют 5/6 со специальными символами:
- Две буквы (без чувствительность к буквам)
- дефис;
- Пять или шесть цифр
- Пробел
- Одна цифра

Шаблон 2: одна буква, за которой следуют 6/8 цифр со специальными символами:
- Одна буква (без чувствительность к букве)
- дефис;
- Шесть или восемь цифр
- Пробел
- одна цифра.

    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_portugal_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_portugal_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver s_license_number

- cart де motor де motor де
- автомагистрали корзины
- cartita de habilitação
- cartita habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>Номер паспорта гражданина Португалии

### <a name="format"></a>Format

одна буква, за которой следуют шесть цифр без пробелов или седиметров
  
### <a name="pattern"></a>Шаблон

одна буква, за которой следуют шесть цифр:
  
- одна буква (без чувствительность к букве)
- шесть цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_portugal_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_eu_passport_date1` ДД.ММ.YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_portugal_eu_passport_number` найдено.
    
```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- португальский паспорт
- португальский порт
- португальский passaporte
- passaporte nº
- passeport n°
- números de passaporte
- португальские паспорта
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="portugal-tax-identification-number"></a>Идентификационный номер налога для Португалии

### <a name="format"></a>Format

девять цифр с необязательными пробелами
  
### <a name="pattern"></a>Шаблон

- три цифры
- дополнительное пространство
- три цифры
- дополнительное пространство
- три цифры
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_portugal_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_portugal_eu_tax_file_number` слово. 
    
Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_portugal_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf #
- cpf
- nif #
- nif
- número de identificação fisca
- numero fiscal
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="romania-drivers-license-number"></a>Номер водительского удостоверения в Румынии

### <a name="format"></a>Format

один символ, за которым следует восемь цифр
  
### <a name="pattern"></a>Шаблон

один символ, за которым следует восемь цифр:
- одна буква (без чувствительность к букве) или цифра 
- восемь цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_romania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_romania_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver s_license_number

- permis deягольник
- permisului deжегольник
- permisului
- permisele deремене
- permisele дейспер
- permis демилидер

## <a name="romania-personal-numeric-code-cnp"></a>Личный числовой код Румынии (CNP)
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

13 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

- одна цифра от 1 до 9
- шесть цифр, представляющих дату рождения (YYMMDD)
- две цифры, которые могут быть 01–52 или 99
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_romania_eu_national_id_card` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_romania_eu_national_id_card` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_romania_eu_national_id_card` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp #
- cnp
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscal nr #
- id-ul taxei
- страховой номер
- insurancenumber #
- national id #
- national id
- national identification number
- numфикr identificare personal
- num себя
- num он же личная unic
- numsridentitate #
- numsridentitate
- numrpersonalunic #
- numrpersonalunic
- numru de identificare fiscal
- numsrul de identificare fiscal
- личный числовой код
- pin #
- pin
- tax file no
- tax file number
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- уникальный идентификационный номер
- уникальный идентификациный номер
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Номер паспорта гражданина Румынии

### <a name="format"></a>Format

восемь или девять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

восемь или девять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_romania_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_romania_eu_passport_date` ДД MMM/MMM YY (пример: 01 FEB/FEB 10) или находится ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_romania_eu_passport_number` найдено. 
    
```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numsrul paулaportului numarul pasaportului numerele pasaportului Paулaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="russia-passport-number-domestic"></a>Внутренний номер паспорта гражданина России
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

10-значный номер

### <a name="pattern"></a>Шаблон

10-значный номер:

- две цифры
- необязательный пробел или дефис
- две цифры
- дополнительное пространство
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Regex Regex_Russian_Passport_Number_Domestic находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_Russian_Passport_Number.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- passport number
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- 000 000 #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Международный номер паспорта гражданина России
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

девятизначный номер

### <a name="pattern"></a>Шаблон

девятизначный номер:

- две цифры
- необязательный пробел или дефис
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Regex Regex_Russian_Passport_Number_International находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_Russian_Passport_Number.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- passport number
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- 000 000 #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Национальный идентификатор для Саудовской Аравии

### <a name="format"></a>Format

10 цифр.

### <a name="pattern"></a>Шаблон

10 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Номер удостоверения личности для национальной регистрации Сингапура (NRIC)

### <a name="format"></a>Format

девять букв и цифр

### <a name="pattern"></a>Шаблон

- девять букв и цифр:
- буква "F", "G", "S" или "T" (без чувствительность к букве) 
- семь цифр 
- алфавитная проверочные цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_singapore_nric;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card 
- Identity Card Number 
- NRIC 
- IC 
- Foreign Identification Number 
- FIN 
- 身份证 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>Номер водительского удостоверения для Словакии

### <a name="format"></a>Format

один символ, за которым следует семь цифр
  
### <a name="pattern"></a>Шаблон

один символ, за которым следует семь цифр
  
- одна буква (без чувствительность к букве) или цифра
- семь цифр 
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_slovakia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_slovakia_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver s_license_number

- vodizski prezz
- vodiéské pre pre
- vodiированнаяského preтхо
- vodizskch preovzov

## <a name="slovakia-personal-number"></a>Персональный номер для Словакии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

девять или десять цифр, содержащих необязательные знаки backslash
  
### <a name="pattern"></a>Шаблон

- шесть цифр, представляющих дату рождения
- необязательная косая черта (/)
- три цифры
- одна необязательная проверотельная цифра
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_slovakia_eu_national_id_card` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_slovakia_eu_national_id_card` слово. 
    
Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_slovakia_eu_national_id_card` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- birth number
- íslo národnej identifánej karty
- íslo obíianského preísí
- daíové ííslo
- id number
- identification no
- identification number
- identifááná karta á
- identifííné ííslo
- identity card no
- номер удостоверения личности
- národná identifááná znaáka á
- national number
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- r.
- rodne cislo
- rodné ííslo
- social security number
- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- tax file no
- tax file number
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="slovakia-passport-number"></a>Номер паспорта гражданина Словакии

### <a name="format"></a>Format

одна цифра или буква, за которой следуют семь цифр без пробелов или седиметров
  
### <a name="pattern"></a>Шаблон

одна цифра или буква (без чувствительность к букве), за которой следуют семь цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_slovakia_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_eu_passport_date1` ДД.ММ.YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_slovakia_eu_passport_number` найдено. 
    
```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- íslo pasu
- ísla pasov
- pas i.
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="slovenia-drivers-license-number"></a>Номер водительского удостоверения для Словении

### <a name="format"></a>Format

девять цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

девять цифр
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_slovenia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_slovenia_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver s_license_number

- vozniko dovoljenje
- лицензия voznizka ztevilka
- voznihkih dovoljenj
- ztevilka voznizkega dovoljenja
- ztevilke voznihkih dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Уникальный номер гражданина Словении
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

13 цифр без пробелов или селитров
  
### <a name="pattern"></a>Шаблон

13 цифр в указанном шаблоне:
  
- семь цифр, соответствующих дате рождения (DDMMLLL), где "LLL" соответствует последним трем цифрам года рождения 
- две цифры, соответствующие области рождения "50"
- три цифры, соответствующие комбинации пола и серийного номера для людей, которые были в один день (000–499 для детей и 500–999 для детей)
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_slovenia_eu_national_id_card` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_slovenia_eu_national_id_card` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_slovenia_eu_national_id_card` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena гtevilka glavnega drjaavljana
- emфио
- enotna maticna otvilka obcana
- id card
- identification number
- identifskacijska текvilka
- identity card
- nacionalna id
- список потани nacionalni
- national id
- osebna izkazт
- osebni koda
- osebni ne
- osebni ebni ebvilka
- личный код
- личный номер
- личный числовой код
- гtevilka drjaavljana
- уникальный номер гражданина
- уникальный номер
- уникальный идентификациный номер
- уникальный номер гражданина
- уникальный регистрационный номер
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Номер паспорта гражданина Словении

### <a name="format"></a>Format

две буквы, за которыми следуют семь цифр без пробелов или седиметров
  
### <a name="pattern"></a>Шаблон

две буквы, за которыми следуют семь цифр:
  
- буква "P"
- одна буква в верхнем регистре
- семь цифр
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_slovenia_eu_passport_number` найдено. 
- Регулярное выражение находит дату в формате `Regex_eu_passport_date1` ДД.ММ.YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_slovenia_eu_passport_number` найдено. 
    
```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- гtevilka potnega lista
- potek veljavnosti
- список potni #
- datum rojstva
- список potni
- гtevilke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="slovenia-tax-identification-number"></a>Идентификационный номер налога для Словении
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

восемь цифр без пробелов или делегировок
  
### <a name="pattern"></a>Шаблон

- одна цифра от 1 до 9
- шесть цифр
- одна контрольная цифра
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_slovenia_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_slovenia_eu_tax_file_number` слово. 
    
Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_slovenia_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davчатая юттеносилка
- identifskacijska текvilka davka
- огтевилка davne datoatoatoe
- tax file no
- tax file number
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="south-africa-identification-number"></a>Идентификационный номер для Южной Африки

### <a name="format"></a>Format

13 цифр, которые могут содержать пробелы.

### <a name="pattern"></a>Шаблон

13 цифр:
- шесть цифр в формате YYMMDD, которые являются датой рождения 
- четыре цифры 
- индикатор гражданства из одной цифры 
- цифра "8" или "9" 
- одна цифра, которая является цифрой контрольной суммы

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- Идентификатор
- Идентификация 
   
## <a name="south-korea-resident-registration-number"></a>Регистрационный номер резидента Южной Кореи

### <a name="format"></a>Format

13 цифр, содержащих дефис.

### <a name="pattern"></a>Шаблон

13 цифр:
- шесть цифр в формате YYMMDD, которые являются датой рождения 
- дефис 
- одна цифра, определяемая возрастом и полом 
- четырехзначный код региона рождения 
- одна цифра, используемая для различения людей, для которых предыдущие числа идентичны 
- контрольная цифра.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_south_korea_resident_number;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card 
- Citizen's Registration Number 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Номер водительского удостоверения для Испании

### <a name="format"></a>Format

восемь цифр, за которыми следует один символ
  
### <a name="pattern"></a>Шаблон

восемь цифр, за которыми следует один символ:
  
- восемь цифр 
- одна цифра или буква (без чувствительность к букве)
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция или  `Func_spain_eu_DL_and_NI_number_citizen` находит `Func_spain_eu_DL_and_NI_number_foreigner` содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_spain_eu_driver's_license_number` найдено. 

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция или  `Func_spain_eu_DL_and_NI_number_citizen` находит `Func_spain_eu_DL_and_NI_number_foreigner` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver s_license_number

- permiso deóción
- permisoóón
- licencia de деакриб
- licencia
- permiso демикодировка
- permiso de деакриб
- permisos de деакриб
- permisos
- carnet демилиру
- carnet de деавия
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>DNI для Испании
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

восемь цифр, за которыми следует один символ
  
### <a name="pattern"></a>Шаблон

семь цифр, за которыми следует один символ
  
- восемь цифр
- Необязательный пробел или дефис
- одна контрольная буква (без чувствительность к букве)
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция или  `Func_spain_eu_DL_and_NI_number_citizen` находит `Func_spain_eu_DL_and_NI_number_foreigner` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_spain_eu_national_id_card"` слово. 

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция или  `Func_spain_eu_DL_and_NI_number_citizen` находит `Func_spain_eu_DL_and_NI_number_foreigner` содержимое, которое соответствует шаблону. 

    
```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni #
- dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- страховой номер
- national identification number
- national identity
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- персональный идентификационный номер
- личное удостоверение нет
- уникальный идентификациный номер
- uniqueid #

## <a name="spain-passport-number"></a>Номер паспорта гражданина Испании

### <a name="format"></a>Format

сочетание букв и чисел из восьми или девяти символов без пробелов или делений.
  
### <a name="pattern"></a>Шаблон

восьми- или девяти символьное сочетание букв и чисел:
  
- две цифры или буквы 
- одна цифра или буква (необязательно)
- шесть цифр
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение  `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_spain_eu_passport_number` найдено. 
- Регулярное выражение `Regex_spain_eu_passport_date` находит дату в формате ДД-ММ-YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_passport_number` из или `Keywords_spain_eu_passport_number` найдено.
    
```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- espa espa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- паспорт испании

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата проблемы
- дата окончания срока действия


## <a name="spain-social-security-number-ssn"></a>Номер социального обеспечения Испании (SSN)

Этот объект типа конфиденциальной информации включается в номер социального обеспечения ЕС или тип конфиденциальной информации эквивалентного ИД. Он доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

11–12 цифр.

### <a name="pattern"></a>Шаблон

11–12 цифр:
- две цифры 
- косая черта (необязательно) 
- семь-восемь цифр 
- косая черта (необязательно) 
- две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

Нет

## <a name="spain-tax-identification-number"></a>Идентификационный номер налога для Испании
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

семь или восемь цифр и одна или две буквы в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

Испанские персональные лица с национальные удостоверения личности для Испании:
  
- восемь цифр 
- одна буква в верхнем регистре (с чувствительностью к регистру) 
    
Нерезиденты без национального удостоверения личности для Испании
  
- одна буква в верхнем регистре "L" (с чувствительностью к регистру)
- семь цифр
- одна буква в верхнем регистре (с чувствительностью к регистру) 
    
Resident Resident Residents under the age of 14 years without a Spain National Identity Card:
  
- одна буква в верхнем регистре "K" (с чувствительностью к регистру)
- семь цифр 
- одна буква в верхнем регистре (с чувствительностью к регистру)
    
Подмена идентификационных номеров
  
- одна буква в верхнем регистре, которая является "X", "Y" или "Z" (с чувствительностью к регистру) 
- семь цифр
- одна буква в верхнем регистре (с чувствительностью к регистру) 
    
Подмены без идентификационных номеров
  
- одна буква в верхнем регистре с буквой "M" (с чувствительностью к регистру) 
- семь цифр
- одна буква в верхнем регистре (с чувствительностью к регистру) 
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция или  `Func_spain_eu_tax_file_number` находит `Func_spain_eu_DL_and_NI_number_citizen` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_spain_eu_tax_file_number` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция или  `Func_spain_eu_tax_file_number` находит `Func_spain_eu_DL_and_NI_number_citizen` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- cif
- cifid #
- cifnúmero #
- número de contribuyú
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- tax file no
- tax file number
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="sql-server-connection-string"></a>SQL Server подключения

### <a name="format"></a>Format

Строка "User Id", "User ID", "uid" или "UserId", за которой следуют символы и строки, описанные в шаблоне ниже.

### <a name="pattern"></a>Шаблон

- строка "User Id", "User ID", "uid" или "UserId"
- любое сочетание от 1 до 200 букв нижнего или верхнего регистра, цифр, символов, специальных символов или пробелов
- строка "Password" или "pwd", где "pwd" не предшествует строчная буква
- знак равного (=)
- любой символ, который не является знаком доллара ($), символом процента (%), больше символа (>), в символе (@), кавычках ("), точка с зазнаковкой (;), левая скобка ([) или левая скобка ({)
- любое сочетание 7–128 символов, которые не являются точками с за точками (;) косая черта (/) или кавычка ()
- точка с зачетом (;) или кавычка (")

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Регулярное выражение CEP_Regex_SQLServerConnectionString находит содержимое, которое соответствует шаблону.
- Ключевое слово из CEP_GlobalFilter не найдено.
- Регулярное выражение CEP_PasswordPlaceHolder не находит содержимое, которое соответствует шаблону.
- Регулярное выражение CEP_CommonExampleKeywords не находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- some-password
- somepassword
- secretPassword
- пример

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

(Обратите внимание, что технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- Пароль или пробелы, за которыми следуют 0-2 пробела, знаки равного (=), 0-2 пробела и звездочка (*) -OR-
- Пароль или pwd, за которым следует:
    - Знак равного (=)
    - Символ "Меньше символа" (<)
    - Любое сочетание из 1–200 символов, которые являются буквами верхнего или нижнего регистра, цифрами, звездочкой (*), дефисом (-), подчеркнутой (_) или символом белого пространства
    - Символ "Больше" (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Обратите внимание, что технически этот тип конфиденциальной информации идентифицирует эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>Номер водительского удостоверения для Швеции

### <a name="format"></a>Format

десять цифр, содержащих дефис
  
### <a name="pattern"></a>Шаблон

десять цифр, содержащих дефис:
  
- шесть цифр 
- дефис
- четыре цифры
    
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Регулярное выражение  `Regex_sweden_eu_driver's_license_number` находит содержимое, которое соответствует шаблону. 
- Ключевое слово  `Keywords_eu_driver's_license_number` из или `Keywords_sweden_eu_driver's_license_number` найдено. 
    
```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- срезы драйверов
- driver'slicence
- срезы драйверов
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- срезы драйверов #
- driver'slicence #
- срезы драйверов #
- driver's lic #
- driver's lics #
- driver's license #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- licen драйвера
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver s_license_number

- ajokortti
- permis deягольник
- ajokortin numero
- kuljjat lic.
- drivere lic.
- körkort
- numulurul permisului deлюсере
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>Национальный ИД Швеции

### <a name="format"></a>Format

10 или 12 цифр и дополнительный разделитель.

### <a name="pattern"></a>Шаблон

10 или 12 цифр с необязательным разделителем
- две цифры (необязательно) 
- Шесть цифр в формате даты ГГММДД. 
- либо "-" или "+" (необязательно)
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит `Func_swedish_national_identifier` содержимое, которое соответствует шаблону.
- Найдено ключевое `Keywords_swedish_national_identifier` слово
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит `Func_swedish_national_identifier` содержимое, которое соответствует шаблону.
- Контрольная сумма проходит проверку.


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id no
- id number
- id #
- identification no
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- документ удостоверения
- identity no
- идентификациный номер
- id-nummer
- личный ид
- personnummer #
- personnummer
- ikteidentifikationsnummer
   
## <a name="sweden-passport-number"></a>Номер паспорта гражданина Швеции
Этот объект типа конфиденциальной информации включается в тип конфиденциальной информации номера паспорта ес и доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

восемь цифр

### <a name="pattern"></a>Шаблон

восемь последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- регулярное выражение Regex_sweden_passport_number находит содержимое, которое соответствует шаблону.
- верно одно из следующих ок.
    - находится ключевое слово из Keyword_passport.
    - находится ключевое слово из Keyword_sweden_passport.

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

### <a name="keywords"></a>Ключевые слова
   
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
- Passport # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パкポ. 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport# 
- Passeport # 
- PasseportNon 
- Passeportn ° 

## <a name="sweden-social-security-number-or-equivalent-identification"></a>Номер социального обеспечения швеции или эквивалентная идентификация
Этот объект типа конфиденциальной информации доступен только в номере социального обеспечения ЕС или типе конфиденциальной информации эквивалентного ИД.

### <a name="format"></a>Format

12 цифр без пробелов и селитров
  
### <a name="pattern"></a>Шаблон

12 цифр:
  
- восемь цифр, соответствующих дате рождения (YYYYMMDD) 
- три цифры, соответствующие серийному номеру, где: 
  - Последняя цифра в серийном номере указывает пол по назначению нечетного номера для самца и четного номера для женщина
  - До 1990 г. назначение серийного номера соответствовало округу, в котором был замещетель номера. Или (если они были до 1947 г.), где они были, согласно налоговым записям, 1 января 1947 г. с особым кодом (обычно 9 в качестве седьмой цифры) для угона.
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция находит  `Func_sweden_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_sweden_eu_ssn_or_equivalent` слово. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
- Функция находит  `Func_sweden_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону. 
    
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

- личный номер
- identification number
- personal id no
- identity no
- identification no
- personal identification no
- personnummer id
- personligt id-nummer
- unikt id-nummer
- personnummer
- identifikationsnumret
- personnummer #
- identifikationsnumret #

## <a name="sweden-tax-identification-number"></a>Идентификационный номер налога для Швеции
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

10 цифр и символ в указанном шаблоне
  
### <a name="pattern"></a>Шаблон

10 цифр и символ:
  
- шесть цифр, соответствующие дате рождения (YYMMDD) 
- знак "плюс" или "минус"
- три цифры, которые делают идентификационный номер уникальным, где: 
  - для номеров, выдавшихся до 1990 г., седьмая и восьмая цифры определяют округ рождения или инородных людей
  - цифра в девятой позиции указывает пол по нечетным для самцов или даже для самцов
- одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция находит  `Func_sweden_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_sweden_eu_tax_file_number` слово. 
    
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_sweden_eu_tax_file_number` содержимое, которое соответствует шаблону. 
    
```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- личный номер
- personnummer
- nummer с ид
- dentifikation
- bettebetalarens identifikationsnummer
- sverige tin
- tax file
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый номер
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="swift-code"></a>Код SWIFT

### <a name="format"></a>Format

четыре буквы, за которыми следуют от 5 до 31 буквы или цифры

### <a name="pattern"></a>Шаблон

четыре буквы, за которыми следуют 5–31 буква или цифры:
- 4-буква банковского кода (без чувствительность к буквам) 
- дополнительное пространство 
- 4–28 букв или цифр (основной номер банковского счета, BBAN) 
- дополнительное пространство 
- от одной до трех букв или цифр (оставшаяся часть BBAN);

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова
   
#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362
- iso 9362
- iso9362
- swift #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic#
- bic #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFTコкド
- SWIFT番号
- BIC番号
- BICコкド
- SWIFT コкド
- SWIFT 番号
- BIC 番号
- BIC コド
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Номер ADV для SSN в Швейцарии
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

13-значный номер

### <a name="pattern"></a>Шаблон

13 цифр:

- три цифры — 756
- необязательная точка
- четыре цифры
- необязательная точка
- четыре цифры
- необязательная точка
- две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_swiss_social_security_number_ahv находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keywords_swiss_social_security_number_ahv.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_swiss_social_security_number_ahv находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- pid
- страховой номер
- personalidno #
- social security number
- личный номер
- персональный идентификационный номер нет.
- insuranceno #
- uniqueidno #
- уникальный идентификационный номер.
- avs number
- personal identity no versicherungsnummer
- identifikationsnummer
- einzigartige identitchtt nicht
- sozialversicherungsnummer
- идентификационный ид персонала
- numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>Национальный идентификационный номер для Тайваня

### <a name="format"></a>Format

одна буква (на английском языке), за которой следуют девять цифр

### <a name="pattern"></a>Шаблон

одна буква (на английском языке), за которой следуют девять цифр:
- одна буква (на английском языке без чувствительность к букве) 
- цифра "1" или "2" 
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_taiwanese_national_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_taiwanese_national_id;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

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
   
## <a name="taiwan-passport-number"></a>Номер паспорта гражданина Тайваня

### <a name="format"></a>Format

- биометрический номер паспорта: девять цифр
- не биометрический номер паспорта: девять цифр

### <a name="pattern"></a>Шаблон
биометрический номер паспорта:
- символ "3" 
- восемь цифр

не биометрический номер паспорта:
- девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC passport number 
- Passport number 
- Passport no 
- Passport Num 
- Passport # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Номер сертификата резидента Тайваня (ARC/TARC)

### <a name="format"></a>Format

10 букв и цифр.

### <a name="pattern"></a>Шаблон

10 букв и цифр:
- две буквы (без чувствительность к буквам) 
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

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

## <a name="thai-population-identification-code"></a>Идентификационный код для тайских пользователей

### <a name="format"></a>Format

13 цифр.

### <a name="pattern"></a>Шаблон

13 цифр:
- первая цифра не является нулем или девятью 
- 12 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_Thai_Citizen_Id находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_Thai_Citizen_Id.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_Thai_Citizen_Id находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- ID Number
- Идентификационный номер
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>Идентификационный номер гражданина Турецкий

### <a name="format"></a>Format

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_Turkish_National_Id находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_Turkish_National_Id.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_Turkish_National_Id находит содержимое, которое соответствует шаблону.

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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kim kim
- TC Kim numaras.
- Vatanda vat vatk numaras.
- Vatanda vat vatk no

## <a name="uk-drivers-license-number"></a>Сша номер водительского удостоверения
Этот объект типа конфиденциальной информации включается в тип конфиденциальной информации номера водительского удостоверения ДЛЯ ЕС. Он доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

Сочетание 18 букв и цифр в указанном формате.

### <a name="pattern"></a>Шаблон

18 букв и цифр
- Пять букв (без чувствительность к букве) или цифра "9" в качестве буквы. 
- Одна цифра.
- Пять цифр в формате даты MMDDY для даты рождения. Седьмый символ приращен на 50, если драйвер является женщина; для экзаменов: от 51 до 62, а не от 01 до 12.
- Две буквы (без чувствительность к букве) или цифра "9" в качестве буквы. 
- Пять цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- light vans 
- quadbikes 
- motor cars 
- 125cc 
- sidecar 
- трициклы 
- ы 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>Сша roll number

### <a name="format"></a>Format

две буквы, за которыми следуют 1–4 цифры

### <a name="pattern"></a>Шаблон

две буквы (без чувствительность к буквам), за которыми следуют 1-4 числа

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>Сша national health service number

### <a name="format"></a>Format

10–17 цифр, разделенных пробелами.

### <a name="pattern"></a>Шаблон

10-17 цифр
- 3 или 10 цифр 
- пробел 
- три цифры 
- пробел 
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова
   
#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service 
- nhs 
- health services authority 
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id 
- patient identification 
- patient no 
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP 
- DOB 
- D.O.B 
- Date of Birth 
- Birth Date 
   
## <a name="uk-national-insurance-number-nino"></a>Сша national insurance number (NINO)
Этот объект типа конфиденциальной информации включается в тип конфиденциальной информации для национального идентификационных номеров ЕС. Он доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

семь символов или девять символов, разделенных пробелами или тире

### <a name="pattern"></a>Шаблон

два возможных шаблона:

- две буквы (допустимые niNOs используют только определенные символы в этом префиксе, который проверяется этим шаблоном; без чувствительность к букве)
- шесть цифр
- либо "A", "B", "C", либо "D" (как и префикс, в суффиксе разрешены только определенные символы, без чувствительность к буквам)

OR

- две буквы
- пробел или тире
- две цифры
- пробел или тире
- две цифры
- пробел или тире
- две цифры
- пробел или тире
- "A", "B", "C" или "D"

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- функция Func_uk_nino находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_uk_nino.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_uk_nino находит содержимое, которое соответствует шаблону;

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- insurance
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- Номер ni
- NI No.
- NI #
- NI #
- insurance #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber

    
## <a name="uk-unique-taxpayer-reference-number"></a>Сша Уникальный справочный номер налогоплательщика
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

10 цифр без пробелов и селитров
 
  
### <a name="pattern"></a>Шаблон

10 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Нет
  
### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция находит  `Func_uk_eu_tax_file_number` содержимое, которое соответствует шаблону. 
- Найдено ключевое  `Keywords_uk_eu_tax_file_number` слово. 
    
```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- налоговый номер
- tax file
- tax id
- tax identification no
- налоговый идентификационный номер
- tax no #
- tax no
- налоговый регистрационный номер
- ыd #
- аdno #
- ыdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="us-bank-account-number"></a>Номер банковского счета в США

### <a name="format"></a>Format

6–17 цифр

### <a name="pattern"></a>Шаблон

6–17 последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

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

## <a name="us-drivers-license-number"></a>Номер водительского удостоверения для США

### <a name="format"></a>Format

Зависит от штата.

### <a name="pattern"></a>Шаблон

зависит от состояния , например Нью-Йорк:
- будут совпадать девять цифр в формате ddd ddd ddd.
- девять цифр, например ddddddddd, не будут совпадать.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_[state_name]_drivers_license_name;
- обнаружено ключевое слово из списка Keyword_us_drivers_license.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL 
- DLS 
- CDL 
- CDLS 
- Идентификатор 
- IDs 
- DL # 
- DLS # 
- CDL # 
- CDLS # 
- ID #
- IDs # 
- ID number 
- ID numbers 
- LIC 
- LIC # 

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- Driver Lic 
- Driver Lics 
- Driver License 
- Driver Licenses 
- DriversLic 
- DriversLics 
- DriversLicense 
- DriversLicenses 
- Drivers Lic 
- Drivers Lics 
- Drivers License 
- Drivers Licenses 
- Driver'Lic 
- Driver'Lics 
- Driver'ы License 
- Driver'licenses 
- Driver' Lic 
- Driver' Lics 
- Driver' License 
- Driver' Licenses
- Driver'sLic 
- Driver'sLics 
- Driver'sLicense 
- Driver'sLicenses 
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
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic# 
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Driver'Lic # 
- Driver'Lics # 
- Driver'ы License # 
- Driver'licenses # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- id card# 
- id cards# 
- identification card# 
- identification cards# 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- аббревиатура состояния (например, "NY") 
- название штата (например, "Нью-Йорк")

## <a name="us-individual-taxpayer-identification-number-itin"></a>Идентификационный номер налогоплательщика (ITIN) для США

### <a name="format"></a>Format

девять цифр, которые начинаются с "9" и содержат цифру "7" или "8" в качестве четвертой цифры, при желании отформатированные с пробелами или тире

### <a name="pattern"></a>Шаблон

отформатированный:
- цифра "9" 
- две цифры 
- пробел или тире 
- "7" или "8" 
- цифра 
- пробел или тире 
- четыре цифры

unformatted:
- цифра "9" 
- две цифры 
- "7" или "8" 
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_formatted_itin находит содержимое, которое соответствует шаблону.
- найдено ключевое слово из Keyword_itin;

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_unformatted_itin находит содержимое, которое соответствует шаблону.
- найдено ключевое слово из Keyword_itin;

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_formatted_itin или Func_unformatted_itin находит содержимое, которое соответствует шаблону.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_itin"></a>Keyword_itin

- налогоплательщик 
- tax id 
- tax identification 
- itin 
- i.t.i.n.
- ssn 
- tin 
- social security 
- tax payer 
- itins 
- ыd 
- individual taxpayer 


## <a name="us-social-security-number-ssn"></a>Номер социального обеспечения (SSN) для США

### <a name="format"></a>Format

девять цифр, которые могут быть в форматированном или неформатированном шаблоне

> [!NOTE]
> Есть SSN выдан до середины 2011 г., он отличается строгим форматированием, при котором определенные части номера должны входить в указанные диапазоны (при этом нет контрольной суммы).

### <a name="pattern"></a>Шаблон

четыре функции искать SSNs в четырех различных шаблонах:
- Func_ssn находит SSN со строгим форматированием с тире или пробелами, выданные до 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);
- Func_unformatted_ssn находит SSN со строгим форматированием, выданные до 2011 г. (без форматирования в виде девяти последовательных цифр — ццццццццц);
- Func_randomized_formatted_ssn находит SSN с тире или пробелами, выданные после 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);
- Func_randomized_unformatted_ssn находит SSN без форматирования в виде девяти последовательных цифр, выданные после 2011 г. (ццццццццц).

### <a name="checksum"></a>Контрольная сумма

Нет


### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
- Функция Func_ssn находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_ssn.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Функция Func_unformatted_ssn находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_ssn.

Политика DLP имеет низкую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в расположении с 300 символами:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_ssn"></a>Keyword_ssn

- Номер SSA
- social security number
- social security #
- social security #
- social security no
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN #
- SS #
- SSID
   
## <a name="us--uk-passport-number"></a>США и Сша passport number
Сша Объект типа конфиденциальной информации passport number доступен в типе конфиденциальной информации номера паспорта ЕС. Он доступен как автономный объект типа конфиденциальной информации.

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport# 
- Passport # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パкポ. 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport# 
- Passeport # 
- PasseportNon 
- Passeportn ° 

## <a name="ukraine-passport-domestic"></a>Внутренний паспорт гражданина Украины
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

девять цифр

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Regex Regex_Ukraine_Passport_Domestic находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_Ukraine_Passport_Domestic.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- паспорта гражданина Украины
- passport number
- passport no
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Паспорт гражданина Украины
Этот тип конфиденциальной информации доступен только в:
- политики защиты от потери данных
- политики соответствия коммуникациям
- управление информацией
- управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Format

восьми-символьный буквонумерный шаблон

### <a name="pattern"></a>Шаблон

восьми-символьный буквонумерный шаблон:
- две буквы или цифры
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в близости от 300 символов:
- Regex Regex_Ukraine_Passport_International находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_Ukraine_Passport_International.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- паспорта гражданина Украины
- passport number
- passport no
- паспорт України
- номер паспорта
