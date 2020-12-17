---
title: Использование таксономии банка терминов при создании средства извлечения
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Используйте таксономию банка терминов при создании средства извлечения в модели осмысления документации в Microsoft SharePoint Syntex.
ms.openlocfilehash: a8078e6ff2d2ecd0f98c22b602a54675f7d62816
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701099"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="039e6-103">Использование таксономии банка терминов при создании средства извлечения</span><span class="sxs-lookup"><span data-stu-id="039e6-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="039e6-104">При создании средства извлечения в модели осмысления документации в SharePoint Syntex можно использовать таксономию банка терминов [служб управляемых метаданных](https://docs.microsoft.com/sharepoint/managed-metadata#terms) для отображения предпочитаемых терминов для извлекаемых данных.</span><span class="sxs-lookup"><span data-stu-id="039e6-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="039e6-105">В качестве примера модель определяет и классифицирует все документы **контракта**, отправленные в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="039e6-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="039e6-106">Кроме того, модель также извлекает значение **службы контракта** из каждого контракта и отображает его в столбце в представлении библиотеки.</span><span class="sxs-lookup"><span data-stu-id="039e6-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="039e6-107">Среди различных значений служб контрактов есть несколько старых значений, которые компания больше не использует, и которые были переименованы.</span><span class="sxs-lookup"><span data-stu-id="039e6-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="039e6-108">Например, все ссылки на значения служб контрактов *Дизайн*, *Графика* и *Топография* должны быть заменены ссылками на *Творческая служба*.</span><span class="sxs-lookup"><span data-stu-id="039e6-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="039e6-109">Когда модель извлекает один из устаревших терминов из документа контракта, желательно, чтобы в представлении библиотеки отображался текущий термин — "Творческая служба".</span><span class="sxs-lookup"><span data-stu-id="039e6-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="039e6-110">В приведенном ниже примере при обучении модели один образец документа содержит устаревший термин *Дизайн*.</span><span class="sxs-lookup"><span data-stu-id="039e6-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Банк терминов](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="039e6-112">Использование столбца управляемых метаданных в средстве извлечения</span><span class="sxs-lookup"><span data-stu-id="039e6-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="039e6-113">Наборы терминов настраиваются в банке терминов служб управляемых метаданных в Центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="039e6-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="039e6-114">В приведенном ниже примере [набор терминов](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) *службы контрактов* включает ряд терминов, в том числе термин *Творческая служба*.</span><span class="sxs-lookup"><span data-stu-id="039e6-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="039e6-115">В сведениях указано, что термин имеет три синонима (*Дизайн*, *Графика* и *Топография*), которые должны быть преобразованы в *Творческая служба*.</span><span class="sxs-lookup"><span data-stu-id="039e6-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![Набор терминов](../media/content-understanding/term-store.png)</br>

> [!NOTE]
>  <span data-ttu-id="039e6-117">Наборы терминов настраиваются в качестве глобальных в поле MMS центра содержимого.</span><span class="sxs-lookup"><span data-stu-id="039e6-117">Term sets are configured as global in the MMS field of the content center.</span></span>

<span data-ttu-id="039e6-118">Существует несколько причин, по которым синонимы могут использоваться в наборе терминов.</span><span class="sxs-lookup"><span data-stu-id="039e6-118">There could be a number of reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="039e6-119">Например, имеются устаревшие либо переименованные термины или отделами организации используются различные вариации при именовании.</span><span class="sxs-lookup"><span data-stu-id="039e6-119">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="039e6-120">Чтобы поле управляемых метаданных можно было выбрать при создании в модели средства извлечения, нужно [добавить его в качестве столбца сайта управляемых метаданных](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span><span class="sxs-lookup"><span data-stu-id="039e6-120">To make the managed metadata field available for you to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="039e6-121">После добавления столбец сайта можно будет выбрать при создании средства извлечения для модели.</span><span class="sxs-lookup"><span data-stu-id="039e6-121">After you add the site column, it will be available for you to select when you create the extractor for your model.</span></span>

   ![Служба контракта](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="039e6-123">После применения модели к библиотеке документов при отправке документов в библиотеку в столбце *Творческие службы* будет отображаться предпочитаемый термин (*Творческая служба*), если средство извлечения найдет одно из значений синонимов (*Дизайн*, *Графика* или *Топография*).</span><span class="sxs-lookup"><span data-stu-id="039e6-123">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![Столбец службы контракта](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="039e6-125">См. также</span><span class="sxs-lookup"><span data-stu-id="039e6-125">See Also</span></span>
[<span data-ttu-id="039e6-126">Общие сведения об управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="039e6-126">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="039e6-127">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="039e6-127">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="039e6-128">Создание столбца управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="039e6-128">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





