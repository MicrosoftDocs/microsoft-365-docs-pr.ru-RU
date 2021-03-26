---
title: Общие сведения об обработке форм
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
description: Узнайте об обработке форм в Microsoft SharePoint Syntex
ms.openlocfilehash: e3cf8298a2db9383e5b88dde737efc84e75c7f19
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222261"
---
# <a name="form-processing-overview"></a><span data-ttu-id="7d03a-103">Общие сведения об обработке форм</span><span class="sxs-lookup"><span data-stu-id="7d03a-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="7d03a-105">Средство Microsoft SharePoint Syntex использует функцию обработки форм приложения Microsoft PowerApps [AI Builder](/ai-builder/overview) для создания моделей в библиотеках документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7d03a-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="7d03a-106">Вы можете использовать функцию обработки форм AI Builder для создания моделей ИИ, использующих технологию машинного обучения для поиска и извлечения пар вида "ключ и значение" и табличных данных из структурированных или частично структурированных документов, таких как формы и счета.</span><span class="sxs-lookup"><span data-stu-id="7d03a-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="7d03a-107">Организации часто получают большое количество счетов по различным каналам, таким как почта, факс, электронная почта и т. д. Обработка этих документов и внесение их в базу данных вручную может занимать очень много времени.</span><span class="sxs-lookup"><span data-stu-id="7d03a-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="7d03a-108">Применяя ИИ для извлечения из ваших документов текста, пар "ключ и значение" и табличных данных, функция обработки форм автоматизирует этот процесс.</span><span class="sxs-lookup"><span data-stu-id="7d03a-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="7d03a-109">Дополнительные сведения о примерах сценариев обработки форм см. в статье [Внедрение SharePoint Syntex: руководство по началу работы](./adoption-getstarted.md).</span><span class="sxs-lookup"><span data-stu-id="7d03a-109">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="7d03a-110">Например, можно создать модель обработки форм, которая найдет все заказы на покупку, загруженные в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="7d03a-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="7d03a-111">Затем вы можете извлечь из каждого заказа и отобразить не или иные сведения, представляющие для вас важность, например *Номер заказа*, *Дата* или *Общая стоимость*.</span><span class="sxs-lookup"><span data-stu-id="7d03a-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Представление библиотеки документов](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="7d03a-113">Вы можете использовать образцы файлов, чтобы обучить модель, указав, какие данные нужно извлекать из форм.</span><span class="sxs-lookup"><span data-stu-id="7d03a-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="7d03a-114">Во время обучения модель усваивает структуру ваших документов.</span><span class="sxs-lookup"><span data-stu-id="7d03a-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="7d03a-115">Чтобы приступить к работе, вам нужно всего пять форм.</span><span class="sxs-lookup"><span data-stu-id="7d03a-115">You only need five form documents to get started.</span></span> <span data-ttu-id="7d03a-116">Приложение AI Builder проанализирует ваши образцы файлов на предмет пар "ключ/значение", а те пары, которые могли быть пропущены, вы можете указать вручную.</span><span class="sxs-lookup"><span data-stu-id="7d03a-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="7d03a-117">AI Builder позволяет протестировать точность работы модели на образцах файлов.</span><span class="sxs-lookup"><span data-stu-id="7d03a-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="7d03a-118">После обучения и публикации вашей модели она создаст рабочий процесс [Power Automate Flow](/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="7d03a-118">After you train and publish your model, your model creates a [Power Automate Flow](/power-automate/getting-started).</span></span> <span data-ttu-id="7d03a-119">Этот процесс будет выполняться при загрузке файла в библиотеку документов SharePoint, извлекая данные, указанные в модели.</span><span class="sxs-lookup"><span data-stu-id="7d03a-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="7d03a-120">Извлеченные данные будут отображаться в столбцах в представлении библиотеки документов вашей модели.</span><span class="sxs-lookup"><span data-stu-id="7d03a-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="7d03a-121">Администратору Office 365 необходимо [включить функцию обработки форм](./set-up-content-understanding.md) для библиотеки документов SharePoint, чтобы пользователи могли [создавать модели обработки форм](create-a-form-processing-model.md) в этой библиотеке.</span><span class="sxs-lookup"><span data-stu-id="7d03a-121">An Office 365 admin needs to [enable Form processing](./set-up-content-understanding.md) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="7d03a-122">Вы можете выбрать сайты во время настройки или после нее в параметрах управления.</span><span class="sxs-lookup"><span data-stu-id="7d03a-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="7d03a-123">Ограничения файлов</span><span class="sxs-lookup"><span data-stu-id="7d03a-123">File limitations</span></span>

<span data-ttu-id="7d03a-124">При использовании моделей обработки форм учитывайте [требования и ограничения к применению файлов](/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="7d03a-124">When using form processing models, make sure to note the [requirements and limitations for file usage](/ai-builder/form-processing-model-requirements).</span></span>

### <a name="multi-geo-environments"></a><span data-ttu-id="7d03a-125">Среды с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="7d03a-125">Multi-Geo environments</span></span>

<span data-ttu-id="7d03a-126">При настройке службы SharePoint Syntex в среде [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md) вы можете настроить ее для обработки форм только в центральном расположении.</span><span class="sxs-lookup"><span data-stu-id="7d03a-126">When setting up SharePoint Syntex in a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), you can only configure it to use form processing in the central location.</span></span> <span data-ttu-id="7d03a-127">Если вы хотите использовать обработку форм во вспомогательном расположении, обратитесь в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7d03a-127">If you want to use form processing in a satellite location, contact Microsoft support.</span></span>






## <a name="see-also"></a><span data-ttu-id="7d03a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7d03a-128">See Also</span></span>
  
[<span data-ttu-id="7d03a-129">Документация Power Automate</span><span class="sxs-lookup"><span data-stu-id="7d03a-129">Power Automate documentation</span></span>](/power-automate/)

[<span data-ttu-id="7d03a-130">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="7d03a-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="7d03a-131">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="7d03a-131">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="7d03a-132">Учебный курс. Повышение продуктивности бизнеса с помощью AI Builder</span><span class="sxs-lookup"><span data-stu-id="7d03a-132">Training: Improve business performance with AI Builder</span></span>](/learn/paths/improve-business-performance-ai-builder/?source=learn)