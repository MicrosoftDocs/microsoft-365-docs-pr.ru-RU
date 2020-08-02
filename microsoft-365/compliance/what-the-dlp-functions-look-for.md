---
title: Функции защиты от потери данных (DLP) для поиска
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
description: Сведения о функциях защиты от потери данных (DLP) для поиска.
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536314"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="38c78-103">Сведения, для обнаружения которых используются функции защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="38c78-103">What the DLP functions look for</span></span>

<span data-ttu-id="38c78-104">Защита от потери данных (DLP) включает типы конфиденциальных данных, такие как номер кредитной карты и номер дебетовой карты ЕС, которые готовы к использованию в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="38c78-104">Data loss prevention (DLP) includes sensitive information types, such as credit card Number and EU Debit card number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="38c78-105">Обычно эти типы конфиденциальной информации используются для поиска данных по определенному шаблону, при этом проводится проверка правильности форматирования, применения контрольных сумм, а также наличия соответствующих ключевых слов и других данных.</span><span class="sxs-lookup"><span data-stu-id="38c78-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="38c78-106">Для некоторых из этих проверок используются внешние функции.</span><span class="sxs-lookup"><span data-stu-id="38c78-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="38c78-107">Например, чтобы определить, что число является номером кредитной карты, проводится поиск дат, формат которых соответствует формату даты окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="38c78-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="38c78-108">В этой статье объясняется, что именно эти функции ищет, чтобы помочь вам разознать, как работают предопределенные типы конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="38c78-108">This article explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="38c78-109">Более подробную информацию можно узнать в статье [Определение объекта типа конфиденциальной информации](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="38c78-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="38c78-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="38c78-110">Func_us_date</span></span>

<span data-ttu-id="38c78-111">Эта функция ищет дату в формате, обычно используемом в США. К ним относятся форматы "месяц/день/год", "месяц-день-год" и "месяц суток год".</span><span class="sxs-lookup"><span data-stu-id="38c78-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="38c78-112">Полные или сокращенные названия месяцев вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="38c78-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="38c78-113">Примеры:</span><span class="sxs-lookup"><span data-stu-id="38c78-113">Examples:</span></span>
  
- <span data-ttu-id="38c78-114">2 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="38c78-114">December 2, 2016</span></span>
    
- <span data-ttu-id="38c78-115">2 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="38c78-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="38c78-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="38c78-116">dec 02 2016</span></span>
    
- <span data-ttu-id="38c78-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="38c78-117">12/2/2016</span></span>
    
- <span data-ttu-id="38c78-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="38c78-118">12/02/16</span></span>
    
- <span data-ttu-id="38c78-119">Dec – 2-2016</span><span class="sxs-lookup"><span data-stu-id="38c78-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="38c78-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="38c78-120">12-2-16</span></span>
    
<span data-ttu-id="38c78-121">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="38c78-121">Accepted month names:</span></span>
  
- <span data-ttu-id="38c78-122">English</span><span class="sxs-lookup"><span data-stu-id="38c78-122">English</span></span>
    
  - <span data-ttu-id="38c78-123">Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь</span><span class="sxs-lookup"><span data-stu-id="38c78-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="38c78-124">Февраль. Фев. Март. Апр. Май июня. сентября. Oct. Ноя. Дек.</span><span class="sxs-lookup"><span data-stu-id="38c78-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="38c78-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="38c78-125">Func_eu_date</span></span>

<span data-ttu-id="38c78-126">Эта функция ищет дату в формате, обычно используемом в Е.У.</span><span class="sxs-lookup"><span data-stu-id="38c78-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="38c78-127">(и большинством мест в США), например "день/месяц/год", "день-месяц-год" и "день месяца год".</span><span class="sxs-lookup"><span data-stu-id="38c78-127">(and most places outside the U.S.), such as "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="38c78-128">Полные или сокращенные названия месяцев вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="38c78-128">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="38c78-129">Примеры:</span><span class="sxs-lookup"><span data-stu-id="38c78-129">Examples:</span></span>
  
- <span data-ttu-id="38c78-130">2 декабря 2016</span><span class="sxs-lookup"><span data-stu-id="38c78-130">2 Dec 2016</span></span>
    
- <span data-ttu-id="38c78-131">02 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="38c78-131">02 dec 2016</span></span>
    
- <span data-ttu-id="38c78-132">2 декабря, 16 декабря</span><span class="sxs-lookup"><span data-stu-id="38c78-132">2 Dec 16</span></span>
    
- <span data-ttu-id="38c78-133">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="38c78-133">2/12/2016</span></span>
    
- <span data-ttu-id="38c78-134">02/12/16</span><span class="sxs-lookup"><span data-stu-id="38c78-134">02/12/16</span></span>
    
- <span data-ttu-id="38c78-135">2 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="38c78-135">2-Dec-2016</span></span>
    
- <span data-ttu-id="38c78-136">2-12-16</span><span class="sxs-lookup"><span data-stu-id="38c78-136">2-12-16</span></span>
    
<span data-ttu-id="38c78-137">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="38c78-137">Accepted month names:</span></span>
  
- <span data-ttu-id="38c78-138">English</span><span class="sxs-lookup"><span data-stu-id="38c78-138">English</span></span>
    
  - <span data-ttu-id="38c78-139">Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь</span><span class="sxs-lookup"><span data-stu-id="38c78-139">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="38c78-140">Февраль. Фев. Март. Апр. Май июня. сентября. Oct. Ноя. Дек.</span><span class="sxs-lookup"><span data-stu-id="38c78-140">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="38c78-141">Dutch</span><span class="sxs-lookup"><span data-stu-id="38c78-141">Dutch</span></span>
    
  - <span data-ttu-id="38c78-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="38c78-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="38c78-143">Февраль февраля МАарт апреля Меи июня 2004 Янв, Сен сентября, Окт ноября декабря</span><span class="sxs-lookup"><span data-stu-id="38c78-143">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="38c78-144">French</span><span class="sxs-lookup"><span data-stu-id="38c78-144">French</span></span>
    
  - <span data-ttu-id="38c78-145">жанвиер, фéвриер, Mars, Аврил, Чиангмай, жуин жуиллет, аоûт, септембре, октобре, Новембре, дéцембре</span><span class="sxs-lookup"><span data-stu-id="38c78-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="38c78-146">жанв.</span><span class="sxs-lookup"><span data-stu-id="38c78-146">janv.</span></span> <span data-ttu-id="38c78-147">фéвр.</span><span class="sxs-lookup"><span data-stu-id="38c78-147">févr.</span></span> <span data-ttu-id="38c78-148">режим MARS Аврил Чиангмай жуин жуил.</span><span class="sxs-lookup"><span data-stu-id="38c78-148">mars avril mai juin juil.</span></span> <span data-ttu-id="38c78-149">аоûт сентября.</span><span class="sxs-lookup"><span data-stu-id="38c78-149">août sept.</span></span> <span data-ttu-id="38c78-150">развертывания.</span><span class="sxs-lookup"><span data-stu-id="38c78-150">oct.</span></span> <span data-ttu-id="38c78-151">ноября.</span><span class="sxs-lookup"><span data-stu-id="38c78-151">nov.</span></span> <span data-ttu-id="38c78-152">дéк.</span><span class="sxs-lookup"><span data-stu-id="38c78-152">déc.</span></span>
    
- <span data-ttu-id="38c78-153">German</span><span class="sxs-lookup"><span data-stu-id="38c78-153">German</span></span>
    
  - <span data-ttu-id="38c78-154">жäнуар, фебруар, мäрз, Апрель, Чиангмай, жуни Жули, Август, Сентябрь, Октобер, Ноябрь, дезембер</span><span class="sxs-lookup"><span data-stu-id="38c78-154">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="38c78-155">Янв./Жäн.</span><span class="sxs-lookup"><span data-stu-id="38c78-155">Jan./Jän.</span></span> <span data-ttu-id="38c78-156">Фев. Мäрз Apr. Чиангмай Жуни Жули Авг. Сентябрь. Окт.</span><span class="sxs-lookup"><span data-stu-id="38c78-156">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="38c78-157">Ноя. дез.</span><span class="sxs-lookup"><span data-stu-id="38c78-157">Nov. Dez.</span></span>
    
- <span data-ttu-id="38c78-158">Italian</span><span class="sxs-lookup"><span data-stu-id="38c78-158">Italian</span></span>
    
  - <span data-ttu-id="38c78-159">женнаио, феббраио, Марзо, Апрель, маггио, гиугно, луглио, Агосто, Сеттембре, Оттобре, Новембре, дицембре</span><span class="sxs-lookup"><span data-stu-id="38c78-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="38c78-160">Женн.</span><span class="sxs-lookup"><span data-stu-id="38c78-160">genn.</span></span> <span data-ttu-id="38c78-161">феббр.</span><span class="sxs-lookup"><span data-stu-id="38c78-161">febbr.</span></span> <span data-ttu-id="38c78-162">Мар.</span><span class="sxs-lookup"><span data-stu-id="38c78-162">mar.</span></span> <span data-ttu-id="38c78-163">Апрель.</span><span class="sxs-lookup"><span data-stu-id="38c78-163">apr.</span></span> <span data-ttu-id="38c78-164">Магг.</span><span class="sxs-lookup"><span data-stu-id="38c78-164">magg.</span></span> <span data-ttu-id="38c78-165">гиугно луглио AG.</span><span class="sxs-lookup"><span data-stu-id="38c78-165">giugno luglio ag.</span></span> <span data-ttu-id="38c78-166">Переключател.</span><span class="sxs-lookup"><span data-stu-id="38c78-166">sett.</span></span> <span data-ttu-id="38c78-167">and.</span><span class="sxs-lookup"><span data-stu-id="38c78-167">ott.</span></span> <span data-ttu-id="38c78-168">ноября.</span><span class="sxs-lookup"><span data-stu-id="38c78-168">nov.</span></span> <span data-ttu-id="38c78-169">DIC.</span><span class="sxs-lookup"><span data-stu-id="38c78-169">dic.</span></span>
    
- <span data-ttu-id="38c78-170">Португальский</span><span class="sxs-lookup"><span data-stu-id="38c78-170">Portuguese</span></span>
    
  - <span data-ttu-id="38c78-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="38c78-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="38c78-172">Янв Фев Mar, Чиангмай, 2004 июня, назад, Настройка ноября Ноя дез</span><span class="sxs-lookup"><span data-stu-id="38c78-172">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="38c78-173">Spanish</span><span class="sxs-lookup"><span data-stu-id="38c78-173">Spanish</span></span>
    
  - <span data-ttu-id="38c78-174">енеро, фебреро, Марзо, Абрил, Майо, Жунио, Жулио, Агосто, септиембре, Октубре, новиембре, диЦиембре</span><span class="sxs-lookup"><span data-stu-id="38c78-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="38c78-175">енеро Фев.</span><span class="sxs-lookup"><span data-stu-id="38c78-175">enero feb.</span></span> <span data-ttu-id="38c78-176">Марзо Граничный маршрутизатор.</span><span class="sxs-lookup"><span data-stu-id="38c78-176">marzo abr.</span></span> <span data-ttu-id="38c78-177">Майо июня.</span><span class="sxs-lookup"><span data-stu-id="38c78-177">mayo jun.</span></span> <span data-ttu-id="38c78-178">июля.</span><span class="sxs-lookup"><span data-stu-id="38c78-178">jul.</span></span> <span data-ttu-id="38c78-179">Агосто сентября./Сет.</span><span class="sxs-lookup"><span data-stu-id="38c78-179">agosto sept./set.</span></span> <span data-ttu-id="38c78-180">развертывания.</span><span class="sxs-lookup"><span data-stu-id="38c78-180">oct.</span></span> <span data-ttu-id="38c78-181">ноября.</span><span class="sxs-lookup"><span data-stu-id="38c78-181">nov.</span></span> <span data-ttu-id="38c78-182">DIC.</span><span class="sxs-lookup"><span data-stu-id="38c78-182">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="38c78-183">Func_eu_date1 (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="38c78-183">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="38c78-184">Эта функция является устаревшей, так как она поддерживает только названия месяцев на португальском языке, которые теперь включены в `Func_eu_date` функцию, описанную выше.</span><span class="sxs-lookup"><span data-stu-id="38c78-184">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="38c78-185">Эта функция служит для поиска даты в формате, принятом в португальском языке.</span><span class="sxs-lookup"><span data-stu-id="38c78-185">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="38c78-186">Формат этой функции такой же `Func_eu_date` , как и в используемом языке.</span><span class="sxs-lookup"><span data-stu-id="38c78-186">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="38c78-187">Примеры:</span><span class="sxs-lookup"><span data-stu-id="38c78-187">Examples:</span></span>
  
- <span data-ttu-id="38c78-188">2 дез 2016</span><span class="sxs-lookup"><span data-stu-id="38c78-188">2 Dez 2016</span></span>
    
- <span data-ttu-id="38c78-189">02 дез 2016</span><span class="sxs-lookup"><span data-stu-id="38c78-189">02 dez 2016</span></span>
    
- <span data-ttu-id="38c78-190">2 дез 16</span><span class="sxs-lookup"><span data-stu-id="38c78-190">2 Dez 16</span></span>
    
- <span data-ttu-id="38c78-191">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="38c78-191">2/12/2016</span></span>
    
- <span data-ttu-id="38c78-192">02/12/16</span><span class="sxs-lookup"><span data-stu-id="38c78-192">02/12/16</span></span>
    
- <span data-ttu-id="38c78-193">2 — дез — 2016</span><span class="sxs-lookup"><span data-stu-id="38c78-193">2-Dez-2016</span></span>
    
- <span data-ttu-id="38c78-194">2-12-16</span><span class="sxs-lookup"><span data-stu-id="38c78-194">2-12-16</span></span>
    
<span data-ttu-id="38c78-195">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="38c78-195">Accepted month names:</span></span>
  
- <span data-ttu-id="38c78-196">Португальский</span><span class="sxs-lookup"><span data-stu-id="38c78-196">Portuguese</span></span>
    
  - <span data-ttu-id="38c78-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="38c78-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="38c78-198">Янв Фев Mar, Чиангмай, 2004 июня, назад, Настройка ноября Ноя дез</span><span class="sxs-lookup"><span data-stu-id="38c78-198">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="38c78-199">Func_eu_date2 (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="38c78-199">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="38c78-200">Эта функция является устаревшей, так как она поддерживает только названия в голландских месяцах, которые теперь включены в `Func_eu_date` функцию, описанную выше.</span><span class="sxs-lookup"><span data-stu-id="38c78-200">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="38c78-201">Эта функция служит для поиска даты в формате, принятом в нидерландском языке.</span><span class="sxs-lookup"><span data-stu-id="38c78-201">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="38c78-202">Формат этой функции такой же `Func_eu_date` , как и в используемом языке.</span><span class="sxs-lookup"><span data-stu-id="38c78-202">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="38c78-203">Примеры:</span><span class="sxs-lookup"><span data-stu-id="38c78-203">Examples:</span></span>
  
- <span data-ttu-id="38c78-204">2 Меи 2016</span><span class="sxs-lookup"><span data-stu-id="38c78-204">2 Mei 2016</span></span>
    
- <span data-ttu-id="38c78-205">02 Меи 2016</span><span class="sxs-lookup"><span data-stu-id="38c78-205">02 mei 2016</span></span>
    
- <span data-ttu-id="38c78-206">2 Меи 16</span><span class="sxs-lookup"><span data-stu-id="38c78-206">2 Mei 16</span></span>
    
- <span data-ttu-id="38c78-207">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="38c78-207">2/12/2016</span></span>
    
- <span data-ttu-id="38c78-208">02/12/16</span><span class="sxs-lookup"><span data-stu-id="38c78-208">02/12/16</span></span>
    
- <span data-ttu-id="38c78-209">2 — Меи — 2016</span><span class="sxs-lookup"><span data-stu-id="38c78-209">2-Mei-2016</span></span>
    
- <span data-ttu-id="38c78-210">2-12-16</span><span class="sxs-lookup"><span data-stu-id="38c78-210">2-12-16</span></span>
    
<span data-ttu-id="38c78-211">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="38c78-211">Accepted month names:</span></span>
  
- <span data-ttu-id="38c78-212">Dutch</span><span class="sxs-lookup"><span data-stu-id="38c78-212">Dutch</span></span>
    
  - <span data-ttu-id="38c78-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="38c78-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="38c78-214">Фев, фев, МАарт апреля Меи июня 2004 Янв, Сен сентября Окт ноября декабря</span><span class="sxs-lookup"><span data-stu-id="38c78-214">jan feb maart apr mei jun jul aug sep sept out okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="38c78-215">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="38c78-215">Func_expiration_date</span></span>

<span data-ttu-id="38c78-216">Эта функция служит для поиска даты в формате, обычно используемом для кредитных и дебетовых карт, где указывается месяц, а дни исключаются.</span><span class="sxs-lookup"><span data-stu-id="38c78-216">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="38c78-217">Эта функция будет сопоставлять даты в формате "месяц/год", "month-Year", "[название месяца] год" и "[аббревиатура] год".</span><span class="sxs-lookup"><span data-stu-id="38c78-217">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="38c78-218">Полные или сокращенные названия месяцев вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="38c78-218">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="38c78-219">Примеры:</span><span class="sxs-lookup"><span data-stu-id="38c78-219">Examples:</span></span>
  
- <span data-ttu-id="38c78-220">ММ/ГГ (например, 01/11 или 1/11);</span><span class="sxs-lookup"><span data-stu-id="38c78-220">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="38c78-221">ММ/ГГГГ (например, 01/2011 или 1/2011);</span><span class="sxs-lookup"><span data-stu-id="38c78-221">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="38c78-222">ММ-ГГ (например, 01-22 или 1-11);</span><span class="sxs-lookup"><span data-stu-id="38c78-222">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="38c78-223">ММ-ГГГГ (например, 01-2000 или 1-2000).</span><span class="sxs-lookup"><span data-stu-id="38c78-223">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="38c78-224">Следующие форматы поддерживают ГГ или ГГГГ:</span><span class="sxs-lookup"><span data-stu-id="38c78-224">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="38c78-225">Month – гггг — например, Янв – 2010 или Январь – 2010 или Янв 10 или Январь – 10.</span><span class="sxs-lookup"><span data-stu-id="38c78-225">Month-YYYY -- for example Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="38c78-226">Месяц ГГГГ (например, "январь 2010", "янв 2010", "январь 10" или "янв 10");</span><span class="sxs-lookup"><span data-stu-id="38c78-226">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="38c78-227">МесяцГГГГ (например, "январь2010", "янв2010", "январь10" или "янв10");</span><span class="sxs-lookup"><span data-stu-id="38c78-227">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="38c78-228">Month/гггг, например, "Январь/2010" или "Янв/2010" или "Январь/10" или "Янв/10"</span><span class="sxs-lookup"><span data-stu-id="38c78-228">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="38c78-229">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="38c78-229">Accepted month names:</span></span>
  
- <span data-ttu-id="38c78-230">English</span><span class="sxs-lookup"><span data-stu-id="38c78-230">English</span></span>
    
  - <span data-ttu-id="38c78-231">Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь</span><span class="sxs-lookup"><span data-stu-id="38c78-231">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="38c78-232">Февраль февраля Mar апреля, Май, Сентябрь октября октября, Май</span><span class="sxs-lookup"><span data-stu-id="38c78-232">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="38c78-233">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="38c78-233">Func_us_address</span></span>

<span data-ttu-id="38c78-234">Эта функция ищет имя штата США или аббревиатуру, за которым следует допустимый почтовый индекс, аналогично тому, как они используются в почтовых адресах.</span><span class="sxs-lookup"><span data-stu-id="38c78-234">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they're used in postal addresses.</span></span> <span data-ttu-id="38c78-235">Необходимо указать правильный почтовый индекс, соответствующий названию штата США или его аббревиатуре.</span><span class="sxs-lookup"><span data-stu-id="38c78-235">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="38c78-236">Название штата США и почтовый индекс не должны разделяться знаками пунктуации или буквами.</span><span class="sxs-lookup"><span data-stu-id="38c78-236">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="38c78-237">Примеры:</span><span class="sxs-lookup"><span data-stu-id="38c78-237">Examples:</span></span>
  
- <span data-ttu-id="38c78-238">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="38c78-238">Washington 98052</span></span>
    
- <span data-ttu-id="38c78-239">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="38c78-239">Washington 98052-9998</span></span>
    
- <span data-ttu-id="38c78-240">WA 98052</span><span class="sxs-lookup"><span data-stu-id="38c78-240">WA 98052</span></span>
    
- <span data-ttu-id="38c78-241">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="38c78-241">WA 98052-9998</span></span>
    

