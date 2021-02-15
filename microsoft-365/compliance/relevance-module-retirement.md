---
title: Выход из модуля релевантности в Advanced eDiscovery
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
ms.collection: M365-security-compliance
description: Модуль релевантности в Advanced eDiscovery будет отменен 10 марта 2021 г. В этой статье объясняется, что делать до выхода из релевантности. В частности, чтобы завершить работу с незаконченными моделями, вы можете использовать пакетное вычисление, чтобы сохранить метаданные из модели.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122538"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="3172d-105">Выход из модуля релевантности в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3172d-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="3172d-106">10 марта 2021 г. мы удаляем модуль релевантности в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3172d-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="3172d-107">Это означает, что у организаций больше не будет доступа к модуле релевантности (путем управления релевантность набора проверки в случае  >   Advanced eDiscovery) или у организаций будет доступ к существующим моделям релевантности.</span><span class="sxs-lookup"><span data-stu-id="3172d-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="3172d-108">Текущий отозвляющийся модуль релевантности будет заменен новым решением прогнозирования кодирования в Q2 CY 2021.</span><span class="sxs-lookup"><span data-stu-id="3172d-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="3172d-109">Эта новая функциональность позволит организациям создавать собственные модели прогнозирования кодирования в более простом и интуитивно понятном рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3172d-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="3172d-110">Для подготовки к предстоящему выводу из системы рекомендуется организациям, которые используют модуль релевантности, экспортировать выходные данные модели до даты выхода из системы путем пакетного вычисления для всех существующих моделей.</span><span class="sxs-lookup"><span data-stu-id="3172d-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="3172d-111">Все показатели релевантности из модели будут постоянно храниться в соответствующем наборе для проверки и доступны при экспорте документов.</span><span class="sxs-lookup"><span data-stu-id="3172d-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="3172d-112">Оценки релевантности также сохраняются в виде метаданных в файле загрузки.</span><span class="sxs-lookup"><span data-stu-id="3172d-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="3172d-113">Кроме того, вы по-прежнему сможете фильтровать содержимое в наборе для проверки на основе оценки релевантности и иметь доступ ко всем метаданным моделей релевантности.</span><span class="sxs-lookup"><span data-stu-id="3172d-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="3172d-114">Завершение незаконченных моделей</span><span class="sxs-lookup"><span data-stu-id="3172d-114">Complete unfinished models</span></span>

<span data-ttu-id="3172d-115">Для любых незавершенных моделей релевантности выполните оценку, обучение и пакетное вычисление, чтобы применить модель к документам в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="3172d-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="3172d-116">При выполнении пакетного вычисления данные сохраняются после даты выхода из модуля релевантности.</span><span class="sxs-lookup"><span data-stu-id="3172d-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="3172d-117">Чтобы выполнить все незавершенные модели, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3172d-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="3172d-118">Обучение модели до тех пор, пока она не будет стабилизируется и не будет готова к пакетным вычислениям.</span><span class="sxs-lookup"><span data-stu-id="3172d-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="3172d-119">См. [обучающие курсы по тегам и релевантности.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="3172d-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="3172d-120">На следующем снимке экрана показан модуль, готовый к пакетным вычислениям.</span><span class="sxs-lookup"><span data-stu-id="3172d-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="3172d-121">Обратите внимание, что оценка и обучение завершены, и следующим шагом является запуск пакетного вычисления.</span><span class="sxs-lookup"><span data-stu-id="3172d-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Снимок экрана: модель, готовая к пакетным вычислениям](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="3172d-123">Запустите пакетное вычисление.</span><span class="sxs-lookup"><span data-stu-id="3172d-123">Run the Batch calculation.</span></span> <span data-ttu-id="3172d-124">См. ["Выполнение пакетного вычисления".](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="3172d-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="3172d-125">Убедитесь, что пакетное вычисление было успешным.</span><span class="sxs-lookup"><span data-stu-id="3172d-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="3172d-126">См. [результаты пакетного вычисления.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)</span><span class="sxs-lookup"><span data-stu-id="3172d-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="3172d-127">За помощью в выполнении незавершенных моделей релевантности обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3172d-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
