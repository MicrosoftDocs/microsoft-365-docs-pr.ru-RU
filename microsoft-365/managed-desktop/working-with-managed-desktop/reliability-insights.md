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
# <a name="reliability-insights"></a><span data-ttu-id="a63d1-103">Аналитика надежности</span><span class="sxs-lookup"><span data-stu-id="a63d1-103">Reliability insights</span></span>

<span data-ttu-id="a63d1-104">В этом представлении содержится сводка по состоянию здоровья управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="a63d1-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="a63d1-105">Чтобы просмотреть данные о надежности, выберите **вкладку "Надежность".**</span><span class="sxs-lookup"><span data-stu-id="a63d1-105">To view reliability data, select the **Reliability** tab.</span></span>


![The Reliability pane: reliability across devices in upper left, reliability over time graph in upper right, top issues table across the bottom.](../../media/insights_reliability.png)

<span data-ttu-id="a63d1-108">В  разделе "Надежность на разных устройствах" приводится краткая сводка по состоянию системы за последние 14 дней с отчетом о проценте устройств, которые считаются "полезными", и времени, за который наблюдалось с момента последнего сбоя.</span><span class="sxs-lookup"><span data-stu-id="a63d1-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="a63d1-109">На **графике надежности** по времени справа сообщается количество устройств с критическими ошибками и общее количество наблюдаемых критических ошибок с течением времени.</span><span class="sxs-lookup"><span data-stu-id="a63d1-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="a63d1-110">В **разделе "Главные проблемы"** подробно даны сведения об обнаруженных проблемах, затрагивающих не менее 5 % управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="a63d1-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="a63d1-111">В этом сообщении содержатся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a63d1-111">Reported details include:</span></span>

- <span data-ttu-id="a63d1-112">Тип проблемы</span><span class="sxs-lookup"><span data-stu-id="a63d1-112">The type of issue</span></span>
    - <span data-ttu-id="a63d1-113">Сбой приложения, в котором приложение перестает работать или неожиданно останавливается</span><span class="sxs-lookup"><span data-stu-id="a63d1-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="a63d1-114">Приложение зависает, когда приложение перестает отвечать на ввод</span><span class="sxs-lookup"><span data-stu-id="a63d1-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="a63d1-115">Критические ошибки, которые возникают, когда Windows столкнулась с проблемой, из которой не удалось восстановиться</span><span class="sxs-lookup"><span data-stu-id="a63d1-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="a63d1-116">Количество устройств, затронутых одной проблемой</span><span class="sxs-lookup"><span data-stu-id="a63d1-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="a63d1-117">Процент управляемых устройств, которые представляют собой число</span><span class="sxs-lookup"><span data-stu-id="a63d1-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="a63d1-118">Общее количество вхождений конкретной проблемы</span><span class="sxs-lookup"><span data-stu-id="a63d1-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="a63d1-119">Программный компонент, который, по-видимому, является источником проблемы</span><span class="sxs-lookup"><span data-stu-id="a63d1-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="a63d1-120">Категория обнаруженной проблемы:</span><span class="sxs-lookup"><span data-stu-id="a63d1-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="a63d1-121">Браузер (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="a63d1-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="a63d1-122">Unknown (компоненты, не относяющиеся к Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="a63d1-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="a63d1-123">Драйвер (звук, графика или другие драйверы)</span><span class="sxs-lookup"><span data-stu-id="a63d1-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="a63d1-124">Производительность (Slack, G-Suites, Microsoft Office и его надстройки или расширения, Teams)</span><span class="sxs-lookup"><span data-stu-id="a63d1-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="a63d1-125">Мультимедиа (изображения, музыка или видео приложения</span><span class="sxs-lookup"><span data-stu-id="a63d1-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="a63d1-126">Безопасность (компоненты безопасности Windows)</span><span class="sxs-lookup"><span data-stu-id="a63d1-126">Security (Windows security components)</span></span>
- <span data-ttu-id="a63d1-127">Текущее состояние операций microsoft Managed Desktop Operations для изучения и устранения проблемы</span><span class="sxs-lookup"><span data-stu-id="a63d1-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

