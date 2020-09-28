---
title: Использование таксономии банка терминов при создании средства извлечения
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Используйте таксономию банка терминов при создании средства извлечения в документе Общие сведения о модели в Microsoft SharePoint Синтекс.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296011"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="acd3a-103">Использование таксономии банка терминов при создании средства извлечения</span><span class="sxs-lookup"><span data-stu-id="acd3a-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="acd3a-104">При создании средства извлечения в документе Общие сведения о модели в SharePoint Синтекс можно использовать таксономию хранилища терминов [службы управляемых метаданных](https://docs.microsoft.com/sharepoint/managed-metadata#terms) для отображения предпочтительных терминов для извлекаемых данных.</span><span class="sxs-lookup"><span data-stu-id="acd3a-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="acd3a-105">В качестве примера модель идентифицирует и классифицирует все документы **контрактов** , которые передаются в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="acd3a-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="acd3a-106">Кроме того, модель также извлекает значение **службы контракта** из каждого контракта и отображает их в столбце представления библиотеки.</span><span class="sxs-lookup"><span data-stu-id="acd3a-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="acd3a-107">Среди различных значений контрактов со службами в контрактах существует несколько более ранних значений, которые компания больше не использует и были переименованы.</span><span class="sxs-lookup"><span data-stu-id="acd3a-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="acd3a-108">Например, все ссылки на термины " *проект*", " *графика*" или " *топографи* контракты" должны теперь называться *изобретательным*.</span><span class="sxs-lookup"><span data-stu-id="acd3a-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="acd3a-109">Каждый раз, когда модель извлекает один из устаревших терминов из документа контракта, вы хотите, чтобы он отображал текущий термин — творческий вид в представлении библиотеки.</span><span class="sxs-lookup"><span data-stu-id="acd3a-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="acd3a-110">В приведенном ниже примере, в ходе обучения модели мы видим, что один из примеров документов содержит устаревший термин *дизайна*.</span><span class="sxs-lookup"><span data-stu-id="acd3a-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Банк терминов](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="acd3a-112">Синонимы наборов терминов</span><span class="sxs-lookup"><span data-stu-id="acd3a-112">Term set synonyms</span></span> 

<span data-ttu-id="acd3a-113">Наборы терминов настраиваются в хранилище терминов служб управляемых метаданных в центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="acd3a-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="acd3a-114">В приведенном ниже примере [набор терминов](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) " *контрактные службы* " настраивается на включение ряда терминов, в том числе *творческого*.</span><span class="sxs-lookup"><span data-stu-id="acd3a-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="acd3a-115">Сведения о том, как с термином состоит из трех синонимов (*конструктор*, *графика*и *топографи*), и синонимы должны быть преобразованы в *творческие*.</span><span class="sxs-lookup"><span data-stu-id="acd3a-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![Набор терминов](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="acd3a-117">В статье <Mike, здесь я не знаю, как описать это.</span><span class="sxs-lookup"><span data-stu-id="acd3a-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="acd3a-118">Какое действие сообщает модели, когда я создаю средство извлечения для извлечения и отображения столбца служб контрактов, как столбец "помечен" для использования набора терминов "управляемые метаданные" для Creative Services? ></span><span class="sxs-lookup"><span data-stu-id="acd3a-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="acd3a-119">Настройка столбца сайта библиотеки документов для поля управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="acd3a-119">Configure your document library site column for a managed metadata field</span></span>


   ![Создание управляемых метаданных](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="acd3a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="acd3a-121">See Also</span></span>
[<span data-ttu-id="acd3a-122">Общие сведения о управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="acd3a-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="acd3a-123">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="acd3a-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="acd3a-124">Создание столбца управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="acd3a-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





