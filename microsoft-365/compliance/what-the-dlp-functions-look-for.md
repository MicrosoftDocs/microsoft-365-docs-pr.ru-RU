---
title: Функции защиты от потери данных (DLP)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Узнайте, что изучить функции защиты от потери данных (DLP).
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841450"
---
# <a name="what-the-dlp-functions-look-for"></a>Сведения, для обнаружения которых используются функции защиты от потери данных

Политики защиты от потери данных могут использовать типы конфиденциальной информации для идентификации конфиденциальных элементов. В качестве примеров типов конфиденциальной информации можно привести номер кредитной карты и номер банковской карты для ЕС. Типы конфиденциальной информации искать определенные шаблоны. Типы конфиденциальной информации проверяют данные, посмотрев на их формат, контрольные списки и насмотрев соответствующие ключевые слова или другую информацию. Для некоторых из этих проверок используются внешние функции. Например, тип конфиденциальной информации "Номер кредитной карты" использует функцию для искомых дат, отформатированные как дата окончания срока действия. Это помогает подтвердить, что номер является номером кредитной карты.
  
В этой статье объясняется, что искать эти функции, чтобы помочь вам понять, как работают предварительно определенные типы конфиденциальной информации. Дополнительные сведения [см.](sensitive-information-type-entity-definitions.md) в определениях сущности типа конфиденциальной информации
  
## <a name="table-of-functions"></a>Таблица функций

|имя функции  |действие функции  |является проверкой|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|обнаруживает и проверяет уникальный налоговый ключ Для Аргентины|Нет|
|Func_aba_routing|определяет номер маршрутки ABA| Да|
|Func_alabama_drivers_license_number|определяет номер водительского удостоверения Алабамы|Нет|
|Func_alaska_delaware_oregon_drivers_license_number|обнаруживает Номер водительского удостоверения в Орегоне, Деляве|Нет|
|Func_alaska_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_alberta_drivers_license_number|определяет номер водительского удостоверения в Альбате|Нет|
|Func_Argentina_Unique_Tax_Key|определяет уникальный налоговый ключ для Аргентины|Нет|
|Func_arizona_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_arkansas_drivers_license_number|определяет номер водительского удостоверения Арканзаса|Нет|
|Func_australian_business_number|определяет номер компании для Австралии|Нет|
|Func_Australian_Company_Number|определяет номер компании для Австралии|Нет|
|Func_australian_medical_account_number|определяет номер медицинской учетной записи Для Австралии|Нет|
|Func_australian_tax_file_number|определяет номер налогового файла для Австралии|Да|
|Func_austria_eu_ssn_or_equivalent|определяет номер социального обеспечения Для Австрия|Нет|
|Func_austria_eu_tax_file_number|определяет номер налогового файла для Австрия|Нет|
|Func_Austria_Value_Added_Tax|определяет налог на добавленную стоимость для Австрия|Нет|
|Func_belgium_national_number|определяет номер для бельгийского национального номера|Нет|
|Func_belgium_value_added_tax_number|определяет номер налога на добавленную стоимость в Бельгии|Нет|
|Func_brazil_cnpj|определяет номер юридического лица для Бразилии (CNPJ)|Да|
|Func_brazil_cpf|обнаруживает CPF для Бразилии|Да|
|Func_brazil_rg|обнаруживает RG для Бразилии|Нет|
|Func_british_columbia_drivers_license_number|определяет номер водительского удостоверения для Английской Колумбии|Нет|
|Func_bulgaria_eu_national_id_card|определяет однородный номер для Болгарии|Нет|
|Func_california_drivers_license_number|определяет номер водительского удостоверения в Калифорнии|Нет|
|Func_canadian_sin|обнаруживает канадский сгреш|Да|
|Func_chile_id_card|обнаруживает ИД-карту Чили|Нет|
|Func_china_resident_id|определяет ИД резидента Китая|Нет|
|Func_colorado_drivers_license_number|определяет номер водительского удостоверения "Климов".|Нет|
|Func_connecticut_drivers_license_number|определяет номер водительского удостоверения Connecticut|Нет|
|Func_credit_card|обнаруживает кредитную карту|да|нет|
|Func_croatia_id_card|обнаруживает ИД-карту Хорватии|Нет|
|Func_croatia_oib_number|определяет номер OIB для Хорватии|Нет|
|Func_cyprus_eu_tax_file_number|определяет номер налогового файла для Кипра|Нет|
|Func_czech_id_card|обнаруживает чешскую ID-карту|Нет|
|Func_czech_id_card_new_format|обнаруживает чешскую ID-карту в новом формате|Нет|
|Func_dea_number|обнаруживает номер DEA|Да|
|Func_denmark_eu_tax_file_number|определяет персональный идентификационный номер для Дании|Нет|
|Func_district_of_columbia_drivers_license_number|определяет номер водительского удостоверения в округе Колумбия|Нет|
|Func_estonia_eu_national_id_card|обнаруживает персональный идентификационный код Для Эстонии|Нет|
|Func_eu_debit_card|определяет дебетовую карту ДЛЯ ЕС|Нет|
|Func_finnish_national_id|обнаруживает национальный ИД Финляндии|Нет|
|Func_florida_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|определяет номер водительского удостоверения "Вайт", "Мериленд", "Климен", "Штат О-ва"|Нет|
|Func_formatted_itin|обнаруживает отформатированные US ITIN|Да|
|Func_fr_insee|обнаруживает Францию INSEE|Нет|
|Func_fr_passport|обнаруживает паспорт гражданина Франции|Нет|
|Func_france_eu_tax_file_number|определяет номер налогового файла для Франции|Нет|
|Func_france_value_added_tax_number|определяет номер налога на добавленную стоимость для Франции|Нет|
|Func_french_drivers_license|определяет водительское удостоверение на французском языке|Нет|
|Func_french_insee|обнаруживает французский INSEE|Нет|
|Func_georgia_drivers_license_number|определяет номер водительского удостоверения для Джорджии|Нет|
|Func_german_drivers_license|определяет водительское удостоверение для Германии|Нет|
|Func_german_passport|обнаруживает паспорт гражданина Германии|Нет|
|Func_german_passport_data|обнаруживает паспорт гражданина Германии|Нет|
|Func_germany_eu_tax_file_number|определяет номер налогового файла для Германии|Нет|
|Func_germany_value_added_tax_number|определяет номер налога на добавленную стоимость в Германии|Нет|
|Func_greece_eu_ssn|обнаруживает грецияский сгреш (AMKA)|Нет|
|Func_hawaii_drivers_license_number|определяет номер водительского удостоверения Для Острова|Нет|
|Func_hong_kong_id_card |обнаруживает ИД-карту в Гонконге|Нет|
|Func_hungarian_value_added_tax_number|определяет номер налога на добавленную стоимость для Венгрии|Нет|
|Func_hungary_eu_national_id_card|определяет персональный идентификационный номер для Венгрии|Нет|
|Func_hungary_eu_ssn_or_equivalent|определяет номер социального обеспечения Для Венгрии|Нет|
|Func_hungary_eu_tax_file_number|определяет номер налогового файла для Венгрии|Нет|
|Func_iban|определяет IBAN|Да|
|Func_idaho_drivers_license_number|определяет номер водительского удостоверения Айдахо|Нет|
|Func_illinois_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_india_aadhaar|detects India aadhaar|Да|
|Func_indiana_drivers_license_number|определяет номер водительского удостоверения в Индии|Нет|
|Func_iowa_drivers_license_number|определяет номер водительского удостоверения "|Нет|
|Func_ireland_pps|обнаруживает PPS для Ирландии|Нет|
|Func_israeli_national_id_number|обнаруживает номер национального ИД для Израиля|Нет|
|Func_italy_eu_national_id_card |определяет финансовый код Для Италия|Нет|
|Func_italy_value_added_tax_number|определяет номер налога на добавленную стоимость для Италия|Нет|
|Func_japanese_my_number_corporate|обнаруживает Японию на моем корпоративном номере|Да|
|Func_japanese_my_number_personal|обнаруживает в Японии мой личный номер|Да|
|Func_jp_bank_account|обнаруживает банковский счет для Японии|Нет|
|Func_jp_bank_account_branch_code|обнаруживает код филиала банковского счета для Японии|Нет|
|Func_jp_drivers_license_number|определяет номер водительского удостоверения для Японии|Нет|
|Func_jp_passport|обнаруживает паспорт гражданина Японии|Нет|
|Func_jp_resident_registration_number|определяет номер регистрации для резидентов Японии|Нет|
|Func_jp_sin|обнаруживает СИН Для Японии|Нет|
|Func_jp_sin_pre_1997|обнаруживает японию до 1997 г.|Нет|
|Func_kansas_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_kentucky_drivers_license_number|определяет номер водительского удостоверения "Не по номеру".|Нет|
|Func_kentucky_massachusetts_virginia_drivers_license_number|определяет номер водительского удостоверения "Книжий", "Неугомя" и "Неавтон".|Нет|
|Func_latvia_eu_national_id_card|обнаруживает персональный код Латвии|Нет|
|Func_lithuania_eu_tax_file_number|обнаруживает персональный код Для Литвы|Нет|
|Func_louisiana_drivers_license_number|определяет номер водительского удостоверения в Штате|Нет|
|Func_luxemburg_eu_tax_file_number|обнаруживает национальный идентификационный номер (естественные лица) в Хымнюсе|Нет|
|Func_luxemburg_eu_tax_file_number_non_natural|обнаруживает национальный идентификационный номер Химмнеса (не является естественным лицом)|Нет|
|Func_maine_drivers_license_number|определяет номер водительского удостоверения Maine|Нет|
|Func_manitoba_drivers_license_number|определяет номер водительского удостоверения Manitoba|Нет|
|Func_maryland_drivers_license_number|определяет номер водительского удостоверения для штата Мариленд|Нет|
|Func_massachusetts_drivers_license_number|определяет номер водительского удостоверения "|Нет|
|Func_mexico_population_registry_code|обнаруживает код реестра для людей в Мексика|Нет|
|Func_michigan_minnesota_drivers_license_number|обнаруживает номер водительского удостоверения «Кнолин, ШтатОм, ШтатОм).|Нет|
|Func_minnesota_drivers_license_number|определяет номер водительского удостоверения в Штате|Нет|
|Func_mississippi_oklahoma_drivers_license_number|определяет номер водительского удостоверения "Неугомя"|Нет|
|Func_missouri_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_montana_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_nebraska_drivers_license_number|определяет номер водительского удостоверения Nebraska|Нет|
|Func_netherlands_bsn|обнаруживает BSN Нидерландов|Нет|
|Func_netherlands_eu_tax_file_number|определяет номер налогового файла для Нидерландов|Нет|
|Func_netherlands_value_added_tax_number|определяет номер налога на добавленную стоимость для Нидерландов|Нет|
|Func_nevada_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_new_brunswick_drivers_license_number|определяет номер водительского удостоверения New Bruns detects|Нет|
|Func_new_hampshire_drivers_license_number|определяет номер водительского удостоверения в Нью-Хэмпшире|Нет|
|Func_new_jersey_drivers_license_number |определяет номер водительского удостоверения в Нью-Джерси|Нет|
|Func_new_mexico_drivers_license_number |определяет номер водительского удостоверения в Нью-Йорке|Нет|
|Func_new_york_drivers_license_number   |определяет номер водительского удостоверения в Нью-Йорке|Нет|
|Func_new_zealand_bank_account_number   |определяет номер банковского счета для Новой Зеландии|Нет|
|Func_new_zealand_inland_revenue_number |определяет номер выручки для новой Зеландии в стране|Нет|
|Func_new_zealand_ministry_of_health_number|обнаруживает номер медицинского номера для Новой Зеландии|Нет|
|Func_newfoundland_labrador_drivers_license_number|определяет номер водительского удостоверения Newfoundland Lab detectr|Нет|
|Func_newzealand_driver_license_number  |определяет номер водительского удостоверения для Новой Зеландии|Нет|
|Func_newzealand_social_welfare_number  |определяет номер социальных сетей Новой Зеландии|Нет|
|Func_north_carolina_drivers_license_number|определяет номер водительского удостоверения "Северная Восток".|Нет|
|Func_north_dakota_drivers_license_number|определяет номер водительского удостоверения "Северная Дансия"|Нет|
|Func_norway_id_number  |определяет номер ИД Норвегии|Нет|
|Func_nova_scotia_drivers_license_number|определяет номер водительского удостоверения Nova Scotia|Нет|
|Func_ohio_drivers_license_number   |определяет номер водительского удостоверения|Нет|
|Func_ontario_drivers_license_number    |определяет номер водительского удостоверения|Нет|
|Func_pennsylvania_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_pesel_identification_number   |обнаруживает национальный ИД для Польша (PESEL)|Нет|
|Func_poland_eu_tax_file_number |определяет номер налогового файла для Германии|Нет|
|Func_polish_national_id    |обнаруживает удостоверение личности для Польша|Нет|
|Func_polish_passport_number    |определяет номер паспорта гражданина Польский|Нет|
|Func_polish_regon_number   |определяет номер польского REGON|Нет|
|Func_portugal_eu_tax_file_number|определяет идентификационный номер налога для Португалии|Нет|
|Func_prince_edward_island_drivers_license_number|определяет номер водительского удостоверения "Острова Ковыл"|Нет|
|Func_quebec_drivers_license_number |определяет номер водительского удостоверения|Нет|
|Func_randomized_formatted_ssn  |обнаруживает случайно отформатированный SSN в США|Да|
|Func_randomized_unformatted_ssn|обнаруживает случайное неформатированное SSN в США|Да|
|Func_rhode_island_drivers_license_number|определяет номер водительского удостоверения на О-вЕ|Нет|
|Func_romania_eu_national_id_card   |обнаруживает персональный числовой код Румынии (CNP)|Нет|
|Func_saskatchewan_drivers_license_number|определяет номер водительского удостоверения Saskatchewan|Нет|
|Func_slovakia_eu_national_id_card  |определяет персональный номер для Словакии|Нет|
|Func_slovenia_eu_national_id_card  |определяет уникальный номер гражданина Словении|Нет|
|Func_slovenia_eu_tax_file_number   |определяет номер налогового файла для Словении|Нет|
|Func_south_africa_identification_number|определяет идентификационный номер для Южной Африки|Да|
|Func_south_carolina_drivers_license_number|определяет номер водительского удостоверения "Южная Африка"|Нет|
|Func_south_dakota_drivers_license_number|определяет номер водительского удостоверения "Южная Африка"|Нет|
|Func_south_korea_resident_number   |определяет номер резидента Южной Республики Корея|Нет|
|Func_spain_eu_DL_and_NI_number_citizen |обнаруживает испанского гражданина номеров DL и NI|Нет|
|Func_spain_eu_DL_and_NI_number_foreigner|обнаружение номеров DL и NI в Испании|Нет|
|Func_spain_eu_driver s_license_number  |определяет номер водительского удостоверения для Испании|Нет|
|Func_spain_eu_tax_file_number  |определяет номер налогового файла для Испании|Нет|
|Func_spanish_social_security_number|определяет номер социального обеспечения на испанском языке|Нет|
|Func_ssn   |Функция для обнаружения нестандартного формата SSN в США|Да|
|Func_sweden_eu_tax_file_number|определяет номер налогового файла для Швеции|Нет|
|Func_swedish_national_identifier|обнаруживает шведский национальный идентификатор|Да|
|Func_swiss_social_security_number_ahv|обнаруживает номер социального обеспечения (AHV) для Швейцарии|Нет|
|Func_taiwanese_national_id |обнаруживает национальный ид тайваньского|Нет|
|Func_tennessee_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_texas_drivers_license_number  |определяет номер водительского удостоверения в Техасе|Нет|
|Func_Thai_Citizen_Id   |обнаруживает ИД тайских граждан|Нет|
|Func_Turkish_National_Id|обнаруживает турецкий национальный ИД|Да|
|Func_uk_drivers_license|определяет водительское удостоверение для Соединенного Королевства|Нет|
|Func_uk_eu_tax_file_number|определяет уникальный номер налогоплательщика для Соединенного Королевства|Нет|
|Func_uk_nhs_number |определяет номер NHS для Соединенного Королевства|Да|
|Func_uk_nino   |определяет NINO для Соединенного Королевства|Нет|
|Func_unformatted_canadian_sin|обнаруживает неформатированный канадский SIN|Нет|
|Func_unformatted_itin  |обнаруживает неформатированные ИТ-11 для США|Да|
|Func_unformatted_ssn   |обнаруживает нестандартное неформатированное неформатированное SSN сша|Да|
|Func_usa_uk_passport   |обнаружение паспортов США и Соединенного Королевства|Да|
|Func_utah_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_vermont_drivers_license_number|определяет номер водительского удостоверения Ver вершины|Нет|
|Func_virginia_drivers_license_number|определяет номер водительского удостоверения|Нет|
|Func_washington_drivers_license_number|определяет номер водительского удостоверения в Вашингтоне|Нет|
|Func_west_virginia_drivers_license_number|определяет номер водительского удостоверения в Западной Востоке|Нет|
|Func_wisconsin_drivers_license_number  |определяет номер водительского удостоверения|Нет|
|Func_wyoming_drivers_license_number    |определяет номер водительского удостоверения Вайоминга|Нет|


## <a name="func_us_date"></a>Func_us_date

Func_us_date ищет даты в общих форматах США. Распространенные форматы: "месяц/день/год", "месяц-день-год" и "месяц день год". Названия или сокращения месяцев не чувствительны к делу. 
  
Примеры:
  
- 2 декабря 2016 г.
    
- 2 декабря 2016 г.
    
- 02.12.2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Принятые названия месяцев:
  
- Английский
    
  - Январь, февраль, март, апрель, май, июнь, июль, август, сентябрь, октябрь, ноябрь, декабрь
    
  - Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates ищет даты в общем e.U. форматы (и большинство мест за пределами США), такие как "день/месяц/год", "день-месяц-год" и "день месяц год". Названия или сокращения месяцев не чувствительны к делу.
  
Примеры:
  
- 2 декабря 2016 г.
    
- 02 декабря 2016 г.
    
- 2 декабря 16 г.
    
- 2/12/2016
    
- 02/12/16
    
- 2–Dec-2016
    
- 2-12-16
    
Принятые названия месяцев:
  
- Английский
    
  - Январь, февраль, март, апрель, май, июнь, июль, август, сентябрь, октябрь, ноябрь, декабрь
    
  - Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.
    
- Голландский
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul aug sep sept oct okt nov dec
    
- Французский
    
  - janvier, février, mars, avril, mai, juin juillet, aoгt, septembre, octobre, novembre, décembre
    
  - janv. févr. mars avril mai juin juil. ao антисайт. oct. nov. déc.
    
- Немецкий
    
  - jznuar, februar, mzrz, April, mai, juni juli, August, September, oktober, November, dezember
    
  - Jan./J жеn. Feb. Mzrz Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.
    
- Итальянский
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.
    
- Португальский
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
- Испанский
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (не рекомендуется)

> [!NOTE]
> Эта функция не поддерживается, так как она поддерживает только португальские названия месяцев, которые теперь включены в  `Func_eu_date` функцию выше. 
  
Эта функция служит для поиска даты в формате, принятом в португальском языке. Формат для этой функции такой же, как и в языке,  `Func_eu_date` который используется.
  
Примеры:
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
Принятые названия месяцев:
  
- Португальский
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (не рекомендуется)

> [!NOTE]
> Эта функция не поддерживается, так как она поддерживает только имена месяцев на нидерландском языке, которые теперь включены в  `Func_eu_date` функцию выше. 
  
Эта функция служит для поиска даты в формате, принятом в нидерландском языке. Формат для этой функции такой же, как и в языке,  `Func_eu_date` который используется.
  
Примеры:
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Принятые названия месяцев:
  
- Голландский
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul aug sep sept out okt nov dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date ищет даты в формате, обычно используемом кредитными и дебетовыми картами. Эта функция будет соответствовать датам в формате "месяц/год", "месяц-год", "[имя месяца] год" и "[аббревиатура месяца] год". Названия или сокращения месяцев не чувствительны к делу.
  
Примеры:
  
- ММ/ГГ (например, 01/11 или 1/11);
    
- ММ/ГГГГ (например, 01/2011 или 1/2011);
    
- ММ-ГГ (например, 01-22 или 1-11);
    
- ММ-ГГГГ (например, 01-2000 или 1-2000).
    
Следующие форматы поддерживают ГГ или ГГГГ:
  
- Month-YYYY — например, январь-2010 или январь-2010, янв-10 или январь-10
    
- Месяц ГГГГ (например, "январь 2010", "янв 2010", "январь 10" или "янв 10");
    
- МесяцГГГГ (например, "январь2010", "янв2010", "январь10" или "янв10");
    
- Месяц/YYYY — например, "январь/2010", "Янв/2010", "январь/10" или "Янв/10"
    
Принятые названия месяцев:
  
- Английский
    
  - Январь, февраль, март, апрель, май, июнь, июль, август, сентябрь, октябрь, ноябрь, декабрь
    
  - Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address ищет название штата США или название почтовой аббревиатуры, а затем допустимый почтовый индекс. Необходимо указать правильный почтовый индекс, соответствующий названию штата США или его аббревиатуре. Название штата США и почтовый индекс не должны разделяться знаками пунктуации или буквами.
  
Примеры:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
