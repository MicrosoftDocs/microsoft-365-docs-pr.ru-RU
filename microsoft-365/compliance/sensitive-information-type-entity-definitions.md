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
recommendations: false
description: В политиках DLP можно использовать 200 типов конфиденциальной информации. В этой статье перечислены все эти типы конфиденциальной информации и показано, что ищет политика DLP при обнаружении каждого типа.
ms.openlocfilehash: 614649367e72766d8df210fccbb4e3cdc9cdb4b6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287471"
---
# <a name="sensitive-information-type-entity-definitions"></a>Определения типов конфиденциальной информации

В этой статье перечислены все определения типа конфиденциальной информации. Каждое определение показывает, что политика DLP ищет для обнаружения каждого типа. Дополнительные сведения о типах конфиденциальной информации см. [в](sensitive-information-type-learn-about.md)

## <a name="aba-routing-number"></a>Номер маршрутивки ABA

### <a name="format"></a>Формат

девять цифр, которые могут быть в форматированном или неформатированном шаблоне

### <a name="pattern"></a>Шаблон

- две цифры в диапазонах 00-12, 21-32, 61-72 или 80
- две цифры
- необязательный дефис
- четыре цифры
- необязательный дефис
- цифру


### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика имеет среднюю уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_aba_routing находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_ABA_Routing.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- банковские перенавязки #
- bankroutingnumber
- маршрутивка #
- маршрутику нет
- номер маршрутной маршрутки
- routing transit number
- маршрутивка #
- RTN


## <a name="argentina-national-identity-dni-number"></a>Номер национального удостоверения (DNI) Аргентины

### <a name="format"></a>Формат

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

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- нумеро documento
- registro nacional de las personas
- rnp

## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>Уникальный ключ идентификации налогов в Аргентине (CUIT/CUIL)

### <a name="format"></a>Формат

11 цифр с тире

### <a name="pattern"></a>Шаблон

11 цифр с тире:
- две цифры в 20, 23, 24, 27, 30, 33 или 34
- дефис (-)
- восемь цифр
- дефис (-)
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит `Func_Argentina_Unique_Tax_Key` содержимое, которое соответствует шаблону.
- Найдено ключевое `Keyword_Argentina_Unique_Tax_Key` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция находит `Func_Argentina_Unique_Tax_Key` содержимое, которое соответствует шаблону.

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- уникальный код идентификации труда 
- Clave Única de Identificación Tributaria
- уникальный код идентификации труда
- CUIL
- Уникальный ключ идентификации налогов
- Уникальный ключ идентификации рабочей силы
- Уникальный ключ идентификации труда
- Уникальный код идентификации работы
- Уникальный код идентификации работы
- Уникальный ключ идентификации работы
- Уникальный ключ идентификации работы
- Уникальный код налоговой идентификации
- Уникальный ключ налоговой идентификации
- Уникальный код идентификации труда
- Уникальный код идентификации труда
- Уникальный ключ идентификации труда
- Уникальный ключ идентификации труда
- налоговый ID
- taxID #
- taxId
- taxidnumber
- налоговый номер
- нет налога
- налог #
- налог #
- ID налогоплательщика
- номер налогоплательщика
- налогоплательщик нет
- налогоплательщик #
- налогоплательщик #
- удостоверение налога
- tax identification
- Número de Identificación Fiscal
- número de contribuyente


## <a name="australia-bank-account-number"></a>Номер банковского счета в Австралии

### <a name="format"></a>Формат

от шести до 10 цифр с номером филиала банковского филиала или без него

### <a name="pattern"></a>Шаблон

Номер учетной записи — от 6 до 10 цифр.

Номер филиала государственного банка Австралии
- три цифры
- дефис
- три цифры

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_australia_bank_account_number.
- регулярное выражение Regex_australia_bank_account_number_bsb находит содержимое, которое соответствует шаблону.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону.

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
- магатэ

## <a name="australia-business-number"></a>Номер бизнеса в Австралии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт


### <a name="format"></a>Формат

11 цифр с необязательными делимитерами

### <a name="pattern"></a>Шаблон

11 цифр с необязательными делимитерами:

- две цифры
- необязательный дефис или пространство
- три цифры
- необязательный дефис или пространство
- три цифры
- необязательный дефис или пространство
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_australian_business_number контента, который соответствует шаблону.
- Ключевое слово Keywords_australian_business_number найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_australian_business_number контента, который соответствует шаблону.

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

- Австралия бизнес нет
- номер бизнеса
- abn #
- businessid #
- бизнес-id
- abn
- businessno #

## <a name="australia-company-number"></a>Номер компании в Австралии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

девять цифр с делимитерами

### <a name="pattern"></a>Шаблон

девять цифр с делимитерами:

- три цифры
- пространство
- три цифры
- пространство
- три цифры


### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_Australian_Company_Number контента, который соответствует шаблону.
- Ключевое слово Keyword_Australian_Company_Number найдено.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_Australian_Company_Number контента, который соответствует шаблону.

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

- может
- Австралийская компания нет
- Австралийская компания нет #
- Номер австралийской компании
- Австралийская компания нет
- Австралийская компания нет #
- австралийский номер компании

## <a name="australia-drivers-license-number"></a>Номер лицензии водителя в Австралии

### <a name="format"></a>Формат

девять букв и цифр

### <a name="pattern"></a>Шаблон

девять букв и цифр:

- две цифры или буквы (не чувствительные к делу)
- две цифры
- пять цифр или букв (не чувствительных к делу)

ИЛИ

- от одного до двух необязательных букв (не чувствительных к делу)
- четыре-девять цифр

ИЛИ

- девять цифр или букв (не чувствительных к делу)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- Водительские права
- Водительские права
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
- Водительские права #
- Водительские права #
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
- Водительские права
- Водительские права
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
- Водительские права #
- Водительские права #
- Driver' License#
- Driver' Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#

## <a name="australia-medical-account-number"></a>Номер медицинской учетной записи Австралии

### <a name="format"></a>Формат

10–11 цифр.

### <a name="pattern"></a>Шаблон

10–11 цифр.
- Первая цифра находится в диапазоне 2–6.
- Девятая цифра — проверочная.
- Десятая цифра — цифра серии.
- Одиннадцатая цифра (необязательно) — индивидуальный номер.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- medicare


## <a name="australia-passport-number"></a>Номер паспорта Австралии

### <a name="format"></a>Формат

восемь или девять символов альфа-цифр

### <a name="pattern"></a>Шаблон

- одна буква (N, E, D, F, A, C, U, X) с семью цифрами или
- Две буквы (PA, PB, PC, PD, PE, PF, PU, PW, PX, PZ) с семью цифрами.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение `Regex_australia_passport_number` находит содержимое, которое соответствует шаблону.
- Найдено ключевое `Keyword_australia_passport_number` слово.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение `Regex_australia_passport_number` находит содержимое, которое соответствует шаблону.

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- national identity card
- travel document
- issuing authority


## <a name="australia-tax-file-number"></a>Номер налогового файла Австралии

### <a name="format"></a>Формат

восемь-девять цифр

### <a name="pattern"></a>Шаблон

от восьми до девяти цифр, обычно представленных с пробелами следующим образом:
- три цифры
- необязательный пробел
- три цифры
- необязательный пробел
- две-три цифры, где последняя цифра — это контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

## <a name="austria-drivers-license-number"></a>Номер водительских прав в Австрии

### <a name="format"></a>Формат

восемь цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

- Обычное выражение  `Regex_austria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_austria_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver s_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>Удостоверение личности в Австрии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

Сочетание букв, цифр и специальных символов с 24 символами

### <a name="pattern"></a>Шаблон

24 символа:

-  22 буквы (не чувствительные к делу), цифры, задние ресницы, косые черты или знаки плюс

- две буквы (не чувствительные к делу), цифры, backslashes, перенаправляющие черты, плюс знаки или равные знаки

### <a name="checksum"></a>Контрольная сумма

Неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

- Обычное выражение  `Regex_austria_eu_national_id_card` находит содержимое, которое соответствует шаблону.
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

- номер удостоверения
- national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>Номер паспорта Австрии

### <a name="format"></a>Формат

Одна буква с необязательным пространством и семью цифрами

### <a name="pattern"></a>Шаблон

Сочетание одной буквы, семи цифр и одного пространства:

- одна буква (не деликатная)
- одно пространство (необязательно)
- семь цифр

### <a name="checksum"></a>Контрольная сумма

неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_austria_eu_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_austria_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия

## <a name="austria-social-security-number"></a>Номер социального обеспечения в Австрии

### <a name="format"></a>Формат

10 цифр в указанном формате

### <a name="pattern"></a>Шаблон

10 цифр:

- три цифры, соответствующие серийному номеру
- одна контрольная цифра
- шесть цифр, соответствующих дате рождения (DDMMYY)

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_austria_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону.
- найдено  `Keywords_austria_eu_ssn_or_equivalent` ключевое слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

- austrian ssn
- номер ehic
- ehic нет
- код страхования
- страховой код #
- номер страховки
- страховки нет
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno #
- социального обеспечения нет
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
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>Идентификационный номер налога в Австрии

### <a name="format"></a>Формат

девять цифр с необязательными чертами дефиза и вперед

### <a name="pattern"></a>Шаблон

девять цифр с необязательными чертами дефиза и вперед:

- две цифры
- дефис (необязательный)
- три цифры
- косая черта (необязательный)
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_austria_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_austria_eu_tax_file_number` слово.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- налоговый номер

## <a name="austria-value-added-tax"></a>Налог на добавленную стоимость в Австрии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

Альфанумерный шаблон с 11-символами

### <a name="pattern"></a>Шаблон

11-символ альфанумерного шаблона:

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

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_Austria_Value_Added_Tax контента, который соответствует шаблону.
- Ключевое слово Keyword_Austria_Value_Added_Tax найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_Austria_Value_Added_Tax контента, который соответствует шаблону.

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

- номер НДС
- vat #
- австрийский номер НДС
- vat No.
- vatno #
- номер налога на добавленную стоимость
- австрийский НДС
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- идентификационный номер ндс
- atu number
- uid number


## <a name="azure-documentdb-auth-key"></a>Ключ auth Azure DocumentDB

### <a name="format"></a>Формат

Строка "DocumentDb" с символами и строками, описанными в приведенной ниже схеме.

### <a name="pattern"></a>Шаблон

- Строка "DocumentDb"
- Любое сочетание между 3-200 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- Больше символа (>), равного знака (=), кавычка (") или apostrophe (')
- Любое сочетание из 86 букв нижнего или верхнего шкафа, цифр, переназначений (/) или знака плюс (+)
- Два одинаковых знака (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение CEP_Regex_AzureDocumentDBAuthKey находит содержимое, которое соответствует шаблону.
- Обычное выражение CEP_CommonExampleKeywords не находит контент, который соответствует шаблону.

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

(Технически этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- тесты.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Строка подключения к базе данных Azure IAAS и строка SQL Azure

### <a name="format"></a>Формат

Строка "Server", "server" или "data source" с символами и строками, описанными в приведенном ниже шаблоне, включая строку "cloudapp.azure".<!--no-hyperlink-->com" или "cloudapp.azure.<!--no-hyperlink-->net" или "database.windows.<!--no-hyperlink-->net", а также строка "Пароль", "пароль" или "pwd".

### <a name="pattern"></a>Шаблон

- строка "Server", "server" или "источник данных"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- любое сочетание между 1-200 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- Строка "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net", или "database.windows.<!--no-hyperlink-->net"
- любое сочетание между 1-300 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- строка "Пароль", "пароль" или "pwd"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- один или несколько символов, которые не являются полуколоном (;), кавычка (") или апостроф (')
- полуколон (;), кавычка (") или апостроф (')

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Регулярное выражение CEP_Regex_AzureConnectionString находит содержимое, которое соответствует шаблону.
- Обычное выражение CEP_CommonExampleKeywords не находит контент, который соответствует шаблону.

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

(Технически этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- тесты.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Строка подключения к IoT Azure

### <a name="format"></a>Формат

Строка "HostName" с символами и строками, описанными в рисунке ниже, включая строки "azure-devices".<!--no-hyperlink-->net" и "SharedAccessKey".

### <a name="pattern"></a>Шаблон

- строка "HostName"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- любое сочетание между 1-200 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- строка "azure-devices.<!--no-hyperlink-->net"
- любое сочетание между 1-200 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- строка "SharedAccessKey"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- любое сочетание из 43 букв нижнего или верхнего шкафа, цифр, переназначений (/) или знака плюс (+)
- равный знак (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение CEP_Regex_AzureIoTConnectionString находит содержимое, которое соответствует шаблону.
- Обычное выражение CEP_CommonExampleKeywords не находит контент, который соответствует шаблону.

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

(Технически этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- тесты.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Пароль параметра публикации Azure

### <a name="format"></a>Формат

Строка "userpwd=" с последующим альфа-числом строка.

### <a name="pattern"></a>Шаблон

- строка "userpwd="
- любое сочетание из 60 нижних букв или цифр
- кавычка ()

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Регулярное выражение CEP_Regex_AzurePublishSettingPasswords находит содержимое, которое соответствует шаблону.
- Обычное выражение CEP_CommonExampleKeywords не находит контент, который соответствует шаблону.


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

(Технически этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- тесты.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Строка подключения кэша Azure Redis

### <a name="format"></a>Формат

Строка "redis.cache.windows.<!--no-hyperlink-->net" с символами и строками, описанными в приведенной ниже схеме, включая строку "пароль" или "pwd".

### <a name="pattern"></a>Шаблон

- строка "redis.cache.windows.<!--no-hyperlink-->net"
- любое сочетание между 1-200 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- строка "пароль" или "pwd"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- любое сочетание из 43 символов, которые являются буквами нижнего или верхнего шкафа, цифрами, переназначаемой чертой (/) или знаком плюс (+)
- равный знак (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение CEP_Regex_AzureRedisCacheConnectionString находит содержимое, которое соответствует шаблону.
- Обычное выражение CEP_CommonExampleKeywords не находит контент, который соответствует шаблону.

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

(Технически этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- тесты.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>Формат

Строка "sig" с символами и строками, описанными в рисунке ниже.

### <a name="pattern"></a>Шаблон

- строка "sig"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- любое сочетание между 43-53 символами, которые являются буквами нижнего или верхнего шкафа, цифрами или процентным знаком (%)
- строка "%3d"
- любой символ, который не является нижней или верхней буквой, цифрой или процентным знаком (%)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение CEP_Regex_AzureSAS находит содержимое, которое соответствует шаблону.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Строка подключения к шинам службы Azure

### <a name="format"></a>Формат

Строка "EndPoint", за которой следуют символы и строки, описанные в приведенной ниже схеме, включая строки "servicebus.windows".<!--no-hyperlink-->net" и "SharedAccesKey".

### <a name="pattern"></a>Шаблон

- строка "EndPoint"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- любое сочетание между 1-200 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- строка "servicebus.windows.<!--no-hyperlink-->net"
- любое сочетание между 1-200 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- строка "SharedAccessKey"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- любое сочетание из 43 символов, которые являются буквами нижнего или верхнего шкафа, цифрами, переназначаемой чертой (/) или знаком плюс (+)
- равный знак (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение CEP_Regex_AzureServiceBusConnectionString находит содержимое, которое соответствует шаблону.
- Обычное выражение CEP_CommonExampleKeywords не находит контент, который соответствует шаблону.

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

(Технически этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- тесты.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Ключ учетной записи azure

### <a name="format"></a>Формат

Строка "DefaultEndpointsProtocol" с символами и строками, описанными в рисунке ниже, включая строку "AccountKey".

### <a name="pattern"></a>Шаблон

- строка "DefaultEndpointsProtocol"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- любое сочетание между 1-200 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- строка "AccountKey"
- от нуля до двух символов белого пространства
- равный знак (=)
- от нуля до двух символов белого пространства
- любое сочетание из 86 символов, которые являются буквами нижнего или верхнего шкафа, цифрами, полосой вперед (/) или знаком плюс (+)
- два одинаковых знака (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение CEP_Regex_AzureStorageAccountKey находит содержимое, которое соответствует шаблону.
- Обычное выражение CEP_AzureEmulatorStorageAccountFilter не находит контент, который соответствует шаблону.
- Обычное выражение CEP_CommonExampleKeywords не находит контент, который соответствует шаблону.

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

(Технически этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Технически этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- тесты.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>служба хранилища Azure учетной записи (общий)

### <a name="format"></a>Формат

Любое сочетание из 86 букв нижнего или верхнего шкафа, цифр, переднюю черту (/) или знак плюс (+), предшествуют или следуют символы, описанные в рисунке ниже.

### <a name="pattern"></a>Шаблон

- от нуля до одного из символов (>), апострофа ('), равного знака (=), кавычка (") или знака номеров (#)
- любое сочетание из 86 символов, которые являются буквами нижнего или верхнего шкафа, цифрами, полосой вперед (/) или знаком плюс (+)
- два одинаковых знака (=)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Регулярное выражение CEP_Regex_AzureStorageAccountKeyGeneric контент, который соответствует шаблону.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Номер водительских прав в Бельгии

### <a name="format"></a>Формат

10 цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

10 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_belgium_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово `Keywords_eu_driver's_license_number` из `Keywords_belgium_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver s_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>Национальный номер Бельгии

### <a name="format"></a>Формат

11 цифр плюс необязательные делимитеры

### <a name="pattern"></a>Шаблон

11 цифр, а также разделители:
- шесть цифр и два необязательных периода в формате YY. MM.DD для даты рождения
- Необязательный делимитер из точки, тире, пространства
- три последовательной цифры (нечетные для мужчин, даже для женщин)
- Необязательный делимитер из точки, тире, пространства
- две контрольные цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- функция Func_belgium_national_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_belgium_national_number;
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- идентификация
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- удостоверение
- надпись
- национальный номер
- национальный реестр
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
- регистрация
- registrationsnumme
- registrierung
- social security number
- ssn #
- ssn
- steuernummer
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #

## <a name="belgium-passport-number"></a>Номер паспорта Бельгии

### <a name="format"></a>Формат

две буквы с шестью цифрами без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

две буквы и шесть цифр

### <a name="checksum"></a>Контрольная сумма

неприменимо

### <a name="definition"></a>Определение

 Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_belgium_eu_passport_number` или найдено.
- Регулярное выражение `Regex_eu_passport_date2` находит дату в формате DD MM YY или ключевое слово из `Keywords_eu_passport_date` или `Keywords_belgium_eu_passport_number` найдено

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_belgium_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Карт -пасспорт
- Livre Passeport
- Pass-Nr
- Passnummer
- reisepass kein

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия

## <a name="belgium-value-added-tax-number"></a>Номер налога на добавленную стоимость в Бельгии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

12-символ альфанумерный шаблон

### <a name="pattern"></a>Шаблон

12-символ альфанумерный шаблон:

- буквы B или b
- письмо E или e
- цифру 0
- цифру от 1 до 9
- необязательная точка или дефис или пространство
- четыре цифры
- необязательная точка или дефис или пространство
- четыре цифры


### <a name="checksum"></a>Контрольная сумма

Да


### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_belgium_value_added_tax_number контента, который соответствует шаблону.
- Ключевое слово Keywords_belgium_value_added_tax_number найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_belgium_value_added_tax_number контента, который соответствует шаблону.

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
- номер НДС
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- vat #


## <a name="brazil-cpf-number"></a>Номер CPF в Бразилии

### <a name="format"></a>Формат

11 цифр, которые включают проверочную цифру и могут быть форматированными или неформатированными.

### <a name="pattern"></a>Шаблон

Форматированный:
- три цифры
- период
- три цифры
- период
- три цифры
- дефис
- две цифры, которые являются контрольными цифрами

Unformatted:
- 11 цифр, где две последние цифры — проверочные.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_brazil_cpf;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- Регистрация
- Доходы
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita


## <a name="brazil-legal-entity-number-cnpj"></a>Номер юридического лица в Бразилии (CNPJ)

### <a name="format"></a>Формат

14 цифр, которые включают регистрационный номер, номер филиала и проверочные цифры, а также разделители.

### <a name="pattern"></a>Шаблон

14 цифр, а также разделители:

- две цифры
- период
- три цифры
- период
- три цифры (эти первые восемь цифр являются регистрационным номером)
- перенарезаемая косая черта
- четырехзначный номер филиала
- дефис
- две цифры, которые являются контрольными цифрами

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_brazil_cnpj;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- Организация
- CNPJ
- Cadastro Nacional da Pessoa Jurídica
- Cadastro Geral de Contribuintes
- CGC
- Pessoa jurídica
- Pessoas jurídicas
- Situação cadastral
- Inscrição
- Empresa


## <a name="brazil-national-identification-card-rg"></a>Национальная идентификация Бразилии (RG)

### <a name="format"></a>Формат

Реестр Geral (старый формат): девять цифр

Registro de Identidade (RIC) (новый формат): 11 цифр

### <a name="pattern"></a>Шаблон

Registro Geral (старый формат):
- две цифры
- период
- три цифры
- период
- три цифры
- дефис
- одна цифра, которая является контрольной цифрой

Registro de Identidade (RIC) (новый формат):
- 10 цифр.
- дефис
- одна цифра, которая является контрольной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- RG (это ключевое слово является чувствительным к делу)
- RIC (это ключевое слово является чувствительным к делу)


## <a name="bulgaria-drivers-license-number"></a>Номер водительского удостоверения Болгарии

### <a name="format"></a>Формат

девять цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_bulgaria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_bulgaria_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Единый гражданский номер Болгарии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

10 цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

10 цифр без пробелов и делимитеров

- шесть цифр, соответствующих дате рождения (YYMMDD)
- две цифры, соответствующие порядку рождения
- одна цифра, соответствующая полу: четная цифра для мужчин и нечетная цифра для женщин
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_bulgaria_eu_national_id_card` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_bulgaria_eu_national_id_card` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- edinen grazhdanski nomer
- egn #
- egn
- identification number
- national id
- национальный номер
- nationalnumber #
- nationalnumber
- личный id
- личный нет
- личный номер
- personalidnumber #
- social security number
- ssn #
- ssn
- единый гражданский id
- единый гражданский нет
- единый гражданский номер
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
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
- ID
- ID
- униформ граждански не
- униформ граждански номер
- Ъ -Газета #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Номер паспорта Болгарии

### <a name="format"></a>Формат

девять цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_bulgaria_eu_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_bulgaria_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия

## <a name="canada-bank-account-number"></a>Номер банковского счета в Канаде

### <a name="format"></a>Формат

7 или 12 цифр

### <a name="pattern"></a>Шаблон

Номер учетной записи Банка Канады — 7 или 12 цифр.

Транзитный номер банковского счета в Канаде имеет указанный ниже формат.
- пять цифр
- дефис
- три цифры OR
- нулевое значение "0"
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_canada_bank_account_number.
- регулярное выражение Regex_canada_bank_account_transit_number находит содержимое, которое соответствует шаблону.

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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


## <a name="canada-drivers-license-number"></a>Номер водительских прав в Канаде

### <a name="format"></a>Формат

Зависит от провинции.

### <a name="pattern"></a>Шаблон

Различные шаблоны, охватывающие:
- Альберта
- British Columbia
- Манитоба
- New Brunswick
- Newfoundland/Labrador
- Nova Scotia
- Онтарио
- Prince Edward Island
- Квебек
- Саскачеван

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- Водительские права
- Водительские права
- Водительские права
- Водительские права
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
- идентификация
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
- Водительские права #
- Водительские права #
- Водительские права #
- Водительские права #
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
- идентификация #


## <a name="canada-health-service-number"></a>Номер службы здравоохранения Канады

### <a name="format"></a>Формат

 10 цифр.

### <a name="pattern"></a>Шаблон

10 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- психиатр
- workers compensation
- инвалидность


## <a name="canada-passport-number"></a>Номер паспорта Канады

### <a name="format"></a>Формат

два верхних буквы с последующим шестью цифрами

### <a name="pattern"></a>Шаблон

два верхних буквы с последующим шестью цифрами

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_canada_passport_number находит содержимое, которое соответствует шаблону;
- Найдено ключевое слово Keyword_canada_passport_number Keyword_passport или Keyword_passport.

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
- Паспорт #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パポ.
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °


## <a name="canada-personal-health-identification-number-phin"></a>Идентификационный номер личного здоровья Канады (PHIN)

### <a name="format"></a>Формат

девять цифр

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_canada_phin находит содержимое, которое соответствует шаблону;
- Найдены по крайней мере два Keyword_canada_phin или Keyword_canada_provinces.

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

- Nunavut
- Квебек
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


## <a name="canada-social-insurance-number"></a>Номер социального страхования Канады

### <a name="format"></a>Формат

девять цифр с необязательными дефисами или пробелами

### <a name="pattern"></a>Шаблон

Форматированный:
- три цифры
- дефис или пространство
- три цифры
- дефис или пространство
- три цифры

Unformatted: nine digits

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_canadian_sin находит содержимое, которое соответствует шаблону.
- По крайней мере два из следующих шаблонов:
    - найдено ключевое слово из Keyword_sin;
    - найдено ключевое слово из Keyword_sin_collaborative;
    - функция Func_eu_date находит дату в правильном формате.
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- грехи
- ssn
- ssns
- social security
- numero d'assurance social
- national identification number
- national id
- грех #
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


## <a name="chile-identity-card-number"></a>Номер удостоверения личности в Чили

### <a name="format"></a>Формат

семь-восемь цифр плюс делимитеры контрольная цифра или буква

### <a name="pattern"></a>Шаблон

семь-восемь цифр плюс делимитеры:
- от одной до двух цифр
- необязательный период
- три цифры
- необязательный период
- три цифры
- тире
- одна цифра или буква (не чувствительная к делу), которая является проверяемой цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_chile_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_chile_id_card;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- трибутарио rol único
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
- identificacion numero
- identidad numero
- Чилийское удостоверение нет.
- Чилийский номер удостоверения
- Чилийская идентичность #
- Уникальный налоговый реестр
- Уникальная роль притока
- Уникальная налоговая роль
- Уникальный номер притока
- Уникальный национальный номер
- Уникальная национальная роль
- Национальная уникальная роль
- Удостоверение Чили нет.
- Номер удостоверения Чили
- Удостоверение Чили #


## <a name="china-resident-identity-card-prc-number"></a>Номер удостоверения резидента Китая (PRC)

### <a name="format"></a>Формат

18 цифр.

### <a name="pattern"></a>Шаблон

18 цифр:
- шесть цифр, которые являются адресным кодом
- восемь цифр в форме YYYYYMMDD, которые являются датой рождения
- три цифры, которые являются кодом заказа
- одна цифра, которая является контрольной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_china_resident_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_china_resident_id;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- PRC
- National Identification Card
- 身份证
- 居民 身份证
- 居民身份证
- 鉴定
- 身分證
- 居民 身份證
- 鑑定


## <a name="credit-card-number"></a>Номер кредитной карты

### <a name="format"></a>Формат

От 14 до 16 цифр, которые могут быть отформатированы или неформатированы (dddd), и которые должны пройти тест Luhn.

### <a name="pattern"></a>Шаблон

Обнаруживает карты всех крупных брендов по всему миру, включая карты Visa, MasterCard, Discover Card, JCB, American Express, подарочные карты и карточки для посетителей.

### <a name="checksum"></a>Контрольная сумма

Да (рассчитывается по алгоритму Луна).

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_credit_card находит содержимое, которое соответствует шаблону;
- Верно одно из условий ниже:
    - найдено ключевое слово из Keyword_cc_verification;
    - найдено ключевое слово из Keyword_cc_name;
    - функция Func_expiration_date находит дату в правильном формате.
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- треска. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- треска. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- 
cód. segurança
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
- доблестная
- vencimento
- транзакция
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
- dinersclub
- откройте для себя
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
- кредитные карточки
- ccn
- card holder
- держатель карт
- card holders
- держатели карт
- check card
- checkcard
- check cards
- checkcards
- debit card
- debitcard
- debit cards
- дебетовые карточки
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
- Корпоративная карта
- Корпоративные карты
- Тип карты
- номер учетной записи карты
- Учетная запись участника карты
- Cardmember Acct.
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
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- n. карт
- n carta
- nr. карт
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
- no. do cartao

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
- Visaカ) ド
- Visa カド
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


## <a name="croatia-drivers-license-number"></a>Номер водительских прав в Хорватии

### <a name="format"></a>Формат

восемь цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

- Обычное выражение  `Regex_croatia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово `Keywords_eu_driver's_license_number` из `Keywords_croatia_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Номер удостоверения личности в Хорватии
Эта сущность включена в тип конфиденциальной информации о номере национального идентификации ЕС. Он доступен в виде отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат

девять цифр

### <a name="pattern"></a>Шаблон

девять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

- majstorski broj grajana
- мастер-номер гражданина
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- личный идентификационный номер
- porezni broj
- porezni identifikacijski broj
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="croatia-passport-number"></a>Номер паспорта Хорватии

### <a name="format"></a>Формат

девять цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_croatia_eu_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_croatia_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice

## <a name="croatia-personal-identification-oib-number"></a>Личный идентификационный номер (OIB) в Хорватии

### <a name="format"></a>Формат

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр:
- 10 цифр.
- окончательная цифра — это контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;
- Ключевое слово из Keywords_croatia_eu_tax_file_number найдено.
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

- majstorski broj grajana
- мастер-номер гражданина
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- личный идентификационный номер
- porezni broj
- porezni identifikacijski broj
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #

## <a name="cyprus-drivers-license-number"></a>Номер лицензии для водителей Кипра

### <a name="format"></a>Формат

12 цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

12 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_cyprus_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_cyprus_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Удостоверение личности на Кипре
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

10 цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

10 цифр.

### <a name="checksum"></a>Контрольная сумма

неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_cyprus_eu_national_id_card` находит содержимое, которое соответствует шаблону.
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

- номер id-карты
- номер удостоверения
- kimlik karti
- national identification number
- личный номер
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Номер паспорта Кипра

### <a name="format"></a>Формат

одна буква с 6-8 цифрами без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

одна буква с шестью или восемью цифрами

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_cyprus_eu_passport_number` или найдено.
- Регулярное выражение `Regex_cyprus_eu_passport_date` находит дату в формате DD/MM/YYYY или найдено ключевое слово `Keywords_cyprus_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_cyprus_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport нет.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- истекает срок действия
- выданный на


## <a name="cyprus-tax-identification-number"></a>Идентификационный номер налога на Кипр
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

восемь цифр и одна буква в указанном шаблоне

### <a name="pattern"></a>Шаблон

восемь цифр и одна буква:

- "0" или "9"
- семь цифр
- одна буква (не деликатная)

### <a name="checksum"></a>Контрольная сумма

неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_cyprus_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_cyprus_eu_tax_file_number` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- код идентификации налога
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tic #
- tic
- tin id
- олово нет
- олово #
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Номер чешского водительского удостоверения

### <a name="format"></a>Формат

две буквы, за которыми следуют шесть цифр

### <a name="pattern"></a>Шаблон

восемь букв и цифр:

- буква "E" (не в случае)
- письмо
- пробел (необязательный)
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_czech_republic_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_czech_republic_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver s_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských průkaz


## <a name="czech-passport-number"></a>Номер чешского паспорта

### <a name="format"></a>Формат

восемь цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

восемь цифр без пробелов или делимитеров

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_czech_republic_eu_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_czech_republic_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="czech-personal-identity-number"></a>Чешский персональный номер

### <a name="format"></a>Формат

девять цифр с необязательным переназначаемой чертой (старый формат) 10 цифр с необязательным переназначе-ным слэшем (новый формат)

### <a name="pattern"></a>Шаблон

девять цифр (старый формат):
- шесть цифр, которые представляют дату рождения
- необязательный слэш
- три цифры

10 цифр (новый формат):
- шесть цифр, которые представляют дату рождения
- необязательный слэш
- четыре цифры, где последняя цифра — это контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:

- функция Func_czech_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_czech_id_card;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

- Функция Func_czech_id_card_new_format контента, который соответствует шаблону.
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

- число рождения
- чешская республика id
- czechidno #
- daпечи číslo
- identifikační číslo
- удостоверение нет
- номер удостоверения
- identityno #
- identityno
- номер страховки
- national identification number
- nationalnumber #
- национальный номер
- osobní číslo
- personalidnumber #
- личный номер
- личный идентификационный номер
- личный номер
- pid #
- pid
- pojištění číslo
- rč
- Rodne cislo
- rodné číslo
- ssn
- ssn #
- social security number
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- уникальный идентификационный номер


## <a name="denmark-drivers-license-number"></a>Номер водительских прав Дании

### <a name="format"></a>Формат

восемь цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_denmark_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_denmark_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver s_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Номер паспорта Дании

### <a name="format"></a>Формат

девять цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_denmark_eu_passport_number` или найдено.
- Регулярное выражение `Regex_eu_passport_date2` находит дату в формате DD MM YY или ключевое слово `Keywords_eu_passport_date` из найдено

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_denmark_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="denmark-personal-identification-number"></a>Личный идентификационный номер Дании

### <a name="format"></a>Формат

10 цифр, содержащих дефис.

### <a name="pattern"></a>Шаблон

10 цифр:
- шесть цифр в формате DDMMYY, которые являются датой рождения
- дефис
- четыре цифры, в которых окончательная цифра — это контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Регулярное выражение Func_denmark_eu_tax_file_number находит содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_denmark_id;
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- gesundheitsverscherungkarte nummer
- карточка здоровья
- номер карточки медицинского страхования
- номер медицинского страхования
- identification number
- identifikationsnummer
- identifikationsnummer #
- номер удостоверения
- krankenkassennummer
- nationalid #
- nationalnumber #
- национальный номер
- personalidnumber #
- personalidentityno #
- личный номер
- personnummer
- personnummer #
- reisekrankenverscherungskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- скейт-ид
- коде фигурного катания
- фигурное фигурное число
- skattenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- налоговый код
- карта медицинского страхования путешествий
- uniqueidentityno #
- налоговый номер
- номер регистрации налога
- tax id
- идентификационный номер налога
- таксомоторный #
- taxnumber #
- нет налога
- taxno #
- taxnumber
- идентификация налога нет
- олово #
- taxidno #
- taxidnumber #
- нет налога #
- tin id
- олово нет
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


## <a name="drug-enforcement-agency-dea-number"></a>Номер Агентства по принудиванию к наркотикам (DEA)

### <a name="format"></a>Формат

две буквы, за которыми следуют семь цифр

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.
- одна буква (не деликатная) из этого набора возможных букв: abcdefghjklmnprstux, который является кодом регистратора
- одна буква (не деликатная), которая является первой буквой фамилии или цифры "9" регистратора.
- семь цифр, последним из которых является контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_dea_number находит содержимое, которое соответствует шаблону;
- Найдено `Keyword_dea_number` ключевое слово
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- администрирование по принудительных лекарственных препарат
- агентство по принудиванию к наркотикам


## <a name="estonia-drivers-license-number"></a>Номер водительских прав Эстонии

### <a name="format"></a>Формат

две буквы, за которыми следуют шесть цифр

### <a name="pattern"></a>Шаблон

две буквы и шесть цифр:

- буквы "ET" (не чувствительные к делу)
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_estonia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_estonia_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver s_license_number

-- permis de conduire
- juhilubade numbrid
- номер juhiloa
- juhiluba


## <a name="estonia-personal-identification-code"></a>Код личной идентификации Эстонии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

11 цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

11 цифр:

- одна цифра, соответствующая полу и столетию рождения (нечетное число мужчин, даже женское; 1-2: 19-й век; 3-4: 20-й век; 5-6: 21 век)
- шесть цифр, соответствующих дате рождения (YYMMDD)
- три цифры, соответствующие последовательному номеру, разделяющей лиц, родившихся в ту же дату
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_estonia_eu_national_id_card` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_estonia_eu_national_id_card` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- национальный номер
- личный код
- личный номер
- личный код идентификации
- личный идентификационный номер
- personalidnumber #
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="estonia-passport-number"></a>Номер паспорта Эстонии

### <a name="format"></a>Формат

одна буква с семью цифрами без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

одна буква, за которой следуют семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_estonia_eu_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_estonia_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi passinumbrid document document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="eu-debit-card-number"></a>Номер дебетовой карты, выпущенной в ЕС

### <a name="format"></a>Формат

16 цифр.

### <a name="pattern"></a>Шаблон

Сложный и надежный шаблон

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- держатель карт
- держатели карт
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
- chequekaart
- cirrus
- cirrus-edc-maestro
- controlekaart
- controlekaarten
- credit card
- credit cards
- creditcard
- кредитные карточки
- debetkaart
- debetkaarten
- debit card
- debit cards
- debitcard
- дебетовые карточки
- debito automatico
- diners club
- dinersclub
- откройте для себя
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
- kaartaantallen
- kaarthouder
- kaarthouders
- karte
- karteninhaber
- karteninhabers
- kartennr
- kartennummer
- kreditkarte
- kreditkarten-nummer
- kreditkarteninhaber
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
- карт
- no de tarjeta
- no do cartao
- no do cartão
- no. de tarjeta

- no. do cartao

- no. do cartão

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
- соло
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
- kreditkartenprufnummer
- kreditkartenprüfnummer
- kwestieaantal
- no. dell'edizione

- no. di sicurezza

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
- veiligheidsaantal
- veiligheidscode
- veiligheidsnummer
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
- истечение срока действия
- истекает срок действия
- истекает срок действия
- истечение срока действия
- fecha de expiracion
- fecha de venc
- gultig bis
- gultigkeitsdatum
- gültig bis
- gültigkeitsdatum
- la scadenza
- scadenza
- доблестная
- validade
- valido hasta
- доблестная
- venc
- vencimento
- vencimiento
- verloopt
- vervaldag
- vervaldatum
- vto
- válido hasta


## <a name="eu-drivers-license-number"></a>Номер водительских прав ЕС

Эти сущности находятся в номере лицензии водителя ЕС и являются конфиденциальными типами информации.

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
- [Люксембург](#luxemburg-drivers-license-number)
- [Мальта](#malta-drivers-license-number)
- [Нидерланды](#netherlands-drivers-license-number)
- [Польша](#poland-drivers-license-number)
- [Португалия](#portugal-drivers-license-number)
- [Румыния](#romania-drivers-license-number)
- [Словакия](#slovakia-drivers-license-number)
- [Словения](#slovenia-drivers-license-number)
- [Испания](#spain-drivers-license-number)
- [Швеция](#sweden-drivers-license-number)
- [U.K.](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Номер национальной идентификации ЕС

Эти сущности находятся в национальном идентификационных номерах ЕС и являются типами конфиденциальной информации.

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
- [Люксембург](#luxemburg-national-identification-number-natural-persons)
- [Мальта](#malta-identity-card-number)
- [Нидерланды](#netherlands-citizens-service-bsn-number)
- [Польша](#poland-national-id-pesel)
- [Португалия](#portugal-citizen-card-number)
- [Румыния](#romania-personal-numeric-code-cnp)
- [Словакия](#slovakia-personal-number)
- [Словения](#slovenia-unique-master-citizen-number)
- [Испания](#spain-dni)
- [U.K.](#uk-national-insurance-number-nino)


## <a name="eu-passport-number"></a>Номер паспорта ЕС

Эти сущности находятся в номере паспорта ЕС и являются типами конфиденциальной информации. Эти сущности находятся в пакете номеров паспортов ЕС.

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
- [Люксембург](#luxemburg-passport-number)
- [Мальта](#malta-passport-number)
- [Нидерланды](#netherlands-passport-number)
- [Польша](#poland-passport-number)
- [Португалия](#portugal-passport-number)
- [Румыния](#romania-passport-number)
- [Словакия](#slovakia-passport-number)
- [Словения](#slovenia-passport-number)
- [Испания](#spain-passport-number)
- [Швеция](#sweden-passport-number)
- [U.K.](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Номер социального обеспечения ЕС или эквивалентная идентификация

Эти сущности, которые находятся в номере социального обеспечения ЕС или эквивалентной идентификации и являются типами конфиденциальной информации.

- [Австрия](#austria-social-security-number)
- [Бельгия](#belgium-national-number)
- [Хорватия](#croatia-personal-identification-oib-number)
- [Чешский](#czech-personal-identity-number)
- [Дания](#denmark-personal-identification-number)
- [Финляндия](#finland-national-id)
- [Франция](#france-social-security-number-insee)
- [Германия](#germany-identity-card-number)
- [Греция](#greece-national-id-card)
- [Венгрия](#hungary-social-security-number-taj)
- [Португалия](#portugal-citizen-card-number)
- [Испания](#spain-social-security-number-ssn)
- [Швеция](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>Номер налоговой идентификации ЕС

Эти сущности находятся в типе конфиденциальной информации по номеру идентификации налогового номера ЕС.

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
- [Люксембург](#luxemburg-national-identification-number-non-natural-persons)
- [Мальта](#malta-tax-identification-number)
- [Нидерланды](#netherlands-tax-identification-number)
- [Польша](#poland-tax-identification-number)
- [Португалия](#portugal-tax-identification-number)
- [Румыния](#romania-personal-numeric-code-cnp)
- [Словакия](#slovakia-personal-number)
- [Словения](#slovenia-tax-identification-number)
- [Испания](#spain-tax-identification-number)
- [Швеция](#sweden-tax-identification-number)
- [U.K.](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Номер водительского удостоверения Финляндии

### <a name="format"></a>Формат

10 цифр, содержащих дефис.

### <a name="pattern"></a>Шаблон

10 цифр, содержащих дефис:

- шесть цифр
- дефис
- три цифры
- цифру или букву

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_finland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_finland_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Номер европейского медицинского страхования Финляндии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

20-значный номер

### <a name="pattern"></a>Шаблон

20-значный номер:

- 10 цифр - 8024680246
- необязательный пробел или дефис
- 10 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- В regex Regex_Finland_European_Health_Insurance_Number контент, который соответствует шаблону.
- Найдено ключевое слово Keyword_Finland_European_Health_Insurance_Number.

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
- finska sjukförsäkringskort
- карточка здоровья
- карта медицинского страхования
- номер медицинского страхования
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- nummer sjukförsäkring
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>Национальный ID Финляндии

### <a name="format"></a>Формат

шесть цифр плюс символ, указывающий на столетие плюс три цифры плюс контрольная цифра

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.
- шесть цифр в формате DDMMYY, которые являются датой рождения
- маркер века (или '-', '+' или 'a')
- трехзначный личный идентификационный номер
- цифру или букву (случай нечувствительный), которая является контрольной цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_finnish_national_id контента, который соответствует шаблону
- найдено ключевое слово Keyword_finnish_national_id из Keyword_finnish_national_id
- проходит проверку

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- функция Func_finnish_national_id контента, который соответствует шаблону
- проходит проверку

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

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id no
- номер id
- identification number
- identiteetti numero
- номер удостоверения
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- национальная id-карта
- нет национального id.
- личный id
- персональный код удостоверения
- personalidnumber #
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Номер паспорта Финляндии

Эта сущность доступна в типе конфиденциальной информации по номеру паспорта ЕС и доступна в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат
сочетание девяти букв и цифр

### <a name="pattern"></a>Шаблон
сочетание девяти букв и цифр:
- две буквы (не чувствительные к делу)
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение `Regex_finland_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово `Keywords_eu_passport_number` из `Keyword_finland_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение `Regex_finland_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово `Keywords_eu_passport_number` из `Keyword_finland_passport_number` или найдено.

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- число passin
- число passin. #
- число passin #
- число passin.
- passi #
- номер passi

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия

## <a name="france-drivers-license-number"></a>Номер водительских прав Во Франции

Эта сущность доступна в типе конфиденциальной информации о номере лицензии водителя ЕС и доступна в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат

12 цифр.

### <a name="pattern"></a>Шаблон

12 цифр с проверкой подлинности, чтобы избежать путаницы с похожими шаблонами, например французскими номерами телефонов.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- функция Func_french_drivers_license контент, который соответствует шаблону.
- ключевое слово Keyword_french_drivers_license найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>Номер медицинского страхования Во Франции
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

21-значный номер

### <a name="pattern"></a>Шаблон

21-значный номер:

- 10 цифр.
- необязательный пробел
- 10 цифр.
- необязательный пробел
- цифру


### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- regex Regex_France_Health_Insurance_Number контент, который соответствует шаблону.
- найдено ключевое слово Keyword_France_Health_Insurance_Number.

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

- карта страхования
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>Национальная id-карта Франции (CNI)

### <a name="format"></a>Формат

12 цифр.

### <a name="pattern"></a>Шаблон

12 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_france_cni находит содержимое, которое соответствует шаблону.
- Ключевое слово Keywords_france_eu_national_id_card найдено.

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
- национальная идентичность
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale


## <a name="france-passport-number"></a>Номер паспорта Франции
Эта сущность доступна в типе конфиденциальной информации по номеру паспорта ЕС. Он также доступен в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат

девять цифр и букв

### <a name="pattern"></a>Шаблон

девять цифр и букв:
- две цифры
- две буквы (не чувствительные к делу)
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит `Func_fr_passport` содержимое, которое соответствует шаблону.
- Ключевое слово `Keywords_eu_passport_number` из `Keywords_france_eu_passport_number` или найдено.
- Регулярное выражение `Regex_eu_passport_date3` находит дату в формате DD MM YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция находит `Func_fr_passport` содержимое, которое соответствует шаблону.
- Ключевое слово `Keywords_eu_passport_number` из `Keywords_france_eu_passport_number` или найдено.


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passeport français
- livre passeport
- карт-порт пасспорта
- numéro passeport
- passeport n°
- n° du passeport
- n° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="france-social-security-number-insee"></a>Номер социального обеспечения Франции (INSEE)

### <a name="format"></a>Формат

15 цифр.

### <a name="pattern"></a>Шаблон

Должен соответствовать одному из двух шаблонов:
- 13 цифр с последующим пространством с двумя цифрами<br/>
или
- 15 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит `Func_french_insee` содержимое, которое соответствует шаблону.
- находится ключевое слово из Keyword_fr_insee;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.
- Контрольная сумма проходит проверку.

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- insee
- fssn #
- le numéro d'identification nationale
- le code de la sécurité sociale
- national id
- national identification
- no d'identité
- 
no. d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- no d'identite
- 
no. d'identite
- ssn
- ssn #
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- social security number
- social security code
- social insurance number


## <a name="france-tax-identification-number"></a>Номер идентификации налога во Франции

### <a name="format"></a>Формат

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

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_france_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_france_eu_tax_file_number` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="france-value-added-tax-number"></a>Номер налога на добавленную стоимость во Франции
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

13 символов альфанумерного шаблона

### <a name="pattern"></a>Шаблон

13 символов альфанумерного шаблона:

- две буквы - FR (случай нечувствительный)
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

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_france_value_added_tax_number контента, который соответствует шаблону.
- Найдено ключевое слово Keywords_france_value_added_tax_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_france_value_added_tax_number контента, который соответствует шаблону.

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

- номер НДС
- vat no
- vat #
- налог на добавленную стоимость
- идентификация сирены без numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- сирена numéro d'identification


## <a name="germany-drivers-license-number"></a>Номер водительских прав в Германии

Этот тип конфиденциальной информации входит в тип конфиденциальной информации номер лицензии водителя ЕС. Он также доступен в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат

сочетание 11 цифр и букв

### <a name="pattern"></a>Шаблон

11 цифр и букв (не чувствительных к делу):
- цифру или букву
- две цифры
- шесть цифр или букв
- цифру
- цифру или букву

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- führerschein
- fuhrerschein
- fuehrerschein
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein- 
- fuhrerschein- 
- fuehrerschein- 
- führerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- fuhrerscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-führerschein
- nr-fuhrerschein
- nr-fuehrerschein
- no-führerschein
- no-fuhrerschein
- no-fuehrerschein
- n-führerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dlno


## <a name="germany-identity-card-number"></a>Номер удостоверения личности в Германии

### <a name="format"></a>Формат

с 1 ноября 2010 г.: девять букв и цифр

с 1 апреля 1987 г. по 31 октября 2010 г.: 10 цифр

### <a name="pattern"></a>Шаблон

с 1 ноября 2010 г.:
- одна буква (не деликатная)
- восемь цифр

с 1 апреля 1987 г. по 31 октября 2010 г.:
- 10 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- идентификация
- identifikation
- identifizierungsnummer
- identity card
- номер удостоверения
- id-nummer
- личный id
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>Номер паспорта Германии

Эта сущность включена в тип конфиденциальной информации номера паспорта ЕС и доступна в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат

10 цифр или букв.

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.
- первый символ — это цифры или буквы из этого набора (C, F, G, H, J, K)
- три цифры
- пять цифр или букв из этого набора (C, H, J-N, P, R, T, V-Z)
- цифру

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_german_passport находит содержимое, которое соответствует шаблону;
- Ключевое слово `Keyword_german_passport` из `Keywords_eu_passport_number_common` или найдено.
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- функция Func_german_passport_data находит содержимое, которое соответствует шаблону;
- Ключевое слово `Keyword_german_passport` из `Keywords_eu_passport_number_common` или найдено.
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
- reisepässe
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов


## <a name="germany-tax-identification-number"></a>Идентификационный номер налога в Германии

### <a name="format"></a>Формат

11 цифр без пробелов и делимитеров

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

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_germany_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_germany_eu_tax_file_number` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- zinn #
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>Номер налога на добавленную стоимость в Германии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

Альфанумерный шаблон 11 символов

### <a name="pattern"></a>Шаблон

11-символ альфанумерного шаблона:

- буква D или d
- письмо E или e
- необязательный пробел
- три цифры
- необязательный пробел или запятая
- три цифры
- необязательный пробел или запятая
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_germany_value_added_tax_number контента, который соответствует шаблону.
- Ключевое слово Keywords_germany_value_added_tax_number найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_germany_value_added_tax_number контента, который соответствует шаблону.

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

- номер НДС
- vat no
- vat #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- nummer mehrwertsteuer


## <a name="greece-drivers-license-number"></a>Номер водительских прав Греции

Эта сущность включена в тип конфиденциальной информации о номере лицензии в ЕС. Он также доступен в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат

девять цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_greece_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_greece_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>Национальная ID-карта Греции

### <a name="format"></a>Формат

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

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_greece_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_greece_id_card.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

- греческий id
- греческий национальный id
- греческая личная id-карта
- греческий id полиции
- identity card
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Номер паспорта Греции

### <a name="format"></a>Формат

Две буквы, за которыми следуют семь цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

Две буквы, за которыми следуют семь цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_greece_eu_passport_number` или найдено.
- Регулярное выражение находит дату `Regex_greece_eu_passport_date` в формате DD MMM YY (Пример - 28 августа 19) или ключевое слово `Keywords_greece_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_greece_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Номер социального обеспечения Греции (AMKA)
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

11 цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

- Шесть цифр в качестве даты рождения YYMMDD
- Четыре цифры
- контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_greece_eu_ssn` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_greece_eu_ssn_or_equivalent` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- социального обеспечения нет
- socialsecurityno #
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Идентификационный номер налога в Греции
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

Девять цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

Девять цифр.

### <a name="checksum"></a>Контрольная сумма

Неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

- Обычное выражение  `Regex_greece_eu_tax_file_number` находит содержимое, которое соответствует шаблону.
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
- asμ|aμ αριθμός
- a.
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- реестра налогов нет
- номер реестра налогов
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- tin id
- олово нет
- олово #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Номер удостоверения личности Гонконга (HKID)

### <a name="format"></a>Формат

Сочетание 8–9 букв и чисел, а также необязательные скобки вокруг последнего символа.

### <a name="pattern"></a>Шаблон

Сочетание 8–9 букв:
- 1-2 буквы (не чувствительные к делу)
- шесть цифр; 
- последний символ (любая цифра или буква "A") является проверочной цифрой и заключен в скобки (необязательно).

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_hong_kong_id_card;
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- удостоверение гонконга
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


## <a name="hungary-drivers-license-number"></a>Номер водительских прав в Венгрии

### <a name="format"></a>Формат

Две буквы с шестью цифрами

### <a name="pattern"></a>Шаблон

Две буквы и шесть цифр:

- Две буквы (не чувствительные к делу)
- шесть цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

- Обычное выражение  `Regex_hungary_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_hungary_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver s_license_number

- vezetoi engedely
- vezetéi engedély
- vezetéi engedélyek


## <a name="hungary-personal-identification-number"></a>Личный идентификационный номер Венгрии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр:

- Одна цифра, соответствующая полу, 1 для мужчины, 2 для женщин. Другие номера также возможны для граждан, родившихся до 1900 г. или граждан с двойным гражданством.
- Шесть цифр, соответствующих дате рождения (YYMMDD)
- Три цифры, соответствующие серийному номеру
- Одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:

- Функция находит  `Func_hungary_eu_national_id_card` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_hungary_eu_national_id_card` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

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

- номер id
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>Номер паспорта Венгрии

### <a name="format"></a>Формат

Две буквы с шестью или семью цифрами без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

Две буквы с шестью или семью цифрами

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_hungary_eu_passport_number` или найдено.
- Обычное выражение находит дату в формате `Regex_hungary_eu_passport_date` DD MMM/MMM YY (Пример - 01 MÁR/MAR 12) или ключевое слово `Keywords_eu_passport_date` из найдено

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_hungary_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="hungary-social-security-number-taj"></a>Номер социального обеспечения Венгрии (TAJ)

### <a name="format"></a>Формат

Девять цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

Девять цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:

- Функция находит  `Func_hungary_eu_ssn_or_equivalent` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_hungary_eu_ssn_or_equivalent` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

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
- социального обеспечения нет
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Идентификация налога в Венгрии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

10 цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

10 цифр:

- Одна цифра, которая должна быть "8"
- Восемь цифр
- Одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:

- Функция находит  `Func_hungary_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_hungary_eu_tax_file_number` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

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
- венгерское олово
- hungatiantin #
- налоговый орган нет
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- номер НДС


## <a name="hungary-value-added-tax-number"></a>Номер налога на добавленную стоимость в Венгрии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

Альфанумерный шаблон 10 символов

### <a name="pattern"></a>Шаблон

10 символов альфанумерного шаблона:

- две буквы - HU или hu
- необязательный пробел
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:

- Функция Func_hungarian_value_added_tax_number контента, который соответствует шаблону.
- Ключевое слово Keywords_hungarian_value_added_tax_number найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

- Функция Func_hungarian_value_added_tax_number контента, который соответствует шаблону.

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
- нет налога.
- налог на добавленную стоимость áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>Постоянный номер учетной записи Индии (PAN)

### <a name="format"></a>Формат

10 букв или цифр.

### <a name="pattern"></a>Шаблон

10 букв или цифр:
- Три буквы (не чувствительные к делу)
- Буквы C, P, H, F, A, T, B, L, J, G (не чувствительны к делу)
- Письмо
- Четыре цифры
- Буква, которая является алфавитной цифрой проверки

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_india_permanent_account_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_india_permanent_account_number;

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

## <a name="india-unique-identification-aadhaar-number"></a>Уникальный идентификационный номер Индии (Aadhaar)

### <a name="format"></a>Формат

12 цифр, содержащих необязательные пробелы или тире.

### <a name="pattern"></a>Шаблон

12 цифр:
- Цифры, не 0 или 1
- Три цифры
- необязательный пробел или тире;
- четыре цифры;
- необязательный пробел или тире;
- Окончательная цифра, которая является чековой цифрой

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_india_aadhaar находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_india_aadhar;
- Контрольная сумма проходит проверку.
-
Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

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

## <a name="indonesia-identity-card-ktp-number"></a>Номер удостоверения личности (KTP) в Индонезии

### <a name="format"></a>Формат

16 цифр, содержащих необязательные точки.

### <a name="pattern"></a>Шаблон

16 цифр:
- две цифры (код провинции);
- точка (необязательно);
- две цифры (код округа или города);
- две цифры (код района);
- точка (необязательно);
- Шесть цифр в формате DDMMYY, которые являются датой рождения
- точка (необязательно);
- четыре цифры.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:

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

## <a name="international-banking-account-number-iban"></a>Номер международного банковского счета (IBAN)

### <a name="format"></a>Формат

Код страны (две буквы), а также проверочные цифры (две) и номер bban (до 30 символов)

### <a name="pattern"></a>Шаблон

Шаблон должен включать в себя все указанные ниже элементы.

- Двухбуквенный код страны
- Две проверочные цифры (после которых может следовать пробел) 
- 1–7 групп из четырех букв или цифр (могут разделяться пробелами)
- 1–3 буквы или цифры

Формат для названия каждой из стран немного отличается. Тип конфиденциальной информации IBAN применяется к следующим 60 странам:

- ad
- ae
- al
- в
- az
- ba
- be
- bg
- bh
- ch
- cr
- cy
- cz
- de
- dk
- сделать
- ee
- es
- fi
- fo
- fr
- GB
- ge
- gi
- gl
- gr
- hr
- hu
- ie
- il
- есть
- оно
- kw
- kz
- lb
- li
- lt
- lu
- lv
- mc
- MD
- me
- mk
- mr
- mt
- mu
- nl
- Нет
- pl
- pt
- ro
- rs
- sa
- se
- si
- sk
- sm
- tn
- tr
- vg

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:

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

Нет.


## <a name="international-classification-of-diseases-icd-10-cm"></a>Международная классификация заболеваний (ICD-10-CM)

### <a name="format"></a>Формат

Dictionary

### <a name="pattern"></a>Шаблон

Ключевое слово

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Ключевое слово Dictionary_icd_10_updated найдено.
- Ключевое слово Dictionary_icd_10_codes найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Найдено ключевое слово Dictionary_icd_10_ обновления.

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

Любой термин из словаря Dictionary_icd_10_updated ключевого слова, который основан на международной классификации заболеваний, десятой ревизии, клинической модификации [(ICD-10-CM).](https://go.microsoft.com/fwlink/?linkid=852604) Этот тип ищет только термин, а не коды страхования.

Любой термин из словаря Dictionary_icd_10_codes ключевого слова, который основан на международной классификации заболеваний, десятой ревизии, клинической модификации [(ICD-10-CM).](https://go.microsoft.com/fwlink/?linkid=852604) Этот тип ищет только коды страхования, а не описание.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Международная классификация заболеваний (ICD-9-CM)

### <a name="format"></a>Формат

Dictionary

### <a name="pattern"></a>Шаблон

Ключевое слово

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Ключевое слово Dictionary_icd_9_updated найдено.
- Ключевое слово Dictionary_icd_9_codes найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Ключевое слово Dictionary_icd_9_updated найдено.

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

Любой термин из словаря Dictionary_icd_9_updated ключевого слова, который основан на международной классификации заболеваний, девятой ревизии, клинической модификации [(ICD-9-CM).](https://go.microsoft.com/fwlink/?linkid=852605) Этот тип ищет только термин, а не коды страхования.

Любой термин из словаря Dictionary_icd_9_codes ключевого слова, который основан на международной классификации болезней, девятой ревизии, клинической модификации [(ICD-9-CM).](https://go.microsoft.com/fwlink/?linkid=852605) Этот тип ищет только коды страхования, а не описание.

## <a name="ip-address"></a>IP-адрес

### <a name="format"></a>Формат

#### <a name="ipv4"></a>IPv4:
Сложный шаблон, который учитывает отформатированные (периоды) и неформатированные (без периодов) версии адресов IPv4

#### <a name="ipv6"></a>IPv6:
Сложный шаблон, который учитывает отформатированные номера IPv6 (включая двоеточия)

### <a name="pattern"></a>Шаблон

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Для IPv6 политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_ipv6_address находит содержимое, которое соответствует шаблону;
- ни одно ключевое слово из Keyword_ipaddress не находится.

Для IPv4 политика DLP имеет высокую уверенность в том, что он обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_ipv4_address находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_ipaddress.

Для IPv6 политика DLP имеет высокую уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

- IP (это ключевое слово является чувствительным к делу)
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה

## <a name="ireland-drivers-license-number"></a>Номер лицензии водителя Ирландии

### <a name="format"></a>Формат

Шесть цифр, за которыми следуют четыре буквы

### <a name="pattern"></a>Шаблон

Шесть цифр и четыре буквы:

- Шесть цифр
- Четыре буквы (не чувствительные к делу)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:

- Обычное выражение  `Regex_ireland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_ireland_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Номер паспорта Ирландии

### <a name="format"></a>Формат

Две буквы или цифры, за которыми следуют семь цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

Две буквы или цифры, за которыми следуют семь цифр:

- Две цифры или буквы (не чувствительные к делу)
- семь цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_ireland_eu_passport_number` или найдено.
- Регулярное выражение находит дату в формате `Regex_ireland_eu_passport_date` DD MMM/MMM YYYY (Пример - 01 BEA/MAY 1988) или ключевое слово из `Keywords_eu_passport_date` найденного

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_ireland_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- нумеро passeport
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="ireland-personal-public-service-pps-number"></a>Номер личной государственной службы Ирландии

### <a name="format"></a>Формат

Старый формат (до 31 декабря 2012 г.):
- семь цифр, за которыми следуют 1-2 буквы

Новый формат (1 января 2013 г. и после):
- семь цифр, за которыми следуют две буквы

### <a name="pattern"></a>Шаблон

Старый формат (до 31 декабря 2012 г.):
- семь цифр
- от одной до двух букв (не чувствительных к делу)

Новый формат (1 января 2013 г. и после):
- семь цифр
- буква (не чувствительная к делу), которая является алфавитной цифрой проверки
- Необязательная буква в диапазоне A-I или "W"

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_ireland_pps находит содержимое, которое соответствует шаблону;
- Ключевое слово из Keywords_ireland_eu_national_id_card найдено.
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

- служба удостоверений клиента
- identification number
- личный номер
- личный номер государственной службы
- личная служба нет
- phearsanta seirbhíse poiblí
- pps no
- число pps
- pps num
- служба pps
- ppsn
- ppsno #
- ppsno
- psp
- служба общего государственного обслуживания
- publicserviceno #
- publicserviceno
- номер дохода и социального страхования
- rsi no
- номер rsi
- rsin
- клиент seirbhís aitheantais
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsantais
- uimhir phearsanta seirbhíse poiblí
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="israel-bank-account-number"></a>Номер банковского счета Израиля

### <a name="format"></a>Формат

13 цифр.

### <a name="pattern"></a>Шаблон

Форматированный:
- две цифры
- тире
- три цифры
- тире
- восемь цифр

Unformatted:
- 	13 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

## <a name="israel-national-identification-number"></a>Национальный идентификационный номер Израиля

### <a name="format"></a>Формат

девять цифр

### <a name="pattern"></a>Шаблон

девять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
-   номер id
-   удостоверение нет        
-   identitynumber #
-   номер удостоверения
-   israeliidentitynumber       
-   личный id
-   уникальный id  


## <a name="italy-drivers-license-number"></a>Номер водительских прав в Италии

Этот тип объекта включен в тип конфиденциальной информации о номере лицензии водителя ЕС. Он также доступен в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат

сочетание 10 букв и цифр

### <a name="pattern"></a>Шаблон

сочетание 10 букв и цифр:
- одна буква (не деликатная)
- буквы "A" или "V" (не чувствительные к делу)
- семь цифр
- одна буква (не деликатная)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение `Regex_italy_drivers_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово `Keywords_eu_driver's_license_number` из `Keyword_italy_drivers_license_number` или найдено.

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- патент numero di
- patente di guida
- patente guida
- patenti di guida
- guida patenti


## <a name="italy-fiscal-code"></a>Финансовый код Италии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

16-символьное сочетание букв и цифр в указанном шаблоне

### <a name="pattern"></a>Шаблон

Сочетание букв и цифр в 16 символов:
- три буквы, соответствующие первым трем согласным в фамилии
- три буквы, соответствующие первому, третьему и четвертому согласным с именем
- две цифры, соответствующие последним цифрам года рождения
- в алфавитном порядке используется одна буква, соответствующая букве за месяц рождения, но используются только буквы A к E, H, L, M, P, R к T (так, январь — A и Октябрь — R)
- две цифры, соответствующие дню рождения, чтобы различать полы, добавляется 40 к дню рождения для женщин
- четыре цифры, соответствующие коду области, определенному муниципалитету, в котором родился человек (коды по всей стране используются для иностранных стран)
- одно число паритета

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_italy_eu_national_id_card` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_italy_eu_national_id_card` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- кодике id personale
- личный кодис
- финансовый код
- личный персонал numero certificato
- numero di identificazione fiscale
- личный id numero
- personale numero
- личный номер сертификата
- личный код
- личный код id
- личный номер
- personalcodeno #
- налоговый код
- tax id
- идентификация налога нет
- идентификационный номер налога
- номер налогового удостоверения
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="italy-passport-number"></a>Номер паспорта Италии

### <a name="format"></a>Формат

две буквы или цифры, за которыми следуют семь цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

две буквы или цифры, а затем семь цифр:

- две цифры или буквы (не чувствительные к делу)
- семь цифр

### <a name="checksum"></a>Контрольная сумма

неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_italy_eu_passport_number` или найдено.
- Обычное выражение находит дату в формате `Regex_italy_eu_passport_date` DD MMM/MMM YYYYY (Пример - 01 GEN/JAN 1988) или ключевое слово из `Keywords_eu_passport_date` найденного

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_italy_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="italy-value-added-tax-number"></a>Номер налога на добавленную стоимость в Италии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

13 символов альфанумерного шаблона с необязательными делимитерами

### <a name="pattern"></a>Шаблон

13 символов альфанумерного шаблона с необязательными делимитерами:

- I или i
- T или t
- необязательное пространство, точка, дефис или запятая
- 11 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_italy_value_added_tax_number контента, который соответствует шаблону.
- Найдено ключевое слово Keywords_italy_value_added_tax_number из Keywords_italy_value_added_tax_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_italy_value_added_tax_number контента, который соответствует шаблону.

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

- номер НДС
- vat no
- vat #
- iva
- iva #


## <a name="japan-bank-account-number"></a>Номер банковского счета в Японии

### <a name="format"></a>Формат

семь или восемь цифр

### <a name="pattern"></a>Шаблон

Номер банковского счета:
- семь или восемь цифр
- Код филиала банковского счета:
- четыре цифры
- пространство или тире (необязательно)
- три цифры

Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_jp_bank_account находит содержимое, которое соответствует шаблону;
- Находится ключевое слово из Keyword_jp_bank_account.
- Верно одно из условий ниже:
- функция Func_jp_bank_account_branch_code находит содержимое, которое соответствует шаблону;
- найдено ключевое слово из Keyword_jp_bank_branch_code.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

## <a name="japan-drivers-license-number"></a>Номер водительских прав в Японии

### <a name="format"></a>Формат

12 цифр.

### <a name="pattern"></a>Шаблон

12 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- slicense драйвера
- driverslicenses
- срезы драйвера
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
- 運転免許証 Нет.
- 運転免許 Нет.
- 免許証 Нет.
- 免許 Нет.
- 運転免許証 #
- 運転免許 #
- 免許証 #
- 免許 #


## <a name="japan-my-number---corporate"></a>Япония Мой номер — корпоративная
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

13-значный номер

### <a name="pattern"></a>Шаблон

13-значный номер:

- одна цифра от одной до девяти
- 12 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_japanese_my_number_corporate контента, который соответствует шаблону.
- Ключевое слово Keywords_japanese_my_number_corporate найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_japanese_my_number_corporate контента, который соответствует шаблону.

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


## <a name="japan-my-number---personal"></a>Япония Мой номер - Личный
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

12-значный номер

### <a name="pattern"></a>Шаблон

12-значный номер:

- четыре цифры
- необязательный пробел, точка или дефис
- четыре цифры
- необязательный пробел, точка или дефис
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_japanese_my_number_personal контента, который соответствует шаблону.
- Ключевое слово Keywords_japanese_my_number_personal найдено.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_japanese_my_number_personal контента, который соответствует шаблону.

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


## <a name="japan-passport-number"></a>Номер паспорта Японии

### <a name="format"></a>Формат

две буквы, за которыми следуют семь цифр

### <a name="pattern"></a>Шаблон

две буквы (не чувствительные к делу), за которыми следуют семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

- Паспорт
- Passport Number
- Паспорт No.
- Passport#
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パポ.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Номер карты проживания в Японии

### <a name="format"></a>Формат

12 букв и цифр

### <a name="pattern"></a>Шаблон

12 букв и цифр:
- две буквы (не чувствительные к делу)
- восемь цифр
- две буквы (не чувствительные к делу)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Регулярное выражение Regex_jp_residence_card_number контент, который соответствует шаблону.
- Ключевое слово Keyword_jp_residence_card_number найдено.

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

- Номер карточки residence
- Карточка residence no
- Карточка residence #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>Регистрационный номер резидента Японии

### <a name="format"></a>Формат

11 цифр.

### <a name="pattern"></a>Шаблон

11 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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


## <a name="japan-social-insurance-number-sin"></a>Номер социального страхования Японии (SIN)

### <a name="format"></a>Формат

7–12 цифр.

### <a name="pattern"></a>Шаблон

7–12 цифр
- четыре цифры
- дефис (необязательный)
- шесть цифр OR
- 7–12 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_jp_sin находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_jp_sin.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- 社会保険 Нет.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Номер водительских прав в Латвии

### <a name="format"></a>Формат

три буквы, за которыми следуют шесть цифр

### <a name="pattern"></a>Шаблон

три буквы и шесть цифр:

- три буквы (не чувствительные к делу)
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_latvia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_latvia_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Персональный код Латвии

### <a name="format"></a>Формат

11 цифр и необязательный дефис

### <a name="pattern"></a>Шаблон

Старый формат

11 цифр и дефис:

- шесть цифр, соответствующих дате рождения (DDMMYY)
- дефис
- одна цифра, соответствующая столетию рождения ("0" для 19-го века, "1" для 20-го века и "2" для 21-го века)
- четыре цифры, случайно созданные

Новый формат

11 цифр.

- Две цифры "32"
- девять цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция или  `Func_latvia_eu_national_id_card` regex находит `Regex_latvia_eu_national_id_card_new_format` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_latvia_eu_national_id_card` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- alvas nē
- число рождения
- номер гражданина
- гражданский номер
- электронный номер переписи
- электронный номер
- финансовый код
- номер пользователя системы здравоохранения
- id #
- id-code
- identification number
- numurs identifikācijas
- id-number
- отдельный номер
- latvija alva
- nacionālais id
- national id
- номер национального идентификации
- номер национального удостоверения
- national insurance number
- номер национального реестра
- нумуры nodokļa
- nodokльu id
- nodokльu identifikācija numurs
- личный номер сертификата
- личный код
- личный код id
- личный номер
- личный код идентификации
- личный идентификатор
- личный номер удостоверения
- личный номер
- личный числимый код
- personalcodeno #
- personas kods
- код идентификации населения
- номер общедоступных служб
- registration number
- номер выручки
- social insurance number
- social security number
- налоговый код штата
- tax file number
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- номер избирателя

## <a name="latvia-passport-number"></a>Номер паспорта Латвии

### <a name="format"></a>Формат

две буквы или цифры, за которыми следуют семь цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

две буквы или цифры, а затем семь цифр:

- две цифры или буквы (не чувствительные к делу)
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_latvia_eu_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_latvia_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="lithuania-drivers-license-number"></a>Номер водительских прав Литвы

### <a name="format"></a>Формат

восемь цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_lithuania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_lithuania_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver s_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>Личный код Литвы
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

11 цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

11 цифр без пробелов и делимитеров:

- одна цифра (1-6), соответствующая полу и столетию рождения
- шесть цифр, соответствующих дате рождения (YYMMDD)
- три цифры, соответствующие серийному номеру даты рождения
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_lithuania_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_lithuania_eu_tax_file_number` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- номер службы гражданина
- mokesči. id
- mokesči . identifikavimas numeris
- mokesči . identifikavimo numeris
- mokesči . numeris
- national identification number
- личный код
- личный числимый код
- piliečio paslaugos numeris
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- unikalus identifikavimo kodas
- число unikalus identifikavimo
- уникальный идентификационный номер
- уникальный номер удостоверения
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Номер паспорта Литвы

### <a name="format"></a>Формат

восемь цифр или букв без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

восемь цифр или букв (не чувствительных к делу)

### <a name="checksum"></a>Контрольная сумма

неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_lithuania_eu_passport_number` или найдено.
- Регулярное выражение `Regex_eu_passport_date3` находит дату в формате DD MM YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_lithuania_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="luxemburg-drivers-license-number"></a>Номер водительских прав в Люксембурге

### <a name="format"></a>Формат

шесть цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_luxemburg_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_luxemburg_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver s_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Национальный идентификационный номер Люксембурга (естественные лица)
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

13 цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

13 цифр:

- 11 цифр.
- две контрольные цифры

### <a name="checksum"></a>Контрольная сумма

да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_luxemburg_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_luxemburg_eu_national_id_card` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- индивидуальный id
- индивидуальная идентификация
- индивидуальное удостоверение
- numéro d'identification personnel
- личный id
- личная идентификация
- персональный идентификатор
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- уникальный id
- уникальный идентификатор
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Номер паспорта Люксембурга

### <a name="format"></a>Формат

восемь цифр или букв без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

восемь цифр или букв (не чувствительных к делу)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_luxemburg_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_luxemburg_eu_passport_number` или найдено.
- Регулярное выражение `Regex_eu_passport_date3` находит дату в формате DD MM YYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_luxemburg_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_luxemburg_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- пропуск люксембурга
- люксембургский пасспорт
- люксембургский паспорт
- no de passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- nombre passeport
- reisepässe
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Номер национальной идентификации в Люксембурге (не естественное лицо)

### <a name="format"></a>Формат

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр.

- две цифры
- необязательный пробел
- три цифры
- необязательный пробел
- три цифры
- необязательный пробел
- две цифры
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_luxemburg_eu_tax_file_number_non_natural` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_luxemburg_eu_tax_file_number` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- люксембургский налоговый identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identification fiscale
- social security
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier id
- steier identifikatiounsnummer
- steier nummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Номер удостоверения личности Малайзии

### <a name="format"></a>Формат

12 цифр, содержащих необязательные дефисы.

### <a name="pattern"></a>Шаблон

12 цифр:
- шесть цифр в формате YYMMDD, которые являются датой рождения
- тире (необязательный)
- двух-буквный код места рождения
- тире (необязательный)
- три случайных цифры
- однозначный гендерный код

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

- карта цифрового приложения
- i/c
- i/c нет
- ic
- IC нет
- id card
- удостоверение личности
- identity card
- k/p
- k/p нет
- kad akuan diri
- kad aplikasi digital
- Kad pengenalan Malaysia
- kp
- kp нет
- mykad
- mykas
- mykid
- mypr
- mytentera
- Удостоверение личности Малайзии
- малайзийские удостоверения личности
- nric
- личные удостоверения личности

## <a name="malta-drivers-license-number"></a>Номер водительского удостоверения Мальты

### <a name="format"></a>Формат

Сочетание двух символов и шести цифр в указанном шаблоне

### <a name="pattern"></a>Шаблон

сочетание двух символов и шести цифр:

- два символа (цифры или буквы, не чувствительные к делу)
- пробел (необязательный)
- три цифры
- пробел (необязательный)
- три цифры

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_malta_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_malta_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver s_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>Номер удостоверения личности Мальты
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

семь цифр, за которыми следует одна буква

### <a name="pattern"></a>Шаблон

семь цифр, за которыми следует одна буква:

- семь цифр
- одна буква в "M, G, A, P, L, H, B, Z" (случай нечувствительный)

### <a name="checksum"></a>Контрольная сумма

Неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_malta_eu_national_id_card` слово.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону.

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

- номер службы гражданина
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi цифры personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- личный числимый код
- уникальный идентификационный номер
- уникальный номер удостоверения
- uniqueidentityno #


## <a name="malta-passport-number"></a>Номер паспорта Мальты

### <a name="format"></a>Формат

семь цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_malta_eu_passport_number` или найдено.
- Найдено `Keywords_eu_passport_date` ключевое слово

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_malta_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="malta-tax-identification-number"></a>Номер идентификации налога На Мальте

### <a name="format"></a>Формат

Для граждан Мальты:
- семь цифр и одна буква в указанном шаблоне

Не мальтийские граждане и мальтийские юридические лица:
- девять цифр

### <a name="pattern"></a>Шаблон

Граждане Мальты: семь цифр и одна буква

- семь цифр
- одна буква (не деликатная)

Не мальтийские граждане и мальтийские сущностями: девять цифр

- девять цифр

### <a name="checksum"></a>Контрольная сумма

Неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Regex  `Regex_malta_eu_tax_file_number`  или `Regex_malta_eu_tax_file_number_non_maltese_national` находит содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_malta_eu_tax_file_number` слово.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

- номер службы гражданина
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi цифры personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- личный числимый код
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- уникальный идентификационный номер
- уникальный номер удостоверения
- uniqueidentityno #


## <a name="medicare-beneficiary-identifier-mbi-card"></a>Идентификатор бенефициара Medicare (MBI)

### <a name="format"></a>Формат

Альфанумерный шаблон 11 символов

### <a name="pattern"></a>Шаблон

- одна цифра от 1 до 9
- одна буква, за исключением S, L, O, I, B, Z
- одна цифра или буква, за исключением S, L, O, I, B, Z
- одна цифра
- необязательный дефис
- одна буква, за исключением S, L, O, I, B, Z
- одна цифра или буква, за исключением S, L, O, I, B, Z
- одна цифра
- необязательный дефис
- две буквы, за исключением S, L, O, I, B, Z
- две цифры

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_mbi_card` находит содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keyword_mbi_card` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_mbi_card` находит содержимое, которое соответствует шаблону.

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi #
- получатель medicare #
- идентификатор бенефициара medicare
- получателя medicare нет
- номер получателя medicare
- получатель medicare #


## <a name="mexico-unique-population-registry-code-curp"></a>Код реестра уникальных популяций Мексики (CURP)

### <a name="format"></a>Формат

Альфанумерный шаблон 18 символов

### <a name="pattern"></a>Шаблон

- четыре буквы (случай нечувствительный)
- шесть цифр с указанием допустимой даты
- письмо - H/h или M/m
- два буквы, указывающие допустимый мексиканский код состояния
- три буквы
- одна буква или цифра
- одна цифра

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_mexico_population_registry_code` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keyword_mexico_population_registry_code` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция находит  `Func_mexico_population_registry_code` содержимое, которое соответствует шаблону.

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- Уникальный код реестра населения 
- уникальный код населения
- CURP
- Личный ID
- Уникальный ID
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave personal Identidad
- личный Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>Номер службы гражданина Нидерландов (BSN)

### <a name="format"></a>Формат

восемь или девять цифр, содержащих необязательные пробелы

### <a name="pattern"></a>Шаблон

восемь-девять цифр:
- три цифры
- пробел (необязательный)
- три цифры
- пробел (необязательный)
- две-три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- burgerservicenummer
- номер службы гражданина
- номер лица
- личный номер
- личный числимый код
- номер, связанный с человеком
- persoonlijk nummer
- код numerieke persoonlijke
- persoonsgebonden
- persoonsnummer
- nummer sociaal-fiscaal
- социально-финансовый номер
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- уникальный идентификационный номер
- уникальный номер удостоверения
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Номер водительских прав Нидерландов

### <a name="format"></a>Формат

10 цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

10 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_netherlands_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_netherlands_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Номер паспорта Нидерландов

### <a name="format"></a>Формат

девять букв или цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

девять букв или цифр

### <a name="checksum"></a>Контрольная сумма

неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_netherlands_eu_passport_number` или найдено.
- Регулярное выражение находит дату в формате `Regex_netherlands_eu_passport_date` DD MMM/MMM YYYY (Пример - 26 MAA/MAR 2012)

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_netherlands_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- nummer paspoort
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>Номер налоговой идентификации в Нидерландах
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

девять цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_netherlands_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_netherlands_eu_tax_file_number` слово.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- идентификация налога в Нидерландах
- идентификация налога в Нидерландах
- олово Нидерландов
- олово Нидерландов
- tax id
- идентификация налога нет
- идентификационный номер налога
- tal идентификации налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- налоговый тал
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="netherlands-value-added-tax-number"></a>Номер налога на добавленную стоимость в Нидерландах
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

Альфанумерный шаблон 14 символов

### <a name="pattern"></a>Шаблон

14-символический альфанумерный шаблон:

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

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_netherlands_value_added_tax_number контента, который соответствует шаблону.
- Найдено ключевое слово Keywords_netherlands_value_added_tax_number.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_netherlands_value_added_tax_number контента, который соответствует шаблону.

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

- номер НДС
- vat no
- vat #
- wearde tafoege tax getal
- btw nūmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Номер банковского счета в Новой Зеландии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

14-значный и 16-значный шаблон с необязательным делимитером

### <a name="pattern"></a>Шаблон

14-значный и 16-значный шаблон с необязательным делимитером:

- две цифры
- необязательный дефис или пространство
- три-четыре цифры
- необязательный дефис или пространство
- семь цифр
- необязательный дефис или пространство
- две-три цифры
- дефис параметров или пространство

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_new_zealand_bank_account_number контента, который соответствует шаблону.
- Ключевое слово Keywords_new_zealand_bank_account_number найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_new_zealand_bank_account_number контента, который соответствует шаблону.

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
- банковский счет
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>Номер водительского удостоверения Новой Зеландии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

восемь шаблонов альфа-цифр символов

### <a name="pattern"></a>Шаблон

восемь шаблонов альфа-цифр символов

- две буквы
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_newzealand_driver_license_number контента, который соответствует шаблону.
- Ключевое слово из Keywords_newzealand_driver_license_number найдено.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_newzealand_driver_license_number контента, который соответствует шаблону.

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
- lic драйвера
- водительское удостоверение
- водительские права
- driverslic
- driverslicence
- driverslicences
- драйверы lic
- lics драйверов
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- driver'slic
- slics драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's licence
- водительские права
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительское удостоверение #
- водительские права #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- international driving permit
- international driving permits
- Автомобильная ассоциация nz
- автомобильная ассоциация Новой Зеландии


## <a name="new-zealand-inland-revenue-number"></a>Число внутренних доходов Новой Зеландии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

восемь или девять цифр с необязательными делимитерами

### <a name="pattern"></a>Шаблон

восемь или девять цифр с необязательными делимитерами

- две или три цифры
- необязательный пробел или дефис
- три цифры
- необязательный пробел или дефис
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_new_zealand_inland_revenue_number контента, который соответствует шаблону.
- Ключевое слово Keywords_new_zealand_inland_revenue_number найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_new_zealand_inland_revenue_number контента, который соответствует шаблону.

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

- ird Нет.
- ird no #
- nz ird
- ird Новой Зеландии
- ird number
- число внутренних доходов


## <a name="new-zealand-ministry-of-health-number"></a>Номер министерства здравоохранения Новой Зеландии

### <a name="format"></a>Формат

три буквы, пространство (необязательно) и четыре цифры

### <a name="pattern"></a>Шаблон

- три буквы (не чувствительные к делу), кроме "I" и "O"
- пробел (необязательный)
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_new_zealand_ministry_of_health_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_nz_terms;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- Номер национального индекса здоровья
- nhi number
- nhi нет.
- NHI #
- Национальный индекс здоровья No.
- Национальный индекс здоровья
- Национальный индекс здоровья #

## <a name="new-zealand-social-welfare-number"></a>Номер социального обеспечения в Новой Зеландии

Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

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

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_newzealand_social_welfare_number контент, который соответствует шаблону.
- Ключевое слово Keywords_newzealand_social_welfare_number найдено.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_newzealand_social_welfare_number контент, который соответствует шаблону.

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

- социальное обеспечение #
- социальное обеспечение #
- No социального обеспечения.
- номер социального обеспечения
- swn #


## <a name="norway-identification-number"></a>Идентификационный номер Норвегии

### <a name="format"></a>Формат

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр:
- шесть цифр в формате DDMMYY, которые являются датой рождения
- трехзначный индивидуальный номер
- две контрольные цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_norway_id_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_norway_id_number;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- Fødselsnummer


## <a name="philippines-unified-multi-purpose-identification-number"></a>Филиппины единый многоцелевой идентификационный номер

### <a name="format"></a>Формат

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

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

## <a name="poland-drivers-license-number"></a>Номер водительских прав в Польше

### <a name="format"></a>Формат

14 цифр, содержащих две косые черты

### <a name="pattern"></a>Шаблон

14 цифр и две косые черты:

- пять цифр
- перенарезаемая косая черта
- две цифры
- перенарезаемая косая черта
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_poland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_poland_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Удостоверение личности в Польше

### <a name="format"></a>Формат

три буквы и шесть цифр

### <a name="pattern"></a>Шаблон

три буквы (не чувствительные к делу) с последующим шестью цифрами

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

- Особист dowód
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.



## <a name="poland-national-id-pesel"></a>Польский национальный ID (PESEL)

### <a name="format"></a>Формат

11 цифр.

### <a name="pattern"></a>Шаблон

- шесть цифр, представляющих дату рождения в формате YYMMDD
- четыре цифры
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_pesel_identification_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_pesel_identification_number;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- numer identyfikacyjny
- pesel
- tożsamości narodowej


## <a name="poland-passport-number"></a>Номер паспорта Польши
Этот тип конфиденциальной информации входит в тип конфиденциальной информации номера паспорта ЕС. Он также доступен в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат

две буквы и семь цифр

### <a name="pattern"></a>Шаблон

Две буквы (не чувствительные к делу) с семью цифрами

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит `Func_polish_passport_number_v2` содержимое, которое соответствует шаблону.
- Контрольная сумма проходит проверку.
- Ключевое слово `Keywords_eu_passport_number` из `Keyword_polish_national_passport_number` или найдено.
- Найдено ключевое `Keywords_eu_passport_date` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция находит `Func_polish_passport_number_v2` содержимое, которое соответствует шаблону.
- Контрольная сумма проходит проверку.
- Ключевое слово `Keywords_eu_passport_number` из `Keyword_polish_national_passport_number` или найдено.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит `Func_polish_passport_number_v2` содержимое, которое соответствует шаблону.
- Контрольная сумма проходит проверку.

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- nr. paszportu
- nr paszportów
- n° passeport
- passeport n°

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="poland-regon-number"></a>Номер REGON в Польше
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

9-значный или 14-значный номер

### <a name="pattern"></a>Шаблон

девять цифр или 14-значное число:

- девять цифр или
- девять цифр
- дефис
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_polish_regon_number контента, который соответствует шаблону.
- Ключевое слово Keywords_polish_regon_number найдено.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_polish_regon_number контента, который соответствует шаблону.

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
- статистический id
- статистический нет
- номер regon
- regonid #
- regonno #
- ID компании
- companyid #
- companyidno #
- numer statystyczny
- regon numeru
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Номер налоговой идентификации в Польше
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

11 цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

11 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

- NIP #
- NIP
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- vat id #
- vat id
- vat no
- номер НДС
- vatid #
- vatid
- vatno #


## <a name="portugal-citizen-card-number"></a>Номер карточки гражданина Португалии

### <a name="format"></a>Формат

восемь цифр

### <a name="pattern"></a>Шаблон

восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

- bilhete de identidade
- cartão de cidadão
- карточка гражданина
- номер документа
- documento de identificação
- номер id
- идентификация no
- identification number
- удостоверение нет
- номер удостоверения
- национальная id-карта
- nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- номер bi португалии


## <a name="portugal-drivers-license-number"></a>Номер водительских прав Португалии

### <a name="format"></a>Формат

два шаблона : две буквы с 5-8 цифрами со специальными символами

### <a name="pattern"></a>Шаблон

Шаблон 1. Две буквы, за которыми следуют 5/6 со специальными символами:
- Две буквы (не чувствительные к делу)
- дефис;
- Пять или шесть цифр
- Пробел
- Одна цифра

Шаблон 2. Одна буква с 6/8 цифрами со специальными символами:
- Одна буква (не деликатная)
- дефис;
- Шесть или восемь цифр
- Пробел
- одна цифра.


### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_portugal_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_portugal_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver s_license_number

- carteira de motorista
- motorista carteira
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>Номер паспорта Португалии

### <a name="format"></a>Формат

одна буква с шестью цифрами без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

одна буква с шестью цифрами:

- одна буква (не деликатная)
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_portugal_eu_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_portugal_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- португальский паспорт
- португальский пасспорт
- португальский passaporte
- passaporte nº
- passeport nº
- números de passaporte
- португальские паспорта
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="portugal-tax-identification-number"></a>Идентификация налога в Португалии

### <a name="format"></a>Формат

девять цифр с необязательными пробелами

### <a name="pattern"></a>Шаблон

- три цифры
- необязательный пробел
- три цифры
- необязательный пробел
- три цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_portugal_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_portugal_eu_tax_file_number` слово.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="romania-drivers-license-number"></a>Номер лицензии водителя в Румынии

### <a name="format"></a>Формат

один символ с восемью цифрами

### <a name="pattern"></a>Шаблон

один символ с восемью цифрами:
- одна буква (не чувствительная к делу) или цифра
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_romania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_romania_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver s_license_number

- permis de conducere
- permisului de conducere
- permisului
- permisele de conducere
- благоприятные условия для допустимой мисели
- допустимые условия

## <a name="romania-personal-numeric-code-cnp"></a>Личный числимый код Румынии (CNP)
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

13 цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

- одна цифра из 1-9
- шесть цифр, представляющих дату рождения (YYMMDD)
- две цифры, которые могут быть 01-52 или 99
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_romania_eu_national_id_card` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_romania_eu_national_id_card` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

- cNP #
- cNP
- код identificare личный
- цифровая кодовая личная
- код unic identificare
- codnumericpersonal #
- кодул финансовый nr.
- identificarea fiscală nr #
- id-ul taxei
- номер страховки
- insurancenumber #
- национальный id #
- national id
- national identification number
- număr identificare personal
- număr identitate
- număr personal unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- личный числимый код
- пин-код #
- пин-код
- налоговый файл нет
- tax file number
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #
- уникальный идентификационный номер
- уникальный номер удостоверения
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Номер паспорта Румынии

### <a name="format"></a>Формат

восемь или девять цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

восемь или девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_romania_eu_passport_number` или найдено.
- Регулярное выражение находит дату в формате `Regex_romania_eu_passport_date` DD MMM/MMM YY (Пример- 01 FEB/FEB 10) или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_romania_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul paşaportului numarul pasaportului numerele paşaportului paşaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="russia-passport-number-domestic"></a>Номер паспорта России внутренний
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

10-значный номер

### <a name="pattern"></a>Шаблон

10-значный номер:

- две цифры
- необязательный пробел или дефис
- две цифры
- необязательный пробел
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- В regex Regex_Russian_Passport_Number_Domestic контент, который соответствует шаблону.
- Ключевое слово Keyword_Russian_Passport_Number найдено.

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
- паспорт нет
- паспорт #
- id паспорта
- passportno #
- passportnumber #
- паспорт нет
- ID
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- 100 000 #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Номер паспорта России
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

девятизначный номер

### <a name="pattern"></a>Шаблон

девятизначный номер:

- две цифры
- необязательный пробел или дефис
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- В regex Regex_Russian_Passport_Number_International контент, который соответствует шаблону.
- Ключевое слово Keyword_Russian_Passport_Number найдено.

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
- паспорт нет
- паспорт #
- id паспорта
- passportno #
- passportnumber #
- паспорт нет
- ID
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- 100 000 #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Национальный идентификатор для Саудовской Аравии

### <a name="format"></a>Формат

10 цифр.

### <a name="pattern"></a>Шаблон

10 последовательных цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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


## <a name="singapore-national-registration-identity-card-nric-number"></a>Номер удостоверения удостоверения национальной регистрации Сингапура (NRIC)

### <a name="format"></a>Формат

девять букв и цифр

### <a name="pattern"></a>Шаблон

- девять букв и цифр:
- буквы "F", "G", "S" или "T" (не чувствительны к делу)
- семь цифр
- цифру проверки алфавита

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_singapore_nric;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

## <a name="slovakia-drivers-license-number"></a>Номер лицензии водителя Словакии

### <a name="format"></a>Формат

один символ, за которым следуют семь цифр

### <a name="pattern"></a>Шаблон

один символ, за которым следуют семь цифр

- одна буква (не чувствительная к делу) или цифра
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_slovakia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_slovakia_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver s_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>Личный номер Словакии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

9 или 10 цифр, содержащих необязательный ответный ответ

### <a name="pattern"></a>Шаблон

- шесть цифр, представляющих дату рождения
- необязательный слэш (/)
- три цифры
- одна необязательная цифра проверки

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_slovakia_eu_national_id_card` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_slovakia_eu_national_id_card` слово.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- число рождения
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daпечи číslo
- номер id
- идентификация no
- identification number
- identifikačná karta č
- identifikačné číslo
- удостоверение нет
- номер удостоверения
- národná identifikačná značka č
- национальный номер
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- Rodne cislo
- rodné číslo
- social security number
- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- налоговый файл нет
- tax file number
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #

## <a name="slovakia-passport-number"></a>Номер паспорта Словакии

### <a name="format"></a>Формат

одна цифра или буква, за которыми следуют семь цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

одна цифра или буква (не чувствительные к делу) с последующим семизначным числом

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_slovakia_eu_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_slovakia_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č.
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="slovenia-drivers-license-number"></a>Номер лицензии водителя Словении

### <a name="format"></a>Формат

девять цифр без пробелов и делимитеров

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_slovenia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_slovenia_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver s_license_number

- vozniško dovoljenje
- лицензия vozniška številka
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Уникальный номер гражданина Словении
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

13 цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

13 цифр в указанном шаблоне:

- семь цифр, соответствующих дате рождения (DDMMLLL), где "LLL" соответствует последним трем цифрам года рождения
- две цифры, соответствующие области рождения "50"
- три цифры, соответствующие сочетанию пола и серийного номера для лиц, родившихся в один день. 000-499 для мужчин и 500-999 для женщин.
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_slovenia_eu_national_id_card` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_slovenia_eu_national_id_card` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- identity card
- nacionalna id
- список потни nacionalni
- national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- личный код
- личный номер
- личный числимый код
- številka državljana
- уникальный номер гражданина
- уникальный номер id
- уникальный номер удостоверения
- уникальный номер гражданина
- уникальный регистрационный номер
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Номер паспорта Словении

### <a name="format"></a>Формат

две буквы, за которыми следуют семь цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

две буквы, за которыми следуют семь цифр:

- буква "P"
- одно верхнее письмо
- семь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_slovenia_eu_passport_number` или найдено.
- Обычное выражение `Regex_eu_passport_date1` находит дату в формате DD.MM.YYYYY или ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_slovenia_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- список potni #
- datum rojstva
- список potni
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="slovenia-tax-identification-number"></a>Идентификационный номер налога в Словении
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

восемь цифр без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

- одна цифра из 1-9
- шесть цифр
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_slovenia_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_slovenia_eu_tax_file_number` слово.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- налоговый файл нет
- tax file number
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="south-africa-identification-number"></a>Идентификационный номер Южной Африки

### <a name="format"></a>Формат

13 цифр, которые могут содержать пробелы.

### <a name="pattern"></a>Шаблон

13 цифр:
- шесть цифр в формате YYMMDD, которые являются датой рождения
- четыре цифры
- однозначный индикатор гражданства
- цифры "8" или "9"
- одна цифра, которая является цифрой чека

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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

## <a name="south-korea-resident-registration-number"></a>Номер регистрации резидента Южной Кореи

### <a name="format"></a>Формат

13 цифр, содержащих дефис.

### <a name="pattern"></a>Шаблон

13 цифр:
- шесть цифр в формате YYMMDD, которые являются датой рождения
- дефис
- одна цифра, определяемая веком и полом
- четырехзначный код региона рождения
- одна цифра, используемая для дифференцировки людей, для которых предыдущие номера идентичны
- контрольная цифра.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_south_korea_resident_number;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

## <a name="spain-drivers-license-number"></a>Номер водительских прав Испании

### <a name="format"></a>Формат

восемь цифр, за которыми следует один символ

### <a name="pattern"></a>Шаблон

восемь цифр, за которыми следует один символ:

- восемь цифр
- одна цифра или буква (не чувствительные к делу)

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция или  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` поиск контента, который соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_spain_eu_driver's_license_number` или найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция или  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` поиск контента, который соответствует шаблону.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver s_license_number

- permiso de conducción
- permiso conducción
- licencia de conducir
- licencia conducir
- permiso conducir
- permiso de conducir
- permisos de conducir
- разрешимые permisos
- carnet conducir
- carnet de conducir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>DNI Испании
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

восемь цифр, за которыми следует один символ

### <a name="pattern"></a>Шаблон

семь цифр, за которыми следует один символ

- восемь цифр
- Необязательный пробел или дефис
- одно чековая буква (не чувствительное к делу)

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция или  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` поиск контента, который соответствует шаблону.
- Найдено ключевое  `Keywords_spain_eu_national_id_card"` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция или  `Func_spain_eu_DL_and_NI_number_citizen` `Func_spain_eu_DL_and_NI_number_foreigner` поиск контента, который соответствует шаблону.


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
- номер страховки
- national identification number
- национальная идентичность
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- личный идентификационный номер
- личные удостоверения нет
- уникальный номер удостоверения
- uniqueid #

## <a name="spain-passport-number"></a>Номер паспорта Испании

### <a name="format"></a>Формат

сочетание букв и номеров с восемью или девятью символами без пробелов или делимитеров

### <a name="pattern"></a>Шаблон

сочетание букв и номеров с восемью или девятью символами:

- две цифры или буквы
- одна цифра или буква (необязательно)
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Неприменимо

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_spain_eu_passport_number` или найдено.
- Регулярное выражение `Regex_spain_eu_passport_date` находит дату в формате DD-MM-YYYYY или найдено ключевое слово `Keywords_eu_passport_date` из

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_passport_number` из `Keywords_spain_eu_passport_number` или найдено.

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

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte нет.
- pasaporte n°
- Паспорт Испании

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="spain-social-security-number-ssn"></a>Номер социального обеспечения Испании (SSN)


### <a name="format"></a>Формат

11–12 цифр.

### <a name="pattern"></a>Шаблон

11-12 цифр:
- две цифры
- косая черта (необязательный)
- семь-восемь цифр
- косая черта (необязательный)
- две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_spanish_social_security_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.
- - Найдено ключевое  `Keywords_spain_eu_ssn_or_equivalent` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- функция Func_spanish_social_security_number находит содержимое, которое соответствует шаблону;
- Контрольная сумма проходит проверку.

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- ssn #
- socialsecurityno
- социального обеспечения нет
- social security number
- número de la seguridad social

## <a name="spain-tax-identification-number"></a>Идентификация налога в Испании
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

семь или восемь цифр и одна или две буквы в указанном шаблоне

### <a name="pattern"></a>Шаблон

Испанские граждане с национальным удостоверением личности Испании:

- восемь цифр
- одно верхнее письмо (чувствительный к делу)

Испанцы-нерезиденты без национального удостоверения личности Испании

- одно верхнее письмо "L" (чувствительный к делу)
- семь цифр
- одно верхнее письмо (чувствительный к делу)

Resident Spaniards under the age of 14 years without a Spain National Identity Card:

- одно верхнее письмо "K" (чувствительный к делу)
- семь цифр
- одно верхнее письмо (чувствительный к делу)

Иностранцы с идентификационным номером иностранца

- одно верхнее письмо с буквами "X", "Y" или "Z" (чувствительные к делу)
- семь цифр
- одно верхнее письмо (чувствительный к делу)

Иностранцы без идентификации иностранца

- одно верхнее письмо с буквой "M" (чувствительный к делу)
- семь цифр
- одно верхнее письмо (чувствительный к делу)

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция или  `Func_spain_eu_tax_file_number` `Func_spain_eu_DL_and_NI_number_citizen` поиск контента, который соответствует шаблону.
- Найдено ключевое  `Keywords_spain_eu_tax_file_number` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция или  `Func_spain_eu_tax_file_number` `Func_spain_eu_DL_and_NI_number_citizen` поиск контента, который соответствует шаблону.

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
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- налоговый файл нет
- tax file number
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="sql-server-connection-string"></a>SQL Server подключения

### <a name="format"></a>Формат

Строка "User Id", "User ID", "uid" или "UserId" с символами и строками, описанными в приведенной ниже схеме.

### <a name="pattern"></a>Шаблон

- строки "User Id", "User ID", "uid" или "UserId"
- любое сочетание между 1-200 буквами нижнего или верхнего шкафа, цифрами, символами, специальными символами или пробелами
- строка "Пароль" или "pwd", где "pwd" не предшествует букве нижнего регистра
- равный знак (=)
- любой символ, который не является символом доллара ($), процентным символом (%), больше символа (>), в символе (@), кавычках ("), зайколоне (;), левом скобке ([) или левой скобке ({)
- любое сочетание из 7-128 символов, которые не являются полуколоном (;), слэшом (/) или кавычками ()
- полуколон (;) или кавычка ()

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Регулярное выражение CEP_Regex_SQLServerConnectionString находит содержимое, которое соответствует шаблону.
- Ключевое слово CEP_GlobalFilter не найдено.
- Обычное выражение CEP_PasswordPlaceHolder не находит контент, который соответствует шаблону.
- Обычное выражение CEP_CommonExampleKeywords не находит контент, который соответствует шаблону.

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

Этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.

- Пароль или pwd с 0-2 пробелами, равным знаком (=), пробелами 0-2 и звездочкой (*) -OR-
- Пароль или pwd, за которыми следуют:
    - Равный знак (=)
    - Меньше символа (<)
    - Любое сочетание 1-200 символов, которые являются буквами верхнего или нижнего регистра, цифрами, звездочкой (*), дефисом (-), подчеркнув (_) или символом whitespace
    - Больше символа (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

Этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.

- contoso
- fabrikam
- northwind
- песочница
- onebox
- localhost
- 127.0.0.1
- тесты.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>Номер водительских прав Швеции

### <a name="format"></a>Формат

10 цифр, содержащих дефис.

### <a name="pattern"></a>Шаблон

10 цифр, содержащих дефис:

- шесть цифр
- дефис
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Обычное выражение  `Regex_sweden_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.
- Ключевое слово  `Keywords_eu_driver's_license_number` из `Keywords_sweden_eu_driver's_license_number` или найдено.

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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver s_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- kuljettajat lic.
- drivere lic.
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>Национальный ID Швеции

### <a name="format"></a>Формат

10 или 12 цифр и дополнительный разделитель.

### <a name="pattern"></a>Шаблон

10 или 12 цифр с необязательным разделителем
- две цифры (необязательно)
- Шесть цифр в формате даты ГГММДД.
- delimiter из "-" или "+" (необязательно)
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит `Func_swedish_national_identifier` содержимое, которое соответствует шаблону.
- Найдено `Keywords_swedish_national_identifier` ключевое слово
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- номер id
- id #
- идентификация no
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- документ удостоверения
- удостоверение нет
- номер удостоверения
- id-nummer
- личный id
- personnummer #
- personnummer
- skatteidentifikationsnummer

## <a name="sweden-passport-number"></a>Номер паспорта Швеции

### <a name="format"></a>Формат

восемь цифр

### <a name="pattern"></a>Шаблон

восемь последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_sweden_passport_number находит содержимое, которое соответствует шаблону.
- ключевое слово `Keywords_eu_passport_number` или `Keyword_sweden_passport` найдено.
- обычное выражение находит дату в формате `Regex_sweden_eu_passport_date` DD MMM/MMM YY (01 JAN/JAN 12) или ключевое слово `Keywords_eu_passport_date` из найденного.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- регулярное выражение Regex_sweden_passport_number находит содержимое, которое соответствует шаблону.
- ключевое слово `Keywords_eu_passport_number` или `Keyword_sweden_passport` найдено.


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- инопланетная карта регистрации
- сборы за обработку g3
- несколько записей
- Numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passnummer
- pass nr
- шенгенская виза
- шенгенские визы
- одна запись
- sverige pass
- visa requirements
- обработка виз
- тип визы

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- дата выпуска
- дата истечения срока действия


## <a name="sweden-tax-identification-number"></a>Номер налоговой идентификации в Швеции
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

10 цифр и символ в указанном шаблоне

### <a name="pattern"></a>Шаблон

10 цифр и символ:

- шесть цифр, соответствующих дате рождения (YYMMDD)
- знак плюс или минус
- три цифры, которые делают идентификационный номер уникальным, где:
  - для номеров, выдавшихся до 1990 г., седьмая и восьмая цифры определяют округ родившихся или родившихся за
  - цифра в девятой позиции указывает пол по нечетным для мужчин или даже для женщин
- одна контрольная цифра

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит  `Func_sweden_eu_tax_file_number` содержимое, которое соответствует шаблону.
- Найдено ключевое  `Keywords_sweden_eu_tax_file_number` слово.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- кадетский id nummer
- идентификация фигурного катания
- skattebetalarens identifikationsnummer
- sverige tin
- налоговый файл
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- налоговый номер
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #


## <a name="swift-code"></a>Код SWIFT

### <a name="format"></a>Формат

четыре буквы с последующим 5-31 буквами или цифрами

### <a name="pattern"></a>Шаблон

четыре буквы, за которыми следуют 5-31 буквы или цифры:
- банковский код с четырьмя буквами (не чувствительный к делу)
- необязательный пробел
- 4–28 букв или цифр (основной номер банковского счета, BBAN)
- необязательный пробел
- от одной до трех букв или цифр (остальная часть BBAN)

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- SWIFTコ) ド
- SWIFT番号
- BIC番号
- BICコ) ド
- SWIFT コド
- SWIFT 番号
- BIC 番号
- BIC コド
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Номер AHV SSN в Швейцарии
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

13-значный номер

### <a name="pattern"></a>Шаблон

13-значный номер:

- три цифры - 756
- необязательная точка
- четыре цифры
- необязательная точка
- четыре цифры
- необязательная точка
- две цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_swiss_social_security_number_ahv контента, который соответствует шаблону.
- Ключевое слово Keywords_swiss_social_security_number_ahv найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_swiss_social_security_number_ahv контента, который соответствует шаблону.

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
- номер страховки
- personalidno #
- social security number
- личный номер
- личные удостоверения нет.
- insuranceno #
- uniqueidno #
- уникального удостоверения нет.
- номер avs
- личный идентификатор не versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- идентификационный код personnelle
- numéro de sécurité sociale


## <a name="taiwan-national-identification-number"></a>Национальный идентификационный номер Тайваня

### <a name="format"></a>Формат

одна буква (на английском языке) с девятью цифрами

### <a name="pattern"></a>Шаблон

одна буква (на английском языке), а затем девять цифр:
- одна буква (на английском языке, а не на английском языке)
- цифры "1" или "2"
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_taiwanese_national_id находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_taiwanese_national_id;
- Контрольная сумма проходит проверку.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

## <a name="taiwan-passport-number"></a>Номер паспорта Тайваня

### <a name="format"></a>Формат

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

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

## <a name="taiwan-resident-certificate-arctarc-number"></a>Номер сертификата жителя Тайваня (ARC/TARC)

### <a name="format"></a>Формат

10 букв и цифр.

### <a name="pattern"></a>Шаблон

10 букв и цифр:
- две буквы (не чувствительные к делу)
- восемь цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

## <a name="thai-population-identification-code"></a>Код идентификации населения Таиланда

### <a name="format"></a>Формат

13 цифр.

### <a name="pattern"></a>Шаблон

13 цифр:
- первая цифра не ноль или девять
- 12 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_Thai_Citizen_Id контент, который соответствует шаблону.
- Ключевое слово Keyword_Thai_Citizen_Id найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_Thai_Citizen_Id контент, который соответствует шаблону.

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

- Идентификационный номер
- Идентификационный номер
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน

## <a name="turkish-national-identification-number"></a>Турецкий национальный идентификационный номер

### <a name="format"></a>Формат

11 цифр.

### <a name="pattern"></a>Шаблон

11 цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_Turkish_National_Id контента, который соответствует шаблону.
- Ключевое слово из Keyword_Turkish_National_Id найдено.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_Turkish_National_Id контента, который соответствует шаблону.

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

- TC Kimlik No
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık нет

## <a name="uk-drivers-license-number"></a>U.K. номер лицензии водителя

### <a name="format"></a>Формат

Сочетание 18 букв и цифр в указанном формате.

### <a name="pattern"></a>Шаблон

18 букв и цифр
- Пять букв (не чувствительных к делу) или цифра "9" на месте буквы.
- Одна цифра.
- Пять цифр в формате даты MMDDY для даты рождения. Седьмой символ приумножен на 50, если драйвер женский; для экзамена, от 51 до 62 вместо 01 до 12.
- Две буквы (не чувствительные к делу) или цифра "9" на месте буквы.
- Пять цифр.

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция находит `Func_uk_drivers_license` содержимое, которое соответствует шаблону.
- Найдено ключевое `Keywords_eu_driver's_license_number` слово.
- Контрольная сумма проходит проверку.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция находит `Func_uk_drivers_license` содержимое, которое соответствует шаблону.
- Контрольная сумма проходит проверку.

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
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
- lic драйвера
- lics драйвера
- driver license
- driver licenses
- водительское удостоверение
- водительские права
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- драйверы lic
- lics драйверов
- drivers license
- drivers licenses
- drivers licence
- водительские права
- driver'lic
- driver'lics
- водительские права
- водительские права
- водительское удостоверение
- водительские права
- lic драйвера
- lics драйвера
- водительские права
- водительские права
- водительские права
- водительские права
- driver'slic
- slics драйвера
- slicense драйвера
- срезы драйвера
- нарезка драйвера
- срезы драйвера
- lic драйвера
- lics драйвера
- driver's license
- driver's licenses
- driver's licence
- водительские права
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- драйверы lic #
- lics драйверов #
- лицензия драйверов #
- лицензии драйверов #
- водительские права #
- водительские права #
- driver'lic #
- driver'lics #
- водительские права #
- водительские права #
- водительское удостоверение #
- водительские права #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driver'slic #
- slics драйвера #
- slicense драйвера #
- срезы драйвера #
- нарезка драйвера #
- срезы драйвера #
- lic драйвера #
- lics драйвера #
- водительские права #
- водительские права #
- водительские права #
- водительские права #
- driving licence 
- driving license
- dlno #
- driv lic
- driv licen
- лицензия driv
- лицензии driv
- лицензия driv
- лицензии driv
- licen драйвера
- драйверы licen
- licen драйвера
- driving lic
- driving licen
- водительские права
- driving licence
- driving licences
- разрешение на вождение
- dl no
- dlno
- номер dl


## <a name="uk-electoral-roll-number"></a>U.K. номер списка выборов

### <a name="format"></a>Формат

две буквы, за которыми следуют 1-4 цифры

### <a name="pattern"></a>Шаблон

две буквы (не чувствительные к делу) с последующим 1-4 числами

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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


## <a name="uk-national-health-service-number"></a>U.K. номер службы здравоохранения

### <a name="format"></a>Формат

10–17 цифр, разделенных пробелами.

### <a name="pattern"></a>Шаблон

10-17 цифр
- 3 или 10 цифр
- пространство
- три цифры
- пространство
- четыре цифры

### <a name="checksum"></a>Контрольная сумма

Да

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- NHS
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

## <a name="uk-national-insurance-number-nino"></a>U.K. номер национального страхования (NINO)
Этот тип конфиденциальной информации входит в тип конфиденциальной информации о номере национальной идентификации ЕС. Он также доступен в качестве отдельного объекта типа конфиденциальной информации.

### <a name="format"></a>Формат

семь символов или девять символов, разделенных пробелами или тире

### <a name="pattern"></a>Шаблон

два возможных шаблона:

- две буквы (допустимые ННИ используют только определенные символы в этом префиксе, который этот шаблон проверяет; не является чувствительным к делу)
- шесть цифр
- или "A", "B", "C", "D" (как и префикс, в суффиксе разрешены только определенные символы, не чувствительные к делу)

ИЛИ

- две буквы
- пространство или тире
- две цифры
- пространство или тире
- две цифры
- пространство или тире
- две цифры
- пространство или тире
- "A", "B", "C" или "D"

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_uk_nino находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_uk_nino.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- страхование
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- Номер NI
- NI No.
- NI #
- NI #
- страхование #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber


## <a name="uk-unique-taxpayer-reference-number"></a>U.K. Уникальный номер ссылки на налогоплательщика
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

10 цифр без пробелов и делимитеров


### <a name="pattern"></a>Шаблон

10 цифр.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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
- налоговый файл
- tax id
- идентификация налога нет
- идентификационный номер налога
- нет налога #
- нет налога
- номер регистрации налога
- таксомоторный #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- олово нет
- олово #

## <a name="us-bank-account-number"></a>Номер банковского счета в США

### <a name="format"></a>Формат

6-17 цифр

### <a name="pattern"></a>Шаблон

6-17 последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
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

## <a name="us-drivers-license-number"></a>Номер водительских прав в США

### <a name="format"></a>Формат

Зависит от штата.

### <a name="pattern"></a>Шаблон

зависит от состояния , например, Нью-Йорка:
- девять цифр, форматированные как ddd ddd ddd ddd, будут соответствовать.
- девять цифр, таких как dddddddd, не совпадают.

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;
- находится ключевое слово из Keyword_[state_name]_drivers_license_name;
- обнаружено ключевое слово из списка Keyword_us_drivers_license.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- ID
- DL #
- DLS #
- CDL #
- CDLS #
- ID #
- ID #
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
- Водительские права
- Водительские права
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
- Водительские права #
- Водительские права #
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
- имя состояния (например, "Нью-Йорк")

## <a name="us-individual-taxpayer-identification-number-itin"></a>Индивидуальный идентификационный номер налогоплательщика США (ITIN)

### <a name="format"></a>Формат

девять цифр, которые начинаются с "9" и содержат "7" или "8" в виде четвертой цифры, необязательно форматированные с пробелами или тире

### <a name="pattern"></a>Шаблон

форматированный:
- цифра "9"
- две цифры
- пространство или тире
- "7" или "8"
- цифру
- пространство или тире
- четыре цифры

unformatted:
- цифра "9"
- две цифры
- "7" или "8"
- пять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_formatted_itin находит содержимое, которое соответствует шаблону.
- найдено ключевое слово из Keyword_itin;

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_unformatted_itin находит содержимое, которое соответствует шаблону.
- найдено ключевое слово из Keyword_itin;

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- олово
- social security
- tax payer
- itins
- таксомоторный
- individual taxpayer


## <a name="us-social-security-number-ssn"></a>Номер социального обеспечения США (SSN)

### <a name="format"></a>Формат

девять цифр, которые могут быть в форматированном или неформатированном шаблоне

> [!NOTE]
> Есть SSN выдан до середины 2011 г., он отличается строгим форматированием, при котором определенные части номера должны входить в указанные диапазоны (при этом нет контрольной суммы).

### <a name="pattern"></a>Шаблон

четыре функции искать SSNs в четырех различных шаблонов:
- Func_ssn находит SSN со строгим форматированием с тире или пробелами, выданные до 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);
- Func_unformatted_ssn находит SSN со строгим форматированием, выданные до 2011 г. (без форматирования в виде девяти последовательных цифр — ццццццццц);
- Func_randomized_formatted_ssn находит SSN с тире или пробелами, выданные после 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);
- Func_randomized_unformatted_ssn находит SSN без форматирования в виде девяти последовательных цифр, выданные после 2011 г. (ццццццццц).

### <a name="checksum"></a>Контрольная сумма

Нет


### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_ssn находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_ssn.

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Функция Func_unformatted_ssn находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_ssn.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- Функция Func_randomized_formatted_ssn находит содержимое, которое соответствует шаблону.
- Находится ключевое слово из Keyword_ssn.

Политика DLP имеет низкую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
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
- социальное обеспечение #
- социальное обеспечение #
- социального обеспечения нет
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN #
- SS #
- SSID

## <a name="us--uk-passport-number"></a>U.S. / U.K. passport number

### <a name="format"></a>Формат

девять цифр

### <a name="pattern"></a>Шаблон

девять последовательных цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет высокую уверенность в том, что этот тип конфиденциальной информации обнаружен, если в непосредственной близости от 300 символов:
- функция Func_usa_uk_passport находит содержимое, которое соответствует шаблону;
- Ключевое слово `Keywords_eu_passport_number` из `Keywords_uk_eu_passport_number` или найдено.
- Найдено `Keywords_eu_passport_date` ключевое слово

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- функция Func_usa_uk_passport находит содержимое, которое соответствует шаблону;
- Ключевое слово `Keywords_eu_passport_number` из `Keywords_uk_eu_passport_number` или найдено.

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- паспорт #
- паспорт #
- passportid
- паспорта
- passportno
- паспорт нет
- passportnumber
- passport number
- passportnumbers
- номера паспортов

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- британский паспорт
- uk passport


## <a name="ukraine-passport-domestic"></a>Внутренний паспорт Украины
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

девять цифр

### <a name="pattern"></a>Шаблон

девять цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- В regex Regex_Ukraine_Passport_Domestic контент, который соответствует шаблону.
- Найдено ключевое слово Keyword_Ukraine_Passport_Domestic.

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

- Паспорт Украины
- passport number
- паспорт нет
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Паспорт Украины
Этот тип конфиденциальной информации доступен только для использования в:
- Политики предотвращения потери данных
- политики соответствия требованиям к коммуникациям
- управление информацией
- Управление записями
- Безопасность облачных приложений Майкрософт

### <a name="format"></a>Формат

альфанумерный шаблон из восьми символов

### <a name="pattern"></a>Шаблон

альфанумерный шаблон из восьми символов:
- две буквы или цифры
- шесть цифр

### <a name="checksum"></a>Контрольная сумма

Нет

### <a name="definition"></a>Определение

Политика DLP имеет среднюю уверенность в том, что она обнаруживает этот тип конфиденциальной информации, если в непосредственной близости от 300 символов:
- Regex Regex_Ukraine_Passport_International контент, который соответствует шаблону.
- Ключевое слово Keyword_Ukraine_Passport_International найдено.

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

- Паспорт Украины
- passport number
- паспорт нет
- паспорт України
- номер паспорта
