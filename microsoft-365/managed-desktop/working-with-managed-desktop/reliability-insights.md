---
title: Аналитика надежности
description: ''
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1f642d2790af5f4ec83dd1bbe57a9be249d095d1
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962336"
---
# <a name="reliability-insights"></a><span data-ttu-id="52ace-103">Аналитика надежности</span><span class="sxs-lookup"><span data-stu-id="52ace-103">Reliability insights</span></span>

<span data-ttu-id="52ace-104">В этом представлении вы найдете сведения о работоспособности управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="52ace-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="52ace-105">Чтобы просмотреть данные о надежности, перейдите на вкладку **надежность** .</span><span class="sxs-lookup"><span data-stu-id="52ace-105">To view reliability data, select the **Reliability** tab.</span></span>


![Область стабильности: надежность на устройствах в левом верхнем углу, надежность с графиком времени в верхнем правом углу таблица "основные проблемы" в нижней части.](images/insights_reliability.png)

<span data-ttu-id="52ace-108">В разделе " **надежность на устройствах** " представлено краткое описание развертывания за последние 14 дней с учетом процента устройств, которые считаются работоспособными, и среднее время, прошедшее с момента последней ошибки в отчете.</span><span class="sxs-lookup"><span data-stu-id="52ace-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="52ace-109">На графике **надежности** в правой части отчета количество устройств с критическими ошибками и общее количество обнаруженных критических ошибок с течением времени.</span><span class="sxs-lookup"><span data-stu-id="52ace-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="52ace-110">В разделе **Top** Details подробные сведения об определенных обнаруженных проблемах, влияющих на 5% управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="52ace-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="52ace-111">В отчет включаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="52ace-111">Reported details include:</span></span>

- <span data-ttu-id="52ace-112">Тип вопроса</span><span class="sxs-lookup"><span data-stu-id="52ace-112">The type of issue</span></span>
    - <span data-ttu-id="52ace-113">Сбои приложений, в результате которых приложение перестает работать или неожиданно прекращает работу</span><span class="sxs-lookup"><span data-stu-id="52ace-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="52ace-114">Зависание приложения, в котором приложение перестает отвечать на входные данные</span><span class="sxs-lookup"><span data-stu-id="52ace-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="52ace-115">Критические ошибки, возникающие при обнаружении проблемы в Windows, не могут быть восстановлены из</span><span class="sxs-lookup"><span data-stu-id="52ace-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="52ace-116">Количество устройств, на которые распространяется одна и та же проблема</span><span class="sxs-lookup"><span data-stu-id="52ace-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="52ace-117">Процентное отношение управляемых устройств, которые представляет число</span><span class="sxs-lookup"><span data-stu-id="52ace-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="52ace-118">Общее количество вхождений конкретной выпуска</span><span class="sxs-lookup"><span data-stu-id="52ace-118">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="52ace-119">Программный компонент, который является источником проблемы</span><span class="sxs-lookup"><span data-stu-id="52ace-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="52ace-120">Категория обнаруженной проблемы:</span><span class="sxs-lookup"><span data-stu-id="52ace-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="52ace-121">Браузер (EDGE, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="52ace-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="52ace-122">Unknown (компоненты не от Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="52ace-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="52ace-123">Driver (аудио, графика или другие драйверы)</span><span class="sxs-lookup"><span data-stu-id="52ace-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="52ace-124">Производительность (резервный, G-комплекты, Microsoft Office и ее надстройки или расширения, Teams)</span><span class="sxs-lookup"><span data-stu-id="52ace-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="52ace-125">Мультимедиа (изображения, музыкальные приложения и видео приложения</span><span class="sxs-lookup"><span data-stu-id="52ace-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="52ace-126">Безопасность (компоненты безопасности Windows)</span><span class="sxs-lookup"><span data-stu-id="52ace-126">Security (Windows security components)</span></span>
- <span data-ttu-id="52ace-127">Текущее состояние по состоянию управляемых операций на рабочем столе Майкрософт исследует и исправлять проблему</span><span class="sxs-lookup"><span data-stu-id="52ace-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

