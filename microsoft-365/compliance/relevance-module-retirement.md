---
title: Выход на пенсию модуля релевантности в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: Модуль Релевантность в Advanced eDiscovery будет отменен 10 марта 2021 г. В этой статье рассказывается о том, что нужно сделать до того, как релевантность будет отменена. В частности, завершив все незавершенные модели, выстроив вычисление Batch, чтобы можно было сохранить метаданные из модели.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822001"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="0f51e-105">Выход на пенсию модуля Релевантность в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0f51e-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="0f51e-106">10 марта 2021 г. мы удаляем модуль Релевантность в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0f51e-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="0f51e-107">Это означает, что организации больше не будут иметь доступ к модуле релевантности (путем управления набором отзывов Релевантность в случае Advanced eDiscovery) или иметь доступ к любым существующим моделям  >   релевантности.</span><span class="sxs-lookup"><span data-stu-id="0f51e-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="0f51e-108">Удаляющийся модуль релевантности будет заменен новым решением прогностического кодирования в Q2 CY 2021.</span><span class="sxs-lookup"><span data-stu-id="0f51e-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="0f51e-109">Эта новая функция позволит организациям создавать собственные модели прогностического кодирования в более простой и интуитивно понятный рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="0f51e-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="0f51e-110">Чтобы подготовиться к предстоящему выходу на пенсию, рекомендуется организациям, которые используют модуль Релевантность экспортировать выход своей модели до даты выхода на пенсию, запуская пакетный расчет для всех существующих моделей.</span><span class="sxs-lookup"><span data-stu-id="0f51e-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="0f51e-111">Все оценки релевантности из модели будут постоянно храниться в соответствующем наборе отзывов и доступны при экспорте документов.</span><span class="sxs-lookup"><span data-stu-id="0f51e-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="0f51e-112">Оценки релевантности также сохраняются в виде метаданных в файле нагрузки.</span><span class="sxs-lookup"><span data-stu-id="0f51e-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="0f51e-113">Кроме того, вы по-прежнему сможете фильтровать содержимое в наборе отзывов на основе показателей релевантности и иметь доступ ко всем метаданным, производимым вашими моделями релевантности.</span><span class="sxs-lookup"><span data-stu-id="0f51e-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="0f51e-114">Завершение незавершенных моделей</span><span class="sxs-lookup"><span data-stu-id="0f51e-114">Complete unfinished models</span></span>

<span data-ttu-id="0f51e-115">Для любых незавершенных моделей релевантности выполните оценку, обучение и пакетный расчет, чтобы можно было применить модель к документам в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="0f51e-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="0f51e-116">Завершение вычисления пакета сохранит сведения после даты выхода на пенсию модуля Релевантность.</span><span class="sxs-lookup"><span data-stu-id="0f51e-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="0f51e-117">Ниже выполните действия по завершению всех незавершенных моделей:</span><span class="sxs-lookup"><span data-stu-id="0f51e-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="0f51e-118">Обучайте модель, пока она не стабилизируется и не будет готова к вычислению batch.</span><span class="sxs-lookup"><span data-stu-id="0f51e-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="0f51e-119">См. [обучение по тегам и релевантности.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="0f51e-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="0f51e-120">На следующем скриншоте показан модуль, готовый к вычислению пакета.</span><span class="sxs-lookup"><span data-stu-id="0f51e-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="0f51e-121">Обратите внимание, что оценка и обучение завершены, и следующим шагом является запуск вычисления пакета.</span><span class="sxs-lookup"><span data-stu-id="0f51e-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Снимок экрана модели, готовой к вычислению пакета](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="0f51e-123">Запустите вычисление Пакета.</span><span class="sxs-lookup"><span data-stu-id="0f51e-123">Run the Batch calculation.</span></span> <span data-ttu-id="0f51e-124">См. [вычисление выполнения пакетных пакетов.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="0f51e-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="0f51e-125">Убедитесь, что вычисление пакета было успешным.</span><span class="sxs-lookup"><span data-stu-id="0f51e-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="0f51e-126">См. [результаты вычислений пакета.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)</span><span class="sxs-lookup"><span data-stu-id="0f51e-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="0f51e-127">Для получения помощи в завершении незавершенных моделей релевантности обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0f51e-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
