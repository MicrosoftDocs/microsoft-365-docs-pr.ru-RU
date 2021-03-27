---
title: Модуль прогностического кодирования для расширенных электронных открытий (предварительный просмотр)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Новый модуль прогностического кодирования в Advanced eDiscovery использует машинное обучение для анализа документов в наборе обзоров для прогнозирования документов, которые имеют отношение к вашему делу или расследованию.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382977"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="c0041-103">Модуль прогностического кодирования для расширенных электронных открытий (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="c0041-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="c0041-104">С помощью нового модуля прогностического кодирования в Advanced eDiscovery можно создать и создать модель, чтобы приоритизировать обзор документов, начиная с наиболее релевантной документации.</span><span class="sxs-lookup"><span data-stu-id="c0041-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="c0041-105">Чтобы начать работу, можно создать модель, наметить не более 50 документов, а затем фильтровать документы с помощью оценки прогнозирования модели, чтобы просмотреть соответствующие не соответствующие документы.</span><span class="sxs-lookup"><span data-stu-id="c0041-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="c0041-106">Ниже представлен краткий обзор рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c0041-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="c0041-107">Откройте модуль прогностического кодирования в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="c0041-107">Open the predictive coding module in a review set.</span></span>

   ![Щелкните список Анализ выпаданий в обзоре, чтобы перейти к модульу прогнозирования кодирования](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="c0041-109">На странице **Модели прогностического кодирования** нажмите **кнопку Новая** модель, чтобы создать новую модель прогностического кодирования.</span><span class="sxs-lookup"><span data-stu-id="c0041-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![Создание новой модели](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="c0041-111">Пометить не менее 50 документов как **релевантные** или **не релевантные.**</span><span class="sxs-lookup"><span data-stu-id="c0041-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="c0041-112">Эта маркировка используется для подготовки системы.</span><span class="sxs-lookup"><span data-stu-id="c0041-112">This labeling is used to train the system.</span></span>

   ![Метка документов как релевантные или не соответствующие для подготовки системы](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="c0041-114">Применить фильтр **оценки прогноза** для модели к набору отзывов.</span><span class="sxs-lookup"><span data-stu-id="c0041-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="c0041-115">Для этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="c0041-115">To do this:</span></span>

   1. <span data-ttu-id="c0041-116">В наборе обзоров щелкните **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="c0041-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="c0041-117">На странице **флажок** Фильтры разоберите раздел **Analytics/ML,** а затем выберите флажок **Оценки** прогноза для модели, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="c0041-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="c0041-118">В **фильтре показателей прогноза** укажите оценку прогноза.</span><span class="sxs-lookup"><span data-stu-id="c0041-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="c0041-119">Фильтр отображает документы в наборе отзывов, соответствующие оценке прогноза.</span><span class="sxs-lookup"><span data-stu-id="c0041-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![Укажите оценку прогнозирования для фильтрации документов](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="c0041-121">Отслеживайте производительность, состояние и стабильность модели.</span><span class="sxs-lookup"><span data-stu-id="c0041-121">Monitor the performance, status, and stability of your model.</span></span>

   ![Мониторинг производительности, состояния и стабильности модели](..\media\PredictiveCoding5.png)
