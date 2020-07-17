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
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="fbd54-103">Сведения, для обнаружения которых используются функции защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="fbd54-103">What the DLP functions look for</span></span>

<span data-ttu-id="fbd54-p101">Защита от потери данных включает различные типы конфиденциальной информации, такие как номер кредитной карты, номер дебетовой карты, выпущенной в ЕС, которые предусмотрены политиками защиты от потери данных. Обычно эти типы конфиденциальной информации используются для поиска данных по определенному шаблону, при этом проводится проверка правильности форматирования, применения контрольных сумм, а также наличия соответствующих ключевых слов и других данных. Для некоторых из этих проверок используются внешние функции. Например, чтобы определить, что число является номером кредитной карты, проводится поиск дат, формат которых соответствует формату даты окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="fbd54-p101">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="fbd54-108">В этой статье рассказывается о сведениях, для обнаружения которых используются эти функции, что поможет вам разобраться в предопределенных типах конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="fbd54-108">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="fbd54-109">Более подробную информацию можно узнать в статье [Определение объекта типа конфиденциальной информации](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="fbd54-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="fbd54-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="fbd54-110">Func_us_date</span></span>

<span data-ttu-id="fbd54-111">Эта функция ищет дату в формате, обычно используемом в США. К ним относятся форматы "месяц/день/год", "месяц-день-год" и "месяц суток год".</span><span class="sxs-lookup"><span data-stu-id="fbd54-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="fbd54-112">Полные или сокращенные названия месяцев вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="fbd54-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="fbd54-113">Примеры:</span><span class="sxs-lookup"><span data-stu-id="fbd54-113">Examples:</span></span>
  
- <span data-ttu-id="fbd54-114">2 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="fbd54-114">December 2, 2016</span></span>
    
- <span data-ttu-id="fbd54-115">2 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="fbd54-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="fbd54-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-116">dec 02 2016</span></span>
    
- <span data-ttu-id="fbd54-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-117">12/2/2016</span></span>
    
- <span data-ttu-id="fbd54-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="fbd54-118">12/02/16</span></span>
    
- <span data-ttu-id="fbd54-119">Dec – 2-2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="fbd54-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="fbd54-120">12-2-16</span></span>
    
<span data-ttu-id="fbd54-121">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="fbd54-121">Accepted month names:</span></span>
  
- <span data-ttu-id="fbd54-122">English</span><span class="sxs-lookup"><span data-stu-id="fbd54-122">English</span></span>
    
  - <span data-ttu-id="fbd54-123">Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь</span><span class="sxs-lookup"><span data-stu-id="fbd54-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="fbd54-124">Февраль. Фев. Март. Апр. Май июня. сентября. Oct. Ноя. Дек.</span><span class="sxs-lookup"><span data-stu-id="fbd54-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="fbd54-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="fbd54-125">Func_eu_date</span></span>

<span data-ttu-id="fbd54-p104">Эта функция служит для поиска даты в формате, который обычно используется в ЕС, а также в большинстве стран за пределами США. Сюда относятся форматы "день/месяц/год", "день-месяц-год" и "день месяц год". Полные или сокращенные названия месяцев вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="fbd54-p104">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="fbd54-130">Примеры:</span><span class="sxs-lookup"><span data-stu-id="fbd54-130">Examples:</span></span>
  
- <span data-ttu-id="fbd54-131">2 декабря 2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-131">2 Dec 2016</span></span>
    
- <span data-ttu-id="fbd54-132">02 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="fbd54-132">02 dec 2016</span></span>
    
- <span data-ttu-id="fbd54-133">2 декабря, 16 декабря</span><span class="sxs-lookup"><span data-stu-id="fbd54-133">2 Dec 16</span></span>
    
- <span data-ttu-id="fbd54-134">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-134">2/12/2016</span></span>
    
- <span data-ttu-id="fbd54-135">02/12/16</span><span class="sxs-lookup"><span data-stu-id="fbd54-135">02/12/16</span></span>
    
- <span data-ttu-id="fbd54-136">2 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="fbd54-136">2-Dec-2016</span></span>
    
- <span data-ttu-id="fbd54-137">2-12-16</span><span class="sxs-lookup"><span data-stu-id="fbd54-137">2-12-16</span></span>
    
<span data-ttu-id="fbd54-138">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="fbd54-138">Accepted month names:</span></span>
  
- <span data-ttu-id="fbd54-139">English</span><span class="sxs-lookup"><span data-stu-id="fbd54-139">English</span></span>
    
  - <span data-ttu-id="fbd54-140">Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь</span><span class="sxs-lookup"><span data-stu-id="fbd54-140">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="fbd54-141">Февраль. Фев. Март. Апр. Май июня. сентября. Oct. Ноя. Дек.</span><span class="sxs-lookup"><span data-stu-id="fbd54-141">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="fbd54-142">Dutch</span><span class="sxs-lookup"><span data-stu-id="fbd54-142">Dutch</span></span>
    
  - <span data-ttu-id="fbd54-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="fbd54-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="fbd54-144">Февраль февраля МАарт апреля Меи июня 2004 Янв, Сен сентября, Окт ноября декабря</span><span class="sxs-lookup"><span data-stu-id="fbd54-144">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="fbd54-145">French</span><span class="sxs-lookup"><span data-stu-id="fbd54-145">French</span></span>
    
  - <span data-ttu-id="fbd54-146">жанвиер, фéвриер, Mars, Аврил, Чиангмай, жуин жуиллет, аоûт, септембре, октобре, Новембре, дéцембре</span><span class="sxs-lookup"><span data-stu-id="fbd54-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="fbd54-147">жанв.</span><span class="sxs-lookup"><span data-stu-id="fbd54-147">janv.</span></span> <span data-ttu-id="fbd54-148">фéвр.</span><span class="sxs-lookup"><span data-stu-id="fbd54-148">févr.</span></span> <span data-ttu-id="fbd54-149">режим MARS Аврил Чиангмай жуин жуил.</span><span class="sxs-lookup"><span data-stu-id="fbd54-149">mars avril mai juin juil.</span></span> <span data-ttu-id="fbd54-150">аоûт сентября.</span><span class="sxs-lookup"><span data-stu-id="fbd54-150">août sept.</span></span> <span data-ttu-id="fbd54-151">развертывания.</span><span class="sxs-lookup"><span data-stu-id="fbd54-151">oct.</span></span> <span data-ttu-id="fbd54-152">ноября.</span><span class="sxs-lookup"><span data-stu-id="fbd54-152">nov.</span></span> <span data-ttu-id="fbd54-153">дéк.</span><span class="sxs-lookup"><span data-stu-id="fbd54-153">déc.</span></span>
    
- <span data-ttu-id="fbd54-154">German</span><span class="sxs-lookup"><span data-stu-id="fbd54-154">German</span></span>
    
  - <span data-ttu-id="fbd54-155">жäнуар, фебруар, мäрз, Апрель, Чиангмай, жуни Жули, Август, Сентябрь, Октобер, Ноябрь, дезембер</span><span class="sxs-lookup"><span data-stu-id="fbd54-155">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="fbd54-156">Янв./Жäн.</span><span class="sxs-lookup"><span data-stu-id="fbd54-156">Jan./Jän.</span></span> <span data-ttu-id="fbd54-157">Фев. Мäрз Apr. Чиангмай Жуни Жули Авг. Сентябрь. Окт.</span><span class="sxs-lookup"><span data-stu-id="fbd54-157">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="fbd54-158">Ноя. дез.</span><span class="sxs-lookup"><span data-stu-id="fbd54-158">Nov. Dez.</span></span>
    
- <span data-ttu-id="fbd54-159">Italian</span><span class="sxs-lookup"><span data-stu-id="fbd54-159">Italian</span></span>
    
  - <span data-ttu-id="fbd54-160">женнаио, феббраио, Марзо, Апрель, маггио, гиугно, луглио, Агосто, Сеттембре, Оттобре, Новембре, дицембре</span><span class="sxs-lookup"><span data-stu-id="fbd54-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="fbd54-161">Женн.</span><span class="sxs-lookup"><span data-stu-id="fbd54-161">genn.</span></span> <span data-ttu-id="fbd54-162">феббр.</span><span class="sxs-lookup"><span data-stu-id="fbd54-162">febbr.</span></span> <span data-ttu-id="fbd54-163">Мар.</span><span class="sxs-lookup"><span data-stu-id="fbd54-163">mar.</span></span> <span data-ttu-id="fbd54-164">Апрель.</span><span class="sxs-lookup"><span data-stu-id="fbd54-164">apr.</span></span> <span data-ttu-id="fbd54-165">Магг.</span><span class="sxs-lookup"><span data-stu-id="fbd54-165">magg.</span></span> <span data-ttu-id="fbd54-166">гиугно луглио AG.</span><span class="sxs-lookup"><span data-stu-id="fbd54-166">giugno luglio ag.</span></span> <span data-ttu-id="fbd54-167">Переключател.</span><span class="sxs-lookup"><span data-stu-id="fbd54-167">sett.</span></span> <span data-ttu-id="fbd54-168">and.</span><span class="sxs-lookup"><span data-stu-id="fbd54-168">ott.</span></span> <span data-ttu-id="fbd54-169">ноября.</span><span class="sxs-lookup"><span data-stu-id="fbd54-169">nov.</span></span> <span data-ttu-id="fbd54-170">DIC.</span><span class="sxs-lookup"><span data-stu-id="fbd54-170">dic.</span></span>
    
- <span data-ttu-id="fbd54-171">Португальский</span><span class="sxs-lookup"><span data-stu-id="fbd54-171">Portuguese</span></span>
    
  - <span data-ttu-id="fbd54-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="fbd54-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="fbd54-173">Янв Фев Mar, Чиангмай, 2004 июня, назад, Настройка ноября Ноя дез</span><span class="sxs-lookup"><span data-stu-id="fbd54-173">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="fbd54-174">Spanish</span><span class="sxs-lookup"><span data-stu-id="fbd54-174">Spanish</span></span>
    
  - <span data-ttu-id="fbd54-175">енеро, фебреро, Марзо, Абрил, Майо, Жунио, Жулио, Агосто, септиембре, Октубре, новиембре, диЦиембре</span><span class="sxs-lookup"><span data-stu-id="fbd54-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="fbd54-176">енеро Фев.</span><span class="sxs-lookup"><span data-stu-id="fbd54-176">enero feb.</span></span> <span data-ttu-id="fbd54-177">Марзо Граничный маршрутизатор.</span><span class="sxs-lookup"><span data-stu-id="fbd54-177">marzo abr.</span></span> <span data-ttu-id="fbd54-178">Майо июня.</span><span class="sxs-lookup"><span data-stu-id="fbd54-178">mayo jun.</span></span> <span data-ttu-id="fbd54-179">июля.</span><span class="sxs-lookup"><span data-stu-id="fbd54-179">jul.</span></span> <span data-ttu-id="fbd54-180">Агосто сентября./Сет.</span><span class="sxs-lookup"><span data-stu-id="fbd54-180">agosto sept./set.</span></span> <span data-ttu-id="fbd54-181">развертывания.</span><span class="sxs-lookup"><span data-stu-id="fbd54-181">oct.</span></span> <span data-ttu-id="fbd54-182">ноября.</span><span class="sxs-lookup"><span data-stu-id="fbd54-182">nov.</span></span> <span data-ttu-id="fbd54-183">DIC.</span><span class="sxs-lookup"><span data-stu-id="fbd54-183">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="fbd54-184">Func_eu_date1 (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="fbd54-184">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="fbd54-185">Эта функция является устаревшей, так как она поддерживает только названия месяцев на португальском языке, которые теперь включены в `Func_eu_date` функцию, описанную выше.</span><span class="sxs-lookup"><span data-stu-id="fbd54-185">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="fbd54-186">Эта функция служит для поиска даты в формате, принятом в португальском языке.</span><span class="sxs-lookup"><span data-stu-id="fbd54-186">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="fbd54-187">Формат этой функции такой же `Func_eu_date` , как и в используемом языке.</span><span class="sxs-lookup"><span data-stu-id="fbd54-187">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="fbd54-188">Примеры:</span><span class="sxs-lookup"><span data-stu-id="fbd54-188">Examples:</span></span>
  
- <span data-ttu-id="fbd54-189">2 дез 2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-189">2 Dez 2016</span></span>
    
- <span data-ttu-id="fbd54-190">02 дез 2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-190">02 dez 2016</span></span>
    
- <span data-ttu-id="fbd54-191">2 дез 16</span><span class="sxs-lookup"><span data-stu-id="fbd54-191">2 Dez 16</span></span>
    
- <span data-ttu-id="fbd54-192">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-192">2/12/2016</span></span>
    
- <span data-ttu-id="fbd54-193">02/12/16</span><span class="sxs-lookup"><span data-stu-id="fbd54-193">02/12/16</span></span>
    
- <span data-ttu-id="fbd54-194">2 — дез — 2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-194">2-Dez-2016</span></span>
    
- <span data-ttu-id="fbd54-195">2-12-16</span><span class="sxs-lookup"><span data-stu-id="fbd54-195">2-12-16</span></span>
    
<span data-ttu-id="fbd54-196">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="fbd54-196">Accepted month names:</span></span>
  
- <span data-ttu-id="fbd54-197">Португальский</span><span class="sxs-lookup"><span data-stu-id="fbd54-197">Portuguese</span></span>
    
  - <span data-ttu-id="fbd54-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="fbd54-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="fbd54-199">Янв Фев Mar, Чиангмай, 2004 июня, назад, Настройка ноября Ноя дез</span><span class="sxs-lookup"><span data-stu-id="fbd54-199">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="fbd54-200">Func_eu_date2 (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="fbd54-200">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="fbd54-201">Эта функция является устаревшей, так как она поддерживает только названия в голландских месяцах, которые теперь включены в `Func_eu_date` функцию, описанную выше.</span><span class="sxs-lookup"><span data-stu-id="fbd54-201">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="fbd54-202">Эта функция служит для поиска даты в формате, принятом в нидерландском языке.</span><span class="sxs-lookup"><span data-stu-id="fbd54-202">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="fbd54-203">Формат этой функции такой же `Func_eu_date` , как и в используемом языке.</span><span class="sxs-lookup"><span data-stu-id="fbd54-203">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="fbd54-204">Примеры:</span><span class="sxs-lookup"><span data-stu-id="fbd54-204">Examples:</span></span>
  
- <span data-ttu-id="fbd54-205">2 Меи 2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-205">2 Mei 2016</span></span>
    
- <span data-ttu-id="fbd54-206">02 Меи 2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-206">02 mei 2016</span></span>
    
- <span data-ttu-id="fbd54-207">2 Меи 16</span><span class="sxs-lookup"><span data-stu-id="fbd54-207">2 Mei 16</span></span>
    
- <span data-ttu-id="fbd54-208">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-208">2/12/2016</span></span>
    
- <span data-ttu-id="fbd54-209">02/12/16</span><span class="sxs-lookup"><span data-stu-id="fbd54-209">02/12/16</span></span>
    
- <span data-ttu-id="fbd54-210">2 — Меи — 2016</span><span class="sxs-lookup"><span data-stu-id="fbd54-210">2-Mei-2016</span></span>
    
- <span data-ttu-id="fbd54-211">2-12-16</span><span class="sxs-lookup"><span data-stu-id="fbd54-211">2-12-16</span></span>
    
<span data-ttu-id="fbd54-212">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="fbd54-212">Accepted month names:</span></span>
  
- <span data-ttu-id="fbd54-213">Dutch</span><span class="sxs-lookup"><span data-stu-id="fbd54-213">Dutch</span></span>
    
  - <span data-ttu-id="fbd54-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="fbd54-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="fbd54-215">Февраль февраля МАарт апреля Меи июня 2004 Янв, Сен сентября, Окт ноября декабря</span><span class="sxs-lookup"><span data-stu-id="fbd54-215">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="fbd54-216">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="fbd54-216">Func_expiration_date</span></span>

<span data-ttu-id="fbd54-217">Эта функция служит для поиска даты в формате, обычно используемом для кредитных и дебетовых карт, где указывается месяц, а дни исключаются.</span><span class="sxs-lookup"><span data-stu-id="fbd54-217">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="fbd54-218">Эта функция будет сопоставлять даты в формате "месяц/год", "month-Year", "[название месяца] год" и "[аббревиатура] год".</span><span class="sxs-lookup"><span data-stu-id="fbd54-218">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="fbd54-219">Полные или сокращенные названия месяцев вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="fbd54-219">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="fbd54-220">Примеры:</span><span class="sxs-lookup"><span data-stu-id="fbd54-220">Examples:</span></span>
  
- <span data-ttu-id="fbd54-221">ММ/ГГ (например, 01/11 или 1/11);</span><span class="sxs-lookup"><span data-stu-id="fbd54-221">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="fbd54-222">ММ/ГГГГ (например, 01/2011 или 1/2011);</span><span class="sxs-lookup"><span data-stu-id="fbd54-222">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="fbd54-223">ММ-ГГ (например, 01-22 или 1-11);</span><span class="sxs-lookup"><span data-stu-id="fbd54-223">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="fbd54-224">ММ-ГГГГ (например, 01-2000 или 1-2000).</span><span class="sxs-lookup"><span data-stu-id="fbd54-224">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="fbd54-225">Следующие форматы поддерживают ГГ или ГГГГ:</span><span class="sxs-lookup"><span data-stu-id="fbd54-225">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="fbd54-226">Месяц-ГГГГ (например, янв-2010, январь-2010, янв-10 или январь-10);</span><span class="sxs-lookup"><span data-stu-id="fbd54-226">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="fbd54-227">Месяц ГГГГ (например, "январь 2010", "янв 2010", "январь 10" или "янв 10");</span><span class="sxs-lookup"><span data-stu-id="fbd54-227">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="fbd54-228">МесяцГГГГ (например, "январь2010", "янв2010", "январь10" или "янв10");</span><span class="sxs-lookup"><span data-stu-id="fbd54-228">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="fbd54-229">Month/гггг, например, "Январь/2010" или "Янв/2010" или "Январь/10" или "Янв/10"</span><span class="sxs-lookup"><span data-stu-id="fbd54-229">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="fbd54-230">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="fbd54-230">Accepted month names:</span></span>
  
- <span data-ttu-id="fbd54-231">English</span><span class="sxs-lookup"><span data-stu-id="fbd54-231">English</span></span>
    
  - <span data-ttu-id="fbd54-232">Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь</span><span class="sxs-lookup"><span data-stu-id="fbd54-232">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="fbd54-233">Февраль февраля Mar апреля, Май, Сентябрь октября октября, Май</span><span class="sxs-lookup"><span data-stu-id="fbd54-233">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="fbd54-234">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="fbd54-234">Func_us_address</span></span>

<span data-ttu-id="fbd54-p112">Эта функция служит для поиска названия штата США или его почтовой аббревиатуры вместе с почтовым индексом в том же виде, в котором они указываются в почтовых адресах. Необходимо указать правильный почтовый индекс, соответствующий названию штата США или его аббревиатуре. Название штата США и почтовый индекс не должны разделяться знаками пунктуации или буквами.</span><span class="sxs-lookup"><span data-stu-id="fbd54-p112">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="fbd54-238">Примеры:</span><span class="sxs-lookup"><span data-stu-id="fbd54-238">Examples:</span></span>
  
- <span data-ttu-id="fbd54-239">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="fbd54-239">Washington 98052</span></span>
    
- <span data-ttu-id="fbd54-240">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="fbd54-240">Washington 98052-9998</span></span>
    
- <span data-ttu-id="fbd54-241">WA 98052</span><span class="sxs-lookup"><span data-stu-id="fbd54-241">WA 98052</span></span>
    
- <span data-ttu-id="fbd54-242">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="fbd54-242">WA 98052-9998</span></span>
    

