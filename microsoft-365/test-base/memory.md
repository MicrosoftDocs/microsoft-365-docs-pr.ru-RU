---
title: Анализ регрессии памяти
description: Как сделать вывод о регрессии памяти
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323107"
---
# <a name="memory-regression-analysis"></a><span data-ttu-id="15e8a-103">Анализ регрессии памяти</span><span class="sxs-lookup"><span data-stu-id="15e8a-103">Memory Regression Analysis</span></span>

<span data-ttu-id="15e8a-104">Тестовая база позволяет более четко заметить значительное увеличение использования памяти в тестовых VMs, работающих с вашими приложениями.</span><span class="sxs-lookup"><span data-stu-id="15e8a-104">Test Base helps you more clearly notice significant memory usage increases in the test VMs running your apps.</span></span> <span data-ttu-id="15e8a-105">Показатели производительности, такие как использование памяти, могут свидетельствовать об общем работоспособности приложений, и мы считаем, что это добавление значительно поможет вашим приложениям работать оптимально.</span><span class="sxs-lookup"><span data-stu-id="15e8a-105">Performance metrics, such as memory usage, can be indicative of overall application health and we believe this addition will greatly help keep your apps performing optimally.</span></span>

<span data-ttu-id="15e8a-106">Ознакомьтесь с дополнительными сведениями или просмотрите это видео, чтобы быстро ознакомиться с последними улучшениями.</span><span class="sxs-lookup"><span data-stu-id="15e8a-106">Read on for more details or watch this video for a quick walk through of the latest improvements.</span></span> 

<span data-ttu-id="15e8a-107">Дополнительные сведения о возможности тестирования базы для M365 в анализе регрессии см. в справке о результатах регрессии, основанных на надежности процесса.</span><span class="sxs-lookup"><span data-stu-id="15e8a-107">For more information on Test Base for M365's ability to help with regression analysis, see Regression results based on process reliability.</span></span>

<span data-ttu-id="15e8a-108"><b>Ближе к регрессиям памяти</b></span><span class="sxs-lookup"><span data-stu-id="15e8a-108"><b>Looking closer at memory regressions</b></span></span>

<span data-ttu-id="15e8a-109">На панели мониторинга M365 показана память, потребляемая вашим приложением в новом предварительно выпущенном обновлении Windows, и сравнивает ее с памятью, используемой в последнем Windows обновлении.</span><span class="sxs-lookup"><span data-stu-id="15e8a-109">The Test Base for M365 dashboard shows the memory consumed by your application on a new pre-released Windows update and compares it with the memory used by the last released Windows update.</span></span> 

<span data-ttu-id="15e8a-110">С помощью усовершенствований этого месяца анализ регрессии памяти теперь показан в любимых процессах.</span><span class="sxs-lookup"><span data-stu-id="15e8a-110">With this month’s enhancements, memory regression analysis is now featured in your favorited processes.</span></span> <span data-ttu-id="15e8a-111">Приложения могут содержать несколько процессов, и вы можете вручную выбрать любимые процессы через вкладку Надежность. Затем наша служба определит регрессии памяти в этих любимых процессах, сравнивая тестовые запуски различных Windows обновлений.</span><span class="sxs-lookup"><span data-stu-id="15e8a-111">Applications can contain multiple processes and you can manually select your favorite processes through the Reliability tab. Our service will then identify memory regressions in these favorited processes while comparing test runs across different Windows update releases.</span></span> <span data-ttu-id="15e8a-112">При обнаружении регрессии можно легко получить сведения о регрессии.</span><span class="sxs-lookup"><span data-stu-id="15e8a-112">If a regression is detected, details about the regression are easily available.</span></span>

<span data-ttu-id="15e8a-113">Теперь рассмотрим эту функцию подробно и обсудим, как можно устранить регрессии памяти с помощью Windows анализатора производительности.</span><span class="sxs-lookup"><span data-stu-id="15e8a-113">Now let's look at this feature in detail and discuss how you can troubleshoot memory regressions using Windows Performance Analyzer.</span></span>

<span data-ttu-id="15e8a-114">Сигнал отказа, вызванный регрессией памяти, показан на панели мониторинга тестирования M365 на странице Результаты тестирования в статье Использование памяти:</span><span class="sxs-lookup"><span data-stu-id="15e8a-114">The failure signal caused by a memory regression is shown in the Test Base for M365 dashboard on the Test results page under Memory Utilization:</span></span>

![Результаты использования памяти](Media/01_memory-utilization-results.png)


<span data-ttu-id="15e8a-116">Сбой приложения из-за более высокого потребления памяти также будет отображаться на странице ```Fail``` Сводка тестов:</span><span class="sxs-lookup"><span data-stu-id="15e8a-116">Failure for the application due to higher memory consumption, will also be displayed as ```Fail``` on the Test Summary page:</span></span>

![Результаты проверки сводки](Media/02_test-summary.png)

<span data-ttu-id="15e8a-118">Предоставляя эти сигналы сбоя заранее, наша цель состоит в четком флаге потенциальных проблем, которые могут нарушить и повлиять на работу конечного пользователя для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="15e8a-118">By providing these failure signals upfront, our goal is to clearly flag potential issues that can disrupt and impact the end user experience for your application.</span></span> 

<span data-ttu-id="15e8a-119">Затем можно скачать файлы журналов и использовать Windows анализатор производительности или предпочтительный набор инструментов для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="15e8a-119">You can then download the log files and use the Windows Performance Analyzer, or your preferred toolkit, to investigate further.</span></span> <span data-ttu-id="15e8a-120">Вы также можете работать совместно с командой Test Base для M365 для устранения проблемы и предотвращения проблем, которые влияют на конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="15e8a-120">You can also work jointly with the Test Base for M365 team on remediating the issue and help prevent issues impacting end users.</span></span>

<span data-ttu-id="15e8a-121">Сигналы памяти запечатлены на вкладке Использование памяти в тестовой базе для службы M365 для всех тестовых запусков.</span><span class="sxs-lookup"><span data-stu-id="15e8a-121">Memory signals are captured in the Memory Utilization tab in the Test Base for M365 service for all test runs.</span></span> <span data-ttu-id="15e8a-122">В приведенном ниже примере показан недавний тестовый запуск с помощью бортового приложения "Стресс памяти тестирования на дым" в отношении предварительного выпуска обновления безопасности в августе 2020 г.</span><span class="sxs-lookup"><span data-stu-id="15e8a-122">The example below shows a recent test run with the onboarded application “Smoke Test Memory Stress” against the pre-release August 2020 security update.</span></span> <span data-ttu-id="15e8a-123">(Это приложение было написано нашей командой для иллюстрации регрессий памяти.)</span><span class="sxs-lookup"><span data-stu-id="15e8a-123">(This application was written by our team to illustrate memory regressions.)</span></span>

![Результаты регрессии памяти](Media/03_memory-regression%20comparison.png)

<span data-ttu-id="15e8a-125">В этом примере любимый процесс "USLTestMemoryStress.exe" в предварительном обновлении августа потреблял в среднем около 100 МБ по сравнению с выпущенной июльской версией, поэтому тестовая база для M365 выявила регрессию.</span><span class="sxs-lookup"><span data-stu-id="15e8a-125">In this example, the favorite process “USLTestMemoryStress.exe” process consumed an average of approximately 100 MB on the pre-release August update compared to the released July update, hence the Test Base for M365 identified a regression.</span></span> 

<span data-ttu-id="15e8a-126">Другие процессы, показанные здесь как "USLTestMemoryStress_Aux1.exe" и "USLTestMemoryStress_Aux2.exe", также относятся к одному приложению, но потребляют примерно такое же количество памяти для двух выпусков, чтобы они "прошли" и считались здоровыми.</span><span class="sxs-lookup"><span data-stu-id="15e8a-126">The other processes—shown here as “USLTestMemoryStress_Aux1.exe” and “USLTestMemoryStress_Aux2.exe”—also belong to the same application, but consumed approximately the same amount of memory for the two releases so they "passed" and were considered healthy.</span></span>

<span data-ttu-id="15e8a-127">Регрессия основного процесса была определена как "статистически значимой", поэтому служба сообщила об этом пользователю и выделила его.</span><span class="sxs-lookup"><span data-stu-id="15e8a-127">The regression on the main process was determined to be “statistically significant” so the service communicated and highlighted this difference to the user.</span></span> <span data-ttu-id="15e8a-128">Если сравнение не является статистически значимым, оно не будет выделено.</span><span class="sxs-lookup"><span data-stu-id="15e8a-128">If the comparison was not statistically significant, it would not be highlighted.</span></span> <span data-ttu-id="15e8a-129">Использование памяти может быть шумным, поэтому мы используем статистические модели, чтобы различать между сборками и выпусками значимые отличия от неконсекентальных различий.</span><span class="sxs-lookup"><span data-stu-id="15e8a-129">Memory utilization can be noisy, so we use statistical models to distinguish, across builds and releases, meaningful differences from inconsequential differences.</span></span> 

<span data-ttu-id="15e8a-130">Сравнение может редко быть помечено, когда нет истинной разницы (ложное срабатывание), но это необходимое решение, чтобы повысить вероятность правильного выявления регрессий (или истинных положительных результатов).)</span><span class="sxs-lookup"><span data-stu-id="15e8a-130">A comparison may rarely be flagged when there is no true difference (a false positive), but this is a necessary tradeoff to improve the likelihood of correctly identifying regressions (or true positives.)</span></span>

<span data-ttu-id="15e8a-131">Следующий шаг — понять, что стало причиной регрессии памяти.</span><span class="sxs-lookup"><span data-stu-id="15e8a-131">The next step is to understand what caused the memory regression.</span></span> <span data-ttu-id="15e8a-132">Вы можете скачать почтовые файлы для обоих исполняемых файлов из параметра Файлы журнала загрузки, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="15e8a-132">You can download the zip files for both executions from the Download log files option, as shown below.</span></span> 

<span data-ttu-id="15e8a-133">Эти почтовые файлы содержат результаты тестового запуска, в том числе результаты скрипта, а также данные о производительности ЦП, включенные в файл ETL.</span><span class="sxs-lookup"><span data-stu-id="15e8a-133">These zip files contain the results of your test run, including script results and memory and CPU performance data which is included in the ETL file.</span></span>

![Тестовые файлы регрессии памяти](Media/04_memory-regression-test-files.png)

<span data-ttu-id="15e8a-135">Вы можете скачать и отсеивать журналы для двух тестовых запусков, а затем найти файл ETL в каждой папке и переименовать их в target.etl (для тестового запуска в предварительном обновлении) и baseline.etl (для тестового запуска последнего выпущенного обновления), чтобы упростить разведку и навигацию.</span><span class="sxs-lookup"><span data-stu-id="15e8a-135">You can download and unzip the logs for the two test runs, then locate the ETL file within each folder and rename them as target.etl (for the test run on the pre-release update) and baseline.etl (for the test run on last released update) to simplify exploration and navigation.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="15e8a-136">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="15e8a-136">Next steps</span></span>

<span data-ttu-id="15e8a-137">Следующую статью необходимо приступить к пониманию интеллектуального анализа регрессии ЦП.</span><span class="sxs-lookup"><span data-stu-id="15e8a-137">Advance to the next article to get started with understanding intelligent CPU regression analysis.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="15e8a-138">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="15e8a-138">Next step</span></span>](cpu.md)

<!---
Add button for next page
-->
