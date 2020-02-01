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
description: Типы конфиденциальной информации ищут определенный шаблон и корроборате его, обеспечивая правильное форматирование, заменяя контрольные суммы и ищут соответствующие ключевые слова или другие сведения. Для некоторых из этих проверок используются внешние функции. В этой статье рассказывается о сведениях, для обнаружения которых используются эти функции, что поможет вам разобраться в предопределенных типах конфиденциальной информации.
ms.openlocfilehash: 86ce1c9d546f776e239fdaca76219129c24a73e8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601206"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="e35c9-105">Сведения, для обнаружения которых используются функции защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="e35c9-105">What the DLP functions look for</span></span>

<span data-ttu-id="e35c9-p102">Защита от потери данных включает различные типы конфиденциальной информации, такие как номер кредитной карты, номер дебетовой карты, выпущенной в ЕС, которые предусмотрены политиками защиты от потери данных. Обычно эти типы конфиденциальной информации используются для поиска данных по определенному шаблону, при этом проводится проверка правильности форматирования, применения контрольных сумм, а также наличия соответствующих ключевых слов и других данных. Для некоторых из этих проверок используются внешние функции. Например, чтобы определить, что число является номером кредитной карты, проводится поиск дат, формат которых соответствует формату даты окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="e35c9-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="e35c9-110">В этой статье рассказывается о сведениях, для обнаружения которых используются эти функции, что поможет вам разобраться в предопределенных типах конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="e35c9-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="e35c9-111">Дополнительные сведения см. в статье [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="e35c9-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="e35c9-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="e35c9-112">Func_us_date</span></span>

<span data-ttu-id="e35c9-113">Эта функция ищет дату в формате, обычно используемом в США. К ним относятся форматы "месяц/день/год", "месяц-день-год" и "месяц суток год".</span><span class="sxs-lookup"><span data-stu-id="e35c9-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="e35c9-114">Полные или сокращенные названия месяцев вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="e35c9-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="e35c9-115">Примеры:</span><span class="sxs-lookup"><span data-stu-id="e35c9-115">Examples:</span></span>
  
- <span data-ttu-id="e35c9-116">2 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="e35c9-116">December 2, 2016</span></span>
    
- <span data-ttu-id="e35c9-117">2 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="e35c9-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="e35c9-118">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-118">dec 02 2016</span></span>
    
- <span data-ttu-id="e35c9-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-119">12/2/2016</span></span>
    
- <span data-ttu-id="e35c9-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="e35c9-120">12/02/16</span></span>
    
- <span data-ttu-id="e35c9-121">Dec – 2-2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="e35c9-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="e35c9-122">12-2-16</span></span>
    
<span data-ttu-id="e35c9-123">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="e35c9-123">Accepted month names:</span></span>
  
- <span data-ttu-id="e35c9-124">английский;</span><span class="sxs-lookup"><span data-stu-id="e35c9-124">English</span></span>
    
  - <span data-ttu-id="e35c9-125">Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь</span><span class="sxs-lookup"><span data-stu-id="e35c9-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e35c9-126">Февраль. Фев. Март. Апр. Май июня. сентября. Oct. Ноя. Дек.</span><span class="sxs-lookup"><span data-stu-id="e35c9-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="e35c9-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="e35c9-127">Func_eu_date</span></span>

<span data-ttu-id="e35c9-p105">Эта функция служит для поиска даты в формате, который обычно используется в ЕС, а также в большинстве стран за пределами США. Сюда относятся форматы "день/месяц/год", "день-месяц-год" и "день месяц год". Полные или сокращенные названия месяцев вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="e35c9-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="e35c9-132">Примеры:</span><span class="sxs-lookup"><span data-stu-id="e35c9-132">Examples:</span></span>
  
- <span data-ttu-id="e35c9-133">2 декабря 2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="e35c9-134">02 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="e35c9-134">02 dec 2016</span></span>
    
- <span data-ttu-id="e35c9-135">2 декабря, 16 декабря</span><span class="sxs-lookup"><span data-stu-id="e35c9-135">2 Dec 16</span></span>
    
- <span data-ttu-id="e35c9-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-136">2/12/2016</span></span>
    
- <span data-ttu-id="e35c9-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e35c9-137">02/12/16</span></span>
    
- <span data-ttu-id="e35c9-138">2 декабря 2016 г.</span><span class="sxs-lookup"><span data-stu-id="e35c9-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="e35c9-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e35c9-139">2-12-16</span></span>
    
<span data-ttu-id="e35c9-140">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="e35c9-140">Accepted month names:</span></span>
  
- <span data-ttu-id="e35c9-141">английский;</span><span class="sxs-lookup"><span data-stu-id="e35c9-141">English</span></span>
    
  - <span data-ttu-id="e35c9-142">Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь</span><span class="sxs-lookup"><span data-stu-id="e35c9-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e35c9-143">Февраль. Фев. Март. Апр. Май июня. сентября. Oct. Ноя. Дек.</span><span class="sxs-lookup"><span data-stu-id="e35c9-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="e35c9-144">голландский;</span><span class="sxs-lookup"><span data-stu-id="e35c9-144">Dutch</span></span>
    
  - <span data-ttu-id="e35c9-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="e35c9-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="e35c9-146">Февраль февраля МАарт апреля Меи июня 2004 Янв, Сен сентября, Окт ноября декабря</span><span class="sxs-lookup"><span data-stu-id="e35c9-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="e35c9-147">французский;</span><span class="sxs-lookup"><span data-stu-id="e35c9-147">French</span></span>
    
  - <span data-ttu-id="e35c9-148">жанвиер, фéвриер, Mars, Аврил, Чиангмай, жуин жуиллет, аоûт, септембре, октобре, Новембре, дéцембре</span><span class="sxs-lookup"><span data-stu-id="e35c9-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="e35c9-149">жанв.</span><span class="sxs-lookup"><span data-stu-id="e35c9-149">janv.</span></span> <span data-ttu-id="e35c9-150">фéвр.</span><span class="sxs-lookup"><span data-stu-id="e35c9-150">févr.</span></span> <span data-ttu-id="e35c9-151">режим MARS Аврил Чиангмай жуин жуил.</span><span class="sxs-lookup"><span data-stu-id="e35c9-151">mars avril mai juin juil.</span></span> <span data-ttu-id="e35c9-152">аоûт сентября.</span><span class="sxs-lookup"><span data-stu-id="e35c9-152">août sept.</span></span> <span data-ttu-id="e35c9-153">развертывания.</span><span class="sxs-lookup"><span data-stu-id="e35c9-153">oct.</span></span> <span data-ttu-id="e35c9-154">ноября.</span><span class="sxs-lookup"><span data-stu-id="e35c9-154">nov.</span></span> <span data-ttu-id="e35c9-155">дéк.</span><span class="sxs-lookup"><span data-stu-id="e35c9-155">déc.</span></span>
    
- <span data-ttu-id="e35c9-156">немецкий;</span><span class="sxs-lookup"><span data-stu-id="e35c9-156">German</span></span>
    
  - <span data-ttu-id="e35c9-157">жäнуар, фебруар, мäрз, Апрель, Чиангмай, жуни Жули, Август, Сентябрь, Октобер, Ноябрь, дезембер</span><span class="sxs-lookup"><span data-stu-id="e35c9-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="e35c9-158">Янв./Жäн.</span><span class="sxs-lookup"><span data-stu-id="e35c9-158">Jan./Jän.</span></span> <span data-ttu-id="e35c9-159">Фев. Мäрз Apr. Чиангмай Жуни Жули Авг. Сентябрь. Окт.</span><span class="sxs-lookup"><span data-stu-id="e35c9-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="e35c9-160">Ноя. дез.</span><span class="sxs-lookup"><span data-stu-id="e35c9-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="e35c9-161">итальянский;</span><span class="sxs-lookup"><span data-stu-id="e35c9-161">Italian</span></span>
    
  - <span data-ttu-id="e35c9-162">женнаио, феббраио, Марзо, Апрель, маггио, гиугно, луглио, Агосто, Сеттембре, Оттобре, Новембре, дицембре</span><span class="sxs-lookup"><span data-stu-id="e35c9-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="e35c9-163">Женн.</span><span class="sxs-lookup"><span data-stu-id="e35c9-163">genn.</span></span> <span data-ttu-id="e35c9-164">феббр.</span><span class="sxs-lookup"><span data-stu-id="e35c9-164">febbr.</span></span> <span data-ttu-id="e35c9-165">Мар.</span><span class="sxs-lookup"><span data-stu-id="e35c9-165">mar.</span></span> <span data-ttu-id="e35c9-166">Апрель.</span><span class="sxs-lookup"><span data-stu-id="e35c9-166">apr.</span></span> <span data-ttu-id="e35c9-167">Магг.</span><span class="sxs-lookup"><span data-stu-id="e35c9-167">magg.</span></span> <span data-ttu-id="e35c9-168">гиугно луглио AG.</span><span class="sxs-lookup"><span data-stu-id="e35c9-168">giugno luglio ag.</span></span> <span data-ttu-id="e35c9-169">Переключател.</span><span class="sxs-lookup"><span data-stu-id="e35c9-169">sett.</span></span> <span data-ttu-id="e35c9-170">and.</span><span class="sxs-lookup"><span data-stu-id="e35c9-170">ott.</span></span> <span data-ttu-id="e35c9-171">ноября.</span><span class="sxs-lookup"><span data-stu-id="e35c9-171">nov.</span></span> <span data-ttu-id="e35c9-172">DIC.</span><span class="sxs-lookup"><span data-stu-id="e35c9-172">dic.</span></span>
    
- <span data-ttu-id="e35c9-173">Португальский</span><span class="sxs-lookup"><span data-stu-id="e35c9-173">Portuguese</span></span>
    
  - <span data-ttu-id="e35c9-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="e35c9-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="e35c9-175">Янв Фев Mar, Чиангмай, 2004 июня, назад, Настройка ноября Ноя дез</span><span class="sxs-lookup"><span data-stu-id="e35c9-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="e35c9-176">испанский;</span><span class="sxs-lookup"><span data-stu-id="e35c9-176">Spanish</span></span>
    
  - <span data-ttu-id="e35c9-177">енеро, фебреро, Марзо, Абрил, Майо, Жунио, Жулио, Агосто, септиембре, Октубре, новиембре, диЦиембре</span><span class="sxs-lookup"><span data-stu-id="e35c9-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="e35c9-178">енеро Фев.</span><span class="sxs-lookup"><span data-stu-id="e35c9-178">enero feb.</span></span> <span data-ttu-id="e35c9-179">Марзо Граничный маршрутизатор.</span><span class="sxs-lookup"><span data-stu-id="e35c9-179">marzo abr.</span></span> <span data-ttu-id="e35c9-180">Майо июня.</span><span class="sxs-lookup"><span data-stu-id="e35c9-180">mayo jun.</span></span> <span data-ttu-id="e35c9-181">июля.</span><span class="sxs-lookup"><span data-stu-id="e35c9-181">jul.</span></span> <span data-ttu-id="e35c9-182">Агосто сентября./Сет.</span><span class="sxs-lookup"><span data-stu-id="e35c9-182">agosto sept./set.</span></span> <span data-ttu-id="e35c9-183">развертывания.</span><span class="sxs-lookup"><span data-stu-id="e35c9-183">oct.</span></span> <span data-ttu-id="e35c9-184">ноября.</span><span class="sxs-lookup"><span data-stu-id="e35c9-184">nov.</span></span> <span data-ttu-id="e35c9-185">DIC.</span><span class="sxs-lookup"><span data-stu-id="e35c9-185">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="e35c9-186">Func_eu_date1 (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="e35c9-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="e35c9-187">Эта функция является устаревшей, так как она поддерживает только названия месяцев на португальском языке, которые теперь `Func_eu_date` включены в функцию, описанную выше.</span><span class="sxs-lookup"><span data-stu-id="e35c9-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="e35c9-188">Эта функция служит для поиска даты в формате, принятом в португальском языке.</span><span class="sxs-lookup"><span data-stu-id="e35c9-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="e35c9-189">Формат этой функции такой же, как `Func_eu_date`и в используемом языке.</span><span class="sxs-lookup"><span data-stu-id="e35c9-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="e35c9-190">Примеры:</span><span class="sxs-lookup"><span data-stu-id="e35c9-190">Examples:</span></span>
  
- <span data-ttu-id="e35c9-191">2 дез 2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="e35c9-192">02 дез 2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-192">02 dez 2016</span></span>
    
- <span data-ttu-id="e35c9-193">2 дез 16</span><span class="sxs-lookup"><span data-stu-id="e35c9-193">2 Dez 16</span></span>
    
- <span data-ttu-id="e35c9-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-194">2/12/2016</span></span>
    
- <span data-ttu-id="e35c9-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e35c9-195">02/12/16</span></span>
    
- <span data-ttu-id="e35c9-196">2 — дез — 2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="e35c9-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e35c9-197">2-12-16</span></span>
    
<span data-ttu-id="e35c9-198">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="e35c9-198">Accepted month names:</span></span>
  
- <span data-ttu-id="e35c9-199">Португальский</span><span class="sxs-lookup"><span data-stu-id="e35c9-199">Portuguese</span></span>
    
  - <span data-ttu-id="e35c9-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="e35c9-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="e35c9-201">Янв Фев Mar, Чиангмай, 2004 июня, назад, Настройка ноября Ноя дез</span><span class="sxs-lookup"><span data-stu-id="e35c9-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="e35c9-202">Func_eu_date2 (не рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="e35c9-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="e35c9-203">Эта функция является устаревшей, так как она поддерживает только названия в голландских месяцах, которые `Func_eu_date` теперь включены в функцию, описанную выше.</span><span class="sxs-lookup"><span data-stu-id="e35c9-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="e35c9-204">Эта функция служит для поиска даты в формате, принятом в нидерландском языке.</span><span class="sxs-lookup"><span data-stu-id="e35c9-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="e35c9-205">Формат этой функции такой же, как `Func_eu_date`и в используемом языке.</span><span class="sxs-lookup"><span data-stu-id="e35c9-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="e35c9-206">Примеры:</span><span class="sxs-lookup"><span data-stu-id="e35c9-206">Examples:</span></span>
  
- <span data-ttu-id="e35c9-207">2 Меи 2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="e35c9-208">02 Меи 2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-208">02 mei 2016</span></span>
    
- <span data-ttu-id="e35c9-209">2 Меи 16</span><span class="sxs-lookup"><span data-stu-id="e35c9-209">2 Mei 16</span></span>
    
- <span data-ttu-id="e35c9-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-210">2/12/2016</span></span>
    
- <span data-ttu-id="e35c9-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e35c9-211">02/12/16</span></span>
    
- <span data-ttu-id="e35c9-212">2 — Меи — 2016</span><span class="sxs-lookup"><span data-stu-id="e35c9-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="e35c9-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e35c9-213">2-12-16</span></span>
    
<span data-ttu-id="e35c9-214">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="e35c9-214">Accepted month names:</span></span>
  
- <span data-ttu-id="e35c9-215">голландский;</span><span class="sxs-lookup"><span data-stu-id="e35c9-215">Dutch</span></span>
    
  - <span data-ttu-id="e35c9-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="e35c9-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="e35c9-217">Февраль февраля МАарт апреля Меи июня 2004 Янв, Сен сентября, Окт ноября декабря</span><span class="sxs-lookup"><span data-stu-id="e35c9-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="e35c9-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="e35c9-218">Func_expiration_date</span></span>

<span data-ttu-id="e35c9-219">Эта функция служит для поиска даты в формате, обычно используемом для кредитных и дебетовых карт, где указывается месяц, а дни исключаются.</span><span class="sxs-lookup"><span data-stu-id="e35c9-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="e35c9-220">Эта функция будет сопоставлять даты в формате "месяц/год", "month-Year", "[название месяца] год" и "[аббревиатура] год".</span><span class="sxs-lookup"><span data-stu-id="e35c9-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="e35c9-221">Полные или сокращенные названия месяцев вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="e35c9-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="e35c9-222">Примеры:</span><span class="sxs-lookup"><span data-stu-id="e35c9-222">Examples:</span></span>
  
- <span data-ttu-id="e35c9-223">ММ/ГГ (например, 01/11 или 1/11);</span><span class="sxs-lookup"><span data-stu-id="e35c9-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="e35c9-224">ММ/ГГГГ (например, 01/2011 или 1/2011);</span><span class="sxs-lookup"><span data-stu-id="e35c9-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="e35c9-225">ММ-ГГ (например, 01-22 или 1-11);</span><span class="sxs-lookup"><span data-stu-id="e35c9-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="e35c9-226">ММ-ГГГГ (например, 01-2000 или 1-2000).</span><span class="sxs-lookup"><span data-stu-id="e35c9-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="e35c9-227">Следующие форматы поддерживают ГГ или ГГГГ:</span><span class="sxs-lookup"><span data-stu-id="e35c9-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="e35c9-228">Месяц-ГГГГ (например, янв-2010, январь-2010, янв-10 или январь-10);</span><span class="sxs-lookup"><span data-stu-id="e35c9-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="e35c9-229">Месяц ГГГГ (например, "январь 2010", "янв 2010", "январь 10" или "янв 10");</span><span class="sxs-lookup"><span data-stu-id="e35c9-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="e35c9-230">МесяцГГГГ (например, "январь2010", "янв2010", "январь10" или "янв10");</span><span class="sxs-lookup"><span data-stu-id="e35c9-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="e35c9-231">Month/гггг, например, "Январь/2010" или "Янв/2010" или "Январь/10" или "Янв/10"</span><span class="sxs-lookup"><span data-stu-id="e35c9-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="e35c9-232">Принятые названия месяцев:</span><span class="sxs-lookup"><span data-stu-id="e35c9-232">Accepted month names:</span></span>
  
- <span data-ttu-id="e35c9-233">английский;</span><span class="sxs-lookup"><span data-stu-id="e35c9-233">English</span></span>
    
  - <span data-ttu-id="e35c9-234">Январь, Февраль, Март, Апрель, Май, Июнь, Июль, Август, Сентябрь, Октябрь, Ноябрь, Декабрь</span><span class="sxs-lookup"><span data-stu-id="e35c9-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e35c9-235">Февраль февраля Mar апреля, Май, Сентябрь октября октября, Май</span><span class="sxs-lookup"><span data-stu-id="e35c9-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="e35c9-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="e35c9-236">Func_us_address</span></span>

<span data-ttu-id="e35c9-p113">Эта функция служит для поиска названия штата США или его почтовой аббревиатуры вместе с почтовым индексом в том же виде, в котором они указываются в почтовых адресах. Необходимо указать правильный почтовый индекс, соответствующий названию штата США или его аббревиатуре. Название штата США и почтовый индекс не должны разделяться знаками пунктуации или буквами.</span><span class="sxs-lookup"><span data-stu-id="e35c9-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="e35c9-240">Примеры:</span><span class="sxs-lookup"><span data-stu-id="e35c9-240">Examples:</span></span>
  
- <span data-ttu-id="e35c9-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="e35c9-241">Washington 98052</span></span>
    
- <span data-ttu-id="e35c9-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="e35c9-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="e35c9-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="e35c9-243">WA 98052</span></span>
    
- <span data-ttu-id="e35c9-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="e35c9-244">WA 98052-9998</span></span>
    

