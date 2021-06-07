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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739815"
---
# <a name="reliability-insights"></a><span data-ttu-id="fe084-103">Аналитика надежности</span><span class="sxs-lookup"><span data-stu-id="fe084-103">Reliability insights</span></span>

<span data-ttu-id="fe084-104">В этом представлении содержится сводка о состоянии здоровья управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="fe084-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="fe084-105">Чтобы просмотреть данные о надежности, выберите вкладку **Надежность.**</span><span class="sxs-lookup"><span data-stu-id="fe084-105">To view reliability data, select the **Reliability** tab.</span></span>


![Области надежности: надежность между устройствами в верхнем левом слева, надежность с течением времени в верхнем правом, верхняя таблица проблем в нижней части.](../../media/insights_reliability.png)

<span data-ttu-id="fe084-108">В разделе **Надежность** между устройствами предлагается краткое сводка о вашем развертывании за последние 14 дней, сообщая о проценте устройств, которые считаются "здоровыми", и о времени, наблюдаемом с момента последнего сообщения о сбое.</span><span class="sxs-lookup"><span data-stu-id="fe084-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="fe084-109">График **надежности с** течением времени справа сообщает о количестве устройств с критическими ошибками и общем количестве наблюдаемых критических ошибок с течением времени.</span><span class="sxs-lookup"><span data-stu-id="fe084-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="fe084-110">В **разделе "Главные проблемы"** подробно заданы определенные обнаруженные проблемы, которые затрагивают не менее 5% управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="fe084-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="fe084-111">В сообщении содержатся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="fe084-111">Reported details include:</span></span>

- <span data-ttu-id="fe084-112">Тип проблемы</span><span class="sxs-lookup"><span data-stu-id="fe084-112">The type of issue</span></span>
    - <span data-ttu-id="fe084-113">Сбои приложения, в которых приложение прекращает работу или неожиданно останавливается</span><span class="sxs-lookup"><span data-stu-id="fe084-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="fe084-114">Приложение зависает, когда приложение перестает отвечать на ввод</span><span class="sxs-lookup"><span data-stu-id="fe084-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="fe084-115">Критические ошибки, которые возникают при Windows проблемы, из-за которой она не может восстановиться.</span><span class="sxs-lookup"><span data-stu-id="fe084-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="fe084-116">Количество устройств, затронутых одной и той же проблемой</span><span class="sxs-lookup"><span data-stu-id="fe084-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="fe084-117">Процент управляемых устройств, число</span><span class="sxs-lookup"><span data-stu-id="fe084-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="fe084-118">Общее число случаев возникновения конкретной проблемы</span><span class="sxs-lookup"><span data-stu-id="fe084-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="fe084-119">Компонент программного обеспечения, который, как представляется, является источником проблемы</span><span class="sxs-lookup"><span data-stu-id="fe084-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="fe084-120">Категория обнаруженной проблемы:</span><span class="sxs-lookup"><span data-stu-id="fe084-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="fe084-121">Браузер (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="fe084-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="fe084-122">Неизвестные (компоненты, не в microsoft)</span><span class="sxs-lookup"><span data-stu-id="fe084-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="fe084-123">Драйвер (звук, графика или другие драйверы)</span><span class="sxs-lookup"><span data-stu-id="fe084-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="fe084-124">Производительность (Slack, G-Suites, Microsoft Office и его надстройки или расширения, Teams)</span><span class="sxs-lookup"><span data-stu-id="fe084-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="fe084-125">Мультимедиа (приложения для изображений, музыки или видео</span><span class="sxs-lookup"><span data-stu-id="fe084-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="fe084-126">Безопасность (Windows компонентов безопасности)</span><span class="sxs-lookup"><span data-stu-id="fe084-126">Security (Windows security components)</span></span>
- <span data-ttu-id="fe084-127">Текущий статус компьютеры, управляемые Майкрософт операций исследует и устраняет проблему</span><span class="sxs-lookup"><span data-stu-id="fe084-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

