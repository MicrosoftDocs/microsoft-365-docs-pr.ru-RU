---
title: Добавление данных из одного набора обзоров в другой набор обзоров
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
description: Узнайте, как выбрать документы из одного набора обзоров и работать с ними по отдельности в другом наборе в Advanced eDiscovery случае.
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
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="c02f7-103">Добавление данных из одного набора для проверки в другой набор для проверки</span><span class="sxs-lookup"><span data-stu-id="c02f7-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="c02f7-104">В некоторых случаях может потребоваться выбрать документы из одного набора обзоров и работать с ними по отдельности в другом наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="c02f7-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="c02f7-105">Это особенно полезно, если вы отобрали содержимое из набора для проверки и хотите проанализировать подмножество данных.</span><span class="sxs-lookup"><span data-stu-id="c02f7-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="c02f7-106">Следуйте рабочего процесса в этой статье, чтобы добавить содержимое из одного набора обзоров в другой.</span><span class="sxs-lookup"><span data-stu-id="c02f7-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="c02f7-107">Создание набора отзывов</span><span class="sxs-lookup"><span data-stu-id="c02f7-107">Create a review set</span></span>

<span data-ttu-id="c02f7-108">Перед началом необходимо создать набор отзывов, чтобы добавить данные.</span><span class="sxs-lookup"><span data-stu-id="c02f7-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="c02f7-109">Новый набор отзывов можно добавить на **вкладке Наборы** обзоров дела.</span><span class="sxs-lookup"><span data-stu-id="c02f7-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="c02f7-110">Дополнительные сведения см. в [обзоре Create a review set.](managing-review-sets.md#create-a-review-set)</span><span class="sxs-lookup"><span data-stu-id="c02f7-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="c02f7-111">Шаг 1. Определение содержимого для добавления в другой набор обзоров</span><span class="sxs-lookup"><span data-stu-id="c02f7-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="c02f7-112">Вы можете добавить содержимое из одного набора для проверки в другой, выбрав определенные документы в исходном наборе для проверки или выбрав все элементы, возвращенные запросом набора для проверки.</span><span class="sxs-lookup"><span data-stu-id="c02f7-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="c02f7-113">Если вы добавляете выбранные элементы, выберите элементы, выберите **Действие,** а затем выберите **Добавить к другому набору отзывов.**</span><span class="sxs-lookup"><span data-stu-id="c02f7-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Добавление к другому набору обзоров в меню Action](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="c02f7-115">Шаг 2. Укажите параметры для добавления в другой набор обзоров</span><span class="sxs-lookup"><span data-stu-id="c02f7-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="c02f7-116">На странице **Добавление к другому набору параметров** обзора выберите набор отзывов, в который необходимо добавить элементы.</span><span class="sxs-lookup"><span data-stu-id="c02f7-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="c02f7-117">Выберите, добавлять ли **все результаты поиска** или **выбранные элементы.**</span><span class="sxs-lookup"><span data-stu-id="c02f7-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="c02f7-118">**Дополнительные** сведения содержат параметры, включающие все метаданные из элементов, а также сведения о том, следует ли включать теги (путем выбора контрольного окна **Метки)** из набора исходных отзывов при добавлении документов в новый набор обзоров.</span><span class="sxs-lookup"><span data-stu-id="c02f7-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Параметры добавления данных в другой набор обзоров](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="c02f7-120">После нажатия **кнопки Ок** создается новое задание (с именем **Добавление** данных в другой набор отзывов), чтобы добавить содержимое в другой набор обзоров.</span><span class="sxs-lookup"><span data-stu-id="c02f7-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="c02f7-121">Вы можете перейти на **вкладку Jobs** и отслеживать ход выполнения этой работы.</span><span class="sxs-lookup"><span data-stu-id="c02f7-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="c02f7-122">Дополнительные сведения см. в см. [в "Управление заданиями".](managing-jobs-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="c02f7-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
