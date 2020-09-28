---
title: Создание центра контента в Microsoft SharePoint Синтекс
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как создать центр управления контентом.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295436"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="6cfba-103">Создание центра контента в Microsoft SharePoint Синтекс</span><span class="sxs-lookup"><span data-stu-id="6cfba-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="6cfba-104">Содержимое этой статьи предназначено для проекта Кортекс Private Preview.</span><span class="sxs-lookup"><span data-stu-id="6cfba-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="6cfba-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="6cfba-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="6cfba-106">Для создания и управления сведениями о моделях в документе необходимо, чтобы центр контента был первым.</span><span class="sxs-lookup"><span data-stu-id="6cfba-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="6cfba-107">Центр контента — это интерфейс создания модели, а также сведения о том, к каким библиотекам документов применены опубликованные модели.</span><span class="sxs-lookup"><span data-stu-id="6cfba-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Выбор библиотеки документов](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="6cfba-109">Во время [установки](set-up-content-understanding.md)создается начальный центр контента.</span><span class="sxs-lookup"><span data-stu-id="6cfba-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="6cfba-110">Кроме того, администратор SharePoint может создать дополнительные центры по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="6cfba-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="6cfba-111">Несмотря на то, что один центр обработки контента может подключаться к средам, для которых требуется выполнить сведение по всей модели, может потребоваться наличие дополнительных центров для нескольких отделов в Организации, которые могут иметь различные требования и требования к их моделям.</span><span class="sxs-lookup"><span data-stu-id="6cfba-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="6cfba-112">Администратор SharePoint может создать сайт центра контента, как, например, для [создания любого другого сайта SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) с помощью шаблона сайта.</span><span class="sxs-lookup"><span data-stu-id="6cfba-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="6cfba-113">Для создания нового центра контента:</span><span class="sxs-lookup"><span data-stu-id="6cfba-113">To create a new content center:</span></span>

1. <span data-ttu-id="6cfba-114">В центре администрирования Microsoft 365 перейдите в центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6cfba-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="6cfba-115">В центре администрирования SharePoint в разделе **сайты**выберите **активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="6cfba-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="6cfba-116">На странице **активные сайты** нажмите кнопку **создать**, а затем выберите **другие параметры**.</span><span class="sxs-lookup"><span data-stu-id="6cfba-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="6cfba-117">В меню **Выбор шаблона** выберите пункт **центр управления контентом**.</span><span class="sxs-lookup"><span data-stu-id="6cfba-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="6cfba-118">Для нового сайта укажите **имя сайта**, **основной администратор**и **язык**.</span><span class="sxs-lookup"><span data-stu-id="6cfba-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="6cfba-119">При необходимости можно выбрать сайт центра контента для отображения на любом из доступных языков.</span><span class="sxs-lookup"><span data-stu-id="6cfba-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="6cfba-120">Для английских файлов можно создавать только текущие модели.</span><span class="sxs-lookup"><span data-stu-id="6cfba-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="6cfba-121">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6cfba-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="6cfba-122">Предоставление доступа к дополнительным пользователям</span><span class="sxs-lookup"><span data-stu-id="6cfba-122">Give access to additional users</span></span>
 
<span data-ttu-id="6cfba-123">После создания сайта вы можете предоставить им дополнительные пользователи доступ к сайту с помощью стандартной [модели разрешений сайта SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="6cfba-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="6cfba-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6cfba-124">See Also</span></span>
[<span data-ttu-id="6cfba-125">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="6cfba-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="6cfba-126">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="6cfba-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="6cfba-127">[Создание центра контента](create-a-content-center.md) 
 [Общие сведения о документе](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6cfba-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="6cfba-128">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="6cfba-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="6cfba-129">Применение модели</span><span class="sxs-lookup"><span data-stu-id="6cfba-129">Apply a model</span></span>](apply-a-model.md)    
