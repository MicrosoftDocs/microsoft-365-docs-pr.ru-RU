---
title: Национальный идентификационный номер ЕС
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
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС по национальному идентификационному номеру. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: 4dac77f129b45f457a82e709cb5a3b846a95cdf4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938765"
---
# <a name="eu-national-identification-number"></a>Национальный идентификационный номер ЕС

В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС по национальному идентификационному номеру. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
  
## <a name="austria"></a>Австрия

### <a name="format"></a>Format

24 – символическое сочетание букв, цифр и специальных символов;
  
### <a name="pattern"></a>Шаблон

24 символа:
  
-  22 буквы (без учета регистра), цифры, обратные косые черты, косые черты и знаки плюса 
    
- Две буквы (без учета регистра), цифры, обратные косые черты, знаки косой черты, знаки плюса и знаки равенства.
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_austria_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_austria_eu_national_id_card` слово FROM. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

Австрийский номер удостоверения
  
Национальный идентификационный номер
  
идентификационный номер
  
national id
  
персоналаусвеис Републик öстерреич
  
## <a name="belgium"></a>Бельгия

Дополнительные сведения можно найти в разделе "Бельгии National Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="bulgaria"></a>Болгария

### <a name="format"></a>Format

Десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Десять цифр без пробелов и разделителей
  
-  Шесть цифр, соответствующих дате рождения (ГГММДД) 
    
- Две цифры, соответствующие порядку рождения
    
- Одна цифра, соответствующая Пол: четное число для пола и нечетная цифра для розетки
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_bulgaria_national_number` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_bulgaria_national_number` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_bulgaria_national_number` находит содержимое, которое соответствует шаблону. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

егн
  
егн #
  
Национальный номер для болгарского языка
  
номер страны
  
social security number
  
натионалнумбер #
  
SSN #
  
SSN
  
натионалнумбер
  
бнн #
  
бнн
  
личный идентификационный номер
  
персоналиднумбер #
  
единен граждански номер
  
единен граздански номер
  
егн
  
егн #
  
## <a name="croatia"></a>Хорватия

Дополнительные сведения см. в разделе "номер идентификатора Хорватия" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="cyprus"></a>Кипр

### <a name="format"></a>Format

Десять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

 Десять цифр 
  
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_cyprus_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_cyprus_eu_national_id_card` слово FROM. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

идентификационный номер карточки
  
national identification number
  
личный идентификационный номер
  
Номер идентификационной карточки
  
ταυτοτητασ
  
## <a name="czech-republic"></a>Чехия

Для получения дополнительных сведений обратитесь к разделу "Чешский Национальный идентификационный номер", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="denmark"></a>Дания

Дополнительные сведения можно найти в разделе "Дания персонального идентификационного номера", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="estonia"></a>Эстония

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр:
  
- Одна цифра, соответствующая упоминанию секса и столетию рождения (нечетный номер, четная розетка), 1-2:19 века; 3-4:20 века; 5-6:21 столетие)
    
- Шесть цифр, соответствующих дате рождения (ГГММДД)
    
- Три цифры, которые соответствуют порядковому номеру, разделенному на одну и ту же дату.
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_estonia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_estonia_eu_national_id_card` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_estonia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

персональный идентификационный код
  
персональный идентификационный номер
  
national identification number
  
номер страны
  
личный идентификационный номер
  
персоналиднумбер #
  
фигуры
  
исикукуд
  
ID — каарт
  
## <a name="finland"></a>Финляндия

Дополнительные сведения можно найти в разделе "Финляндия национального ID", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Франция

Дополнительные сведения можно найти в разделе "Французская Национальная ИДЕНТИФИКАЦИОНная карточка (CNI)" [, в которой отображаются типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Германия

Дополнительные сведения можно найти в разделе "номер идентификационной карточки для Германии" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Греция

Дополнительные сведения можно найти в разделе "Греция National ID Card", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Венгрия

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
  
- Функция `Func_hungary_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_hungary_eu_national_id_card` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_hungary_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

персональный идентификационный номер
  
identification number
  
личный идентификационный номер
  
сземéлязоносíтó игазолвáни
  
## <a name="ireland"></a>Ирландия

### <a name="format"></a>Format

Сочетание букв, цифр и пробела в указанном шаблоне.
  
### <a name="pattern"></a>Шаблон

Сочетание букв, цифр и пробела в указанном шаблоне.
  
От 01 января 2013 до Now:
  
-  семь цифр; 
    
- Одна контрольная цифра
    
- Один пробел или буква в верхнем регистре "W" (с учетом регистра)
    
До 01 января 2013:
  
-  семь цифр; 
    
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
    
```
 
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

номер личной общедоступной службы
  
PPS нет
  
номер дохода и социального страхования
  
RSI нет
  
персональный идентификационный номер
  
identification number
  
личный идентификационный номер
  
уимхир феарсанта сеирбхíсе поиблí
  
уимх. настроен
  
## <a name="italy"></a>Италия

### <a name="format"></a>Format

16 – символическое сочетание букв и цифр в указанном шаблоне.
  
### <a name="pattern"></a>Шаблон

16 – буквенное сочетание букв и цифр:
  
- Три буквы, соответствующие первым трем согласным в имени семейства
    
- Три буквы, соответствующие первым, третьим и четвертым согласным в имени.
    
- Две цифры, соответствующие последним цифрам года рождения
    
- Одна буква, соответствующая букве дня рождения, буквы используются в алфавитном порядке, но используются только буквы от A до E, H, L, M, P, R — T (то есть Январь — это R, а Октябрь — R)
    
- Две цифры, которые соответствуют дню месяца рождения, для различения пола, 40 добавляется в день рождения для женщин
    
- Четыре цифры, соответствующие коду города, который относится к органу государственной власти, в котором был создан пользователь, (для иностранных стран используются коды уровня страны).
    
- Одна цифра четности
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_italy_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_italy_eu_national_id_card` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_italy_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

персональный код
  
номер личного кода
  
личный номер сертификата
  
Финансовый код
  
персоналкодено #
  
личный идентификационный номер
  
личный код
  
Персональные подкодеки
  
Нумеро цертификато персональный
  
персональные настройки нумеро
  
личный идентификатор нумеро
  
личные коды для сокодовых костей
  
финансовый отчет по сокостям
  
## <a name="latvia"></a>Латвия

### <a name="format"></a>Format

11 цифр и дефис в указанном формате.
  
### <a name="pattern"></a>Шаблон

11 цифр и дефис:
  
-  Шесть цифр, соответствующих дате рождения (ДДММГГ —) 
    
- дефис;
    
- Одна цифра, соответствующая столетию рождения ("0" для 19 века, "1" для 20-й век) и "2" для 21 века)
    
- Четыре цифры, созданные случайным образом
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_latvia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_latvia_eu_national_id_card` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_latvia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

персональный код
  
номер личного кода
  
личный номер сертификата
  
персоналкодено #
  
личный идентификационный номер
  
личный код
  
Пользователи Кодс
  
## <a name="lithuania"></a>Литва

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр без пробелов и разделителей:
  
- Одна цифра, соответствующая пол и век рождения человека
    
-  Шесть цифр, соответствующих дате рождения (ГГММДД) 
    
- Три цифры, которые соответствуют серийному числу даты рождения.
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_lithuania_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_lithuania_eu_national_id_card` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_lithuania_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
 
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

персональный числовой код
  
уникальный идентификационный номер
  
номер службы для себя
  
уникальный идентификационный номер
  
уникуеидентитино #
  
персональный код.
  
асменинис скаитменинис кодас
  
уникалус идентификавимо нумерис
  
пилиеčио паслаугос нумерис
  
уникалус идентификавимо кодас
  
асменс кодас.
  
## <a name="luxemburg"></a>луксембург

### <a name="format"></a>Format

11 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

11 цифр.
  
- Одна цифра, соответствующая пол и век рождения человека
    
-  Шесть цифр, соответствующих дате рождения (ГГММДД) 
    
- Три цифры, которые соответствуют серийному числу даты рождения.
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_luxemburg_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_luxemburg_eu_national_id_card` слово FROM. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

личный идентификатор
  
личный идентификационный номер
  
персоналидно #
  
уникальный идентификационный номер
  
персоналиднумбер #
  
уникальный ключ идентификатора
  
личный код
  
уникуеидкэй #
  
отдельный код
  
индивидуальный идентификатор
  
Идентификатор еиндеутиже — нуммер
  
Идентификатор еиндеутиже
  
ID персоннелле
  
нумéро д'идентификатион сотрудники
  
идперсоннелле #
  
персöнличе идентификатионснуммер
  
еиндеутижеид #
  
## <a name="malta"></a>Мальта

### <a name="format"></a>Format

Семь цифр, за которыми следует одна буква
  
### <a name="pattern"></a>Шаблон

Семь цифр, за которыми следует одна буква:
  
-  семь цифр; 
    
- Одна прописная буква (с учетом регистра)
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_malta_eu_national_id_card` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:
  
- Регулярное выражение `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
 
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

персональный числовой код
  
уникальный идентификационный номер
  
номер службы для себя
  
уникальный идентификационный номер
  
уникуеидентитино #
  
кодиċи нумерали персонали
  
нумру Ta ' идентификаззжони унику
  
нумруные зада сервизз таċ ċиттадин
  
нумру Ta ' идентитà унику
  
## <a name="netherlands"></a>Нидерланды

### <a name="format"></a>Format

Девять цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

Девять цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_netherlands_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое слово FROM.
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_netherlands_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
 
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

персональный числовой код
  
уникальный идентификационный номер
  
номер службы для себя
  
уникальный идентификационный номер
  
уникуеидентитино #
  
BSN
  
BSN #
  
персунлижке нумериеке код
  
униек идентификатиенуммер
  
буржерсервиценуммер
  
униек идентитеитснуммер
  
## <a name="poland"></a>Польша

Дополнительные сведения см. в разделе "Польша National ID (PESEL)" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Португалия

Дополнительные сведения можно найти в разделе "номер карты для Португалия" в разделе [сведения о типах конфиденциальной информации для поиска](what-the-sensitive-information-types-look-for.md).
  
## <a name="romania"></a>Румыния

### <a name="format"></a>Format

13 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

13 цифр.
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_romania_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_romania_eu_national_id_card` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_romania_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
 
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

персональный числовой код
  
уникальный идентификационный номер
  
кнп
  
кнп #
  
крепления
  
крепления #
  
страховой номер
  
инсуранценумбер #
  
уникальный идентификационный номер
  
уникуеидентитино #
  
цифровой платеж, персональный
  
Личный идентификаре наложенного платежа
  
наложенный Уник идентификаре
  
нумăр Personal Уник
  
нумăр идентитате
  
нумăр идентификаре персональный
  
нумăридентитате #
  
коднумерикперсонал #
  
нумăрперсоналуник #
  
## <a name="slovakia"></a>Словакия

### <a name="format"></a>Format

Десять цифр, содержащих одну обратную косую черту;
  
### <a name="pattern"></a>Шаблон

Десять цифр, содержащих одну обратную косую черту:
  
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_slovakia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_slovakia_eu_national_id_card` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_slovakia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
 
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

номер рождения
  
national identification number
  
персональный идентификационный номер
  
social security number
  
натионалнумбер #
  
SSN #
  
SSN
  
номер страны
  
личный идентификационный номер
  
персоналиднумбер #
  
рč
  
роднé číсло
  
родне Цисло
  
## <a name="slovenia"></a>Словения

### <a name="format"></a>Format

13 цифр без пробелов и разделителей
  
### <a name="pattern"></a>Шаблон

13 цифр в указанном шаблоне:
  
-  Семь цифр, которые соответствуют дате рождения (ДДММЛЛЛ), где "ЛЛЛ" соответствует последним трем цифрам года рождения 
    
- Две цифры, соответствующие области рождения
    
- Три цифры, которые соответствуют сочетанию пола и серийного номера для людей, которые приставили один и тот же день (000-499 для пола и 500-999 для розетки)
    
- Одна контрольная цифра
    
### <a name="checksum"></a>Контрольная сумма

Да
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_slovenia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_slovenia_eu_national_id_card` слово FROM. 
    
Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Функция `Func_slovenia_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
```
 
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

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

персональный числовой код
  
уникальный идентификационный номер
  
уникальный регистрационный номер
  
уникальный идентификационный номер
  
уникуеидентитино #
  
уникальный основной номер
  
единствена идентификаЦижска šтевилка
  
уникуеидентитино #
  
единствена šтевилка главнега дрžавлжана
  
емšо
  
## <a name="spain"></a>Испания

### <a name="format"></a>Format

Семь цифр, за которыми следует один символ
  
### <a name="pattern"></a>Шаблон

Семь цифр, за которыми следует один символ
  
- семь цифр;
    
- Одна цифра или буква (без учета регистра)
    
### <a name="checksum"></a>Контрольная сумма

Неприменимо
  
### <a name="definition"></a>Определение

Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:
  
- Регулярное выражение `Regex_spain_eu_national_id_card` находит содержимое, которое соответствует шаблону. 
    
- Найдено ключевое `Keywords_spain_eu_national_id_card"` слово FROM. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Ключевые слова

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

DNI
  
national identification number
  
Национальный идентификационный номер
  
страховой номер
  
персональный идентификационный номер
  
Национальная идентификация
  
личный идентификатор
  
уникальный идентификационный номер
  
натионалидно #
  
уникальным #
  
DNI #
  
натионалид #
  
ние #
  
ние
  
ниенúмеро #
  
ние нúмеро
  
документо наЦионал де ИДЕНТИДАД
  
ИДЕНТИДАД úнико
  
нúмеро наЦионал ИДЕНТИДАД
  
DNI нúмеро
  
днинúмеро #
  
идентидадúнико #
  
## <a name="sweden"></a>Швеция

Для получения дополнительных сведений обратитесь к разделу "Швеции National ID", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>См. также

[Что позволяют искать типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md)

