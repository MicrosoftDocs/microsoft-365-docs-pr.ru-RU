---
title: Какие функции по предотвращению потери данных (DLP)
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
recommendations: false
description: Узнайте, какие функции по предотвращению потери данных (DLP) выполняются.
ms.openlocfilehash: 47eda79470fd131939c493ac4f66af6efea01dd6
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086516"
---
# <a name="what-the-dlp-functions-look-for"></a>Сведения, для обнаружения которых используются функции защиты от потери данных

Политики предотвращения потери данных (DLP) могут использовать типы конфиденциальной информации для идентификации конфиденциальных элементов. Номер кредитной карты и номер дебетовой карты ЕС являются примерами типов конфиденциальной информации. Типы конфиденциальных сведений искать определенные шаблоны. Типы конфиденциальных сведений проверяют данные, глядя на его формат, это контрольные списки, а также ищет соответствующие ключевые слова или другую информацию. Для некоторых из этих проверок используются внешние функции. Например, тип конфиденциальной информации о номере кредитной карты использует функцию, чтобы искать даты, форматированные как дата истечения срока действия. Это позволяет подтвердить, что номер — это номер кредитной карты.
  
В этой статье рассказывается о том, какие функции выполняют эти функции, чтобы понять, как работают предопределяемы типы конфиденциальной информации. Дополнительные сведения см. в виде определений сущности [типа конфиденциальной информации](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>Таблица функций

|имя функции  |действие функции  |является валидатором|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|обнаруживает и проверяет уникальный налоговый ключ Аргентины|нет|
|Func_aba_routing|обнаруживает номер маршрутивки ABA| Да|
|Func_alabama_drivers_license_number|обнаруживает номер лицензии водителя Алабамы|нет|
|Func_alaska_delaware_oregon_drivers_license_number|обнаруживает номер лицензии на Аляску, Делавэр, Орегон|нет|
|Func_alaska_drivers_license_number|обнаруживает номер лицензии водителя Аляски|нет|
|Func_alberta_drivers_license_number|определяет номер водительских прав в Альберте|нет|
|Func_Argentina_Unique_Tax_Key|обнаруживает уникальный налоговый ключ Аргентины|нет|
|Func_arizona_drivers_license_number|определяет номер лицензии водителя Аризоны|нет|
|Func_arkansas_drivers_license_number|обнаруживает номер лицензии водителя Arkansas|нет|
|Func_australian_business_number|обнаруживает бизнес-номер Австралии|нет|
|Func_Australian_Company_Number|определяет номер компании в Австралии|нет|
|Func_australian_medical_account_number|обнаруживает номер медицинской учетной записи Австралии|нет|
|Func_australian_tax_file_number|обнаруживает номер налогового файла Австралии|Да|
|Func_austria_eu_ssn_or_equivalent|определяет номер социального обеспечения в Австрии|нет|
|Func_austria_eu_tax_file_number|определяет номер налогового файла в Австрии|нет|
|Func_Austria_Value_Added_Tax|определяет налог на добавленную стоимость в Австрии|нет|
|Func_belgium_national_number|определяет национальный номер Бельгии|нет|
|Func_belgium_value_added_tax_number|определяет номер налога на добавленную стоимость в Бельгии|нет|
|Func_brazil_cnpj|обнаруживает номер юридического лица Бразилии (CNPJ)|Да|
|Func_brazil_cpf|обнаруживает Бразилии CPF|Да|
|Func_brazil_rg|обнаруживает RG Бразилии|нет|
|Func_british_columbia_drivers_license_number|определяет номер водительских прав в Британской Колумбии|нет|
|Func_bulgaria_eu_national_id_card|определяет единый гражданский номер Болгарии|нет|
|Func_california_drivers_license_number|определяет номер лицензии пилота в Калифорнии|нет|
|Func_canadian_sin|обнаруживает грех Канады|Да|
|Func_chile_id_card|обнаруживает удостоверение личности Чили|нет|
|Func_china_resident_id|обнаруживает ID резидента Китая|нет|
|Func_colorado_drivers_license_number|обнаруживает номер водительских прав в Колорадо|нет|
|Func_connecticut_drivers_license_number|определяет номер лицензии водителя Connecticut|нет|
|Func_credit_card|обнаруживает кредитную карту|да|нет|
|Func_croatia_id_card|обнаруживает удостоверение личности Хорватии|нет|
|Func_croatia_oib_number|определяет номер OIB в Хорватии|нет|
|Func_cyprus_eu_tax_file_number|обнаруживает номер кипрского налогового файла|нет|
|Func_czech_id_card|обнаруживает чешскую ID-карту|нет|
|Func_czech_id_card_new_format|обнаружение чешской ID-карты в новом формате|нет|
|Func_dea_number|обнаруживает номер DEA|Да|
|Func_denmark_eu_tax_file_number|обнаруживает личный идентификационный номер Дании|нет|
|Func_district_of_columbia_drivers_license_number|определяет номер водительских прав округа Колумбия|нет|
|Func_estonia_eu_national_id_card|обнаружение кода идентификации личности в Эстонии|нет|
|Func_eu_debit_card|обнаруживает дебетовую карту ЕС|нет|
|Func_finnish_national_id|обнаружение финского национального ID|нет|
|Func_florida_drivers_license_number|обнаруживает номер водительской лицензии Флориды|нет|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|обнаруживает номер водительских прав во Флориде, Мэриленде, Мичигане и Миннесоте|нет|
|Func_formatted_itin|обнаруживает отформатированные ITIN США|Да|
|Func_fr_insee|обнаруживает Францию INSEE|нет|
|Func_fr_passport|обнаруживает паспорт Франции|нет|
|Func_france_eu_tax_file_number|определяет номер налогового файла Франции|нет|
|Func_france_value_added_tax_number|определяет номер налога на добавленную стоимость во Франции|нет|
|Func_french_drivers_license|обнаруживает французские водительские права|нет|
|Func_french_insee|обнаруживает французский INSEE|нет|
|Func_georgia_drivers_license_number|определяет номер водительского удостоверения Джорджии|нет|
|Func_german_drivers_license|обнаружение водительских прав в Германии|нет|
|Func_german_passport|обнаруживает паспорт Германии|нет|
|Func_german_passport_data|обнаруживает паспорт Германии|нет|
|Func_germany_eu_tax_file_number|обнаруживает номер налогового файла Германии|нет|
|Func_germany_value_added_tax_number|определяет номер налога на добавленную стоимость в Германии|нет|
|Func_greece_eu_ssn|обнаруживает грех Греции (AMKA)|нет|
|Func_hawaii_drivers_license_number|определяет номер водительских прав на Гавайях|нет|
|Func_hong_kong_id_card |обнаруживает ID-карту Гонконга|нет|
|Func_hungarian_value_added_tax_number|определяет номер налога на добавленную стоимость в Венгрии|нет|
|Func_hungary_eu_national_id_card|обнаруживает личный идентификационный номер Венгрии|нет|
|Func_hungary_eu_ssn_or_equivalent|определяет номер социального обеспечения в Венгрии|нет|
|Func_hungary_eu_tax_file_number|обнаруживает номер налогового файла Венгрии|нет|
|Func_iban|обнаруживает IBAN|Да|
|Func_idaho_drivers_license_number|определяет номер лицензии водителя Айдахо|нет|
|Func_illinois_drivers_license_number|определяет номер водительских прав штата Иллинойс|нет|
|Func_india_aadhaar|обнаруживает Индию aadhaar|Да|
|Func_indiana_drivers_license_number|обнаруживает номер водительских прав Индианы|нет|
|Func_iowa_drivers_license_number|определяет номер лицензии водителя Айовы|нет|
|Func_ireland_pps|обнаруживает PPS Ирландии|нет|
|Func_israeli_national_id_number|обнаруживает номер национального ID Израиля|нет|
|Func_italy_eu_national_id_card |обнаруживает финансовый код Италии|нет|
|Func_italy_value_added_tax_number|определяет номер налога на добавленную стоимость в Италии|нет|
|Func_japanese_my_number_corporate|обнаруживает Японию мой корпоративный номер|Да|
|Func_japanese_my_number_personal|обнаруживает Японию мой личный номер|Да|
|Func_jp_bank_account|обнаруживает банковский счет в Японии|нет|
|Func_jp_bank_account_branch_code|обнаруживает код филиала учетной записи банка Японии|нет|
|Func_jp_drivers_license_number|определяет номер водительских прав в Японии|нет|
|Func_jp_passport|обнаруживает паспорт Японии|нет|
|Func_jp_resident_registration_number|определяет регистрационный номер резидента Японии|нет|
|Func_jp_sin|обнаруживает Син Японии|нет|
|Func_jp_sin_pre_1997|обнаруживает Японию до 1997 г.|нет|
|Func_kansas_drivers_license_number|определяет номер лицензии водителя в Канзасе|нет|
|Func_kentucky_drivers_license_number|определяет номер водительских прав в Кентукки|нет|
|Func_kentucky_massachusetts_virginia_drivers_license_number|определяет номер водительских прав в Кентукки, Массачусетсе и Вирджинии|нет|
|Func_latvia_eu_national_id_card|обнаруживает личный код Латвии|нет|
|Func_lithuania_eu_tax_file_number|обнаруживает личный код Литвы|нет|
|Func_louisiana_drivers_license_number|обнаруживает номер лицензии водителя Луизианы|нет|
|Func_luxemburg_eu_tax_file_number|обнаруживает национальный идентификационный номер Люксембурга (естественные лица)|нет|
|Func_luxemburg_eu_tax_file_number_non_natural|обнаруживает номер национальной идентификации в Люксембурге (не естественное лицо)|нет|
|Func_maine_drivers_license_number|определяет номер водительских прав в Maine|нет|
|Func_manitoba_drivers_license_number|определяет номер водительских прав Manitoba|нет|
|Func_maryland_drivers_license_number|обнаруживает номер водительских прав в Мэриленде|нет|
|Func_massachusetts_drivers_license_number|обнаруживает номер водительских прав в Штате Массачусетс|нет|
|Func_mexico_population_registry_code|обнаруживает код реестра населения Мексики|нет|
|Func_michigan_minnesota_drivers_license_number|определяет номер лицензии водителя в Штате Миннесота|нет|
|Func_minnesota_drivers_license_number|определяет номер водительских прав в Штате Миннесота|нет|
|Func_mississippi_oklahoma_drivers_license_number|обнаруживает миссисипи, номер водительской лицензии Оклахомы|нет|
|Func_missouri_drivers_license_number|определяет номер водительских прав в Штате Миссури|нет|
|Func_montana_drivers_license_number|обнаруживает номер водительских прав в Монтане|нет|
|Func_nebraska_drivers_license_number|определяет номер водительских прав Nebraska|нет|
|Func_netherlands_bsn|обнаруживает Нидерланды BSN|нет|
|Func_netherlands_eu_tax_file_number|обнаруживает номер налогового файла Нидерландов|нет|
|Func_netherlands_value_added_tax_number|определяет номер налога на добавленную стоимость в Нидерландах|нет|
|Func_nevada_drivers_license_number|определяет номер лицензии водителя Невады|нет|
|Func_new_brunswick_drivers_license_number|обнаруживает номер лицензии водителя New Brunswick|нет|
|Func_new_hampshire_drivers_license_number|обнаруживает номер водительских прав в Нью-Гемпшире|нет|
|Func_new_jersey_drivers_license_number |обнаруживает номер лицензии водителя в Нью-Джерси|нет|
|Func_new_mexico_drivers_license_number |обнаруживает номер водительских прав в Нью-Мексико|нет|
|Func_new_york_drivers_license_number   |обнаруживает номер водительских прав в Нью-Йорке|нет|
|Func_new_zealand_bank_account_number   |обнаруживает номер банковского счета в Новой Зеландии|нет|
|Func_new_zealand_inland_revenue_number |определяет число внутренних доходов в Новой Зеландии|нет|
|Func_new_zealand_ministry_of_health_number|обнаруживает номер министерства здравоохранения Новой Зеландии|нет|
|Func_newfoundland_labrador_drivers_license_number|обнаруживает номер лицензии водителя Newfoundland Labrador|нет|
|Func_newzealand_driver_license_number  |определяет номер водительского удостоверения Новой Зеландии|нет|
|Func_newzealand_social_welfare_number  |определяет номер социального обеспечения в Новой Зеландии|нет|
|Func_north_carolina_drivers_license_number|обнаруживает номер водительских прав в Северной Каролине|нет|
|Func_north_dakota_drivers_license_number|определяет номер водительских прав в Северной Дакоте|нет|
|Func_norway_id_number  |обнаруживает номер норвежского ID|нет|
|Func_nova_scotia_drivers_license_number|обнаруживает номер водительских прав Nova Scotia|нет|
|Func_ohio_drivers_license_number   |определяет номер водительских прав в Огайо|нет|
|Func_ontario_drivers_license_number    |определяет номер водительских прав Онтарио|нет|
|Func_pennsylvania_drivers_license_number|обнаруживает номер лицензии водителя Пенсильвании|нет|
|Func_pesel_identification_number   |обнаружение польского национального ID (PESEL)|нет|
|Func_poland_eu_tax_file_number |определяет номер налогового файла Польши|нет|
|Func_polish_national_id    |обнаруживает удостоверение личности в Польше|нет|
|Func_polish_passport_number    |определяет номер польского паспорта|нет|
|Func_polish_regon_number   |обнаруживает польский номер REGON|нет|
|Func_portugal_eu_tax_file_number|определяет номер идентификации налога в Португалии|нет|
|Func_prince_edward_island_drivers_license_number|обнаруживает номер лицензии водителя острова Принца Эдуарда|нет|
|Func_quebec_drivers_license_number |обнаруживает номер лицензии водителя Квебека|нет|
|Func_randomized_formatted_ssn  |обнаруживает рандомизированный форматированный SSN США|Да|
|Func_randomized_unformatted_ssn|обнаруживает рандомизированные неформатированные SSN США|Да|
|Func_rhode_island_drivers_license_number|обнаруживает номер лицензии водителя Род-Айленда|нет|
|Func_romania_eu_national_id_card   |обнаруживает личный числимый код Румынии (CNP)|нет|
|Func_saskatchewan_drivers_license_number|обнаруживает номер водительских прав Saskatchewan|нет|
|Func_slovakia_eu_national_id_card  |определяет личный номер Словакии|нет|
|Func_slovenia_eu_national_id_card  |определяет уникальный номер гражданина Словении|нет|
|Func_slovenia_eu_tax_file_number   |определяет номер налогового файла Словении|нет|
|Func_south_africa_identification_number|обнаруживает идентификационный номер Южной Африки|Да|
|Func_south_carolina_drivers_license_number|обнаруживает номер водительских прав в Южной Каролине|нет|
|Func_south_dakota_drivers_license_number|определяет номер водительских прав в Южной Дакоте|нет|
|Func_south_korea_resident_number   |определяет номер резидента Южной Кореи|нет|
|Func_spain_eu_DL_and_NI_number_citizen |обнаруживает гражданина номеров Испании DL и NI|нет|
|Func_spain_eu_DL_and_NI_number_foreigner|обнаруживает иностранцев номеров DL и NI в Испании|нет|
|Func_spain_eu_driver s_license_number  |определяет номер водительских прав в Испании|нет|
|Func_spain_eu_tax_file_number  |определяет номер налогового файла Испании|нет|
|Func_spanish_social_security_number|обнаруживает номер испанского социального обеспечения|нет|
|Func_ssn   |Функция обнаружения неадомизированных форматизированных SSN США|Да|
|Func_sweden_eu_tax_file_number|обнаруживает номер налогового файла Швеции|нет|
|Func_swedish_national_identifier|обнаружение национального идентификатора Швеции|Да|
|Func_swiss_social_security_number_ahv|обнаруживает швейцарский номер социального обеспечения AHV|нет|
|Func_taiwanese_national_id |обнаружение тайваньского национального ID|нет|
|Func_tennessee_drivers_license_number|обнаруживает номер лицензии водителей Теннесси|нет|
|Func_texas_drivers_license_number  |определяет номер лицензии водителя Техаса|нет|
|Func_Thai_Citizen_Id   |обнаруживает ИД гражданина Таиланда|нет|
|Func_Turkish_National_Id|обнаружение турецкого национального ID|Да|
|Func_uk_drivers_license|обнаруживает водительские права Великобритании|нет|
|Func_uk_eu_tax_file_number|определяет уникальный номер налогоплательщика Великобритании|нет|
|Func_uk_nhs_number |detects UK NHS number|Да|
|Func_uk_nino   |обнаруживает NINO Великобритании|нет|
|Func_unformatted_canadian_sin|обнаружение неформатированной канадской sin|нет|
|Func_unformatted_itin  |обнаруживает unformatted US ITIN|Да|
|Func_unformatted_ssn   |обнаруживает не рандомизированные неформатированные SSN США|Да|
|Func_usa_uk_passport   |обнаружение паспорта США и Великобритании|Да|
|Func_utah_drivers_license_number|определяет номер водительских прав в штате Юта|нет|
|Func_vermont_drivers_license_number|обнаруживает номер водительских прав Вермонта|нет|
|Func_virginia_drivers_license_number|обнаруживает номер водительских прав в Штате Вирджиния|нет|
|Func_washington_drivers_license_number|определяет номер водительских прав в Вашингтоне|нет|
|Func_west_virginia_drivers_license_number|определяет номер лицензии водителя в Западной Вирджинии|нет|
|Func_wisconsin_drivers_license_number  |обнаруживает номер водительских прав в Висконсине|нет|
|Func_wyoming_drivers_license_number    |обнаруживает номер водительских прав в Вайоминге|нет|


## <a name="func_us_date"></a>Func_us_date

Func_us_date ищет даты в обычных американских форматах. Общие форматы: "месяц/день/год", "месяц-день-год" и "год дня месяца". Имена или аббревиатуры месяцев не являются чувствительными к делу. 
  
Примеры:
  
- 2 декабря 2016 г.
    
- 2 декабря 2016 г.
    
- dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Принятые названия месяцев:
  
- Английский
    
  - Январь, февраль, апрель, май, июнь, июль, август, сентябрь, октябрь, ноябрь, декабрь
    
  - Январь. Февраль. Март. Apr. Май июнь июль авг. Сентябрь. Октябрь Nov. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates ищет даты в общем ЕАО. форматы (и большинство мест за пределами США), такие как "день/месяц/год", "день-месяц-год" и "день месяца года". Имена или аббревиатуры месяцев не являются чувствительными к делу.
  
Примеры:
  
- 2 декабря 2016 г.
    
- 02 декабря 2016 г.
    
- 2 декабря 16
    
- 2/12/2016
    
- 02/12/16
    
- 2 декабря 2016 г.
    
- 2-12-16
    
Принятые названия месяцев:
  
- Английский
    
  - Январь, февраль, апрель, май, июнь, июль, август, сентябрь, октябрь, ноябрь, декабрь
    
  - Январь. Февраль. Март. Apr. Май июнь июль авг. Сентябрь. Октябрь Nov. Dec.
    
- Голландский
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul aug sep sept okt nov dec
    
- Французский
    
  - janvier, février, mars, avril, mai, juin juillet, aoūt, septembre, octobre, novembre, décembre
    
  - janv. févr. Mars avril mai juin juil. aoūt sept. oct. nov. déc.
    
- Немецкий
    
  - jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember
    
  - Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.
    
- Итальянский
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. febbr. mar. apr. magg. giugno luglio ag. sett. Отт. nov. dic.
    
- Португальский
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
- Испанский
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (не рекомендуется)

> [!NOTE]
> Эта функция отстает, так как поддерживает только имена португальских месяцев, которые теперь включены в  `Func_eu_date` вышеуказанную функцию. 
  
Эта функция служит для поиска даты в формате, принятом в португальском языке. Формат этой функции такой  `Func_eu_date` же, как и у используемого языка.
  
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
> Эта функция отстает, так как поддерживает только имена нидерландских месяцев, которые теперь включены в  `Func_eu_date` вышеуказанную функцию. 
  
Эта функция служит для поиска даты в формате, принятом в нидерландском языке. Формат этой функции такой  `Func_eu_date` же, как и у используемого языка.
  
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

Func_expiration_date ищет даты, которые находятся в форматах, обычно используемых кредитными и дебетовыми картами. Эта функция будет совпадать с датами в формате "месяц/год", "месяц-год", "[имя месяца] год" и "[месячная аббревиатура] год". Имена или аббревиатуры месяцев не являются чувствительными к делу.
  
Примеры:
  
- ММ/ГГ (например, 01/11 или 1/11);
    
- ММ/ГГГГ (например, 01/2011 или 1/2011);
    
- ММ-ГГ (например, 01-22 или 1-11);
    
- ММ-ГГГГ (например, 01-2000 или 1-2000).
    
Следующие форматы поддерживают ГГ или ГГГГ:
  
- Month-YYYYY — например, январь-2010 или январь-2010 или январь-10 января
    
- Месяц ГГГГ (например, "январь 2010", "янв 2010", "январь 10" или "янв 10");
    
- МесяцГГГГ (например, "январь2010", "янв2010", "январь10" или "янв10");
    
- Month/YYYY — например, "январь/2010", "Январь/2010", "январь/10" или "Январь/10"
    
Принятые названия месяцев:
  
- Английский
    
  - Январь, февраль, апрель, май, июнь, июль, август, сентябрь, октябрь, ноябрь, декабрь
    
  - Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address ищет имя или аббревиатура почтовых сообщений США, за которым следует допустимый почтовый индекс. Необходимо указать правильный почтовый индекс, соответствующий названию штата США или его аббревиатуре. Название штата США и почтовый индекс не должны разделяться знаками пунктуации или буквами.
  
Примеры:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
