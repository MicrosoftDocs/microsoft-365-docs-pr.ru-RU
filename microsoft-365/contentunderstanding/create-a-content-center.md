---
title: Создание центра контента в Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Узнайте, как создать центр контента
ms.openlocfilehash: 878319dd938f565f00a250f0b08de15641644e1c
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087443"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="d00f9-103">Создание центра контента в Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d00f9-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="d00f9-104">Чтобы создавать модели осмысления документации и управлять ими, сначала необходим центр контента.</span><span class="sxs-lookup"><span data-stu-id="d00f9-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="d00f9-105">Центр контента — это интерфейс создания модели, а также сведения о том, какие модели публикации библиотеки документов были применены.</span><span class="sxs-lookup"><span data-stu-id="d00f9-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Выбор библиотеки документов](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="d00f9-107">Центр контента по умолчанию создается во время [настройки](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="d00f9-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="d00f9-108">Но администратор SharePoint может при необходимости создавать и дополнительные центры.</span><span class="sxs-lookup"><span data-stu-id="d00f9-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="d00f9-109">Один центр контента подходит для сред, для которых вы создаете свертывание всех моделей. Вам может потребоваться создать дополнительные центры для нескольких отделов в организации, у которых могут быть различные потребности и разрешения на доступ к их моделям.</span><span class="sxs-lookup"><span data-stu-id="d00f9-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="d00f9-110">Администратор SharePoint может создать сайт центра контента так же, как и [любой другой сайт SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) через панель подготовки сайта центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="d00f9-110">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="d00f9-111">Чтобы создать нового центр контента:</span><span class="sxs-lookup"><span data-stu-id="d00f9-111">To create a new content center:</span></span>

1. <span data-ttu-id="d00f9-112">В Центре администрирования Microsoft 365 перейдите в центр администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d00f9-112">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="d00f9-113">В центре администрирования SharePoint в разделе **Сайты** выберите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="d00f9-113">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="d00f9-114">На странице **Активные сайты** нажмите кнопку **Создать**, а затем выберите **Другие параметры**.</span><span class="sxs-lookup"><span data-stu-id="d00f9-114">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="d00f9-115">В меню **Выбор шаблона** выберите пункт **Центр контента**.</span><span class="sxs-lookup"><span data-stu-id="d00f9-115">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="d00f9-116">Для нового сайта укажите **имя сайта**, **основного администратора**, а также **язык**.</span><span class="sxs-lookup"><span data-stu-id="d00f9-116">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="d00f9-117">Для отображения сайта центра контента можно выбрать любой из доступных языков, однако обратите внимание, что модели можно создавать только для англоязычных файлов.</span><span class="sxs-lookup"><span data-stu-id="d00f9-117">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="d00f9-118">Также учтите, что язык сайта по умолчанию нельзя изменить после создания сайта.</span><span class="sxs-lookup"><span data-stu-id="d00f9-118">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="d00f9-119">Выберите **Завершено**.</span><span class="sxs-lookup"><span data-stu-id="d00f9-119">Select **Finished**.</span></span>
 
<span data-ttu-id="d00f9-120">После создания сайта центра контента он появится на странице **Активные сайты** в центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d00f9-120">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="d00f9-121">Предоставление доступа для дополнительных пользователей</span><span class="sxs-lookup"><span data-stu-id="d00f9-121">Give access to additional users</span></span>
 
<span data-ttu-id="d00f9-122">Создав сайт, вы сможете предоставлять доступ к нему для других пользователей с помощью стандартной [модели разрешений сайта SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="d00f9-122">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="d00f9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d00f9-123">See Also</span></span>
[<span data-ttu-id="d00f9-124">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="d00f9-124">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="d00f9-125">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="d00f9-125">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d00f9-126">Создание центра управления контентом</span><span class="sxs-lookup"><span data-stu-id="d00f9-126">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="d00f9-127">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="d00f9-127">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="d00f9-128">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="d00f9-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="d00f9-129">Применение модели</span><span class="sxs-lookup"><span data-stu-id="d00f9-129">Apply a model</span></span>](apply-a-model.md)    
