---
title: Добавление данных из одного набора для проверки в другой набор для проверки
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как выбирать документы из одного набора для проверки и работать с ними по отдельности в другом наборе в случае Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285184"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="682bb-103">Добавление данных в набор для проверки из другого набора для проверки</span><span class="sxs-lookup"><span data-stu-id="682bb-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="682bb-104">В некоторых случаях может потребоваться выбрать документы из одного набора для проверки и работать с ними по отдельности в другом наборе.</span><span class="sxs-lookup"><span data-stu-id="682bb-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="682bb-105">Это особенно полезно, если вы отсчитали содержимое в наборе для проверки и хотите запустить аналитику для подмножеств данных.</span><span class="sxs-lookup"><span data-stu-id="682bb-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="682bb-106">Выполните рабочий процесс в этой статье, чтобы добавить содержимое из одного набора отзывов в другой.</span><span class="sxs-lookup"><span data-stu-id="682bb-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="682bb-107">Создание набора для проверки</span><span class="sxs-lookup"><span data-stu-id="682bb-107">Create a review set</span></span>

<span data-ttu-id="682bb-108">Перед началом необходимо создать набор для проверки, в который будут добавлены данные.</span><span class="sxs-lookup"><span data-stu-id="682bb-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="682bb-109">Новый набор для проверки можно добавить на **вкладку "Наборы** проверки" дела.</span><span class="sxs-lookup"><span data-stu-id="682bb-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="682bb-110">Дополнительные сведения см. в [подстройки "Создание набора для проверки".](managing-review-sets.md#create-a-review-set)</span><span class="sxs-lookup"><span data-stu-id="682bb-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="682bb-111">Шаг 1. Определение контента для добавления в другой набор для проверки</span><span class="sxs-lookup"><span data-stu-id="682bb-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="682bb-112">Вы можете добавить содержимое из одного набора для проверки в другой, выбрав конкретные документы в наборе для проверки источника или выбрав все элементы, возвращенные запросом набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="682bb-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="682bb-113">При добавлении выбранных элементов выберите элементы, **выберите** действие, а затем выберите "Добавить в другой набор **для проверки".**</span><span class="sxs-lookup"><span data-stu-id="682bb-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Добавление в другой набор отзывов в меню "Действие"](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="682bb-115">Шаг 2. Указание параметров для добавления в другой набор для проверки</span><span class="sxs-lookup"><span data-stu-id="682bb-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="682bb-116">На странице **"Добавить в другой набор** для проверки параметров" выберите набор для проверки, в который нужно добавить элементы.</span><span class="sxs-lookup"><span data-stu-id="682bb-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="682bb-117">Выберите, следует ли добавлять **все результаты поиска** или **выбранные элементы.**</span><span class="sxs-lookup"><span data-stu-id="682bb-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="682bb-118"> Дополнительные сведения предоставляют параметры, включающие все метаданные из элементов  и то, следует ли включать теги (путем выбора пункта "Метки") из набора исходных отзывов при добавлении документов в новый набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="682bb-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Варианты добавления данных в другой набор для проверки](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="682bb-120">После нажатия **кнопки "ОК"** создается новое задание (с именем **"Добавление** данных в другой набор для проверки") для добавления содержимого в другой набор для проверки.</span><span class="sxs-lookup"><span data-stu-id="682bb-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="682bb-121">Можно перейти на **вкладку "Задания"** и отслеживать ход выполнения этого задания.</span><span class="sxs-lookup"><span data-stu-id="682bb-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="682bb-122">Дополнительные сведения см. в [под управлением заданий.](managing-jobs-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="682bb-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
