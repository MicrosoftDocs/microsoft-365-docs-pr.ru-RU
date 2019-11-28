---
title: Аналитика надежности
description: ''
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634036"
---
# <a name="reliability-insights"></a><span data-ttu-id="f5b30-103">Аналитика надежности</span><span class="sxs-lookup"><span data-stu-id="f5b30-103">Reliability insights</span></span>

<span data-ttu-id="f5b30-104">В этом представлении вы найдете сведения о работоспособности управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="f5b30-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="f5b30-105">Чтобы просмотреть данные о надежности, перейдите на вкладку **надежность** .</span><span class="sxs-lookup"><span data-stu-id="f5b30-105">To view reliability data, select the **Reliability** tab.</span></span>


![Область надежности](images/insights_reliability.png)

<span data-ttu-id="f5b30-107">В разделе " **надежность на устройствах** " представлено краткое описание развертывания за последние 14 дней с учетом процента устройств, которые считаются работоспособными, и среднее время, прошедшее с момента последней ошибки в отчете.</span><span class="sxs-lookup"><span data-stu-id="f5b30-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="f5b30-108">На графике **надежности** в правой части отчета количество устройств с критическими ошибками и общее количество обнаруженных критических ошибок с течением времени.</span><span class="sxs-lookup"><span data-stu-id="f5b30-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="f5b30-109">В разделе **Top** Details подробные сведения об определенных обнаруженных проблемах, влияющих на 5% управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="f5b30-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="f5b30-110">В отчет включаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f5b30-110">Reported details include:</span></span>

- <span data-ttu-id="f5b30-111">Тип вопроса</span><span class="sxs-lookup"><span data-stu-id="f5b30-111">The type of issue</span></span>
    - <span data-ttu-id="f5b30-112">Сбои приложений, в результате которых приложение перестает работать или неожиданно прекращает работу</span><span class="sxs-lookup"><span data-stu-id="f5b30-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="f5b30-113">Зависание приложения, в котором приложение перестает отвечать на входные данные</span><span class="sxs-lookup"><span data-stu-id="f5b30-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="f5b30-114">Критические ошибки, возникающие при обнаружении проблемы в Windows, не могут быть восстановлены из</span><span class="sxs-lookup"><span data-stu-id="f5b30-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="f5b30-115">Количество устройств, на которые распространяется одна и та же проблема</span><span class="sxs-lookup"><span data-stu-id="f5b30-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="f5b30-116">Процентное отношение управляемых устройств, которые представляет число</span><span class="sxs-lookup"><span data-stu-id="f5b30-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="f5b30-117">Общее количество вхождений конкретной выпуска</span><span class="sxs-lookup"><span data-stu-id="f5b30-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="f5b30-118">Программный компонент, который является источником проблемы</span><span class="sxs-lookup"><span data-stu-id="f5b30-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="f5b30-119">Категория обнаруженной проблемы:</span><span class="sxs-lookup"><span data-stu-id="f5b30-119">The category of the detected problem:</span></span>
    - <span data-ttu-id="f5b30-120">Браузер (EDGE, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="f5b30-120">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="f5b30-121">Unknown (компоненты не от Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f5b30-121">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="f5b30-122">Driver (аудио, графика или другие драйверы)</span><span class="sxs-lookup"><span data-stu-id="f5b30-122">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="f5b30-123">Производительность (резервный, G-комплекты, Microsoft Office и ее надстройки или расширения, Teams)</span><span class="sxs-lookup"><span data-stu-id="f5b30-123">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="f5b30-124">Мультимедиа (изображения, музыкальные приложения и видео приложения</span><span class="sxs-lookup"><span data-stu-id="f5b30-124">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="f5b30-125">Безопасность (компоненты безопасности Windows)</span><span class="sxs-lookup"><span data-stu-id="f5b30-125">Security (Windows security components)</span></span>
- <span data-ttu-id="f5b30-126">Текущее состояние по состоянию управляемых операций на рабочем столе Майкрософт исследует и исправлять проблему</span><span class="sxs-lookup"><span data-stu-id="f5b30-126">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

