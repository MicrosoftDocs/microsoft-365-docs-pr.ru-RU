---
title: Анализ регрессии ЦП
description: Понимание результатов регрессии и показателей потребления ЦП
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
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322994"
---
# <a name="intelligent-cpu-regression-analysis"></a><span data-ttu-id="4f0d2-103">Интеллектуальный анализ регрессии ЦП</span><span class="sxs-lookup"><span data-stu-id="4f0d2-103">Intelligent CPU regression analysis</span></span>

<span data-ttu-id="4f0d2-104">Использование ЦП может указывать, влияет ли приложение на обновление операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-104">CPU utilization can indicate whether an application is affected by an operating system update.</span></span> 

<span data-ttu-id="4f0d2-105">Тестовая база для Microsoft 365 предоставляет разработчикам программного обеспечения представление о регрессии производительности ЦП, которые происходят при запуске их приложения в различных версиях предстоящего обновления Windows операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="4f0d2-105">Test Base for Microsoft 365 provides software developers with an insight into CPU performance regressions which occur when their application is running on different versions of an upcoming Windows Operating System (OS) update.</span></span> 

<span data-ttu-id="4f0d2-106">Эти регрессии ЦП позволяют разработчикам обнаруживать и устранять проблемы с приложениями (и потенциальные сбои) до широкого развертывания обновления ОС, тем самым предотвращая плохое впечатление для конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-106">These CPU regressions enable developers to detect and resolve application issues (and potential failures) before the OS update is deployed broadly, thus preventing a bad experience for the end user.</span></span>


### <a name="how-cpu-regression-analysis-works"></a><span data-ttu-id="4f0d2-107">Работа анализа регрессии ЦП</span><span class="sxs-lookup"><span data-stu-id="4f0d2-107">How CPU regression analysis works</span></span> ###

<span data-ttu-id="4f0d2-108">Как пользователь тестовой базы вы можете загрузить файлы приложения (в одном файле .zip), а также связанные тестовые сценарии и выбрать версию ОС Windows, на которой вы хотите протестировать свое приложение на портале Test Base в Azure.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-108">As a Test Base user, you can upload your application's binaries (in a single .zip file), along with associated test scripts and select the Windows OS version against which you would like to test your application on the Test Base portal on Azure.</span></span> 

<span data-ttu-id="4f0d2-109">Затем служба тестовой базы запускает тестовые сценарии и выполняет анализ регрессии **ЦП.**</span><span class="sxs-lookup"><span data-stu-id="4f0d2-109">The Test Base service then runs the test scripts and performs the **CPU Regression Analysis**.</span></span> 

<span data-ttu-id="4f0d2-110">Служба проверяет, является ли использование ЦП для приложения в предварительной версии обновления для целевой ОС соответствием с использованием ЦП для выпущенной версии ОС.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-110">The service checks if the CPU utilization for the application on the pre-release version of the update for the target OS is in line with the CPU utilization for the released version of the OS.</span></span> 

<span data-ttu-id="4f0d2-111">Использование ЦП не является 100%-ным сравнением, так как процессы, запущенные в двух версиях ОС, могут быть или не совпадать точно из-за различных версий ОС; Однако анализ, выполняемый тестовой базой, может показать, влияет ли использование ЦП для приложения на предстоящее обновление ОС и какие процессы отступили от предыдущих тестовых запусков.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-111">CPU utilization is not a 100% like-for-like comparison because the processes running on the two versions of the OS may or may not be an exact match due to differing OS versions; however, the analysis performed by Test Base can show you whether CPU utilization for your application is impacted by an upcoming OS update and specifically which processes have regressed from previous test runs.</span></span>

<span data-ttu-id="4f0d2-112">На снимке ниже приведены два выпуска ОС, с которыми сравниваются использование ЦП для одного приложения.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-112">In the snapshot below, there are two OS releases against which the CPU utilizations are compared for the same application.</span></span> 
-   <span data-ttu-id="4f0d2-113">На вкладке использования ЦП показаны верхние и нижние границы использования обоих выпусков на уровне 90 и 10 процентил соответственно.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-113">The CPU utilization tab shows the upper and lower bounds of utilization for both releases at 90th and 10th percentiles respectively.</span></span> 
-   <span data-ttu-id="4f0d2-114">На графиках покажут временную серию использования ЦП наряду со средним использованием.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-114">The graphs show the time series of CPU utilization along with the average utilization.</span></span> 

<span data-ttu-id="4f0d2-115">Теперь пользователи могут использовать эти функции, чтобы определить, влияет ли использование ЦП приложения на обновления ОС и какие процессы отступили от предыдущего выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-115">Customers can now use the functionality to determine if their application's CPU utilization is impacted by OS updates and specifically which processes have regressed from their previous execution.</span></span>


![Анализ регрессии ЦП](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a><span data-ttu-id="4f0d2-117">Идентификация соответствующих процессов</span><span class="sxs-lookup"><span data-stu-id="4f0d2-117">Relevant Process Identification</span></span> ###

<span data-ttu-id="4f0d2-118">Здесь мы обсудим, как определить регрессивные процессы в приложении.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-118">Here, we discuss how to identify regressed processes in the application.</span></span> 

<span data-ttu-id="4f0d2-119">Анализ регрессии производительности требует отслеживания различных типов счетчиков производительности для каждого процесса, запущенного на виртуальной машине во время тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-119">Analyzing performance regression requires tracking different kinds of performance counters for every process running on a virtual machine during the test run.</span></span> 

<span data-ttu-id="4f0d2-120">Такой анализ захватывает множество переменных для многих процессов для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-120">Such analysis captures a lot of variables for a lot of processes for a given application.</span></span> <span data-ttu-id="4f0d2-121">Не все процессы связаны с запуском или приложением.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-121">Not all processes are associated with a run or application.</span></span> <span data-ttu-id="4f0d2-122">Для решения этой задачи применяется алгоритм взаимного ранжирования информации с использованием теории вероятности и информации, чтобы выяснить, какие процессы наиболее актуальны для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-122">To work around this challenge, a mutual information ranking algorithm using probability and information theory is applied to figure out which processes are most relevant for a given application.</span></span> 

<span data-ttu-id="4f0d2-123">Приложение можно считать одним типом дискретной случайной переменной, а процесс — еще одним видом дискретной случайной переменной.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-123">An application can be considered one type of discrete random variable while a process is considered another kind of discrete random variable.</span></span> <span data-ttu-id="4f0d2-124">Связь двух случайных переменных измеряется с помощью условных вероятностей для релевантности.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-124">The association of the two random variables is measured using conditional probabilities for relevance.</span></span> 

<span data-ttu-id="4f0d2-125">Затем процессы отображаются в порядке их релевантности для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-125">Processes are then displayed in the order of their relevance for each application.</span></span> <span data-ttu-id="4f0d2-126">Можно также использовать подмножество процессов, которые можно отслеживать по умолчанию, а также соответствующие процессы для анализа регрессии ЦП.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-126">You can also favorite a subset of processes that can be monitored, by default, along with relevant processes for CPU regression analysis.</span></span> <span data-ttu-id="4f0d2-127">После обнаружения регрессии можно скачать Windows анализатора производительности и проанализировать причины регрессии производительности ЦП.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-127">Once a regression is detected, you can download the Windows Performance Analyzer toolkit and analyze reasons for CPU performance regressions.</span></span> 

<span data-ttu-id="4f0d2-128">Анализатор Windows производительности принимает журнал трассировки событий (ETL) в качестве входных данных, и эти файлы etl доступны в файлах журналов, загружаемых для тестового выполнения на портале.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-128">The Windows Performance Analyzer takes event trace log (ETL) as inputs and these .etl files are available in the log files downloadable for test runs on the portal.</span></span> <span data-ttu-id="4f0d2-129">Если вы хотите узнать больше об отладке производительности ЦП, см. Windows документации по анализатору производительности.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-129">If you would like to know more about debugging CPU performance, see the Windows Performance Analyzer documentation.</span></span>

