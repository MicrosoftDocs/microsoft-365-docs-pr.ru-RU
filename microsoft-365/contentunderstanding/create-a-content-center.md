---
title: Создание центра контента (Предварительная версия)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как создать центр управления контентом.
ms.openlocfilehash: ced47f8029079910479dd9aa5c43b39870a56aea
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537571"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="87d66-103">Создание центра контента (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="87d66-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="87d66-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="87d66-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="87d66-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="87d66-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="87d66-106">Для создания и управления сведениями о моделях в документе необходимо, чтобы центр контента был первым.</span><span class="sxs-lookup"><span data-stu-id="87d66-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="87d66-107">Центр контента — это интерфейс создания модели, а также сведения о том, какие библиотеки документов были применены к опубликованным моделям.</span><span class="sxs-lookup"><span data-stu-id="87d66-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![Выбор библиотеки документов](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="87d66-109">Во время [установки](set-up-content-understanding.md)создается начальный центр обработки контента, но администратор SharePoint может создать дополнительные компоненты по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="87d66-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="87d66-110">Несмотря на то, что один центр обработки контента может подключаться к средам, в которых вы хотите просмотреть все действия с моделью, может потребоваться дополнительная настройка, если у вас есть несколько отделов в вашей организации, которые могут иметь различные потребности и требования к их моделям.</span><span class="sxs-lookup"><span data-stu-id="87d66-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="87d66-111">Администратор SharePoint может создать сайт центра контента, как, например, для [создания любого другого сайта SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) с помощью шаблона сайта.</span><span class="sxs-lookup"><span data-stu-id="87d66-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="87d66-112">Для создания нового центра контента:</span><span class="sxs-lookup"><span data-stu-id="87d66-112">To create a new content center:</span></span>

1. <span data-ttu-id="87d66-113">В центре администрирования Microsoft 365 перейдите в центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="87d66-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="87d66-114">В центре администрирования SharePoint в разделе **сайты**выберите **активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="87d66-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="87d66-115">На странице **активные сайты** нажмите кнопку **создать**, а затем выберите **другие параметры**.</span><span class="sxs-lookup"><span data-stu-id="87d66-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="87d66-116">В меню **Выбор шаблона** выберите пункт **центр управления контентом**.</span><span class="sxs-lookup"><span data-stu-id="87d66-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="87d66-117">Для нового сайта укажите **имя сайта**, **основной администратор**и **язык**.</span><span class="sxs-lookup"><span data-stu-id="87d66-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="87d66-118">Вы можете выбрать сайт центра контента для отображения на любом из доступных языков, но обратите внимание, что в настоящее время модели можно создавать только для английских файлов.</span><span class="sxs-lookup"><span data-stu-id="87d66-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="87d66-119">Выберите пункт **Завершено**.</span><span class="sxs-lookup"><span data-stu-id="87d66-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="87d66-120">Предоставление доступа к дополнительным пользователям</span><span class="sxs-lookup"><span data-stu-id="87d66-120">Give access to additional users</span></span>
 
<span data-ttu-id="87d66-121">После создания сайта вы можете предоставить им дополнительные пользователи доступ к сайту с помощью стандартной [модели разрешений сайта SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="87d66-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="87d66-122">См. также</span><span class="sxs-lookup"><span data-stu-id="87d66-122">See Also</span></span>
[<span data-ttu-id="87d66-123">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="87d66-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="87d66-124">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="87d66-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="87d66-125">[Создание центра контента](create-a-content-center.md) 
 [Общие сведения о документе](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="87d66-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="87d66-126">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="87d66-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="87d66-127">Применение модели</span><span class="sxs-lookup"><span data-stu-id="87d66-127">Apply a model</span></span>](apply-a-model.md)    




