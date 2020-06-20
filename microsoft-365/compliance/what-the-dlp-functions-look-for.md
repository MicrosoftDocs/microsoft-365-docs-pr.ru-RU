---
title: Сведения, для обнаружения которых используются функции защиты от потери данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Узнайте, что ищет функции защиты от потери данных (DLP), чтобы узнать, как работают предопределенные типы конфиденциальной информации.
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819279"
---
# <a name="what-the-dlp-functions-look-for"></a>Сведения, для обнаружения которых используются функции защиты от потери данных

Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.
  
В этой статье рассказывается о сведениях, для обнаружения которых используются эти функции, что поможет вам разобраться в предопределенных типах конфиденциальной информации. Более подробную информацию можно узнать в статье [Определение объекта типа конфиденциальной информации](sensitive-information-type-entity-definitions.md)
  
## <a name="func_us_date"></a>Func_us_date

Эта функция ищет дату в формате, обычно используемом в США. К ним относятся форматы "месяц/день/год", "месяц-день-год" и "месяц суток год". Полные или сокращенные названия месяцев вводятся без учета регистра. 
  
Примеры:
  
- 2 декабря 2016 г.
    
- 2 декабря 2016 г.
    
- Dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec – 2-2016
    
- 12-2-16
    
Принятые названия месяцев:
  
- English
    
  - Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь
    
  - Февраль. Фев. Март. Апр. Май июня. сентября. Oct. Ноя. Дек.
    
## <a name="func_eu_date"></a>Func_eu_date

This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.
  
Примеры:
  
- 2 декабря 2016
    
- 02 декабря 2016 г.
    
- 2 декабря, 16 декабря
    
- 2/12/2016
    
- 02/12/16
    
- 2 декабря 2016 г.
    
- 2-12-16
    
Принятые названия месяцев:
  
- English
    
  - Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь
    
  - Февраль. Фев. Март. Апр. Май июня. сентября. Oct. Ноя. Дек.
    
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Февраль февраля МАарт апреля Меи июня 2004 Янв, Сен сентября, Окт ноября декабря
    
- French
    
  - жанвиер, фéвриер, Mars, Аврил, Чиангмай, жуин жуиллет, аоûт, септембре, октобре, Новембре, дéцембре
    
  - жанв. фéвр. режим MARS Аврил Чиангмай жуин жуил. аоûт сентября. развертывания. ноября. дéк.
    
- German
    
  - жäнуар, фебруар, мäрз, Апрель, Чиангмай, жуни Жули, Август, Сентябрь, Октобер, Ноябрь, дезембер
    
  - Янв./Жäн. Фев. Мäрз Apr. Чиангмай Жуни Жули Авг. Сентябрь. Окт. Ноя. дез.
    
- Italian
    
  - женнаио, феббраио, Марзо, Апрель, маггио, гиугно, луглио, Агосто, Сеттембре, Оттобре, Новембре, дицембре
    
  - Женн. феббр. Мар. Апрель. Магг. гиугно луглио AG. Переключател. and. ноября. DIC.
    
- Португальский
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Янв Фев Mar, Чиангмай, 2004 июня, назад, Настройка ноября Ноя дез
    
- Spanish
    
  - енеро, фебреро, Марзо, Абрил, Майо, Жунио, Жулио, Агосто, септиембре, Октубре, новиембре, диЦиембре
    
  - енеро Фев. Марзо Граничный маршрутизатор. Майо июня. июля. Агосто сентября./Сет. развертывания. ноября. DIC.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (не рекомендуется)

> [!NOTE]
> Эта функция является устаревшей, так как она поддерживает только названия месяцев на португальском языке, которые теперь включены в `Func_eu_date` функцию, описанную выше. 
  
Эта функция служит для поиска даты в формате, принятом в португальском языке. Формат этой функции такой же `Func_eu_date` , как и в используемом языке.
  
Примеры:
  
- 2 дез 2016
    
- 02 дез 2016
    
- 2 дез 16
    
- 2/12/2016
    
- 02/12/16
    
- 2 — дез — 2016
    
- 2-12-16
    
Принятые названия месяцев:
  
- Португальский
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Янв Фев Mar, Чиангмай, 2004 июня, назад, Настройка ноября Ноя дез
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (не рекомендуется)

> [!NOTE]
> Эта функция является устаревшей, так как она поддерживает только названия в голландских месяцах, которые теперь включены в `Func_eu_date` функцию, описанную выше. 
  
Эта функция служит для поиска даты в формате, принятом в нидерландском языке. Формат этой функции такой же `Func_eu_date` , как и в используемом языке.
  
Примеры:
  
- 2 Меи 2016
    
- 02 Меи 2016
    
- 2 Меи 16
    
- 2/12/2016
    
- 02/12/16
    
- 2 — Меи — 2016
    
- 2-12-16
    
Принятые названия месяцев:
  
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Февраль февраля МАарт апреля Меи июня 2004 Янв, Сен сентября, Окт ноября декабря
    
## <a name="func_expiration_date"></a>Func_expiration_date

Эта функция служит для поиска даты в формате, обычно используемом для кредитных и дебетовых карт, где указывается месяц, а дни исключаются. Эта функция будет сопоставлять даты в формате "месяц/год", "month-Year", "[название месяца] год" и "[аббревиатура] год". Полные или сокращенные названия месяцев вводятся без учета регистра.
  
Примеры:
  
- ММ/ГГ (например, 01/11 или 1/11);
    
- ММ/ГГГГ (например, 01/2011 или 1/2011);
    
- ММ-ГГ (например, 01-22 или 1-11);
    
- ММ-ГГГГ (например, 01-2000 или 1-2000).
    
Следующие форматы поддерживают ГГ или ГГГГ:
  
- Месяц-ГГГГ (например, янв-2010, январь-2010, янв-10 или январь-10);
    
- Месяц ГГГГ (например, "январь 2010", "янв 2010", "январь 10" или "янв 10");
    
- МесяцГГГГ (например, "январь2010", "янв2010", "январь10" или "янв10");
    
- Month/гггг, например, "Январь/2010" или "Янв/2010" или "Январь/10" или "Янв/10"
    
Принятые названия месяцев:
  
- English
    
  - Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь
    
  - Февраль февраля Mar апреля, Май, Сентябрь октября октября, Май
    
## <a name="func_us_address"></a>Func_us_address

This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.
  
Примеры:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

