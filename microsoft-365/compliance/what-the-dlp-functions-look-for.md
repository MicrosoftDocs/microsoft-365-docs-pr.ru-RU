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
ms.openlocfilehash: 787abc1e7fb4c95392a76f7514ceffd3f7f4dda0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288099"
---
# <a name="what-the-dlp-functions-look-for"></a>Сведения, для обнаружения которых используются функции защиты от потери данных

Политики предотвращения потери данных (DLP) могут использовать типы конфиденциальной информации для идентификации конфиденциальных элементов. Номер кредитной карты и номер дебетовой карты ЕС являются примерами типов конфиденциальной информации. Типы конфиденциальных сведений искать определенные шаблоны. Типы конфиденциальных сведений проверяют данные, глядя на его формат, это контрольные списки, а также ищет соответствующие ключевые слова или другую информацию. Для некоторых из этих проверок используются внешние функции. Например, тип конфиденциальной информации о номере кредитной карты использует функцию, чтобы искать даты, форматированные как дата истечения срока действия. Это позволяет подтвердить, что номер — это номер кредитной карты.

В этой статье рассказывается о том, какие функции выполняют эти функции, чтобы понять, как работают предопределяемы типы конфиденциальной информации. Дополнительные сведения см. в виде определений сущности [типа конфиденциальной информации](sensitive-information-type-entity-definitions.md)

## <a name="table-of-functions"></a>Таблица функций

<br>

****

|имя функции|действие функции|является валидатором|
|---|---|:---:|
|Func_Argentina_Unique_Tax_Key|обнаруживает и проверяет уникальный налоговый ключ Аргентины|Нет|
|Func_aba_routing|обнаруживает номер маршрутивки ABA|да|
|Func_alabama_drivers_license_number|обнаруживает номер лицензии водителя Алабамы|Нет|
|Func_alaska_delaware_oregon_drivers_license_number|обнаруживает номер лицензии на Аляску, Делавэр, Орегон|Нет|
|Func_alaska_drivers_license_number|обнаруживает номер лицензии водителя Аляски|Нет|
|Func_alberta_drivers_license_number|определяет номер водительских прав в Альберте|Нет|
|Func_Argentina_Unique_Tax_Key|обнаруживает уникальный налоговый ключ Аргентины|Нет|
|Func_arizona_drivers_license_number|определяет номер лицензии водителя Аризоны|Нет|
|Func_arkansas_drivers_license_number|обнаруживает номер лицензии водителя Arkansas|Нет|
|Func_australian_business_number|обнаруживает бизнес-номер Австралии|Нет|
|Func_Australian_Company_Number|определяет номер компании в Австралии|Нет|
|Func_australian_medical_account_number|обнаруживает номер медицинской учетной записи Австралии|Нет|
|Func_australian_tax_file_number|обнаруживает номер налогового файла Австралии|да|
|Func_austria_eu_ssn_or_equivalent|определяет номер социального обеспечения в Австрии|Нет|
|Func_austria_eu_tax_file_number|определяет номер налогового файла в Австрии|Нет|
|Func_Austria_Value_Added_Tax|определяет налог на добавленную стоимость в Австрии|Нет|
|Func_belgium_national_number|определяет национальный номер Бельгии|Нет|
|Func_belgium_value_added_tax_number|определяет номер налога на добавленную стоимость в Бельгии|Нет|
|Func_brazil_cnpj|обнаруживает номер юридического лица Бразилии (CNPJ)|да|
|Func_brazil_cpf|обнаруживает Бразилии CPF|да|
|Func_brazil_rg|обнаруживает RG Бразилии|Нет|
|Func_british_columbia_drivers_license_number|определяет номер водительских прав в Британской Колумбии|Нет|
|Func_bulgaria_eu_national_id_card|определяет единый гражданский номер Болгарии|Нет|
|Func_california_drivers_license_number|определяет номер лицензии пилота в Калифорнии|Нет|
|Func_canadian_sin|обнаруживает грех Канады|да|
|Func_chile_id_card|обнаруживает удостоверение личности Чили|Нет|
|Func_china_resident_id|обнаруживает ID резидента Китая|Нет|
|Func_colorado_drivers_license_number|обнаруживает номер водительских прав в Колорадо|Нет|
|Func_connecticut_drivers_license_number|определяет номер лицензии водителя Connecticut|Нет|
|Func_credit_card|обнаруживает кредитную карту|да|
|Func_croatia_id_card|обнаруживает удостоверение личности Хорватии|Нет|
|Func_croatia_oib_number|определяет номер OIB в Хорватии|Нет|
|Func_cyprus_eu_tax_file_number|обнаруживает номер кипрского налогового файла|Нет|
|Func_czech_id_card|обнаруживает чешскую ID-карту|Нет|
|Func_czech_id_card_new_format|обнаружение чешской ID-карты в новом формате|Нет|
|Func_dea_number|обнаруживает номер DEA|да|
|Func_denmark_eu_tax_file_number|обнаруживает личный идентификационный номер Дании|Нет|
|Func_district_of_columbia_drivers_license_number|определяет номер водительских прав округа Колумбия|Нет|
|Func_estonia_eu_national_id_card|обнаружение кода идентификации личности в Эстонии|Нет|
|Func_eu_debit_card|обнаруживает дебетовую карту ЕС|Нет|
|Func_finnish_national_id|обнаружение финского национального ID|Нет|
|Func_florida_drivers_license_number|обнаруживает номер водительской лицензии Флориды|Нет|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|обнаруживает номер водительских прав во Флориде, Мэриленде, Мичигане и Миннесоте|Нет|
|Func_formatted_itin|обнаруживает отформатированные ITIN США|да|
|Func_fr_insee|обнаруживает Францию INSEE|Нет|
|Func_fr_passport|обнаруживает паспорт Франции|Нет|
|Func_france_eu_tax_file_number|определяет номер налогового файла Франции|Нет|
|Func_france_value_added_tax_number|определяет номер налога на добавленную стоимость во Франции|Нет|
|Func_french_drivers_license|обнаруживает французские водительские права|Нет|
|Func_french_insee|обнаруживает французский INSEE|Нет|
|Func_georgia_drivers_license_number|определяет номер водительского удостоверения Джорджии|Нет|
|Func_german_drivers_license|обнаружение водительских прав в Германии|Нет|
|Func_german_passport|обнаруживает паспорт Германии|Нет|
|Func_german_passport_data|обнаруживает паспорт Германии|Нет|
|Func_germany_eu_tax_file_number|обнаруживает номер налогового файла Германии|Нет|
|Func_germany_value_added_tax_number|определяет номер налога на добавленную стоимость в Германии|Нет|
|Func_greece_eu_ssn|обнаруживает грех Греции (AMKA)|Нет|
|Func_hawaii_drivers_license_number|определяет номер водительских прав на Гавайях|Нет|
|Func_hong_kong_id_card|обнаруживает ID-карту Гонконга|Нет|
|Func_hungarian_value_added_tax_number|определяет номер налога на добавленную стоимость в Венгрии|Нет|
|Func_hungary_eu_national_id_card|обнаруживает личный идентификационный номер Венгрии|Нет|
|Func_hungary_eu_ssn_or_equivalent|определяет номер социального обеспечения в Венгрии|Нет|
|Func_hungary_eu_tax_file_number|обнаруживает номер налогового файла Венгрии|Нет|
|Func_iban|обнаруживает IBAN|да|
|Func_idaho_drivers_license_number|определяет номер лицензии водителя Айдахо|Нет|
|Func_illinois_drivers_license_number|определяет номер водительских прав штата Иллинойс|Нет|
|Func_india_aadhaar|обнаруживает Индию aadhaar|да|
|Func_indiana_drivers_license_number|обнаруживает номер водительских прав Индианы|Нет|
|Func_iowa_drivers_license_number|определяет номер лицензии водителя Айовы|Нет|
|Func_ireland_pps|обнаруживает PPS Ирландии|Нет|
|Func_israeli_national_id_number|обнаруживает номер национального ID Израиля|Нет|
|Func_italy_eu_national_id_card|обнаруживает финансовый код Италии|Нет|
|Func_italy_value_added_tax_number|определяет номер налога на добавленную стоимость в Италии|Нет|
|Func_japanese_my_number_corporate|обнаруживает Японию мой корпоративный номер|да|
|Func_japanese_my_number_personal|обнаруживает Японию мой личный номер|да|
|Func_jp_bank_account|обнаруживает банковский счет в Японии|Нет|
|Func_jp_bank_account_branch_code|обнаруживает код филиала учетной записи банка Японии|Нет|
|Func_jp_drivers_license_number|определяет номер водительских прав в Японии|Нет|
|Func_jp_passport|обнаруживает паспорт Японии|Нет|
|Func_jp_resident_registration_number|определяет регистрационный номер резидента Японии|Нет|
|Func_jp_sin|обнаруживает Син Японии|Нет|
|Func_jp_sin_pre_1997|обнаруживает Японию до 1997 г.|Нет|
|Func_kansas_drivers_license_number|определяет номер лицензии водителя в Канзасе|Нет|
|Func_kentucky_drivers_license_number|определяет номер водительских прав в Кентукки|Нет|
|Func_kentucky_massachusetts_virginia_drivers_license_number|определяет номер водительских прав в Кентукки, Массачусетсе и Вирджинии|Нет|
|Func_latvia_eu_national_id_card|обнаруживает личный код Латвии|Нет|
|Func_lithuania_eu_tax_file_number|обнаруживает личный код Литвы|Нет|
|Func_louisiana_drivers_license_number|обнаруживает номер лицензии водителя Луизианы|Нет|
|Func_luxemburg_eu_tax_file_number|обнаруживает национальный идентификационный номер Люксембурга (естественные лица)|Нет|
|Func_luxemburg_eu_tax_file_number_non_natural|обнаруживает номер национальной идентификации в Люксембурге (не естественное лицо)|Нет|
|Func_maine_drivers_license_number|определяет номер водительских прав в Maine|Нет|
|Func_manitoba_drivers_license_number|определяет номер водительских прав Manitoba|Нет|
|Func_maryland_drivers_license_number|обнаруживает номер водительских прав в Мэриленде|Нет|
|Func_massachusetts_drivers_license_number|обнаруживает номер водительских прав в Штате Массачусетс|Нет|
|Func_mexico_population_registry_code|обнаруживает код реестра населения Мексики|Нет|
|Func_michigan_minnesota_drivers_license_number|определяет номер лицензии водителя в Штате Миннесота|Нет|
|Func_minnesota_drivers_license_number|определяет номер водительских прав в Штате Миннесота|Нет|
|Func_mississippi_oklahoma_drivers_license_number|обнаруживает миссисипи, номер водительской лицензии Оклахомы|Нет|
|Func_missouri_drivers_license_number|определяет номер водительских прав в Штате Миссури|Нет|
|Func_montana_drivers_license_number|обнаруживает номер водительских прав в Монтане|Нет|
|Func_nebraska_drivers_license_number|определяет номер водительских прав Nebraska|Нет|
|Func_netherlands_bsn|обнаруживает Нидерланды BSN|Нет|
|Func_netherlands_eu_tax_file_number|обнаруживает номер налогового файла Нидерландов|Нет|
|Func_netherlands_value_added_tax_number|определяет номер налога на добавленную стоимость в Нидерландах|Нет|
|Func_nevada_drivers_license_number|определяет номер лицензии водителя Невады|Нет|
|Func_new_brunswick_drivers_license_number|обнаруживает номер лицензии водителя New Brunswick|Нет|
|Func_new_hampshire_drivers_license_number|обнаруживает номер водительских прав в Нью-Гемпшире|Нет|
|Func_new_jersey_drivers_license_number|обнаруживает номер лицензии водителя в Нью-Джерси|Нет|
|Func_new_mexico_drivers_license_number|обнаруживает номер водительских прав в Нью-Мексико|Нет|
|Func_new_york_drivers_license_number|обнаруживает номер водительских прав в Нью-Йорке|Нет|
|Func_new_zealand_bank_account_number|обнаруживает номер банковского счета в Новой Зеландии|Нет|
|Func_new_zealand_inland_revenue_number|определяет число внутренних доходов в Новой Зеландии|Нет|
|Func_new_zealand_ministry_of_health_number|обнаруживает номер министерства здравоохранения Новой Зеландии|Нет|
|Func_newfoundland_labrador_drivers_license_number|обнаруживает номер лицензии водителя Newfoundland Labrador|Нет|
|Func_newzealand_driver_license_number|определяет номер водительского удостоверения Новой Зеландии|Нет|
|Func_newzealand_social_welfare_number|определяет номер социального обеспечения в Новой Зеландии|Нет|
|Func_north_carolina_drivers_license_number|обнаруживает номер водительских прав в Северной Каролине|Нет|
|Func_north_dakota_drivers_license_number|определяет номер водительских прав в Северной Дакоте|Нет|
|Func_norway_id_number|обнаруживает номер норвежского ID|Нет|
|Func_nova_scotia_drivers_license_number|обнаруживает номер водительских прав Nova Scotia|Нет|
|Func_ohio_drivers_license_number|определяет номер водительских прав в Огайо|Нет|
|Func_ontario_drivers_license_number|определяет номер водительских прав Онтарио|Нет|
|Func_pennsylvania_drivers_license_number|обнаруживает номер лицензии водителя Пенсильвании|Нет|
|Func_pesel_identification_number|обнаружение польского национального ID (PESEL)|Нет|
|Func_poland_eu_tax_file_number|определяет номер налогового файла Польши|Нет|
|Func_polish_national_id|обнаруживает удостоверение личности в Польше|Нет|
|Func_polish_passport_number|определяет номер польского паспорта|Нет|
|Func_polish_regon_number|обнаруживает польский номер REGON|Нет|
|Func_portugal_eu_tax_file_number|определяет номер идентификации налога в Португалии|Нет|
|Func_prince_edward_island_drivers_license_number|обнаруживает номер лицензии водителя острова Принца Эдуарда|Нет|
|Func_quebec_drivers_license_number|обнаруживает номер лицензии водителя Квебека|Нет|
|Func_randomized_formatted_ssn|обнаруживает рандомизированный форматированный SSN США|да|
|Func_randomized_unformatted_ssn|обнаруживает рандомизированные неформатированные SSN США|да|
|Func_rhode_island_drivers_license_number|обнаруживает номер лицензии водителя Род-Айленда|Нет|
|Func_romania_eu_national_id_card|обнаруживает личный числимый код Румынии (CNP)|Нет|
|Func_saskatchewan_drivers_license_number|обнаруживает номер водительских прав Saskatchewan|Нет|
|Func_slovakia_eu_national_id_card|определяет личный номер Словакии|Нет|
|Func_slovenia_eu_national_id_card|определяет уникальный номер гражданина Словении|Нет|
|Func_slovenia_eu_tax_file_number|определяет номер налогового файла Словении|Нет|
|Func_south_africa_identification_number|обнаруживает идентификационный номер Южной Африки|да|
|Func_south_carolina_drivers_license_number|обнаруживает номер водительских прав в Южной Каролине|Нет|
|Func_south_dakota_drivers_license_number|определяет номер водительских прав в Южной Дакоте|Нет|
|Func_south_korea_resident_number|определяет номер резидента Южной Кореи|Нет|
|Func_spain_eu_DL_and_NI_number_citizen|обнаруживает гражданина номеров Испании DL и NI|Нет|
|Func_spain_eu_DL_and_NI_number_foreigner|обнаруживает иностранцев номеров DL и NI в Испании|Нет|
|Func_spain_eu_driver s_license_number|определяет номер водительских прав в Испании|Нет|
|Func_spain_eu_tax_file_number|определяет номер налогового файла Испании|Нет|
|Func_spanish_social_security_number|обнаруживает номер испанского социального обеспечения|Нет|
|Func_ssn|Функция обнаружения неадомизированных форматизированных SSN США|да|
|Func_sweden_eu_tax_file_number|обнаруживает номер налогового файла Швеции|Нет|
|Func_swedish_national_identifier|обнаружение национального идентификатора Швеции|да|
|Func_swiss_social_security_number_ahv|обнаруживает швейцарский номер социального обеспечения AHV|Нет|
|Func_taiwanese_national_id|обнаружение тайваньского национального ID|Нет|
|Func_tennessee_drivers_license_number|обнаруживает номер лицензии водителей Теннесси|Нет|
|Func_texas_drivers_license_number|определяет номер лицензии водителя Техаса|Нет|
|Func_Thai_Citizen_Id|обнаруживает ИД гражданина Таиланда|Нет|
|Func_Turkish_National_Id|обнаружение турецкого национального ID|да|
|Func_uk_drivers_license|обнаруживает водительские права Великобритании|Нет|
|Func_uk_eu_tax_file_number|определяет уникальный номер налогоплательщика Великобритании|Нет|
|Func_uk_nhs_number|detects UK NHS number|да|
|Func_uk_nino|обнаруживает NINO Великобритании|Нет|
|Func_unformatted_canadian_sin|обнаружение неформатированной канадской sin|Нет|
|Func_unformatted_itin|обнаруживает unformatted US ITIN|да|
|Func_unformatted_ssn|обнаруживает не рандомизированные неформатированные SSN США|да|
|Func_usa_uk_passport|обнаружение паспорта США и Великобритании|да|
|Func_utah_drivers_license_number|определяет номер водительских прав в штате Юта|Нет|
|Func_vermont_drivers_license_number|обнаруживает номер водительских прав Вермонта|Нет|
|Func_virginia_drivers_license_number|обнаруживает номер водительских прав в Штате Вирджиния|Нет|
|Func_washington_drivers_license_number|определяет номер водительских прав в Вашингтоне|Нет|
|Func_west_virginia_drivers_license_number|определяет номер лицензии водителя в Западной Вирджинии|Нет|
|Func_wisconsin_drivers_license_number|обнаруживает номер водительских прав в Висконсине|Нет|
|Func_wyoming_drivers_license_number|обнаруживает номер водительских прав в Вайоминге|Нет|
|

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
