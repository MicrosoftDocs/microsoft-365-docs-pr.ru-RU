---
title: Использование таксономии банка терминов при создании средства извлечения
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Используйте таксономию банка терминов при создании средства извлечения в модели осмысления документации в Microsoft SharePoint Syntex.
ms.openlocfilehash: b8dfc028e0a18f3345fec466ec5e0079ed2d11ce
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925348"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="cbab4-103">Использование таксономии банка терминов при создании средства извлечения</span><span class="sxs-lookup"><span data-stu-id="cbab4-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="cbab4-104">При создании средства извлечения в модели осмысления документации в SharePoint Syntex можно использовать глобальные наборы терминов в [банке терминов](/sharepoint/managed-metadata), чтобы отображать предпочитаемые термины для извлекаемых данных.</span><span class="sxs-lookup"><span data-stu-id="cbab4-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of global term sets in the [term store](/sharepoint/managed-metadata) to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="cbab4-105">В качестве примера модель определяет и классифицирует все документы **контракта**, отправленные в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="cbab4-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="cbab4-106">Кроме того, модель также извлекает значение **службы контракта** из каждого контракта и отображает его в столбце в представлении библиотеки.</span><span class="sxs-lookup"><span data-stu-id="cbab4-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="cbab4-107">Среди различных значений служб контрактов есть несколько старых значений, которые компания больше не использует, и которые были переименованы.</span><span class="sxs-lookup"><span data-stu-id="cbab4-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="cbab4-108">Например, все ссылки на значения служб контрактов *Дизайн*, *Графика* и *Топография* должны быть заменены ссылками на *Творческая служба*.</span><span class="sxs-lookup"><span data-stu-id="cbab4-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="cbab4-109">Когда модель извлекает один из устаревших терминов из документа контракта, желательно, чтобы в представлении библиотеки отображался текущий термин — "Творческая служба".</span><span class="sxs-lookup"><span data-stu-id="cbab4-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="cbab4-110">В приведенном ниже примере при обучении модели один образец документа содержит устаревший термин *Дизайн*.</span><span class="sxs-lookup"><span data-stu-id="cbab4-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Банк терминов](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="cbab4-112">Использование столбца управляемых метаданных в средстве извлечения</span><span class="sxs-lookup"><span data-stu-id="cbab4-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="cbab4-113">Наборы терминов настраиваются в банке терминов служб управляемых метаданных в Центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cbab4-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="cbab4-114">В приведенном ниже примере [набор терминов](/sharepoint/managed-metadata#term-set) *службы контрактов* включает несколько терминов, в том числе термин *Творческая служба*.</span><span class="sxs-lookup"><span data-stu-id="cbab4-114">In the example below, the *Contract Services* [term set](/sharepoint/managed-metadata#term-set) is configured to include several terms, including *Creative*.</span></span>  <span data-ttu-id="cbab4-115">В сведениях указано, что термин имеет три синонима (*Дизайн*, *Графика* и *Топография*), которые должны быть преобразованы в *Творческая служба*.</span><span class="sxs-lookup"><span data-stu-id="cbab4-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![Набор терминов](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="cbab4-117">Существует множество причин, по которым синонимы могут использоваться в наборе терминов.</span><span class="sxs-lookup"><span data-stu-id="cbab4-117">There could be many reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="cbab4-118">Например, имеются устаревшие либо переименованные термины или отделами организации используются различные вариации при именовании.</span><span class="sxs-lookup"><span data-stu-id="cbab4-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="cbab4-119">Чтобы поле управляемых метаданных можно было выбрать при создании средства извлечения в модели, нужно [добавить его в качестве столбца сайта управляемых метаданных](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span><span class="sxs-lookup"><span data-stu-id="cbab4-119">To make the managed metadata field available to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="cbab4-120">После добавления столбец сайта можно выбрать при создании средства извлечения для модели.</span><span class="sxs-lookup"><span data-stu-id="cbab4-120">After you add the site column, you can select it when you create the extractor for your model.</span></span>

   ![Служба контракта](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="cbab4-122">После применения модели к библиотеке документов при отправке документов в библиотеку в столбце *Творческие службы* будет отображаться предпочитаемый термин (*Творческая служба*), если средство извлечения найдет одно из значений синонимов (*Дизайн*, *Графика* или *Топография*).</span><span class="sxs-lookup"><span data-stu-id="cbab4-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![Столбец службы контракта](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="cbab4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="cbab4-124">See Also</span></span>
[<span data-ttu-id="cbab4-125">Общие сведения об управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="cbab4-125">Introduction to Managed Metadata</span></span>](/sharepoint/managed-metadata#terms)

[<span data-ttu-id="cbab4-126">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="cbab4-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="cbab4-127">Создание столбца управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="cbab4-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)