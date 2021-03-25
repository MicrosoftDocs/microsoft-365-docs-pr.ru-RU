---
title: Отчет о защите от угроз в ATP Защитника Майкрософт
description: Отслеживание обнаружения оповещений, категорий и серьезности с помощью отчета о защите от угроз
keywords: обнаружение оповещений, источник, оповещение по категориям, серьезность оповещения, классификация оповещений, определение
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ecd2df31e1e03da5134d3d4180dcba75d3cee26
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183841"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="f4e21-104">Отчет о защите от угроз в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f4e21-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f4e21-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f4e21-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4e21-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f4e21-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4e21-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4e21-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f4e21-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f4e21-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f4e21-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f4e21-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="f4e21-110">В отчете о защите от угроз содержится информация на высоком уровне о оповещениях, созданных в организации.</span><span class="sxs-lookup"><span data-stu-id="f4e21-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="f4e21-111">В отчете содержатся сведения об источниках обнаружения, категориях, серьезности, состояниях, классификациях и определениях оповещений во времени.</span><span class="sxs-lookup"><span data-stu-id="f4e21-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="f4e21-112">Панель мониторинга структурирована в два раздела:</span><span class="sxs-lookup"><span data-stu-id="f4e21-112">The dashboard is structured into two sections:</span></span>

![Изображение отчета о защите от угроз](images/threat-protection-reports.png)

<span data-ttu-id="f4e21-114">Раздел</span><span class="sxs-lookup"><span data-stu-id="f4e21-114">Section</span></span> | <span data-ttu-id="f4e21-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f4e21-115">Description</span></span> 
:---|:---
<span data-ttu-id="f4e21-116">1</span><span class="sxs-lookup"><span data-stu-id="f4e21-116">1</span></span> | <span data-ttu-id="f4e21-117">Тенденции оповещений</span><span class="sxs-lookup"><span data-stu-id="f4e21-117">Alerts trends</span></span>
<span data-ttu-id="f4e21-118">2</span><span class="sxs-lookup"><span data-stu-id="f4e21-118">2</span></span> | <span data-ttu-id="f4e21-119">Сводка оповещений</span><span class="sxs-lookup"><span data-stu-id="f4e21-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="f4e21-120">Тенденции оповещений</span><span class="sxs-lookup"><span data-stu-id="f4e21-120">Alert trends</span></span>
<span data-ttu-id="f4e21-121">По умолчанию тенденции оповещения отображают сведения об оповещении за 30-дневный период, заканчивающийся в последний полный день.</span><span class="sxs-lookup"><span data-stu-id="f4e21-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="f4e21-122">Чтобы получить более точное представление о тенденциях, происходящих в вашей организации, вы можете отладить отчетный период, отрегулив показанный период времени.</span><span class="sxs-lookup"><span data-stu-id="f4e21-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="f4e21-123">Чтобы настроить период времени, выберите диапазон времени из параметров отсев:</span><span class="sxs-lookup"><span data-stu-id="f4e21-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="f4e21-124">30 дней</span><span class="sxs-lookup"><span data-stu-id="f4e21-124">30 days</span></span>
- <span data-ttu-id="f4e21-125">3 месяцев</span><span class="sxs-lookup"><span data-stu-id="f4e21-125">3 months</span></span>
- <span data-ttu-id="f4e21-126">6 месяцев</span><span class="sxs-lookup"><span data-stu-id="f4e21-126">6 months</span></span>
- <span data-ttu-id="f4e21-127">Пользовательские</span><span class="sxs-lookup"><span data-stu-id="f4e21-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="f4e21-128">Эти фильтры применяются только в разделе тенденции оповещения.</span><span class="sxs-lookup"><span data-stu-id="f4e21-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="f4e21-129">Это не влияет на раздел сводки оповещений.</span><span class="sxs-lookup"><span data-stu-id="f4e21-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="f4e21-130">Сводка оповещений</span><span class="sxs-lookup"><span data-stu-id="f4e21-130">Alert summary</span></span>
<span data-ttu-id="f4e21-131">Хотя тенденции оповещения показывают тенденции оповещения, в сводке оповещений показана оповещенная информация, охватившая текущий день.</span><span class="sxs-lookup"><span data-stu-id="f4e21-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="f4e21-132">Сводка оповещений позволяет сверлить до определенной очереди оповещения с соответствующим фильтром, примененным к ней.</span><span class="sxs-lookup"><span data-stu-id="f4e21-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="f4e21-133">Например, щелкнув планку EDR в карточке источников обнаружения, вы сможете найти очередь оповещений с результатами, показывающими только оповещения, созданные при обнаружении EDR.</span><span class="sxs-lookup"><span data-stu-id="f4e21-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="f4e21-134">Данные, отражающиеся в сводной статье, могут быть за 180 дней до текущей даты.</span><span class="sxs-lookup"><span data-stu-id="f4e21-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="f4e21-135">Например, если сегодня 5 ноября 2019 г., данные сводного раздела будут отражать цифры, начиная с 5 мая 2019 г. по 5 ноября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="f4e21-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="f4e21-136">Фильтр, применяемый в разделе тенденции, не применяется в сводной части.</span><span class="sxs-lookup"><span data-stu-id="f4e21-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="f4e21-137">Атрибуты оповещений</span><span class="sxs-lookup"><span data-stu-id="f4e21-137">Alert attributes</span></span>
<span data-ttu-id="f4e21-138">Отчет состоит из карт, отображает следующие атрибуты оповещений:</span><span class="sxs-lookup"><span data-stu-id="f4e21-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="f4e21-139">**Источники обнаружения:** показывает сведения о датчиках и технологиях обнаружения, которые предоставляют данные, используемые Microsoft Defender для конечной точки для запуска оповещений.</span><span class="sxs-lookup"><span data-stu-id="f4e21-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="f4e21-140">**Категории угроз:** показаны типы действий угроз или атак, которые вызвали оповещения, указав возможные области фокуса для операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="f4e21-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="f4e21-141">**Серьезность**: показывает уровень серьезности оповещений, указывающее коллективное потенциальное влияние угроз на организацию и уровень реагирования, необходимый для их устранения.</span><span class="sxs-lookup"><span data-stu-id="f4e21-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="f4e21-142">**Состояние**: показывает состояние оповещений с разрешением, указывающее эффективность ответов ручного оповещения и автоматического восстановления (если включено).</span><span class="sxs-lookup"><span data-stu-id="f4e21-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="f4e21-143">**Определение &** классификации: показывает, как вы классифицировали оповещения по разрешению, классифицировали ли их как реальные угрозы (настоящие оповещения) или как неправильные обнаружения (ложные оповещения).</span><span class="sxs-lookup"><span data-stu-id="f4e21-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="f4e21-144">Эти карточки также показывают определение разрешенных оповещений, предоставляя дополнительные сведения о типах обнаруженных фактических угроз или о неправильно обнаруженных действиях.</span><span class="sxs-lookup"><span data-stu-id="f4e21-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="f4e21-145">Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="f4e21-145">Filter data</span></span>

<span data-ttu-id="f4e21-146">Используйте предоставленные фильтры, чтобы включить или исключить оповещения с определенными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="f4e21-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="f4e21-147">Эти фильтры применяются **для всех** карт в отчете.</span><span class="sxs-lookup"><span data-stu-id="f4e21-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="f4e21-148">Например, чтобы показать данные только о предупреждениях высокой степени тяжести:</span><span class="sxs-lookup"><span data-stu-id="f4e21-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="f4e21-149">В **статье Filters > строгость** выберите **High**</span><span class="sxs-lookup"><span data-stu-id="f4e21-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="f4e21-150">Убедитесь, что все другие параметры **в статье Severity** отклонились.</span><span class="sxs-lookup"><span data-stu-id="f4e21-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="f4e21-151">Нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f4e21-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="f4e21-152">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="f4e21-152">Related topic</span></span>
- [<span data-ttu-id="f4e21-153">Отчет о состоянии и соответствии требованиям к устройству</span><span class="sxs-lookup"><span data-stu-id="f4e21-153">Device health and compliance report</span></span>](machine-reports.md)
