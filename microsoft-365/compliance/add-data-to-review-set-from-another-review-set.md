---
title: Добавление данных из одного набора проверки в другой
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
description: ''
ms.openlocfilehash: 62acfd2240801e59447209c7cb1e41912d3dcf4d
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256756"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="9de65-102">Добавление данных в набор проверки из другого набора проверки</span><span class="sxs-lookup"><span data-stu-id="9de65-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="9de65-103">В некоторых случаях может потребоваться выбрать документы из одного набора проверки и работать с ними по отдельности в другом наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="9de65-103">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="9de65-104">Это особенно полезно, если вы использи контент из набора проверки и хотите запустить аналитику для подмножества данных.</span><span class="sxs-lookup"><span data-stu-id="9de65-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="9de65-105">Выполните действия, описанные в этой статье, чтобы добавить контент из одного набора проверки в другой.</span><span class="sxs-lookup"><span data-stu-id="9de65-105">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9de65-106">Подготовка</span><span class="sxs-lookup"><span data-stu-id="9de65-106">Before you begin</span></span>

<span data-ttu-id="9de65-107">Прежде чем начать, вам потребуется создать новый набор рецензирования, чтобы добавить данные в.</span><span class="sxs-lookup"><span data-stu-id="9de65-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="9de65-108">Новый набор проверки можно добавить на вкладке " **наборы проверки** ".</span><span class="sxs-lookup"><span data-stu-id="9de65-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="9de65-109">Дополнительные сведения можно найти [в статье Создание набора проверки](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="9de65-109">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="9de65-110">Шаг 1: Определение контента для добавления в другой набор проверки</span><span class="sxs-lookup"><span data-stu-id="9de65-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="9de65-111">Вы можете добавить содержимое из одного набора проверки в другой, выбрав определенные документы в наборе проверки источника или выбрав все элементы, возвращенные в запросе на выборку результатов проверки.</span><span class="sxs-lookup"><span data-stu-id="9de65-111">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="9de65-112">Если вы добавляете выбранные элементы, выберите их, выберите **действие**и нажмите кнопку **Добавить в другой набор рецензирования**.</span><span class="sxs-lookup"><span data-stu-id="9de65-112">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Добавить в другой набор проверки](media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="9de65-114">Шаг 2: Указание параметров для добавления в другой набор рецензирования</span><span class="sxs-lookup"><span data-stu-id="9de65-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="9de65-115">В раскрывающейся панели " **Добавить в другую проверку** " выберите набор проверок, в который нужно добавить элементы.</span><span class="sxs-lookup"><span data-stu-id="9de65-115">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="9de65-116">Выберите, нужно ли добавить **все результаты поиска** или **Выбранные элементы**.</span><span class="sxs-lookup"><span data-stu-id="9de65-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="9de65-117">**Дополнительные сведения** предоставляют параметры для включения всех метаданных из элементов и того, следует ли включать теги (устанавливая флажок **метки** ) из проверки источника при добавлении документов в новый набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="9de65-117">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Добавить в другой набор проверки](media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="9de65-119">После нажатия кнопки **ОК**создается новое задание (с именем **Добавление данных в другой набор проверки**) для добавления контента в другой набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="9de65-119">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="9de65-120">Вы можете перейти на вкладку **задания** и следить за ходом выполнения этого задания.</span><span class="sxs-lookup"><span data-stu-id="9de65-120">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="9de65-121">Более подробную информацию можно узнать в статье [Управление заданиями](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="9de65-121">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
