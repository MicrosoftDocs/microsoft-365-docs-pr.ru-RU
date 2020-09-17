---
title: Аналитика надежности
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950346"
---
# <a name="reliability-insights"></a><span data-ttu-id="c97bf-103">Аналитика надежности</span><span class="sxs-lookup"><span data-stu-id="c97bf-103">Reliability insights</span></span>

<span data-ttu-id="c97bf-104">В этом представлении вы найдете сведения о работоспособности управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="c97bf-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="c97bf-105">Чтобы просмотреть данные о надежности, перейдите на вкладку **надежность** .</span><span class="sxs-lookup"><span data-stu-id="c97bf-105">To view reliability data, select the **Reliability** tab.</span></span>


![Область стабильности: надежность на устройствах в левом верхнем углу, надежность с графиком времени в верхнем правом углу таблица "основные проблемы" в нижней части.](../../media/insights_reliability.png)

<span data-ttu-id="c97bf-108">В разделе " **надежность на устройствах** " представлено краткое описание развертывания за последние 14 дней с учетом процента устройств, которые считаются работоспособными, и среднее время, прошедшее с момента последней ошибки в отчете.</span><span class="sxs-lookup"><span data-stu-id="c97bf-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="c97bf-109">На графике **надежности** в правой части отчета количество устройств с критическими ошибками и общее количество обнаруженных критических ошибок с течением времени.</span><span class="sxs-lookup"><span data-stu-id="c97bf-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="c97bf-110">В разделе **Top** Details подробные сведения об определенных обнаруженных проблемах, влияющих на 5% управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="c97bf-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="c97bf-111">В отчет включаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="c97bf-111">Reported details include:</span></span>

- <span data-ttu-id="c97bf-112">Тип вопроса</span><span class="sxs-lookup"><span data-stu-id="c97bf-112">The type of issue</span></span>
    - <span data-ttu-id="c97bf-113">Сбои приложений, в результате которых приложение перестает работать или неожиданно прекращает работу</span><span class="sxs-lookup"><span data-stu-id="c97bf-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="c97bf-114">Зависание приложения, в котором приложение перестает отвечать на входные данные</span><span class="sxs-lookup"><span data-stu-id="c97bf-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="c97bf-115">Критические ошибки, возникающие при обнаружении проблемы в Windows, не могут быть восстановлены из</span><span class="sxs-lookup"><span data-stu-id="c97bf-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="c97bf-116">Количество устройств, на которые распространяется одна и та же проблема</span><span class="sxs-lookup"><span data-stu-id="c97bf-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="c97bf-117">Процентное отношение управляемых устройств, которые представляет число</span><span class="sxs-lookup"><span data-stu-id="c97bf-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="c97bf-118">Общее количество вхождений конкретной ошибки</span><span class="sxs-lookup"><span data-stu-id="c97bf-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="c97bf-119">Программный компонент, который является источником проблемы</span><span class="sxs-lookup"><span data-stu-id="c97bf-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="c97bf-120">Категория обнаруженной проблемы:</span><span class="sxs-lookup"><span data-stu-id="c97bf-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="c97bf-121">Браузер (EDGE, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="c97bf-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="c97bf-122">Unknown (компоненты не от Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c97bf-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="c97bf-123">Driver (аудио, графика или другие драйверы)</span><span class="sxs-lookup"><span data-stu-id="c97bf-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="c97bf-124">Производительность (резервный, G-комплекты, Microsoft Office и ее надстройки или расширения, Teams)</span><span class="sxs-lookup"><span data-stu-id="c97bf-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="c97bf-125">Мультимедиа (изображения, музыкальные приложения и видео приложения</span><span class="sxs-lookup"><span data-stu-id="c97bf-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="c97bf-126">Безопасность (компоненты безопасности Windows)</span><span class="sxs-lookup"><span data-stu-id="c97bf-126">Security (Windows security components)</span></span>
- <span data-ttu-id="c97bf-127">Текущее состояние по состоянию управляемых операций на рабочем столе Майкрософт исследует и исправлять проблему</span><span class="sxs-lookup"><span data-stu-id="c97bf-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

